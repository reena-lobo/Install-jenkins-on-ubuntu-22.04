# Install-jenkins-on-ubuntu-22.04

launch an ec2 instance
enable port 8080

copy below code in userdata section(so that no need to login to server) while launching the server

#!/bin/bash

## To install Java 
sudo apt install openjdk-11-jdk -y 

## To Import Jenkins repo & Key 
curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
## Update, Upgrade the OS & Install Jenkins
sudo apt update -y
sudo apt install jenkins -y
sudo systemctl status jenkins
sudo systemctl status jenkins
sudo systemctl enable --now jenkins


click on launch instance
then in url 
url:publicip:8080
if connected no issues
otherwise  launch the instance (as mentioned above) connect to server and install jenkins using below steps
1.ssh to server
sudo -i
systemctl status jenkins
java -version

still if it is not installed 
create a file
vim jenkins-install.sh
//paste the userdata for jenkins installation
save and exit
systemctl status jenkins
output:active(running)

go to url:
public ip:8080

if connected unlock jenkins screen comes 
copy the path 
vim paste the path
you will get password copy it and paste it in administration password
then redirected to 
customized jenkins page
install suggested plugins

fill the form
save
now start using jenkins



