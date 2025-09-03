# SimpleALB
Launching an ALB in AWS with simple EC2 User Script

# Steps to Launch EC2 Instances
1. Select AMI: Amazon Linux
2. Instance type: t3.micro (Free-tier)
3. Key pair not needed for simplicity although advised
4. Security group: Allow inbound traffic from SSH and HTTP
5. Under **Advanced Details**, copy and paste the script from ['ec2-user-script.sh'](./ec2-user-script.sh) into **User Data**
6. Launch 2 Instances

Now test if the EC2s are running. Search **http://{public-ipv4-address-of-the-instance}**

# Launch ALB
1. Scheme: Internet-facing
2. Load balancer IP: IPv4
3. Network mapping: Select all AZs
4. Add new security group only allowing HTTP inbound traffic and all outbound traffic
5. Target group: The two EC2 instances created
