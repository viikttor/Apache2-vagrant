# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = "ubuntu/xenial64"

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # NOTE: This will enable public access to the opened port
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine and only allow access
  # via 127.0.0.1 to disable public access
  config.vm.network "forwarded_port", guest: 80, host: 8080
  
  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "172.18.23.250"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  # config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
  #   vb.memory = "1024"
  # end
  #
  # View the documentation for the provider you are using for more
  # information on available options.

  # Enable provisioning with a shell script. Additional provisioners such as
  # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
  # documentation for more information about their specific syntax and use.
  config.vm.provision "shell", inline: <<-SHELL
  apt-get update 
  apt-get install -y apache2 
  apt-get install -y apt-transport-https ca-certificates curl software-properties-common 
  #sudo apt-get update
  #sudo apt-get install python-dev python-setuptools
  #sudo easy_install pip
  #sudo pip install virtualenv
  #sudo virtualenv pythonclub --no-site-packages
  #pip install django
  #pip install django==1.5
  #sudo apt-get -y install python  
  #git clone https://github.com/edsonbenites/devops-sample-vestibulares.git /var/www/devops-sample-vestibulares
  #git clone https://github.com/edsonbenites/html-docs-hello-world.git /var/www/html-docs-hello-world
  #git clone https://github.com/edsonbenites/devops-aula13.git /var/www/devops-aula13
  rm -rf /var/www/introducao-html-css
  git clone https://github.com/viikttor/introducao-html-css.git /var/www/introducao-html-css
  git clone https://github.com/viikttor/Apache2-vagrant.git /etc/apache2/sites-enable
  # git clone https://github.com/mattdesl/simple-html-index.git /var/www/simple-html-index
  rm /etc/apache2/sites-enabled/000-default.conf
  git clone https://github.com/viikttor/Apache2-vagrant.git /etc/apache2/sites-enabled
  service apache2 restart 

  SHELL
end
