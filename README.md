# Covid-19 Data Resources

The COVID-19 pandemic has generated an enormous demand for data in
India and around the world. Policymakers responding to the crisis need
data on the spread of the disease, the healthcare resources at their
disposal and the economic hardships being faced by the
population. Epidemiologists need data to parameterize their models and
estimate the dangers. Economists need data to assess the tradeoffs
between policy alternatives. 

This repository represents an effort by the [Development Data
Lab](devdatalab.org) to provide some these data in the form of an
administrative data backbone with local estimates of health system
capacity and local economic conditions. We'll supplement what's here
with additional information like real-time COVID-19 case data and
further demographic and economics data; we have many variables and
data sources we've identified and targeted for inclusion, but are
limited by manpower.

| ![Hospital Beds by District](assets/dlhs4_perk_beds_pubpriv.png?raw=true "Hospital Beds") | 
|:--:| 
| *Hospital Bed Availability by District* |

## Repo Structure

| Directory   | Explanation |
| ----------- | ----------- |
| a/          | Analysis file with material used in the *current* version of the data build.
| b/          | Build folder.  |
| e/          | Explore folder. |
| assets/     | Various web assets, such as images embedded in `README.md`.  |

The root path of the folder only has one code file:
- `make_covid.do`, which runs the full build and the full analysis.

### Code Globals

This repository's build refers to locations of code and data using
Stata global variables. You will need to set the following globals to
run the code:

| Global   | Explanation |
| ----------- | ----------- |
| `$tmp`          | A temporary folder for intermediate data and outputs.
| `$ccode`          | Root folder for this repository.  |
| `$hosp`          | Output folder for hospital data. |

A global can be set in Stata with e.g. `global tmp temporary/directory/location`.

## Downloading the Data

This repository is structured such that the first half runs on
Development Data Lab servers to produce datasets that serve as inputs
for the Covid-related analytics, like the EC microdata file, the DLHS
district-level aggregates, and a shortened VD/TD/PCA. These files have
been compressed into a single archive available
[here](https://dl.dropboxusercontent.com/s/80igbve4f751rz1/ddl_covid_input_data.tar.gz?dl=0). 

The second half then needs to run on those files to produce the final
outputs, like the hospital bed estimates. If you are interested in
downloading those data without running any of the code, you can do so
[here](https://dl.dropboxusercontent.com/s/ig9u8ol45445vdl/ddl_covid_output_data.tar.gz?dl=0).

## Metadata

Metadata tables describing the datasets and variable specifications
for these data can be found
[here](https://github.com/devdatalab/covid/blob/master/assets/metadata.md).
