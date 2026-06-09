# Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::GetAllMappedDatabases

- ea: `0x1c7e0`
- end: `0x1c8a4`
- name: `Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::GetAllMappedDatabases`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x63cc0`

## callees

- `0x1b420`
- `0x1c7e0`
- `0x1e1d0`
- `0x1e210`
- `0x1e280`
- `0x1e2c0`

## string_xrefs

- `0x1c7f7`: `MetadataWebServiceApplication.GetAllMappedDatabases called on '{0}'.`
- `0x1c864`: `MetadataWebServiceApplication.GetAllMappedDatabases found {0} content databases in '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x1c7e0  ldarg.0
0x1c7e1  ldstr    aGetallmappedda// "GetAllMappedDatabases"
0x1c7e6  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::SendTraceStart(string function)
0x1c7eb  ldc.i4   0x70345A
0x1c7f0  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1c7f5  ldc.i4.s 0x64
0x1c7f7  ldstr    aMetadatawebser_17// "MetadataWebServiceApplication.GetAllMap"...
0x1c7fc  ldc.i4.1
0x1c7fd  newarr   [mscorlib]System.Object
0x1c802  stloc.2
0x1c803  ldloc.2
0x1c804  ldc.i4.0
0x1c805  ldarg.0
0x1c806  call     instance class Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::get_DatabaseMapperContext()
0x1c80b  callvirt instance string Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext::get_Name()
0x1c810  stelem.ref
0x1c811  ldloc.2
0x1c812  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x1c817  ldarg.0
0x1c818  call     instance class Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::get_DatabaseMapperContext()
0x1c81d  ldc.i4   0x1000
0x1c822  conv.i8
0x1c823  callvirt instance void Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext::CheckPermission(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.AccessControl.SPIisWebServiceApplicationRights requiredPermissions)
0x1c828  ldc.i4.s 0x40
0x1c82a  ldc.i4.0
0x1c82b  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase> [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceDataMap::GetAllServiceDataDsn(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.ServiceExtensionType, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.ServiceExtensionOption)
0x1c830  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::CS$<>9__CachedAnonymousMethodDelegate1
0x1c835  brtrue.s loc_1C848
0x1c837  ldnull
0x1c838  ldftn    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::<GetAllMappedDatabases>b__0(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase db)
0x1c83e  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0x1c843  stsfld   class [mscorlib]System.Func`2<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::CS$<>9__CachedAnonymousMethodDelegate1
0x1c848  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::CS$<>9__CachedAnonymousMethodDelegate1
0x1c84d  call     T0x2B00001D
0x1c852  call     T0x2B000016
0x1c857  stloc.0
0x1c858  ldc.i4   0x70345B
0x1c85d  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1c862  ldc.i4.s 0x32
0x1c864  ldstr    aMetadatawebser_18// "MetadataWebServiceApplication.GetAllMap"...
0x1c869  ldc.i4.2
0x1c86a  newarr   [mscorlib]System.Object
0x1c86f  stloc.3
0x1c870  ldloc.3
0x1c871  ldc.i4.0
0x1c872  ldloc.0
0x1c873  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x1c878  box      [mscorlib]System.Int32
0x1c87d  stelem.ref
0x1c87e  ldloc.3
0x1c87f  ldc.i4.1
0x1c880  ldarg.0
0x1c881  call     instance class Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::get_DatabaseMapperContext()
0x1c886  callvirt instance string Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext::get_Name()
0x1c88b  stelem.ref
0x1c88c  ldloc.3
0x1c88d  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x1c892  ldloc.0
0x1c893  stloc.1
0x1c894  leave.s  loc_1C8A2
0x1c896  ldarg.0
0x1c897  ldstr    aGetallmappedda// "GetAllMappedDatabases"
0x1c89c  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::SendTraceEnd(string function)
0x1c8a1  endfinally
0x1c8a2  ldloc.1
0x1c8a3  ret
```
