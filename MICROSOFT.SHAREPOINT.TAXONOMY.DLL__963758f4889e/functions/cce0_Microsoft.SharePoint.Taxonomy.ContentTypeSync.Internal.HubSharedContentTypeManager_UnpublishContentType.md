# Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::UnpublishContentType

- ea: `0xcce0`
- end: `0xcff9`
- name: `Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::UnpublishContentType`
- size: `793`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xc9d0`
- `0x720a0`

## callees

- `0xcce0`
- `0xd1d0`
- `0xd2a0`
- `0xdb00`
- `0xe9a0`
- `0x13520`
- `0x2acd0`
- `0x4ce10`
- `0x55560`
- `0x56c20`
- `0x65250`
- `0x655e0`

## string_xrefs

- `0xcdc3`: `Metadata web service application proxy {0} is not in a working state. Skip it.`
- `0xcece`: `Updated the package list`

## pseudocode

```c

```

## disassembly

```asm
0xcce0  ldc.i4   0x62316F6A
0xcce5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xccea  ldc.i4.s 0x64
0xccec  ldstr    aUnpublishconte// "UnpublishContentType starts for content"...
0xccf1  ldc.i4.1
0xccf2  newarr   [mscorlib]System.Object
0xccf7  stloc.s  0xB
0xccf9  ldloc.s  0xB
0xccfb  ldc.i4.0
0xccfc  ldarga.s 1
0xccfe  constrained. [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId
0xcd04  callvirt instance string [mscorlib]System.Object::ToString()
0xcd09  stelem.ref
0xcd0a  ldloc.s  0xB
0xcd0c  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xcd11  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0xcd16  stloc.0
0xcd17  ldarga.s 1
0xcd19  constrained. [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId
0xcd1f  callvirt instance string [mscorlib]System.Object::ToString()
0xcd24  stloc.1
0xcd25  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy, bool>::.ctor()
0xcd2a  stloc.2
0xcd2b  ldarg.0
0xcd2c  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy> Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::get_RelevantProxyList()
0xcd31  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>::GetEnumerator()
0xcd36  stloc.s  0xC
0xcd38  br       loc_CFAA
0xcd3d  ldloca.s 0xC
0xcd3f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>::get_Current()
0xcd44  stloc.3
0xcd45  ldarg.0
0xcd46  ldfld    class Microsoft.SharePoint.Taxonomy.TaxonomySession Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::session
0xcd4b  ldloc.3
0xcd4c  callvirt instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomySession::GetTermStore(class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy proxy)
0xcd51  stloc.s  4
0xcd53  ldloc.s  4
0xcd55  brtrue   loc_CDEE
0xcd5a  ldarg.2
0xcd5b  stloc.s  5
0xcd5d  ldloc.s  5
0xcd5f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xcd64  brfalse.s loc_CD75
0xcd66  ldarga.s 1
0xcd68  constrained. [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId
0xcd6e  callvirt instance string [mscorlib]System.Object::ToString()
0xcd73  stloc.s  5
0xcd75  ldarg.0
0xcd76  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::hubWeb
0xcd7b  ldloc.3
0xcd7c  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0xcd81  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xcd86  ldsfld   string [mscorlib]System.String::Empty
0xcd8b  ldstr    asc_794BA// ""
0xcd90  ldloc.s  5
0xcd92  ldnull
0xcd93  ldc.i4.s 0x10
0xcd95  call     string Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationUtility::GetReadableStatus(valuetype Microsoft.SharePoint.Taxonomy.ContentTypeSync.SyndicationStatus status)
0xcd9a  ldstr    aErrortermstore// "ErrorTermStoreNotFound"
0xcd9f  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0xcda4  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xcda9  stloc.s  0xD
0xcdab  ldloca.s 0xD
0xcdad  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToLocalTime()
0xcdb2  call     void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubTimerJobDefinition::AddLogItem(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb rootWeb, string proxyName, valuetype [mscorlib]System.Guid storeId, string serviceApplicationName, string siteUrl, string objectName, string stage, string stageMessage, string message, valuetype [mscorlib]System.DateTime createdTime)
0xcdb7  ldc.i4   0x62316F6B
0xcdbc  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xcdc1  ldc.i4.s 0xF
0xcdc3  ldstr    aMetadataWebSer// "Metadata web service application proxy "...
0xcdc8  ldc.i4.1
0xcdc9  newarr   [mscorlib]System.Object
0xcdce  stloc.s  0xE
0xcdd0  ldloc.s  0xE
0xcdd2  ldc.i4.0
0xcdd3  ldloc.3
0xcdd4  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0xcdd9  stelem.ref
0xcdda  ldloc.s  0xE
0xcddc  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xcde1  ldloc.2
0xcde2  ldloc.3
0xcde3  ldc.i4.0
0xcde4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy, bool>::set_Item(var<u1>, !!T0)
0xcde9  br       loc_CFAA
0xcdee  ldloc.s  4
0xcdf0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_Id()
0xcdf5  stloc.s  6
0xcdf7  ldc.i4   0x62316F6C
0xcdfc  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xce01  ldc.i4.s 0x64
0xce03  ldstr    aUnpublishingCo// "Unpublishing content type to term store"...
0xce08  ldc.i4.1
0xce09  newarr   [mscorlib]System.Object
0xce0e  stloc.s  0xF
0xce10  ldloc.s  0xF
0xce12  ldc.i4.0
0xce13  ldloca.s 6
0xce15  constrained. [mscorlib]System.Guid
0xce1b  callvirt instance string [mscorlib]System.Object::ToString()
0xce20  stelem.ref
0xce21  ldloc.s  0xF
0xce23  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xce28  ldloc.0
0xce29  ldloc.s  6
0xce2b  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0xce30  brtrue   loc_CF79
0xce35  ldloca.s 6
0xce37  constrained. [mscorlib]System.Guid
0xce3d  callvirt instance string [mscorlib]System.Object::ToString()
0xce42  stloc.s  7
0xce44  ldloc.0
0xce45  ldloc.s  6
0xce47  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0xce4c  ldloc.3
0xce4d  callvirt instance string Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::get_ServiceApplicationName()
0xce52  stloc.s  8
0xce54  ldloc.s  8
0xce56  stloc.s  7
0xce58  ldloc.s  4
0xce5a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_PartitionId()
0xce5f  stloc.s  9
0xce61  ldloc.3
0xce62  ldloc.s  9
0xce64  ldloc.1
0xce65  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubConstants::TypeIdContentType
0xce6a  callvirt instance void Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::UnpublishPackage(valuetype [mscorlib]System.Guid rawPartitionId, string packageId, valuetype [mscorlib]System.Guid packageType)
0xce6f  ldc.i4   0x62316F6D
0xce74  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xce79  ldc.i4.s 0x64
0xce7b  ldstr    aUnpublishedThe// "Unpublished the content type on term st"...
0xce80  ldc.i4.1
0xce81  newarr   [mscorlib]System.Object
0xce86  stloc.s  0x10
0xce88  ldloc.s  0x10
0xce8a  ldc.i4.0
0xce8b  ldloca.s 6
0xce8d  constrained. [mscorlib]System.Guid
0xce93  callvirt instance string [mscorlib]System.Object::ToString()
0xce98  stelem.ref
0xce99  ldloc.s  0x10
0xce9b  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xcea0  ldarg.0
0xcea1  ldloc.s  6
0xcea3  ldloc.s  8
0xcea5  ldloc.1
0xcea6  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubConstants::TypeIdContentType
0xceab  ldc.i4.0
0xceac  call     instance void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::UpdatePackageList(valuetype [mscorlib]System.Guid storeId, string serviceApplicationName, string packageId, valuetype [mscorlib]System.Guid typeId, bool isPublished)
0xceb1  ldloc.2
0xceb2  ldloc.3
0xceb3  ldc.i4.1
0xceb4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy, bool>::set_Item(var<u1>, !!T0)
0xceb9  ldarg.0
0xceba  ldloc.3
0xcebb  ldarg.1
0xcebc  ldc.i4.0
0xcebd  call     instance void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::Audit(class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy proxy, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId contentTypeId, bool isPublishing)
0xcec2  ldc.i4   0x62316F6E
0xcec7  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xcecc  ldc.i4.s 0x64
0xcece  ldstr    aUpdatedThePack// "Updated the package list"
0xced3  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0xced8  leave    loc_CFAA
0xcedd  stloc.s  0xA
0xcedf  ldc.i4   0x63683576
0xcee4  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xcee9  ldc.i4.s 0xA
0xceeb  ldstr    aFailedToUnpubl// "Failed to unpublish content type {0} fo"...
0xcef0  ldc.i4.3
0xcef1  newarr   [mscorlib]System.Object
0xcef6  stloc.s  0x11
0xcef8  ldloc.s  0x11
0xcefa  ldc.i4.0
0xcefb  ldarga.s 1
0xcefd  constrained. [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId
0xcf03  callvirt instance string [mscorlib]System.Object::ToString()
0xcf08  stelem.ref
0xcf09  ldloc.s  0x11
0xcf0b  ldc.i4.1
0xcf0c  ldloc.3
0xcf0d  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0xcf12  stelem.ref
0xcf13  ldloc.s  0x11
0xcf15  ldc.i4.2
0xcf16  ldloc.s  0xA
0xcf18  callvirt instance string [mscorlib]System.Object::ToString()
0xcf1d  stelem.ref
0xcf1e  ldloc.s  0x11
0xcf20  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xcf25  ldloc.2
0xcf26  ldloc.3
0xcf27  ldc.i4.0
0xcf28  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy, bool>::set_Item(var<u1>, !!T0)
0xcf2d  ldarg.0
0xcf2e  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::hubWeb
0xcf33  ldloc.3
0xcf34  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0xcf39  ldloc.s  6
0xcf3b  ldloc.s  7
0xcf3d  ldarg.0
0xcf3e  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::hubWeb
0xcf43  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Url()
0xcf48  ldarga.s 1
0xcf4a  constrained. [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId
0xcf50  callvirt instance string [mscorlib]System.Object::ToString()
0xcf55  ldnull
0xcf56  ldc.i4.s 0x10
0xcf58  call     string Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationUtility::GetReadableStatus(valuetype Microsoft.SharePoint.Taxonomy.ContentTypeSync.SyndicationStatus status)
0xcf5d  ldloc.s  0xA
0xcf5f  callvirt instance string [mscorlib]System.Exception::get_Message()
0xcf64  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xcf69  stloc.s  0x12
0xcf6b  ldloca.s 0x12
0xcf6d  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToLocalTime()
0xcf72  call     void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubTimerJobDefinition::AddLogItem(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb rootWeb, string proxyName, valuetype [mscorlib]System.Guid storeId, string serviceApplicationName, string siteUrl, string objectName, string stage, string stageMessage, string message, valuetype [mscorlib]System.DateTime createdTime)
0xcf77  leave.s  loc_CFAA
0xcf79  ldc.i4   0x62316F6F
0xcf7e  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xcf83  ldc.i4.s 0x64
0xcf85  ldstr    aSkippedTermSto_0// "Skipped term store {0} because it has b"...
0xcf8a  ldc.i4.1
0xcf8b  newarr   [mscorlib]System.Object
0xcf90  stloc.s  0x13
0xcf92  ldloc.s  0x13
0xcf94  ldc.i4.0
0xcf95  ldloca.s 6
0xcf97  constrained. [mscorlib]System.Guid
0xcf9d  callvirt instance string [mscorlib]System.Object::ToString()
0xcfa2  stelem.ref
0xcfa3  ldloc.s  0x13
0xcfa5  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xcfaa  ldloca.s 0xC
0xcfac  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>::MoveNext()
0xcfb1  brtrue   loc_CD3D
0xcfb6  leave.s  loc_CFC6
0xcfb8  ldloca.s 0xC
0xcfba  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>
0xcfc0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcfc5  endfinally
0xcfc6  ldc.i4   0x62316F70
0xcfcb  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xcfd0  ldc.i4.s 0x64
0xcfd2  ldstr    aUnpublishconte_0// "UnpublishContentType ends for content t"...
0xcfd7  ldc.i4.1
0xcfd8  newarr   [mscorlib]System.Object
0xcfdd  stloc.s  0x14
0xcfdf  ldloc.s  0x14
0xcfe1  ldc.i4.0
0xcfe2  ldarga.s 1
0xcfe4  constrained. [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId
0xcfea  callvirt instance string [mscorlib]System.Object::ToString()
0xcfef  stelem.ref
0xcff0  ldloc.s  0x14
0xcff2  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xcff7  ldloc.2
0xcff8  ret
```
