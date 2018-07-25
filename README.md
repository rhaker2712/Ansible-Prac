# Create a VM on Azure

As a practise, I just followed this simple steps to create a VM in Ansible.

## Prerequisites

To manage Azure resources with Ansible, you need the following:

* You will need to pip install ansible[azure].
* You will need ansible version 2.5.5 or higher.
* Azure credentials, and Ansible configured to use them.
  [Create Azure credentials and configure Ansible](https://docs.microsoft.com/en-us/azure/virtual-machines/linux/ansible-install-configure#create-azure-credentials)
  (I have copied the decrypted .credential file from [azure-s4hana](https://github.com/Centiq/azure-s4hana) project and then set the environment variables suggested by above link)
* Install Azure CLI version 2.0.4 or later.

## Create supporting Azure resources
  
  * $ az group create --name rt_test --location eastus
  * $ az network vnet create --resource-group rt_test --name myVnet  --address-prefix 10.0.0.0/16 --subnet-name mySubnet --subnet-prefix 10.0.1.0/24
  
 ## Create and run Ansible playbook
  
  * $ ansible-playbook azure_create_vm.yml
