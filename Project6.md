## PROJECT 6: Web Solution With WordPress

To begin with, I launched two EC2 instances using Redhat (not Ubuntu). One instance will serve as the 'Web Server' while the other will serve as the 'Database Server'.

Next, I create 3 volumes in the same AZ (Availability Zone) as my Web Server EC2, each of 10 GiB and respectively name web1, web2 and web3.

![](./images/volumes.PNG)

Next, I attached all three volumes one by one to the Web Server EC2 instance, as displayed below:

![](./images/attached_volumes.PNG)


From my webserver instance, I ran the command below to confirm that my volumes have been successfully attached:

`lsblk`


![](./images/volue_instance.PNG)

To see all (available) mount points and free space on my server, I ran this command:

`df -h`

The output is displayed below:

![](./images/mount_point.PNG)

Next, I used the *gdisk* utility to create a single partition on each of the 3 disks, beginning with the first volume, using the command below:

`sudo gdisk /dev/xvdf`

The configuration is displayed below:

![xvdf disk configuration](./images/xvdf_volume.PNG "xvdf disk configuration")

I repeated the last step for the *xvdg disk*, as below:

`sudo gdisk /dev/xvdg`

![xvdg disk configuration](./images/xvdg_disk.PNG "xvdg disk configuration")

Similarly, the previous step was repeated the *xvdh disk*, as below:

`sudo gdisk /dev/xvdh`

![xvdh disk configuration](./images/xvdh_disk.PNG "xvdh disk configuration")