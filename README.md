# AIMER
The Aimer software package is  a computational pipeline for analyzing bisulfite sequencing data (WGBS and RRBS). 
Aimer can assess methylation level of each cytosine, and discover the imprinted region in the whole genome.

Release AIMER 1.0
===============

## Install AIMER 1.0

### Required libraries
* The GNU Scientific Library: this has always been required. It can be
  installed using `apt` on Linux, using `brew` on macOS, or from
  source available [here](http://www.gnu.org/software/gsl).

### Configuration

1. Download AIMER.zip [here](https://github.com/yanrui2020/AIMER.git)
2. Unpack the archive:
```
$ tar -zxvf AIMER.zip
```
3.Set environment variables
```
4.Get Dpendent software
```
* `numpy <http://www.numpy.org>`_, version 1.8.2
* `pyfasta<http://www.pyfasta.org>`_, version 

Usage
=====
Step 1
Get each bin score
```
Input: BS-seq.sam
get_AMR_single_base_resolution.py -f input.sam -b 300 -c 20 -g genome -o Diff_socre.bed
Options
-f The file name of mixing tissue, only accept bam file currently
-b Length of each bin, default is 300
-c Lowest coverage cutoff in each bin, default is 20

Step 2 
Get importing region
```
Input: Diff_score.bed  output of get_AMR_single_base_resolution.py
DMR_finder.py -b Input.bed -m 0.4 -s 0.7 -g 700 -c 10 -o AMR.bed
Options
```
-b INPUT_BIN, --input_bin=INPUT_BIN
                        input file, output of get_AMR_single_base_resolution.py
-m PROPORTION, --proportion=PROPORTION
                        proportion of minor
                        part,min(m1,m2)/(m1+m2),default=0.4
-s DIFFSCORECUTOFF, --DiffScoreCutoff=DIFFSCORECUTOFF
                        the cutoff of diff_score to extend a merged
                        AMR,default=0.7
-g GAP, --Gap=GAP     the gap length to extend a merged AMR,default=700
-c CG, --CG=CG        the cg number of sigle bin to extend a merged
                        AMR,default=10
-o OUTPUTFILENAME, --outputfilename=OUTPUTFILENAME
                        the output file name (with path), bed format
 

Contacts and bug reports
====================

Qian Zhao 
zhaoq@tmu.edu.cn
Yanrui Luo
luoyanrui@hotmail.com

Copyright and License Information
==========================
Copyright (C) 

Current Authors: Qian Zhao  Yanrui Luo

This is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This software is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.
