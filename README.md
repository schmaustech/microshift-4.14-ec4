# microshift-4.14-ec4
~~~bash
[root@asus3-vm1 ~]# dnf repolist
Updating Subscription Management repositories.
repo id                                                                                           repo name
codeready-builder-for-rhel-9-x86_64-rpms                                                          Red Hat CodeReady Linux Builder for RHEL 9 x86_64 (RPMs)
epel                                                                                              Extra Packages for Enterprise Linux 9 - x86_64
rhel-9-for-x86_64-appstream-rpms                                                                  Red Hat Enterprise Linux 9 for x86_64 - AppStream (RPMs)
rhel-9-for-x86_64-baseos-rpms                                                                     Red Hat Enterprise Linux 9 for x86_64 - BaseOS (RPMs)
rhel-9-for-x86_64-rt-rpms                                                                         Red Hat Enterprise Linux 9 for x86_64 - Real Time (RPMs)
[root@asus3-vm1 ~]# subscription-manager repos --enable=rhocp-4.13-for-rhel-9-x86_64-rpms
Repository 'rhocp-4.13-for-rhel-9-x86_64-rpms' is enabled for this system.
[root@asus3-vm1 ~]# yum install cri-o cri-tools openshift-clients 
Updating Subscription Management repositories.
Red Hat OpenShift Container Platform 4.13 for RHEL 9 x86_64 (RPMs)                                                                                                                 6.9 MB/s |  15 MB     00:02    
Dependencies resolved.
===================================================================================================================================================================================================================
 Package                                  Architecture                  Version                                                                     Repository                                                Size
===================================================================================================================================================================================================================
Installing:
 cri-o                                    x86_64                        1.26.4-3.rhaos4.13.git615a02c.el9                                           rhocp-4.13-for-rhel-9-x86_64-rpms                         37 M
 cri-tools                                x86_64                        1.26.0-3.el9                                                                rhocp-4.13-for-rhel-9-x86_64-rpms                        8.6 M
 openshift-clients                        x86_64                        4.13.0-202308112024.p0.g17b7acc.assembly.stream.el9                         rhocp-4.13-for-rhel-9-x86_64-rpms                         49 M
Installing dependencies:
 runc                                     x86_64                        4:1.1.6-3.rhaos4.13.el9                                                     rhocp-4.13-for-rhel-9-x86_64-rpms                        3.1 M

Transaction Summary
===================================================================================================================================================================================================================
Install  4 Packages

Total download size: 98 M
Installed size: 346 M
Is this ok [y/N]: y
Downloading Packages:
(1/4): runc-1.1.6-3.rhaos4.13.el9.x86_64.rpm                                                                                                                                       2.1 MB/s | 3.1 MB     00:01    
(2/4): cri-tools-1.26.0-3.el9.x86_64.rpm                                                                                                                                           3.1 MB/s | 8.6 MB     00:02    
(3/4): cri-o-1.26.4-3.rhaos4.13.git615a02c.el9.x86_64.rpm                                                                                                                          5.6 MB/s |  37 MB     00:06    
(4/4): openshift-clients-4.13.0-202308112024.p0.g17b7acc.assembly.stream.el9.x86_64.rpm                                                                                            5.8 MB/s |  49 MB     00:08    
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Total                                                                                                                                                                              9.8 MB/s |  98 MB     00:09     
Running transaction check
Transaction check succeeded.
Running transaction test
Transaction test succeeded.
Running transaction
  Preparing        :                                                                                                                                                                                           1/1 
  Installing       : runc-4:1.1.6-3.rhaos4.13.el9.x86_64                                                                                                                                                       1/4 
  Installing       : cri-o-1.26.4-3.rhaos4.13.git615a02c.el9.x86_64                                                                                                                                            2/4 
  Running scriptlet: cri-o-1.26.4-3.rhaos4.13.git615a02c.el9.x86_64                                                                                                                                            2/4 
Created symlink /etc/systemd/system/multi-user.target.wants/crio-subid.service → /usr/lib/systemd/system/crio-subid.service.
Created symlink /etc/systemd/system/crio.service.wants/crio-subid.service → /usr/lib/systemd/system/crio-subid.service.

  Installing       : openshift-clients-4.13.0-202308112024.p0.g17b7acc.assembly.stream.el9.x86_64                                                                                                              3/4 
  Installing       : cri-tools-1.26.0-3.el9.x86_64                                                                                                                                                             4/4 
  Running scriptlet: cri-tools-1.26.0-3.el9.x86_64                                                                                                                                                             4/4 
  Verifying        : runc-4:1.1.6-3.rhaos4.13.el9.x86_64                                                                                                                                                       1/4 
  Verifying        : cri-tools-1.26.0-3.el9.x86_64                                                                                                                                                             2/4 
  Verifying        : cri-o-1.26.4-3.rhaos4.13.git615a02c.el9.x86_64                                                                                                                                            3/4 
  Verifying        : openshift-clients-4.13.0-202308112024.p0.g17b7acc.assembly.stream.el9.x86_64                                                                                                              4/4 
Installed products updated.

Installed:
  cri-o-1.26.4-3.rhaos4.13.git615a02c.el9.x86_64      cri-tools-1.26.0-3.el9.x86_64      openshift-clients-4.13.0-202308112024.p0.g17b7acc.assembly.stream.el9.x86_64      runc-4:1.1.6-3.rhaos4.13.el9.x86_64     

Complete!


[root@asus3-vm1 microshift-4.14-ec4]# subscription-manager repos --enable=fast-datapath-for-rhel-8-x86_64-rpms
Error: 'fast-datapath-for-rhel-8-x86_64-rpms' does not match a valid repository ID. Use "subscription-manager repos --list" to see valid repositories.
[root@asus3-vm1 microshift-4.14-ec4]# subscription-manager repos --enable=fast-datapath-for-rhel-9-x86_64-rpms
Repository 'fast-datapath-for-rhel-9-x86_64-rpms' is enabled for this system.
[root@asus3-vm1 microshift-4.14-ec4]# yum install openvswitch-selinux-extra-policy
Updating Subscription Management repositories.
Fast Datapath for RHEL 9 x86_64 (RPMs)                                                                                                                                             396 kB/s | 181 kB     00:00    
Dependencies resolved.
===================================================================================================================================================================================================================
 Package                                                      Architecture                       Version                                    Repository                                                        Size
===================================================================================================================================================================================================================
Installing:
 openvswitch-selinux-extra-policy                             noarch                             1.0-34.el9fdp                              fast-datapath-for-rhel-9-x86_64-rpms                              14 k

Transaction Summary
===================================================================================================================================================================================================================
Install  1 Package

Total download size: 14 k
Installed size: 25 k
Is this ok [y/N]: y
Downloading Packages:
openvswitch-selinux-extra-policy-1.0-34.el9fdp.noarch.rpm                                                                                                                           80 kB/s |  14 kB     00:00    
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Total                                                                                                                                                                               80 kB/s |  14 kB     00:00     
Running transaction check
Transaction check succeeded.
Running transaction test
Transaction test succeeded.
Running transaction
  Preparing        :                                                                                                                                                                                           1/1 
  Running scriptlet: openvswitch-selinux-extra-policy-1.0-34.el9fdp.noarch                                                                                                                                     1/1 
  Installing       : openvswitch-selinux-extra-policy-1.0-34.el9fdp.noarch                                                                                                                                     1/1 
  Running scriptlet: openvswitch-selinux-extra-policy-1.0-34.el9fdp.noarch                                                                                                                                     1/1 
  Verifying        : openvswitch-selinux-extra-policy-1.0-34.el9fdp.noarch                                                                                                                                     1/1 
Installed products updated.

Installed:
  openvswitch-selinux-extra-policy-1.0-34.el9fdp.noarch                                                                                                                                                            

Complete!

[root@asus3-vm1 ~]# cd microshift-4.14-ec4/
[root@asus3-vm1 microshift-4.14-ec4]# ls
microshift-4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9.x86_64.rpm             microshift-release-info-4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9.noarch.rpm
microshift-greenboot-4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9.noarch.rpm   microshift-selinux-4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9.noarch.rpm
microshift-networking-4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9.x86_64.rpm

[root@asus3-vm1 microshift-4.14-ec4]# yum install ./*
Updating Subscription Management repositories.
Last metadata expiration check: 0:00:15 ago on Wed 20 Sep 2023 06:52:40 PM CDT.
Dependencies resolved.
===================================================================================================================================================================================================================
 Package                                     Architecture               Version                                                                     Repository                                                Size
===================================================================================================================================================================================================================
Installing:
 microshift                                  x86_64                     4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9                      @commandline                                              49 M
 microshift-greenboot                        noarch                     4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9                      @commandline                                              19 k
 microshift-networking                       x86_64                     4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9                      @commandline                                              19 k
 microshift-release-info                     noarch                     4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9                      @commandline                                              15 k
 microshift-selinux                          noarch                     4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9                      @commandline                                              24 k
Installing dependencies:
 NetworkManager-ovs                          x86_64                     1:1.42.2-6.el9_2                                                            rhel-9-for-x86_64-appstream-rpms                          60 k
 conntrack-tools                             x86_64                     1.4.7-2.el9                                                                 rhel-9-for-x86_64-appstream-rpms                         239 k
 greenboot                                   x86_64                     0.15.4-1.el9                                                                rhel-9-for-x86_64-appstream-rpms                          41 k
 libnetfilter_cthelper                       x86_64                     1.0.0-22.el9                                                                rhel-9-for-x86_64-appstream-rpms                          26 k
 libnetfilter_cttimeout                      x86_64                     1.0.0-19.el9                                                                rhel-9-for-x86_64-appstream-rpms                          25 k
 libnetfilter_queue                          x86_64                     1.0.5-1.el9                                                                 rhel-9-for-x86_64-appstream-rpms                          31 k
 openvswitch3.1                              x86_64                     3.1.0-44.el9fdp                                                             fast-datapath-for-rhel-9-x86_64-rpms                     6.8 M
 unbound-libs                                x86_64                     1.16.2-3.el9                                                                rhel-9-for-x86_64-appstream-rpms                         553 k

Transaction Summary
===================================================================================================================================================================================================================
Install  13 Packages

Total size: 57 M
Total download size: 7.8 M
Installed size: 228 M
Is this ok [y/N]: y
Downloading Packages:
(1/8): libnetfilter_queue-1.0.5-1.el9.x86_64.rpm                                                                                                                                    44 kB/s |  31 kB     00:00    
(2/8): libnetfilter_cttimeout-1.0.0-19.el9.x86_64.rpm                                                                                                                               28 kB/s |  25 kB     00:00    
(3/8): libnetfilter_cthelper-1.0.0-22.el9.x86_64.rpm                                                                                                                                24 kB/s |  26 kB     00:01    
(4/8): unbound-libs-1.16.2-3.el9.x86_64.rpm                                                                                                                                        616 kB/s | 553 kB     00:00    
(5/8): greenboot-0.15.4-1.el9.x86_64.rpm                                                                                                                                            45 kB/s |  41 kB     00:00    
(6/8): conntrack-tools-1.4.7-2.el9.x86_64.rpm                                                                                                                                      162 kB/s | 239 kB     00:01    
(7/8): openvswitch3.1-3.1.0-44.el9fdp.x86_64.rpm                                                                                                                                   7.5 MB/s | 6.8 MB     00:00    
(8/8): NetworkManager-ovs-1.42.2-6.el9_2.x86_64.rpm                                                                                                                                 46 kB/s |  60 kB     00:01    
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Total                                                                                                                                                                              2.5 MB/s | 7.8 MB     00:03     
Running transaction check
Transaction check succeeded.
Running transaction test
Transaction test succeeded.
Running transaction
  Preparing        :                                                                                                                                                                                           1/1 
  Installing       : NetworkManager-ovs-1:1.42.2-6.el9_2.x86_64                                                                                                                                               1/13 
  Installing       : greenboot-0.15.4-1.el9.x86_64                                                                                                                                                            2/13 
  Running scriptlet: greenboot-0.15.4-1.el9.x86_64                                                                                                                                                            2/13 
Created symlink /etc/systemd/system/multi-user.target.wants/greenboot-healthcheck.service → /usr/lib/systemd/system/greenboot-healthcheck.service.
Created symlink /etc/systemd/system/boot-complete.target.requires/greenboot-healthcheck.service → /usr/lib/systemd/system/greenboot-healthcheck.service.
Created symlink /etc/systemd/system/multi-user.target.wants/greenboot-task-runner.service → /usr/lib/systemd/system/greenboot-task-runner.service.
Created symlink /etc/systemd/system/redboot.target.requires/redboot-task-runner.service → /usr/lib/systemd/system/redboot-task-runner.service.
Created symlink /etc/systemd/system/multi-user.target.wants/greenboot-status.service → /usr/lib/systemd/system/greenboot-status.service.
Created symlink /etc/systemd/system/ostree-finalize-staged.service.requires/greenboot-grub2-set-counter.service → /usr/lib/systemd/system/greenboot-grub2-set-counter.service.
Created symlink /etc/systemd/system/multi-user.target.wants/greenboot-grub2-set-success.service → /usr/lib/systemd/system/greenboot-grub2-set-success.service.
Created symlink /etc/systemd/system/greenboot-healthcheck.service.requires/greenboot-rpm-ostree-grub2-check-fallback.service → /usr/lib/systemd/system/greenboot-rpm-ostree-grub2-check-fallback.service.
Created symlink /etc/systemd/system/redboot.target.wants/redboot-auto-reboot.service → /usr/lib/systemd/system/redboot-auto-reboot.service.

  Running scriptlet: unbound-libs-1.16.2-3.el9.x86_64                                                                                                                                                         3/13 
  Installing       : unbound-libs-1.16.2-3.el9.x86_64                                                                                                                                                         3/13 
  Running scriptlet: unbound-libs-1.16.2-3.el9.x86_64                                                                                                                                                         3/13 
Created symlink /etc/systemd/system/timers.target.wants/unbound-anchor.timer → /usr/lib/systemd/system/unbound-anchor.timer.

  Running scriptlet: openvswitch3.1-3.1.0-44.el9fdp.x86_64                                                                                                                                                    4/13 
  Installing       : openvswitch3.1-3.1.0-44.el9fdp.x86_64                                                                                                                                                    4/13 
  Running scriptlet: openvswitch3.1-3.1.0-44.el9fdp.x86_64                                                                                                                                                    4/13 
  Installing       : libnetfilter_cttimeout-1.0.0-19.el9.x86_64                                                                                                                                               5/13 
  Installing       : libnetfilter_queue-1.0.5-1.el9.x86_64                                                                                                                                                    6/13 
  Installing       : libnetfilter_cthelper-1.0.0-22.el9.x86_64                                                                                                                                                7/13 
  Installing       : conntrack-tools-1.4.7-2.el9.x86_64                                                                                                                                                       8/13 
  Running scriptlet: conntrack-tools-1.4.7-2.el9.x86_64                                                                                                                                                       8/13 
  Installing       : microshift-greenboot-4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9.noarch                                                                                                       9/13 
  Running scriptlet: microshift-networking-4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9.x86_64                                                                                                     10/13 
  Installing       : microshift-networking-4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9.x86_64                                                                                                     10/13 
  Running scriptlet: microshift-networking-4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9.x86_64                                                                                                     10/13 
Warning: The unit file, source configuration file or drop-ins of NetworkManager.service changed on disk. Run 'systemctl daemon-reload' to reload units.

  Installing       : microshift-selinux-4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9.noarch                                                                                                        11/13 
  Running scriptlet: microshift-selinux-4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9.noarch                                                                                                        11/13 
  Installing       : microshift-4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9.x86_64                                                                                                                12/13 
  Running scriptlet: microshift-4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9.x86_64                                                                                                                12/13 
  Installing       : microshift-release-info-4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9.noarch                                                                                                   13/13 
  Running scriptlet: microshift-selinux-4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9.noarch                                                                                                        13/13 
  Running scriptlet: microshift-release-info-4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9.noarch                                                                                                   13/13 
  Verifying        : libnetfilter_cthelper-1.0.0-22.el9.x86_64                                                                                                                                                1/13 
  Verifying        : libnetfilter_queue-1.0.5-1.el9.x86_64                                                                                                                                                    2/13 
  Verifying        : libnetfilter_cttimeout-1.0.0-19.el9.x86_64                                                                                                                                               3/13 
  Verifying        : conntrack-tools-1.4.7-2.el9.x86_64                                                                                                                                                       4/13 
  Verifying        : unbound-libs-1.16.2-3.el9.x86_64                                                                                                                                                         5/13 
  Verifying        : greenboot-0.15.4-1.el9.x86_64                                                                                                                                                            6/13 
  Verifying        : NetworkManager-ovs-1:1.42.2-6.el9_2.x86_64                                                                                                                                               7/13 
  Verifying        : openvswitch3.1-3.1.0-44.el9fdp.x86_64                                                                                                                                                    8/13 
  Verifying        : microshift-4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9.x86_64                                                                                                                 9/13 
  Verifying        : microshift-greenboot-4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9.noarch                                                                                                      10/13 
  Verifying        : microshift-networking-4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9.x86_64                                                                                                     11/13 
  Verifying        : microshift-release-info-4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9.noarch                                                                                                   12/13 
  Verifying        : microshift-selinux-4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9.noarch                                                                                                        13/13 
Installed products updated.

Installed:
  NetworkManager-ovs-1:1.42.2-6.el9_2.x86_64                                                              conntrack-tools-1.4.7-2.el9.x86_64                                                                       
  greenboot-0.15.4-1.el9.x86_64                                                                           libnetfilter_cthelper-1.0.0-22.el9.x86_64                                                                
  libnetfilter_cttimeout-1.0.0-19.el9.x86_64                                                              libnetfilter_queue-1.0.5-1.el9.x86_64                                                                    
  microshift-4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9.x86_64                                microshift-greenboot-4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9.noarch                       
  microshift-networking-4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9.x86_64                     microshift-release-info-4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9.noarch                    
  microshift-selinux-4.14.0~ec.4-202308011235.p0.gc4f572a.assembly.ec.4.el9.noarch                        openvswitch3.1-3.1.0-44.el9fdp.x86_64                                                                    
  unbound-libs-1.16.2-3.el9.x86_64                                                                       

Complete!
~~~
