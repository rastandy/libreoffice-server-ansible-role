# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure('2') do |config|

  # Ensure we use our vagrant private key
  config.ssh.insert_key = false
  config.ssh.private_key_path = '~/.vagrant.d/insecure_private_key'

  config.vm.define 'libreoffice-server' do |machine|
    machine.vm.box = "bento/centos-7.2"

    machine.vm.network :private_network, ip: '192.168.88.34'
    machine.vm.hostname = 'libreoffice-server.local'
    machine.vm.provision 'ansible' do |ansible|
      ansible.playbook = 'tests/test.yml'
      ansible.sudo = true
      ansible.host_key_checking = false
    end
  end
end
