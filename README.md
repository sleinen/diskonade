# diskonade

When your disks are lemons...

## Motivation

I help operate some OpenStack clusters built from modern commodity
servers.  The clusters use [Ceph](http://ceph.com/) and
[Quobyte USP](http://www.quobyte.com/) for distributed storage.  Data
is stored on 4TB disks in some of these commodity servers.  The disks
are of the "datacenter capacity" category.  In the first 22 months of
operation, we lost 23 of 384 disks to disk errors.  This gave us many
opportunities to learn how to streamline our processes.  So far we
have worked with Wiki pages to document our procedures, but the
instructions have become unwieldy over time, and we need some
automation.

## Prerequisites

The script expects a few tools to be installed.  On a Debian/Ubuntu
system, the following packages should be there:

* freeipmi
* smartmontools
* hdparm

In addition, the script tries to use the "sas2ircu" (for LSI SAS2008
HBAs) or "sas3ircu" (for Broadcom SAS3008 HBAs) command to obtain
physical location information about the broken disk.  This program is
specific to LSI disk controllers and can be obtained from the vendor.
