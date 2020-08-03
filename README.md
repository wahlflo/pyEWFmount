# pyEWFmount
A python cli wrapper script for mounting ewf files

## Installation

### Install requirement ewfmount
Install libewf with pacman:
```
sudo pacman -S libewf
```
or ewf-tools with apt:
```
sudo apt install ewf-tools
```

### Install requirement dislocker:
Install dislocker from GitHub:
```
git clone https://github.com/Aorimn/dislocker
cd dislocker
cmake .
make dislocker-fuse;
sudo make install
```


### Install pyEWFmount
```
pip3 install py_ewf_mount
```

## Usage
Type ```pyEWFmount --help``` or ```pyMountEWF --help``` to view the help.
```
pyEWFmount by Florian Wahl, 03.08.2020

usage: pyMountEWF [-h] [-i INPUT] [-o OUTPUT]

optional arguments:
  -h, --help            show this help message and exit
  -i INPUT, --input INPUT
                        path to a EWF file which should be mounted
  -o OUTPUT, --output OUTPUT
                        Specify the name of the mounted directory (default: /mnt/YYYY.MM.DD_hh.mm)
```

## Example
```
$ sudo pyMountEWF -i forensic_image.E01
pyEWFmount by Florian Wahl, 02.08.2020

[+] ewf file mounted to "/mnt/2020.08.03_18.49/.ewf"
[+] Select Partition to mount:
Disk /dev/loop6: 1011 MiB, 1060110336 bytes, 2070528 sectors
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disklabel type: dos
Disk identifier: 0x24677b2d

Device       Boot Start     End Sectors  Size Id Type
/dev/loop6p1       2048 2070527 2068480 1010M  7 HPFS/NTFS/exFAT

select number of partition (0 for complete disk) [1] >
[+] selected partition "/dev/loop6p1"
Bitlocker Recovery Key (if encrypted otherwise empty) > 493625-443036-224400-065417-708741-624547-702218-359777
Mount in readonly mode (y/n) [y]: y
Mount as NTFS filesystem (y/n) [y]: y
[+] Partition 1 was mounted under "/mnt/2020.08.03_18.49/partition_1_decrypted"

Press ENTER to mount another partition
```