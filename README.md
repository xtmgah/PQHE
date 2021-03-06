# Pooled QTL Heritability Estimator (PQHE)
**Pooled QTL Heritability Estimator (PQHE)** is a method to estimate QTL heritability using pooled sequencing data obtained under different experimental designs. This method was implemented via R programming. The R script of PQHE can be used at command line from terminal.

# Introduction
Bulked segregant analysis (BSA) is originally proposed for rapid identification of molecular markers associated with a trait of interest. In recent years, next generation sequencing (NGS) technologies have been applied to BSA. By referring to a known genome sequence, a huge number of markers (mainly single nucleotide polymorphisms, SNPs) can be detected and mapped simultaneously by NGS. This greatly enhances the power of BSA. Such NGS-assisted BSA (abbr. BSA-seq) has proven to be an efficient and cost-effective method for quick mapping of single major genes as well as quantitative trait loci (QTLs). QTL mapping by BSA-seq, or termed ‘pooled QTL mapping’, is very fascinating because it requires to genotype (sequence) only a pair of DNA pools in-stead of many individuals. 

Although pooled QTL mapping has the significant advantage of being simple and fast, it also has an obvious weakness. In conventional QTL mapping studies, both QTL location and QTL heritability (the proportion of phenotypic variation contributed by a QTL) can be estimated. Up to now, however, QTL heritability estimation in pooled QTL mapping has not been realized.

To solve this weakness, we propose a method for pooled QTL heritability estimation. To make this method widely useful, this method was implemented by R language and the R script is provided in this project (PQHE).

# Download and installation
R script (pooled_QTL_heritability_estimator.R) can be directly downloaded and used in batch mode of R.

# Required R package
Before using the R script of PQHE, the R package [rootSolve](https://cran.r-project.org/web/packages/rootSolve) must be installed.

    install.packages("rootSolve")

In the R script (estimate_QTL_heritability.R), R package [rootSolve](https://cran.r-project.org/web/packages/rootSolve) is used for solving nonlinear equations.

# Command line usage

    Rscript estimate_QTL_heritability.R example_conf.txt

Rscript comes with R, and it can replace R CMD BATCH to run R scripts in R batch mode. The path of Rscript should be added in the system environment. The estimation results will be printed in the terminal.

# Examples
# Example1.rice_Chr3.conf.txt
    b   = 0.25   # F2 population
    m1  = 50     # individuals in pool-1
    m2  = 50     # individuals in pool-2
    n   = 531    # sample size of population 
    AF1 = 0.724  # estimated bulked allele frequency in pool-1
    AF2 = 0.114  # estimated bulked allele frequency in pool-2


# Example2.rice_Chr6.conf.txt
    b   = 0.5    # RILs population
    m1  = 20     # individuals in pool-1
    m2  = 20     # individuals in pool-2
    n   = 241    # sample size of population 
    AF1 = 0.875  # estimated bulked allele frequency in pool-1
    AF2 = 0.075  # estimated bulked allele frequency in pool-2


# Example3.yeast_Chr13.conf.txt
    b   = 0.5    # haploid population
    m1  = 32     # individuals in pool-1
    n   = 301    # sample size of population 
    AF1 = 0.865  # estimated bulked allele frequency in pool-1



# Example4.yeast_Chr15.conf.txt
    b  = 0.5     # haploid population
    m1  = 32     # individuals in pool-1
    n   = 301    # sample size of population 
    AF1 = 0.125  # estimated bulked allele frequency in pool-1
    AFU = 0.625  # estimated bulked allele frequency in unselected/random pool or total population
