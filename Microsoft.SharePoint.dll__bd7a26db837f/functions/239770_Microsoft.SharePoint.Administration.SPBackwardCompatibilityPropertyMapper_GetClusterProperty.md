# Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::GetClusterProperty

- ea: `0x239770`
- end: `0x23a221`
- name: `Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::GetClusterProperty`
- size: `2737`
- prototype: ``
- caller_count: `1`
- callee_count: `77`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x239570`

## callees

- `0x1c8720`
- `0x1c8850`
- `0x1c89e0`
- `0x2232b0`
- `0x227310`
- `0x22ccf0`
- `0x22cd70`
- `0x22cdb0`
- `0x22ceb0`
- `0x22cf00`
- `0x22cf70`
- `0x22cfa0`
- `0x22cfe0`
- `0x22d630`
- `0x239770`
- `0x23c1e0`
- `0x23c250`
- `0x23c290`
- `0x23c2b0`
- `0x28cf60`
- `0x28cf80`
- `0x28cfa0`
- `0x28f380`
- `0x295fd0`
- `0x295ff0`
- `0x296010`
- `0x296030`
- `0x296050`
- `0x296070`
- `0x29d1e0`
- `0x2c03d0`
- `0x2c03f0`
- `0x2c0410`
- `0x2c0430`
- `0x2c0450`
- `0x2c4360`
- `0x2c43a0`
- `0x2c43e0`
- `0x2c44e0`
- `0x2eb6c0`
- `0x31d4a0`
- `0x31e970`
- `0x31ea60`
- `0x31f2c0`
- `0x323760`
- `0x32bfe0`
- `0x32ccc0`
- `0x32cd30`
- `0x32cd70`
- `0x32ce10`

## string_xrefs

- `0x2397f4`: `avnumberofthreads`
- `0x239827`: `avvendorupdatecount`
- `0x239841`: `createadaccounts`
- `0x239868`: `data-retrieval-services-enabled`
- `0x239875`: `data-retrieval-services-oledb-providers`
- `0x239882`: `data-retrieval-services-response-size`
- `0x23988f`: `data-retrieval-services-timeout`
- `0x23989c`: `data-retrieval-services-update`
- `0x2398d0`: `htmltranslbpath`
- `0x2398dd`: `htmltransmaxcachesize`
- `0x2399a0`: `max-template-document-size`
- `0x2399ad`: `token-timeout`
- `0x239a22`: `database-command-timeout`
- `0x239db0`: `SPEED_data-retrieval-services-oledb-providers_TrimEmptyValues`

## pseudocode

```c

```

## disassembly

```asm
0x239770  ldarg.1
0x239771  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x239776  stloc.0
0x239777  ldloc.0
0x239778  dup
0x239779  stloc.s  5
0x23977b  brfalse  loc_23A208
0x239780  volatile.
0x239782  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{7F5A19CB-910C-4E1B-81E8-035FE0963D88}::$$method0x6004a5d-1
0x239787  brtrue   loc_239AAA
0x23978c  ldc.i4.s 0x3D
0x23978e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x239793  dup
0x239794  ldstr    aAdaccountdomai// "adaccountdomain"
0x239799  ldc.i4.0
0x23979a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23979f  dup
0x2397a0  ldstr    aAdaccountou// "adaccountou"
0x2397a5  ldc.i4.1
0x2397a6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2397ab  dup
0x2397ac  ldstr    aAdminport// "adminport"
0x2397b1  ldc.i4.2
0x2397b2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2397b7  dup
0x2397b8  ldstr    aAdminportident// "adminportidentity"
0x2397bd  ldc.i4.3
0x2397be  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2397c3  dup
0x2397c4  ldstr    aAdminportusess// "adminportusesssl"
0x2397c9  ldc.i4.4
0x2397ca  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2397cf  dup
0x2397d0  ldstr    aAvallowdownloa// "avallowdownload"
0x2397d5  ldc.i4.5
0x2397d6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2397db  dup
0x2397dc  ldstr    aAvcleaningenab// "avcleaningenabled"
0x2397e1  ldc.i4.6
0x2397e2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2397e7  dup
0x2397e8  ldstr    aAvdownloadscan// "avdownloadscanenabled"
0x2397ed  ldc.i4.7
0x2397ee  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2397f3  dup
0x2397f4  ldstr    aAvnumberofthre// "avnumberofthreads"
0x2397f9  ldc.i4.8
0x2397fa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2397ff  dup
0x239800  ldstr    aAvtimeout// "avtimeout"
0x239805  ldc.i4.s 9
0x239807  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23980c  dup
0x23980d  ldstr    aAvuploadscanen// "avuploadscanenabled"
0x239812  ldc.i4.s 0xA
0x239814  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x239819  dup
0x23981a  ldstr    aAvvendorid// "avvendorid"
0x23981f  ldc.i4.s 0xB
0x239821  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x239826  dup
0x239827  ldstr    aAvvendorupdate// "avvendorupdatecount"
0x23982c  ldc.i4.s 0xC
0x23982e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x239833  dup
0x239834  ldstr    aAvskipsearchcr// "avskipsearchcrawl"
0x239839  ldc.i4.s 0xD
0x23983b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x239840  dup
0x239841  ldstr    aCreateadaccoun// "createadaccounts"
0x239846  ldc.i4.s 0xE
0x239848  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23984d  dup
0x23984e  ldstr    aCoauthoringmax// "coauthoringmaxauthors"
0x239853  ldc.i4.s 0xF
0x239855  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23985a  dup
0x23985b  ldstr    aCoauthoringver// "coauthoringversionperiod"
0x239860  ldc.i4.s 0x10
0x239862  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x239867  dup
0x239868  ldstr    aDataRetrievalS// "data-retrieval-services-enabled"
0x23986d  ldc.i4.s 0x11
0x23986f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x239874  dup
0x239875  ldstr    aDataRetrievalS_0// "data-retrieval-services-oledb-providers"
0x23987a  ldc.i4.s 0x12
0x23987c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x239881  dup
0x239882  ldstr    aDataRetrievalS_1// "data-retrieval-services-response-size"
0x239887  ldc.i4.s 0x13
0x239889  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23988e  dup
0x23988f  ldstr    aDataRetrievalS_2// "data-retrieval-services-timeout"
0x239894  ldc.i4.s 0x14
0x239896  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23989b  dup
0x23989c  ldstr    aDataRetrievalS_3// "data-retrieval-services-update"
0x2398a1  ldc.i4.s 0x15
0x2398a3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2398a8  dup
0x2398a9  ldstr    aDeveloperDashb// "developer-dashboard"
0x2398ae  ldc.i4.s 0x16
0x2398b0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2398b5  dup
0x2398b6  ldstr    aDisablecoautho// "disablecoauthoring"
0x2398bb  ldc.i4.s 0x17
0x2398bd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2398c2  dup
0x2398c3  ldstr    aFulltextsearch// "fulltextsearchenabled"
0x2398c8  ldc.i4.s 0x18
0x2398ca  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2398cf  dup
0x2398d0  ldstr    aHtmltranslbpat// "htmltranslbpath"
0x2398d5  ldc.i4.s 0x19
0x2398d7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2398dc  dup
0x2398dd  ldstr    aHtmltransmaxca// "htmltransmaxcachesize"
0x2398e2  ldc.i4.s 0x1A
0x2398e4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2398e9  dup
0x2398ea  ldstr    aHtmltransmaxsi// "htmltransmaxsize"
0x2398ef  ldc.i4.s 0x1B
0x2398f1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2398f6  dup
0x2398f7  ldstr    aHtmltranson// "htmltranson"
0x2398fc  ldc.i4.s 0x1C
0x2398fe  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x239903  dup
0x239904  ldstr    aHtmltranstimeo// "htmltranstimeout"
0x239909  ldc.i4.s 0x1D
0x23990b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x239910  dup
0x239911  ldstr    aIrmrmsenabled// "irmrmsenabled"
0x239916  ldc.i4.s 0x1E
0x239918  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23991d  dup
0x23991e  ldstr    aIrmaddinsenabl// "irmaddinsenabled"
0x239923  ldc.i4.s 0x1F
0x239925  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23992a  dup
0x23992b  ldstr    aIrmrmsusead// "irmrmsusead"
0x239930  ldc.i4.s 0x20
0x239932  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x239937  dup
0x239938  ldstr    aIrmrmscertserv// "irmrmscertserver"
0x23993d  ldc.i4.s 0x21
0x23993f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x239944  dup
0x239945  ldstr    aSendAdEmail// "send-ad-email"
0x23994a  ldc.i4.s 0x22
0x23994c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x239951  dup
0x239952  ldstr    aSmtpServer// "smtp-server"
0x239957  ldc.i4.s 0x23
0x239959  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23995e  dup
0x23995f  ldstr    aTimerInitialSw// "timer-initial-sweep-interval"
0x239964  ldc.i4.s 0x24
0x239966  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23996b  dup
0x23996c  ldstr    aTimerLockRefre// "timer-lock-refresh-interval"
0x239971  ldc.i4.s 0x25
0x239973  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x239978  dup
0x239979  ldstr    aTimerLockTimeo// "timer-lock-timeout"
0x23997e  ldc.i4.s 0x26
0x239980  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x239985  dup
0x239986  ldstr    aTimerSweepInte// "timer-sweep-interval"
0x23998b  ldc.i4.s 0x27
0x23998d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x239992  dup
0x239993  ldstr    aLargeFileChunk// "large-file-chunk-size"
0x239998  ldc.i4.s 0x28
0x23999a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23999f  dup
0x2399a0  ldstr    aMaxTemplateDoc// "max-template-document-size"
0x2399a5  ldc.i4.s 0x29
0x2399a7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2399ac  dup
0x2399ad  ldstr    aTokenTimeout// "token-timeout"
0x2399b2  ldc.i4.s 0x2A
0x2399b4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2399b9  dup
0x2399ba  ldstr    aDatabaseConnec// "database-connection-timeout"
0x2399bf  ldc.i4.s 0x2B
0x2399c1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2399c6  dup
0x2399c7  ldstr    aWorkflowCpuThr// "workflow-cpu-throttle"
0x2399cc  ldc.i4.s 0x2C
0x2399ce  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2399d3  dup
0x2399d4  ldstr    aWorkflowTimerj// "workflow-timerjob-cpu-throttle"
0x2399d9  ldc.i4.s 0x2D
0x2399db  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2399e0  dup
0x2399e1  ldstr    aWorkflowEventd// "workflow-eventdelivery-batchsize"
0x2399e6  ldc.i4.s 0x2E
0x2399e8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2399ed  dup
0x2399ee  ldstr    aWorkflowEventd_0// "workflow-eventdelivery-throttle"
0x2399f3  ldc.i4.s 0x2F
0x2399f5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2399fa  dup
0x2399fb  ldstr    aWorkflowEventd_1// "workflow-eventdelivery-timeout"
0x239a00  ldc.i4.s 0x30
0x239a02  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x239a07  dup
0x239a08  ldstr    aWorkitemEventd// "workitem-eventdelivery-batchsize"
0x239a0d  ldc.i4.s 0x31
0x239a0f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x239a14  dup
0x239a15  ldstr    aWorkitemEventd_0// "workitem-eventdelivery-throttle"
0x239a1a  ldc.i4.s 0x32
0x239a1c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x239a21  dup
0x239a22  ldstr    aDatabaseComman// "database-command-timeout"
0x239a27  ldc.i4.s 0x33
0x239a29  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x239a2e  dup
0x239a2f  ldstr    aDataSourceCont// "data-source-controls-enabled"
0x239a34  ldc.i4.s 0x34
0x239a36  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x239a3b  dup
0x239a3c  ldstr    aVhresultenable// "vhresultenabled"
0x239a41  ldc.i4.s 0x35
0x239a43  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x239a48  dup
0x239a49  ldstr    aRefcounttracki// "refcounttrackingenabled"
0x239a4e  ldc.i4.s 0x36
0x239a50  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x239a55  dup
0x239a56  ldstr    aRefcountcallst// "refcountcallstacktrackingenabled"
0x239a5b  ldc.i4.s 0x37
0x239a5d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x239a62  dup
0x239a63  ldstr    aRefcounttracki_0// "refcounttrackingautoreleaseenabled"
0x239a68  ldc.i4.s 0x38
0x239a6a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x239a6f  dup
0x239a70  ldstr    aRefcounttracki_1// "refcounttrackingmaxcallstacks"
0x239a75  ldc.i4.s 0x39
0x239a77  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x239a7c  dup
0x239a7d  ldstr    aLockorderenabl// "lockorderenabled"
0x239a82  ldc.i4.s 0x3A
0x239a84  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x239a89  dup
0x239a8a  ldstr    aSqltraceenable// "sqltraceenabled"
0x239a8f  ldc.i4.s 0x3B
0x239a91  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x239a96  dup
0x239a97  ldstr    aDeclarativewor// "declarativeworkflowautostartonemailenab"...
0x239a9c  ldc.i4.s 0x3C
0x239a9e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x239aa3  volatile.
0x239aa5  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{7F5A19CB-910C-4E1B-81E8-035FE0963D88}::$$method0x6004a5d-1
0x239aaa  volatile.
0x239aac  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{7F5A19CB-910C-4E1B-81E8-035FE0963D88}::$$method0x6004a5d-1
0x239ab1  ldloc.s  5
0x239ab3  ldloca.s 6
0x239ab5  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x239aba  brfalse  loc_23A208
0x239abf  ldloc.s  6
0x239ac1  switch   loc_239BBF, loc_239BD0, loc_239BE1, loc_239BF8, loc_239C09, loc_239C2A, loc_239C45, loc_239C60, loc_239C7B, loc_239C96, loc_239CBB, loc_239CD6, loc_239CF1, loc_239D0C, loc_239D27, loc_239D3D, loc_239D53, loc_239D69, loc_239D7F, loc_239E0C, loc_239E22, loc_239E38, loc_239E4E, loc_239E6E, loc_239E84, loc_239E90, loc_239EA6, loc_239EC1, loc_239EDC, loc_239EF7, loc_239F1C, loc_239F37, loc_239F52, loc_239F6D, loc_239F83, loc_239F94, loc_239FBF, loc_239FD5, loc_239FEB, loc_23A001, loc_23A017, loc_23A02D, loc_23A043, loc_23A063, loc_23A083, loc_23A099, loc_23A0AF, loc_23A0C5, loc_23A0DB, loc_23A0FB, loc_23A111, loc_23A127, loc_23A147 \
0x239bba  br       loc_23A208
0x239bbf  ldarg.0
0x239bc0  call     class Microsoft.SharePoint.Administration.SPWebService Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::GetContentService(class Microsoft.SharePoint.Administration.SPPersistedObject obj)
0x239bc5  callvirt instance string Microsoft.SharePoint.Administration.SPWebService::get_ActiveDirectoryDomain()
0x239bca  stloc.1
0x239bcb  br       loc_23A21F
0x239bd0  ldarg.0
0x239bd1  call     class Microsoft.SharePoint.Administration.SPWebService Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::GetContentService(class Microsoft.SharePoint.Administration.SPPersistedObject obj)
0x239bd6  callvirt instance string Microsoft.SharePoint.Administration.SPWebService::get_ActiveDirectoryOrganizationalUnit()
0x239bdb  stloc.1
0x239bdc  br       loc_23A21F
0x239be1  ldarg.0
0x239be2  ldc.i4.0
0x239be3  callvirt instance class [System]System.Uri Microsoft.SharePoint.Administration.SPWebApplication::GetResponseUri(valuetype Microsoft.SharePoint.Administration.SPUrlZone zone)
0x239be8  callvirt instance int32 [System]System.Uri::get_Port()
0x239bed  call     string Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::itoa(int32 value)
0x239bf2  stloc.1
0x239bf3  br       loc_23A21F
0x239bf8  ldarg.0
0x239bf9  callvirt instance class Microsoft.SharePoint.Administration.SPApplicationPool Microsoft.SharePoint.Administration.SPWebApplication::get_ApplicationPool()
0x239bfe  callvirt instance string Microsoft.SharePoint.Administration.SPProcessIdentity::get_Username()
0x239c03  stloc.1
0x239c04  br       loc_23A21F
0x239c09  ldarg.0
0x239c0a  ldc.i4.0
0x239c0b  callvirt instance class [System]System.Uri Microsoft.SharePoint.Administration.SPWebApplication::GetResponseUri(valuetype Microsoft.SharePoint.Administration.SPUrlZone zone)
0x239c10  callvirt instance string [System]System.Uri::get_Scheme()
0x239c15  ldstr    aHttps_1// "https"
0x239c1a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x239c1f  call     string Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::btoa(bool value)
0x239c24  stloc.1
0x239c25  br       loc_23A21F
0x239c2a  ldarg.0
0x239c2b  call     class Microsoft.SharePoint.Administration.SPWebService Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::GetContentService(class Microsoft.SharePoint.Administration.SPPersistedObject obj)
  ... truncated ...
```
