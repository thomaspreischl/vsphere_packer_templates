# vpshere_packer_deployments
this repository contains packer scripts to automatically create, preconfigure and deploy vm templates in vmware vsphere


## Reqirements

Before you can create your vmware vsphere templates with this packer deployment scripts, you have to install packer and the required plugins.

Folow the steps at https://chocolatey.org/install to install chocolatey.

If you have installed chocolatey, you can install the reqired packages for packer.

execute the following commands in your Powershell

`cinst packer -y`

`choco install Packer-provisioner-windows-update`

If the required Packages are installed. You can go on with the next steps

## Prepare the scripts to make an automated deployment of your vmware vsphere Templates

1. Clone the Repository
2. Upload the desired ISO Files to a Datastore of your vcenter/ vsphere environment
3. copy the variables.json file and change the setting for your environment
3. change the password for your autounattend.xml files 

`<Password> <Value> YOUR PASSWORD </Value> <PlainText>true</PlainText> </Password>`
                
 and

`<AdministratorPassword> <Value> YOUR PASSWORD </Value> <PlainText>true</PlainText> </AdministratorPassword>`

## Execute the Scripts 

go to the *w***.base* folder

Execute the scripts as followed:

`packer build  -var-file ..\variables_YOUR_VARFILE.json .\Server2019_vsphere.json`
