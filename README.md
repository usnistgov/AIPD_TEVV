# Data and analysis workbooks for Ikonomova *et al*.-- Experimental Evaluation of AI-Driven Protein Design Risks Using Safe Biological Proxies

This repository contains the data and workbooks used to create figures contained in the publication *"Experimental Evaluation of AI-Driven Protein Design Risks Using Safe Biological Proxies."*
The files are organized as follows:
```
.
├── analysis
│   ├── blast_bestmatch.ipynb
│   ├── heatmap.ipynb
│   ├── pdz_analysis.ipynb
│   ├── t7_analysis.ipynb
│   └── ura3_analysis.ipynb
├── CODEMETA.yaml
├── CODEOWNERS
├── data
│   ├── assay
│   │   ├── pdz_all_results_df.csv
│   │   ├── t7_cfe_hierarchical_model.csv
│   │   └── URA3
│   │       ├── 2025-01-03_URA-assay_6-variants
│   │       ├── 2025-01-09_URA-assay_12-variants
│   │       ├── 2025-01-15_URA-assay_16-variants
│   │       ├── 2025-01-16_URA-assay_16-variants
│   │       ├── 2025-01-18_URA-assay_16-variants
│   │       ├── 2025-01-24_URA-assay_16-variants
│   │       ├── 2025-01-25_URA-assay_16-variants
│   │       ├── 2025-01-28_URA-assay_16-variants
│   │       ├── 2025-03-14_URA-assay_16-variants
│   │       ├── 2025-03-18_URA-assay_16-variants
│   │       ├── 2025-03-25_URA-assay_16-variants
│   │       └── 2025-04-22_URA-assay_16-variants
│   ├── blast
│   │   ├── psd95pdz3_blast_results.csv
│   │   ├── t7rnapol_blast_results.csv
│   │   └── ura3_blast_results.csv
│   ├── fasta
│   │   ├── psd95pdz3.fasta
│   │   ├── t7rnapol.fasta
│   │   └── ura3.fasta
│   ├── output
│   │   ├── pdz_blast_flags.csv
│   │   ├── pdz_insilico_merged.csv
│   │   ├── t7_insilico_merged.csv
│   │   ├── t7rnapol_blast_flags.csv
│   │   ├── ura3_blast_flags.csv
│   │   └── ura3_insilico_merged.csv
│   ├── selected_sequences.csv
│   └── ura3_plasmid_list_with_sequence.csv
├── fair-software.md
├── LICENSE.md
├── README.md
└── requirements.txt
```

- `/analysis` contains the workbooks; `/data` contains all data.
- `requirements.txt` contains all necessary Python modules to run the workbooks.
- All Jupyter notebooks are tested on MacOS 15.4, Python 3.12.

## Analysis
### blast_bestmatch
This workbook generates the csv files containing best matches to synthetic homologs using NCBI BLAST+. Results are saved to `data/blast` and used in other analysis notebooks.

### heatmap
This workbook generates the heatmap from publication Figure 3, using normalized primary assay data from all protein targets.

### {protein}_analysis
These workbooks generate the individual plots for the synthetic homolog primary assay results, used to create publication Figures 2-4 and various Supplementary Figures.

### seqid_vs_tm
This workbook calculates and plots the relationship between number of sequence substitutions from wildtype in synthetic homologs and calculated TM-score when compared to wildtype. An example for PDZ3 is seen in publication Figure S13.

## Data
`selected_sequences.csv`: contains the *in silico* metrics for all synthetic homologs.

`ura3_plasmid_list_with_sequence.csv`: contains the DNA plate locations and identifiers for URA3 synthetic homologs, used to map identifiers to assay results.
### assay
This folder contains the data collected in primary assays of synthetic homologs.
### blast
This folder contains the output of the `blast_bestmatch` workbook: best match entries for all synthetic homologs, if found. Blank cells indicate a match was not found.
### fasta
This folder contains amino acid or DNA fasta sequences for all synthetic homologs, used by `blast_bestmatch` to calculate best match entries.
### output
This folder contains all data exported by the analysis workbooks, including merged experimental and *in silico* datasets for synthetic homologs and results of BLAST flagging analysis.

## Citation
- Ikonomova, S. P., Wittmann, B. J., Piorino, F., Ross, D. J., Schaffter, S. W., Vasilyeva, O., Horvitz, E., Diggans, J., Strychalski, E. A., Lin-Gibson, S., & Taghon, G. J. (2025 May X). *Experimental evaluation of AI-driven protein design risks using safe biological proxies*. bioRxiv. https://doi.org/XXXX

BibTeX:
```
@unpublished{Ikonomova2025_TEVV,
  author = {Ikonomova, Svetlana P. and Wittmann, Bruce J. and Piorino, Fernanda and Ross, David J. and Schaffter, Samuel W. and Vasilyeva, Olga and Horvitz, Eric and Diggans, James and Strychalski, Elizabeth A. and Lin-Gibson, Sheng and Taghon, Geoffrey J.},
  title = {Experimental Evaluation of {AI}-Driven Protein Design Risks Using Safe Biological Proxies},
  year = {2025},
  month = {May},
  day = {X},
  note = {bioRxiv preprint},
  doi = {10.1101/XXXX},  % Replace XXXX with actual DOI
  url = {https://doi.org/10.1101/XXXX}  % Replace XXXX with actual DOI
}
```

## Contact information
For questions pertaining to these files or the publication in general, please contact:

- geoffrey.taghon@nist.gov (Jupyter notebooks, CSV data)
- bwittmann@microsoft.com (AI sequence generation)
