- Preprocessing - Raw data QC 

## 1. Create conda new conda environment.
```
conda create --name rna_seq
```

## 2. list environments to see created conda environment
```
conda list env
```

## 3. Activate environment.
```
conda activate rna_seq
```

## 4. Install gffread.
```
conda install -c bioconda gffread
```

## 4. Install gffread.
```
conda install -c bioconda gffread
```
## 5. Change directory to where the files are or you could provide the absolute path to the respective inputs

## 6. convert the .gff3 to gtf
```
gffread -E -F -T Tribolium_castaneum.gff3 -o Tribolium.gtf
```
## 7. Install the hisat2 aligner
```
conda install -c bioconda hisat2
```

## 8. Unzip the file first genome fasta file
```
tar -xf Tribolium_castaneum.genome.fa.tar.bz2
```
## 9. Build the genome with the untarred file
```
hisat2-build Tribolium_castaneum.genome.fa TriboliumBuild
```
## 10. Try running hisat on one file/sample
```
hisat2 -q -x TriboliumBuild -U SRR8288561.fastq.gz -S SRR8288561_accepted_hits.sam
```
## 11. Once you confirm hisat2 is running, you repeat this for all the other samples.
