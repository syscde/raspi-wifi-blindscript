raspi-wifi-blindscript
======================

A minimium script to configure Wi-Fi network on Raspbian system for Raspberry Pi(R) ARM computer. 

This script is useful for headless usage of Raspberry Pi. You may connect a brand new Raspbian system to Wi-Fi network, only by "blindly" entering one line of command via a USB keyboard. You don't need wired network connection, direct changing linux partition or even a screen. 

This script may also be used in any Linux system with wpa_supplicant tools installed. 

System requirements
----------------------
* Linux system
* wpa\_supplicant installed, wpa\_cli command available
* A Wi-Fi network card supported by your system

How to use (generally)
----------------------
1. Edit the script file `w.sh`, enter your Wi-Fi SSID and password. 
2. Execute with `./w.sh` using root privilege. (by root user or via sudo)

How to use it for configuring Wi-Fi for a new Raspbian system
----------------------
1. Write Raspbian system image to SD card.
2. Edit script file `w.sh`, copy it to the boot partition (aka. the first, small FAT partition) of SD card.  
   (Note: DON'T edit this file with Windows Notepad, as it can't recognize Unix style line-endings! Use [Notepad++](http://notepad-plus-plus.org/) or other text editor instead.)
3. Power on Raspberry Pi, with a supported Wi-Fi usb dongle, and a usb keyboard connected.
4. Wait 2 minutes. (for the first boot)
5. Press `ESC` key. (to exit raspi-config)
6. Wait 30 seconds. (for entering command line)
7. Input this command and press enter:  
   `sudo /boot/w.sh`  
   You may not see your entering without a screen - just relax. It's OK to do it blind. 
8. Wi-Fi connection will be established within several seconds. The indicator light on your Wi-Fi dongle (if exists) will light up and flash. 

You can connect to your Raspberry Pi via SSH. Pi's IP address can be found in router admin interface, or using an IP scanner software. 
