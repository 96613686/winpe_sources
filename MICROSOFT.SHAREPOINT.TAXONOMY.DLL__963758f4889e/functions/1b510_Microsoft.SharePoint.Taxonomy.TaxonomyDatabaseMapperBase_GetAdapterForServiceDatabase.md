# Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::GetAdapterForServiceDatabase

- ea: `0x1b510`
- end: `0x1b55a`
- name: `Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::GetAdapterForServiceDatabase`
- size: `74`
- prototype: ``
- caller_count: `10`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1b430`
- `0x1b440`
- `0x1b580`
- `0x1bd00`
- `0x1cd80`
- `0x1ce30`
- `0x1d840`
- `0x1de50`
- `0x1dec0`
- `0x1e000`

## callees

- `0x1b420`
- `0x1b510`
- `0x1b560`
- `0x1e290`
- `0x2acd0`
- `0x579b0`

## string_xrefs

- `0x1b539`: `DatabaseMapperNoServiceDatabase`
- `0x1b52f`: `Configuration problem:  The taxonomy service database is missing`

## pseudocode

```c

```

## disassembly

```asm
0x1b510  ldarg.0
0x1b511  call     instance class Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::get_DatabaseMapperContext()
0x1b516  callvirt instance class Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext::get_Database()
0x1b51b  ldnull
0x1b51c  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x1b521  brfalse.s loc_1B549
0x1b523  ldc.i4   0x681692
0x1b528  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1b52d  ldc.i4.s 0x14
0x1b52f  ldstr    aConfigurationP// "Configuration problem:  The taxonomy se"...
0x1b534  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x1b539  ldstr    aDatabasemapper_0// "DatabaseMapperNoServiceDatabase"
0x1b53e  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x1b543  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x1b548  throw
0x1b549  ldarg.0
0x1b54a  call     instance class Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::get_DatabaseMapperContext()
0x1b54f  callvirt instance class Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext::get_Database()
0x1b554  call     class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapter Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::GetAdapterForServiceDatabase(class Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase database)
0x1b559  ret
```
