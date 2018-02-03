# Assign3
## Spring 2018

The purpose of this exercise is to get comfortable creating scripts using vim on a server, while teaching you the remainder of bash scripting you'll need as a foundation for this course. The scripts themselves are not particularly exciting but they are the building blocks you'll need.  You will be asked to create 11 scripts, which all come from http://dtg.usc.edu/tgrn510/index.php/bash-scripting/.  These are to all be placed in your "bin" directory. The results of running these should be put into a forked version of this github. 

The final question is considerably more difficult and requires you to put concepts together you have learned at this point.

 Completion means the scripts work in your home directory and you have put the results in your github where you will replace the placeholder text with the results from running the script. For exampler, you should replace

*REPLACE WITH RESULTS*

with codeblock text using backticks, which show both the program being called in trgn510.pmed.io and the result.  After, it should be:

`
davidcraig@trgn510:~/bin ls | test.sh
TEST.SH
`

### 1
Please create pointless.sh, changing from printing your hostname with $HOSTNAME, to your $USER

`
[varshagi@trgn510 bin]$ ./pointless.sh

varshagi
5
6

`

### 2
Please create quotequotes.sh, please add 1 additional lines that prints the process id of the current script using a special variable in a sentence: "The process id for this script is **235**'

`
[varshagi@trgn510 bin]$ ./quotequotes.sh
varshagi
VARIABLE
I am on varshagi
I am on $USER
I am on $USER
The process id of this script is 1609

`

### 3
Please create processes.sh.  Modify it such that it prints the top 5 CPU consuming processes

`
[varshagi@trgn510 bin]$ ./processes.sh
varshagi 28936  0.0  0.0 113128   564 pts/5    S+   18:44   0:00 /bin/bash ./processes.sh
varshagi 28937  0.0  0.0 151200  1884 pts/5    R+   18:44   0:00 ps -ax -u --sort pcpu
varshagi 28938  0.0  0.0 112660   960 pts/5    S+   18:44   0:00 grep varshagi
varshagi 28939  0.0  0.0 107940   672 pts/5    S+   18:44   0:00 tail -n 5
davidcr+ 32695  0.0  0.0 178124  3444 pts/2    S+   Feb02   0:00 ssh varshagi@trgn510.pmed.io

`
### 4
Please create makeupper.sh.  Modify it to return lower case results, and change the name to makelower.sh

`
[varshagi@trgn510 bin]$ ps -ef | makelower.sh | head
uid        pid  ppid  c stime tty          time cmd
root         1     0  0 jan19 ?        00:03:11 /usr/lib/systemd/systemd --switched-root --system --deserialize 19
root         2     0  0 jan19 ?        00:00:00 [kthreadd]
root         3     2  0 jan19 ?        00:00:00 [ksoftirqd/0]
root         5     2  0 jan19 ?        00:00:00 [kworker/0:0h]
root         7     2  0 jan19 ?        00:00:01 [migration/0]
root         8     2  0 jan19 ?        00:00:00 [rcu_bh]
root         9     2  0 jan19 ?        00:00:59 [rcu_sched]
root        10     2  0 jan19 ?        00:00:05 [watchdog/0]
root        11     2  0 jan19 ?        00:00:04 [watchdog/1]

`

### 5
Referring to math.sh, create a script called add.sh that takes two inputs and adds them, **add.sh 5 3** 
`
[varshagi@trgn510 bin]$ add.sh 9 9
18

`

### 6
Create a program "mb_or_kb.sh", referring to bigornot.sh and useful.sh, create a script called big file that checks to see if the file exists provided as the first argument exists, and if it exists then gets the filesize, storing it as a variable. I have not provided you with a way to get filesize in exercise, and expect you to search web for a way.  The program then checks to see if the size is greater than 1,000,000.  If its less then 1,000,000, it prints the number of kilobytes (divide by 1000) followed by "kB".  If its greater than 1,000,000, then print the number of megabytes followed by "MB".

`

[varshagi@trgn510 bin]$ sh mb_or_kb.sh
 enter file name
HG001_GRCh37_GIAB_highconf_CG-IllFB-IllGATKHC-Ion-10X-SOLID_CHROM1-X_v.3.3.2_highconf_PGandRTGphasetransfer.vcf.gz
 file exists and is not empty
134602752
cut: 134602752: No such file or directory
file size is in 134.60 mb

`

### 7
Create a program "count_by_to.sh", referring to count.sh.  The file should take two arguments, and should count jumping by the first argument until the second argument is reached, starting at 0.  For example, *count.sh 2 10* would print 0 2 4 6 8 10

`

[varshagi@trgn510 bin]$ count.sh 2 10
0
2
4
6
8
10

`

### 9
Please create whatgene.sh.  Please edit such that the function print_gene, prints upper case of the input.

`
[varshagi@trgn510 bin]$ ./whatgene.sh
mygene PTEN
mygene JUPITER

`

### 10
Please create a bash shell called "genotype.sh" that takes a VCF as argument 1, and prints space delimited chromosome, position, reference, alternative, and genotype for all genotypes in VCF.

`
[varshagi@trgn510 bin]$ ./genotype.sh~/projects/assign2/HG001_GRCh37_GIAB_highconf_CG
-IllFB-IllGATKHC-Ion-10X-SOLID_CHROM1-X_v.3.3.2_highconf_PGandRTGphasetransfer.vcf | head 1 239339 A G 0/1 1 239482 G T 0/1 1 240147 C T 0/1 1 240898 T G 0/1 1 567239 CG C 1|1 1 568745 C CCA 0/1 1 837214 G C 0|1 1 838153 CA C 1|1 1 842825 A G 1|1 1 845283 G T 1|1

`
