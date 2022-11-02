# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # General Vagrant VM configuration.
  config.vm.box = "ubuntu/trusty64"
  config.ssh.insert_key = false
  config.ssh.private_key_path = "~/.vagrant.d/insecure_private_key"
  config.vm.synced_folder ".", "/vagrant", disabled: true
  config.vm.provider :virtualbox do |v|
    v.memory = 512
    v.linked_clone = true
  end

  # Application server 1.
  config.vm.define "ubuntu-1" do |u|
    u.vm.hostname = "ubuntu-1"
    u.vm.network :private_network, ip: "172.17.250.132"
  end

  # Application server 2.
  config.vm.define "ubuntu-2" do |u|
    u.vm.hostname = "ubuntu-2"
    u.vm.network :private_network, ip: "172.17.250.133"
  end

  # Database server.
  config.vm.define "ubuntu-3" do |u|
    u.vm.hostname = "ubuntu-3"
    u.vm.network :private_network, ip: "172.17.250.134"
  end

  ## Ansible provisioner.
  #config.vm.provision :ansible do |ansible|
  #  ansible.playbook = "provisioning/playbook.yml"
  #end
end
