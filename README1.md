# Memcached_Vagrant

This is a DevOps project to download Ubuntu 16.04 Desktop vagrant box from cloud, install Apache2, configure it to serve web pages over HTTP, then HTTPS, install memcached and PHP, reconfigure Apache2 to serve PHP pages instead of .html. This is the fully automated process to end up with a reproducible image and a memcached monitor web page using vagrant distributed virtual machine environment technology.

setup
Download and install virtualbox (https://www.virtualbox.org/)
Download and install vagrant (http://vagrantup.com)
what it does do?
Installs Apache2, configures it to serve web pages over HTTP (port 8080) and open a simple "Hello, World!" web page by automatically opening http://localhost:8080/app in default web browser.
Reconfigures Apache2 to run using HTTPS rather than HTTP. Creates self-signed certificates and use those certificates to run HTTPS. Opens a link, https://localhost:8443/app
You will get an exception about an insecure connection due to the self-signed cert. Feel free to ignore this.
Installs memcached and sets test data (hits/misses)
Adds a cronjob that runs /home/vagrant/exercise-memcached.sh once per minute
Writes a PHP web application that outputs memcached stats
It additionally calculates the "get" hit rate and show it as a percentage ("X% of gets missed the cache")
It additionally shows the percentage of memcached memory used
This project has vagrant file and provisioning scripts/configs that recreate everything mentioned above. Just run vagrant up, and have your completed and fixed environment running with memcached stats web page
