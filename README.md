# antsxReproducibility

log reproducibility results

```R
myta=c("vol_mtg_sn_snc_leftsnseg"    ,    "vol_mtg_sn_snc_rightsnseg" )
myta="vol_mtg_sn_snr_leftdeep_cit168"
myta="vol_mtg_sn_snc_leftcit168"
#
myta=c(
      "vol_mtg_sn_snr_leftdeep_cit168","vol_mtg_sn_snr_rightdeep_cit168",
      "vol_mtg_sn_snc_leftdeep_cit168","vol_mtg_sn_snc_rightdeep_cit168")
myta=c( "vol_nbm_right_midbf", "vol_nbm_left_midbf",  "vol_nbm_right_antbf",
              "vol_nbm_left_antbf",  "vol_nbm_right_posbf", "vol_nbm_left_posbf" )
#
myta=c(
    "vol_mtg_sn_snr_leftsnseg","vol_mtg_sn_snr_rightsnseg",
    "vol_mtg_sn_snc_leftsnseg","vol_mtg_sn_snc_rightsnseg")

myta0=c("vol_mtg_sn_snc_leftsnseg")
myta1=c("vol_mtg_sn_snc_rightsnseg")

mytalist = list( myta0, myta1 )
for ( vv in c(1) ) {
  for ( rez in c("OR","SR"))
  for ( ta in 1:length(mytalist) ) {
    tarAnat=mytalist[[ta]]
    anatcsv=paste0("_v",vv,rez,"_mergewide.csv")
    anfn=paste0(tarAnat,collapse='-')
    outfn=paste0("/tmp/antspyT1wreproV",vv,rez,"_",anfn,".html")
    print(outfn)
    rmarkdown::render( "src/antspyT1wrepro.Rmd", output_file=outfn )
    system( paste("open",outfn ))
    }
  }
```
