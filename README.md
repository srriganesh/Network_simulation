# Network_simulation
# 🌐 Hybrid RIP–OSPF Network Simulation (Cisco Packet Tracer)

## 📘 Project Overview

This project demonstrates a **hybrid routing setup** combining both **RIP (Routing Information Protocol)** and **OSPF (Open Shortest Path First)** to achieve scalable and efficient routing across multiple subnet domains.

The network is designed and simulated using **Cisco Packet Tracer**, consisting of **three OSPF domains** interconnected via **backbone routers (R1, R5, R9)**. Each OSPF domain is connected to a corresponding **RIP-based internal LAN**. 

This design allows seamless communication between multiple autonomous systems using **route redistribution** between RIP and OSPF.

---

## 🧩 Network Architecture

The topology is divided into **three major regions**:

| Region | Protocol | Core Router | Internal Routers | LANs |
|:------:|:----------|:-------------|:------------------|:------|
| Region 1 | RIP + OSPF | R1 | R2, R3, R4 | PC-A, Server, Laptop-A, PC-B, PC-C |
| Region 2 | RIP + OSPF | R5 | R6, R7, R8 | PC-D, IP Phone, PC-E, PC-F |
| Region 3 | RIP + OSPF | R9 | R10, R11, R12 | PC-G, PC-K, PC-L, Laptop-E |

---

## 🔁 Routing Setup

### 🟣 RIP Configuration
RIP (Routing Information Protocol) is used inside each local region to maintain **simple and dynamic distance-vector routing** among the internal routers.

**RIP Features:**
- Distance Vector Protocol
- Uses Hop Count as metric
- Max hop count: 15
- Classful (RIPv1) or Classless (RIPv2)
- Periodic updates every 30 seconds

**Configuration Example (Router R2):**
```bash
Router(config)# router rip
Router(config-router)# version 2
Router(config-router)# network 192.168.1.0
Router(config-router)# network 192.168.2.0
Router(config-router)# no auto-summary
