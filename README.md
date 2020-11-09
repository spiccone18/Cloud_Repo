## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

https://drive.google.com/file/d/1UAQuU52ZZuV-L0UtnduslCL7QOMBx3od/view?usp=sharing

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook may be used to install only certain pieces of it, such as Filebeat.

  - /Users/spiccone/Downloads/install-elk.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the applications will be highly secured and traffic is distributed, in addition to restricting access to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the file system and system configuration.
- _TODO: What does Filebeat watch for?_ collects data about the file system 
- _TODO: What does Metricbeat record?_ metric beat collects information on machine metrics, such as uptime 

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function       | IP Address     | Operating System |   |   |   |   |
|----------|----------------|----------------|------------------|---|---|---|---|
| Jump-Box | Gateway        | 10.0.0.4       | Linux            |   |   |   |   |
| Web-1    | VM - Container | 10.0.0.9       | Linux            |   |   |   |   |
| Web-2    | VM - Container | 10.0.0.10      | Linux            |   |   |   |   |
| ELK-VM   | VM monitoring  | 10.1.0.4       | Linux            |   |   |   |   |
| MRG_LB_1 | Load balancing | 20.185.177.250 | N/A              |   |   |   |   |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the jump box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_ - 72.66.118.174

Machines within the network can only be accessed by the Ansible container 
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_  10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses   |
|----------|---------------------|------------------------|
| Jump-Box | Yes                 | 72.66.118.174          |
| Web-1    | No                  | 10.0.0.4               |
| Web-2    | No                  | 10.0.0.4               |
| Elk-VM   | No                  | 10.0.0.4 72.66.118.174 |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_ Anisble's main advantage is that it saves architects time in configuration by the use of easily re-useable playbooks. 

The playbook implements the following tasks:
- Install docker
- Install pip3 which is the package instlaler for Python
- Install the Docker python module
- Set the vm.max_map_count to 262144 to allow the the target VM to use more memory
- download and launch the docker ELK container 

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

Screenshots: user/spiccone/Downloads/README 2/Images

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: 10.0.0.9 and 10.0.0.10

We have installed the following Beats on these machines:
- _TODO: Filebeat and Metricbeat

These Beats allow us to collect the following information from each machine:
- _TODO: Filebeat fowards and centralizes log data to elasitcsearch or Logstash. Filebeat moitors log files or locations we specify so we keep an accurate eye on actions, commands, updates being done on the system. Metricbeat periodically collects metrics from the OS and from other services running on the server. By using Metricbeat we have a better idea which servers are running, which arent, CPU usage, etc. 

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._