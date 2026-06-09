# Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::SetVirtualServerProperty

- ea: `0x23b7b0`
- end: `0x23c169`
- name: `Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::SetVirtualServerProperty`
- size: `2489`
- prototype: ``
- caller_count: `1`
- callee_count: `71`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x239720`

## callees

- `0x1c8720`
- `0x1c89b0`
- `0x1c8a20`
- `0x209050`
- `0x223bc0`
- `0x224400`
- `0x224460`
- `0x23b7b0`
- `0x23c1b0`
- `0x23c1f0`
- `0x23c260`
- `0x23c280`
- `0x23ca70`
- `0x23cad0`
- `0x23cb10`
- `0x23ea30`
- `0x23ea50`
- `0x23ead0`
- `0x295fe0`
- `0x296000`
- `0x296020`
- `0x296040`
- `0x296070`
- `0x2d23b0`
- `0x2d23d0`
- `0x2d23f0`
- `0x2d2410`
- `0x2d2470`
- `0x31d5d0`
- `0x31d800`
- `0x31de20`
- `0x31de70`
- `0x31dee0`
- `0x31df20`
- `0x31df60`
- `0x31dfa0`
- `0x31e040`
- `0x31e520`
- `0x31e560`
- `0x31e580`
- `0x31e5a0`
- `0x31e600`
- `0x31e640`
- `0x31e680`
- `0x31e700`
- `0x31e830`
- `0x31e8c0`
- `0x31e900`
- `0x31e940`
- `0x31e980`

## string_xrefs

- `0x23b854`: `data-retrieval-services-enabled`
- `0x23b86e`: `data-retrieval-services-oledb-providers`
- `0x23b87b`: `data-retrieval-services-response-size`
- `0x23b888`: `data-retrieval-services-timeout`
- `0x23b895`: `data-retrieval-services-update`
- `0x23b861`: `data-retrieval-services-inherit`
- `0x23b8af`: `dead-site-auto-delete`
- `0x23b8e3`: `defaultquotatemplate`
- `0x23b8f0`: `delete-web-send-email`
- `0x23b924`: `job-dead-site-delete`
- `0x23b9cd`: `securityvalidation-enabled`
- `0x23b9da`: `securityvalidation-expire`
- `0x23b9e7`: `securityvalidation-timeout`
- `0x23ba9d`: `clientcallablesettings-maxobjectpaths`
- `0x23c133`: `Setting backwards compatible virtual server property failed, vs: {0} key: {1} value: {2}. {3}`

## pseudocode

```c

```

## disassembly

```asm
0x23b7b0  ldarg.1
0x23b7b1  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x23b7b6  stloc.0
0x23b7b7  ldarg.0
0x23b7b8  callvirt instance class Microsoft.SharePoint.Administration.SPAlternateUrlCollection Microsoft.SharePoint.Administration.SPWebApplication::get_AlternateUrls()
0x23b7bd  stloc.1
0x23b7be  ldloc.0
0x23b7bf  dup
0x23b7c0  stloc.s  8
0x23b7c2  brfalse  loc_23C116
0x23b7c7  volatile.
0x23b7c9  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{7F5A19CB-910C-4E1B-81E8-035FE0963D88}::$$method0x6004a60-1
0x23b7ce  brtrue   loc_23BABD
0x23b7d3  ldc.i4.s 0x39
0x23b7d5  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x23b7da  dup
0x23b7db  ldstr    aAlertsEnabled// "alerts-enabled"
0x23b7e0  ldc.i4.0
0x23b7e1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b7e6  dup
0x23b7e7  ldstr    aAlertsLimited// "alerts-limited"
0x23b7ec  ldc.i4.1
0x23b7ed  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b7f2  dup
0x23b7f3  ldstr    aAlertsMaximum// "alerts-maximum"
0x23b7f8  ldc.i4.2
0x23b7f9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b7fe  dup
0x23b7ff  ldstr    aAlertsMaximumQ// "alerts-maximum-query-set"
0x23b804  ldc.i4.3
0x23b805  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b80a  dup
0x23b80b  ldstr    aAlertsFlags// "alerts-flags"
0x23b810  ldc.i4.4
0x23b811  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b816  dup
0x23b817  ldstr    aAlertsEventBat// "alerts-event-batch-size"
0x23b81c  ldc.i4.5
0x23b81d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b822  dup
0x23b823  ldstr    aEventhandlerse// "eventhandlersenabled"
0x23b828  ldc.i4.6
0x23b829  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b82e  dup
0x23b82f  ldstr    aChangeLogExpir// "change-log-expiration-enabled"
0x23b834  ldc.i4.7
0x23b835  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b83a  dup
0x23b83b  ldstr    aChangeLogReten// "change-log-retention-period"
0x23b840  ldc.i4.8
0x23b841  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b846  dup
0x23b847  ldstr    aEventLogRetent// "event-log-retention-period"
0x23b84c  ldc.i4.s 9
0x23b84e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b853  dup
0x23b854  ldstr    aDataRetrievalS// "data-retrieval-services-enabled"
0x23b859  ldc.i4.s 0xA
0x23b85b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b860  dup
0x23b861  ldstr    aDataRetrievalS_4// "data-retrieval-services-inherit"
0x23b866  ldc.i4.s 0xB
0x23b868  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b86d  dup
0x23b86e  ldstr    aDataRetrievalS_0// "data-retrieval-services-oledb-providers"
0x23b873  ldc.i4.s 0xC
0x23b875  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b87a  dup
0x23b87b  ldstr    aDataRetrievalS_1// "data-retrieval-services-response-size"
0x23b880  ldc.i4.s 0xD
0x23b882  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b887  dup
0x23b888  ldstr    aDataRetrievalS_2// "data-retrieval-services-timeout"
0x23b88d  ldc.i4.s 0xE
0x23b88f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b894  dup
0x23b895  ldstr    aDataRetrievalS_3// "data-retrieval-services-update"
0x23b89a  ldc.i4.s 0xF
0x23b89c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b8a1  dup
0x23b8a2  ldstr    aDaysToShowNewI// "days-to-show-new-icon"
0x23b8a7  ldc.i4.s 0x10
0x23b8a9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b8ae  dup
0x23b8af  ldstr    aDeadSiteAutoDe// "dead-site-auto-delete"
0x23b8b4  ldc.i4.s 0x11
0x23b8b6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b8bb  dup
0x23b8bc  ldstr    aDeadSiteNotify// "dead-site-notify-after"
0x23b8c1  ldc.i4.s 0x12
0x23b8c3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b8c8  dup
0x23b8c9  ldstr    aDeadSiteNumNot// "dead-site-num-notifications"
0x23b8ce  ldc.i4.s 0x13
0x23b8d0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b8d5  dup
0x23b8d6  ldstr    aDefaulttimezon// "defaulttimezone"
0x23b8db  ldc.i4.s 0x14
0x23b8dd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b8e2  dup
0x23b8e3  ldstr    aDefaultquotate// "defaultquotatemplate"
0x23b8e8  ldc.i4.s 0x15
0x23b8ea  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b8ef  dup
0x23b8f0  ldstr    aDeleteWebSendE// "delete-web-send-email"
0x23b8f5  ldc.i4.s 0x16
0x23b8f7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b8fc  dup
0x23b8fd  ldstr    aDisablecoautho// "disablecoauthoring"
0x23b902  ldc.i4.s 0x17
0x23b904  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b909  dup
0x23b90a  ldstr    aForceseekenabl// "forceseekenabled"
0x23b90f  ldc.i4.s 0x18
0x23b911  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b916  dup
0x23b917  ldstr    aJobImmediateAl// "job-immediate-alerts"
0x23b91c  ldc.i4.s 0x19
0x23b91e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b923  dup
0x23b924  ldstr    aJobDeadSiteDel// "job-dead-site-delete"
0x23b929  ldc.i4.s 0x1A
0x23b92b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b930  dup
0x23b931  ldstr    aJobDiskquotaWa// "job-diskquota-warning"
0x23b936  ldc.i4.s 0x1B
0x23b938  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b93d  dup
0x23b93e  ldstr    aMaxFilePostSiz// "max-file-post-size"
0x23b943  ldc.i4.s 0x1C
0x23b945  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b94a  dup
0x23b94b  ldstr    aPeoplepickerSe// "peoplepicker-searchadcustomfilter"
0x23b950  ldc.i4.s 0x1D
0x23b952  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b957  dup
0x23b958  ldstr    aPeoplepickerSe_0// "peoplepicker-searchadcustomquery"
0x23b95d  ldc.i4.s 0x1E
0x23b95f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b964  dup
0x23b965  ldstr    aPeoplepickerOn// "peoplepicker-onlysearchwithinsitecollec"...
0x23b96a  ldc.i4.s 0x1F
0x23b96c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b971  dup
0x23b972  ldstr    aPeoplepickerPe// "peoplepicker-peopleeditoronlyresolvewit"...
0x23b977  ldc.i4.s 0x20
0x23b979  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b97e  dup
0x23b97f  ldstr    aPeoplepickerNo// "peoplepicker-nowindowsaccountsfornonwin"...
0x23b984  ldc.i4.s 0x21
0x23b986  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b98b  dup
0x23b98c  ldstr    aPresenceenable// "presenceenabled"
0x23b991  ldc.i4.s 0x22
0x23b993  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b998  dup
0x23b999  ldstr    aRecycleBinClea// "recycle-bin-cleanup-enabled"
0x23b99e  ldc.i4.s 0x23
0x23b9a0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b9a5  dup
0x23b9a6  ldstr    aRecycleBinEnab// "recycle-bin-enabled"
0x23b9ab  ldc.i4.s 0x24
0x23b9ad  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b9b2  dup
0x23b9b3  ldstr    aRecycleBinRete// "recycle-bin-retention-period"
0x23b9b8  ldc.i4.s 0x25
0x23b9ba  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b9bf  dup
0x23b9c0  ldstr    aSecondStageRec// "second-stage-recycle-bin-quota"
0x23b9c5  ldc.i4.s 0x26
0x23b9c7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b9cc  dup
0x23b9cd  ldstr    aSecurityvalida// "securityvalidation-enabled"
0x23b9d2  ldc.i4.s 0x27
0x23b9d4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b9d9  dup
0x23b9da  ldstr    aSecurityvalida_0// "securityvalidation-expire"
0x23b9df  ldc.i4.s 0x28
0x23b9e1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b9e6  dup
0x23b9e7  ldstr    aSecurityvalida_1// "securityvalidation-timeout"
0x23b9ec  ldc.i4.s 0x29
0x23b9ee  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b9f3  dup
0x23b9f4  ldstr    aSendAdEmail// "send-ad-email"
0x23b9f9  ldc.i4.s 0x2A
0x23b9fb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23ba00  dup
0x23ba01  ldstr    aSpallowglobalc// "spallowglobalcatalog"
0x23ba06  ldc.i4.s 0x2B
0x23ba08  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23ba0d  dup
0x23ba0e  ldstr    aSpallowp2p// "spallowp2p"
0x23ba13  ldc.i4.s 0x2C
0x23ba15  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23ba1a  dup
0x23ba1b  ldstr    aSsc// "ssc"
0x23ba20  ldc.i4.s 0x2D
0x23ba22  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23ba27  dup
0x23ba28  ldstr    aSscContact// "ssc-contact"
0x23ba2d  ldc.i4.s 0x2E
0x23ba2f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23ba34  dup
0x23ba35  ldstr    aStorageMetrics// "storage-metrics-processing-duration"
0x23ba3a  ldc.i4.s 0x2F
0x23ba3c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23ba41  dup
0x23ba42  ldstr    aDefaultzoneout// "defaultzoneoutgoingurl"
0x23ba47  ldc.i4.s 0x30
0x23ba49  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23ba4e  dup
0x23ba4f  ldstr    aCustomzoneoutg// "customzoneoutgoingurl"
0x23ba54  ldc.i4.s 0x31
0x23ba56  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23ba5b  dup
0x23ba5c  ldstr    aExtranetzoneou// "extranetzoneoutgoingurl"
0x23ba61  ldc.i4.s 0x32
0x23ba63  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23ba68  dup
0x23ba69  ldstr    aIntranetzoneou// "intranetzoneoutgoingurl"
0x23ba6e  ldc.i4.s 0x33
0x23ba70  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23ba75  dup
0x23ba76  ldstr    aInternetzoneou// "internetzoneoutgoingurl"
0x23ba7b  ldc.i4.s 0x34
0x23ba7d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23ba82  dup
0x23ba83  ldstr    aQueryMaximumre// "query-maximumresult"
0x23ba88  ldc.i4.s 0x35
0x23ba8a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23ba8f  dup
0x23ba90  ldstr    aClientcallable// "clientcallablesettings-maxresourceperre"...
0x23ba95  ldc.i4.s 0x36
0x23ba97  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23ba9c  dup
0x23ba9d  ldstr    aClientcallable_0// "clientcallablesettings-maxobjectpaths"
0x23baa2  ldc.i4.s 0x37
0x23baa4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23baa9  dup
0x23baaa  ldstr    aClientcallable_1// "clientcallablesettings-enablestacktrace"
0x23baaf  ldc.i4.s 0x38
0x23bab1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23bab6  volatile.
0x23bab8  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{7F5A19CB-910C-4E1B-81E8-035FE0963D88}::$$method0x6004a60-1
0x23babd  volatile.
0x23babf  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{7F5A19CB-910C-4E1B-81E8-035FE0963D88}::$$method0x6004a60-1
0x23bac4  ldloc.s  8
0x23bac6  ldloca.s 9
0x23bac8  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x23bacd  brfalse  loc_23C116
0x23bad2  ldloc.s  9
0x23bad4  switch   loc_23BBC2, loc_23BBD3, loc_23BBE4, loc_23BBF5, loc_23BC06, loc_23BC17, loc_23BC28, loc_23BC39, loc_23BC4A, loc_23BC63, loc_23BC7C, loc_23BC92, loc_23BCA3, loc_23BCFA, loc_23BD10, loc_23BD26, loc_23BD3C, loc_23BD4D, loc_23BD5E, loc_23BD77, loc_23BD88, loc_23BD99, loc_23BDA5, loc_23BDB6, loc_23BDC7, loc_23BDD8, loc_23BE15, loc_23BE52, loc_23BE8F, loc_23BEA0, loc_23BEB1, loc_23BEC2, loc_23BED8, loc_23BEEE, loc_23BF04, loc_23BF15, loc_23BF26, loc_23BF37, loc_23BF48, loc_23BF59, loc_23BF6F, loc_23BF85, loc_23BFA2, loc_23BFB3, loc_23BFC4, loc_23BFD5, loc_23BFE6, loc_23BFF7, loc_23C008, loc_23C031, loc_23C05A, loc_23C083, loc_23C0A9 \
0x23bbbd  br       loc_23C116
0x23bbc2  ldarg.0
0x23bbc3  ldarg.2
0x23bbc4  call     bool Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::atob(string value)
0x23bbc9  callvirt instance void Microsoft.SharePoint.Administration.SPWebApplication::set_AlertsEnabled(bool value)
0x23bbce  br       loc_23C123
0x23bbd3  ldarg.0
0x23bbd4  ldarg.2
0x23bbd5  call     bool Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::atob(string value)
0x23bbda  callvirt instance void Microsoft.SharePoint.Administration.SPWebApplication::set_AlertsLimited(bool value)
0x23bbdf  br       loc_23C123
0x23bbe4  ldarg.0
0x23bbe5  ldarg.2
0x23bbe6  call     int32 Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::atoi(string value)
0x23bbeb  callvirt instance void Microsoft.SharePoint.Administration.SPWebApplication::set_AlertsMaximum(int32 value)
0x23bbf0  br       loc_23C123
0x23bbf5  ldarg.0
0x23bbf6  ldarg.2
0x23bbf7  call     int32 Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::atoi(string value)
0x23bbfc  callvirt instance void Microsoft.SharePoint.Administration.SPWebApplication::set_AlertsMaximumQuerySet(int32 value)
0x23bc01  br       loc_23C123
0x23bc06  ldarg.0
0x23bc07  ldarg.2
0x23bc08  call     unsigned int32 Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::atol(string value)
0x23bc0d  callvirt instance void Microsoft.SharePoint.Administration.SPWebApplication::set_AlertFlags(unsigned int32 value)
0x23bc12  br       loc_23C123
0x23bc17  ldarg.0
0x23bc18  ldarg.2
0x23bc19  call     int32 Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::atoi(string value)
0x23bc1e  callvirt instance void Microsoft.SharePoint.Administration.SPWebApplication::set_AlertsEventBatchSize(int32 value)
0x23bc23  br       loc_23C123
0x23bc28  ldarg.0
0x23bc29  ldarg.2
0x23bc2a  call     bool Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::atob(string value)
0x23bc2f  callvirt instance void Microsoft.SharePoint.Administration.SPWebApplication::set_EventHandlersEnabled(bool value)
0x23bc34  br       loc_23C123
0x23bc39  ldarg.0
0x23bc3a  ldarg.2
0x23bc3b  call     bool Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::atob(string value)
0x23bc40  callvirt instance void Microsoft.SharePoint.Administration.SPWebApplication::set_ChangeLogExpirationEnabled(bool value)
0x23bc45  br       loc_23C123
0x23bc4a  ldarg.0
0x23bc4b  ldarg.2
0x23bc4c  call     int32 Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::atoi(string value)
0x23bc51  ldc.i4.0
0x23bc52  ldc.i4.0
0x23bc53  ldc.i4.0
  ... truncated ...
```
