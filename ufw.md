
# UFW - Uncomplicated Firewall

The default firewall configuration tool for Ubuntu is ufw. Developed to ease iptables firewall configuration, ufw provides a user friendly way to create an IPv4 or IPv6 host-based firewall. By default UFW is disabled. 

**How to install UFW**
```sudo apt install ufw```

**Check UFW Firewall**
```sudo ufw status verbose```

**Enable/disable UFW Firewall**
```sudo ufw enable/disable```

**UFW Default Policies**
The default UFW firewall polices are placed in the `/etc/default/ufw` file and can be altered using the following command.
```
sudo ufw default deny incoming
sudo ufw default allow outgoing
```
**UFW Application Profiles**
When installing a software package using **APT** package manager, it will include an application profile in `/etc/ufw/applications.d` directory that defines the service and hold UFW settings.
 ```sudo ufw app list ```
 If you want to get more information about a particular profile and defined rules you can use the following command.
 ```sudo ufw app info 'Apache'```

**Allow SSH Connections on UFW**
```sudo ufw allow ssh```
```sudo ufw allow 2222/tcp```

**Block all SSH connections type the following command.**
``` sudo ufw deny ssh/tcp```
```sudo ufw deny 2222/tcp  [If using custom SSH port]```

**Enable Specific Ports on UFW**
 Open Port 80 HTTP on UFW
```sudo ufw allow http     [By service name]```
```sudo ufw allow 80/tcp   [By port number]```
```sudo ufw allow 'Apache' [By application profile]```
Open Port 443 HTTPS on UFW
```sudo ufw allow https```
```sudo ufw allow 443/tcp```
```sudo ufw allow 'Apache Secure'```

 **Allow Specific IP Addresses on Specific Port**
 ```sudo ufw allow from 192.168.56.1 to any port 22```
