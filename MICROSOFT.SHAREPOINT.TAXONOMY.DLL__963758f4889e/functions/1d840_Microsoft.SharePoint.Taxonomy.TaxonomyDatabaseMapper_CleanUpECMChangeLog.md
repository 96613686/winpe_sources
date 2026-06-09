# Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::CleanUpECMChangeLog

- ea: `0x1d840`
- end: `0x1d928`
- name: `Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::CleanUpECMChangeLog`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x64040`

## callees

- `0x1a700`
- `0x1b420`
- `0x1b510`
- `0x1d840`
- `0x1e1d0`
- `0x1e210`
- `0x1e280`
- `0x1e290`

## string_xrefs

- `0x1d874`: `CleanUpECMChangeLog called, but the db was read only, so not attempting.`
- `0x1d896`: `Begin MetadataWebServiceApplication.CleanUpECMChangeLog called on '{0}'`
- `0x1d8cd`: `End MetadataWebServiceApplication.CleanUpECMChangeLog called on '{0}'`
- `0x1d8fc`: `MetadataWebServiceApplication.CleanUpECMChangeLog failed with Exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1d840  ldc.i4   0x50C783
0x1d845  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1d84a  ldc.i4.s 0x32
0x1d84c  ldstr    aCleanupecmchan// "CleanUpECMChangeLog called on WebApp"
0x1d851  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x1d856  ldarg.0
0x1d857  call     instance class Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::get_DatabaseMapperContext()
0x1d85c  callvirt instance class Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext::get_Database()
0x1d861  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPDatabase::get_IsReadOnly()
0x1d866  brfalse.s loc_1D87F
0x1d868  ldc.i4   0x58D017
0x1d86d  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1d872  ldc.i4.s 0xF
0x1d874  ldstr    aCleanupecmchan_0// "CleanUpECMChangeLog called, but the db "...
0x1d879  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x1d87e  ret
0x1d87f  ldarg.0
0x1d880  ldstr    aCleanupchangel// "CleanupChangeLog"
0x1d885  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::SendTraceStart(string function)
0x1d88a  ldc.i4   0x50C784
0x1d88f  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1d894  ldc.i4.s 0x32
0x1d896  ldstr    aBeginMetadataw// "Begin MetadataWebServiceApplication.Cle"...
0x1d89b  ldc.i4.1
0x1d89c  newarr   [mscorlib]System.Object
0x1d8a1  stloc.1
0x1d8a2  ldloc.1
0x1d8a3  ldc.i4.0
0x1d8a4  ldarg.0
0x1d8a5  call     instance class Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::get_DatabaseMapperContext()
0x1d8aa  callvirt instance string Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext::get_Name()
0x1d8af  stelem.ref
0x1d8b0  ldloc.1
0x1d8b1  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x1d8b6  ldarg.0
0x1d8b7  call     instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapter Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::GetAdapterForServiceDatabase()
0x1d8bc  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadWrite::CleanUpECMChangeLog()
0x1d8c1  ldc.i4   0x50C785
0x1d8c6  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1d8cb  ldc.i4.s 0x32
0x1d8cd  ldstr    aEndMetadataweb// "End MetadataWebServiceApplication.Clean"...
0x1d8d2  ldc.i4.1
0x1d8d3  newarr   [mscorlib]System.Object
0x1d8d8  stloc.2
0x1d8d9  ldloc.2
0x1d8da  ldc.i4.0
0x1d8db  ldarg.0
0x1d8dc  call     instance class Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::get_DatabaseMapperContext()
0x1d8e1  callvirt instance string Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext::get_Name()
0x1d8e6  stelem.ref
0x1d8e7  ldloc.2
0x1d8e8  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x1d8ed  leave.s  loc_1D919
0x1d8ef  stloc.0
0x1d8f0  ldc.i4   0x50C786
0x1d8f5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1d8fa  ldc.i4.s 0xA
0x1d8fc  ldstr    aMetadatawebser_19// "MetadataWebServiceApplication.CleanUpEC"...
0x1d901  ldc.i4.1
0x1d902  newarr   [mscorlib]System.Object
0x1d907  stloc.3
0x1d908  ldloc.3
0x1d909  ldc.i4.0
0x1d90a  ldloc.0
0x1d90b  callvirt instance string [mscorlib]System.Object::ToString()
0x1d910  stelem.ref
0x1d911  ldloc.3
0x1d912  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x1d917  leave.s  loc_1D919
0x1d919  leave.s  loc_1D927
0x1d91b  ldarg.0
0x1d91c  ldstr    aCleanupchangel// "CleanupChangeLog"
0x1d921  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::SendTraceEnd(string function)
0x1d926  endfinally
0x1d927  ret
```
