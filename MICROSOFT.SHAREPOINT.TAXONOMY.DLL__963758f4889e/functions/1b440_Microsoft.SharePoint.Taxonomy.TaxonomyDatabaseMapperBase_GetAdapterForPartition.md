# Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::GetAdapterForPartition

- ea: `0x1b440`
- end: `0x1b503`
- name: `Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::GetAdapterForPartition`
- size: `195`
- prototype: ``
- caller_count: `44`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1bc50`
- `0x1beb0`
- `0x1c080`
- `0x1c0a0`
- `0x1c150`
- `0x1c1e0`
- `0x1c240`
- `0x1c2c0`
- `0x1c330`
- `0x1c3a0`
- `0x1c3e0`
- `0x1c450`
- `0x1c4b0`
- `0x1c550`
- `0x1c660`
- `0x1c770`
- `0x1c8b0`
- `0x1cb00`
- `0x1cb50`
- `0x1cba0`
- `0x1cbf0`
- `0x1cc40`
- `0x1cc90`
- `0x1cce0`
- `0x1cd30`
- `0x1cd80`
- `0x1cea0`
- `0x1d080`
- `0x1d190`
- `0x1d260`
- `0x1d3a0`
- `0x1d4d0`
- `0x1d520`
- `0x1d5a0`
- `0x1d5f0`
- `0x1d640`
- `0x1d690`
- `0x1d700`
- `0x1d750`
- `0x1d7a0`
- `0x1d7f0`
- `0x1d9f0`
- `0x1e000`
- `0x1e130`

## callees

- `0x1b420`
- `0x1b440`
- `0x1b510`
- `0x1b5f0`
- `0x1e290`
- `0x1e2a0`
- `0x2acd0`
- `0x579b0`

## string_xrefs

- `0x1b46f`: `Invalid configuration: Multiple content databases were found with taxonomy extensions for partition ID {0}`
- `0x1b4d1`: `Invalid configuration: No content database extension was mapped for partition {0}, and there is no service database to fall back to`
- `0x1b4ec`: `DatabaseMapperNoServiceDatabase`

## pseudocode

```c

```

## disassembly

```asm
0x1b440  ldarg.0
0x1b441  call     instance class Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::get_DatabaseMapperContext()
0x1b446  callvirt instance bool Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext::get_UseServiceDataMap()
0x1b44b  brfalse  loc_1B4FC
0x1b450  ldarg.1
0x1b451  ldc.i4.s 0x40
0x1b453  ldc.i4.0
0x1b454  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase> [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceDataMap::GetServiceDataDsn(valuetype [mscorlib]System.Guid, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.ServiceExtensionType, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.ServiceExtensionOption)
0x1b459  stloc.0
0x1b45a  ldloc.0
0x1b45b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase>::get_Count()
0x1b460  ldc.i4.1
0x1b461  ble.s    loc_1B49A
0x1b463  ldc.i4   0x681690
0x1b468  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1b46d  ldc.i4.s 0x14
0x1b46f  ldstr    aInvalidConfigu// "Invalid configuration: Multiple content"...
0x1b474  ldc.i4.1
0x1b475  newarr   [mscorlib]System.Object
0x1b47a  stloc.2
0x1b47b  ldloc.2
0x1b47c  ldc.i4.0
0x1b47d  ldarg.1
0x1b47e  box      [mscorlib]System.Guid
0x1b483  stelem.ref
0x1b484  ldloc.2
0x1b485  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x1b48a  ldstr    aDatabasemapper// "DatabaseMapperTooManyMappedDatabases"
0x1b48f  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x1b494  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x1b499  throw
0x1b49a  ldloc.0
0x1b49b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase>::get_Count()
0x1b4a0  ldc.i4.1
0x1b4a1  bne.un.s loc_1B4B2
0x1b4a3  ldloc.0
0x1b4a4  ldc.i4.0
0x1b4a5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase>::get_Item(!!T0)
0x1b4aa  stloc.1
0x1b4ab  ldloc.1
0x1b4ac  call     class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapter Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::GetAdapterForContentDatabase(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase contentDatabase)
0x1b4b1  ret
0x1b4b2  ldarg.0
0x1b4b3  call     instance class Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::get_DatabaseMapperContext()
0x1b4b8  callvirt instance class Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext::get_Database()
0x1b4bd  ldnull
0x1b4be  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x1b4c3  brfalse.s loc_1B4FC
0x1b4c5  ldc.i4   0x681691
0x1b4ca  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1b4cf  ldc.i4.s 0x14
0x1b4d1  ldstr    aInvalidConfigu_0// "Invalid configuration: No content datab"...
0x1b4d6  ldc.i4.1
0x1b4d7  newarr   [mscorlib]System.Object
0x1b4dc  stloc.3
0x1b4dd  ldloc.3
0x1b4de  ldc.i4.0
0x1b4df  ldarg.1
0x1b4e0  box      [mscorlib]System.Guid
0x1b4e5  stelem.ref
0x1b4e6  ldloc.3
0x1b4e7  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x1b4ec  ldstr    aDatabasemapper_0// "DatabaseMapperNoServiceDatabase"
0x1b4f1  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x1b4f6  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x1b4fb  throw
0x1b4fc  ldarg.0
0x1b4fd  call     instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapter Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::GetAdapterForServiceDatabase()
0x1b502  ret
```
