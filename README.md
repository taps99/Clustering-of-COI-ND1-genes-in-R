# Using unsupervised machine learning to cluster two genes (COI and ND1) in Microchiroptera in R.


# Objective
The specific objective of this study is to compare the clustering patterns of the COI and ND1 genes in the
family Microchiroptera using unsupervised clustering. In particular, I will be clustering the genes using
k-mer frequencies as the primary sequence feature for this analysis. I will also be comparing the degree of
clustering between two k-mer lengths for each gene (k-mers of 4 and 6). Do COI and ND1 exhibit different
clustering patterns within the Microchiroptera family, and does clustering strength between these genes
increase with increasing k-mer length?


# Description of Data Set
For my analysis, I’ve chosen to analyze two genes from the Microchiroptera family: COI and ND1. The
main reason I chose these genes is because I knew that there was going to be a lot of data present for these
particular genes, since they are commonly used in these types of analyses. I needed to pick genes with a good
amount of data since I wanted to use k-mer frequencies as my sequence feature of choice to use for clustering,
which requires more data than if I were to use alignments. This sequence data was obtained from Nucleotide
database from NCBI using the entrez package in R. Since there was a large amount of data to fetch from
the database, I used the functions from the EntrezFunctions script provided by our instructors to obtain and import the data into RStudio. 
I separated the data from each gene into their own data frames, which
contained 18202 COI sequences and 1973 ND1 sequences respectively. My first step was to filter for any
duplicate sequences, which removed nearly 50% of the COI sequences. My goal was to equalize the number
of sequences before starting my analysis, which I did by randomly sampling from the 9685 remaining COI
sequences. Finally I also removed sequences that I thought were low-quality such as sequences with very
long lengths or with a high percentage of N’s within them. The final number of sequences was 1411 COI
sequences and 1256 ND1 sequences.

Source of dataset citation: Nucleotide. Bethesda (MD): National Library of Medicine (US), National
Center for Biotechnology Information; 2004 – 2022-12-15. Available from: https://www.ncbi.nlm.nih.gov/
nucleotide/


![image](https://github.com/taps99/Clustering-of-COI-ND1-genes-in-R/assets/88162045/84b0e0f5-711e-484e-a1cc-882a04a3e63b)


# Results & Discussion
By looking at the results of this analysis, it is clear to see that the ND1 gene exhibits far better clustering
patterns than the COI gene within the family Microchiroptera. The cluster plots demonstrates this obvious
difference between the clustering patterns of both genes (Figure 3). This is further supported by the Silhou-
ette plots that showcase the difference in cluster strength between both genes (Figure 4). ND1 sequences
had a much larger average silhouette width compared to COI sequences. Silhouette indices range from -1 to
1, where 1 is indicative of optimal clustering (Gentleman & Carey, 2008). These results were not expected,
as COI is the hallmark gene used for DNA barcoding. Therefore, I estimated that the clustering patterns for
COI would be more distinct than what my analysis has shown. I did not expect to see such a big difference
in the degree of clustering between these two genes, as they are both mitochondrial genes from the same
taxonomic group. In terms of comparing k-mer lengths (4 and 6), I expected to see stronger clustering as
k-mer length increased.

The conclusions of this analysis are not completely definitive, as there are many parameters and methods
that could be altered to achieve potentially more accurate results. For instance, a larger sample size could
have influenced the clustering patterns seen between both genes. As mentioned before, I had to randomly
sample from the abundance of COI sequences to equalize the number of sequences to that of the ND1 gene.
Of course, the clustering method, metrics, and parameters chosen throughout this analysis could also all
be altered in order to give potentially different results. In the context of choosing the optimal number of
clusters, I simply used a heuristic method of determining that number by using the silhouette method plots.
This served as a guideline for my analysis, instead of just arbitrarily choosing a number of clusters to work
with. In terms of choosing the optimal k-mer length for my analysis, I had to find a ‘sweetspot’ between
using a length that would give me the best results, and a length that is computationally feasible for me to
work with. As a result, I found that a k-mer length of 6 was the optimal choice for my analysis, since I found
that any larger k-mer values took far too long to compute. There exists methods to computing the optimal
k-mer length using and comparing abundance histograms for different lengths, but these methods take a lot
of time to perform (Chikhi et al., 2014).

The next steps in this research would involve using alternative clustering methods that for these specific
genes (such as hierarchical clusters and k-means clustering) and seeing how the results might change. For
instance, the application of hierarchical clustering of DNA k-mers for RNA-seq data was already done in a
study by Kaisers et al. (2018). If I were to conduct a larger project on this topic, I would investigate and
compare different clustering methods to see which ones would reveal the most accurate clustering patterns
in a given set of sequence data. I would also look to investigate the possibility of clustering for larger k-mer
lengths, to see if the results seen in my analysis align with the results of this future research. The results of
my analysis showcase difference between the clustering patterns of the COI and ND1 genes, which could be
worth further investigating to better understand which genes are more suitable for taxonomic classification
in a given taxonomic group.
