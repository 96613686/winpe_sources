# Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::Create_2

- ea: `0x64250`
- end: `0x644ba`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::Create_2`
- size: `618`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x3b1c0`
- `0x64230`

## callees

- `0x1a180`
- `0x1b430`
- `0x24050`
- `0x25a60`
- `0x2acd0`
- `0x2ad40`
- `0x63a20`
- `0x63a30`
- `0x64110`
- `0x64250`
- `0x64660`
- `0x64ba0`
- `0x65a90`
- `0x66d30`

## string_xrefs

- `0x642c9`: `ErrorMetadataServiceNotInstalled`
- `0x6425c`: `MetadataWebServiceApplication '{0}' create started.`
- `0x642a5`: `hubUriString`
- `0x64304`: `MetadataWebServiceApplication '{0}' with DB provision disabled: Create method skipped creation of databaseParameters.`
- `0x64367`: `MetadataWebServiceApplication '{0}' create failed. Exception: {1}`
- `0x643b0`: `MetadataWebServiceApplication attempt to delete incorrectly provisioned service application '{0}' failed . Exception: {1}`
- `0x64474`: `Added {0} as a term store admin in MetadataWebServiceApplication '{1}'.`
- `0x6449f`: `MetadataWebServiceApplication '{0}' create complete.`

## pseudocode

```c

```

## disassembly

```asm
0x64250  ldc.i4   0x61617330
0x64255  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6425a  ldc.i4.s 0x14
0x6425c  ldstr    aMetadatawebser_38// "MetadataWebServiceApplication '{0}' cre"...
0x64261  ldc.i4.1
0x64262  newarr   [mscorlib]System.Object
0x64267  stloc.s  0xB
0x64269  ldloc.s  0xB
0x6426b  ldc.i4.0
0x6426c  ldarg.0
0x6426d  stelem.ref
0x6426e  ldloc.s  0xB
0x64270  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x64275  ldarg.s  0xA
0x64277  brtrue.s loc_642B0
0x64279  ldarg.s  7
0x6427b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x64280  brtrue.s loc_642B0
0x64282  ldarg.s  7
0x64284  call     bool Microsoft.SharePoint.Taxonomy.Internal.CommonValidator::IsValidHubUrl(string urlString)
0x64289  brtrue.s loc_642B0
0x6428b  ldstr    aErrorinvalidhu// "ErrorInvalidHubUrl"
0x64290  ldc.i4.1
0x64291  newarr   [mscorlib]System.Object
0x64296  stloc.s  0xC
0x64298  ldloc.s  0xC
0x6429a  ldc.i4.0
0x6429b  ldarg.s  7
0x6429d  stelem.ref
0x6429e  ldloc.s  0xC
0x642a0  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x642a5  ldstr    aHuburistring// "hubUriString"
0x642aa  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x642af  throw
0x642b0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x642b5  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_Services()
0x642ba  callvirt T0x2B000011
0x642bf  stloc.0
0x642c0  ldnull
0x642c1  ldloc.0
0x642c2  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x642c7  brfalse.s loc_642D9
0x642c9  ldstr    aErrormetadatas// "ErrorMetadataServiceNotInstalled"
0x642ce  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x642d3  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x642d8  throw
0x642d9  ldnull
0x642da  stloc.1
0x642db  call     bool Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_IsServiceDatabaseEnabled()
0x642e0  brtrue.s loc_642EA
0x642e2  ldarg.1
0x642e3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x642e8  brtrue.s loc_642F8
0x642ea  ldarg.1
0x642eb  ldarg.2
0x642ec  ldarg.0
0x642ed  ldarg.3
0x642ee  ldarg.s  4
0x642f0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPDatabaseParameters Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase::CreateDatabaseParameters(string databaseName, string databaseServer, string sharedAppName, string sqlAuthUserName, string sqlAuthPassword)
0x642f5  stloc.1
0x642f6  br.s     loc_6431D
0x642f8  ldc.i4   0x230D01B
0x642fd  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x64302  ldc.i4.s 0x32
0x64304  ldstr    aMetadatawebser_39// "MetadataWebServiceApplication '{0}' wit"...
0x64309  ldc.i4.1
0x6430a  newarr   [mscorlib]System.Object
0x6430f  stloc.s  0xD
0x64311  ldloc.s  0xD
0x64313  ldc.i4.0
0x64314  ldarg.0
0x64315  stelem.ref
0x64316  ldloc.s  0xD
0x64318  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x6431d  ldnull
0x6431e  stloc.2
0x6431f  ldarg.0
0x64320  ldloc.0
0x64321  ldloc.1
0x64322  ldarg.s  6
0x64324  ldarg.s  0xE
0x64326  call     class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::Create(string name, class Microsoft.SharePoint.Taxonomy.MetadataWebService service, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPDatabaseParameters databaseParameters, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisWebServiceApplicationPool applicationPool, bool fDeferUpgradeActions)
0x6432b  stloc.2
0x6432c  ldloc.2
0x6432d  ldarg.s  0xA
0x6432f  callvirt instance void Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::set_IsPartitioned(bool value)
0x64334  ldloc.2
0x64335  ldc.i4.1
0x64336  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Update(bool)
0x6433b  ldloc.2
0x6433c  ldarg.0
0x6433d  ldarg.1
0x6433e  ldarg.2
0x6433f  ldc.i4.1
0x64340  ldarg.3
0x64341  ldarg.s  4
0x64343  ldc.i4.1
0x64344  ldarg.s  5
0x64346  ldarg.s  6
0x64348  ldc.i4.0
0x64349  ldarg.s  7
0x6434b  ldc.i4.1
0x6434c  ldarg.s  8
0x6434e  ldarg.s  0xB
0x64350  ldarg.s  0xC
0x64352  ldc.i4.1
0x64353  callvirt instance void Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::Update(string sharedAppName, string databaseName, string databaseServer, bool doSetAuthenticationMode, string sqlAuthUserName, string sqlAuthPassword, bool doSetFailoverServer, string failoverServer, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisWebServiceApplicationPool applicationPool, bool unpublishAllPackages, string hubUri, bool doSetErrorReport, bool isErrorReportEnabled, int32 cacheCheckInterval, int32 maxChannelCache, bool doProvision)
0x64358  leave.s  loc_643D8
0x6435a  stloc.3
0x6435b  ldc.i4   0x63636338
0x64360  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x64365  ldc.i4.s 0xA
0x64367  ldstr    aMetadatawebser_40// "MetadataWebServiceApplication '{0}' cre"...
0x6436c  ldc.i4.2
0x6436d  newarr   [mscorlib]System.Object
0x64372  stloc.s  0xE
0x64374  ldloc.s  0xE
0x64376  ldc.i4.0
0x64377  ldarg.0
0x64378  stelem.ref
0x64379  ldloc.s  0xE
0x6437b  ldc.i4.1
0x6437c  ldloc.3
0x6437d  callvirt instance string [mscorlib]System.Object::ToString()
0x64382  stelem.ref
0x64383  ldloc.s  0xE
0x64385  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x6438a  ldloc.2
0x6438b  ldnull
0x6438c  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x64391  brfalse.s loc_643A0
0x64393  ldloc.2
0x64394  ldc.i4.0
0x64395  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplication::Unprovision(bool)
0x6439a  ldloc.2
0x6439b  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Delete()
0x643a0  leave.s  loc_643D6
0x643a2  stloc.s  4
0x643a4  ldc.i4   0x63636339
0x643a9  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x643ae  ldc.i4.s 0xA
0x643b0  ldstr    aMetadatawebser_41// "MetadataWebServiceApplication attempt t"...
0x643b5  ldc.i4.2
0x643b6  newarr   [mscorlib]System.Object
0x643bb  stloc.s  0xF
0x643bd  ldloc.s  0xF
0x643bf  ldc.i4.0
0x643c0  ldarg.0
0x643c1  stelem.ref
0x643c2  ldloc.s  0xF
0x643c4  ldc.i4.1
0x643c5  ldloc.s  4
0x643c7  callvirt instance string [mscorlib]System.Object::ToString()
0x643cc  stelem.ref
0x643cd  ldloc.s  0xF
0x643cf  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x643d4  leave.s  loc_643D6
0x643d6  rethrow
0x643d8  ldarg.s  0xD
0x643da  brfalse.s loc_64414
0x643dc  ldnull
0x643dd  stloc.s  5
0x643df  ldc.i4.0
0x643e0  stloc.s  6
0x643e2  ldarg.s  7
0x643e4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x643e9  brtrue.s loc_643F7
0x643eb  ldarg.s  7
0x643ed  newobj   instance void [System]System.Uri::.ctor(string)
0x643f2  stloc.s  5
0x643f4  ldc.i4.1
0x643f5  stloc.s  6
0x643f7  ldloc.2
0x643f8  callvirt instance class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisWebServiceApplication::get_Uri()
0x643fd  ldloc.2
0x643fe  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x64403  ldc.i4.0
0x64404  ldc.i4.0
0x64405  ldloc.s  6
0x64407  ldloc.s  5
0x64409  ldc.i4.1
0x6440a  ldarg.s  9
0x6440c  ldarg.s  0xA
0x6440e  call     class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::CreateProxy(class [System]System.Uri metadataAppUri, string proxyName, bool isDefaultKeywordTaxonomy, bool isDefaultSiteCollectionTaxonomy, bool isContentTypeSyndicationEnabled, class [System]System.Uri hubUrl, bool isContentTypePushdownEnabled, bool isInDefaultAssociationGroup, bool isPartitioned)
0x64413  pop
0x64414  ldarg.s  0xA
0x64416  brtrue.s loc_64493
0x64418  call     string Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::GetCurrentUserName()
0x6441d  stloc.s  7
0x6441f  newobj   instance void class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights>::.ctor()
0x64424  stloc.s  8
0x64426  ldloc.s  8
0x64428  ldloc.s  7
0x6442a  ldc.i4   0x110
0x6442f  conv.i8
0x64430  ldc.i4.0
0x64431  conv.i8
0x64432  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAce`1<var<u1>> class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAcl`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights>::Add(!!T0, string, var<u1>)
0x64437  stloc.s  9
0x64439  ldloc.2
0x6443a  callvirt instance class Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_DatabaseMapper()
0x6443f  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapter Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::get_LegacyDatabaseAdapter()
0x64444  stloc.s  0xA
0x64446  ldloc.s  0xA
0x64448  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPServiceApplicationUtilities::DefaultPartitionId
0x6444d  ldc.i4.0
0x6444e  ldloc.s  9
0x64450  callvirt instance string class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAce`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights>::get_PrincipalName()
0x64455  ldloc.s  9
0x64457  callvirt instance string class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAce`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights>::get_DisplayName()
0x6445c  ldloc.s  9
0x6445e  callvirt instance var<u1> class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAce`1<valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights>::get_GrantRightsMask()
0x64463  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadWrite::WritePermission(valuetype [mscorlib]System.Guid resolvedPartitionId, int32 groupId, string principalName, string displayName, valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights taxonomyRights)
0x64468  ldc.i4   0x66676631
0x6446d  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x64472  ldc.i4.s 0x64
0x64474  ldstr    aAdded0AsATermS// "Added {0} as a term store admin in Meta"...
0x64479  ldc.i4.2
0x6447a  newarr   [mscorlib]System.Object
0x6447f  stloc.s  0x10
0x64481  ldloc.s  0x10
0x64483  ldc.i4.0
0x64484  ldloc.s  7
0x64486  stelem.ref
0x64487  ldloc.s  0x10
0x64489  ldc.i4.1
0x6448a  ldarg.0
0x6448b  stelem.ref
0x6448c  ldloc.s  0x10
0x6448e  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x64493  ldc.i4   0x61617331
0x64498  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6449d  ldc.i4.s 0x14
0x6449f  ldstr    aMetadatawebser_42// "MetadataWebServiceApplication '{0}' cre"...
0x644a4  ldc.i4.1
0x644a5  newarr   [mscorlib]System.Object
0x644aa  stloc.s  0x11
0x644ac  ldloc.s  0x11
0x644ae  ldc.i4.0
0x644af  ldarg.0
0x644b0  stelem.ref
0x644b1  ldloc.s  0x11
0x644b3  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x644b8  ldloc.2
0x644b9  ret
```
