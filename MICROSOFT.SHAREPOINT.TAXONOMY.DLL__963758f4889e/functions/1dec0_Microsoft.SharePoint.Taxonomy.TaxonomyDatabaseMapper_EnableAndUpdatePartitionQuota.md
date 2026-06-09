# Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::EnableAndUpdatePartitionQuota

- ea: `0x1dec0`
- end: `0x1df2b`
- name: `Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::EnableAndUpdatePartitionQuota`
- size: `107`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3b1c0`
- `0x3b800`

## callees

- `0x1ae40`
- `0x1b420`
- `0x1b510`
- `0x1e280`

## string_xrefs

- `0x1decc`: `EnableAndUpdatePartitionQuota on service app: '{0}' started.`
- `0x1df0a`: `EnableAndUpdatePartitionQuota on service app: '{0}' ended.`

## pseudocode

```c

```

## disassembly

```asm
0x1dec0  ldc.i4   0x1DB45A
0x1dec5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1deca  ldc.i4.s 0x32
0x1decc  ldstr    aEnableandupdat// "EnableAndUpdatePartitionQuota on servic"...
0x1ded1  ldc.i4.1
0x1ded2  newarr   [mscorlib]System.Object
0x1ded7  stloc.0
0x1ded8  ldloc.0
0x1ded9  ldc.i4.0
0x1deda  ldarg.0
0x1dedb  call     instance class Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::get_DatabaseMapperContext()
0x1dee0  callvirt instance string Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext::get_Name()
0x1dee5  stelem.ref
0x1dee6  ldloc.0
0x1dee7  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x1deec  ldarg.0
0x1deed  call     instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapter Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::GetAdapterForServiceDatabase()
0x1def2  ldarg.1
0x1def3  ldarg.2
0x1def4  ldarg.3
0x1def5  ldarg.s  4
0x1def7  ldarg.s  5
0x1def9  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadWrite::EnableAndUpdatePartitionQuota(int32 groupsPerPartition, int32 termSetsPerPartition, int32 termsPerPartition, int32 labelsPerPartition, int32 propertiesPerPartition)
0x1defe  ldc.i4   0x1DB45B
0x1df03  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1df08  ldc.i4.s 0x32
0x1df0a  ldstr    aEnableandupdat_0// "EnableAndUpdatePartitionQuota on servic"...
0x1df0f  ldc.i4.1
0x1df10  newarr   [mscorlib]System.Object
0x1df15  stloc.1
0x1df16  ldloc.1
0x1df17  ldc.i4.0
0x1df18  ldarg.0
0x1df19  call     instance class Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::get_DatabaseMapperContext()
0x1df1e  callvirt instance string Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext::get_Name()
0x1df23  stelem.ref
0x1df24  ldloc.1
0x1df25  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x1df2a  ret
```
