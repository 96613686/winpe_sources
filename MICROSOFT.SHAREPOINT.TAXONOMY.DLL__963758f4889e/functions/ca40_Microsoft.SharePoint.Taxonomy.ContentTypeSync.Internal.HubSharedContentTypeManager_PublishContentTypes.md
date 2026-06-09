# Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::PublishContentTypes

- ea: `0xca40`
- end: `0xccd9`
- name: `Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::PublishContentTypes`
- size: `665`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x72060`

## callees

- `0xca40`
- `0xd000`
- `0xd020`
- `0xd040`
- `0xdb00`
- `0xdcd0`
- `0xdce0`
- `0xdd60`
- `0xe9a0`
- `0x13520`
- `0x2acd0`
- `0x4ce10`
- `0x55560`
- `0x65250`

## string_xrefs

- `0xcae1`: `Metadata web service application proxy {0} is not in a working state. Skip it.`
- `0xcba4`: `Skipped term store {0} for content type {1} because it has been processed already.`

## pseudocode

```c

```

## disassembly

```asm
0xca40  newobj   instance void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.PublishingContext::.ctor()
0xca45  stloc.0
0xca46  ldarg.1
0xca47  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType>::get_Count()
0xca4c  brtrue.s loc_CA55
0xca4e  ldloc.0
0xca4f  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy, bool> Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.PublishingContext::get_Result()
0xca54  ret
0xca55  ldarg.1
0xca56  ldc.i4.0
0xca57  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType>::get_Item(!!T0)
0xca5c  stloc.1
0xca5d  ldarg.0
0xca5e  call     instance void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::EnsureTemporaryFolder()
0xca63  ldarg.0
0xca64  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy> Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::get_RelevantProxyList()
0xca69  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>::GetEnumerator()
0xca6e  stloc.s  8
0xca70  br       loc_CC97
0xca75  ldloca.s 8
0xca77  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>::get_Current()
0xca7c  stloc.2
0xca7d  ldarg.0
0xca7e  ldfld    class Microsoft.SharePoint.Taxonomy.TaxonomySession Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::session
0xca83  ldloc.2
0xca84  callvirt instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomySession::GetTermStore(class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy proxy)
0xca89  stloc.3
0xca8a  ldloc.3
0xca8b  brtrue   loc_CB11
0xca90  ldarg.0
0xca91  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::hubWeb
0xca96  ldloc.2
0xca97  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0xca9c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xcaa1  ldsfld   string [mscorlib]System.String::Empty
0xcaa6  ldstr    asc_794BA// ""
0xcaab  ldloc.1
0xcaac  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Name()
0xcab1  ldnull
0xcab2  ldc.i4.1
0xcab3  call     string Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationUtility::GetReadableStatus(valuetype Microsoft.SharePoint.Taxonomy.ContentTypeSync.SyndicationStatus status)
0xcab8  ldstr    aErrortermstore// "ErrorTermStoreNotFound"
0xcabd  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0xcac2  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xcac7  stloc.s  9
0xcac9  ldloca.s 9
0xcacb  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToLocalTime()
0xcad0  call     void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubTimerJobDefinition::AddLogItem(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb rootWeb, string proxyName, valuetype [mscorlib]System.Guid storeId, string serviceApplicationName, string siteUrl, string objectName, string stage, string stageMessage, string message, valuetype [mscorlib]System.DateTime createdTime)
0xcad5  ldc.i4   0x62316F63
0xcada  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xcadf  ldc.i4.s 0xF
0xcae1  ldstr    aMetadataWebSer// "Metadata web service application proxy "...
0xcae6  ldc.i4.1
0xcae7  newarr   [mscorlib]System.Object
0xcaec  stloc.s  0xA
0xcaee  ldloc.s  0xA
0xcaf0  ldc.i4.0
0xcaf1  ldloc.2
0xcaf2  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0xcaf7  stelem.ref
0xcaf8  ldloc.s  0xA
0xcafa  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xcaff  ldloc.0
0xcb00  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy, bool> Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.PublishingContext::get_Result()
0xcb05  ldloc.2
0xcb06  ldc.i4.0
0xcb07  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy, bool>::set_Item(var<u1>, !!T0)
0xcb0c  br       loc_CC97
0xcb11  ldloc.3
0xcb12  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_Id()
0xcb17  stloc.s  4
0xcb19  ldc.i4   0x62316F64
0xcb1e  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xcb23  ldc.i4.s 0x64
0xcb25  ldstr    aPublishingToTe// "Publishing to term store {0}"
0xcb2a  ldc.i4.1
0xcb2b  newarr   [mscorlib]System.Object
0xcb30  stloc.s  0xB
0xcb32  ldloc.s  0xB
0xcb34  ldc.i4.0
0xcb35  ldloca.s 4
0xcb37  constrained. [mscorlib]System.Guid
0xcb3d  callvirt instance string [mscorlib]System.Object::ToString()
0xcb42  stelem.ref
0xcb43  ldloc.s  0xB
0xcb45  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xcb4a  ldloca.s 4
0xcb4c  constrained. [mscorlib]System.Guid
0xcb52  callvirt instance string [mscorlib]System.Object::ToString()
0xcb57  stloc.s  5
0xcb59  ldloc.2
0xcb5a  callvirt instance string Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::get_ServiceApplicationName()
0xcb5f  stloc.s  5
0xcb61  ldarg.1
0xcb62  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType>::GetEnumerator()
0xcb67  stloc.s  0xC
0xcb69  br.s     loc_CBDC
0xcb6b  ldloca.s 0xC
0xcb6d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType>::get_Current()
0xcb72  stloc.s  6
0xcb74  ldloc.0
0xcb75  ldloc.s  6
0xcb77  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Id()
0xcb7c  ldloc.3
0xcb7d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_Id()
0xcb82  callvirt instance bool Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.PublishingContext::ContainsModifiedPackage(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId contentTypeId, valuetype [mscorlib]System.Guid storeId)
0xcb87  brtrue.s loc_CB98
0xcb89  ldarg.0
0xcb8a  ldloc.0
0xcb8b  ldloc.s  6
0xcb8d  ldloc.3
0xcb8e  ldloc.2
0xcb8f  ldloc.s  5
0xcb91  call     instance void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::PublishContentTypeCore(class Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.PublishingContext publishingContext, class [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType contentType, class Microsoft.SharePoint.Taxonomy.TermStore store, class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy proxy, string serviceApplicationName)
0xcb96  br.s     loc_CBDC
0xcb98  ldc.i4   0x637A6434
0xcb9d  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xcba2  ldc.i4.s 0x64
0xcba4  ldstr    aSkippedTermSto// "Skipped term store {0} for content type"...
0xcba9  ldc.i4.2
0xcbaa  newarr   [mscorlib]System.Object
0xcbaf  stloc.s  0xD
0xcbb1  ldloc.s  0xD
0xcbb3  ldc.i4.0
0xcbb4  ldloc.3
0xcbb5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_Id()
0xcbba  stloc.s  0xE
0xcbbc  ldloca.s 0xE
0xcbbe  constrained. [mscorlib]System.Guid
0xcbc4  callvirt instance string [mscorlib]System.Object::ToString()
0xcbc9  stelem.ref
0xcbca  ldloc.s  0xD
0xcbcc  ldc.i4.1
0xcbcd  ldloc.s  6
0xcbcf  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Name()
0xcbd4  stelem.ref
0xcbd5  ldloc.s  0xD
0xcbd7  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xcbdc  ldloca.s 0xC
0xcbde  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType>::MoveNext()
0xcbe3  brtrue.s loc_CB6B
0xcbe5  leave.s  loc_CBF5
0xcbe7  ldloca.s 0xC
0xcbe9  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType>
0xcbef  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcbf4  endfinally
0xcbf5  ldloc.0
0xcbf6  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy, bool> Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.PublishingContext::get_Result()
0xcbfb  ldloc.2
0xcbfc  ldc.i4.1
0xcbfd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy, bool>::set_Item(var<u1>, !!T0)
0xcc02  leave    loc_CC97
0xcc07  stloc.s  7
0xcc09  ldc.i4   0x666A3275
0xcc0e  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xcc13  ldc.i4.s 0xA
0xcc15  ldstr    aContentTypePub// "Content type publish failed with except"...
0xcc1a  ldc.i4.3
0xcc1b  newarr   [mscorlib]System.Object
0xcc20  stloc.s  0xF
0xcc22  ldloc.s  0xF
0xcc24  ldc.i4.0
0xcc25  ldloc.2
0xcc26  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0xcc2b  stelem.ref
0xcc2c  ldloc.s  0xF
0xcc2e  ldc.i4.1
0xcc2f  ldloc.1
0xcc30  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Name()
0xcc35  stelem.ref
0xcc36  ldloc.s  0xF
0xcc38  ldc.i4.2
0xcc39  ldloc.s  7
0xcc3b  callvirt instance string [mscorlib]System.Object::ToString()
0xcc40  stelem.ref
0xcc41  ldloc.s  0xF
0xcc43  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xcc48  ldarg.0
0xcc49  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::hubWeb
0xcc4e  ldloc.2
0xcc4f  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0xcc54  ldloc.3
0xcc55  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_Id()
0xcc5a  ldloc.s  5
0xcc5c  ldstr    asc_794BA// ""
0xcc61  ldloc.1
0xcc62  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Name()
0xcc67  ldnull
0xcc68  ldc.i4.1
0xcc69  call     string Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationUtility::GetReadableStatus(valuetype Microsoft.SharePoint.Taxonomy.ContentTypeSync.SyndicationStatus status)
0xcc6e  ldloc.s  7
0xcc70  callvirt instance string [mscorlib]System.Exception::get_Message()
0xcc75  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xcc7a  stloc.s  0x10
0xcc7c  ldloca.s 0x10
0xcc7e  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToLocalTime()
0xcc83  call     void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubTimerJobDefinition::AddLogItem(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb rootWeb, string proxyName, valuetype [mscorlib]System.Guid storeId, string serviceApplicationName, string siteUrl, string objectName, string stage, string stageMessage, string message, valuetype [mscorlib]System.DateTime createdTime)
0xcc88  ldloc.0
0xcc89  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy, bool> Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.PublishingContext::get_Result()
0xcc8e  ldloc.2
0xcc8f  ldc.i4.0
0xcc90  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy, bool>::set_Item(var<u1>, !!T0)
0xcc95  leave.s  loc_CC97
0xcc97  ldloca.s 8
0xcc99  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>::MoveNext()
0xcc9e  brtrue   loc_CA75
0xcca3  leave.s  loc_CCB3
0xcca5  ldloca.s 8
0xcca7  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>
0xccad  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xccb2  endfinally
0xccb3  leave.s  loc_CCBC
0xccb5  ldarg.0
0xccb6  call     instance void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::CleanUpTemporaryFolder()
0xccbb  endfinally
0xccbc  ldc.i4   0x62316F69
0xccc1  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xccc6  ldc.i4.s 0x64
0xccc8  ldstr    aPublishcontent// "PublishContentType ends for content typ"...
0xcccd  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0xccd2  ldloc.0
0xccd3  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy, bool> Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.PublishingContext::get_Result()
0xccd8  ret
```
