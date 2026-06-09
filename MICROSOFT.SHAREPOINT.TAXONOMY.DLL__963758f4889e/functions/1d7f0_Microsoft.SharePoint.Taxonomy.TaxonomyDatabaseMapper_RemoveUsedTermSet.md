# Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::RemoveUsedTermSet

- ea: `0x1d7f0`
- end: `0x1d833`
- name: `Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::RemoveUsedTermSet`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x64030`

## callees

- `0x1a590`
- `0x1b420`
- `0x1b440`
- `0x1d7f0`
- `0x1e030`
- `0x1e1d0`
- `0x1e210`
- `0x1e2c0`

## string_xrefs

- `0x1d7f1`: `RemoveUsedTermSet`
- `0x1d827`: `RemoveUsedTermSet`

## pseudocode

```c

```

## disassembly

```asm
0x1d7f0  ldarg.0
0x1d7f1  ldstr    aRemoveusedterm// "RemoveUsedTermSet"
0x1d7f6  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::SendTraceStart(string function)
0x1d7fb  ldarg.0
0x1d7fc  call     instance class Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::get_DatabaseMapperContext()
0x1d801  ldc.i4   0x4000
0x1d806  conv.i8
0x1d807  callvirt instance void Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext::CheckPermission(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.AccessControl.SPIisWebServiceApplicationRights requiredPermissions)
0x1d80c  ldarg.0
0x1d80d  ldarg.1
0x1d80e  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::ResolvePartitionId(valuetype [mscorlib]System.Guid rawPartitionId)
0x1d813  stloc.0
0x1d814  ldarg.0
0x1d815  ldloc.0
0x1d816  call     instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapter Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::GetAdapterForPartition(valuetype [mscorlib]System.Guid resolvedPartitionId)
0x1d81b  stloc.1
0x1d81c  ldloc.1
0x1d81d  ldloc.0
0x1d81e  ldarg.2
0x1d81f  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadWrite::RemoveUsedTermSet(valuetype [mscorlib]System.Guid partitionId, valuetype [mscorlib]System.Guid termSetId)
0x1d824  leave.s  loc_1D832
0x1d826  ldarg.0
0x1d827  ldstr    aRemoveusedterm// "RemoveUsedTermSet"
0x1d82c  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::SendTraceEnd(string function)
0x1d831  endfinally
0x1d832  ret
```
