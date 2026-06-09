# Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::CreateProxy

- ea: `0x65a90`
- end: `0x65bdb`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::CreateProxy`
- size: `331`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3bf00`
- `0x64250`

## callees

- `0x2acd0`
- `0x63180`
- `0x65280`
- `0x653f0`
- `0x65a90`
- `0x65be0`
- `0x65f40`

## string_xrefs

- `0x65a9c`: `MetadataWebServiceApplicationProxy '{0}' create started.`
- `0x65b49`: `Skipping partition check for service application proxy '{0}' because an exception was encountered.  Generally this occurs if the service application is still being created. Exception: {1}`
- `0x65b8a`: `ErrorServicePartitionSettingsMustMatch`
- `0x65bc0`: `MetadataWebServiceApplicationProxy '{0}' create complete.`

## pseudocode

```c

```

## disassembly

```asm
0x65a90  ldc.i4   0x61617431
0x65a95  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x65a9a  ldc.i4.s 0x14
0x65a9c  ldstr    aMetadatawebser_60// "MetadataWebServiceApplicationProxy '{0}"...
0x65aa1  ldc.i4.1
0x65aa2  newarr   [mscorlib]System.Object
0x65aa7  stloc.s  7
0x65aa9  ldloc.s  7
0x65aab  ldc.i4.0
0x65aac  ldarg.1
0x65aad  stelem.ref
0x65aae  ldloc.s  7
0x65ab0  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x65ab5  ldarg.s  8
0x65ab7  brtrue.s loc_65AD7
0x65ab9  ldarg.s  4
0x65abb  brfalse.s loc_65AD7
0x65abd  ldarg.s  5
0x65abf  ldnull
0x65ac0  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x65ac5  brfalse.s loc_65AD7
0x65ac7  ldstr    aErrorsyndicati// "ErrorSyndicationEnabledWithoutHub"
0x65acc  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x65ad1  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x65ad6  throw
0x65ad7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x65adc  stloc.0
0x65add  ldloc.0
0x65ade  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_Services()
0x65ae3  callvirt T0x2B000011
0x65ae8  stloc.1
0x65ae9  ldloc.1
0x65aea  ldarg.1
0x65aeb  ldarg.0
0x65aec  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxy Microsoft.SharePoint.Taxonomy.MetadataWebService::CreateProxy(string name, class [System]System.Uri serviceApplicationUri)
0x65af1  isinst   Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy
0x65af6  stloc.2
0x65af7  ldloc.2
0x65af8  ldc.i4.1
0x65af9  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Update(bool)
0x65afe  ldarg.s  7
0x65b00  brfalse.s loc_65B22
0x65b02  ldarg.2
0x65b03  brtrue.s loc_65B0F
0x65b05  call     bool Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::GetAreKeywordsEnabledInDefaultGroup()
0x65b0a  ldc.i4.0
0x65b0b  ceq
0x65b0d  starg.s  2
0x65b0f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxyGroup [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxyGroup::get_Default()
0x65b14  stloc.3
0x65b15  ldloc.3
0x65b16  ldloc.2
0x65b17  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxyGroup::Add(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxy)
0x65b1c  ldloc.3
0x65b1d  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x65b22  ldloc.2
0x65b23  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Provision()
0x65b28  ldc.i4.0
0x65b29  stloc.s  4
0x65b2b  ldc.i4.1
0x65b2c  stloc.s  5
0x65b2e  ldloc.2
0x65b2f  callvirt instance bool Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::GetIsServiceApplicationPartitioned()
0x65b34  stloc.s  4
0x65b36  leave.s  loc_65B74
0x65b38  stloc.s  6
0x65b3a  ldc.i4.0
0x65b3b  stloc.s  5
0x65b3d  ldc.i4   0x62766F37
0x65b42  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x65b47  ldc.i4.s 0x32
0x65b49  ldstr    aSkippingPartit_0// "Skipping partition check for service ap"...
0x65b4e  ldc.i4.2
0x65b4f  newarr   [mscorlib]System.Object
0x65b54  stloc.s  8
0x65b56  ldloc.s  8
0x65b58  ldc.i4.0
0x65b59  ldloc.2
0x65b5a  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_DisplayName()
0x65b5f  stelem.ref
0x65b60  ldloc.s  8
0x65b62  ldc.i4.1
0x65b63  ldloc.s  6
0x65b65  callvirt instance string [mscorlib]System.Object::ToString()
0x65b6a  stelem.ref
0x65b6b  ldloc.s  8
0x65b6d  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x65b72  leave.s  loc_65B74
0x65b74  ldloc.s  5
0x65b76  brfalse.s loc_65B9A
0x65b78  ldarg.s  8
0x65b7a  ldloc.s  4
0x65b7c  beq.s    loc_65B9A
0x65b7e  ldloc.2
0x65b7f  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Unprovision()
0x65b84  ldloc.2
0x65b85  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Delete()
0x65b8a  ldstr    aErrorservicepa// "ErrorServicePartitionSettingsMustMatch"
0x65b8f  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x65b94  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x65b99  throw
0x65b9a  ldloc.2
0x65b9b  ldarg.s  8
0x65b9d  callvirt instance void Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::set_IsPartitioned(bool value)
0x65ba2  ldloc.2
0x65ba3  ldc.i4.1
0x65ba4  ldarg.2
0x65ba5  ldc.i4.1
0x65ba6  ldarg.3
0x65ba7  ldc.i4.1
0x65ba8  ldarg.s  4
0x65baa  ldarg.s  5
0x65bac  ldc.i4.1
0x65bad  ldarg.s  6
0x65baf  callvirt instance void Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::Update(bool doSetDefaultKeyword, bool isDefaultKeywordTaxonomy, bool doSetDefaultSiteCollection, bool isDefaultSiteCollectionTaxonomy, bool doSetContentTypeSyndication, bool isContentTypeSyndicationEnabled, class [System]System.Uri hubUrl, bool doSetContentTypePushdown, bool isContentTypePushdownEnabled)
0x65bb4  ldc.i4   0x61617432
0x65bb9  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x65bbe  ldc.i4.s 0x14
0x65bc0  ldstr    aMetadatawebser_61// "MetadataWebServiceApplicationProxy '{0}"...
0x65bc5  ldc.i4.1
0x65bc6  newarr   [mscorlib]System.Object
0x65bcb  stloc.s  9
0x65bcd  ldloc.s  9
0x65bcf  ldc.i4.0
0x65bd0  ldarg.1
0x65bd1  stelem.ref
0x65bd2  ldloc.s  9
0x65bd4  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x65bd9  ldloc.2
0x65bda  ret
```
