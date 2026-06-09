# Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::.cctor

- ea: `0x23c2c0`
- end: `0x23c6e8`
- name: `Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::.cctor`
- size: `1064`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x23c30a`: `avnumberofthreads`
- `0x23c337`: `avvendorupdatecount`
- `0x23c340`: `createadaccounts`
- `0x23c36d`: `data-retrieval-services-enabled`
- `0x23c514`: `data-retrieval-services-enabled`
- `0x23c376`: `data-retrieval-services-oledb-providers`
- `0x23c524`: `data-retrieval-services-oledb-providers`
- `0x23c37f`: `data-retrieval-services-response-size`
- `0x23c52c`: `data-retrieval-services-response-size`
- `0x23c388`: `data-retrieval-services-timeout`
- `0x23c534`: `data-retrieval-services-timeout`
- `0x23c391`: `data-retrieval-services-update`
- `0x23c53d`: `data-retrieval-services-update`
- `0x23c3ac`: `htmltranslbpath`
- `0x23c3b5`: `htmltransmaxcachesize`
- `0x23c445`: `token-timeout`
- `0x23c51c`: `data-retrieval-services-inherit`
- `0x23c54f`: `dead-site-auto-delete`
- `0x23c573`: `defaultquotatemplate`
- `0x23c57c`: `delete-web-send-email`
- `0x23c5a9`: `job-dead-site-delete`
- `0x23c61e`: `securityvalidation-enabled`
- `0x23c627`: `securityvalidation-expire`
- `0x23c630`: `securityvalidation-timeout`
- `0x23c6b7`: `clientcallablesettings-maxobjectpaths`

## pseudocode

```c

```

## disassembly

```asm
0x23c2c0  ldc.i4.s 0x3D
0x23c2c2  newarr   [mscorlib]System.String
0x23c2c7  stloc.0
0x23c2c8  ldloc.0
0x23c2c9  ldc.i4.0
0x23c2ca  ldstr    aAdaccountdomai// "adaccountdomain"
0x23c2cf  stelem.ref
0x23c2d0  ldloc.0
0x23c2d1  ldc.i4.1
0x23c2d2  ldstr    aAdaccountou// "adaccountou"
0x23c2d7  stelem.ref
0x23c2d8  ldloc.0
0x23c2d9  ldc.i4.2
0x23c2da  ldstr    aAdminport// "adminport"
0x23c2df  stelem.ref
0x23c2e0  ldloc.0
0x23c2e1  ldc.i4.3
0x23c2e2  ldstr    aAdminportident// "adminportidentity"
0x23c2e7  stelem.ref
0x23c2e8  ldloc.0
0x23c2e9  ldc.i4.4
0x23c2ea  ldstr    aAdminportusess// "adminportusesssl"
0x23c2ef  stelem.ref
0x23c2f0  ldloc.0
0x23c2f1  ldc.i4.5
0x23c2f2  ldstr    aAvallowdownloa// "avallowdownload"
0x23c2f7  stelem.ref
0x23c2f8  ldloc.0
0x23c2f9  ldc.i4.6
0x23c2fa  ldstr    aAvcleaningenab// "avcleaningenabled"
0x23c2ff  stelem.ref
0x23c300  ldloc.0
0x23c301  ldc.i4.7
0x23c302  ldstr    aAvdownloadscan// "avdownloadscanenabled"
0x23c307  stelem.ref
0x23c308  ldloc.0
0x23c309  ldc.i4.8
0x23c30a  ldstr    aAvnumberofthre// "avnumberofthreads"
0x23c30f  stelem.ref
0x23c310  ldloc.0
0x23c311  ldc.i4.s 9
0x23c313  ldstr    aAvskipsearchcr// "avskipsearchcrawl"
0x23c318  stelem.ref
0x23c319  ldloc.0
0x23c31a  ldc.i4.s 0xA
0x23c31c  ldstr    aAvtimeout// "avtimeout"
0x23c321  stelem.ref
0x23c322  ldloc.0
0x23c323  ldc.i4.s 0xB
0x23c325  ldstr    aAvuploadscanen// "avuploadscanenabled"
0x23c32a  stelem.ref
0x23c32b  ldloc.0
0x23c32c  ldc.i4.s 0xC
0x23c32e  ldstr    aAvvendorid// "avvendorid"
0x23c333  stelem.ref
0x23c334  ldloc.0
0x23c335  ldc.i4.s 0xD
0x23c337  ldstr    aAvvendorupdate// "avvendorupdatecount"
0x23c33c  stelem.ref
0x23c33d  ldloc.0
0x23c33e  ldc.i4.s 0xE
0x23c340  ldstr    aCreateadaccoun// "createadaccounts"
0x23c345  stelem.ref
0x23c346  ldloc.0
0x23c347  ldc.i4.s 0xF
0x23c349  ldstr    aCoauthoringmax// "coauthoringmaxauthors"
0x23c34e  stelem.ref
0x23c34f  ldloc.0
0x23c350  ldc.i4.s 0x10
0x23c352  ldstr    aCoauthoringver// "coauthoringversionperiod"
0x23c357  stelem.ref
0x23c358  ldloc.0
0x23c359  ldc.i4.s 0x11
0x23c35b  ldstr    aDeveloperDashb// "developer-dashboard"
0x23c360  stelem.ref
0x23c361  ldloc.0
0x23c362  ldc.i4.s 0x12
0x23c364  ldstr    aDisablecoautho// "disablecoauthoring"
0x23c369  stelem.ref
0x23c36a  ldloc.0
0x23c36b  ldc.i4.s 0x13
0x23c36d  ldstr    aDataRetrievalS// "data-retrieval-services-enabled"
0x23c372  stelem.ref
0x23c373  ldloc.0
0x23c374  ldc.i4.s 0x14
0x23c376  ldstr    aDataRetrievalS_0// "data-retrieval-services-oledb-providers"
0x23c37b  stelem.ref
0x23c37c  ldloc.0
0x23c37d  ldc.i4.s 0x15
0x23c37f  ldstr    aDataRetrievalS_1// "data-retrieval-services-response-size"
0x23c384  stelem.ref
0x23c385  ldloc.0
0x23c386  ldc.i4.s 0x16
0x23c388  ldstr    aDataRetrievalS_2// "data-retrieval-services-timeout"
0x23c38d  stelem.ref
0x23c38e  ldloc.0
0x23c38f  ldc.i4.s 0x17
0x23c391  ldstr    aDataRetrievalS_3// "data-retrieval-services-update"
0x23c396  stelem.ref
0x23c397  ldloc.0
0x23c398  ldc.i4.s 0x18
0x23c39a  ldstr    aFulltextsearch// "fulltextsearchenabled"
0x23c39f  stelem.ref
0x23c3a0  ldloc.0
0x23c3a1  ldc.i4.s 0x19
0x23c3a3  ldstr    aGlobaladmingro// "globaladmingroup"
0x23c3a8  stelem.ref
0x23c3a9  ldloc.0
0x23c3aa  ldc.i4.s 0x1A
0x23c3ac  ldstr    aHtmltranslbpat// "htmltranslbpath"
0x23c3b1  stelem.ref
0x23c3b2  ldloc.0
0x23c3b3  ldc.i4.s 0x1B
0x23c3b5  ldstr    aHtmltransmaxca// "htmltransmaxcachesize"
0x23c3ba  stelem.ref
0x23c3bb  ldloc.0
0x23c3bc  ldc.i4.s 0x1C
0x23c3be  ldstr    aHtmltransmaxsi// "htmltransmaxsize"
0x23c3c3  stelem.ref
0x23c3c4  ldloc.0
0x23c3c5  ldc.i4.s 0x1D
0x23c3c7  ldstr    aHtmltranson// "htmltranson"
0x23c3cc  stelem.ref
0x23c3cd  ldloc.0
0x23c3ce  ldc.i4.s 0x1E
0x23c3d0  ldstr    aHtmltranstimeo// "htmltranstimeout"
0x23c3d5  stelem.ref
0x23c3d6  ldloc.0
0x23c3d7  ldc.i4.s 0x1F
0x23c3d9  ldstr    aIrmrmsenabled// "irmrmsenabled"
0x23c3de  stelem.ref
0x23c3df  ldloc.0
0x23c3e0  ldc.i4.s 0x20
0x23c3e2  ldstr    aIrmaddinsenabl// "irmaddinsenabled"
0x23c3e7  stelem.ref
0x23c3e8  ldloc.0
0x23c3e9  ldc.i4.s 0x21
0x23c3eb  ldstr    aIrmrmsusead// "irmrmsusead"
0x23c3f0  stelem.ref
0x23c3f1  ldloc.0
0x23c3f2  ldc.i4.s 0x22
0x23c3f4  ldstr    aIrmrmscertserv// "irmrmscertserver"
0x23c3f9  stelem.ref
0x23c3fa  ldloc.0
0x23c3fb  ldc.i4.s 0x23
0x23c3fd  ldstr    aOldglobaladmin// "oldglobaladmingroup"
0x23c402  stelem.ref
0x23c403  ldloc.0
0x23c404  ldc.i4.s 0x24
0x23c406  ldstr    aSendAdEmail// "send-ad-email"
0x23c40b  stelem.ref
0x23c40c  ldloc.0
0x23c40d  ldc.i4.s 0x25
0x23c40f  ldstr    aSmtpServer// "smtp-server"
0x23c414  stelem.ref
0x23c415  ldloc.0
0x23c416  ldc.i4.s 0x26
0x23c418  ldstr    aTimerInitialSw// "timer-initial-sweep-interval"
0x23c41d  stelem.ref
0x23c41e  ldloc.0
0x23c41f  ldc.i4.s 0x27
0x23c421  ldstr    aTimerLockRefre// "timer-lock-refresh-interval"
0x23c426  stelem.ref
0x23c427  ldloc.0
0x23c428  ldc.i4.s 0x28
0x23c42a  ldstr    aTimerLockTimeo// "timer-lock-timeout"
0x23c42f  stelem.ref
0x23c430  ldloc.0
0x23c431  ldc.i4.s 0x29
0x23c433  ldstr    aTimerSweepInte// "timer-sweep-interval"
0x23c438  stelem.ref
0x23c439  ldloc.0
0x23c43a  ldc.i4.s 0x2A
0x23c43c  ldstr    aLargeFileChunk// "large-file-chunk-size"
0x23c441  stelem.ref
0x23c442  ldloc.0
0x23c443  ldc.i4.s 0x2B
0x23c445  ldstr    aTokenTimeout// "token-timeout"
0x23c44a  stelem.ref
0x23c44b  ldloc.0
0x23c44c  ldc.i4.s 0x2C
0x23c44e  ldstr    aDatabaseConnec// "database-connection-timeout"
0x23c453  stelem.ref
0x23c454  ldloc.0
0x23c455  ldc.i4.s 0x2D
0x23c457  ldstr    aWorkflowCpuThr// "workflow-cpu-throttle"
0x23c45c  stelem.ref
0x23c45d  ldloc.0
0x23c45e  ldc.i4.s 0x2E
0x23c460  ldstr    aWorkflowTimerj// "workflow-timerjob-cpu-throttle"
0x23c465  stelem.ref
0x23c466  ldloc.0
0x23c467  ldc.i4.s 0x2F
0x23c469  ldstr    aWorkflowEventd// "workflow-eventdelivery-batchsize"
0x23c46e  stelem.ref
0x23c46f  ldloc.0
0x23c470  ldc.i4.s 0x30
0x23c472  ldstr    aWorkflowEventd_0// "workflow-eventdelivery-throttle"
0x23c477  stelem.ref
0x23c478  ldloc.0
0x23c479  ldc.i4.s 0x31
0x23c47b  ldstr    aWorkflowEventd_1// "workflow-eventdelivery-timeout"
0x23c480  stelem.ref
0x23c481  ldloc.0
0x23c482  ldc.i4.s 0x32
0x23c484  ldstr    aWorkitemEventd// "workitem-eventdelivery-batchsize"
0x23c489  stelem.ref
0x23c48a  ldloc.0
0x23c48b  ldc.i4.s 0x33
0x23c48d  ldstr    aWorkitemEventd_0// "workitem-eventdelivery-throttle"
0x23c492  stelem.ref
0x23c493  ldloc.0
0x23c494  ldc.i4.s 0x34
0x23c496  ldstr    aDataSourceCont// "data-source-controls-enabled"
0x23c49b  stelem.ref
0x23c49c  ldloc.0
0x23c49d  ldc.i4.s 0x35
0x23c49f  ldstr    aVhresultenable// "vhresultenabled"
0x23c4a4  stelem.ref
0x23c4a5  ldloc.0
0x23c4a6  ldc.i4.s 0x36
0x23c4a8  ldstr    aRefcounttracki// "refcounttrackingenabled"
0x23c4ad  stelem.ref
0x23c4ae  ldloc.0
0x23c4af  ldc.i4.s 0x37
0x23c4b1  ldstr    aRefcountcallst// "refcountcallstacktrackingenabled"
0x23c4b6  stelem.ref
0x23c4b7  ldloc.0
0x23c4b8  ldc.i4.s 0x38
0x23c4ba  ldstr    aRefcounttracki_0// "refcounttrackingautoreleaseenabled"
0x23c4bf  stelem.ref
0x23c4c0  ldloc.0
0x23c4c1  ldc.i4.s 0x39
0x23c4c3  ldstr    aRefcounttracki_1// "refcounttrackingmaxcallstacks"
0x23c4c8  stelem.ref
0x23c4c9  ldloc.0
0x23c4ca  ldc.i4.s 0x3A
0x23c4cc  ldstr    aLockorderenabl// "lockorderenabled"
0x23c4d1  stelem.ref
0x23c4d2  ldloc.0
0x23c4d3  ldc.i4.s 0x3B
0x23c4d5  ldstr    aSqltraceenable// "sqltraceenabled"
0x23c4da  stelem.ref
0x23c4db  ldloc.0
0x23c4dc  ldc.i4.s 0x3C
0x23c4de  ldstr    aDeclarativewor// "declarativeworkflowautostartonemailenab"...
0x23c4e3  stelem.ref
0x23c4e4  ldloc.0
0x23c4e5  stsfld   string[] Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::s_ClusterProperties
0x23c4ea  ldc.i4.s 0x38
0x23c4ec  newarr   [mscorlib]System.String
0x23c4f1  stloc.1
0x23c4f2  ldloc.1
0x23c4f3  ldc.i4.0
0x23c4f4  ldstr    aAlertsEnabled// "alerts-enabled"
0x23c4f9  stelem.ref
0x23c4fa  ldloc.1
0x23c4fb  ldc.i4.1
0x23c4fc  ldstr    aAlertsLimited// "alerts-limited"
0x23c501  stelem.ref
0x23c502  ldloc.1
0x23c503  ldc.i4.2
0x23c504  ldstr    aAlertsMaximum// "alerts-maximum"
0x23c509  stelem.ref
0x23c50a  ldloc.1
0x23c50b  ldc.i4.3
0x23c50c  ldstr    aEventhandlerse// "eventhandlersenabled"
0x23c511  stelem.ref
0x23c512  ldloc.1
0x23c513  ldc.i4.4
0x23c514  ldstr    aDataRetrievalS// "data-retrieval-services-enabled"
0x23c519  stelem.ref
0x23c51a  ldloc.1
0x23c51b  ldc.i4.5
0x23c51c  ldstr    aDataRetrievalS_4// "data-retrieval-services-inherit"
0x23c521  stelem.ref
0x23c522  ldloc.1
0x23c523  ldc.i4.6
0x23c524  ldstr    aDataRetrievalS_0// "data-retrieval-services-oledb-providers"
0x23c529  stelem.ref
0x23c52a  ldloc.1
0x23c52b  ldc.i4.7
0x23c52c  ldstr    aDataRetrievalS_1// "data-retrieval-services-response-size"
0x23c531  stelem.ref
0x23c532  ldloc.1
0x23c533  ldc.i4.8
0x23c534  ldstr    aDataRetrievalS_2// "data-retrieval-services-timeout"
0x23c539  stelem.ref
0x23c53a  ldloc.1
0x23c53b  ldc.i4.s 9
0x23c53d  ldstr    aDataRetrievalS_3// "data-retrieval-services-update"
0x23c542  stelem.ref
0x23c543  ldloc.1
0x23c544  ldc.i4.s 0xA
0x23c546  ldstr    aDaysToShowNewI// "days-to-show-new-icon"
0x23c54b  stelem.ref
0x23c54c  ldloc.1
0x23c54d  ldc.i4.s 0xB
0x23c54f  ldstr    aDeadSiteAutoDe// "dead-site-auto-delete"
0x23c554  stelem.ref
  ... truncated ...
```
