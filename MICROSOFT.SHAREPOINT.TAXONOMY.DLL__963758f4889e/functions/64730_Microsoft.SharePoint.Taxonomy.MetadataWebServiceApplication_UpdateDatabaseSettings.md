# Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::UpdateDatabaseSettings

- ea: `0x64730`
- end: `0x64897`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::UpdateDatabaseSettings`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x64660`

## callees

- `0x1df40`
- `0x63a50`
- `0x63a60`
- `0x63a80`
- `0x64730`
- `0x64b50`
- `0x64ba0`
- `0x64d70`
- `0x66ce0`
- `0x66d20`
- `0x66d30`
- `0x66e90`

## string_xrefs

- `0x6473c`: `MetadataWebServiceApplication database '{0}' settings update started.`
- `0x6487d`: `MetadataWebServiceApplication database '{0}' settings update ended.`

## pseudocode

```c

```

## disassembly

```asm
0x64730  ldc.i4   0xC4709
0x64735  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6473a  ldc.i4.s 0x32
0x6473c  ldstr    aMetadatawebser_45// "MetadataWebServiceApplication database "...
0x64741  ldc.i4.1
0x64742  newarr   [mscorlib]System.Object
0x64747  stloc.s  7
0x64749  ldloc.s  7
0x6474b  ldc.i4.0
0x6474c  ldarg.1
0x6474d  stelem.ref
0x6474e  ldloc.s  7
0x64750  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x64755  ldc.i4.0
0x64756  stloc.0
0x64757  ldc.i4.0
0x64758  stloc.1
0x64759  ldarg.s  0xA
0x6475b  ldnull
0x6475c  stind.ref
0x6475d  ldnull
0x6475e  stloc.2
0x6475f  ldnull
0x64760  stloc.3
0x64761  ldarg.1
0x64762  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x64767  brfalse.s loc_64774
0x64769  ldarg.2
0x6476a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6476f  brtrue   loc_6480B
0x64774  ldarg.1
0x64775  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6477a  brtrue.s loc_64780
0x6477c  ldarg.1
0x6477d  stloc.2
0x6477e  br.s     loc_64787
0x64780  ldarg.0
0x64781  call     instance string Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_DatabaseName()
0x64786  stloc.2
0x64787  ldarg.2
0x64788  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6478d  brtrue.s loc_64793
0x6478f  ldarg.2
0x64790  stloc.3
0x64791  br.s     loc_6479A
0x64793  ldarg.0
0x64794  call     instance string Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_DatabaseServer()
0x64799  stloc.3
0x6479a  ldarg.0
0x6479b  call     instance string Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_DatabaseName()
0x647a0  ldloc.2
0x647a1  ldc.i4.5
0x647a2  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x647a7  brfalse.s loc_647B8
0x647a9  ldarg.0
0x647aa  call     instance string Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_DatabaseServer()
0x647af  ldloc.3
0x647b0  ldc.i4.5
0x647b1  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x647b6  brtrue.s loc_6480B
0x647b8  ldnull
0x647b9  stloc.s  4
0x647bb  ldarg.3
0x647bc  brfalse.s loc_647D5
0x647be  ldarg.1
0x647bf  ldarg.2
0x647c0  ldarg.0
0x647c1  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x647c6  ldarg.s  4
0x647c8  ldarg.s  5
0x647ca  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPDatabaseParameters Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase::CreateDatabaseParameters(string databaseName, string databaseServer, string sharedAppName, string sqlAuthUserName, string sqlAuthPassword)
0x647cf  stloc.s  4
0x647d1  ldc.i4.1
0x647d2  stloc.1
0x647d3  br.s     loc_647E4
0x647d5  ldarg.1
0x647d6  ldarg.2
0x647d7  ldarg.0
0x647d8  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x647dd  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPDatabaseParameters Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase::CreateDatabaseParameters(string databaseName, string databaseServer, string sharedAppName)
0x647e2  stloc.s  4
0x647e4  ldloc.s  4
0x647e6  call     class Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase::Create(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPDatabaseParameters databaseParameters)
0x647eb  stloc.s  5
0x647ed  ldarg.s  0xA
0x647ef  ldarg.0
0x647f0  ldfld    class Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::database
0x647f5  stind.ref
0x647f6  ldarg.0
0x647f7  ldloc.s  5
0x647f9  stfld    class Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::database
0x647fe  ldc.i4.1
0x647ff  stloc.0
0x64800  ldarg.0
0x64801  call     instance class Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_DatabaseMapper()
0x64806  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::RefreshLocalData()
0x6480b  ldloc.0
0x6480c  brfalse.s loc_64818
0x6480e  ldarg.0
0x6480f  ldarg.s  8
0x64811  ldarg.s  9
0x64813  call     instance void Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::SetDatabase(int32 cacheCheckInterval, int32 maxChannelCache)
0x64818  ldc.i4.0
0x64819  stloc.s  6
0x6481b  ldarg.3
0x6481c  brfalse.s loc_64833
0x6481e  ldloc.1
0x6481f  brtrue.s loc_64833
0x64821  ldarg.0
0x64822  call     instance class Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_Database()
0x64827  ldarg.s  4
0x64829  ldarg.s  5
0x6482b  callvirt instance void Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase::SetAuthenticationMode(string sqlAuthUserName, string sqlAuthPassword)
0x64830  ldc.i4.1
0x64831  stloc.s  6
0x64833  ldarg.s  6
0x64835  brfalse.s loc_64862
0x64837  ldarg.s  7
0x64839  brtrue.s loc_64842
0x6483b  ldsfld   string [mscorlib]System.String::Empty
0x64840  starg.s  7
0x64842  ldarg.0
0x64843  call     instance string Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_FailoverServer()
0x64848  ldarg.s  7
0x6484a  ldc.i4.5
0x6484b  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x64850  brtrue.s loc_64862
0x64852  ldarg.0
0x64853  call     instance class Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_Database()
0x64858  ldarg.s  7
0x6485a  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPDatabase::AddFailoverServiceInstance(string)
0x6485f  ldc.i4.1
0x64860  stloc.s  6
0x64862  ldloc.s  6
0x64864  brfalse.s loc_64871
0x64866  ldarg.0
0x64867  call     instance class Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_Database()
0x6486c  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x64871  ldc.i4   0xC470A
0x64876  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6487b  ldc.i4.s 0x32
0x6487d  ldstr    aMetadatawebser_46// "MetadataWebServiceApplication database "...
0x64882  ldc.i4.1
0x64883  newarr   [mscorlib]System.Object
0x64888  stloc.s  8
0x6488a  ldloc.s  8
0x6488c  ldc.i4.0
0x6488d  ldarg.1
0x6488e  stelem.ref
0x6488f  ldloc.s  8
0x64891  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x64896  ret
```
