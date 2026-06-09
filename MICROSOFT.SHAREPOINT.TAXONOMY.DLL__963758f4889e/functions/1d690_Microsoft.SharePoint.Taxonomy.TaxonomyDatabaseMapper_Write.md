# Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::Write

- ea: `0x1d690`
- end: `0x1d6f6`
- name: `Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::Write`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x63fc0`

## callees

- `0x1a330`
- `0x1b420`
- `0x1b440`
- `0x1d690`
- `0x1e030`
- `0x1e1d0`
- `0x1e210`
- `0x1e2c0`
- `0x1e2d0`
- `0x33ca0`

## string_xrefs

- `0x1d691`: `Write`
- `0x1d6ea`: `Write`

## pseudocode

```c

```

## disassembly

```asm
0x1d690  ldarg.0
0x1d691  ldstr    aWrite// "Write"
0x1d696  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::SendTraceStart(string function)
0x1d69b  ldarg.0
0x1d69c  call     instance class Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::get_DatabaseMapperContext()
0x1d6a1  ldc.i4   0x2000
0x1d6a6  conv.i8
0x1d6a7  callvirt instance void Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext::CheckPermission(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.AccessControl.SPIisWebServiceApplicationRights requiredPermissions)
0x1d6ac  ldarg.0
0x1d6ad  call     instance class Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::get_DatabaseMapperContext()
0x1d6b2  ldc.i4   0x4000
0x1d6b7  conv.i8
0x1d6b8  callvirt instance bool Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext::DoesUserHavePermissions(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.AccessControl.SPIisWebServiceApplicationRights requiredPermissions)
0x1d6bd  ldc.i4.0
0x1d6be  ceq
0x1d6c0  stloc.0
0x1d6c1  ldarg.1
0x1d6c2  call     valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ParseRawPartitionId(string xmlData)
0x1d6c7  stloc.1
0x1d6c8  ldarg.0
0x1d6c9  ldloc.1
0x1d6ca  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::ResolvePartitionId(valuetype [mscorlib]System.Guid rawPartitionId)
0x1d6cf  stloc.2
0x1d6d0  ldarg.0
0x1d6d1  ldloc.2
0x1d6d2  call     instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapter Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::GetAdapterForPartition(valuetype [mscorlib]System.Guid resolvedPartitionId)
0x1d6d7  stloc.3
0x1d6d8  ldloc.3
0x1d6d9  ldloc.2
0x1d6da  ldarg.1
0x1d6db  ldloc.0
0x1d6dc  ldarg.0
0x1d6dd  call     instance class Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::get_DatabaseMapperContext()
0x1d6e2  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadWrite::Write(valuetype [mscorlib]System.Guid resolvedPartitionId, string xmlData, bool isRestrictedWrite, class Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext databaseMapperContext)
0x1d6e7  leave.s  loc_1D6F5
0x1d6e9  ldarg.0
0x1d6ea  ldstr    aWrite// "Write"
0x1d6ef  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::SendTraceEnd(string function)
0x1d6f4  endfinally
0x1d6f5  ret
```
