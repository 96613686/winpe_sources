# Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyReplicator::Replicate

- ea: `0x5f940`
- end: `0x5fad0`
- name: `Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyReplicator::Replicate`
- size: `400`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x28be0`
- `0x58290`
- `0x582c0`
- `0x5f370`
- `0x5f390`
- `0x5f800`
- `0x5f820`
- `0x5f840`
- `0x5f880`
- `0x5f8a0`
- `0x5f8c0`
- `0x5f8e0`
- `0x5f940`
- `0x5fad0`

## string_xrefs

- `0x5fa53`: `DeletedGroupCount`
- `0x5fa6e`: `DeletedTermSetCount`
- `0x5fa89`: `DeletedTermCount`

## pseudocode

```c

```

## disassembly

```asm
0x5f940  ldc.i4   0x120E449
0x5f945  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x5f94a  ldc.i4.s 0x32
0x5f94c  ldstr    aStartingReplic// "Starting replication."
0x5f951  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x5f956  ldarg.s  4
0x5f958  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x5f95d  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x5f962  brfalse.s loc_5F967
0x5f964  ldc.i4.0
0x5f965  starg.s  1
0x5f967  ldarg.0
0x5f968  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyReplicator::remoteService
0x5f96d  ldarg.0
0x5f96e  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.LocalService Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyReplicator::localService
0x5f973  newobj   instance void Microsoft.SharePoint.Taxonomy.Hybrid.PrerequisiteChecker::.ctor(class Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService remoteService, class Microsoft.SharePoint.Taxonomy.Hybrid.LocalService localService)
0x5f978  stloc.0
0x5f979  ldloc.0
0x5f97a  ldarg.3
0x5f97b  callvirt instance void Microsoft.SharePoint.Taxonomy.Hybrid.PrerequisiteChecker::CheckReplicationPrerequisite(class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> targetGroupIds)
0x5f980  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x5f985  stloc.1
0x5f986  ldloc.1
0x5f987  ldstr    aIsincremental// "IsIncremental"
0x5f98c  ldarg.1
0x5f98d  box      [mscorlib]System.Boolean
0x5f992  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x5f997  ldstr    aSharepointhybr_35// "SharePointHybridTaxonomy_ReplicationSta"...
0x5f99c  ldloc.1
0x5f99d  ldc.r8   NaN
0x5f9a6  call     void Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserEngagement::WriteLog(string engagementName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, [opt] float64 durationMs)
0x5f9ab  ldarg.0
0x5f9ac  ldarg.1
0x5f9ad  ldarg.2
0x5f9ae  ldarg.3
0x5f9af  ldarg.s  4
0x5f9b1  ldc.i4.3
0x5f9b2  call     instance class Microsoft.SharePoint.Taxonomy.Hybrid.RemoteDataPack Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyReplicator::FetchRemoteItemsWithRetry(bool isIncremental, bool isFullProperties, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> targetGroupIds, valuetype [mscorlib]System.DateTime lastReplicationTime, int32 retryCount)
0x5f9b7  stloc.2
0x5f9b8  ldarg.1
0x5f9b9  call     class Microsoft.SharePoint.Taxonomy.Hybrid.IUpdateItemsAlgorithm Microsoft.SharePoint.Taxonomy.Hybrid.LocalService::GetUpdateItemsAlgorithm(bool isIncremental)
0x5f9be  stloc.3
0x5f9bf  ldarg.0
0x5f9c0  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.LocalService Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyReplicator::localService
0x5f9c5  ldloc.3
0x5f9c6  ldarg.0
0x5f9c7  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.Hybrid.UserPrincipalNameMapper Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyReplicator::userPrincipalNameMapper
0x5f9cc  ldloc.2
0x5f9cd  ldarg.2
0x5f9ce  ldarg.s  4
0x5f9d0  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x5f9d5  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x5f9da  ldarg.3
0x5f9db  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.Hybrid.HybridTaxonomyStatus Microsoft.SharePoint.Taxonomy.Hybrid.LocalService::UpdateTaxonomyItems(class Microsoft.SharePoint.Taxonomy.Hybrid.IUpdateItemsAlgorithm updateItemsAlgorithm, class Microsoft.SharePoint.Taxonomy.Internal.Hybrid.UserPrincipalNameMapper userNameMapper, class Microsoft.SharePoint.Taxonomy.Hybrid.RemoteDataPack remoteDataPack, bool isFullProperties, bool isFirstUpdate, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> targetGroupIds)
0x5f9e0  stloc.s  4
0x5f9e2  ldarg.s  5
0x5f9e4  ldloc.2
0x5f9e5  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.Hybrid.RemoteDataPack::get_LastChangedItemTime()
0x5f9ea  stobj    [mscorlib]System.DateTime
0x5f9ef  ldloc.s  4
0x5f9f1  ldc.i4.2
0x5f9f2  conv.i8
0x5f9f3  and
0x5f9f4  ldc.i4.0
0x5f9f5  conv.i8
0x5f9f6  bne.un   loc_5FAB7
0x5f9fb  ldloc.1
0x5f9fc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Clear()
0x5fa01  ldloc.1
0x5fa02  ldstr    aModifiedgroupc// "ModifiedGroupCount"
0x5fa07  ldloc.2
0x5fa08  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermGroup> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteDataPack::get_GroupCollection()
0x5fa0d  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermGroup>::get_Count()
0x5fa12  box      [mscorlib]System.Int32
0x5fa17  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x5fa1c  ldloc.1
0x5fa1d  ldstr    aModifiedtermse// "ModifiedTermSetCount"
0x5fa22  ldloc.2
0x5fa23  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermSet> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteDataPack::get_TermSetCollection()
0x5fa28  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermSet>::get_Count()
0x5fa2d  box      [mscorlib]System.Int32
0x5fa32  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x5fa37  ldloc.1
0x5fa38  ldstr    aModifiedtermco// "ModifiedTermCount"
0x5fa3d  ldloc.2
0x5fa3e  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteDataPack::get_TermCollection()
0x5fa43  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term>::get_Count()
0x5fa48  box      [mscorlib]System.Int32
0x5fa4d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x5fa52  ldloc.1
0x5fa53  ldstr    aDeletedgroupco// "DeletedGroupCount"
0x5fa58  ldloc.2
0x5fa59  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteDataPack::get_DeletedGroupIds()
0x5fa5e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x5fa63  box      [mscorlib]System.Int32
0x5fa68  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x5fa6d  ldloc.1
0x5fa6e  ldstr    aDeletedtermset// "DeletedTermSetCount"
0x5fa73  ldloc.2
0x5fa74  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteDataPack::get_DeletedTermSetIds()
0x5fa79  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x5fa7e  box      [mscorlib]System.Int32
0x5fa83  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x5fa88  ldloc.1
0x5fa89  ldstr    aDeletedtermcou// "DeletedTermCount"
0x5fa8e  ldloc.2
0x5fa8f  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteDataPack::get_DeletedTermIds()
0x5fa94  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>>::get_Count()
0x5fa99  box      [mscorlib]System.Int32
0x5fa9e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x5faa3  ldstr    aSharepointhybr_36// "SharePointHybridTaxonomy_ReplicationIte"...
0x5faa8  ldloc.1
0x5faa9  ldc.r8   NaN
0x5fab2  call     void Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserEngagement::WriteLog(string engagementName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, [opt] float64 durationMs)
0x5fab7  ldc.i4   0x120E44A
0x5fabc  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x5fac1  ldc.i4.s 0x32
0x5fac3  ldstr    aFinishedReplic// "Finished replication."
0x5fac8  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x5facd  ldloc.s  4
0x5facf  ret
```
