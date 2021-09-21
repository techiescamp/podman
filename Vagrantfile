Vagrant.configure("2") do |config|
    config.vm.provision "shell", inline: <<-SHELL
        sudo apt-get update -y
        sudo apt-get -y install runc 
        sudo apt-get -y install podman
        echo "10.0.0.11  podman" >> /etc/hosts
    SHELL
    
    config.vm.define "podman" do |podman|
      lab.vm.box = "bento/ubuntu-20.10"
      lab.vm.hostname = "lab"
      lab.vm.network "private_network", ip: "10.0.0.11"
      lab.vm.provider "virtualbox" do |vb|
          vb.memory = 1024
          vb.cpus = 1
      end
    end
  end