# Configuring-and-testing-basic-firewall-rules-to-allow-or-black-traffic-task-4

configuring  basic firewall rules to allow or block traffic and test them on both Windows and Linux systems.

🪟 Windows Firewall Configuration
Allow or Block Ports with Windows Defender Firewall:
Open Start → Windows Defender Firewall with Advanced Security.

Click Inbound Rules → New Rule…

Choose Port, then click Next.

Choose TCP or UDP, enter the port number(s) you want to allow/block, e.g. 80.

Choose Allow the connection or Block the connection, then click Next.

Choose when the rule applies (Domain, Private, Public).

Name the rule, e.g., Allow HTTP or Block HTTP.

Click Finish.


🐧 Linux Firewall Configuration
You can use UFW (Uncomplicated Firewall) or iptables.

1️⃣ Using UFW
Install UFW :

sudo apt update
sudo apt install ufw

Enable UFW:
sudo ufw enable

Allow traffic on a specific port (e.g., SSH - port 22):
sudo ufw allow 22/tcp

Block traffic on a specific port (e.g., HTTP - port 80):
sudo ufw deny 80/tcp

View active rules:
sudo ufw status numbered



2️⃣ Using iptables (alternative)
Allow SSH (port 22):
sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT

Block HTTP (port 80):
sudo iptables -A INPUT -p tcp --dport 80 -j DROP

🔎 Testing the Firewall Rules
Use tools like:

ping (ICMP): ping <IP>

ssh/ftp:

Linux: ssh username@<ip> -p <PORT> (or) ssh username@<ip> / ftp <ip>

Windows: ssh username@<ip> -p <PORT>  (or) ssh username@<ip> / ftp <ip> (PowerShell)

✅ If the firewall allows, the connection should succeed.
❌ If the firewall blocks, the connection should fail.
