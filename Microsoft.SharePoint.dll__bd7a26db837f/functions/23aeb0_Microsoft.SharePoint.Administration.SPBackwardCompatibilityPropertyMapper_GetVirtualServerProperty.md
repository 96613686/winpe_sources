# Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::GetVirtualServerProperty

- ea: `0x23aeb0`
- end: `0x23b7a4`
- name: `Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::GetVirtualServerProperty`
- size: `2292`
- prototype: ``
- caller_count: `1`
- callee_count: `62`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x239620`

## callees

- `0x1c8720`
- `0x223b60`
- `0x2243d0`
- `0x23aeb0`
- `0x23c170`
- `0x23c1e0`
- `0x23c250`
- `0x23c270`
- `0x23ca60`
- `0x23cac0`
- `0x23cb00`
- `0x23ea20`
- `0x23ea40`
- `0x23eac0`
- `0x295fd0`
- `0x295ff0`
- `0x296010`
- `0x296030`
- `0x296070`
- `0x2d23a0`
- `0x2d23c0`
- `0x2d23e0`
- `0x2d2400`
- `0x2d2460`
- `0x31d5d0`
- `0x31d7f0`
- `0x31de10`
- `0x31de60`
- `0x31ded0`
- `0x31df10`
- `0x31df50`
- `0x31df90`
- `0x31e030`
- `0x31e510`
- `0x31e550`
- `0x31e570`
- `0x31e590`
- `0x31e5f0`
- `0x31e630`
- `0x31e670`
- `0x31e6f0`
- `0x31e830`
- `0x31e8b0`
- `0x31e8f0`
- `0x31e930`
- `0x31e970`
- `0x31ea60`
- `0x31ea70`
- `0x31ebd0`
- `0x31ec30`

## string_xrefs

- `0x23af51`: `data-retrieval-services-enabled`
- `0x23af6b`: `data-retrieval-services-oledb-providers`
- `0x23af78`: `data-retrieval-services-response-size`
- `0x23af85`: `data-retrieval-services-timeout`
- `0x23af92`: `data-retrieval-services-update`
- `0x23af5e`: `data-retrieval-services-inherit`
- `0x23afac`: `dead-site-auto-delete`
- `0x23afe0`: `defaultquotatemplate`
- `0x23afed`: `delete-web-send-email`
- `0x23b02e`: `job-dead-site-delete`
- `0x23b0d7`: `securityvalidation-enabled`
- `0x23b0e4`: `securityvalidation-expire`
- `0x23b0f1`: `securityvalidation-timeout`
- `0x23b1a7`: `clientcallablesettings-maxobjectpaths`

## pseudocode

```c

```

## disassembly

```asm
0x23aeb0  ldarg.1
0x23aeb1  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x23aeb6  stloc.0
0x23aeb7  ldnull
0x23aeb8  stloc.1
0x23aeb9  ldnull
0x23aeba  stloc.2
0x23aebb  ldloc.0
0x23aebc  dup
0x23aebd  stloc.s  5
0x23aebf  brfalse  loc_23B790
0x23aec4  volatile.
0x23aec6  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{7F5A19CB-910C-4E1B-81E8-035FE0963D88}::$$method0x6004a5f-1
0x23aecb  brtrue   loc_23B1C7
0x23aed0  ldc.i4.s 0x3A
0x23aed2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x23aed7  dup
0x23aed8  ldstr    aAlertsEnabled// "alerts-enabled"
0x23aedd  ldc.i4.0
0x23aede  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23aee3  dup
0x23aee4  ldstr    aAlertsLimited// "alerts-limited"
0x23aee9  ldc.i4.1
0x23aeea  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23aeef  dup
0x23aef0  ldstr    aAlertsMaximum// "alerts-maximum"
0x23aef5  ldc.i4.2
0x23aef6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23aefb  dup
0x23aefc  ldstr    aAlertsMaximumQ// "alerts-maximum-query-set"
0x23af01  ldc.i4.3
0x23af02  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23af07  dup
0x23af08  ldstr    aAlertsFlags// "alerts-flags"
0x23af0d  ldc.i4.4
0x23af0e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23af13  dup
0x23af14  ldstr    aAlertsEventBat// "alerts-event-batch-size"
0x23af19  ldc.i4.5
0x23af1a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23af1f  dup
0x23af20  ldstr    aChangeLogExpir// "change-log-expiration-enabled"
0x23af25  ldc.i4.6
0x23af26  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23af2b  dup
0x23af2c  ldstr    aChangeLogReten// "change-log-retention-period"
0x23af31  ldc.i4.7
0x23af32  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23af37  dup
0x23af38  ldstr    aEventLogRetent// "event-log-retention-period"
0x23af3d  ldc.i4.8
0x23af3e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23af43  dup
0x23af44  ldstr    aEventhandlerse// "eventhandlersenabled"
0x23af49  ldc.i4.s 9
0x23af4b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23af50  dup
0x23af51  ldstr    aDataRetrievalS// "data-retrieval-services-enabled"
0x23af56  ldc.i4.s 0xA
0x23af58  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23af5d  dup
0x23af5e  ldstr    aDataRetrievalS_4// "data-retrieval-services-inherit"
0x23af63  ldc.i4.s 0xB
0x23af65  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23af6a  dup
0x23af6b  ldstr    aDataRetrievalS_0// "data-retrieval-services-oledb-providers"
0x23af70  ldc.i4.s 0xC
0x23af72  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23af77  dup
0x23af78  ldstr    aDataRetrievalS_1// "data-retrieval-services-response-size"
0x23af7d  ldc.i4.s 0xD
0x23af7f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23af84  dup
0x23af85  ldstr    aDataRetrievalS_2// "data-retrieval-services-timeout"
0x23af8a  ldc.i4.s 0xE
0x23af8c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23af91  dup
0x23af92  ldstr    aDataRetrievalS_3// "data-retrieval-services-update"
0x23af97  ldc.i4.s 0xF
0x23af99  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23af9e  dup
0x23af9f  ldstr    aDaysToShowNewI// "days-to-show-new-icon"
0x23afa4  ldc.i4.s 0x10
0x23afa6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23afab  dup
0x23afac  ldstr    aDeadSiteAutoDe// "dead-site-auto-delete"
0x23afb1  ldc.i4.s 0x11
0x23afb3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23afb8  dup
0x23afb9  ldstr    aDeadSiteNotify// "dead-site-notify-after"
0x23afbe  ldc.i4.s 0x12
0x23afc0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23afc5  dup
0x23afc6  ldstr    aDeadSiteNumNot// "dead-site-num-notifications"
0x23afcb  ldc.i4.s 0x13
0x23afcd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23afd2  dup
0x23afd3  ldstr    aDefaulttimezon// "defaulttimezone"
0x23afd8  ldc.i4.s 0x14
0x23afda  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23afdf  dup
0x23afe0  ldstr    aDefaultquotate// "defaultquotatemplate"
0x23afe5  ldc.i4.s 0x15
0x23afe7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23afec  dup
0x23afed  ldstr    aDeleteWebSendE// "delete-web-send-email"
0x23aff2  ldc.i4.s 0x16
0x23aff4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23aff9  dup
0x23affa  ldstr    aDisablecoautho// "disablecoauthoring"
0x23afff  ldc.i4.s 0x17
0x23b001  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b006  dup
0x23b007  ldstr    aForceseekenabl// "forceseekenabled"
0x23b00c  ldc.i4.s 0x18
0x23b00e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b013  dup
0x23b014  ldstr    aJobImmediateAl// "job-immediate-alerts"
0x23b019  ldc.i4.s 0x19
0x23b01b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b020  dup
0x23b021  ldstr    aJobUsageAnalys// "job-usage-analysis"
0x23b026  ldc.i4.s 0x1A
0x23b028  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b02d  dup
0x23b02e  ldstr    aJobDeadSiteDel// "job-dead-site-delete"
0x23b033  ldc.i4.s 0x1B
0x23b035  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b03a  dup
0x23b03b  ldstr    aJobDiskquotaWa// "job-diskquota-warning"
0x23b040  ldc.i4.s 0x1C
0x23b042  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b047  dup
0x23b048  ldstr    aMaxFilePostSiz// "max-file-post-size"
0x23b04d  ldc.i4.s 0x1D
0x23b04f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b054  dup
0x23b055  ldstr    aPeoplepickerSe// "peoplepicker-searchadcustomfilter"
0x23b05a  ldc.i4.s 0x1E
0x23b05c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b061  dup
0x23b062  ldstr    aPeoplepickerSe_0// "peoplepicker-searchadcustomquery"
0x23b067  ldc.i4.s 0x1F
0x23b069  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b06e  dup
0x23b06f  ldstr    aPeoplepickerOn// "peoplepicker-onlysearchwithinsitecollec"...
0x23b074  ldc.i4.s 0x20
0x23b076  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b07b  dup
0x23b07c  ldstr    aPeoplepickerPe// "peoplepicker-peopleeditoronlyresolvewit"...
0x23b081  ldc.i4.s 0x21
0x23b083  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b088  dup
0x23b089  ldstr    aPeoplepickerNo// "peoplepicker-nowindowsaccountsfornonwin"...
0x23b08e  ldc.i4.s 0x22
0x23b090  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b095  dup
0x23b096  ldstr    aPresenceenable// "presenceenabled"
0x23b09b  ldc.i4.s 0x23
0x23b09d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b0a2  dup
0x23b0a3  ldstr    aRecycleBinClea// "recycle-bin-cleanup-enabled"
0x23b0a8  ldc.i4.s 0x24
0x23b0aa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b0af  dup
0x23b0b0  ldstr    aRecycleBinEnab// "recycle-bin-enabled"
0x23b0b5  ldc.i4.s 0x25
0x23b0b7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b0bc  dup
0x23b0bd  ldstr    aRecycleBinRete// "recycle-bin-retention-period"
0x23b0c2  ldc.i4.s 0x26
0x23b0c4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b0c9  dup
0x23b0ca  ldstr    aSecondStageRec// "second-stage-recycle-bin-quota"
0x23b0cf  ldc.i4.s 0x27
0x23b0d1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b0d6  dup
0x23b0d7  ldstr    aSecurityvalida// "securityvalidation-enabled"
0x23b0dc  ldc.i4.s 0x28
0x23b0de  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b0e3  dup
0x23b0e4  ldstr    aSecurityvalida_0// "securityvalidation-expire"
0x23b0e9  ldc.i4.s 0x29
0x23b0eb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b0f0  dup
0x23b0f1  ldstr    aSecurityvalida_1// "securityvalidation-timeout"
0x23b0f6  ldc.i4.s 0x2A
0x23b0f8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b0fd  dup
0x23b0fe  ldstr    aSendAdEmail// "send-ad-email"
0x23b103  ldc.i4.s 0x2B
0x23b105  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b10a  dup
0x23b10b  ldstr    aSpallowglobalc// "spallowglobalcatalog"
0x23b110  ldc.i4.s 0x2C
0x23b112  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b117  dup
0x23b118  ldstr    aSpallowp2p// "spallowp2p"
0x23b11d  ldc.i4.s 0x2D
0x23b11f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b124  dup
0x23b125  ldstr    aSsc// "ssc"
0x23b12a  ldc.i4.s 0x2E
0x23b12c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b131  dup
0x23b132  ldstr    aSscContact// "ssc-contact"
0x23b137  ldc.i4.s 0x2F
0x23b139  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b13e  dup
0x23b13f  ldstr    aStorageMetrics// "storage-metrics-processing-duration"
0x23b144  ldc.i4.s 0x30
0x23b146  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b14b  dup
0x23b14c  ldstr    aDefaultzoneout// "defaultzoneoutgoingurl"
0x23b151  ldc.i4.s 0x31
0x23b153  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b158  dup
0x23b159  ldstr    aCustomzoneoutg// "customzoneoutgoingurl"
0x23b15e  ldc.i4.s 0x32
0x23b160  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b165  dup
0x23b166  ldstr    aExtranetzoneou// "extranetzoneoutgoingurl"
0x23b16b  ldc.i4.s 0x33
0x23b16d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b172  dup
0x23b173  ldstr    aIntranetzoneou// "intranetzoneoutgoingurl"
0x23b178  ldc.i4.s 0x34
0x23b17a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b17f  dup
0x23b180  ldstr    aInternetzoneou// "internetzoneoutgoingurl"
0x23b185  ldc.i4.s 0x35
0x23b187  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b18c  dup
0x23b18d  ldstr    aQueryMaximumre// "query-maximumresult"
0x23b192  ldc.i4.s 0x36
0x23b194  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b199  dup
0x23b19a  ldstr    aClientcallable// "clientcallablesettings-maxresourceperre"...
0x23b19f  ldc.i4.s 0x37
0x23b1a1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b1a6  dup
0x23b1a7  ldstr    aClientcallable_0// "clientcallablesettings-maxobjectpaths"
0x23b1ac  ldc.i4.s 0x38
0x23b1ae  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b1b3  dup
0x23b1b4  ldstr    aClientcallable_1// "clientcallablesettings-enablestacktrace"
0x23b1b9  ldc.i4.s 0x39
0x23b1bb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x23b1c0  volatile.
0x23b1c2  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{7F5A19CB-910C-4E1B-81E8-035FE0963D88}::$$method0x6004a5f-1
0x23b1c7  volatile.
0x23b1c9  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{7F5A19CB-910C-4E1B-81E8-035FE0963D88}::$$method0x6004a5f-1
0x23b1ce  ldloc.s  5
0x23b1d0  ldloca.s 6
0x23b1d2  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x23b1d7  brfalse  loc_23B790
0x23b1dc  ldloc.s  6
0x23b1de  switch   loc_23B2D0, loc_23B2E1, loc_23B2F2, loc_23B303, loc_23B314, loc_23B325, loc_23B336, loc_23B347, loc_23B361, loc_23B37B, loc_23B38C, loc_23B3A2, loc_23B3B3, loc_23B40B, loc_23B421, loc_23B437, loc_23B44D, loc_23B45E, loc_23B46F, loc_23B48A, loc_23B49B, loc_23B4AC, loc_23B4B8, loc_23B4C9, loc_23B4DA, loc_23B4EB, loc_23B4FD, loc_23B50F, loc_23B521, loc_23B533, loc_23B544, loc_23B555, loc_23B566, loc_23B57C, loc_23B592, loc_23B5A8, loc_23B5B9, loc_23B5CA, loc_23B5DB, loc_23B5EC, loc_23B5FD, loc_23B613, loc_23B629, loc_23B649, loc_23B65A, loc_23B66B, loc_23B67C, loc_23B68D, loc_23B69E, loc_23B6AF, loc_23B6CF, loc_23B6EF, loc_23B70F \
0x23b2cb  br       loc_23B790
0x23b2d0  ldarg.0
0x23b2d1  callvirt instance bool Microsoft.SharePoint.Administration.SPWebApplication::get_AlertsEnabled()
0x23b2d6  call     string Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::btoa(bool value)
0x23b2db  stloc.1
0x23b2dc  br       loc_23B7A2
0x23b2e1  ldarg.0
0x23b2e2  callvirt instance bool Microsoft.SharePoint.Administration.SPWebApplication::get_AlertsLimited()
0x23b2e7  call     string Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::btoa(bool value)
0x23b2ec  stloc.1
0x23b2ed  br       loc_23B7A2
0x23b2f2  ldarg.0
0x23b2f3  callvirt instance int32 Microsoft.SharePoint.Administration.SPWebApplication::get_AlertsMaximum()
0x23b2f8  call     string Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::itoa(int32 value)
0x23b2fd  stloc.1
0x23b2fe  br       loc_23B7A2
0x23b303  ldarg.0
0x23b304  callvirt instance int32 Microsoft.SharePoint.Administration.SPWebApplication::get_AlertsMaximumQuerySet()
0x23b309  call     string Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::itoa(int32 value)
0x23b30e  stloc.1
0x23b30f  br       loc_23B7A2
0x23b314  ldarg.0
0x23b315  callvirt instance unsigned int32 Microsoft.SharePoint.Administration.SPWebApplication::get_AlertFlags()
0x23b31a  call     string Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::ltoa(unsigned int32 value)
0x23b31f  stloc.1
0x23b320  br       loc_23B7A2
0x23b325  ldarg.0
0x23b326  callvirt instance int32 Microsoft.SharePoint.Administration.SPWebApplication::get_AlertsEventBatchSize()
0x23b32b  call     string Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::itoa(int32 value)
0x23b330  stloc.1
0x23b331  br       loc_23B7A2
0x23b336  ldarg.0
0x23b337  callvirt instance bool Microsoft.SharePoint.Administration.SPWebApplication::get_ChangeLogExpirationEnabled()
0x23b33c  call     string Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::btoa(bool value)
0x23b341  stloc.1
0x23b342  br       loc_23B7A2
0x23b347  ldarg.0
0x23b348  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.SharePoint.Administration.SPWebApplication::get_ChangeLogRetentionPeriod()
0x23b34d  stloc.s  7
0x23b34f  ldloca.s 7
0x23b351  call     instance int32 [mscorlib]System.TimeSpan::get_Days()
0x23b356  call     string Microsoft.SharePoint.Administration.SPBackwardCompatibilityPropertyMapper::itoa(int32 value)
  ... truncated ...
```
