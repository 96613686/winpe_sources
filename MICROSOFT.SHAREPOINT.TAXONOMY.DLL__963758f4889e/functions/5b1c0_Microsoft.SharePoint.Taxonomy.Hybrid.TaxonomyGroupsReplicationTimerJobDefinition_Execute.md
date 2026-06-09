# Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyGroupsReplicationTimerJobDefinition::Execute

- ea: `0x5b1c0`
- end: `0x5b760`
- name: `Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyGroupsReplicationTimerJobDefinition::Execute`
- size: `1440`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callees

- `0x242a0`
- `0x28be0`
- `0x28cf0`
- `0x28dd0`
- `0x2acd0`
- `0x2ad40`
- `0x56b70`
- `0x59ea0`
- `0x5a020`
- `0x5a200`
- `0x5b1c0`
- `0x5b780`
- `0x5b790`
- `0x5b7a0`
- `0x5b7d0`
- `0x5fd90`
- `0x60170`
- `0x75430`

## string_xrefs

- `0x5b41e`: `attemptTimes`
- `0x5b45b`: `Taxonomy replication: attempt times:{0}`
- `0x5b5d6`: `Failed to update the taxonomy groups replication timer job object`
- `0x5b5e6`: `SharePointHybridTaxonomy_ReplicationUpdateTimerJobFailure`

## pseudocode

```c

```

## disassembly

```asm
0x5b1c0  ldnull
0x5b1c1  stloc.s  0xF
0x5b1c3  newobj   instance void <>c__DisplayClass7::.ctor()
0x5b1c8  stloc.s  0x10
0x5b1ca  ldloc.s  0x10
0x5b1cc  ldarg.0
0x5b1cd  stfld    class Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyGroupsReplicationTimerJobDefinition <>c__DisplayClass7::<>4__this
0x5b1d2  ldloc.s  0x10
0x5b1d4  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x5b1d9  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass7::replicationStartTime
0x5b1de  ldc.i4.0
0x5b1df  stloc.0
0x5b1e0  ldarg.0
0x5b1e1  ldfld    valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyGroupsReplicationTimerJobDefinition::lastGetChangesTimeForRemoteDatabase
0x5b1e6  stloc.1
0x5b1e7  ldloc.s  0x10
0x5b1e9  ldloc.1
0x5b1ea  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x5b1ef  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x5b1f4  stfld    bool <>c__DisplayClass7::replicateDelta
0x5b1f9  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x5b1fe  ldarg.0
0x5b1ff  ldfld    valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyGroupsReplicationTimerJobDefinition::lastSuccessfulReplicationTime
0x5b204  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x5b209  ldarg.0
0x5b20a  ldfld    valuetype [mscorlib]System.TimeSpan Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyGroupsReplicationTimerJobDefinition::FullReplicationFailureMaxTimeSpan
0x5b20f  call     bool [mscorlib]System.TimeSpan::op_GreaterThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x5b214  brfalse.s loc_5B21E
0x5b216  ldloc.s  0x10
0x5b218  ldc.i4.0
0x5b219  stfld    bool <>c__DisplayClass7::replicateDelta
0x5b21e  ldloc.s  0x10
0x5b220  ldfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass7::replicationStartTime
0x5b225  ldarg.0
0x5b226  ldfld    valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyGroupsReplicationTimerJobDefinition::lastFullReplicationTime
0x5b22b  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x5b230  ldarg.0
0x5b231  ldfld    valuetype [mscorlib]System.TimeSpan Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyGroupsReplicationTimerJobDefinition::FullReplicationInterval
0x5b236  call     bool [mscorlib]System.TimeSpan::op_GreaterThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x5b23b  brfalse.s loc_5B245
0x5b23d  ldloc.s  0x10
0x5b23f  ldc.i4.0
0x5b240  stfld    bool <>c__DisplayClass7::replicateDelta
0x5b245  ldc.i4   0x12103C3
0x5b24a  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x5b24f  ldc.i4.s 0x32
0x5b251  ldstr    aTaxonomyReplic_0// "Taxonomy replication: start executing t"...
0x5b256  ldc.i4.3
0x5b257  newarr   [mscorlib]System.Object
0x5b25c  stloc.s  0x11
0x5b25e  ldloc.s  0x11
0x5b260  ldc.i4.0
0x5b261  ldloc.s  0x10
0x5b263  ldfld    bool <>c__DisplayClass7::replicateDelta
0x5b268  box      [mscorlib]System.Boolean
0x5b26d  stelem.ref
0x5b26e  ldloc.s  0x11
0x5b270  ldc.i4.1
0x5b271  ldloc.1
0x5b272  box      [mscorlib]System.DateTime
0x5b277  stelem.ref
0x5b278  ldloc.s  0x11
0x5b27a  ldc.i4.2
0x5b27b  ldarg.0
0x5b27c  ldfld    valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyGroupsReplicationTimerJobDefinition::lastSuccessfulReplicationTime
0x5b281  box      [mscorlib]System.DateTime
0x5b286  stelem.ref
0x5b287  ldloc.s  0x11
0x5b289  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x5b28e  ldc.i4.0
0x5b28f  stloc.2
0x5b290  ldnull
0x5b291  stloc.3
0x5b292  call     void Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserEngagement::Flush()
0x5b297  ldstr    aSharepointhybr_26// "SharePointHybridTaxonomy_TimerJobStarte"...
0x5b29c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x5b2a1  stloc.s  0xD
0x5b2a3  ldloc.s  0xD
0x5b2a5  ldstr    aReplicatedelta// "replicateDelta"
0x5b2aa  ldloc.s  0x10
0x5b2ac  ldfld    bool <>c__DisplayClass7::replicateDelta
0x5b2b1  box      [mscorlib]System.Boolean
0x5b2b6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x5b2bb  ldloc.s  0xD
0x5b2bd  ldstr    aLastreplicatio// "lastReplicationTime"
0x5b2c2  ldloc.1
0x5b2c3  box      [mscorlib]System.DateTime
0x5b2c8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x5b2cd  ldloc.s  0xD
0x5b2cf  ldc.r8   NaN
0x5b2d8  call     void Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserEngagement::WriteLog(string engagementName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, [opt] float64 durationMs)
0x5b2dd  ldarg.0
0x5b2de  call     instance class [System]System.Uri Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyGroupsReplicationTimerJobDefinition::get_LocalSiteUrl()
0x5b2e3  ldarg.0
0x5b2e4  call     instance string Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyGroupsReplicationTimerJobDefinition::get_LocalTermStoreName()
0x5b2e9  call     class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Hybrid.TermStoreFactory::GetLocalTermStore(class [System]System.Uri siteUrl, string termStoreName)
0x5b2ee  stloc.s  5
0x5b2f0  ldloc.s  5
0x5b2f2  ldstr    aLocaltermstore// "localTermStore"
0x5b2f7  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x5b2fc  ldarg.0
0x5b2fd  call     instance class [System]System.Uri Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyGroupsReplicationTimerJobDefinition::get_RemoteSiteUrl()
0x5b302  ldnull
0x5b303  call     class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Hybrid.TermStoreFactory::GetRemoteTermStore(class [System]System.Uri url, [opt] string userAgentType)
0x5b308  stloc.s  6
0x5b30a  ldloc.s  6
0x5b30c  ldstr    aRemotetermstor// "remoteTermStore"
0x5b311  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x5b316  ldloc.s  6
0x5b318  ldc.i4.1
0x5b319  newobj   instance void Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::.ctor(class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore termStore, [opt] bool fetchSpecialGroupIds)
0x5b31e  stloc.s  7
0x5b320  ldarg.0
0x5b321  ldfld    bool Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyGroupsReplicationTimerJobDefinition::isReplicateAllGroups
0x5b326  brfalse.s loc_5B37F
0x5b328  ldloc.s  0x10
0x5b32a  ldloc.s  7
0x5b32c  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::GetAllGroupIds()
0x5b331  stfld    class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass7::remoteGroupGuids
0x5b336  ldloc.s  0x10
0x5b338  ldloc.s  7
0x5b33a  ldloc.s  0x10
0x5b33c  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass7::remoteGroupGuids
0x5b341  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::GetTargetGroupNames(class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> targetGroupIds)
0x5b346  stfld    class [System.Core]System.Collections.Generic.HashSet`1<string> <>c__DisplayClass7::remoteGroupNames
0x5b34b  ldloc.s  5
0x5b34d  ldloc.s  6
0x5b34f  ldloc.s  0x10
0x5b351  ldfld    bool <>c__DisplayClass7::replicateDelta
0x5b356  ldloc.0
0x5b357  ldarg.0
0x5b358  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyGroupsReplicationTimerJobDefinition::replicatedGroupGuids
0x5b35d  ldloc.s  0x10
0x5b35f  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass7::remoteGroupGuids
0x5b364  call     T0x2B00005D
0x5b369  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x5b36e  ldloc.1
0x5b36f  ldloc.s  0x10
0x5b371  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass7::getChangesTimeForRemoteDatabase
0x5b376  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.Hybrid.HybridTaxonomyStatus Microsoft.SharePoint.Taxonomy.TermStore::Replicate(class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore remoteTermStore, bool isIncremental, bool isFullProperties, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> targetGroupIds, valuetype [mscorlib]System.DateTime lastReplicationTime, [out] valuetype [mscorlib]System.DateTime& lastChangedItemTime)
0x5b37b  stloc.s  4
0x5b37d  br.s     loc_5B3C8
0x5b37f  ldloc.s  0x10
0x5b381  ldarg.0
0x5b382  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyGroupsReplicationTimerJobDefinition::replicatedGroupGuids
0x5b387  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x5b38c  stfld    class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass7::remoteGroupGuids
0x5b391  ldloc.s  0x10
0x5b393  ldloc.s  7
0x5b395  ldloc.s  0x10
0x5b397  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass7::remoteGroupGuids
0x5b39c  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::GetTargetGroupNames(class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> targetGroupIds)
0x5b3a1  stfld    class [System.Core]System.Collections.Generic.HashSet`1<string> <>c__DisplayClass7::remoteGroupNames
0x5b3a6  ldloc.s  5
0x5b3a8  ldloc.s  6
0x5b3aa  ldloc.s  0x10
0x5b3ac  ldfld    bool <>c__DisplayClass7::replicateDelta
0x5b3b1  ldloc.0
0x5b3b2  ldloc.s  0x10
0x5b3b4  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass7::remoteGroupGuids
0x5b3b9  ldloc.1
0x5b3ba  ldloc.s  0x10
0x5b3bc  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass7::getChangesTimeForRemoteDatabase
0x5b3c1  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.Hybrid.HybridTaxonomyStatus Microsoft.SharePoint.Taxonomy.TermStore::Replicate(class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore remoteTermStore, bool isIncremental, bool isFullProperties, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> targetGroupIds, valuetype [mscorlib]System.DateTime lastReplicationTime, [out] valuetype [mscorlib]System.DateTime& lastChangedItemTime)
0x5b3c6  stloc.s  4
0x5b3c8  ldc.i4   0x12103C4
0x5b3cd  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x5b3d2  ldc.i4.s 0x32
0x5b3d4  ldstr    aTaxonomyReplic_1// "Taxonomy replication: successfully exec"...
0x5b3d9  ldc.i4.2
0x5b3da  newarr   [mscorlib]System.Object
0x5b3df  stloc.s  0x12
0x5b3e1  ldloc.s  0x12
0x5b3e3  ldc.i4.0
0x5b3e4  ldloc.s  0x10
0x5b3e6  ldfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass7::getChangesTimeForRemoteDatabase
0x5b3eb  box      [mscorlib]System.DateTime
0x5b3f0  stelem.ref
0x5b3f1  ldloc.s  0x12
0x5b3f3  ldc.i4.1
0x5b3f4  ldloc.s  4
0x5b3f6  box      Microsoft.SharePoint.Taxonomy.Hybrid.HybridTaxonomyStatus
0x5b3fb  stelem.ref
0x5b3fc  ldloc.s  0x12
0x5b3fe  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x5b403  leave    loc_5B559
0x5b408  stloc.s  8
0x5b40a  ldloc.2
0x5b40b  ldc.i4.1
0x5b40c  add.ovf
0x5b40d  stloc.2
0x5b40e  ldstr    aSharepointhybr_27// "SharePointHybridTaxonomy_ReplicationExc"...
0x5b413  ldloc.s  8
0x5b415  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x5b41a  stloc.s  9
0x5b41c  ldloc.s  9
0x5b41e  ldstr    aAttempttimes// "attemptTimes"
0x5b423  ldloc.2
0x5b424  box      [mscorlib]System.Int32
0x5b429  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x5b42e  ldloc.s  9
0x5b430  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x5b435  ldloc.s  0x10
0x5b437  ldfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass7::replicationStartTime
0x5b43c  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x5b441  stloc.s  0x13
0x5b443  ldloca.s 0x13
0x5b445  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x5b44a  call     void Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserEngagement::WriteException(string engagementName, class [mscorlib]System.Exception exception, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, [opt] float64 durationMs)
0x5b44f  ldc.i4   0x12103C5
0x5b454  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x5b459  ldloc.s  8
0x5b45b  ldstr    aTaxonomyReplic_2// "Taxonomy replication: attempt times:{0}"
0x5b460  ldc.i4.1
0x5b461  newarr   [mscorlib]System.Object
0x5b466  stloc.s  0x14
0x5b468  ldloc.s  0x14
0x5b46a  ldc.i4.0
0x5b46b  ldloc.2
0x5b46c  box      [mscorlib]System.Int32
0x5b471  stelem.ref
0x5b472  ldloc.s  0x14
0x5b474  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendExceptionTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, class [mscorlib]System.Exception, string, object[])
0x5b479  ldloc.2
0x5b47a  ldc.i4.3
0x5b47b  bne.un   loc_5B554
0x5b480  ldloc.s  0x10
0x5b482  ldfld    bool <>c__DisplayClass7::replicateDelta
0x5b487  brtrue.s loc_5B4B8
0x5b489  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x5b48e  ldarg.0
0x5b48f  call     instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyGroupsReplicationTimerJobDefinition::get_LastGetChangesTimeForRemoteDatabase()
0x5b494  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x5b499  ldarg.0
0x5b49a  ldfld    valuetype [mscorlib]System.TimeSpan Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyGroupsReplicationTimerJobDefinition::RemoteDatabaseChangeLogPersistedTime
0x5b49f  call     bool [mscorlib]System.TimeSpan::op_LessThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x5b4a4  brfalse.s loc_5B4B8
0x5b4a6  ldloc.s  8
0x5b4a8  stloc.3
0x5b4a9  ldloc.s  0x10
0x5b4ab  ldc.i4.1
0x5b4ac  stfld    bool <>c__DisplayClass7::replicateDelta
0x5b4b1  ldc.i4.0
0x5b4b2  stloc.2
0x5b4b3  br       loc_5B554
0x5b4b8  ldloc.3
0x5b4b9  brfalse.s loc_5B516
0x5b4bb  ldstr    aSharepointhybr_28// "SharePointHybridTaxonomy_FullAndIncreme"...
0x5b4c0  ldloc.s  8
0x5b4c2  ldnull
0x5b4c3  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x5b4c8  ldloc.s  0x10
0x5b4ca  ldfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass7::replicationStartTime
0x5b4cf  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x5b4d4  stloc.s  0x15
0x5b4d6  ldloca.s 0x15
0x5b4d8  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x5b4dd  call     void Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserEngagement::WriteException(string engagementName, class [mscorlib]System.Exception exception, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, [opt] float64 durationMs)
0x5b4e2  call     void Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserEngagement::Flush()
0x5b4e7  ldstr    aTaxonomyfullre// "TaxonomyFullReplicationAndIncrementalRe"...
0x5b4ec  ldc.i4.2
0x5b4ed  newarr   [mscorlib]System.Object
0x5b4f2  stloc.s  0x16
0x5b4f4  ldloc.s  0x16
0x5b4f6  ldc.i4.0
0x5b4f7  ldloc.3
0x5b4f8  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5b4fd  stelem.ref
0x5b4fe  ldloc.s  0x16
0x5b500  ldc.i4.1
0x5b501  ldloc.s  8
0x5b503  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5b508  stelem.ref
0x5b509  ldloc.s  0x16
0x5b50b  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x5b510  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPException::.ctor(string)
0x5b515  throw
0x5b516  ldloc.s  0x10
0x5b518  ldfld    bool <>c__DisplayClass7::replicateDelta
0x5b51d  brtrue.s loc_5B526
0x5b51f  ldstr    aSharepointhybr_29// "SharePointHybridTaxonomy_FullReplicatio"...
0x5b524  br.s     loc_5B52B
0x5b526  ldstr    aSharepointhybr_30// "SharePointHybridTaxonomy_IncrementalRep"...
0x5b52b  ldloc.s  8
0x5b52d  ldnull
0x5b52e  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x5b533  ldloc.s  0x10
0x5b535  ldfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass7::replicationStartTime
0x5b53a  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x5b53f  stloc.s  0x17
0x5b541  ldloca.s 0x17
0x5b543  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x5b548  call     void Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserEngagement::WriteException(string engagementName, class [mscorlib]System.Exception exception, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, [opt] float64 durationMs)
0x5b54d  call     void Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserEngagement::Flush()
0x5b552  rethrow
0x5b554  leave    loc_5B2DD
0x5b559  ldloc.3
0x5b55a  brfalse.s loc_5B5AB
0x5b55c  ldstr    aSharepointhybr_31// "SharePointHybridTaxonomy_FullReplicatio"...
0x5b561  ldloc.3
  ... truncated ...
```
