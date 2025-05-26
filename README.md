# NanoCluster

![NanoCluster Banner](https://wiki.sipeed.com/hardware/zh/cluster/NanoCluster/assets/product.png)

> Compact & Affordable Cluster for Everyone

This repository is mainly for user feedback. You can submit related usage issues to discuss.
 

## Introduction

NanoCluster is an ultra-miniature cluster board developed by Sipeed, featuring 7 SOM slots interconnected via a RISC-V-based Gigabit switch. It supports USB-C PD power supply and optional PoE expansion. Additionally, NanoCluster provides independent UART and power control, making it an ideal entry-level platform for HomeLab users exploring distributed computing, Kubernetes, Docker, and edge computing.

NanoCluster is compatible with Sipeed's Longan Module 3H (4 × Cortex-A53), M4N (4 × Cortex-A55 + NPU), as well as the Raspberry Pi Compute Module 4 (4 × Cortex-A72) and Compute Module 5 (4× Cortex-A76). Users can freely choose compute modules based on performance needs and budget, or mix and match different architectures to build a highly customized and heterogeneous computing cluster.

The NanoCluster adopts an open SOM interface standard, supporting both official core modules and custom adapter boards for third-party SOM solutions. This design greatly enhances the platform's flexibility.

## Baseboard

<table>
  <thead>
    <tr>
      <th colspan="2">Hardware Specifications</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>SOM Slots</strong></td>
      <td>7× Dual M.2 M-Key vertical slots</td>
    </tr>
    <tr>
      <td><strong>Power Supply</strong></td>
      <td>USB-C 20V PD (Max 60W), Optional 60W PoE module</td>
    </tr>
    <tr>
      <td><strong>Ethernet</strong></td>
      <td>Integrated RISC-V Gigabit switch chip JL6108 for high-speed interconnection, supporting web-based management and SDK-based custom feature development</td>
    </tr>
    <tr>
      <td><strong>USB Ports</strong></td>
      <td>USB-A Host (Top), USB-A OTG (Bottom), connected to Slot 1</td>
    </tr>
    <tr>
      <td><strong>Display Interface</strong></td>
      <td>HDMI, connected to Slot 1</td>
    </tr>
    <tr>
      <td><strong>Cooling System</strong></td>
      <td>Equipped with a 60mm 2-pin fan for efficient cooling</td>
    </tr>
    <tr>
      <td><strong>Status Indicators</strong></td>
      <td>7× SYS LED indicators for node status monitoring</td>
    </tr>
    <tr>
      <td><strong>Serial Communication</strong></td>
      <td>7× independent UARTs for easy debugging and control, optional quad-serial USB module available</td>
    </tr>
    <tr>
      <td><strong>Power Management</strong></td>
      <td>Slot1 centrally manages other Slots and switch power through IO expansion chip</td>
    </tr>
    <tr>
      <td><strong>Power Consumption</strong></td>
      <td>3.6 W</td>
    </tr>
    <tr>
      <td><strong>Dimensions</strong></td>
      <td>PCBA: 88x57mm, approximately 100x60x60mm with SOMs installed and fan mounted</td>
    </tr>
  </tbody>
</table>

<br>

<img src="https://wiki.sipeed.com/hardware/zh/cluster/NanoCluster/assets/bare_board.jpeg" alt="底板裸板特写图" width="600" height="450"/>

## SOM

<table>
    <tr>
        <th>SOM</th>
        <th>LM3H</th>
        <th>M4N</th>
        <th>CM4</th>
        <th>CM5</th>
    </tr>
    <tr>
        <td>SoC</td>
        <td>H618</td>
        <td>AX650N</td>
        <td>BCM2711</td>
        <td>BCM2712</td>
    </tr>
    <tr>
        <td>Memory</td>
        <td>2GB ~ 4GB</td>
        <td>8GB</td>
        <td>1GB ~ 8GB</td>
        <td>1GB ~ 16GB</td>
    </tr>
    <tr>
        <td>eMMC</td>
        <td>32GB</td>
        <td>32GB</td>
        <td>0GB ~ 64GB</td>
        <td>0GB ~ 64GB</td>
    </tr>
    <tr>
        <td>CPU</td>
        <td>4 × A53<br>1.5 GHz</td>
        <td>8 × A55<br>1.6 GHz</td>
        <td>4 × A72<br>1.5 GHz</td>
        <td>4 × A76<br>2.4 GHz</td>
    </tr>
    <tr>
        <td>GPU</td>
        <td>Mali-G31</td>
        <td>-</td>
        <td>VideoCore VI</td>
        <td>VideoCore VII</td>
    </tr>
    <tr>
        <td>NPU</td>
        <td>-</td>
        <td>18TOPS INT8</td>
        <td>-</td>
        <td>-</td>
    </tr>
    <tr>
        <td>Network</td>
        <td>100M</td>
        <td>1G</td>
        <td>1G</td>
        <td>1G</td>
    </tr>
    <tr>
        <td>Additional Interfaces</td>
        <td>None</td>
        <td>Download interface + M.2 SSD + USB 3.0</td>
        <td>Download interface + M.2 SSD</td>
        <td>Download interface + M.2 SSD + USB 3.0</td>
    </tr>
    <tr>
        <td>Power<br>Idle /<br>Full Load /<br>Peak</td>
        <td><nobr>1.2W/2.6W/3.7W</nobr></td>
        <td><nobr>3W/8.3W/9W</nobr></td>
        <td><nobr>3W/4.5W/4.6W</nobr></td>
        <td><nobr>4W/7.6W/8W</nobr></td>
    </tr>
</table>

![SOM图](https://wiki.sipeed.com/hardware/zh/cluster/NanoCluster/assets/som.jpeg)

## Interface Diagram

### Baseboard Interfaces

![接口图示](https://wiki.sipeed.com/hardware/zh/cluster/NanoCluster/assets/board_io.jpeg)

### SOM

- The LM3H SOM connects directly to the baseboard via 7 × dual M.2 M-Key vertical slots.

- The M4N SOM connects to a dedicated adapter board through a BTB connector, which then interfaces with the baseboard.

<table>
    <tr>
        <th>SOM</th>
        <th>LM3H</th>
        <th>M4N</th>
    </tr>
    <tr>
        <td>Front Side</td>
        <td><img src="https://wiki.sipeed.com/hardware/zh/cluster/NanoCluster/assets/lm3h_front.jpeg" width="250"/></td>
        <td><img src="https://wiki.sipeed.com/hardware/zh/cluster/NanoCluster/assets/m4n_front.jpeg" width="250"/></td>
    </tr>
    <tr>
        <td>Back Side</td>
        <td><img src="https://wiki.sipeed.com/hardware/zh/cluster/NanoCluster/assets/lm3h_back.jpeg" width="250"/></td>
        <td><img src="https://wiki.sipeed.com/hardware/zh/cluster/NanoCluster/assets/m4n_back.jpeg" width="250"/></td>
    </tr>
</table>

### Adapter Boards

- The CM4 / CM5 adapter board features a BTB connector on the front side, supporting CM4 and CM5 SOMs. It also includes a Boot button and a Type-C port for flashing. The back side includes an SD card slot, an M.2 NVMe SSD connector (compatible with 2242 or 2230 size), and a reserved USB pad for optional CM5 USB 3.0 support.

- The M4N adapter board features a BTB connector for Sipeed M4N SOMs, a Boot button, and a Type-C flashing port on the front side. The back side includes an M.2 NVMe SSD connector (2242 or 2230), and a reserved USB pad for optional USB 3.0 support.

<table>
    <tr>
        <th>Adapter Board</th>
        <th>CM4 / CM5</th>
        <th>M4N</th>
    </tr>
    <tr>
        <td>Front Side</td>
        <td><img src="https://wiki.sipeed.com/hardware/zh/cluster/NanoCluster/assets/cm4_adapter_front.jpeg" width="250"/></td>
        <td><img src="https://wiki.sipeed.com/hardware/zh/cluster/NanoCluster/assets/m4n_adapter_front.jpeg" width="250"/></td>
    </tr>
    <tr>
        <td>Back Side</td>
        <td><img src="https://wiki.sipeed.com/hardware/zh/cluster/NanoCluster/assets/cm4_adapter_back.jpeg" width="250"/></td>
        <td><img src="https://wiki.sipeed.com/hardware/zh/cluster/NanoCluster/assets/m4n_adapter_back.jpeg" width="250"/></td>
    </tr>
</table>

## Where to Buy

- [Pre-sale Page](https://sipeed.com/nanocluster)

## Resources & Community

- [Wiki](https://wiki.sipeed.com/nanocluster)
- [HDK](https://dl.sipeed.com/Cluster/NanoCluster)
- [GitHub](https://github.com/sipeed/NanoCluster)
