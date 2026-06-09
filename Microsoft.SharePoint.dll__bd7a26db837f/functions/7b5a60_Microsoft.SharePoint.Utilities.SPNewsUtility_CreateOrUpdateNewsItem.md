# Microsoft.SharePoint.Utilities.SPNewsUtility::CreateOrUpdateNewsItem

- ea: `0x7b5a60`
- end: `0x7b5e7f`
- name: `Microsoft.SharePoint.Utilities.SPNewsUtility::CreateOrUpdateNewsItem`
- size: `1055`
- prototype: ``
- caller_count: `0`
- callee_count: `39`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1b7dd0`
- `0x343400`
- `0x348fc0`
- `0x3e99a0`
- `0x3e99f0`
- `0x3e9a20`
- `0x3e9a30`
- `0x4cd8e0`
- `0x4cddc0`
- `0x4e7720`
- `0x5c1130`
- `0x678580`
- `0x6c9890`
- `0x7b5a60`
- `0x7b69b0`
- `0x7b6c10`
- `0x7b7130`
- `0x7b7150`
- `0x7b7170`
- `0x7b7190`
- `0x7b71b0`
- `0x7b71d0`
- `0x7b71f0`
- `0x7b7210`
- `0x7b7230`
- `0x7b7320`
- `0x7b7340`
- `0x7b7360`
- `0x7b7380`
- `0x7b73a0`
- `0x7b73c0`
- `0x7b84c0`
- `0x7be4d0`
- `0x7be510`
- `0x7be550`
- `0x7be580`
- `0x7bea40`
- `0x7beb40`
- `0x8ecdb0`

## string_xrefs

- `0x7b5a6e`: `SPNewsCreateOrUpdateNewsItemKillSwitch`
- `0x7b5a9b`: `SPNewsUtility.CreateOrUpdateNewsItem`
- `0x7b5ad1`: `SPNewsUtility.CreateOrUpdateNewsItem`
- `0x7b5aeb`: `SPNewsUtility.CreateOrUpdateNewsItem: Argument null exception`
- `0x7b5b0c`: `SPNewsUtility.CreateOrUpdateNewsItem: Create`
- `0x7b5b44`: `SPNewsUtility.CreateOrUpdateNewsItem: Update`
- `0x7b5b8b`: `SPNewsUtility.CreateOrUpdateNewsItem: attempted update on non-existent item`
- `0x7b5d8e`: `SPNewsUtility.CreateOrUpdateNewsItem: SPSpotlightResultCode.TooManyItems`
- `0x7b5db5`: `SPNewsUtility.CreateOrUpdateNewsItem: SPSpotlightResultCode.FolderDoesNotExist`
- `0x7b5dd2`: `SPNewsUtility.CreateOrUpdateNewsItem: SPSpotlightResultCode.ItemDoesNotExist`
- `0x7b5def`: `SPNewsUtility.CreateOrUpdateNewsItem: SPSpotlightResultCode.ItemNotInSpotlight`
- `0x7b5e0c`: `SPNewsUtility.CreateOrUpdateNewsItem: SPSpotlightResultCode.InvalidArgument`
- `0x7b5e29`: `SPNewsUtility.CreateOrUpdateNewsItem: SPSpotlightResultCode.ServerError`

## pseudocode

```c

```

## disassembly

```asm
0x7b5a60  ldc.i4.0
0x7b5a61  stloc.0
0x7b5a62  ldc.i4.0
0x7b5a63  stloc.1
0x7b5a64  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Utilities.SPNewsUtility::CREATE_OR_UPDATE_KILL_SWITCH_GUID
0x7b5a69  ldstr    a09082016// "09/08/2016"
0x7b5a6e  ldstr    aSpnewscreateor// "SPNewsCreateOrUpdateNewsItemKillSwitch"
0x7b5a73  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x7b5a78  brtrue   loc_7B5E76
0x7b5a7d  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0x7b5a82  brfalse  loc_7B5E70
0x7b5a87  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0x7b5a8c  ldc.i4   0x23D
0x7b5a91  call     bool Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsExpFeatureToggleEnabled(class Microsoft.SharePoint.SPContext spContext, valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId featureId)
0x7b5a96  brfalse  loc_7B5E70
0x7b5a9b  ldstr    aSpnewsutilityC// "SPNewsUtility.CreateOrUpdateNewsItem"
0x7b5aa0  ldc.i4   0x11DE841
0x7b5aa5  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x7b5aaa  ldc.i4   0x11DE842
0x7b5aaf  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x7b5ab4  ldc.i4   0x11DE843
0x7b5ab9  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x7b5abe  ldc.i4.0
0x7b5abf  ldnull
0x7b5ac0  newobj   instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitor::.ctor(string scenarioName, unsigned int32 startTag, unsigned int32 successTag, unsigned int32 unexpectedFailureTag, [opt] valuetype Microsoft.SharePoint.Administration.SPLogType logType, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x7b5ac5  stloc.2
0x7b5ac6  ldloc.2
0x7b5ac7  ldc.i4   0x11DE844
0x7b5acc  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x7b5ad1  ldstr    aSpnewsutilityC// "SPNewsUtility.CreateOrUpdateNewsItem"
0x7b5ad6  ldloca.s 0
0x7b5ad8  call     void Microsoft.SharePoint.Utilities.SPNewsUtility::ThrowIfNoContextWeb(class Microsoft.SharePoint.Utilities.SPReliabilityMonitor monitor, unsigned int32 tag, string monitorPrefix, [out] bool& failureLogged)
0x7b5add  ldarg.0
0x7b5ade  brtrue.s loc_7B5AFE
0x7b5ae0  ldloc.2
0x7b5ae1  ldc.i4   0x11DE845
0x7b5ae6  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x7b5aeb  ldstr    aSpnewsutilityC_0// "SPNewsUtility.CreateOrUpdateNewsItem: A"...
0x7b5af0  ldnull
0x7b5af1  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x7b5af6  ldc.i4.1
0x7b5af7  stloc.0
0x7b5af8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor()
0x7b5afd  throw
0x7b5afe  ldarg.0
0x7b5aff  callvirt instance int32 Microsoft.SharePoint.Utilities.SPNewsItem::get_itemId()
0x7b5b04  ldc.i4.0
0x7b5b05  bgt.s    loc_7B5B3F
0x7b5b07  ldc.i4   0x13100C1
0x7b5b0c  ldstr    aSpnewsutilityC_1// "SPNewsUtility.CreateOrUpdateNewsItem: C"...
0x7b5b11  ldnull
0x7b5b12  ldloca.s 0xB
0x7b5b14  initobj  [mscorlib]System.Guid
0x7b5b1a  ldloc.s  0xB
0x7b5b1c  ldnull
0x7b5b1d  ldnull
0x7b5b1e  call     void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::WriteUsageTag(unsigned int32 tag, string devCommentIgnored, [opt] string userLogin, [opt] valuetype [mscorlib]System.Guid siteSubscriptionId, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, [opt] string userAgent)
0x7b5b23  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0x7b5b28  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPContext::get_Web()
0x7b5b2d  ldc.i4.1
0x7b5b2e  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPWeb::GetNewsList(bool allowCreate)
0x7b5b33  stloc.s  4
0x7b5b35  ldloc.s  4
0x7b5b37  callvirt instance class Microsoft.SharePoint.SPListItem Microsoft.SharePoint.SPList::AddItem()
0x7b5b3c  stloc.3
0x7b5b3d  br.s     loc_7B5B9E
0x7b5b3f  ldc.i4   0x13100C2
0x7b5b44  ldstr    aSpnewsutilityC_2// "SPNewsUtility.CreateOrUpdateNewsItem: U"...
0x7b5b49  ldnull
0x7b5b4a  ldloca.s 0xC
0x7b5b4c  initobj  [mscorlib]System.Guid
0x7b5b52  ldloc.s  0xC
0x7b5b54  ldnull
0x7b5b55  ldnull
0x7b5b56  call     void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::WriteUsageTag(unsigned int32 tag, string devCommentIgnored, [opt] string userLogin, [opt] valuetype [mscorlib]System.Guid siteSubscriptionId, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, [opt] string userAgent)
0x7b5b5b  ldc.i4.1
0x7b5b5c  stloc.1
0x7b5b5d  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0x7b5b62  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPContext::get_Web()
0x7b5b67  ldc.i4.1
0x7b5b68  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPWeb::GetNewsList(bool allowCreate)
0x7b5b6d  stloc.s  4
0x7b5b6f  ldloc.s  4
0x7b5b71  ldarg.0
0x7b5b72  callvirt instance int32 Microsoft.SharePoint.Utilities.SPNewsItem::get_itemId()
0x7b5b77  callvirt instance class Microsoft.SharePoint.SPListItem Microsoft.SharePoint.SPList::GetItemById(int32 id)
0x7b5b7c  stloc.3
0x7b5b7d  leave.s  loc_7B5B9E
0x7b5b7f  pop
0x7b5b80  ldloc.2
0x7b5b81  ldc.i4   0x11DE84A
0x7b5b86  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x7b5b8b  ldstr    aSpnewsutilityC_3// "SPNewsUtility.CreateOrUpdateNewsItem: a"...
0x7b5b90  ldnull
0x7b5b91  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x7b5b96  ldc.i4.1
0x7b5b97  stloc.0
0x7b5b98  newobj   instance void [mscorlib]System.IO.FileNotFoundException::.ctor()
0x7b5b9d  throw
0x7b5b9e  ldloc.3
0x7b5b9f  ldsfld   valuetype SPNewsFieldInfo SPNewsUtilityProperties::ColumnPictureUrl2
0x7b5ba4  stloc.s  0xD
0x7b5ba6  ldloca.s 0xD
0x7b5ba8  call     instance string SPNewsFieldInfo::get_Name()
0x7b5bad  ldarg.0
0x7b5bae  callvirt instance string Microsoft.SharePoint.Utilities.SPNewsItem::get_pictureUrl()
0x7b5bb3  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0x7b5bb8  ldloc.3
0x7b5bb9  ldsfld   valuetype SPNewsFieldInfo SPNewsUtilityProperties::ColumnUrl2
0x7b5bbe  stloc.s  0xE
0x7b5bc0  ldloca.s 0xE
0x7b5bc2  call     instance string SPNewsFieldInfo::get_Name()
0x7b5bc7  ldarg.0
0x7b5bc8  callvirt instance string Microsoft.SharePoint.Utilities.SPNewsItemMetadata::get_url()
0x7b5bcd  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0x7b5bd2  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Utilities.SPNewsUtility::SUPPORT_EXTRA_FIELDS_GUID
0x7b5bd7  ldstr    a1252017// "1/25/2017"
0x7b5bdc  ldstr    aSupportextrafi// "SupportExtraFields"
0x7b5be1  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x7b5be6  brtrue.s loc_7B5C36
0x7b5be8  ldloc.3
0x7b5be9  ldsfld   valuetype SPNewsFieldInfo SPNewsUtilityProperties::ColumnBackupPictureUrl
0x7b5bee  stloc.s  0xF
0x7b5bf0  ldloca.s 0xF
0x7b5bf2  call     instance string SPNewsFieldInfo::get_Name()
0x7b5bf7  ldarg.0
0x7b5bf8  callvirt instance string Microsoft.SharePoint.Utilities.SPNewsItem::get_backupPictureUrl()
0x7b5bfd  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0x7b5c02  ldloc.3
0x7b5c03  ldsfld   valuetype SPNewsFieldInfo SPNewsUtilityProperties::ColumnPictureAltText
0x7b5c08  stloc.s  0x10
0x7b5c0a  ldloca.s 0x10
0x7b5c0c  call     instance string SPNewsFieldInfo::get_Name()
0x7b5c11  ldarg.0
0x7b5c12  callvirt instance string Microsoft.SharePoint.Utilities.SPNewsItem::get_pictureAltText()
0x7b5c17  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0x7b5c1c  ldloc.3
0x7b5c1d  ldsfld   valuetype SPNewsFieldInfo SPNewsUtilityProperties::ColumnProperties
0x7b5c22  stloc.s  0x11
0x7b5c24  ldloca.s 0x11
0x7b5c26  call     instance string SPNewsFieldInfo::get_Name()
0x7b5c2b  ldarg.0
0x7b5c2c  callvirt instance string Microsoft.SharePoint.Utilities.SPNewsItem::get_properties()
0x7b5c31  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0x7b5c36  ldloc.3
0x7b5c37  ldsfld   valuetype SPNewsFieldInfo SPNewsUtilityProperties::ColumnCaption
0x7b5c3c  stloc.s  0x12
0x7b5c3e  ldloca.s 0x12
0x7b5c40  call     instance string SPNewsFieldInfo::get_Name()
0x7b5c45  ldarg.0
0x7b5c46  callvirt instance string Microsoft.SharePoint.Utilities.SPNewsItem::get_caption()
0x7b5c4b  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0x7b5c50  ldloc.3
0x7b5c51  ldstr    aTitle_0// "Title"
0x7b5c56  ldarg.0
0x7b5c57  callvirt instance string Microsoft.SharePoint.Utilities.SPNewsItemMetadata::get_title()
0x7b5c5c  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0x7b5c61  ldloc.3
0x7b5c62  ldsfld   valuetype SPNewsFieldInfo SPNewsUtilityProperties::ColumnType
0x7b5c67  stloc.s  0x13
0x7b5c69  ldloca.s 0x13
0x7b5c6b  call     instance string SPNewsFieldInfo::get_Name()
0x7b5c70  ldarg.0
0x7b5c71  callvirt instance valuetype Microsoft.SharePoint.Utilities.SPNewsItemType Microsoft.SharePoint.Utilities.SPNewsItemMetadata::get_newsType()
0x7b5c76  box      [mscorlib]System.Int32
0x7b5c7b  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0x7b5c80  ldloc.3
0x7b5c81  ldsfld   valuetype SPNewsFieldInfo SPNewsUtilityProperties::ColumnSiteId
0x7b5c86  stloc.s  0x14
0x7b5c88  ldloca.s 0x14
0x7b5c8a  call     instance string SPNewsFieldInfo::get_Name()
0x7b5c8f  ldarg.0
0x7b5c90  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Utilities.SPNewsItemMetadata::get_siteId()
0x7b5c95  box      [mscorlib]System.Guid
0x7b5c9a  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0x7b5c9f  ldloc.3
0x7b5ca0  ldsfld   valuetype SPNewsFieldInfo SPNewsUtilityProperties::ColumnWebId
0x7b5ca5  stloc.s  0x15
0x7b5ca7  ldloca.s 0x15
0x7b5ca9  call     instance string SPNewsFieldInfo::get_Name()
0x7b5cae  ldarg.0
0x7b5caf  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Utilities.SPNewsItemMetadata::get_webId()
0x7b5cb4  box      [mscorlib]System.Guid
0x7b5cb9  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0x7b5cbe  ldloc.3
0x7b5cbf  ldsfld   valuetype SPNewsFieldInfo SPNewsUtilityProperties::ColumnUniqueId
0x7b5cc4  stloc.s  0x16
0x7b5cc6  ldloca.s 0x16
0x7b5cc8  call     instance string SPNewsFieldInfo::get_Name()
0x7b5ccd  ldarg.0
0x7b5cce  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Utilities.SPNewsItemMetadata::get_uniqueId()
0x7b5cd3  box      [mscorlib]System.Guid
0x7b5cd8  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0x7b5cdd  ldloc.3
0x7b5cde  ldsfld   valuetype SPNewsFieldInfo SPNewsUtilityProperties::ColumnFileExtension
0x7b5ce3  stloc.s  0x17
0x7b5ce5  ldloca.s 0x17
0x7b5ce7  call     instance string SPNewsFieldInfo::get_Name()
0x7b5cec  ldarg.0
0x7b5ced  callvirt instance string Microsoft.SharePoint.Utilities.SPNewsItemMetadata::get_fileExtension()
0x7b5cf2  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0x7b5cf7  ldloc.3
0x7b5cf8  ldsfld   valuetype SPNewsFieldInfo SPNewsUtilityProperties::ColumnProgId
0x7b5cfd  stloc.s  0x18
0x7b5cff  ldloca.s 0x18
0x7b5d01  call     instance string SPNewsFieldInfo::get_Name()
0x7b5d06  ldarg.0
0x7b5d07  callvirt instance string Microsoft.SharePoint.Utilities.SPNewsItemMetadata::get_progId()
0x7b5d0c  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0x7b5d11  ldloc.1
0x7b5d12  brtrue.s loc_7B5D2E
0x7b5d14  ldloc.3
0x7b5d15  ldsfld   valuetype SPNewsFieldInfo SPNewsUtilityProperties::ColumnFlags
0x7b5d1a  stloc.s  0x19
0x7b5d1c  ldloca.s 0x19
0x7b5d1e  call     instance string SPNewsFieldInfo::get_Name()
0x7b5d23  ldc.i4.0
0x7b5d24  box      [mscorlib]System.Int32
0x7b5d29  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0x7b5d2e  ldloc.3
0x7b5d2f  callvirt instance void Microsoft.SharePoint.SPItem::Update()
0x7b5d34  ldloc.3
0x7b5d35  callvirt instance int32 Microsoft.SharePoint.SPItem::get_ID()
0x7b5d3a  stloc.s  5
0x7b5d3c  ldloc.1
0x7b5d3d  brfalse.s loc_7B5D52
0x7b5d3f  ldarg.1
0x7b5d40  brtrue.s loc_7B5D52
0x7b5d42  ldloc.2
0x7b5d43  ldnull
0x7b5d44  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::Success([opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x7b5d49  ldloc.s  5
0x7b5d4b  stloc.s  0xA
0x7b5d4d  leave    loc_7B5E7C
0x7b5d52  ldnull
0x7b5d53  stloc.s  6
0x7b5d55  ldloc.s  4
0x7b5d57  ldloc.s  5
0x7b5d59  ldarg.1
0x7b5d5a  call     class Microsoft.SharePoint.Utilities.SPSpotlightResult Microsoft.SharePoint.Utilities.SPNewsUtility::AddToSpotlight(class Microsoft.SharePoint.SPList newsList, int32 itemId, int32 afterItemId)
0x7b5d5f  stloc.s  7
0x7b5d61  ldloc.s  7
0x7b5d63  callvirt instance valuetype Microsoft.SharePoint.Utilities.SPSpotlightResultCode Microsoft.SharePoint.Utilities.SPSpotlightResult::get_ResultCode()
0x7b5d68  stloc.s  8
0x7b5d6a  ldloc.s  8
0x7b5d6c  brtrue.s loc_7B5D7E
0x7b5d6e  ldloc.2
0x7b5d6f  ldnull
0x7b5d70  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::Success([opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x7b5d75  ldloc.s  5
0x7b5d77  stloc.s  0xA
0x7b5d79  leave    loc_7B5E7C
0x7b5d7e  ldloc.s  8
0x7b5d80  ldc.i4.3
0x7b5d81  bne.un.s loc_7B5DA5
0x7b5d83  ldloc.2
0x7b5d84  ldc.i4   0x12593E3
0x7b5d89  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x7b5d8e  ldstr    aSpnewsutilityC_4// "SPNewsUtility.CreateOrUpdateNewsItem: S"...
0x7b5d93  ldnull
0x7b5d94  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x7b5d99  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0x7b5d9e  stloc.s  6
0x7b5da0  br       loc_7B5E34
0x7b5da5  ldloc.s  8
0x7b5da7  ldc.i4.1
0x7b5da8  bne.un.s loc_7B5DC2
0x7b5daa  ldloc.2
0x7b5dab  ldc.i4   0x1259400
0x7b5db0  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x7b5db5  ldstr    aSpnewsutilityC_5// "SPNewsUtility.CreateOrUpdateNewsItem: S"...
0x7b5dba  ldnull
0x7b5dbb  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x7b5dc0  br.s     loc_7B5E34
0x7b5dc2  ldloc.s  8
0x7b5dc4  ldc.i4.2
0x7b5dc5  bne.un.s loc_7B5DDF
0x7b5dc7  ldloc.2
0x7b5dc8  ldc.i4   0x1259401
0x7b5dcd  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x7b5dd2  ldstr    aSpnewsutilityC_6// "SPNewsUtility.CreateOrUpdateNewsItem: S"...
0x7b5dd7  ldnull
0x7b5dd8  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x7b5ddd  br.s     loc_7B5E34
0x7b5ddf  ldloc.s  8
0x7b5de1  ldc.i4.4
0x7b5de2  bne.un.s loc_7B5DFC
0x7b5de4  ldloc.2
0x7b5de5  ldc.i4   0x1259402
0x7b5dea  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x7b5def  ldstr    aSpnewsutilityC_7// "SPNewsUtility.CreateOrUpdateNewsItem: S"...
0x7b5df4  ldnull
0x7b5df5  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x7b5dfa  br.s     loc_7B5E34
0x7b5dfc  ldloc.s  8
0x7b5dfe  ldc.i4.5
0x7b5dff  bne.un.s loc_7B5E19
0x7b5e01  ldloc.2
0x7b5e02  ldc.i4   0x1259403
0x7b5e07  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
  ... truncated ...
```
