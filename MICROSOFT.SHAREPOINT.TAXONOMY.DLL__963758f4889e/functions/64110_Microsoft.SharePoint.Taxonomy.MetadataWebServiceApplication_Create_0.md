# Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::Create_0

- ea: `0x64110`
- end: `0x6422c`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::Create_0`
- size: `284`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x64100`
- `0x64250`

## callees

- `0x242a0`
- `0x242d0`
- `0x635b0`
- `0x63a20`
- `0x63a30`
- `0x64110`
- `0x644c0`
- `0x66ce0`

## string_xrefs

- `0x6411c`: `MetadataWebServiceApplication '{0}' simple create started.`
- `0x6413e`: `service`
- `0x64168`: `MetadataWebServiceApplication '{0}' with DB provision disabled: Create method skipped null check for databaseParameters.`
- `0x641bb`: `MetadataWebServiceApplication '{0}' with DB provision disabled: Create method skipped creation of MetadataWebServiceDatabase.`
- `0x64211`: `MetadataWebServiceApplication '{0}' simple create complete.`

## pseudocode

```c

```

## disassembly

```asm
0x64110  ldc.i4   0x61617238
0x64115  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6411a  ldc.i4.s 0x14
0x6411c  ldstr    aMetadatawebser_34// "MetadataWebServiceApplication '{0}' sim"...
0x64121  ldc.i4.1
0x64122  newarr   [mscorlib]System.Object
0x64127  stloc.3
0x64128  ldloc.3
0x64129  ldc.i4.0
0x6412a  ldarg.0
0x6412b  stelem.ref
0x6412c  ldloc.3
0x6412d  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x64132  ldarg.0
0x64133  ldstr    aName_1// "name"
0x64138  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNullOrEmpty(string value, string parameterName)
0x6413d  ldarg.1
0x6413e  ldstr    aService// "service"
0x64143  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x64148  call     bool Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_IsServiceDatabaseEnabled()
0x6414d  brfalse.s loc_6415C
0x6414f  ldarg.2
0x64150  ldstr    aDatabaseparame// "databaseParameters"
0x64155  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x6415a  br.s     loc_64181
0x6415c  ldc.i4   0x230D019
0x64161  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x64166  ldc.i4.s 0x32
0x64168  ldstr    aMetadatawebser_35// "MetadataWebServiceApplication '{0}' wit"...
0x6416d  ldc.i4.1
0x6416e  newarr   [mscorlib]System.Object
0x64173  stloc.s  4
0x64175  ldloc.s  4
0x64177  ldc.i4.0
0x64178  ldarg.0
0x64179  stelem.ref
0x6417a  ldloc.s  4
0x6417c  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x64181  ldarg.0
0x64182  ldloca.s 0
0x64184  call     bool Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::IsNameValid(string sharedAppName, [out] string& errorMessage)
0x64189  brtrue.s loc_64192
0x6418b  ldloc.0
0x6418c  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPException::.ctor(string)
0x64191  throw
0x64192  ldnull
0x64193  stloc.1
0x64194  call     bool Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_IsServiceDatabaseEnabled()
0x64199  brtrue.s loc_6419E
0x6419b  ldarg.2
0x6419c  brfalse.s loc_641AF
0x6419e  ldarg.2
0x6419f  call     class Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase::Create(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPDatabaseParameters databaseParameters)
0x641a4  stloc.1
0x641a5  ldloc.1
0x641a6  ldarg.s  4
0x641a8  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedUpgradableObject::set_ShouldDeferUpgradeActions(bool)
0x641ad  br.s     loc_641D4
0x641af  ldc.i4   0x230D01A
0x641b4  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x641b9  ldc.i4.s 0x32
0x641bb  ldstr    aMetadatawebser_36// "MetadataWebServiceApplication '{0}' wit"...
0x641c0  ldc.i4.1
0x641c1  newarr   [mscorlib]System.Object
0x641c6  stloc.s  5
0x641c8  ldloc.s  5
0x641ca  ldc.i4.0
0x641cb  ldarg.0
0x641cc  stelem.ref
0x641cd  ldloc.s  5
0x641cf  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x641d4  ldarg.0
0x641d5  ldarg.1
0x641d6  ldloc.1
0x641d7  ldarg.3
0x641d8  newobj   instance void Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::.ctor(string name, class Microsoft.SharePoint.Taxonomy.MetadataWebService service, class Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase database, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisWebServiceApplicationPool appPool)
0x641dd  stloc.2
0x641de  ldloc.2
0x641df  ldc.i4.0
0x641e0  callvirt instance void Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::set_IsPartitioned(bool value)
0x641e5  ldloc.2
0x641e6  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x641eb  ldloc.2
0x641ec  ldstr    aHttp// "http"
0x641f1  ldc.i4.1
0x641f2  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisWebServiceEndpoint [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisWebServiceApplication::AddServiceEndpoint(string, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisWebServiceBindingType)
0x641f7  pop
0x641f8  ldloc.2
0x641f9  ldstr    aHttps// "https"
0x641fe  ldc.i4.2
0x641ff  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisWebServiceEndpoint [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisWebServiceApplication::AddServiceEndpoint(string, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisWebServiceBindingType)
0x64204  pop
0x64205  ldc.i4   0x61617239
0x6420a  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6420f  ldc.i4.s 0x14
0x64211  ldstr    aMetadatawebser_37// "MetadataWebServiceApplication '{0}' sim"...
0x64216  ldc.i4.1
0x64217  newarr   [mscorlib]System.Object
0x6421c  stloc.s  6
0x6421e  ldloc.s  6
0x64220  ldc.i4.0
0x64221  ldarg.0
0x64222  stelem.ref
0x64223  ldloc.s  6
0x64225  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x6422a  ldloc.2
0x6422b  ret
```
