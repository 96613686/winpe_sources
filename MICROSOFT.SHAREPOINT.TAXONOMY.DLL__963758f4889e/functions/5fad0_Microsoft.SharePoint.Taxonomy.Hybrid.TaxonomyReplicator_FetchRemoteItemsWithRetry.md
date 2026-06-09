# Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyReplicator::FetchRemoteItemsWithRetry

- ea: `0x5fad0`
- end: `0x5fbea`
- name: `Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyReplicator::FetchRemoteItemsWithRetry`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x5f940`

## callees

- `0x2acd0`
- `0x58330`
- `0x59f80`
- `0x59fd0`
- `0x5e8c0`
- `0x5fad0`

## string_xrefs

- `0x5fae9`: `Fetching items attempts {0}. Batch size {1}.`
- `0x5fbd5`: `TaxonomyOnlineServiceUnavailable`

## pseudocode

```c

```

## disassembly

```asm
0x5fad0  ldc.i4.1
0x5fad1  stloc.0
0x5fad2  ldc.i4   0x100
0x5fad7  stloc.1
0x5fad8  br       loc_5FBCD
0x5fadd  ldc.i4   0x12DB605
0x5fae2  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x5fae7  ldc.i4.s 0x14
0x5fae9  ldstr    aFetchingItemsA// "Fetching items attempts {0}. Batch size"...
0x5faee  ldc.i4.2
0x5faef  newarr   [mscorlib]System.Object
0x5faf4  stloc.s  8
0x5faf6  ldloc.s  8
0x5faf8  ldc.i4.0
0x5faf9  ldloc.0
0x5fafa  box      [mscorlib]System.Int32
0x5faff  stelem.ref
0x5fb00  ldloc.s  8
0x5fb02  ldc.i4.1
0x5fb03  ldloc.1
0x5fb04  box      [mscorlib]System.Int32
0x5fb09  stelem.ref
0x5fb0a  ldloc.s  8
0x5fb0c  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x5fb11  ldarg.1
0x5fb12  ldloc.1
0x5fb13  call     class Microsoft.SharePoint.Taxonomy.Hybrid.IFetchItemsAlgorithm Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::GetFetchItemsAlgorithm(bool isIncremental, int32 batchSize)
0x5fb18  stloc.2
0x5fb19  ldloc.2
0x5fb1a  isinst   Microsoft.SharePoint.Taxonomy.Hybrid.FetchIncrementalItemsAlgorithm
0x5fb1f  stloc.3
0x5fb20  ldloc.3
0x5fb21  brfalse.s loc_5FB34
0x5fb23  ldloc.3
0x5fb24  ldarg.0
0x5fb25  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.LocalService Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyReplicator::localService
0x5fb2a  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Hybrid.LocalService::get_LocalTermSetIds()
0x5fb2f  callvirt instance void Microsoft.SharePoint.Taxonomy.Hybrid.FetchIncrementalItemsAlgorithm::set_LocalTermSetIds(class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> value)
0x5fb34  ldarg.0
0x5fb35  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyReplicator::remoteService
0x5fb3a  ldloc.2
0x5fb3b  ldarg.2
0x5fb3c  ldarg.s  4
0x5fb3e  ldarg.3
0x5fb3f  callvirt instance class Microsoft.SharePoint.Taxonomy.Hybrid.RemoteDataPack Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::FetchTaxonomyItems(class Microsoft.SharePoint.Taxonomy.Hybrid.IFetchItemsAlgorithm fetchItemsAlgorithm, bool fullProperties, valuetype [mscorlib]System.DateTime lastReplicationTime, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> targetGroupIds)
0x5fb44  stloc.s  4
0x5fb46  ldloc.s  4
0x5fb48  stloc.s  7
0x5fb4a  leave    loc_5FBE7
0x5fb4f  stloc.s  5
0x5fb51  ldloc.s  5
0x5fb53  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x5fb58  isinst   [System]System.Net.HttpWebResponse
0x5fb5d  stloc.s  6
0x5fb5f  ldloc.s  6
0x5fb61  brfalse.s loc_5FBC9
0x5fb63  ldloc.s  6
0x5fb65  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0x5fb6a  ldc.i4   0x1AD
0x5fb6f  beq.s    loc_5FB7F
0x5fb71  ldloc.s  6
0x5fb73  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0x5fb78  ldc.i4   0x1F7
0x5fb7d  bne.un.s loc_5FBC9
0x5fb7f  ldc.i4   0x12DB606
0x5fb84  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x5fb89  ldc.i4.s 0x14
0x5fb8b  ldstr    aReplicationCso// "Replication CSOM request was throttled "...
0x5fb90  ldc.i4.1
0x5fb91  newarr   [mscorlib]System.Object
0x5fb96  stloc.s  9
0x5fb98  ldloc.s  9
0x5fb9a  ldc.i4.0
0x5fb9b  ldloc.s  6
0x5fb9d  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0x5fba2  box      [System]System.Net.HttpStatusCode
0x5fba7  callvirt instance string [mscorlib]System.Object::ToString()
0x5fbac  stelem.ref
0x5fbad  ldloc.s  9
0x5fbaf  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x5fbb4  ldloc.1
0x5fbb5  ldc.i4.2
0x5fbb6  div
0x5fbb7  ldc.i4.s 0x10
0x5fbb9  blt.s    loc_5FBC0
0x5fbbb  ldloc.1
0x5fbbc  ldc.i4.2
0x5fbbd  div
0x5fbbe  br.s     loc_5FBC2
0x5fbc0  ldc.i4.s 0x10
0x5fbc2  stloc.1
0x5fbc3  ldloc.0
0x5fbc4  ldc.i4.1
0x5fbc5  add.ovf
0x5fbc6  stloc.0
0x5fbc7  br.s     loc_5FBCB
0x5fbc9  rethrow
0x5fbcb  leave.s  loc_5FBCD
0x5fbcd  ldloc.0
0x5fbce  ldarg.s  5
0x5fbd0  ble      loc_5FADD
0x5fbd5  ldstr    aTaxonomyonline// "TaxonomyOnlineServiceUnavailable"
0x5fbda  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x5fbdf  ldc.i4.s 0xFE
0x5fbe1  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPException::.ctor(string, int32)
0x5fbe6  throw
0x5fbe7  ldloc.s  7
0x5fbe9  ret
```
