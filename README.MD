# Prerequisites:
·         A hypervisor capable machine running ubuntu 22.04.3 LTS.
·         A Ubuntu Server 20.04 ISO that is NOT live. (Generic) (https://releases.ubuntu.com/20.04.6/ubuntu-20.04.6-live-server-amd64.iso?_ga=2.85763994.2008084420.1692365682-1293080909.1689863957)
·         Preseed file with configuration
·         Isolinux file to edit grub

# Creating a Preseed file:
Demo Preseed file: urvishmistry/preseed (github.com)
 
# Isolinux file
Create a file named txt.cfg and edit the contents from this link: https://github.com/urvishmistry/preseed/blob/main/txt.cfg 

# Steps to follow:

## Installation of Cubic:

```
sudo apt-add-repository ppa:cubic-wizard/release
sudo apt update
sudo apt install cubic
```

## GUI Steps:

1. Start Cubic
2. Select work directory where the new ISO will be created. Click Next.
3. Point to the original Ubuntu ISO downloaded. Once loaded, change the details in the right pane for the new ISO. Click Next.
4. Now; the Cubic will load a virtual environment with chroot.
5. Execute commands that you think you'll need in the target ISO. For this tutorial; we are not executing any commands and not modifying ISO. Click Next.
6. This is important screen. DO NOT CLICK NEXT. 
7. Click on Preseed. Click on new file icon on the top toolbar. Name the file: `auto-inst.seed`
8. Paste the contents from the Preseed file you have edited before.
9. Click on Boot tab on the top toolbar.
10. There is a file under isolinux subfolder named txt.cfg
11. Replace all the content with the one from the Isolinux file step mentioned above.
12. Click next.
13. Select gzip compression.
14. Bootable ISO is created. 
