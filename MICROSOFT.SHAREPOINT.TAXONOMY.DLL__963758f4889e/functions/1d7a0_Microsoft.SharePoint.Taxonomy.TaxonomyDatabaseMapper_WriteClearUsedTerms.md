# Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::WriteClearUsedTerms

- ea: `0x1d7a0`
- end: `0x1d7e6`
- name: `Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::WriteClearUsedTerms`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x64010`

## callees

- `0x1a6b0`
- `0x1b420`
- `0x1b440`
- `0x1d7a0`
- `0x1e030`
- `0x1e1d0`
- `0x1e210`
- `0x1e2c0`

## string_xrefs

- `0x1d7a1`: `WriteClearUsedTerms`
- `0x1d7da`: `WriteClearUsedTerms`

## pseudocode

```c

```

## disassembly

```asm
0x1d7a0  ldarg.0
0x1d7a1  ldstr    aWriteclearused// "WriteClearUsedTerms"
0x1d7a6  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::SendTraceStart(string function)
0x1d7ab  ldarg.0
0x1d7ac  call     instance class Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::get_DatabaseMapperContext()
0x1d7b1  ldc.i4   0x1000
0x1d7b6  conv.i8
0x1d7b7  callvirt instance void Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext::CheckPermission(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.AccessControl.SPIisWebServiceApplicationRights requiredPermissions)
0x1d7bc  ldarg.0
0x1d7bd  ldarg.1
0x1d7be  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::ResolvePartitionId(valuetype [mscorlib]System.Guid rawPartitionId)
0x1d7c3  stloc.0
0x1d7c4  ldarg.0
0x1d7c5  ldloc.0
0x1d7c6  call     instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapter Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::GetAdapterForPartition(valuetype [mscorlib]System.Guid resolvedPartitionId)
0x1d7cb  stloc.1
0x1d7cc  ldloc.1
0x1d7cd  ldloc.0
0x1d7ce  ldarg.2
0x1d7cf  ldarg.3
0x1d7d0  ldarg.s  4
0x1d7d2  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadWrite::WriteClearUsedTerms(valuetype [mscorlib]System.Guid partitionId, valuetype [mscorlib]System.Guid webAppId, valuetype [mscorlib]System.Guid contentDatabaseId, valuetype [mscorlib]System.Guid siteId)
0x1d7d7  leave.s  loc_1D7E5
0x1d7d9  ldarg.0
0x1d7da  ldstr    aWriteclearused// "WriteClearUsedTerms"
0x1d7df  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::SendTraceEnd(string function)
0x1d7e4  endfinally
0x1d7e5  ret
```
