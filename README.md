# vm4docker
run docker with vmware on OS X

## related to this project

- [ansible rule osx](https://github.com/yvess/ansible-vm4docker-client)
- [ansible rule docker ubuntu vm](https://github.com/yvess/ansible-vm4docker-server)
- [sublime plugin for auto reload](https://github.com/yvess/sublime_vm4docker)

## Install

Install brew if you don't have it already.

```bash
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

For more information go to [brew.sh](http://brew.sh).

Now you need ansible:

```bash
brew install ansible
```

Install the ansible roles

```bash
ansible-galaxy install yvess.vm4docker-client yvess.vm4docker-server
```

Put your ansible roles into your local ansible configuration management.
If you are new to ansible you can use the files in [./cm](./cm) as template.

Update your variables in `hosts`.

- docker_hostip=192.168.13.128, ip of your docker vm
- docker_gatewayip=192.168.13.1, ip of your gateway normally docker_host_ip with .1
- docker_mac=0e:0c:23:bf:2e:3b, put in you mac address or your docker vm

You should get this values when you ssh into your docker vm and do `ifconfig`.

No run you ansible rules to setup everything.

```bash
ansible-playbook -K main.yml
```

enjoy your flexible docker setup.
