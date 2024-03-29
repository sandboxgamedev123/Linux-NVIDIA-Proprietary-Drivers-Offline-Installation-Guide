# Linux-NVIDIA-Proprietary-Drivers-Offline-Installation-Guide
This is a guide to having an offline package of NVIDIA proprietary drivers for Linux. This guide is for installing NVIDIA propietary drivers completely offline on a clean installation of Linux.

Since this guide pertains to NVIDIA drivers, packages will not be provided. This repository is just a README.md describing the process of creating an offline package of NVIDIA proprietary drivers for Linux.

The packages that will be obtained in following example:

nvidia-driver-535 (535.54.03)

nvidia-settings

nvidia-prime

This was tested on Linux Mint 21.2 Cinnamon x64 and the guide will be based on obtaining ".deb" files. Therefore, this guide is may work well for other Debian/Ubuntu based distros.

"sudo apt-get install --download-only nvidia-driver-535" is not recommended because upon a fresh installation of Linux, tests have shown that the system still tries to download files.

Also, I cannot comment on the security of the websites for which the ".deb" files are obtained.

Main URL: http://87.238.33.18/ubuntu/pool/multiverse/n/

Scroll down the page until the NVIDIA drivers are seen.

The following example is for nvidia-driver-535:

nvidia-driver-535 URL: http://87.238.33.18/ubuntu/pool/multiverse/n/nvidia-graphics-drivers-535/

Download the ".deb" files for 22.04.01.

These files can be packaged into their own archive. The files can be installed by executing each file individually.

The files that state "open" are not recommended to install. There are also other files that are not recommended to install depending on whether usage of X11 or Wayland is planned. Read the description of the files before installing them.

Open a command-line window and type the following:

sudo apt-get install --download-only nvidia-settings

The command will download ".deb" files into the following directory:

/var/cache/apt/archives/

Opening the "partial" folder should allow copying the ".deb" files from the "archives" folder to another folder.

The following website downloads an additional ".deb" that may be required for nvidia-settings:

http://archive.ubuntu.com/ubuntu/pool/main/n/nvidia-settings/libxnvctrl0_510.47.03-0ubuntu1_amd64.deb

The command for nvidia-prime:

sudo apt-get install --download-only nvidia-prime

After the apropriate files are installed, restart the computer. Open a command-line window and type the following:

inxi -G

The command will provide information that the NVIDIA proprietary driver is installed.
