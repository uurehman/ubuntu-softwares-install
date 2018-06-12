# ubuntu-softwares-install
# Getting Started with Ubuntu
*List of commands to install different tools and customize settings*

------

## Chromium Browser
	sudo apt-get install chromium-browser

----------
## Sublime Text
#### Install the GPG key:
	wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -

#### Ensure apt is set up to work with https sources:
	sudo apt-get install apt-transport-https

#### Select the channel to use:

###### Stable
	echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list

##### Dev
	echo "deb https://download.sublimetext.com/ apt/dev/" | sudo tee /etc/apt/sources.list.d/sublime-text.list

#### Update apt sources and install Sublime Text
	sudo apt-get update
	sudo apt-get install sublime-text

#### Licence Key

'''
—– BEGIN LICENSE —–
TwitterInc
200 User License
EA7E-890007
1D77F72E 390CDD93 4DCBA022 FAF60790
61AA12C0 A37081C5 D0316412 4584D136
94D7F7D4 95BC8C1C 527DA828 560BB037
D1EDDD8C AE7B379F 50C9D69D B35179EF
2FE898C4 8E4277A8 555CE714 E1FB0E43
D5D52613 C3D12E98 BC49967F 7652EED2
9D2D2E61 67610860 6D338B72 5CF95C69
E36B85CC 84991F19 7575D828 470A92AB
—— END LICENSE ——
'''

-------------

## Virtual Box
#### combine downloading and registering:
	wget -q https://www.virtualbox.org/download/oracle_vbox_2016.asc -O- | sudo apt-key add -
	wget -q https://www.virtualbox.org/download/oracle_vbox.asc -O- | sudo apt-key add -

#### Install VirtualBox
	sudo apt-get update
	sudo apt-get install virtualbox

Replace virtualbox-5.2 by virtualbox-5.1 to install VirtualBox 5.1.30 
Note: Ubuntu/Debian users might want to install the dkms package to ensure that the VirtualBox host kernel modules (vboxdrv, vboxnetflt and vboxnetadp) are properly updated if the linux kernel version changes during the next apt-get upgrade. For Debian it is available in Lenny backports and in the normal repository for Squeeze and later. The dkms package can be installed through the Synaptic Package manager or through the following command:

	sudo apt-get install dkms

------------
## Dropbox Headless Install via command line
	cd ~ && wget -O - "https://www.dropbox.com/download?plat=lnx.x86_64" | tar xzf -

Next, run the Dropbox daemon from the newly created .dropbox-dist folder.

	~/.dropbox-dist/dropboxd

------------

## Installing Kazam (Screen Capture)
sudo apt-get clean
sudo apt install kazam

--------

## Installing Tor Browser
	sudo add-apt-repository ppa:webupd8team/tor-browser
	sudo apt-get update
	sudo apt-get install tor-browser

------------

## Installing LAMP
Link: 	https://howtoubuntu.org/how-to-install-lamp-on-ubuntu 
STEPS:
1. Install Apache
	sudo apt install apache2
2. Install MySQL
	sudo apt install mysql-server
3. Install PHP
	sudo apt install php-pear php-fpm php-dev php-zip php-curl php-xmlrpc php-gd php-mysql php-mbstring php-xml libapache2-mod-php
4. Restart Server
	sudo service apache2 restart
5. Check Apache
"Open a web browser and navigate to http://localhost/. You should see a message saying It works!"
6. Check PHP
	php -r 'echo "\n\nYour PHP installation is working fine.\n\n\n";'

---------

## Show Internet speed in Menu Bar
	sudo add-apt-repository ppa:nilarimogard/webupd8
	sudo apt-get update
	sudo apt-get install indicator-netspeed

------

## Customization Commands

#### Place Launcher to Bottom
	gsettings set com.canonical.Unity.Launcher launcher-position Bottom

#### Natural Scroll of track pad
	gsettings set org.gnome.desktop.peripherals.touchpad natural-scroll true

#### Launcher icon toggle for minimizing windows.
	gsettings set org.compiz.unityshell:/org/compiz/profiles/unity/plugins/unityshell/ launcher-minimize-window true

--------

## Other Commands

#### Releasing Locks
	sudo rm /var/lib/apt/lists/lock
	sudo rm /var/cache/apt/archives/lock
	sudo rm /var/lib/dpkg/lock

#### Changing MAC Address
	sudo ifconfig wlo1 down
	sudo ifconfig wlo1 hw ether 00:11:22:33:44:55
	sudo ifconfig wlo1 up
