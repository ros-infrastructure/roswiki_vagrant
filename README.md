roswiki_vagrant
===============
A set of Vagrant and Puppet scripts to deploy and test roswiki in a VM.

Requirements
============

The only requirements of roswiki_vagrant are just Vagrant and Virtualbox.

Virtualbox
----------
The most recent version of Virtualbox can be installed from
https://www.virtualbox.org/wiki/Downloads, make sure to install VirtualBox Extension Pack too.


Vagrant
-------
The Vagrant team provides Debian packages available from their
website: http://www.vagrantup.com/downloads.html

vagrant-vbguest
---------------
Vagrant needs the Virtualbox Guest Additions to be in sync with the version of
Virtualbox installed on the host. The vagrant-vbguest plugin checks that the
version of the Virtualbox Guest Additions matches and installs the most recent
version if needed.

To install vagrant-vbguest just type:

```
$ vagrant plugin install vagrant-vbguest
```


Usage
=====
Checkout this repository and roswiki's side by side, so both copies are siblings and
type the following from the roswiki_vagrant directory to start the VM:

```
$ vagrant up
```

After a few minutes, the VM should be running and fully provisioned with an empty wiki.
To access the wiki, point your web browser to http://localhost:8080, If desired, the port
can be changed in Vagrantfile:

```
config.vm.network "forwarded_port", guest: 8080, host: 8080
```

where guest is the port where Apache listens inside the VM and host the port that is
accessible from the web browser.
