# Task: Create an EC2 instance then install Apache Server on it.

## 1. Security Group 
- Create Security Group for Apache Web Server and SSH

### Open EC2 service and create a Security Group

![img.png](images/ec2.jpg)
---
![img.png](images/SG_1.jpg)
---
![img.png](images/SG_2.jpg)

### Giving name to SG & Adding inbound rules

![img.png](images/SG_3.jpg)
---
![img.png](images/SG_4.jpg)

## 2. EC2 Instance

![img.png](images/instance_1.jpg)

### Create EC2 instance

![img.png](images/instance_2.jpg)

### EC2 details

![img.png](images/instance_3.jpg)
---
![img.png](images/instance_4.jpg)
---
![img.png](images/instance_5.jpg)
---
![img.png](images/instance_6.jpg)
---
![img.png](images/instance_7.jpg)
---
![img.png](images/instance_8.jpg)

## 3. Connect EC2 and install Apache Server

![img.png](images/conn_1.jpg)
---
![img.png](images/conn_2.jpg)
---
![img.png](images/conn_3.jpg)
---

### Open a command prompt (cmd) or terminal, enter to the folder which key pair exists, paste the command line you've copied from AWS:

![img.png](images/conn_4.jpg)
---
![img.png](images/conn_5.jpg)
---

### Install requirements to EC2 machine:

```commandline
#!/bin/bash
sudo yum update -y
sudo yum install -y httpd
sudo systemctl enable httpd
sudo service httpd start
sudo echo '<h1>Welcome to VBO AWS Data Enegineering</h1>' | sudo tee /var/www/html/index.html
sudo mkdir /var/www/html/app1
sudo echo '<!DOCTYPE html> <html> <body style="background-color:rgb(250, 210, 210);"> <h1>Welcome to VBO AWS Data Enegineering</h1> <p>Application Version: V1</p> </body></html>' | sudo tee /var/www/html/app1/index.html
sudo curl http://169.254.169.254/latest/dynamic/instance-identity/document -o /var/www/html/app1/metadata.html
```

## 4. Open browser and see result
![img.png](images/00_from_browser_httpd.png)

---

![img.png](images/01_web_ui_app1.png)


## 5. Terminate instance
