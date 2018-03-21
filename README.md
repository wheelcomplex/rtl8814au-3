<u>**rtl8814au for linux**</u>

rtl8814au linux kernel driver Wireless Dual-Band USB Adapter
also for rtl8813au devices.

<u>If one USB-ID is missing, please mail me.</u>  

support for kernels 4.15(Ubuntu 18.04 LTS works for 2.4G only).

**Building and install driver**

for building type  
`make`  

You need to install the needed fw with  
`sudo make installfw`  

for load the driver  
`sudo insmod rtl8814au.ko`  

## DKMS
This driver can be installed using [DKMS](http://linux.dell.com/dkms/). This is a system which will automatically recompile and install a kernel module when a new kernel gets installed or updated. To make use of DKMS, install the `dkms` package, which on Debian (based) systems is done like this:
```
sudo apt install dkms
```

## Installation of Driver
In order to install the driver open a terminal in the directory with the source code and execute the following command:
```
sudo ./dkms-install.sh
```

## Removal of Driver
In order to remove the driver from your system open a terminal in the directory with the source code and execute the following command:
```
sudo ./dkms-remove.sh
```

**STATUS**  
Currently as educational driver,  
but driver is working fine in STA  

**USB3 Mode Issue**  
Realtek aka the chipdesigner does some **stupid** idea to switch into USB3 mode via special usb read/write command.  
  
On cold boot this device will appear as normal USB2 device.
Switching is tested, but currently not active yet !

## Note
For Ubuntu 17.04 add the following lines
```
[device]
wifi.scan-rand-mac-address=no
```
at the end of file /etc/NetworkManager/NetworkManager.conf and restart NetworkManager with the command:
```
sudo service NetworkManager restart
```

**TODO**, will work on if I have enough time,  
currently <u>not</u>

- rip out firmware blob
- activate USB3 switch
- minor crosscompile check


Hans Ulli Kroll <ulli.kroll@googlemail.com>
