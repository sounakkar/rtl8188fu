For Kernel 4.15.x ~ 5.11.x (Linux Mint or Ubuntu or All Debian Derivatives)
tested on debian with signed kernel 5.11.x & 5.10.x & 5.5.x & kernel 4.19.x
------------------

## How to install

`sudo apt-get install build-essential git dkms linux-headers-$(uname -r)`

`git clone https://github.com/kelebek333/rtl8188fu`

`sudo dkms add ./rtl8188fu`

`sudo dkms build rtl8188fu/1.1`

`sudo dkms install rtl8188fu/1.1`

`sudo cp ./rtl8188fu/firmware/rtl8188fufw.bin /lib/firmware/rtlwifi/`

------------------

Run following commands for disable power management and plugging/replugging issues.

`sudo mkdir -p /etc/modprobe.d/`

`sudo touch /etc/modprobe.d/rtl8188fu.conf`

`echo "options rtl8188fu rtw_power_mgnt=0 rtw_enusbss=0" | sudo tee /etc/modprobe.d/rtl8188fu.conf`

------------------

## How to uninstall

`sudo dkms remove rtl8188fu/1.1 --all`

`sudo rm -f /lib/firmware/rtlwifi/rtl8188fufw.bin`

`sudo rm -f /etc/modprobe.d/rtl8188fu.conf`


------------------

## How to install from PPA repository

You can install rtl81188fu driver with following commands from PPA.

Ubuntu(Latest)  / Linux Mint (latest) / Debian (Stable/SID/unstable)

`sudo add-apt-repository ppa:kelebek333/kablosuz`

`sudo apt-get update`

`sudo apt install rtl8188fu-dkms`


You can purge packages with following commands

`sudo apt purge rtl8188fu-dkms`


