 Basic Syslog Topology & Configuration
This simple topology demonstrates how to configure a router to send syslog messages to a server.

Topology Components:

1x Router: (e.g., Cisco 1941)

1x Syslog Server: (Generic Server device)

Cabling: Straight-through Ethernet cable.

IP Addressing: Router Gig0/0: 192.168.1.1/24, Syslog Server: 192.168.1.100/24.

Cisco IOS Configuration:

Configure Router Interface:

Router(config)# interface gigabitethernet 0/0
Router(config-if)# ip address 192.168.1.1 255.255.255.0
Router(config-if)# no shutdown
Configure Syslog Destination:

Router(config)# logging 192.168.1.100
This command directs the router to send log messages to the specified syslog server.

Optional: Set Trap Level:

By default, the trap level is Informational (6). You can change this to filter messages.

Router(config)# logging trap notifications
This command will send all messages with a severity level of 5 (Notifications) or lower (more critical) to the syslog server.
