# Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager::GetTermStore_0

- ea: `0x2fe50`
- end: `0x2ff70`
- name: `Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager::GetTermStore_0`
- size: `288`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x2fe40`
- `0x53d60`

## callees

- `0x1ed00`
- `0x1ed20`
- `0x25e50`
- `0x2fe50`
- `0x2ff70`
- `0x302e0`
- `0x33640`
- `0x337e0`
- `0x337f0`
- `0x56c20`
- `0x56c70`
- `0x660d0`

## string_xrefs

- `0x2feae`: `Reattempting GetTermStoreData() for offline term store because forceRefetchIfOffline=true.  Proxy Name = "{0}"`
- `0x2fee4`: `Reattempting GetTermStoreData() for offline term store because enough time has elapsed.  Proxy Name = "{0}"`

## pseudocode

```c

```

## disassembly

```asm
0x2fe50  ldarg.3
0x2fe51  ldc.i4.0
0x2fe52  stind.i1
0x2fe53  ldarg.0
0x2fe54  call     instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager::get_Cache()
0x2fe59  stloc.0
0x2fe5a  ldloc.0
0x2fe5b  ldarg.0
0x2fe5c  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager::get_TermStore()
0x2fe61  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_PartitionId()
0x2fe66  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache::GetTermStoreData(valuetype [mscorlib]System.Guid partitionId)
0x2fe6b  stloc.1
0x2fe6c  ldc.i4.0
0x2fe6d  stloc.2
0x2fe6e  ldloc.1
0x2fe6f  brtrue.s loc_2FE78
0x2fe71  ldc.i4.1
0x2fe72  stloc.2
0x2fe73  br       loc_2FF04
0x2fe78  ldloc.0
0x2fe79  isinst   Microsoft.SharePoint.Taxonomy.Internal.ForegroundFlushingTaxonomyCache
0x2fe7e  brfalse  loc_2FF04
0x2fe83  ldloc.1
0x2fe84  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore::get_LoadedFromPersistedData()
0x2fe89  brtrue.s loc_2FE93
0x2fe8b  ldloc.1
0x2fe8c  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore::get_IsInitialized()
0x2fe91  brtrue.s loc_2FF04
0x2fe93  ldarg.0
0x2fe94  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager::termStore
0x2fe99  callvirt instance class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy Microsoft.SharePoint.Taxonomy.TermStore::get_SharedServiceProxy()
0x2fe9e  stloc.3
0x2fe9f  ldarg.2
0x2fea0  brfalse.s loc_2FED0
0x2fea2  ldc.i4   0x853561
0x2fea7  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x2feac  ldc.i4.s 0x32
0x2feae  ldstr    aReattemptingGe// "Reattempting GetTermStoreData() for off"...
0x2feb3  ldc.i4.1
0x2feb4  newarr   [mscorlib]System.Object
0x2feb9  stloc.s  4
0x2febb  ldloc.s  4
0x2febd  ldc.i4.0
0x2febe  ldloc.3
0x2febf  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x2fec4  stelem.ref
0x2fec5  ldloc.s  4
0x2fec7  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x2fecc  ldc.i4.1
0x2fecd  stloc.2
0x2fece  br.s     loc_2FF04
0x2fed0  ldloc.3
0x2fed1  callvirt instance bool Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::ShouldReattemptOfflineTermStore()
0x2fed6  brfalse.s loc_2FF04
0x2fed8  ldc.i4   0x853562
0x2fedd  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x2fee2  ldc.i4.s 0x32
0x2fee4  ldstr    aReattemptingGe_0// "Reattempting GetTermStoreData() for off"...
0x2fee9  ldc.i4.1
0x2feea  newarr   [mscorlib]System.Object
0x2feef  stloc.s  5
0x2fef1  ldloc.s  5
0x2fef3  ldc.i4.0
0x2fef4  ldloc.3
0x2fef5  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x2fefa  stelem.ref
0x2fefb  ldloc.s  5
0x2fefd  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x2ff02  ldc.i4.1
0x2ff03  stloc.2
0x2ff04  ldloc.2
0x2ff05  brfalse.s loc_2FF6E
0x2ff07  ldarg.1
0x2ff08  brfalse.s loc_2FF39
0x2ff0a  ldarg.0
0x2ff0b  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager::get_TermStore()
0x2ff10  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_PartitionId()
0x2ff15  ldc.i4.0
0x2ff16  ldsfld   string [mscorlib]System.String::Empty
0x2ff1b  ldc.i4.0
0x2ff1c  call     class Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore::CreateUninitializedTermStore(valuetype [mscorlib]System.Guid partitionId, bool isUserDeniedAccess, string proxyName, bool doLogEvent)
0x2ff21  stloc.1
0x2ff22  ldarg.0
0x2ff23  call     instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager::get_Cache()
0x2ff28  ldarg.0
0x2ff29  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager::get_TermStore()
0x2ff2e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_PartitionId()
0x2ff33  ldloc.1
0x2ff34  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache::AddTermStoreData(valuetype [mscorlib]System.Guid partitionId, class Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore sharedTermStore)
0x2ff39  ldarg.0
0x2ff3a  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.DataAccessManager Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager::dataAccessManager
0x2ff3f  ldarg.0
0x2ff40  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager::get_TermStore()
0x2ff45  callvirt instance class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy Microsoft.SharePoint.Taxonomy.TermStore::get_SharedServiceProxy()
0x2ff4a  ldarg.0
0x2ff4b  call     instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager::get_Cache()
0x2ff50  ldarg.3
0x2ff51  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore Microsoft.SharePoint.Taxonomy.Internal.DataAccessManager::GetTermStoreData(class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy sharedServiceProxy, class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache cache, [out] bool& partitionCreated)
0x2ff56  stloc.1
0x2ff57  ldarg.0
0x2ff58  call     instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager::get_Cache()
0x2ff5d  ldarg.0
0x2ff5e  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager::get_TermStore()
0x2ff63  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_PartitionId()
0x2ff68  ldloc.1
0x2ff69  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache::AddTermStoreData(valuetype [mscorlib]System.Guid partitionId, class Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore sharedTermStore)
0x2ff6e  ldloc.1
0x2ff6f  ret
```
