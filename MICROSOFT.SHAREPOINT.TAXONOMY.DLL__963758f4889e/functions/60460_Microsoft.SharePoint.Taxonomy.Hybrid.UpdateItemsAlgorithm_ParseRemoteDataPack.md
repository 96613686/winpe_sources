# Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::ParseRemoteDataPack

- ea: `0x60460`
- end: `0x605d3`
- name: `Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::ParseRemoteDataPack`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x603f0`

## callees

- `0x242a0`
- `0x5f800`
- `0x5f820`
- `0x5f840`
- `0x5f860`
- `0x5f880`
- `0x5f8a0`
- `0x5f8c0`

## string_xrefs

- `0x604fa`: `RemoteDeletedGroupIds`
- `0x6050a`: `RemoteDeletedTermSetIds`
- `0x6051a`: `RemoteDeletedTermIds`
- `0x60530`: `Parsing remote data pack. Total deleted groups: {0}, total deleted term sets: {1}, total deleted terms: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x60460  ldarg.0
0x60461  ldarg.1
0x60462  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermGroup> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteDataPack::get_GroupCollection()
0x60467  stfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermGroup> Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::remoteGroupCollection
0x6046c  ldarg.0
0x6046d  ldarg.1
0x6046e  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermSet> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteDataPack::get_TermSetCollection()
0x60473  stfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermSet> Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::remoteTermSetCollection
0x60478  ldarg.0
0x60479  ldarg.1
0x6047a  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteDataPack::get_TermCollection()
0x6047f  stfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term> Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::remoteTermCollection
0x60484  ldarg.0
0x60485  ldarg.1
0x60486  callvirt instance class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Taxonomy.Hybrid.RemoteDataPack::get_TermDescriptions()
0x6048b  stfld    class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::remoteTermDescriptions
0x60490  ldarg.0
0x60491  ldarg.1
0x60492  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteDataPack::get_DeletedGroupIds()
0x60497  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::remoteDeletedGroupIds
0x6049c  ldarg.0
0x6049d  ldarg.1
0x6049e  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteDataPack::get_DeletedTermSetIds()
0x604a3  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::remoteDeletedTermSetIds
0x604a8  ldarg.0
0x604a9  ldarg.1
0x604aa  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteDataPack::get_DeletedTermIds()
0x604af  stfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>> Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::remoteDeletedTermIds
0x604b4  ldarg.0
0x604b5  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermGroup> Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::remoteGroupCollection
0x604ba  ldstr    aRemotegroupcol// "RemoteGroupCollection"
0x604bf  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x604c4  ldarg.0
0x604c5  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermSet> Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::remoteTermSetCollection
0x604ca  ldstr    aRemotetermsetc// "RemoteTermSetCollection"
0x604cf  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x604d4  ldarg.0
0x604d5  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term> Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::remoteTermCollection
0x604da  ldstr    aRemotetermcoll// "RemoteTermCollection"
0x604df  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x604e4  ldarg.0
0x604e5  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::remoteTermDescriptions
0x604ea  ldstr    aRemotetermdesc// "RemoteTermDescriptions"
0x604ef  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x604f4  ldarg.0
0x604f5  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::remoteDeletedGroupIds
0x604fa  ldstr    aRemotedeletedg// "RemoteDeletedGroupIds"
0x604ff  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x60504  ldarg.0
0x60505  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::remoteDeletedTermSetIds
0x6050a  ldstr    aRemotedeletedt// "RemoteDeletedTermSetIds"
0x6050f  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x60514  ldarg.0
0x60515  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>> Microsoft.SharePoint.Taxonomy.Hybrid.UpdateItemsAlgorithm::remoteDeletedTermIds
0x6051a  ldstr    aRemotedeletedt_0// "RemoteDeletedTermIds"
0x6051f  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x60524  ldc.i4   0x120E453
0x60529  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6052e  ldc.i4.s 0x32
0x60530  ldstr    aParsingRemoteD// "Parsing remote data pack. Total deleted"...
0x60535  ldc.i4.3
0x60536  newarr   [mscorlib]System.Object
0x6053b  stloc.0
0x6053c  ldloc.0
0x6053d  ldc.i4.0
0x6053e  ldarg.1
0x6053f  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteDataPack::get_DeletedGroupIds()
0x60544  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x60549  box      [mscorlib]System.Int32
0x6054e  stelem.ref
0x6054f  ldloc.0
0x60550  ldc.i4.1
0x60551  ldarg.1
0x60552  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteDataPack::get_DeletedTermSetIds()
0x60557  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x6055c  box      [mscorlib]System.Int32
0x60561  stelem.ref
0x60562  ldloc.0
0x60563  ldc.i4.2
0x60564  ldarg.1
0x60565  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteDataPack::get_DeletedTermIds()
0x6056a  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>>::get_Count()
0x6056f  box      [mscorlib]System.Int32
0x60574  stelem.ref
0x60575  ldloc.0
0x60576  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x6057b  ldc.i4   0x120E454
0x60580  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x60585  ldc.i4.s 0x32
0x60587  ldstr    aParsingRemoteD_0// "Parsing remote data pack. Total modifie"...
0x6058c  ldc.i4.3
0x6058d  newarr   [mscorlib]System.Object
0x60592  stloc.1
0x60593  ldloc.1
0x60594  ldc.i4.0
0x60595  ldarg.1
0x60596  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermGroup> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteDataPack::get_GroupCollection()
0x6059b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermGroup>::get_Count()
0x605a0  box      [mscorlib]System.Int32
0x605a5  stelem.ref
0x605a6  ldloc.1
0x605a7  ldc.i4.1
0x605a8  ldarg.1
0x605a9  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermSet> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteDataPack::get_TermSetCollection()
0x605ae  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermSet>::get_Count()
0x605b3  box      [mscorlib]System.Int32
0x605b8  stelem.ref
0x605b9  ldloc.1
0x605ba  ldc.i4.2
0x605bb  ldarg.1
0x605bc  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteDataPack::get_TermCollection()
0x605c1  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term>::get_Count()
0x605c6  box      [mscorlib]System.Int32
0x605cb  stelem.ref
0x605cc  ldloc.1
0x605cd  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x605d2  ret
```
