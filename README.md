# CMIT 351 Project 1  
Cisco Packet Tracer LAN Implementation

## Overview
This project presents a prototype Local Area Network built in Cisco Packet Tracer for ACME University IT. The design follows the requirement to improve LAN performance by reducing large broadcast domains through proper Layer 2 segmentation. The topology includes two managed switches and three hosts, along with three VLANs that represent organizational groups. The project demonstrates how segmentation, structured cabling, VLAN configuration, and trunking contribute to reliable LAN behavior.

## Network Design
The LAN consists of two switches named S1 and S2 and three computers named PC-A, PC-B, and PC-C. PC-A connects to S1 on interface 6. S1 connects to S2 through interface 1 on each switch. PC-B connects to S2 on interface 11, and PC-C connects to S2 on interface 18. The addressing plan places PC-A and PC-B in the 192.168.10.0 network with the default gateway 192.168.10.1. PC-C uses the 192.168.20.0 network with a gateway of 192.168.20.1. This structure supports the VLAN segmentation defined later in the project.

## Basic Switch Configuration
Both switches include the same administrative configuration. The enable secret password is set to "class," and the console and VTY lines use the password "cisco." Logging is set to synchronous, and each switch displays the message of the day banner "Unauthorized access is strictly prohibited." These foundational settings provide consistent and secure switch behavior before VLAN and trunking configurations are applied.

## VLAN Structure
The network includes three VLANs named Students, Faculty, and Management. VLAN 10 represents the Students group, VLAN 20 represents the Faculty group, and VLAN 99 serves as the Management VLAN used to manage both switches. On S1, VLAN 10 includes interfaces 6, 12 through 20, and 22 through 23. VLAN 20 includes interfaces 11 and 21. The management interface for S1 uses VLAN 99 with the IP address 192.168.1.11 and subnet mask 255.255.255.0. On S2, interface 11 is assigned to VLAN 10, and interface 18 is assigned to VLAN 20. The management interface for S2 also uses VLAN 99 with the address 192.168.1.12 and the same subnet mask. These assignments enforce proper segmentation throughout the network.

## VLAN Trunking
To allow VLAN traffic to pass between S1 and S2, interface 1 on both switches is manually configured as a trunk. Dynamic trunking protocols are not used. The explicit trunk configuration ensures that VLANs 10, 20, and 99 remain intact as they traverse the link between the two switches. This provides consistent behavior across the LAN and preserves segmentation across both devices.

## Connectivity Testing
Connectivity testing confirmed that PC-A and PC-B could communicate because they share the same subnet and VLAN. PC-C, located in a different subnet and VLAN, remained isolated, which is the correct behavior since there is no router-on-a-stick or Layer 3 device to enable inter-VLAN routing. After VLANs and trunking were configured, both switches communicated successfully through their management interfaces. Ping results showed that communication between devices in the same VLAN worked as expected, while communication across VLAN boundaries did not, which aligns with the project's goals.

## File Information
The repository contains the completed Packet Tracer file named LAN_Project.pka. Opening this file in Cisco Packet Tracer provides access to the full topology, including all cabling, VLAN assignments, switch configurations, management interfaces, and trunking settings.

## Purpose
This project demonstrates core networking concepts including VLAN segmentation, switch configuration, trunking, IP addressing, and connectivity validation. It reflects essential skills used in real-world networking environments and fulfills the academic objectives of CMIT 351 Project 1.
