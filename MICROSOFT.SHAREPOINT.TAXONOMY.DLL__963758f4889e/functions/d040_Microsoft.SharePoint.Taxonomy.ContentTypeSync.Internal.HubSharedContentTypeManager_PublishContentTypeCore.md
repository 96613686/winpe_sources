# Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::PublishContentTypeCore

- ea: `0xd040`
- end: `0xd1c7`
- name: `Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::PublishContentTypeCore`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0xca40`

## callees

- `0xd040`
- `0xd1d0`
- `0xd280`
- `0xd2a0`
- `0xd4a0`
- `0xdd00`
- `0xdd20`
- `0x55560`
- `0x56c20`
- `0x655b0`

## string_xrefs

- `0xd1bc`: `Updated the package list`
- `0xd0b4`: `Content type {0} has been exported to a local path {1}`

## pseudocode

```c

```

## disassembly

```asm
0xd040  ldarg.3
0xd041  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_PartitionId()
0xd046  stloc.0
0xd047  ldarg.2
0xd048  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Id()
0xd04d  stloc.s  4
0xd04f  ldloca.s 4
0xd051  constrained. [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId
0xd057  callvirt instance string [mscorlib]System.Object::ToString()
0xd05c  stloc.1
0xd05d  ldnull
0xd05e  stloc.2
0xd05f  ldarg.1
0xd060  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId, string> Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.PublishingContext::get_ExportedPackages()
0xd065  ldarg.2
0xd066  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Id()
0xd06b  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId, string>::ContainsKey(var<u1>)
0xd070  brfalse.s loc_D084
0xd072  ldarg.1
0xd073  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId, string> Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.PublishingContext::get_ExportedPackages()
0xd078  ldarg.2
0xd079  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Id()
0xd07e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId, string>::get_Item(void)
0xd083  stloc.2
0xd084  ldloc.2
0xd085  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd08a  brfalse.s loc_D0D9
0xd08c  ldarg.0
0xd08d  ldarg.s  4
0xd08f  ldarg.2
0xd090  call     instance string Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::ExportContentType(class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy proxy, class [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType contentType)
0xd095  stloc.2
0xd096  ldarg.1
0xd097  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId, string> Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.PublishingContext::get_ExportedPackages()
0xd09c  ldarg.2
0xd09d  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Id()
0xd0a2  ldloc.2
0xd0a3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId, string>::set_Item(var<u1>, !!T0)
0xd0a8  ldc.i4   0x62316F62
0xd0ad  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xd0b2  ldc.i4.s 0x64
0xd0b4  ldstr    aContentType0Ha// "Content type {0} has been exported to a"...
0xd0b9  ldc.i4.2
0xd0ba  newarr   [mscorlib]System.Object
0xd0bf  stloc.s  5
0xd0c1  ldloc.s  5
0xd0c3  ldc.i4.0
0xd0c4  ldarg.2
0xd0c5  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Name()
0xd0ca  stelem.ref
0xd0cb  ldloc.s  5
0xd0cd  ldc.i4.1
0xd0ce  ldloc.2
0xd0cf  stelem.ref
0xd0d0  ldloc.s  5
0xd0d2  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xd0d7  br.s     loc_D10E
0xd0d9  ldc.i4   0x637A6435
0xd0de  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xd0e3  ldc.i4.s 0x64
0xd0e5  ldstr    aContentType0Is// "Content type {0} is using a previously "...
0xd0ea  ldc.i4.2
0xd0eb  newarr   [mscorlib]System.Object
0xd0f0  stloc.s  6
0xd0f2  ldloc.s  6
0xd0f4  ldc.i4.0
0xd0f5  ldarg.2
0xd0f6  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Name()
0xd0fb  stelem.ref
0xd0fc  ldloc.s  6
0xd0fe  ldc.i4.1
0xd0ff  ldarg.s  4
0xd101  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0xd106  stelem.ref
0xd107  ldloc.s  6
0xd109  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xd10e  ldloc.2
0xd10f  ldarg.3
0xd110  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_Id()
0xd115  ldloc.0
0xd116  ldloc.1
0xd117  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubConstants::TypeIdContentType
0xd11c  call     string Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::ModifyPackageForUpload(string filePath, valuetype [mscorlib]System.Guid storeId, valuetype [mscorlib]System.Guid rawPartitionId, string packageId, valuetype [mscorlib]System.Guid typeId)
0xd121  stloc.3
0xd122  ldc.i4   0x62316F65
0xd127  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xd12c  ldc.i4.s 0x64
0xd12e  ldstr    aPreparedTheCon// "Prepared the content type package."
0xd133  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0xd138  ldarg.1
0xd139  ldarg.3
0xd13a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_Id()
0xd13f  ldarg.2
0xd140  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Id()
0xd145  ldloc.3
0xd146  callvirt instance void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.PublishingContext::SetModifiedPackage(valuetype [mscorlib]System.Guid storeId, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId contentTypeId, string modifiedPackagePath)
0xd14b  ldarg.s  4
0xd14d  ldloc.3
0xd14e  callvirt instance void Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::PublishPackage(string filePath)
0xd153  ldc.i4   0x637A6436
0xd158  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xd15d  ldc.i4.s 0x64
0xd15f  ldstr    aPublishedToTer// "Published to term store {0}"
0xd164  ldc.i4.1
0xd165  newarr   [mscorlib]System.Object
0xd16a  stloc.s  7
0xd16c  ldloc.s  7
0xd16e  ldc.i4.0
0xd16f  ldarg.3
0xd170  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_Id()
0xd175  stloc.s  8
0xd177  ldloca.s 8
0xd179  constrained. [mscorlib]System.Guid
0xd17f  callvirt instance string [mscorlib]System.Object::ToString()
0xd184  stelem.ref
0xd185  ldloc.s  7
0xd187  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xd18c  ldarg.0
0xd18d  ldarg.3
0xd18e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_Id()
0xd193  ldarg.s  5
0xd195  ldloc.1
0xd196  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubConstants::TypeIdContentType
0xd19b  ldc.i4.1
0xd19c  call     instance void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::UpdatePackageList(valuetype [mscorlib]System.Guid storeId, string serviceApplicationName, string packageId, valuetype [mscorlib]System.Guid typeId, bool isPublished)
0xd1a1  ldarg.0
0xd1a2  ldarg.s  4
0xd1a4  ldarg.2
0xd1a5  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Id()
0xd1aa  ldc.i4.1
0xd1ab  call     instance void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::Audit(class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy proxy, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId contentTypeId, bool isPublishing)
0xd1b0  ldc.i4   0x62316F67
0xd1b5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xd1ba  ldc.i4.s 0x64
0xd1bc  ldstr    aUpdatedThePack// "Updated the package list"
0xd1c1  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0xd1c6  ret
```
