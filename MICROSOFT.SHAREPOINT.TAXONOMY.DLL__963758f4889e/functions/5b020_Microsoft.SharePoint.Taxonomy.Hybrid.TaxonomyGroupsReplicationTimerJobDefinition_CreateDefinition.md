# Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyGroupsReplicationTimerJobDefinition::CreateDefinition

- ea: `0x5b020`
- end: `0x5b1b5`
- name: `Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyGroupsReplicationTimerJobDefinition::CreateDefinition`
- size: `405`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x242a0`
- `0x242d0`
- `0x59ea0`
- `0x5a020`
- `0x5a0f0`
- `0x5a200`
- `0x5ae70`
- `0x5afb0`
- `0x5b020`
- `0x5fd90`
- `0x60170`

## string_xrefs

- `0x5b0f4`: `remoteService`
- `0x5b0b1`: `onPremTermStoreName`

## pseudocode

```c

```

## disassembly

```asm
0x5b020  call     void Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyGroupsReplicationTimerJobDefinition::DeleteExistingJobDefinitions()
0x5b025  ldarg.0
0x5b026  ldstr    aRemotesiteurl// "remoteSiteUrl"
0x5b02b  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x5b030  ldarg.0
0x5b031  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x5b036  ldc.i4.5
0x5b037  rem
0x5b038  call     int32 [mscorlib]System.Math::Abs(int32)
0x5b03d  ldc.i4.1
0x5b03e  add.ovf
0x5b03f  stloc.0
0x5b040  ldc.i4   0x12103C1
0x5b045  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x5b04a  ldc.i4.s 0x32
0x5b04c  ldstr    aCalculatedHour// "Calculated hour bucket for remote site "...
0x5b051  ldc.i4.2
0x5b052  newarr   [mscorlib]System.Object
0x5b057  stloc.s  0xA
0x5b059  ldloc.s  0xA
0x5b05b  ldc.i4.0
0x5b05c  ldarg.0
0x5b05d  stelem.ref
0x5b05e  ldloc.s  0xA
0x5b060  ldc.i4.1
0x5b061  ldloc.0
0x5b062  box      [mscorlib]System.Int32
0x5b067  stelem.ref
0x5b068  ldloc.s  0xA
0x5b06a  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x5b06f  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPDailySchedule::.ctor()
0x5b074  stloc.1
0x5b075  ldloc.1
0x5b076  ldloc.0
0x5b077  ldc.i4.1
0x5b078  sub.ovf
0x5b079  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPDailySchedule::set_BeginHour(int32)
0x5b07e  ldloc.1
0x5b07f  ldc.i4.0
0x5b080  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPDailySchedule::set_BeginMinute(int32)
0x5b085  ldloc.1
0x5b086  ldc.i4.0
0x5b087  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPDailySchedule::set_BeginSecond(int32)
0x5b08c  ldloc.1
0x5b08d  ldloc.0
0x5b08e  ldc.i4.1
0x5b08f  add.ovf
0x5b090  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPDailySchedule::set_EndHour(int32)
0x5b095  ldloc.1
0x5b096  ldc.i4.s 0x3B
0x5b098  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPDailySchedule::set_EndMinute(int32)
0x5b09d  ldloc.1
0x5b09e  ldc.i4.s 0x3B
0x5b0a0  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPDailySchedule::set_EndSecond(int32)
0x5b0a5  ldarg.1
0x5b0a6  ldstr    aLocalsiteurl// "localSiteUrl"
0x5b0ab  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x5b0b0  ldarg.2
0x5b0b1  ldstr    aOnpremtermstor// "onPremTermStoreName"
0x5b0b6  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNullOrEmpty(string value, string parameterName)
0x5b0bb  ldarg.2
0x5b0bc  callvirt instance string [mscorlib]System.String::Trim()
0x5b0c1  starg.s  2
0x5b0c3  ldarg.1
0x5b0c4  ldarg.2
0x5b0c5  call     class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Hybrid.TermStoreFactory::GetLocalTermStore(class [System]System.Uri siteUrl, string termStoreName)
0x5b0ca  stloc.2
0x5b0cb  ldloc.2
0x5b0cc  ldstr    aLocaltermstore// "localTermStore"
0x5b0d1  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x5b0d6  ldarg.0
0x5b0d7  ldnull
0x5b0d8  call     class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Hybrid.TermStoreFactory::GetRemoteTermStore(class [System]System.Uri url, [opt] string userAgentType)
0x5b0dd  stloc.3
0x5b0de  ldloc.3
0x5b0df  ldstr    aRemotetermstor// "remoteTermStore"
0x5b0e4  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x5b0e9  ldloc.3
0x5b0ea  ldc.i4.1
0x5b0eb  newobj   instance void Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::.ctor(class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore termStore, [opt] bool fetchSpecialGroupIds)
0x5b0f0  stloc.s  4
0x5b0f2  ldloc.s  4
0x5b0f4  ldstr    aRemoteservice// "remoteService"
0x5b0f9  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x5b0fe  ldnull
0x5b0ff  stloc.s  6
0x5b101  ldarg.3
0x5b102  brfalse.s loc_5B109
0x5b104  ldarg.3
0x5b105  ldlen
0x5b106  conv.i4
0x5b107  brtrue.s loc_5B127
0x5b109  ldc.i4.1
0x5b10a  stloc.s  5
0x5b10c  ldloc.s  4
0x5b10e  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::GetAllGroupIds()
0x5b113  stloc.s  6
0x5b115  ldloc.s  4
0x5b117  ldloc.s  6
0x5b119  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::GetTargetGroupNames(class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> targetGroupIds)
0x5b11e  call     T0x2B00000F
0x5b123  starg.s  3
0x5b125  br.s     loc_5B166
0x5b127  ldc.i4.0
0x5b128  stloc.s  7
0x5b12a  br.s     loc_5B14D
0x5b12c  ldarg.3
0x5b12d  ldloc.s  7
0x5b12f  ldelem.ref
0x5b130  ldstr    aReplicationgro// "replicationGroupName"
0x5b135  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNullOrEmpty(string value, string parameterName)
0x5b13a  ldarg.3
0x5b13b  ldloc.s  7
0x5b13d  ldarg.3
0x5b13e  ldloc.s  7
0x5b140  ldelem.ref
0x5b141  callvirt instance string [mscorlib]System.String::Trim()
0x5b146  stelem.ref
0x5b147  ldloc.s  7
0x5b149  ldc.i4.1
0x5b14a  add.ovf
0x5b14b  stloc.s  7
0x5b14d  ldloc.s  7
0x5b14f  ldarg.3
0x5b150  ldlen
0x5b151  conv.i4
0x5b152  blt.s    loc_5B12C
0x5b154  ldc.i4.0
0x5b155  stloc.s  5
0x5b157  ldloc.s  4
0x5b159  ldarg.3
0x5b15a  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x5b15f  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::GetTargetGroupIds(class [System.Core]System.Collections.Generic.HashSet`1<string> targetGroupNames)
0x5b164  stloc.s  6
0x5b166  ldarg.0
0x5b167  ldarg.1
0x5b168  ldarg.2
0x5b169  ldarg.3
0x5b16a  ldloc.s  6
0x5b16c  call     T0x2B00006B
0x5b171  ldloc.s  5
0x5b173  newobj   instance void Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyGroupsReplicationTimerJobDefinition::.ctor(class [System]System.Uri remoteSiteUrl, class [System]System.Uri localSiteUrl, string localTermStoreName, string[] replicatedGroupNames, valuetype [mscorlib]System.Guid[] replicatedGroupGuids, bool isReplicateAllGroups)
0x5b178  stloc.s  9
0x5b17a  ldloc.s  9
0x5b17c  ldloc.1
0x5b17d  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSchedule)
0x5b182  ldloc.s  9
0x5b184  stloc.s  8
0x5b186  ldloc.s  8
0x5b188  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x5b18d  ldc.i4   0x12103C2
0x5b192  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x5b197  ldc.i4.s 0x32
0x5b199  ldstr    aFinishedSchedu_0// "Finished scheduling taxonomy groups rep"...
0x5b19e  ldc.i4.1
0x5b19f  newarr   [mscorlib]System.Object
0x5b1a4  stloc.s  0xB
0x5b1a6  ldloc.s  0xB
0x5b1a8  ldc.i4.0
0x5b1a9  ldarg.0
0x5b1aa  stelem.ref
0x5b1ab  ldloc.s  0xB
0x5b1ad  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x5b1b2  ldloc.s  8
0x5b1b4  ret
```
