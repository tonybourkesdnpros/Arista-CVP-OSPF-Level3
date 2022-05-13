# ATD-Lab-Reset

This is a collection of Ansible playbooks/configs, configlets (in the form of .cfg text files), and YAML files to configure the Arista ATD lab environment 
for the Arista ACE Level 3 certification course lab topology (as of July 2021). 

This will **only** work on the ATD Level 3 labs, but you can modidfy the YAML files and playbooks to suit other environments. 

The playbooks/configs/YAML files will set the Level 3 lab environment to the baseline configlet assignments: 

The playbooks will set the configlets. It will create containers (but does not delete them). 

This does **not** create the change control or execute the change control. At this time, that must be done manually by an administrator. 

## Getting Started

Make sure the CVP Ansible modules are installed 

    ansible-galaxy collection install arista.cvp:==3.2.0

Now that the environment is ready, clone the ATD-Lab-Reset repo to the ATD VS-Code environment (Terminal). 

    > git clone https://github.com/tonybourkesdnpros/Arista-CVP-OSPF-Level3
    
This will create a new directory called ATD-CVP-OSPF-Level3

Edit the inventory.yml file to reflect the password for your particular enviroment: 

<code>           ansible_password: aristaXXXX</code>

## The Playbooks

* generate_OSPF_config.yml

This creates OSPF underlay configuration from YAML

* upload_OSPF_config.yml

This uploads the OSPF underlay configuration as configlets to CVP

* apply_OSPF_config.yml

This applies the configlets to the switches

## 

To use a playbook use the command: 

    > ansible-playbook playbook/[playbook].yml
    

