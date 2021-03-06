# Terraform: 101-vm-simple-windows

## Very simple deployment of a Windows VM

### Description 
This is a conversion of ARM template *[101-vm-simple-windows](https://github.com/Azure/azure-quickstart-templates/tree/master/101-vm-simple-windows)* from the repository *[azure\azure-quickstart-templates](https://github.com/Azure/azure-quickstart-templates)* to Terraform configuration.

This configuration allows you to deploy a simple Windows VM using a few different options for the Windows version, using the latest patched version. This will deploy a A2 size VM in the resource group location and return the fully qualified domain name of the VM, and it will deploy the following resources…
 
![result](result.png)

> ### Note:
> If there is already the specified resource group exists then the script will not continue with the deployment. If you want to deploy the resources to the existing resource group, then import the resource group to state before the deployment.

### Syntax
```
# To initialize the configuration directory
PS C:\Terraform\101-vm-simple-windows> terraform init 

# To check the execution plan
PS C:\Terraform\101-vm-simple-windows> terraform plan

# To deploy the configuration
PS C:\Terraform\101-vm-simple-windows> terraform apply
```  

### Example
```
# Initialize
PS C:\Terraform\101-vm-simple-windows> terraform init 

# Plan
PS C:\Terraform\101-vm-simple-windows> terraform plan

var.adminPassword
Password for the Virtual Machine.
Enter a value: *********

<--- output truncated --->

# Apply
PS C:\Terraform\101-vm-simple-windows> terraform apply 

var.adminPassword
Password for the Virtual Machine.
Enter a value: *********
```

### Output
```
azurerm_virtual_machine.avm-01: Creating...
azurerm_virtual_machine.avm-01: Still creating... [10s elapsed]

<--- output truncated --->

azurerm_virtual_machine.avm-01: Creation complete after 2m2s 

Apply complete! Resources: 9 added, 0 changed, 0 destroyed.

Outputs:

hostname = demodns2020.westus.cloudapp.azure.com
```

>Azure Cloud Shelll comes with terraform pre-installed and you deploy this configuration in Cloud Shell as well.
>
>[![](https://shell.azure.com/images/launchcloudshell.png "Launch Azure Cloud Shell")](https://shell.azure.com)
