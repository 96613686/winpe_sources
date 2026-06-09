# Microsoft.SharePoint.Taxonomy.Internal.BackgroundFlushingTaxonomyCache::CheckForChanges

- ea: `0x20600`
- end: `0x20980`
- name: `Microsoft.SharePoint.Taxonomy.Internal.BackgroundFlushingTaxonomyCache::CheckForChanges`
- size: `896`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x205d0`
- `0x205f0`

## callees

- `0x1ec00`
- `0x1ed60`
- `0x1f860`
- `0x1fbf0`
- `0x1fd00`
- `0x20550`
- `0x20570`
- `0x20600`
- `0x20980`
- `0x256d0`
- `0x25af0`
- `0x263b0`
- `0x26410`
- `0x26570`
- `0x65c80`
- `0x66880`

## string_xrefs

- `0x2060c`: `Checking for Term store changes and updating caches`
- `0x20869`: `Taxonomy_FoundChangesForCache`
- `0x208d1`: `Taxonomy_ForcedCacheUpdate`
- `0x2090a`: `Failed to get term store during cache check for changes.  Proxy '{0}'. Exception: {1}`
- `0x20975`: `Caches have been updated.`

## pseudocode

```c

```

## disassembly

```asm
0x20600  ldc.i4   0x31346763
0x20605  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x2060a  ldc.i4.s 0x64
0x2060c  ldstr    aCheckingForTer// "Checking for Term store changes and upd"...
0x20611  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x20616  ldarg.0
0x20617  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache::get_SharedServiceId()
0x2061c  call     class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::Get(valuetype [mscorlib]System.Guid proxyId)
0x20621  stloc.0
0x20622  ldloc.0
0x20623  ldnull
0x20624  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x20629  brfalse.s loc_20642
0x2062b  ldc.i4   0x35657273
0x20630  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x20635  ldc.i4.s 0x64
0x20637  ldstr    aCannotCheckFor// "Cannot check for changes because no EMM"...
0x2063c  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x20641  ret
0x20642  ldloc.0
0x20643  callvirt instance bool Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::GetIsServiceDataMapEnabled()
0x20648  ldc.i4.0
0x20649  ceq
0x2064b  stloc.1
0x2064c  ldarg.1
0x2064d  brtrue.s loc_20659
0x2064f  ldarg.0
0x20650  ldloc.0
0x20651  call     instance bool Microsoft.SharePoint.Taxonomy.Internal.BackgroundFlushingTaxonomyCache::TimeToCheckForUpdates(class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy applicationProxy)
0x20656  brtrue.s loc_20659
0x20658  ret
0x20659  ldnull
0x2065a  stloc.2
0x2065b  ldloca.s 3
0x2065d  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x20663  ldc.i4.0
0x20664  stloc.s  4
0x20666  ldarg.0
0x20667  call     instance int32 Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::get_TermStoreCount()
0x2066c  ldc.i4.0
0x2066d  ble      loc_2095C
0x20672  ldloc.0
0x20673  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x20678  newobj   instance void Microsoft.SharePoint.Taxonomy.Internal.DataAccessManager::.ctor(class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy applicationProxy, valuetype [mscorlib]System.Guid rawPartitionId)
0x2067d  stloc.s  5
0x2067f  ldc.i4.0
0x20680  stloc.s  6
0x20682  ldc.i4.0
0x20683  stloc.s  7
0x20685  ldloc.1
0x20686  brfalse  loc_20750
0x2068b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x20690  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x20695  stloc.3
0x20696  ldarg.0
0x20697  ldfld    valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.Internal.BackgroundFlushingTaxonomyCache::lastChangeTime
0x2069c  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x206a1  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x206a6  brfalse  loc_2072C
0x206ab  ldloc.s  5
0x206ad  ldc.i4.1
0x206ae  ldarg.0
0x206af  ldfld    valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.Internal.BackgroundFlushingTaxonomyCache::lastChangeTime
0x206b4  call     valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.Internal.CommonValidator::GetValidDBTime(valuetype [mscorlib]System.DateTime time)
0x206b9  ldloca.s 0x11
0x206bb  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x206c1  ldloc.s  0x11
0x206c3  ldloca.s 0x12
0x206c5  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x206cb  ldloc.s  0x12
0x206cd  ldloca.s 0x13
0x206cf  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.Taxonomy.ChangedItemType>
0x206d5  ldloc.s  0x13
0x206d7  ldloca.s 0x14
0x206d9  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.Taxonomy.ChangedOperationType>
0x206df  ldloc.s  0x14
0x206e1  ldarg.1
0x206e2  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x206e7  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.ChangedItem> Microsoft.SharePoint.Taxonomy.Internal.DataAccessManager::GetChanges(bool forAllPartitions, valuetype [mscorlib]System.DateTime sinceTime, valuetype [mscorlib]System.Nullable`1<int32> groupId, valuetype [mscorlib]System.Nullable`1<int32> termSetId, valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.Taxonomy.ChangedItemType> changedItemType, valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.Taxonomy.ChangedOperationType> changedOperationType, valuetype [mscorlib]System.Nullable`1<bool> enforceUpdate)
0x206ec  stloc.s  8
0x206ee  ldloc.s  8
0x206f0  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.ChangedItem>::get_Count()
0x206f5  ldc.i4.0
0x206f6  ble.s    loc_20748
0x206f8  ldloc.s  7
0x206fa  ldloc.s  8
0x206fc  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.ChangedItem>::get_Count()
0x20701  add.ovf
0x20702  stloc.s  7
0x20704  ldarg.0
0x20705  call     instance class [mscorlib]System.Threading.ReaderWriterLock Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::get_DataLock()
0x2070a  ldc.i4.m1
0x2070b  callvirt instance void [mscorlib]System.Threading.ReaderWriterLock::AcquireWriterLock(int32)
0x20710  ldarg.0
0x20711  ldarg.0
0x20712  ldloc.s  8
0x20714  call     instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::InvalidateCacheWhileLocked(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.ChangedItem> changedItems)
0x20719  stfld    valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.Internal.BackgroundFlushingTaxonomyCache::lastChangeTime
0x2071e  leave.s  loc_20748
0x20720  ldarg.0
0x20721  call     instance class [mscorlib]System.Threading.ReaderWriterLock Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::get_DataLock()
0x20726  callvirt instance void [mscorlib]System.Threading.ReaderWriterLock::ReleaseWriterLock()
0x2072b  endfinally
0x2072c  ldloc.s  5
0x2072e  ldloca.s 0x15
0x20730  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x20736  ldloc.s  0x15
0x20738  ldloca.s 0x16
0x2073a  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x20740  ldloc.s  0x16
0x20742  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.Internal.DataAccessManager::GetChangeTime(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> groupGuid, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> termSetGuid)
0x20747  pop
0x20748  ldc.i4.1
0x20749  stloc.s  4
0x2074b  br       loc_208CE
0x20750  ldarg.0
0x20751  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.Taxonomy.Internal.BackgroundFlushingTaxonomyCache::databaseLastChangeTimes
0x20756  callvirt instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>[] class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.DateTime>::ToArray()
0x2075b  stloc.s  0x17
0x2075d  ldc.i4.0
0x2075e  stloc.s  0x18
0x20760  br       loc_20859
0x20765  ldloc.s  0x17
0x20767  ldloc.s  0x18
0x20769  ldelema  valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.DateTime>
0x2076e  ldobj    valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.DateTime>
0x20773  stloc.s  9
0x20775  ldloca.s 9
0x20777  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.DateTime>::get_Key()
0x2077c  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x20781  stloc.3
0x20782  ldloca.s 9
0x20784  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.DateTime>::get_Value()
0x20789  stloc.s  0xA
0x2078b  ldloc.s  0xA
0x2078d  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x20792  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x20797  brfalse  loc_20853
0x2079c  ldloc.s  5
0x2079e  ldloca.s 3
0x207a0  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x207a5  ldloc.s  0xA
0x207a7  call     valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.Internal.CommonValidator::GetValidDBTime(valuetype [mscorlib]System.DateTime time)
0x207ac  ldloca.s 0x19
0x207ae  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x207b4  ldloc.s  0x19
0x207b6  ldloca.s 0x1A
0x207b8  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x207be  ldloc.s  0x1A
0x207c0  ldloca.s 0x1B
0x207c2  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.Taxonomy.ChangedItemType>
0x207c8  ldloc.s  0x1B
0x207ca  ldloca.s 0x1C
0x207cc  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.Taxonomy.ChangedOperationType>
0x207d2  ldloc.s  0x1C
0x207d4  ldarg.1
0x207d5  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x207da  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.ChangedItem> Microsoft.SharePoint.Taxonomy.Internal.DataAccessManager::GetChangesForDatabase(valuetype [mscorlib]System.Guid contentDatabaseId, valuetype [mscorlib]System.DateTime sinceTime, valuetype [mscorlib]System.Nullable`1<int32> groupId, valuetype [mscorlib]System.Nullable`1<int32> termSetId, valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.Taxonomy.ChangedItemType> changedItemType, valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.Taxonomy.ChangedOperationType> changedOperationType, valuetype [mscorlib]System.Nullable`1<bool> enforceUpdate)
0x207df  stloc.s  0xD
0x207e1  ldloc.s  0xD
0x207e3  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.ChangedItem>::get_Count()
0x207e8  ldc.i4.0
0x207e9  ble.s    loc_20850
0x207eb  ldloc.s  7
0x207ed  ldloc.s  0xD
0x207ef  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.ChangedItem>::get_Count()
0x207f4  add.ovf
0x207f5  stloc.s  7
0x207f7  ldarg.0
0x207f8  call     instance class [mscorlib]System.Threading.ReaderWriterLock Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::get_DataLock()
0x207fd  ldc.i4.m1
0x207fe  callvirt instance void [mscorlib]System.Threading.ReaderWriterLock::AcquireWriterLock(int32)
0x20803  ldarg.0
0x20804  ldloc.s  0xD
0x20806  call     instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::InvalidateCacheWhileLocked(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.ChangedItem> changedItems)
0x2080b  stloc.s  0xB
0x2080d  ldarg.0
0x2080e  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.Taxonomy.Internal.BackgroundFlushingTaxonomyCache::databaseLastChangeTimes
0x20813  ldloca.s 3
0x20815  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x2081a  ldloca.s 0xC
0x2081c  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.DateTime>::TryGetValue(var<u1>, !!T0)
0x20821  brfalse.s loc_20842
0x20823  ldloc.s  0xB
0x20825  ldloc.s  0xC
0x20827  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x2082c  brfalse.s loc_20842
0x2082e  ldarg.0
0x2082f  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.Taxonomy.Internal.BackgroundFlushingTaxonomyCache::databaseLastChangeTimes
0x20834  ldloca.s 3
0x20836  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x2083b  ldloc.s  0xB
0x2083d  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.DateTime>::set_Item(var<u1>, !!T0)
0x20842  leave.s  loc_20850
0x20844  ldarg.0
0x20845  call     instance class [mscorlib]System.Threading.ReaderWriterLock Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::get_DataLock()
0x2084a  callvirt instance void [mscorlib]System.Threading.ReaderWriterLock::ReleaseWriterLock()
0x2084f  endfinally
0x20850  ldc.i4.1
0x20851  stloc.s  4
0x20853  ldloc.s  0x18
0x20855  ldc.i4.1
0x20856  add
0x20857  stloc.s  0x18
0x20859  ldloc.s  0x18
0x2085b  ldloc.s  0x17
0x2085d  ldlen
0x2085e  conv.i4
0x2085f  blt      loc_20765
0x20864  ldloc.s  7
0x20866  ldc.i4.0
0x20867  ble.s    loc_208AB
0x20869  ldstr    aTaxonomyFoundc// "Taxonomy_FoundChangesForCache"
0x2086e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x20873  stloc.s  0xE
0x20875  ldloc.s  0xE
0x20877  ldstr    aChangecount// "ChangeCount"
0x2087c  ldloc.s  7
0x2087e  box      [mscorlib]System.Int32
0x20883  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x20888  ldloc.s  0xE
0x2088a  ldstr    aDatabasecount// "DatabaseCount"
0x2088f  ldarg.0
0x20890  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.Taxonomy.Internal.BackgroundFlushingTaxonomyCache::databaseLastChangeTimes
0x20895  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.DateTime>::get_Count()
0x2089a  box      [mscorlib]System.Int32
0x2089f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x208a4  ldloc.s  0xE
0x208a6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPUserEngagement::WriteDiagnosticEvent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x208ab  ldloc.s  4
0x208ad  brtrue.s loc_208CE
0x208af  ldloc.s  5
0x208b1  ldloca.s 0x1D
0x208b3  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x208b9  ldloc.s  0x1D
0x208bb  ldloca.s 0x1E
0x208bd  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x208c3  ldloc.s  0x1E
0x208c5  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.Internal.DataAccessManager::GetChangeTime(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> groupGuid, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> termSetGuid)
0x208ca  pop
0x208cb  ldc.i4.1
0x208cc  stloc.s  4
0x208ce  ldarg.1
0x208cf  brfalse.s loc_208F7
0x208d1  ldstr    aTaxonomyForced// "Taxonomy_ForcedCacheUpdate"
0x208d6  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x208db  stloc.s  0xF
0x208dd  ldloc.s  0xF
0x208df  ldstr    aChangecount// "ChangeCount"
0x208e4  ldloc.s  7
0x208e6  box      [mscorlib]System.Int32
0x208eb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x208f0  ldloc.s  0xF
0x208f2  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPUserEngagement::WriteDiagnosticEvent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x208f7  leave.s  loc_20944
0x208f9  stloc.s  0x10
0x208fb  ldloc.s  0x10
0x208fd  stloc.2
0x208fe  ldc.i4   0x63683930
0x20903  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x20908  ldc.i4.s 0xF
0x2090a  ldstr    aFailedToGetTer_1// "Failed to get term store during cache c"...
0x2090f  ldc.i4.2
0x20910  newarr   [mscorlib]System.Object
0x20915  stloc.s  0x1F
0x20917  ldloc.s  0x1F
0x20919  ldc.i4.0
0x2091a  ldloc.0
0x2091b  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_DisplayName()
0x20920  stelem.ref
0x20921  ldloc.s  0x1F
0x20923  ldc.i4.1
0x20924  ldloc.s  0x10
0x20926  callvirt instance string [mscorlib]System.Object::ToString()
0x2092b  stelem.ref
0x2092c  ldloc.s  0x1F
0x2092e  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x20933  ldloc.s  0x10
0x20935  isinst   [mscorlib]System.UnauthorizedAccessException
0x2093a  brfalse.s loc_2093F
0x2093c  ldc.i4.1
0x2093d  stloc.s  6
0x2093f  ldc.i4.0
0x20940  stloc.s  4
0x20942  rethrow
0x20944  leave.s  loc_2095C
0x20946  ldarg.0
0x20947  ldloc.s  4
0x20949  ldloc.s  6
0x2094b  ldloc.0
0x2094c  call     instance void Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::UpdateStatusForTermStores(bool isOnline, bool isAccessDenied, class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy applicationProxy)
0x20951  ldarg.0
0x20952  ldloc.s  4
0x20954  ldloc.3
0x20955  ldloc.2
0x20956  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache::SetGlobalServiceOnlineState(bool value, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> contentDatabaseId, class [mscorlib]System.Exception exception)
0x2095b  endfinally
0x2095c  leave.s  loc_20969
0x2095e  ldloc.s  4
0x20960  brfalse.s loc_20968
  ... truncated ...
```
