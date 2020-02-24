
# tmVar Variant Normalization Instructions

One of the key innovations described in the publication [tmVar: A text mining approach for extracting sequence variants in biomedical literature](https://www.ncbi.nlm.nih.gov/research/bionlp/Tools/tmvar/) is a method of normalizing extracted variant mentions to unique identifiers (dbSNP RSIDs). However it is unclear how this feature can be used and running the `tmVar` model out of the box does not produce this behaviour. To normalize extracted variants `GNormPlus` must first be run on the input data and the results of this must be fed into `tmVar`.

## Getting Started

- Download `GNormPlus` from the NCBI's [website](https://www.ncbi.nlm.nih.gov/research/bionlp/Tools/gnormplus/) and decompess the folder.
- Install `tmVar` from the NCBI's [website](https://www.ncbi.nlm.nih.gov/research/bionlp/Tools/tmvar/) and extract it into the same directory as `GNormPlus`.

## Directory Structure

```
project
│
└─── gnormplus_input
└─── gnormplus_output
└─── tmvar_output
│
└───tmVar
│   │   corpus
│   │   CRF
│        ...
│   
└───GNormPlus
    │   Corpus
    │   CRF
        ...
```

## Example Run

```
java -Xmx10G -Xms10G -jar tmVar.jar gnormplus_input gnormplus_output
java -Xmx10G -Xms10G -jar GNormPlus.jar gnormplus_output tmvar_output setup.txt

```

## Acknowledgments

* Chih-Hsuan Wei for clarifying this process.
