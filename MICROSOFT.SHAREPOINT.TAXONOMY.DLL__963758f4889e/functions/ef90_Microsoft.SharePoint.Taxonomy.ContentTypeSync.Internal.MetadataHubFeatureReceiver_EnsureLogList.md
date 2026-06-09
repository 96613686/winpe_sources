# Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.MetadataHubFeatureReceiver::EnsureLogList

- ea: `0xef90`
- end: `0xf102`
- name: `Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.MetadataHubFeatureReceiver::EnsureLogList`
- size: `370`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x108f0`
- `0x13920`
- `0x3e190`
- `0x725c0`

## callees

- `0xef90`
- `0xf110`
- `0x13670`
- `0x13700`
- `0x2acd0`

## string_xrefs

- `0xf076`: `StoreName`
- `0xf07b`: `$Resources:osrvcore,TaxFieldDisplayNameStoreName;`

## pseudocode

```c

```

## disassembly

```asm
0xef90  ldarg.0
0xef91  ldarg.1
0xef92  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPList Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationUtility::GetLogList(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb rootWeb, bool isApplicationLog)
0xef97  stloc.0
0xef98  ldloc.0
0xef99  brtrue   loc_F024
0xef9e  ldarg.1
0xef9f  brtrue.s loc_EFA8
0xefa1  ldstr    aListsContentty// "lists/ContentTypeSyncLog"
0xefa6  br.s     loc_EFAD
0xefa8  ldstr    aListsContentty_0// "lists/ContentTypeAppLog"
0xefad  stloc.1
0xefae  ldarg.1
0xefaf  brtrue.s loc_EFBD
0xefb1  ldstr    aSubscriberlogl// "SubscriberLogListDescription"
0xefb6  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0xefbb  br.s     loc_EFC7
0xefbd  ldstr    aApplicationlog// "ApplicationLogListDescription"
0xefc2  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0xefc7  stloc.2
0xefc8  ldarg.1
0xefc9  brtrue.s loc_EFD2
0xefcb  ldstr    aResourcesOsrvc// "$Resources:osrvcore,ContentTypeSyncErro"...
0xefd0  br.s     loc_EFD7
0xefd2  ldstr    aResourcesOsrvc_0// "$Resources:osrvcore,ContentTypeApplicat"...
0xefd7  stloc.3
0xefd8  ldarg.0
0xefd9  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPListCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Lists()
0xefde  ldloc.3
0xefdf  ldloc.2
0xefe0  ldloc.1
0xefe1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xefe6  stloc.s  6
0xefe8  ldloca.s 6
0xefea  constrained. [mscorlib]System.Guid
0xeff0  callvirt instance string [mscorlib]System.Object::ToString()
0xeff5  ldc.i4.s 0x64
0xeff7  ldnull
0xeff8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPListCollection::Add(string, string, string, string, int32, string)
0xeffd  stloc.s  4
0xefff  ldarg.0
0xf000  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPListCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Lists()
0xf005  ldloc.s  4
0xf007  ldc.i4.0
0xf008  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPList [Microsoft.SharePoint]Microsoft.SharePoint.SPListCollection::GetList(valuetype [mscorlib]System.Guid, bool)
0xf00d  stloc.0
0xf00e  ldloc.0
0xf00f  ldc.i4.1
0xf010  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_Hidden(bool)
0xf015  ldloc.0
0xf016  ldc.i4.0
0xf017  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_AllowDeletion(bool)
0xf01c  ldloc.0
0xf01d  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::Update()
0xf022  br.s     loc_F055
0xf024  ldc.i4.0
0xf025  stloc.s  5
0xf027  ldloc.0
0xf028  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_Hidden()
0xf02d  brtrue.s loc_F039
0xf02f  ldloc.0
0xf030  ldc.i4.1
0xf031  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_Hidden(bool)
0xf036  ldc.i4.1
0xf037  stloc.s  5
0xf039  ldloc.0
0xf03a  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_AllowDeletion()
0xf03f  brfalse.s loc_F04B
0xf041  ldloc.0
0xf042  ldc.i4.0
0xf043  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::set_AllowDeletion(bool)
0xf048  ldc.i4.1
0xf049  stloc.s  5
0xf04b  ldloc.s  5
0xf04d  brfalse.s loc_F055
0xf04f  ldloc.0
0xf050  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPList::Update()
0xf055  ldarg.1
0xf056  brfalse.s loc_F09F
0xf058  ldloc.0
0xf059  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubConstants::FieldIdStoreId
0xf05e  ldstr    aStoreid// "StoreId"
0xf063  ldstr    aResourcesOsrvc_1// "$Resources:osrvcore,TaxFieldDisplayName"...
0xf068  ldc.i4.s 0xE
0xf06a  ldc.i4.1
0xf06b  call     void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationUtility::AddFieldIfNotExisting(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList list, valuetype [mscorlib]System.Guid fieldId, string fieldName, string fieldDisplayName, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldType fieldType, bool isRequired)
0xf070  ldloc.0
0xf071  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubConstants::FieldIdStoreName
0xf076  ldstr    aStorename// "StoreName"
0xf07b  ldstr    aResourcesOsrvc_2// "$Resources:osrvcore,TaxFieldDisplayName"...
0xf080  ldc.i4.2
0xf081  ldc.i4.1
0xf082  call     void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationUtility::AddFieldIfNotExisting(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList list, valuetype [mscorlib]System.Guid fieldId, string fieldName, string fieldDisplayName, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldType fieldType, bool isRequired)
0xf087  ldloc.0
0xf088  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubConstants::FieldIdSubscriberSiteUrl
0xf08d  ldstr    aSiteurl// "SiteUrl"
0xf092  ldstr    aResourcesOsrvc_3// "$Resources:osrvcore,TaxFieldDisplayName"...
0xf097  ldc.i4.s 0xB
0xf099  ldc.i4.1
0xf09a  call     void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationUtility::AddFieldIfNotExisting(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList list, valuetype [mscorlib]System.Guid fieldId, string fieldName, string fieldDisplayName, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldType fieldType, bool isRequired)
0xf09f  ldloc.0
0xf0a0  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationUtility::FieldIdPublishedObjectName
0xf0a5  ldstr    aPublishedobjec// "PublishedObjectName"
0xf0aa  ldstr    aResourcesOsrvc_4// "$Resources:osrvcore,TaxFieldDisplayName"...
0xf0af  ldc.i4.2
0xf0b0  ldc.i4.0
0xf0b1  call     void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationUtility::AddFieldIfNotExisting(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList list, valuetype [mscorlib]System.Guid fieldId, string fieldName, string fieldDisplayName, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldType fieldType, bool isRequired)
0xf0b6  ldloc.0
0xf0b7  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationUtility::FieldIdFailureStage
0xf0bc  ldstr    aFailureStage// "Failure Stage"
0xf0c1  ldstr    aResourcesOsrvc_5// "$Resources:osrvcore,TaxFieldDisplayName"...
0xf0c6  ldc.i4.2
0xf0c7  ldc.i4.1
0xf0c8  call     void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationUtility::AddFieldIfNotExisting(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList list, valuetype [mscorlib]System.Guid fieldId, string fieldName, string fieldDisplayName, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldType fieldType, bool isRequired)
0xf0cd  ldloc.0
0xf0ce  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationUtility::FieldIdFailureMessage
0xf0d3  ldstr    aFailureMessage// "Failure Message"
0xf0d8  ldstr    aResourcesOsrvc_6// "$Resources:osrvcore,TaxFieldDisplayName"...
0xf0dd  ldc.i4.2
0xf0de  ldc.i4.1
0xf0df  call     void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationUtility::AddFieldIfNotExisting(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList list, valuetype [mscorlib]System.Guid fieldId, string fieldName, string fieldDisplayName, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldType fieldType, bool isRequired)
0xf0e4  ldloc.0
0xf0e5  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationUtility::FieldIdFailureTime
0xf0ea  ldstr    aFailureTime// "Failure Time"
0xf0ef  ldstr    aResourcesOsrvc_7// "$Resources:osrvcore,TaxFieldDisplayName"...
0xf0f4  ldc.i4.4
0xf0f5  ldc.i4.1
0xf0f6  call     void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationUtility::AddFieldIfNotExisting(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList list, valuetype [mscorlib]System.Guid fieldId, string fieldName, string fieldDisplayName, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldType fieldType, bool isRequired)
0xf0fb  ldloc.0
0xf0fc  call     void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.MetadataHubFeatureReceiver::SetupListSecurity(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList list)
0xf101  ret
```
