Vagrant.configure(2) do |config|
  config.vm.define "odl" do |odl|
    odl.vm.box = "ubuntu/xenial64"
    odl.vm.network "private_network", ip: "10.10.10.2"
    odl.vm.network "forwarded_port", guest: 8181, host: 58181
    odl.vm.provider "virtualbox" do |v|
      v.memory = 4048
      v.cpus = 2
    end
    odl.vm.provision "shell", path: "odl-provision.sh"
  end

  config.vm.define "mininet" do |mininet|
    mininet.vm.box = "ubuntu/xenial64"
    mininet.vm.network "private_network", ip: "10.10.10.3"
    mininet.vm.provision "shell", path: "mininet-provision.sh"
  end

  config.vm.define "ofm" do |ofm|
    ofm.vm.box = "ubuntu/xenial64"
    ofm.vm.network "private_network", ip: "10.10.10.4"
    ofm.vm.network "forwarded_port", guest: 9000, host: 19000
    ofm.vm.provision "shell", path: "ofm-provision.sh"
  end
end
