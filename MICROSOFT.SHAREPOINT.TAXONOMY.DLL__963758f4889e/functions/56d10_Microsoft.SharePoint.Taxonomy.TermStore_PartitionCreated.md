# Microsoft.SharePoint.Taxonomy.TermStore::PartitionCreated

- ea: `0x56d10`
- end: `0x56deb`
- name: `Microsoft.SharePoint.Taxonomy.TermStore::PartitionCreated`
- size: `219`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x53d60`
- `0x56c90`

## callees

- `0x26930`
- `0x293c0`
- `0x56a80`
- `0x56ab0`
- `0x56d10`

## string_xrefs

- `0x56d1c`: `Begin: TermStore.PartitionCreated`
- `0x56d3c`: `TermStore.PartitionCreated: loading the assembly Microsoft.Office.Server.Search.dll`
- `0x56d5b`: `Could not get INotificationHandler interface of MetadataServiceNotificationHandler.`
- `0x56d73`: `TermStore.PartitionCreated: invoking Search INotificationHandler with elevated privileges`
- `0x56dab`: `TermStore.PartitionCreated: failure when calling SearchProvisionUtils.ProvisionOOBSearchTermSets. Proceed without blocking taxonomy store initialization. [Exception = {0}]`
- `0x56de0`: `End: TermStore.PartitionCreated`

## pseudocode

```c

```

## disassembly

```asm
0x56d10  ldc.i4   0xDA2D8
0x56d15  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x56d1a  ldc.i4.s 0x14
0x56d1c  ldstr    aBeginTermstore_13// "Begin: TermStore.PartitionCreated"
0x56d21  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x56d26  ldc.i4.0
0x56d27  stloc.0
0x56d28  ldarg.0
0x56d29  ldloca.s 0
0x56d2b  call     instance void Microsoft.SharePoint.Taxonomy.TermStore::RunWithElevation(bool& shouldRevert)
0x56d30  ldc.i4   0xDA2D9
0x56d35  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x56d3a  ldc.i4.s 0x14
0x56d3c  ldstr    aTermstoreParti// "TermStore.PartitionCreated: loading the"...
0x56d41  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x56d46  newobj   instance void [Microsoft.Office.Server.Search]Microsoft.Office.Server.Search.Administration.MetadataServiceNotificationHandler::.ctor()
0x56d4b  stloc.1
0x56d4c  ldloc.1
0x56d4d  brtrue.s loc_56D67
0x56d4f  ldc.i4   0x218108
0x56d54  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x56d59  ldc.i4.s 0x14
0x56d5b  ldstr    aCouldNotGetIno// "Could not get INotificationHandler inte"...
0x56d60  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x56d65  br.s     loc_56D84
0x56d67  ldc.i4   0x11A354
0x56d6c  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x56d71  ldc.i4.s 0x14
0x56d73  ldstr    aTermstoreParti_0// "TermStore.PartitionCreated: invoking Se"...
0x56d78  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x56d7d  ldloc.1
0x56d7e  ldarg.0
0x56d7f  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.INotificationHandler::TermStorePartitionCreated(class Microsoft.SharePoint.Taxonomy.TermStore store)
0x56d84  ldc.i4   0x2B22
0x56d89  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x56d8e  brfalse.s loc_56D9C
0x56d90  ldarg.0
0x56d91  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.DataAccessManager Microsoft.SharePoint.Taxonomy.TermStore::dataAccessManager
0x56d96  ldc.i4.1
0x56d97  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.DataAccessManager::SetSearchNotified(bool isSearchNotified)
0x56d9c  leave.s  loc_56DC8
0x56d9e  stloc.2
0x56d9f  ldc.i4   0x11A355
0x56da4  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x56da9  ldc.i4.s 0x14
0x56dab  ldstr    aTermstoreParti_1// "TermStore.PartitionCreated: failure whe"...
0x56db0  ldc.i4.1
0x56db1  newarr   [mscorlib]System.Object
0x56db6  stloc.3
0x56db7  ldloc.3
0x56db8  ldc.i4.0
0x56db9  ldloc.2
0x56dba  callvirt instance string [mscorlib]System.Exception::get_Message()
0x56dbf  stelem.ref
0x56dc0  ldloc.3
0x56dc1  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x56dc6  leave.s  loc_56DC8
0x56dc8  leave.s  loc_56DD4
0x56dca  ldloc.0
0x56dcb  brfalse.s loc_56DD3
0x56dcd  ldarg.0
0x56dce  call     instance void Microsoft.SharePoint.Taxonomy.TermStore::RevertElevation()
0x56dd3  endfinally
0x56dd4  ldc.i4   0xDA2DA
0x56dd9  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x56dde  ldc.i4.s 0x14
0x56de0  ldstr    aEndTermstorePa// "End: TermStore.PartitionCreated"
0x56de5  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x56dea  ret
```
