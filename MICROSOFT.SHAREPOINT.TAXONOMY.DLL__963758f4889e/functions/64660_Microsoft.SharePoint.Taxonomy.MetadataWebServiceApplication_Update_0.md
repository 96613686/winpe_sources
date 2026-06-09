# Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::Update_0

- ea: `0x64660`
- end: `0x6472b`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::Update_0`
- size: `203`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x64250`
- `0x64630`

## callees

- `0x63a30`
- `0x64660`
- `0x64730`
- `0x648a0`

## string_xrefs

- `0x64697`: `MetadataWebServiceApplication '{0}' with DB provision disabled: Update method skipped updating database settings.`
- `0x646e1`: `The old database persisted object {0} is being deleted`
- `0x6470f`: `MetadataWebServiceApplication '{0}' with DB provision disabled: Update method skipped deletion of the database.`

## pseudocode

```c

```

## disassembly

```asm
0x64660  ldnull
0x64661  stloc.0
0x64662  call     bool Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_IsServiceDatabaseEnabled()
0x64667  brtrue.s loc_64671
0x64669  ldarg.2
0x6466a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6466f  brtrue.s loc_6468B
0x64671  ldarg.0
0x64672  ldarg.2
0x64673  ldarg.3
0x64674  ldarg.s  4
0x64676  ldarg.s  5
0x64678  ldarg.s  6
0x6467a  ldarg.s  7
0x6467c  ldarg.s  8
0x6467e  ldarg.s  0xE
0x64680  ldarg.s  0xF
0x64682  ldloca.s 0
0x64684  call     instance void Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::UpdateDatabaseSettings(string databaseName, string databaseServer, bool doSetAuthenticationMode, string sqlAuthUserName, string sqlAuthPassword, bool doSetFailoverServer, string failoverServer, int32 cacheCheckInterval, int32 maxChannelCache, [out] class Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase& oldDatabase)
0x64689  br.s     loc_646B2
0x6468b  ldc.i4   0x230D01C
0x64690  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x64695  ldc.i4.s 0x32
0x64697  ldstr    aMetadatawebser_43// "MetadataWebServiceApplication '{0}' wit"...
0x6469c  ldc.i4.1
0x6469d  newarr   [mscorlib]System.Object
0x646a2  stloc.1
0x646a3  ldloc.1
0x646a4  ldc.i4.0
0x646a5  ldarg.0
0x646a6  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x646ab  stelem.ref
0x646ac  ldloc.1
0x646ad  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x646b2  ldarg.0
0x646b3  ldarg.1
0x646b4  ldarg.s  9
0x646b6  ldarg.s  0xA
0x646b8  ldarg.s  0xB
0x646ba  ldarg.s  0xC
0x646bc  ldarg.s  0xD
0x646be  ldarg.s  0x10
0x646c0  call     instance void Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::UpdateData(string sharedAppName, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisWebServiceApplicationPool applicationPool, bool unpublishAllPackages, string hubUri, bool doSetErrorReport, bool isErrorReportEnabled, bool doProvision)
0x646c5  call     bool Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_IsServiceDatabaseEnabled()
0x646ca  brfalse.s loc_64703
0x646cc  ldloc.0
0x646cd  ldnull
0x646ce  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x646d3  brfalse.s loc_6472A
0x646d5  ldc.i4   0x212348
0x646da  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x646df  ldc.i4.s 0x64
0x646e1  ldstr    aTheOldDatabase// "The old database persisted object {0} i"...
0x646e6  ldc.i4.1
0x646e7  newarr   [mscorlib]System.Object
0x646ec  stloc.2
0x646ed  ldloc.2
0x646ee  ldc.i4.0
0x646ef  ldloc.0
0x646f0  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x646f5  stelem.ref
0x646f6  ldloc.2
0x646f7  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x646fc  ldloc.0
0x646fd  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Delete()
0x64702  ret
0x64703  ldc.i4   0x230D01D
0x64708  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6470d  ldc.i4.s 0x32
0x6470f  ldstr    aMetadatawebser_44// "MetadataWebServiceApplication '{0}' wit"...
0x64714  ldc.i4.1
0x64715  newarr   [mscorlib]System.Object
0x6471a  stloc.3
0x6471b  ldloc.3
0x6471c  ldc.i4.0
0x6471d  ldarg.0
0x6471e  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x64723  stelem.ref
0x64724  ldloc.3
0x64725  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x6472a  ret
```
