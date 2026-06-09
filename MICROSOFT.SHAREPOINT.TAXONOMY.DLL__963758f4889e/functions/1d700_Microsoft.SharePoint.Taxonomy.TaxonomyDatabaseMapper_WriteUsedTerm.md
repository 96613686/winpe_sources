# Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::WriteUsedTerm

- ea: `0x1d700`
- end: `0x1d74a`
- name: `Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::WriteUsedTerm`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x63fd0`

## callees

- `0x1a5e0`
- `0x1b420`
- `0x1b440`
- `0x1d700`
- `0x1e030`
- `0x1e1d0`
- `0x1e210`
- `0x1e2c0`

## string_xrefs

- `0x1d701`: `WriteUsedTerm`
- `0x1d73e`: `WriteUsedTerm`

## pseudocode

```c

```

## disassembly

```asm
0x1d700  ldarg.0
0x1d701  ldstr    aWriteusedterm// "WriteUsedTerm"
0x1d706  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::SendTraceStart(string function)
0x1d70b  ldarg.0
0x1d70c  call     instance class Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::get_DatabaseMapperContext()
0x1d711  ldc.i4   0x1000
0x1d716  conv.i8
0x1d717  callvirt instance void Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext::CheckPermission(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.AccessControl.SPIisWebServiceApplicationRights requiredPermissions)
0x1d71c  ldarg.0
0x1d71d  ldarg.1
0x1d71e  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::ResolvePartitionId(valuetype [mscorlib]System.Guid rawPartitionId)
0x1d723  stloc.0
0x1d724  ldarg.0
0x1d725  ldloc.0
0x1d726  call     instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapter Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::GetAdapterForPartition(valuetype [mscorlib]System.Guid resolvedPartitionId)
0x1d72b  stloc.1
0x1d72c  ldloc.1
0x1d72d  ldloc.0
0x1d72e  ldarg.2
0x1d72f  ldarg.3
0x1d730  ldarg.s  4
0x1d732  ldarg.s  5
0x1d734  ldarg.s  6
0x1d736  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadWrite::WriteUsedTerm(valuetype [mscorlib]System.Guid partitionId, valuetype [mscorlib]System.Guid webAppId, valuetype [mscorlib]System.Guid contentDatabaseId, valuetype [mscorlib]System.Guid siteId, valuetype [mscorlib]System.Guid termSetId, valuetype [mscorlib]System.Guid termId)
0x1d73b  leave.s  loc_1D749
0x1d73d  ldarg.0
0x1d73e  ldstr    aWriteusedterm// "WriteUsedTerm"
0x1d743  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::SendTraceEnd(string function)
0x1d748  endfinally
0x1d749  ret
```
