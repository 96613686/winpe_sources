# Microsoft.SharePoint.Taxonomy.Internal.PartitionExportImport::Import

- ea: `0x2a240`
- end: `0x2a339`
- name: `Microsoft.SharePoint.Taxonomy.Internal.PartitionExportImport::Import`
- size: `249`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1c4b0`
- `0x1c500`

## callees

- `0x177d0`
- `0x2a240`
- `0x735b0`
- `0x735d0`

## string_xrefs

- `0x2a2ec`: `NoCompression`
- `0x2a2d6`: `OverwriteExisting`

## pseudocode

```c

```

## disassembly

```asm
0x2a240  newobj   instance void <>c__DisplayClass9::.ctor()
0x2a245  stloc.3
0x2a246  ldloc.3
0x2a247  ldarg.0
0x2a248  stfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapter <>c__DisplayClass9::databaseAdapter
0x2a24d  ldloc.3
0x2a24e  ldarg.1
0x2a24f  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass9::partitionId
0x2a254  ldloc.3
0x2a255  ldarg.2
0x2a256  stfld    string <>c__DisplayClass9::path
0x2a25b  ldloc.3
0x2a25c  ldarg.3
0x2a25d  stfld    bool <>c__DisplayClass9::overwriteExisting
0x2a262  ldloc.3
0x2a263  ldarg.s  4
0x2a265  stfld    bool <>c__DisplayClass9::noCompression
0x2a26a  ldnull
0x2a26b  stloc.1
0x2a26c  newobj   instance void <>c__DisplayClassc::.ctor()
0x2a271  stloc.2
0x2a272  ldloc.2
0x2a273  ldloc.3
0x2a274  stfld    class <>c__DisplayClass9 <>c__DisplayClassc::CS$<>8__localsa
0x2a279  ldloc.2
0x2a27a  ldstr    aTaxonomyPartit_0// "Taxonomy Partition Import"
0x2a27f  ldc.i4   0x78035D
0x2a284  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x2a289  ldc.i4   0x78035E
0x2a28e  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x2a293  ldc.i4   0x78035F
0x2a298  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x2a29d  ldc.i4.0
0x2a29e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x2a2a3  stloc.0
0x2a2a4  ldloc.0
0x2a2a5  ldstr    aPartitionid_1// "PartitionId"
0x2a2aa  ldloc.3
0x2a2ab  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass9::partitionId
0x2a2b0  box      [mscorlib]System.Guid
0x2a2b5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2a2ba  ldloc.0
0x2a2bb  ldstr    aContentdatabas_1// "ContentDatabaseId"
0x2a2c0  ldloc.3
0x2a2c1  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapter <>c__DisplayClass9::databaseAdapter
0x2a2c6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase::get_ContentDatabaseId()
0x2a2cb  box      [mscorlib]System.Guid
0x2a2d0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2a2d5  ldloc.0
0x2a2d6  ldstr    aOverwriteexist// "OverwriteExisting"
0x2a2db  ldloc.3
0x2a2dc  ldfld    bool <>c__DisplayClass9::overwriteExisting
0x2a2e1  box      [mscorlib]System.Boolean
0x2a2e6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2a2eb  ldloc.0
0x2a2ec  ldstr    aNocompression// "NoCompression"
0x2a2f1  ldloc.3
0x2a2f2  ldfld    bool <>c__DisplayClass9::noCompression
0x2a2f7  box      [mscorlib]System.Boolean
0x2a2fc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2a301  ldloc.0
0x2a302  newobj   instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitor::.ctor(string, unsigned int32, unsigned int32, unsigned int32, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPLogType, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x2a307  stfld    class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitor <>c__DisplayClassc::monitor
0x2a30c  ldloc.1
0x2a30d  brtrue.s loc_2A31C
0x2a30f  ldloc.2
0x2a310  ldftn    instance void <>c__DisplayClassc::<Import>b__8()
0x2a316  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSecurity/CodeToRunElevated::.ctor(object, native int)
0x2a31b  stloc.1
0x2a31c  ldloc.1
0x2a31d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.SPSecurity::RunWithElevatedPrivileges(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSecurity/CodeToRunElevated)
0x2a322  leave.s  loc_2A338
0x2a324  ldloc.2
0x2a325  ldfld    class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitor <>c__DisplayClassc::monitor
0x2a32a  brfalse.s loc_2A337
0x2a32c  ldloc.2
0x2a32d  ldfld    class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitor <>c__DisplayClassc::monitor
0x2a332  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a337  endfinally
0x2a338  ret
```
