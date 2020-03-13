TwoSampleMR v0.5.3 (Release candidate)
==============

Changes:

* When converting to MRInput format and supplying an LD matrix, the LD matrix SNP order was not matching the summary data order. Credit goes to Mona Almramhi for spotting and fixing this issue.
* Reinstating all datasets that were previously disabled (ukb-a, ukb-d, ubm-a)


TwoSampleMR v0.5.2 (Release date: 2020-03-11)
==============

Changes:

* No longer marking LD functions as deprecated for now. Thanks to Jonas Bovijn for discussions on this.
* Various fixes for `R CMD check` warnings and notes.


TwoSampleMR v0.5.1 (Release date: 2020-02-14)
==============

Changes:

* A number of datasets have been found to have issues since 0.5.0. These include"
* Some a minority of non-effect alleles being incorrect in the ieu-a batch. The consequence of this is harmonisation may have thrown out some SNPs due to harmonisation mismatches. Error arose in 0.5.0 and now fixed
* p-value issues with the ubm-a batch. This would have led to fewer top-hits being identified than they should have. Error arose in 0.5.0 and currently disabled
* Effect allele frequency issues with the ukb-a batch, potentially due to misreported effect alleles. Error arose in 0.5.0 and currently disabled


TwoSampleMR v0.5.0 (Release date: 2020-01-01)
==============

Changes:

* Major update, details here: https://mrcieu.github.io/TwoSampleMR/articles/gwas2020.html


TwoSampleMR v0.4.26 (Release date: 2019-12-01)
==============

Changes:

* Improved precision of low p-values in steiger tests. Thanks to Hannah V Meyer and Tom Palmer for this.
* Improved instrument extraction for new datasets


TwoSampleMR v0.4.25 (Release date: 2019-09-12)
==============

Changes:

* Changes in googleAuthR package break authentication. Added interception to install older version while this is being fixed. Please use `devtools::install_github("MarkEdmondson1234/googleAuthR@v0.8.1")`


TwoSampleMR v0.4.24 (Release date: 2019-09-10)
==============

Changes:

* Bug found in extract_instruments when requesting non-default parameters. Thanks to Shantanu Bafna for pointing this out.


TwoSampleMR v0.4.23 (Release date: 2019-08-12)
==============

Changes:

* Forcing server to `extract_instruments` when pre-computed outcomes are not present by default. The old behaviour is still possible by setting `extract_instruments(force_server_if_empty=FALSE)`


TwoSampleMR v0.4.22 (Release date: 2019-02-22)
==============

Changes:

* Changing default API address in preparation for moving to version 0.5.0 which will use the new API


TwoSampleMR v0.4.21 (Release date: 2019-02-19)
==============

Changes:

* Updated mixture of experts


TwoSampleMR v0.4.20 (Release date: 2019-01-31)
==============


Changes:

* The harmonise function now returns a summary of the harmonisation procedure e.g. number of SNPs removed etc. Access via attr(obj, "log")
* Note that this has been tested and shown to give the same results as previously but there is a chance that it might lead to slightly different behaviour. Please install the previous version if you would prefer to avoid possibilities of changed behaviour - devtools::install_github("MRCIEU/TwoSampleMR@0.4.18")


TwoSampleMR v0.4.19 (Release date: 2019-01-31)
==============

Changes:

* Fixed a bug in mr_heterogeneity that would have impacted a minority of cases. If the method list was being specified then the order of the results didn't always match the method (MR Egger and IVW were mixed up). This did not affect default usage. Thanks to Anna Guyatt for pointing this out.
* Added index of suspicion functionality, and penalised mode estimator
* Added transformation function to scale effect estimate units to SD scale
* Starting to write change log again!



TwoSampleMR v0.4.18 (Release date: 2018-12-03)
==============

Changes:

* Improved performance of harmonisation


TwoSampleMR v0.4.17 (Release date: 2018-12-03)
==============

Changes:

* Added facility to harmonise indels


TwoSampleMR v0.4.17 (Release date: 2018-12-03)
==============

Changes:

* Documentation and options added to multivariable MR


TwoSampleMR v0.3.4 (Release date: 2017-11-30)
==============

Changes:

* Moving over to elastic search database so the request batching is changing from 50 SNPs per chunk to 10000. This can be modified through extract_outcome_data(splitsize=50)
* Changing harmonise_data behaviour - now does not discard the bad SNPs but retains them with the mr_keep column indicating whether or not they will be used by the mr analysis functions
* Fixed issue with oauth token
* Updated scatter plot to register the mr_keep column.


TwoSampleMR v0.3.3 (Release date: 2017-11-23)
==============

Changes:

* Fixed bug in singlesnp and leaveoneout analyses


TwoSampleMR v0.3.2 (Release date: 2017-11-22)
==============

Changes:

* Added function to check for latest version on package load


TwoSampleMR v0.3.1 (Release date: 2017-11-22)
==============

Changes:

* One of the external packages that TwoSampleMR depends upon had changed, making the authorisation behaviour change. The authorisation was timing out after an hour and it was not refreshing after its timeout. This has now been fixed - the authorisation token will refresh after an hour.

* The authorisation token used to be stored in a hidden file called .httr-oauth. This has now been changed - it will be stored in a visible file called 'mrbase.oauth'.
