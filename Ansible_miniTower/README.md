## Ansible Host setup in Azure

# What is Ansible?

`Ansible is an open-source IT automation tool that simplifies the process of configuration management, application deployment, and task automation. It uses a simple, human-readable language called YAML (Yet Another Markup Language) to define automation jobs, making it easy for both technical and non-technical users to understand and manage.`


# Key features of Ansible include:

 - Agentless: No need to install any agents on the target machines.
 - Idempotency: Ensures that repeated executions of tasks produce the same result, avoiding unintended changes.
 - Extensible: Integrates easily with various modules and plugins to extend its functionality.



How is Ansible Used?
Ansible is used to automate a wide range of IT tasks, including:

 - Configuration Management: Ensuring systems are configured consistently across environments.
 - Application Deployment: Automating the deployment of applications to multiple servers.
 - Orchestration: Coordinating multiple systems and services to work together in a specific order.
 - Provisioning: Automating the setup of new servers, virtual machines, and other infrastructure components.
 - Security and Compliance: Enforcing security policies and ensuring systems comply with regulations.



# design
![alt text](image-33.png)



# demo
![alt text](Azure_ansible_flask_vnetPeering.gif)

create a resource group to hold meta data of the vm infrastructure  

![alt text](image.png)


![alt text](image-1.png)

![alt text](image-2.png)


![alt text](image-3.png)


use mremoteng to SSH to the ubuntu host ( ansible controller server)



![alt text](image-4.png)


![alt text](image-5.png)


switch to root and setup the ansible and webapp parts

`sudo apt update`

![alt text](image-6.png)


![alt text](image-7.png)


`sudo apt install ansible`

![alt text](image-8.png)


`ansible --version`

![alt text](image-9.png)

allow nsg inbound rule to access port 5000
![alt text](image-10.png)

#----------------------------

create a new vnet for target hosts

![alt text](image-11.png)

deploy a ubuntu target host and test the connectivity

![alt text](image-12.png)


![alt text](image-13.png)

![alt text](image-14.png)

ping private IP of master from target



setup peering and check the connectivity

![alt text](image-15.png)

![alt text](image-18.png)
![alt text](image-16.png)


create a user and setup a passwordless authentication by sharing the public key in authorised manner

![alt text](image-17.png)

test the password less authentication using ansible adhoc command and with ping module
![alt text](image-20.png)


have the hosts file updated with target host's private IP

# initial testing:  web <-> Ansible functionality
![alt text](image-24.png)

## Later to update the subprocess call with the ansible playbook

# testing
![alt text](image-22.png)

![alt text](image-23.png)


# docker playbook installation
![alt text](image-27.png)

# before ansible playbook execution
![alt text](image-28.png)

# execution
![alt text](image-32.png)
![alt text](image-29.png)

# result - SUCCESS

![alt text](image-30.png)

![alt text](image-31.png)

project structure

![alt text](image-25.png)


# all  resources

![alt text](image-26.png)
 

