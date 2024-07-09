# DeepDSMRI
**DeepDSMRI: Deep Domain Shift Analyzer for MRI**

The paper has been accepted at the 28th UK Conference on Medical Image Understanding and Analysis - MIUA

## Abstract
The use of MR images in medical image analysis from different centers in clinical applications and medical research has grown in popularity. However, challenges arise due to inherent variability between centers, leading to domain shift issues that reduce the reliability and robustness of the analysis results. Furthermore, the lack of suitable tools for analyzing domain shift hampers the progress of developing and validating domain adaptation and harmonization techniques. Utilizing pre-trained deep models as feature extractors, we introduce a novel framework called DeepDSMRI (Deep Domain Shift analyzer for MRI), designed explicitly to comprehend the extent of domain shift in MRI datasets. DeepDSMRI provides adequate insights into the existence of domain shift for diverse MRI modalities, including structural, functional, and diffusion-weighted images. The proposed framework incorporates visualization tools (e.g., t-SNE and UMAP) to illustrate grouping similar data and isolating dissimilar data into distinct clusters. Moreover, the quantitative analysis measures the classification accuracy between domains and the domain shift distance. The efficacy of the proposed DeepDSMRI is demonstrated through experimental assessments conducted on seven extensive multi-center neuroimaging databases.

![Proposed_model](https://github.com/rkushol/DeepDSMRI/assets/76894940/aa469b6e-ade0-4e2d-aa51-f898e00bec03)


The complete code will be released soon.


## Requirements
medpy  
pandas  
scikit-learn  
umap-learn  
numpy  
scipy  
matplotlib  
scikit-image  
seaborn  
nibabel  
plotly   


To create a new conda environment: `conda create -n deep_dsmri python=3.9`

To install all the packages from the requirements.txt file: `pip3 install -r requirements.txt`

## Datasets
ADNI, AIBL, PPMI and ABIDE datasets can be downloaded from [ADNI](http://adni.loni.usc.edu/) (Alzheimer’s Disease Neuroimaging Initiative)

CALSNIC dataset can be requested from [CALSNIC](https://calsnic.org/) (Canadian ALS Neuroimaging Consortium)


## Command
Run `python deep_dsmri.py output_folder_name “input directory”`. For example, `python deep_dsmri.py CALSNIC1 "D:\DS_MRI\Dataset\CALSNIC1"`. It will generate `features.csv` and `results.tsv` in the `Results/CALSNIC1` folder.

## Hyper-parameters
`-b`-> number of gap in consecutive slices, default= 5. The features will be extracted from an interval of five slices by default. Setting the value as `1` will consider every slice in the range.   
`-c`-> percent of central images, default= 70. The first 15% and last 15% slices will not be considered by default. Setting the value as `100` will start the slice range from first to last.  
`-p`-> perplexity for t-SNE method, default= 30. The t-SNE method requires the total samples to be greater than the value of perplexity. The perplexity is related to the number of nearest neighbours. Larger datasets usually require a larger perplexity. Consider selecting a value between 5 and 50.

## Contact
Email at: kushol@ualberta.ca
