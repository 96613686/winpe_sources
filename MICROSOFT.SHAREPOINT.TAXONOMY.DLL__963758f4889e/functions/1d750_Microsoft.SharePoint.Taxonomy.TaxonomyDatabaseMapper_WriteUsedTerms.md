# Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::WriteUsedTerms

- ea: `0x1d750`
- end: `0x1d79a`
- name: `Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::WriteUsedTerms`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x63ff0`

## callees

- `0x1a630`
- `0x1b420`
- `0x1b440`
- `0x1d750`
- `0x1e030`
- `0x1e1d0`
- `0x1e210`
- `0x1e2c0`

## string_xrefs

- `0x1d751`: `WriteUsedTerms`
- `0x1d78e`: `WriteUsedTerms`

## pseudocode

```c

```

## disassembly

```asm
0x1d750  ldarg.0
0x1d751  ldstr    aWriteusedterms// "WriteUsedTerms"
0x1d756  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::SendTraceStart(string function)
0x1d75b  ldarg.0
0x1d75c  call     instance class Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::get_DatabaseMapperContext()
0x1d761  ldc.i4   0x1000
0x1d766  conv.i8
0x1d767  callvirt instance void Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext::CheckPermission(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.AccessControl.SPIisWebServiceApplicationRights requiredPermissions)
0x1d76c  ldarg.0
0x1d76d  ldarg.1
0x1d76e  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::ResolvePartitionId(valuetype [mscorlib]System.Guid rawPartitionId)
0x1d773  stloc.0
0x1d774  ldarg.0
0x1d775  ldloc.0
0x1d776  call     instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapter Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::GetAdapterForPartition(valuetype [mscorlib]System.Guid resolvedPartitionId)
0x1d77b  stloc.1
0x1d77c  ldloc.1
0x1d77d  ldloc.0
0x1d77e  ldarg.2
0x1d77f  ldarg.3
0x1d780  ldarg.s  4
0x1d782  ldarg.s  5
0x1d784  ldarg.s  6
0x1d786  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadWrite::WriteUsedTerms(valuetype [mscorlib]System.Guid partitionId, valuetype [mscorlib]System.Guid webAppId, valuetype [mscorlib]System.Guid contentDatabaseId, valuetype [mscorlib]System.Guid siteId, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> termSetIds, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> termIds)
0x1d78b  leave.s  loc_1D799
0x1d78d  ldarg.0
0x1d78e  ldstr    aWriteusedterms// "WriteUsedTerms"
0x1d793  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::SendTraceEnd(string function)
0x1d798  endfinally
0x1d799  ret
```
