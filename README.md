BackupPC configuration files for httpd
======================================

This repository provides configuration files for your apache2 web server and a systemd service file to run a dedicated instance of httpd.

When do I need these files?
---------------------------

You need these files if you need your web server for web development. BackupPC requires httpd running as the *backuppc* user but the default user for your web projects should be *http* or *www-data* depending on your Linux distribution.

How to start the web server?
----------------------------

After copying the files to the right locations you start the systemd service as follows.

<code>sudo systemctl start httpd-backuppc</code>

Alternatively you can start it manually by executing

<code>sudo apachectl -f /etc/httpd/conf/backuppc.conf</code>

How to install?
---------------

Just copy the files to

* backuppc.conf ➡ <code>/etc/httpd/conf</code>
* httpd-mpm-backuppc.conf ➡ <code>/etc/httpd/conf/extra</code>
* httpd-backuppc.service ➡ <code>/usr/lib/systemd/system</code>

If you are using Arch Linux, it provides a PKGBUILD for these files. All you need to do here is to run the following commands.

<pre><code>mkdir /tmp/backuppc-httpd
cd /tmp/backuppc-httpd
wget https://aur.archlinux.org/packages/ba/backuppc-httpd/PKGBUILD
makepkg -si
</code></pre>
