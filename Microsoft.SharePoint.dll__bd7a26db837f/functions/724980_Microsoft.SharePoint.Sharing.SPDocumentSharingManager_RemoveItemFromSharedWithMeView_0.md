# Microsoft.SharePoint.Sharing.SPDocumentSharingManager::RemoveItemFromSharedWithMeView_0

- ea: `0x724980`
- end: `0x724f01`
- name: `Microsoft.SharePoint.Sharing.SPDocumentSharingManager::RemoveItemFromSharedWithMeView_0`
- size: `1409`
- prototype: ``
- caller_count: `1`
- callee_count: `46`
- tags: `file_ops, broker_com_uri`

## callers

- `0x724600`

## callees

- `0x1bfe50`
- `0x1c1770`
- `0x1c17c0`
- `0x1c18c0`
- `0x1c1920`
- `0x269ac0`
- `0x26b840`
- `0x26e660`
- `0x26f690`
- `0x342f00`
- `0x3e99e0`
- `0x3e99f0`
- `0x46a260`
- `0x4cd8e0`
- `0x4cddc0`
- `0x4cde40`
- `0x507700`
- `0x5078b0`
- `0x509440`
- `0x52a140`
- `0x53be00`
- `0x53bf80`
- `0x540cf0`
- `0x572820`
- `0x577060`
- `0x594c60`
- `0x5966e0`
- `0x5c10e0`
- `0x5c3ce0`
- `0x5c3eb0`
- `0x5caf50`
- `0x720ed0`
- `0x720ef0`
- `0x724980`
- `0x7254d0`
- `0x7254f0`
- `0x725510`
- `0x725530`
- `0x7be4d0`
- `0x7be510`
- `0x7be580`
- `0x7beb40`
- `0x8ecdb0`
- `0x93dab0`
- `0x93dae0`
- `0x957b70`

## string_xrefs

- `0x724ee2`: `SharedWithMeError_UnableToRemoveItem`
- `0x724982`: `RemoveItemFromSharedWithMeView`
- `0x7249b9`: `DocumentSharingManager.RemoveItemFromSharedWithMeView: current user will be removed from SharedWith column on item {0}.`
- `0x724a4e`: `DocumentSharingManager.RemoveItemFromSharedWithMeView: Target site subscription ID {0} does not match with current site subscription ID {1}`
- `0x724b04`: `DocumentSharingManager.RemoveItemFromSharedWithMeView: Couldn't FlagRemovedItemFromItemReference. Unhandled exception:{0}`
- `0x724b58`: `DocumentSharingManager.RemoveItemFromSharedWithMeView: Could not find list item in web. Item: {0}.`
- `0x724bb4`: `DocumentSharingManager.RemoveItemFromSharedWithMeView: Couldn't find SharedWithField by ID. Trying to find it by internal name instead.`
- `0x724c02`: `DocumentSharingManager.RemoveItemFromSharedWithMeView: Could not find SharedWith field in list. Item: {0}.`
- `0x724c82`: `DocumentSharingManager.RemoveItemFromSharedWithMeView: Item does not have a SharedWith column. Item: {0}.`
- `0x724ce3`: `DocumentSharingManager.RemoveItemFromSharedWithMeView: Item's SharedWith column is not of the right type. Item: {0}.`
- `0x724d1b`: `DocumentSharingManager.RemoveItemFromSharedWithMeView: Processing SharedWith column for item containing `
- `0x724db1`: `DocumentSharingManager.RemoveItemFromSharedWithMeView: Updating SharedWith column on item {0} to remove current user {1}.`
- `0x724e79`: `DocumentSharingManager.RemoveItemFromSharedWithMeView: Could not find current user in item's SharedWith column. Item: {0}, User: {1}`
- `0x724ed1`: `DocumentSharingManager.RemoveItemFromSharedWithMeView: Unhandled exception:`
- `0x724a9a`: `DocumentSharingManager.RemoveItemsFromSharedWithMeView: Called API with itemPath not in same tenant at location: {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x724980  ldc.i4.0
0x724981  stloc.0
0x724982  ldstr    aRemoveitemfrom// "RemoveItemFromSharedWithMeView"
0x724987  ldc.i4   0x14D55D7
0x72498c  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x724991  ldc.i4   0x14D55D8
0x724996  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x72499b  ldc.i4   0x14D55D9
0x7249a0  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x7249a5  ldc.i4.0
0x7249a6  ldnull
0x7249a7  newobj   instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitor::.ctor(string scenarioName, unsigned int32 startTag, unsigned int32 successTag, unsigned int32 unexpectedFailureTag, [opt] valuetype Microsoft.SharePoint.Administration.SPLogType logType, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x7249ac  stloc.2
0x7249ad  ldc.i4   0x14D55DA
0x7249b2  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x7249b7  ldc.i4.s 0x32
0x7249b9  ldstr    aDocumentsharin_21// "DocumentSharingManager.RemoveItemFromSh"...
0x7249be  ldc.i4.1
0x7249bf  newarr   [mscorlib]System.Object
0x7249c4  stloc.s  0x10
0x7249c6  ldloc.s  0x10
0x7249c8  ldc.i4.0
0x7249c9  ldarg.0
0x7249ca  callvirt instance string Microsoft.SharePoint.SPResourcePath::get_DecodedUrl()
0x7249cf  stelem.ref
0x7249d0  ldloc.s  0x10
0x7249d2  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x7249d7  ldnull
0x7249d8  stloc.3
0x7249d9  ldarg.0
0x7249da  newobj   instance void Microsoft.SharePoint.SPSite::.ctor(class Microsoft.SharePoint.SPResourcePath requestUrl)
0x7249df  stloc.s  4
0x7249e1  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0x7249e6  callvirt instance class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPContext::get_Site()
0x7249eb  callvirt instance class Microsoft.SharePoint.SPSiteSubscription Microsoft.SharePoint.SPSite::get_SiteSubscription()
0x7249f0  brfalse.s loc_724A0D
0x7249f2  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0x7249f7  callvirt instance class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPContext::get_Site()
0x7249fc  callvirt instance class Microsoft.SharePoint.SPSiteSubscription Microsoft.SharePoint.SPSite::get_SiteSubscription()
0x724a01  callvirt instance class Microsoft.SharePoint.SPSiteSubscriptionIdentifier Microsoft.SharePoint.SPSiteSubscription::get_Id()
0x724a06  call     valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionIdentifier::op_Implicit(class Microsoft.SharePoint.SPSiteSubscriptionIdentifier identifier)
0x724a0b  br.s     loc_724A12
0x724a0d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x724a12  stloc.s  5
0x724a14  ldloc.s  4
0x724a16  callvirt instance class Microsoft.SharePoint.SPSiteSubscription Microsoft.SharePoint.SPSite::get_SiteSubscription()
0x724a1b  brfalse.s loc_724A30
0x724a1d  ldloc.s  4
0x724a1f  callvirt instance class Microsoft.SharePoint.SPSiteSubscription Microsoft.SharePoint.SPSite::get_SiteSubscription()
0x724a24  callvirt instance class Microsoft.SharePoint.SPSiteSubscriptionIdentifier Microsoft.SharePoint.SPSiteSubscription::get_Id()
0x724a29  call     valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionIdentifier::op_Implicit(class Microsoft.SharePoint.SPSiteSubscriptionIdentifier identifier)
0x724a2e  br.s     loc_724A35
0x724a30  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x724a35  stloc.s  6
0x724a37  ldloca.s 5
0x724a39  ldloc.s  6
0x724a3b  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x724a40  brtrue.s loc_724AB8
0x724a42  ldc.i4   0x14D55DB
0x724a47  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x724a4c  ldc.i4.s 0x32
0x724a4e  ldstr    aDocumentsharin_22// "DocumentSharingManager.RemoveItemFromSh"...
0x724a53  ldc.i4.2
0x724a54  newarr   [mscorlib]System.Object
0x724a59  stloc.s  0x11
0x724a5b  ldloc.s  0x11
0x724a5d  ldc.i4.0
0x724a5e  ldloc.s  6
0x724a60  box      [mscorlib]System.Guid
0x724a65  stelem.ref
0x724a66  ldloc.s  0x11
0x724a68  ldc.i4.1
0x724a69  ldloc.s  5
0x724a6b  box      [mscorlib]System.Guid
0x724a70  stelem.ref
0x724a71  ldloc.s  0x11
0x724a73  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x724a78  ldstr    aSharedwithmeer_0// "SharedWithMeError_InvalidListItem"
0x724a7d  ldc.i4.0
0x724a7e  newarr   [mscorlib]System.Object
0x724a83  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x724a88  ldc.i4.m1
0x724a89  newobj   instance void Microsoft.SharePoint.Sharing.SharedWithMeViewItemRemovalResult::.ctor(string errorMessage, valuetype Microsoft.SharePoint.Sharing.RemoveItemsFromSharedWithMeViewErrorCode errorCode)
0x724a8e  stloc.1
0x724a8f  ldloc.2
0x724a90  ldc.i4   0x14D55DC
0x724a95  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x724a9a  ldstr    aDocumentsharin_42// "DocumentSharingManager.RemoveItemsFromS"...
0x724a9f  ldarg.0
0x724aa0  callvirt instance string Microsoft.SharePoint.SPResourcePath::get_DecodedUrl()
0x724aa5  call     string [mscorlib]System.String::Format(string, object)
0x724aaa  ldnull
0x724aab  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x724ab0  ldloc.1
0x724ab1  stloc.s  0xF
0x724ab3  leave    loc_724EFE
0x724ab8  ldloc.s  4
0x724aba  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPSite::OpenWeb()
0x724abf  stloc.s  7
0x724ac1  ldarg.1
0x724ac2  ldind.ref
0x724ac3  ldloc.s  4
0x724ac5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSite::get_ID()
0x724aca  callvirt instance void Microsoft.SharePoint.SharedWithMeRemovedItem::set_SiteId(valuetype [mscorlib]System.Guid value)
0x724acf  ldarg.1
0x724ad0  ldind.ref
0x724ad1  ldloc.s  7
0x724ad3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPWeb::get_ID()
0x724ad8  callvirt instance void Microsoft.SharePoint.SharedWithMeRemovedItem::set_WebId(valuetype [mscorlib]System.Guid value)
0x724add  ldloc.s  7
0x724adf  ldarg.0
0x724ae0  callvirt instance class Microsoft.SharePoint.SPListItem Microsoft.SharePoint.SPWeb::GetListItem(class Microsoft.SharePoint.SPResourcePath path)
0x724ae5  stloc.3
0x724ae6  leave.s  loc_724AF4
0x724ae8  ldloc.s  7
0x724aea  brfalse.s loc_724AF3
0x724aec  ldloc.s  7
0x724aee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x724af3  endfinally
0x724af4  leave.s  loc_724B20
0x724af6  stloc.s  8
0x724af8  ldc.i4   0x15D7880
0x724afd  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x724b02  ldc.i4.s 0x32
0x724b04  ldstr    aDocumentsharin_24// "DocumentSharingManager.RemoveItemFromSh"...
0x724b09  ldc.i4.1
0x724b0a  newarr   [mscorlib]System.Object
0x724b0f  stloc.s  0x12
0x724b11  ldloc.s  0x12
0x724b13  ldc.i4.0
0x724b14  ldloc.s  8
0x724b16  stelem.ref
0x724b17  ldloc.s  0x12
0x724b19  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x724b1e  leave.s  loc_724B20
0x724b20  leave.s  loc_724B2E
0x724b22  ldloc.s  4
0x724b24  brfalse.s loc_724B2D
0x724b26  ldloc.s  4
0x724b28  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x724b2d  endfinally
0x724b2e  ldloc.3
0x724b2f  brtrue.s loc_724B84
0x724b31  ldstr    aSharedwithmeer_0// "SharedWithMeError_InvalidListItem"
0x724b36  ldc.i4.0
0x724b37  newarr   [mscorlib]System.Object
0x724b3c  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x724b41  ldc.i4.m1
0x724b42  newobj   instance void Microsoft.SharePoint.Sharing.SharedWithMeViewItemRemovalResult::.ctor(string errorMessage, valuetype Microsoft.SharePoint.Sharing.RemoveItemsFromSharedWithMeViewErrorCode errorCode)
0x724b47  stloc.1
0x724b48  ldloc.2
0x724b49  ldc.i4   0x14D55DD
0x724b4e  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x724b53  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x724b58  ldstr    aDocumentsharin_25// "DocumentSharingManager.RemoveItemFromSh"...
0x724b5d  ldc.i4.1
0x724b5e  newarr   [mscorlib]System.Object
0x724b63  stloc.s  0x13
0x724b65  ldloc.s  0x13
0x724b67  ldc.i4.0
0x724b68  ldarg.0
0x724b69  callvirt instance string Microsoft.SharePoint.SPResourcePath::get_DecodedUrl()
0x724b6e  stelem.ref
0x724b6f  ldloc.s  0x13
0x724b71  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x724b76  ldnull
0x724b77  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x724b7c  ldloc.1
0x724b7d  stloc.s  0xF
0x724b7f  leave    loc_724EFE
0x724b84  ldloc.3
0x724b85  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPListItem::get_ParentList()
0x724b8a  callvirt instance class Microsoft.SharePoint.SPFieldCollection Microsoft.SharePoint.SPList::get_Fields()
0x724b8f  ldstr    aEf991a83108d44// "{EF991A83-108D-4407-8EE5-CCC0C3D836B9}"
0x724b94  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x724b99  ldc.i4.0
0x724b9a  callvirt instance class Microsoft.SharePoint.SPField Microsoft.SharePoint.SPFieldCollection::GetFieldById(valuetype [mscorlib]System.Guid fieldId, bool bThrowException)
0x724b9f  stloc.s  9
0x724ba1  ldloc.s  9
0x724ba3  brtrue   loc_724C2E
0x724ba8  ldc.i4   0x14D55DE
0x724bad  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x724bb2  ldc.i4.s 0x32
0x724bb4  ldstr    aDocumentsharin_26// "DocumentSharingManager.RemoveItemFromSh"...
0x724bb9  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x724bbe  ldloc.3
0x724bbf  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPListItem::get_ParentList()
0x724bc4  callvirt instance class Microsoft.SharePoint.SPFieldCollection Microsoft.SharePoint.SPList::get_Fields()
0x724bc9  ldstr    aSharedwithuser// "SharedWithUsers"
0x724bce  ldc.i4.0
0x724bcf  callvirt instance class Microsoft.SharePoint.SPField Microsoft.SharePoint.SPFieldCollection::GetFieldByInternalName(string strName, bool bThrowException)
0x724bd4  stloc.s  9
0x724bd6  ldloc.s  9
0x724bd8  brtrue.s loc_724C2E
0x724bda  ldstr    aSharedwithmeer_1// "SharedWithMeError_InvalidItemSharing"
0x724bdf  ldc.i4.0
0x724be0  newarr   [mscorlib]System.Object
0x724be5  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x724bea  ldc.i4.s 0xFE
0x724bec  newobj   instance void Microsoft.SharePoint.Sharing.SharedWithMeViewItemRemovalResult::.ctor(string errorMessage, valuetype Microsoft.SharePoint.Sharing.RemoveItemsFromSharedWithMeViewErrorCode errorCode)
0x724bf1  stloc.1
0x724bf2  ldloc.2
0x724bf3  ldc.i4   0x14D55DF
0x724bf8  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x724bfd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x724c02  ldstr    aDocumentsharin_27// "DocumentSharingManager.RemoveItemFromSh"...
0x724c07  ldc.i4.1
0x724c08  newarr   [mscorlib]System.Object
0x724c0d  stloc.s  0x14
0x724c0f  ldloc.s  0x14
0x724c11  ldc.i4.0
0x724c12  ldarg.0
0x724c13  callvirt instance string Microsoft.SharePoint.SPResourcePath::get_DecodedUrl()
0x724c18  stelem.ref
0x724c19  ldloc.s  0x14
0x724c1b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x724c20  ldnull
0x724c21  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x724c26  ldloc.1
0x724c27  stloc.s  0xF
0x724c29  leave    loc_724EFE
0x724c2e  ldarg.1
0x724c2f  ldind.ref
0x724c30  ldloc.3
0x724c31  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPListItem::get_UniqueId()
0x724c36  callvirt instance void Microsoft.SharePoint.SharedWithMeRemovedItem::set_UniqueId(valuetype [mscorlib]System.Guid value)
0x724c3b  ldarg.1
0x724c3c  ldind.ref
0x724c3d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x724c42  callvirt instance void Microsoft.SharePoint.SharedWithMeRemovedItem::set_DateRemoved(valuetype [mscorlib]System.DateTime value)
0x724c47  ldloc.3
0x724c48  ldloc.s  9
0x724c4a  callvirt instance string Microsoft.SharePoint.SPField::get_InternalName()
0x724c4f  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0x724c54  stloc.s  0xA
0x724c56  ldloc.s  0xA
0x724c58  brtrue.s loc_724CAE
0x724c5a  ldstr    aSharedwithmeer_1// "SharedWithMeError_InvalidItemSharing"
0x724c5f  ldc.i4.0
0x724c60  newarr   [mscorlib]System.Object
0x724c65  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x724c6a  ldc.i4.s 0xFE
0x724c6c  newobj   instance void Microsoft.SharePoint.Sharing.SharedWithMeViewItemRemovalResult::.ctor(string errorMessage, valuetype Microsoft.SharePoint.Sharing.RemoveItemsFromSharedWithMeViewErrorCode errorCode)
0x724c71  stloc.1
0x724c72  ldloc.2
0x724c73  ldc.i4   0x14D55E0
0x724c78  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x724c7d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x724c82  ldstr    aDocumentsharin_28// "DocumentSharingManager.RemoveItemFromSh"...
0x724c87  ldc.i4.1
0x724c88  newarr   [mscorlib]System.Object
0x724c8d  stloc.s  0x15
0x724c8f  ldloc.s  0x15
0x724c91  ldc.i4.0
0x724c92  ldarg.0
0x724c93  callvirt instance string Microsoft.SharePoint.SPResourcePath::get_DecodedUrl()
0x724c98  stelem.ref
0x724c99  ldloc.s  0x15
0x724c9b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x724ca0  ldnull
0x724ca1  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x724ca6  ldloc.1
0x724ca7  stloc.s  0xF
0x724ca9  leave    loc_724EFE
0x724cae  ldloc.s  0xA
0x724cb0  isinst   Microsoft.SharePoint.SPFieldUserValueCollection
0x724cb5  stloc.s  0xB
0x724cb7  ldloc.s  0xB
0x724cb9  brtrue.s loc_724D0F
0x724cbb  ldstr    aSharedwithmeer_1// "SharedWithMeError_InvalidItemSharing"
0x724cc0  ldc.i4.0
0x724cc1  newarr   [mscorlib]System.Object
0x724cc6  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x724ccb  ldc.i4.s 0xFE
0x724ccd  newobj   instance void Microsoft.SharePoint.Sharing.SharedWithMeViewItemRemovalResult::.ctor(string errorMessage, valuetype Microsoft.SharePoint.Sharing.RemoveItemsFromSharedWithMeViewErrorCode errorCode)
0x724cd2  stloc.1
0x724cd3  ldloc.2
0x724cd4  ldc.i4   0x14D55E1
0x724cd9  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x724cde  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x724ce3  ldstr    aDocumentsharin_29// "DocumentSharingManager.RemoveItemFromSh"...
0x724ce8  ldc.i4.1
0x724ce9  newarr   [mscorlib]System.Object
0x724cee  stloc.s  0x16
0x724cf0  ldloc.s  0x16
0x724cf2  ldc.i4.0
0x724cf3  ldarg.0
0x724cf4  callvirt instance string Microsoft.SharePoint.SPResourcePath::get_DecodedUrl()
0x724cf9  stelem.ref
0x724cfa  ldloc.s  0x16
0x724cfc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x724d01  ldnull
0x724d02  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x724d07  ldloc.1
0x724d08  stloc.s  0xF
0x724d0a  leave    loc_724EFE
0x724d0f  ldc.i4   0x14D55E2
0x724d14  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x724d19  ldc.i4.s 0x32
0x724d1b  ldstr    aDocumentsharin_30// "DocumentSharingManager.RemoveItemFromSh"...
  ... truncated ...
```
