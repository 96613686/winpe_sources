# Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.MetadataHubFeatureReceiver::FeatureDeactivating

- ea: `0xecd0`
- end: `0xedca`
- name: `Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.MetadataHubFeatureReceiver::FeatureDeactivating`
- size: `250`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xecd0`
- `0x137e0`
- `0x242a0`

## string_xrefs

- `0xed3e`: `MetadataHubPreviousToken`
- `0xed50`: `MetadataHubPreviousToken`
- `0xeda9`: `Removed MetadataPublish feature from the root web`

## pseudocode

```c

```

## disassembly

```asm
0xecd0  ldarg.1
0xecd1  ldstr    aProperties_0// "properties"
0xecd6  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0xecdb  ldarg.1
0xecdc  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFeature [Microsoft.SharePoint]Microsoft.SharePoint.SPFeatureReceiverProperties::get_Feature()
0xece1  ldstr    aPropertiesFeat// "properties.Feature"
0xece6  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0xeceb  ldarg.1
0xecec  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFeature [Microsoft.SharePoint]Microsoft.SharePoint.SPFeatureReceiverProperties::get_Feature()
0xecf1  callvirt instance object [Microsoft.SharePoint]Microsoft.SharePoint.SPFeature::get_Parent()
0xecf6  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPSite
0xecfb  stloc.0
0xecfc  ldloc.0
0xecfd  brtrue.s loc_ED05
0xecff  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0xed04  throw
0xed05  ldloc.0
0xed06  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_RootWeb()
0xed0b  stloc.1
0xed0c  ldc.i4   0x3879716F
0xed11  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xed16  ldc.i4.s 0x32
0xed18  ldstr    aDeactivatingMe// "Deactivating MetadataHub feature"
0xed1d  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0xed22  ldloc.1
0xed23  ldstr    aPackagelist// "PackageList"
0xed28  call     void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationUtility::RemoveList(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb rootWeb, string listName)
0xed2d  ldloc.1
0xed2e  ldstr    aContenttypeapp// "ContentTypeAppLog"
0xed33  call     void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationUtility::RemoveList(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb rootWeb, string listName)
0xed38  ldloc.1
0xed39  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPPropertyBag [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Properties()
0xed3e  ldstr    aMetadatahubpre// "MetadataHubPreviousToken"
0xed43  callvirt instance bool [System]System.Collections.Specialized.StringDictionary::ContainsKey(string)
0xed48  brfalse.s loc_ED65
0xed4a  ldloc.1
0xed4b  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPPropertyBag [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Properties()
0xed50  ldstr    aMetadatahubpre// "MetadataHubPreviousToken"
0xed55  callvirt instance void [System]System.Collections.Specialized.StringDictionary::Remove(string)
0xed5a  ldloc.1
0xed5b  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPPropertyBag [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Properties()
0xed60  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPPropertyBag::Update()
0xed65  ldc.i4   0x38797170
0xed6a  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xed6f  ldc.i4.s 0x32
0xed71  ldstr    aRemovingMetada// "Removing MetadataPublish feature from t"...
0xed76  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0xed7b  ldloc.1
0xed7c  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFeatureCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Features()
0xed81  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.MetadataHubFeatureReceiver::PublishActionFeatureId
0xed86  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFeature [Microsoft.SharePoint]Microsoft.SharePoint.SPFeatureCollection::get_Item(valuetype [mscorlib]System.Guid)
0xed8b  brfalse.s loc_EDB3
0xed8d  ldloc.1
0xed8e  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFeatureCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Features()
0xed93  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.MetadataHubFeatureReceiver::PublishActionFeatureId
0xed98  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPFeatureCollection::Remove(valuetype [mscorlib]System.Guid)
0xed9d  ldc.i4   0x38797237
0xeda2  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xeda7  ldc.i4.s 0x32
0xeda9  ldstr    aRemovedMetadat// "Removed MetadataPublish feature from th"...
0xedae  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0xedb3  ldc.i4   0x38797266
0xedb8  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xedbd  ldc.i4.s 0x32
0xedbf  ldstr    aDeactivatedMet// "Deactivated MetadataHub feature"
0xedc4  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0xedc9  ret
```
