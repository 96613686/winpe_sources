# Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.MetadataHubFeatureReceiver::EnsureCabListExists

- ea: `0xee60`
- end: `0xef89`
- name: `Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.MetadataHubFeatureReceiver::EnsureCabListExists`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x725c0`

## callees

- `0xee60`
- `0xf110`
- `0xf1e0`
- `0x13230`
- `0x13700`
- `0x13710`
- `0x2acd0`

## string_xrefs

- `0xef0b`: `StoreName`
- `0xef10`: `FieldDisplayNameStoreName`

## pseudocode

```c

```

## disassembly

```asm
0xee60  ldarg.0
0xee61  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPList Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubConstants::GetPackageList(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb rootWeb)
0xee66  stloc.0
0xee67  ldloc.0
0xee68  brtrue.s loc_EEBB
0xee6a  ldarg.0
0xee6b  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPListCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Lists()
0xee70  ldstr    aPackagelist// "PackageList"
0xee75  ldstr    aCablistdescrip// "CabListDescription"
0xee7a  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0xee7f  ldc.i4.s 0x64
0xee81  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPListCollection::Add(string, string, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPListTemplateType)
0xee86  stloc.1
0xee87  ldarg.0
0xee88  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPListCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Lists()
0xee8d  ldloc.1
0xee8e  ldc.i4.0
0xee8f  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPList [Microsoft.SharePoint]Microsoft.SharePoint.SPListCollection::GetList(valuetype [mscorlib]System.Guid, bool)
0xee94  stloc.0
0xee95  ldloc.0
0xee96  ldstr    aCablisttitle// "CabListTitle"
0xee9b  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0xeea0  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_Title(string)
0xeea5  ldloc.0
0xeea6  ldc.i4.1
0xeea7  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_Hidden(bool)
0xeeac  ldloc.0
0xeead  ldc.i4.0
0xeeae  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_AllowDeletion(bool)
0xeeb3  ldloc.0
0xeeb4  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::Update()
0xeeb9  br.s     loc_EEE8
0xeebb  ldc.i4.0
0xeebc  stloc.2
0xeebd  ldloc.0
0xeebe  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_Hidden()
0xeec3  brtrue.s loc_EECE
0xeec5  ldloc.0
0xeec6  ldc.i4.1
0xeec7  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_Hidden(bool)
0xeecc  ldc.i4.1
0xeecd  stloc.2
0xeece  ldloc.0
0xeecf  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_AllowDeletion()
0xeed4  brfalse.s loc_EEDF
0xeed6  ldloc.0
0xeed7  ldc.i4.0
0xeed8  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_AllowDeletion(bool)
0xeedd  ldc.i4.1
0xeede  stloc.2
0xeedf  ldloc.2
0xeee0  brfalse.s loc_EEE8
0xeee2  ldloc.0
0xeee3  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::Update()
0xeee8  ldloc.0
0xeee9  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubConstants::FieldIdStoreId
0xeeee  ldstr    aStoreid// "StoreId"
0xeef3  ldstr    aFielddisplayna// "FieldDisplayNameStoreId"
0xeef8  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0xeefd  ldc.i4.s 0xE
0xeeff  ldc.i4.1
0xef00  call     void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationUtility::AddFieldIfNotExisting(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList list, valuetype [mscorlib]System.Guid fieldId, string fieldName, string fieldDisplayName, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldType fieldType, bool isRequired)
0xef05  ldloc.0
0xef06  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubConstants::FieldIdStoreName
0xef0b  ldstr    aStorename// "StoreName"
0xef10  ldstr    aFielddisplayna_0// "FieldDisplayNameStoreName"
0xef15  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0xef1a  ldc.i4.2
0xef1b  ldc.i4.1
0xef1c  call     void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationUtility::AddFieldIfNotExisting(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList list, valuetype [mscorlib]System.Guid fieldId, string fieldName, string fieldDisplayName, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldType fieldType, bool isRequired)
0xef21  ldloc.0
0xef22  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubConstants::FieldIdPackageType
0xef27  ldstr    aPackagetype// "PackageType"
0xef2c  ldstr    aFielddisplayna_1// "FieldDisplayNamePackageType"
0xef31  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0xef36  ldc.i4.s 0xE
0xef38  ldc.i4.1
0xef39  call     void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationUtility::AddFieldIfNotExisting(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList list, valuetype [mscorlib]System.Guid fieldId, string fieldName, string fieldDisplayName, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldType fieldType, bool isRequired)
0xef3e  ldloc.0
0xef3f  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubConstants::FieldIdPackageId
0xef44  ldstr    aPackageid_0// "PackageId"
0xef49  ldstr    aFielddisplayna_2// "FieldDisplayNamePackageId"
0xef4e  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0xef53  ldc.i4.2
0xef54  ldc.i4.1
0xef55  ldc.i4.1
0xef56  call     void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationUtility::AddFieldIfNotExisting(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList list, valuetype [mscorlib]System.Guid fieldId, string fieldName, string fieldDisplayName, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldType fieldType, bool isRequired, bool isIndexed)
0xef5b  ldloc.0
0xef5c  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubConstants::FieldIdUnpublished
0xef61  ldstr    aUnpublished// "Unpublished"
0xef66  ldstr    aFielddisplayna_3// "FieldDisplayNameUnpublished"
0xef6b  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0xef70  ldc.i4.8
0xef71  ldc.i4.1
0xef72  call     void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationUtility::AddFieldIfNotExisting(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList list, valuetype [mscorlib]System.Guid fieldId, string fieldName, string fieldDisplayName, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldType fieldType, bool isRequired)
0xef77  ldloc.0
0xef78  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPBuiltInFieldId::LinkTitle
0xef7d  call     void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.MetadataHubFeatureReceiver::RemoveViewField(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList list, valuetype [mscorlib]System.Guid fieldGuid)
0xef82  ldloc.0
0xef83  call     void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.MetadataHubFeatureReceiver::SetupListSecurity(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList list)
0xef88  ret
```
