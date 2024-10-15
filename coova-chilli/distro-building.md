---
layout: page
title: CoovaChilli distribution building
permalink: /CoovaChilli/DistroBuilding/
---

Building [CoovaChilli](/CoovaChilli) Binaries
=============================================

RPM (Redhat/Fedora)
-------------------
```sh
    wget https://github.com/coova/coova-chilli/archive/1.3.1.4.tar.gz
    cp 1.3.1.4.tar.gz /usr/src/redhat/SOURCES/
    tar xzf 1.3.1.4.tar.gz
    cd coova-chilli-1.3.1.4/
    rpmbuild -ba coova-chilli.spec
```

DEB (Debian/Ubuntu)
-------------------
```sh
    wget https://github.com/coova/coova-chilli/archive/1.3.1.4.tar.gz
    tar xzf 1.3.1.4.tar.gz
    cd coova-chilli-1.3.1.4/
    debuild -b 
```

Gentoo Linux
------------

The ebuild is available on Sunrise overlay so install this overlay first (if you don't have it yet):
(This needs updating for Git).
```sh
    # Install layman to manage Gentoo overlays
    sudo USE="subversion" emerge -a layman
    # Install sunrise overlay
    sudo layman -f -a sunrise
    sudo echo "source /var/lib/layman/make.conf" >> /etc/make.conf
    # To keep the overlay up to date run
    sudo layman -s overlay
```

Now you can install the CoovaChilli package by running emerge:
```sh
    sudo emerge -a coova-chilli
```

To start chilli:
```sh
    sudo /etc/init.d/chilli
```

PKG (FreeBSD)
-------------

Make sure your ports tree is up to date. The quickest way is to use the portsnap utility, see:
[here](http://www.freebsd.org/doc/en_US.ISO8859-1/books/handbook/updating-upgrading-portsnap.html)

Once you're up to date
```sh
    cd /usr/ports/net-mgmt/coovachilli
    make package
```
