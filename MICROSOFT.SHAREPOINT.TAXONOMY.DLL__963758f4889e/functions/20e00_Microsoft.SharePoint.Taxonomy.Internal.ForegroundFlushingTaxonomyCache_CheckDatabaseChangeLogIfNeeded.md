# Microsoft.SharePoint.Taxonomy.Internal.ForegroundFlushingTaxonomyCache::CheckDatabaseChangeLogIfNeeded

- ea: `0x20e00`
- end: `0x21301`
- name: `Microsoft.SharePoint.Taxonomy.Internal.ForegroundFlushingTaxonomyCache::CheckDatabaseChangeLogIfNeeded`
- size: `1281`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x20da0`
- `0x20dd0`

## callees

- `0x1ec00`
- `0x1ed60`
- `0x1f860`
- `0x1fbf0`
- `0x1fd00`
- `0x20550`
- `0x20570`
- `0x20e00`
- `0x213c0`
- `0x256d0`
- `0x25af0`
- `0x26410`
- `0x265d0`
- `0x63a30`
- `0x65c80`
- `0x668a0`

## string_xrefs

- `0x212f6`: `Caches have been updated.`
- `0x20e0c`: `Checking for term store changes and updating caches`
- `0x20e37`: `Cannot check for changes because the MetadataWebServiceApplicationProxy was not found`
- `0x20f08`: `Gave up waiting for ServiceRequestLock because existing request was taking too long.  ContentDatabaseId={0}, Proxy='{1}'`
- `0x20f5f`: `Skipping check for changes because it was already performed by another thread.  ContentDatabaseId={0}, Proxy='{1}'`
- `0x20fc4`: `Calling GetChangesForDatabase on service database, Proxy='{0}', forceImmediateCheck={1}`
- `0x210df`: `Taxonomy_FoundChangesForCache2`
- `0x21224`: `Taxonomy_ForcedCacheUpdate2`

## pseudocode

```c

```

## disassembly

```asm
0x20e00  ldc.i4   0x78C880
0x20e05  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x20e0a  ldc.i4.s 0x64
0x20e0c  ldstr    aCheckingForTer_0// "Checking for term store changes and upd"...
0x20e11  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x20e16  ldarg.0
0x20e17  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache::get_SharedServiceId()
0x20e1c  call     class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::Get(valuetype [mscorlib]System.Guid proxyId)
0x20e21  stloc.0
0x20e22  ldloc.0
0x20e23  ldnull
0x20e24  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x20e29  brfalse.s loc_20E42
0x20e2b  ldc.i4   0x78C881
0x20e30  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x20e35  ldc.i4.s 0x64
0x20e37  ldstr    aCannotCheckFor_0// "Cannot check for changes because the Me"...
0x20e3c  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x20e41  ret
0x20e42  ldarg.0
0x20e43  call     instance int32 Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::get_TermStoreCount()
0x20e48  brtrue.s loc_20E61
0x20e4a  ldc.i4   0x78C882
0x20e4f  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x20e54  ldc.i4.s 0x64
0x20e56  ldstr    aCannotCheckFor_1// "Cannot check for changes because there "...
0x20e5b  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x20e60  ret
0x20e61  ldarg.0
0x20e62  ldarg.1
0x20e63  call     instance class TrackedDatabase Microsoft.SharePoint.Taxonomy.Internal.ForegroundFlushingTaxonomyCache::GetOrCreateTrackedDatabase(valuetype [mscorlib]System.Guid contentDatabaseId)
0x20e68  stloc.1
0x20e69  call     bool Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_IsServiceDatabaseEnabled()
0x20e6e  brtrue.s loc_20E7E
0x20e70  ldsfld   int32 Microsoft.SharePoint.Taxonomy.PartitionSettings::DefaultCacheCheckInterval
0x20e75  ldc.i4   0x3E8
0x20e7a  mul.ovf
0x20e7b  stloc.2
0x20e7c  br.s     loc_20E8B
0x20e7e  ldloc.0
0x20e7f  callvirt instance int32 Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::GetCacheCheckIntervalInSeconds()
0x20e84  ldc.i4   0x3E8
0x20e89  mul.ovf
0x20e8a  stloc.2
0x20e8b  call     int32 [mscorlib]System.Environment::get_TickCount()
0x20e90  stloc.3
0x20e91  ldc.i4.0
0x20e92  stloc.s  0x15
0x20e94  ldloc.1
0x20e95  ldfld    object TrackedDatabase::AccessLock
0x20e9a  dup
0x20e9b  stloc.s  0x16
0x20e9d  ldloca.s 0x15
0x20e9f  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x20ea4  ldloc.1
0x20ea5  ldfld    valuetype [mscorlib]System.DateTime TrackedDatabase::LastChangeTime
0x20eaa  stloc.s  5
0x20eac  ldloc.1
0x20ead  ldfld    int32 TrackedDatabase::TickCountOfLastCheck
0x20eb2  stloc.s  4
0x20eb4  leave.s  loc_20EC2
0x20eb6  ldloc.s  0x15
0x20eb8  brfalse.s loc_20EC1
0x20eba  ldloc.s  0x16
0x20ebc  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x20ec1  endfinally
0x20ec2  ldarg.2
0x20ec3  brtrue.s loc_20ED1
0x20ec5  ldloc.s  4
0x20ec7  brfalse.s loc_20ED1
0x20ec9  ldloc.3
0x20eca  ldloc.s  4
0x20ecc  sub
0x20ecd  ldloc.2
0x20ece  bge.s    loc_20ED1
0x20ed0  ret
0x20ed1  ldc.i4.0
0x20ed2  stloc.s  6
0x20ed4  ldnull
0x20ed5  stloc.s  7
0x20ed7  ldloc.0
0x20ed8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x20edd  newobj   instance void Microsoft.SharePoint.Taxonomy.Internal.DataAccessManager::.ctor(class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy applicationProxy, valuetype [mscorlib]System.Guid rawPartitionId)
0x20ee2  stloc.s  8
0x20ee4  ldc.i4.0
0x20ee5  stloc.s  9
0x20ee7  ldc.i4.0
0x20ee8  stloc.s  0xA
0x20eea  ldloc.1
0x20eeb  ldfld    object TrackedDatabase::ServiceRequestLock
0x20ef0  ldc.i4   0x4E20
0x20ef5  call     bool [mscorlib]System.Threading.Monitor::TryEnter(object, int32)
0x20efa  brtrue.s loc_20F36
0x20efc  ldc.i4   0x78C883
0x20f01  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x20f06  ldc.i4.s 0x32
0x20f08  ldstr    aGaveUpWaitingF// "Gave up waiting for ServiceRequestLock "...
0x20f0d  ldc.i4.2
0x20f0e  newarr   [mscorlib]System.Object
0x20f13  stloc.s  0x17
0x20f15  ldloc.s  0x17
0x20f17  ldc.i4.0
0x20f18  ldarg.1
0x20f19  box      [mscorlib]System.Guid
0x20f1e  stelem.ref
0x20f1f  ldloc.s  0x17
0x20f21  ldc.i4.1
0x20f22  ldloc.0
0x20f23  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_DisplayName()
0x20f28  stelem.ref
0x20f29  ldloc.s  0x17
0x20f2b  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x20f30  newobj   instance void [mscorlib]System.TimeoutException::.ctor()
0x20f35  throw
0x20f36  ldc.i4.0
0x20f37  stloc.s  0x14
0x20f39  ldloc.1
0x20f3a  ldfld    object TrackedDatabase::AccessLock
0x20f3f  dup
0x20f40  stloc.s  0x18
0x20f42  ldloca.s 0x14
0x20f44  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x20f49  ldloc.1
0x20f4a  ldfld    int32 TrackedDatabase::TickCountOfLastCheck
0x20f4f  ldloc.s  4
0x20f51  beq.s    loc_20F8C
0x20f53  ldc.i4   0x78C884
0x20f58  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x20f5d  ldc.i4.s 0x32
0x20f5f  ldstr    aSkippingCheckF// "Skipping check for changes because it w"...
0x20f64  ldc.i4.2
0x20f65  newarr   [mscorlib]System.Object
0x20f6a  stloc.s  0x19
0x20f6c  ldloc.s  0x19
0x20f6e  ldc.i4.0
0x20f6f  ldarg.1
0x20f70  box      [mscorlib]System.Guid
0x20f75  stelem.ref
0x20f76  ldloc.s  0x19
0x20f78  ldc.i4.1
0x20f79  ldloc.0
0x20f7a  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_DisplayName()
0x20f7f  stelem.ref
0x20f80  ldloc.s  0x19
0x20f82  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x20f87  leave    loc_21300
0x20f8c  leave.s  loc_20F9A
0x20f8e  ldloc.s  0x14
0x20f90  brfalse.s loc_20F99
0x20f92  ldloc.s  0x18
0x20f94  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x20f99  endfinally
0x20f9a  ldloc.s  5
0x20f9c  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x20fa1  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x20fa6  brfalse  loc_21131
0x20fab  ldarg.1
0x20fac  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x20fb1  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x20fb6  brfalse.s loc_20FEE
0x20fb8  ldc.i4   0x78C885
0x20fbd  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x20fc2  ldc.i4.s 0x32
0x20fc4  ldstr    aCallingGetchan// "Calling GetChangesForDatabase on servic"...
0x20fc9  ldc.i4.2
0x20fca  newarr   [mscorlib]System.Object
0x20fcf  stloc.s  0x1A
0x20fd1  ldloc.s  0x1A
0x20fd3  ldc.i4.0
0x20fd4  ldloc.0
0x20fd5  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_DisplayName()
0x20fda  stelem.ref
0x20fdb  ldloc.s  0x1A
0x20fdd  ldc.i4.1
0x20fde  ldarg.2
0x20fdf  box      [mscorlib]System.Boolean
0x20fe4  stelem.ref
0x20fe5  ldloc.s  0x1A
0x20fe7  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x20fec  br.s     loc_2102C
0x20fee  ldc.i4   0x78C886
0x20ff3  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x20ff8  ldc.i4.s 0x32
0x20ffa  ldstr    aCallingGetchan_0// "Calling GetChangesForDatabase on Conten"...
0x20fff  ldc.i4.3
0x21000  newarr   [mscorlib]System.Object
0x21005  stloc.s  0x1B
0x21007  ldloc.s  0x1B
0x21009  ldc.i4.0
0x2100a  ldarg.1
0x2100b  box      [mscorlib]System.Guid
0x21010  stelem.ref
0x21011  ldloc.s  0x1B
0x21013  ldc.i4.1
0x21014  ldloc.0
0x21015  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_DisplayName()
0x2101a  stelem.ref
0x2101b  ldloc.s  0x1B
0x2101d  ldc.i4.2
0x2101e  ldarg.2
0x2101f  box      [mscorlib]System.Boolean
0x21024  stelem.ref
0x21025  ldloc.s  0x1B
0x21027  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x2102c  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x21031  stloc.s  0xB
0x21033  ldloc.s  8
0x21035  ldarg.1
0x21036  ldloc.s  5
0x21038  call     valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.Internal.CommonValidator::GetValidDBTime(valuetype [mscorlib]System.DateTime time)
0x2103d  ldloca.s 0x1C
0x2103f  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x21045  ldloc.s  0x1C
0x21047  ldloca.s 0x1D
0x21049  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x2104f  ldloc.s  0x1D
0x21051  ldloca.s 0x1E
0x21053  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.Taxonomy.ChangedItemType>
0x21059  ldloc.s  0x1E
0x2105b  ldloca.s 0x1F
0x2105d  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.Taxonomy.ChangedOperationType>
0x21063  ldloc.s  0x1F
0x21065  ldarg.2
0x21066  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x2106b  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.ChangedItem> Microsoft.SharePoint.Taxonomy.Internal.DataAccessManager::GetChangesForDatabase(valuetype [mscorlib]System.Guid contentDatabaseId, valuetype [mscorlib]System.DateTime sinceTime, valuetype [mscorlib]System.Nullable`1<int32> groupId, valuetype [mscorlib]System.Nullable`1<int32> termSetId, valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.Taxonomy.ChangedItemType> changedItemType, valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.Taxonomy.ChangedOperationType> changedOperationType, valuetype [mscorlib]System.Nullable`1<bool> enforceUpdate)
0x21070  stloc.s  0xC
0x21072  ldloc.s  0xB
0x21074  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x21079  ldloc.s  0xC
0x2107b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.ChangedItem>::get_Count()
0x21080  ldc.i4.0
0x21081  ble      loc_2118C
0x21086  ldloc.s  0xA
0x21088  ldloc.s  0xC
0x2108a  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.ChangedItem>::get_Count()
0x2108f  add.ovf
0x21090  stloc.s  0xA
0x21092  ldarg.0
0x21093  call     instance class [mscorlib]System.Threading.ReaderWriterLock Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::get_DataLock()
0x21098  ldc.i4.m1
0x21099  callvirt instance void [mscorlib]System.Threading.ReaderWriterLock::AcquireWriterLock(int32)
0x2109e  ldarg.0
0x2109f  ldloc.s  0xC
0x210a1  call     instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::InvalidateCacheWhileLocked(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.ChangedItem> changedItems)
0x210a6  stloc.s  0xD
0x210a8  leave.s  loc_210B6
0x210aa  ldarg.0
0x210ab  call     instance class [mscorlib]System.Threading.ReaderWriterLock Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::get_DataLock()
0x210b0  callvirt instance void [mscorlib]System.Threading.ReaderWriterLock::ReleaseWriterLock()
0x210b5  endfinally
0x210b6  ldc.i4.0
0x210b7  stloc.s  0xE
0x210b9  ldloc.1
0x210ba  ldfld    object TrackedDatabase::AccessLock
0x210bf  dup
0x210c0  stloc.s  0x20
0x210c2  ldloca.s 0xE
0x210c4  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x210c9  ldloc.1
0x210ca  ldloc.s  0xD
0x210cc  stfld    valuetype [mscorlib]System.DateTime TrackedDatabase::LastChangeTime
0x210d1  leave.s  loc_210DF
0x210d3  ldloc.s  0xE
0x210d5  brfalse.s loc_210DE
0x210d7  ldloc.s  0x20
0x210d9  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x210de  endfinally
0x210df  ldstr    aTaxonomyFoundc_0// "Taxonomy_FoundChangesForCache2"
0x210e4  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x210e9  stloc.s  0xF
0x210eb  ldloc.s  0xF
0x210ed  ldstr    aContentdatabas_1// "ContentDatabaseId"
0x210f2  ldarg.1
0x210f3  box      [mscorlib]System.Guid
0x210f8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x210fd  ldloc.s  0xF
0x210ff  ldstr    aChangecount// "ChangeCount"
0x21104  ldloc.s  0xA
0x21106  box      [mscorlib]System.Int32
0x2110b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x21110  ldloc.s  0xF
0x21112  ldstr    aDurationms// "DurationMs"
0x21117  ldloc.s  0xB
0x21119  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x2111e  box      [mscorlib]System.Int64
0x21123  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x21128  ldloc.s  0xF
0x2112a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPUserEngagement::WriteDiagnosticEvent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x2112f  br.s     loc_2118C
0x21131  ldc.i4   0x78C887
0x21136  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x2113b  ldc.i4.s 0x32
0x2113d  ldstr    aCallingGetchan_1// "Calling GetChangeTimeForDatabase with C"...
0x21142  ldc.i4.3
0x21143  newarr   [mscorlib]System.Object
0x21148  stloc.s  0x21
0x2114a  ldloc.s  0x21
0x2114c  ldc.i4.0
0x2114d  ldarg.1
0x2114e  box      [mscorlib]System.Guid
  ... truncated ...
```
