# Microsoft.SharePoint.Sharing.SPDocumentSharingManager::RemoveItemFromSharedWithMeView

- ea: `0x7240a0`
- end: `0x7245f9`
- name: `Microsoft.SharePoint.Sharing.SPDocumentSharingManager::RemoveItemFromSharedWithMeView`
- size: `1369`
- prototype: ``
- caller_count: `0`
- callee_count: `45`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1bfe50`
- `0x1c1770`
- `0x1c17c0`
- `0x1c18c0`
- `0x1c1920`
- `0x269a80`
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
- `0x577060`
- `0x594c60`
- `0x5966e0`
- `0x5c10e0`
- `0x5c3ce0`
- `0x5c3eb0`
- `0x5caf40`
- `0x720ed0`
- `0x720ef0`
- `0x7240a0`
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

- `0x7245da`: `SharedWithMeError_UnableToRemoveItem`
- `0x7240a2`: `RemoveItemFromSharedWithMeView`
- `0x7240d9`: `DocumentSharingManager.RemoveItemFromSharedWithMeView: current user will be removed from SharedWith column on item {0}.`
- `0x724169`: `DocumentSharingManager.RemoveItemFromSharedWithMeView: Target site subscription ID {0} does not match with current site subscription ID {1}`
- `0x7241b5`: `DocumentSharingManager.RemoveItemsFromSharedWithMeView: Called API with itemUrl not in same tenant at location: {0}.`
- `0x72421a`: `DocumentSharingManager.RemoveItemFromSharedWithMeView: Couldn't FlagRemovedItemFromItemReference. Unhandled exception:{0}`
- `0x72426e`: `DocumentSharingManager.RemoveItemFromSharedWithMeView: Could not find list item in web. Item: {0}.`
- `0x7242c5`: `DocumentSharingManager.RemoveItemFromSharedWithMeView: Couldn't find SharedWithField by ID. Trying to find it by internal name instead.`
- `0x724313`: `DocumentSharingManager.RemoveItemFromSharedWithMeView: Could not find SharedWith field in list. Item: {0}.`
- `0x72438e`: `DocumentSharingManager.RemoveItemFromSharedWithMeView: Item does not have a SharedWith column. Item: {0}.`
- `0x7243ea`: `DocumentSharingManager.RemoveItemFromSharedWithMeView: Item's SharedWith column is not of the right type. Item: {0}.`
- `0x72441d`: `DocumentSharingManager.RemoveItemFromSharedWithMeView: Processing SharedWith column for item containing `
- `0x7244b3`: `DocumentSharingManager.RemoveItemFromSharedWithMeView: Updating SharedWith column on item {0} to remove current user {1}.`
- `0x724576`: `DocumentSharingManager.RemoveItemFromSharedWithMeView: Could not find current user in item's SharedWith column. Item: {0}, User: {1}`
- `0x7245c9`: `DocumentSharingManager.RemoveItemFromSharedWithMeView: Unhandled exception:`

## pseudocode

```c

```

## disassembly

```asm
0x7240a0  ldc.i4.0
0x7240a1  stloc.0
0x7240a2  ldstr    aRemoveitemfrom// "RemoveItemFromSharedWithMeView"
0x7240a7  ldc.i4   0x10524D5
0x7240ac  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x7240b1  ldc.i4   0x10524D6
0x7240b6  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x7240bb  ldc.i4   0x10524D7
0x7240c0  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x7240c5  ldc.i4.0
0x7240c6  ldnull
0x7240c7  newobj   instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitor::.ctor(string scenarioName, unsigned int32 startTag, unsigned int32 successTag, unsigned int32 unexpectedFailureTag, [opt] valuetype Microsoft.SharePoint.Administration.SPLogType logType, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x7240cc  stloc.2
0x7240cd  ldc.i4   0x1141458
0x7240d2  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x7240d7  ldc.i4.s 0x32
0x7240d9  ldstr    aDocumentsharin_21// "DocumentSharingManager.RemoveItemFromSh"...
0x7240de  ldc.i4.1
0x7240df  newarr   [mscorlib]System.Object
0x7240e4  stloc.s  0x10
0x7240e6  ldloc.s  0x10
0x7240e8  ldc.i4.0
0x7240e9  ldarg.0
0x7240ea  stelem.ref
0x7240eb  ldloc.s  0x10
0x7240ed  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x7240f2  ldnull
0x7240f3  stloc.3
0x7240f4  ldarg.0
0x7240f5  newobj   instance void Microsoft.SharePoint.SPSite::.ctor(string requestUrl)
0x7240fa  stloc.s  4
0x7240fc  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0x724101  callvirt instance class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPContext::get_Site()
0x724106  callvirt instance class Microsoft.SharePoint.SPSiteSubscription Microsoft.SharePoint.SPSite::get_SiteSubscription()
0x72410b  brfalse.s loc_724128
0x72410d  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0x724112  callvirt instance class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPContext::get_Site()
0x724117  callvirt instance class Microsoft.SharePoint.SPSiteSubscription Microsoft.SharePoint.SPSite::get_SiteSubscription()
0x72411c  callvirt instance class Microsoft.SharePoint.SPSiteSubscriptionIdentifier Microsoft.SharePoint.SPSiteSubscription::get_Id()
0x724121  call     valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionIdentifier::op_Implicit(class Microsoft.SharePoint.SPSiteSubscriptionIdentifier identifier)
0x724126  br.s     loc_72412D
0x724128  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x72412d  stloc.s  5
0x72412f  ldloc.s  4
0x724131  callvirt instance class Microsoft.SharePoint.SPSiteSubscription Microsoft.SharePoint.SPSite::get_SiteSubscription()
0x724136  brfalse.s loc_72414B
0x724138  ldloc.s  4
0x72413a  callvirt instance class Microsoft.SharePoint.SPSiteSubscription Microsoft.SharePoint.SPSite::get_SiteSubscription()
0x72413f  callvirt instance class Microsoft.SharePoint.SPSiteSubscriptionIdentifier Microsoft.SharePoint.SPSiteSubscription::get_Id()
0x724144  call     valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionIdentifier::op_Implicit(class Microsoft.SharePoint.SPSiteSubscriptionIdentifier identifier)
0x724149  br.s     loc_724150
0x72414b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x724150  stloc.s  6
0x724152  ldloca.s 5
0x724154  ldloc.s  6
0x724156  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x72415b  brtrue.s loc_7241CE
0x72415d  ldc.i4   0x1141459
0x724162  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x724167  ldc.i4.s 0x32
0x724169  ldstr    aDocumentsharin_22// "DocumentSharingManager.RemoveItemFromSh"...
0x72416e  ldc.i4.2
0x72416f  newarr   [mscorlib]System.Object
0x724174  stloc.s  0x11
0x724176  ldloc.s  0x11
0x724178  ldc.i4.0
0x724179  ldloc.s  6
0x72417b  box      [mscorlib]System.Guid
0x724180  stelem.ref
0x724181  ldloc.s  0x11
0x724183  ldc.i4.1
0x724184  ldloc.s  5
0x724186  box      [mscorlib]System.Guid
0x72418b  stelem.ref
0x72418c  ldloc.s  0x11
0x72418e  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x724193  ldstr    aSharedwithmeer_0// "SharedWithMeError_InvalidListItem"
0x724198  ldc.i4.0
0x724199  newarr   [mscorlib]System.Object
0x72419e  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x7241a3  ldc.i4.m1
0x7241a4  newobj   instance void Microsoft.SharePoint.Sharing.SharedWithMeViewItemRemovalResult::.ctor(string errorMessage, valuetype Microsoft.SharePoint.Sharing.RemoveItemsFromSharedWithMeViewErrorCode errorCode)
0x7241a9  stloc.1
0x7241aa  ldloc.2
0x7241ab  ldc.i4   0x114145A
0x7241b0  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x7241b5  ldstr    aDocumentsharin_23// "DocumentSharingManager.RemoveItemsFromS"...
0x7241ba  ldarg.0
0x7241bb  call     string [mscorlib]System.String::Format(string, object)
0x7241c0  ldnull
0x7241c1  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x7241c6  ldloc.1
0x7241c7  stloc.s  0xF
0x7241c9  leave    loc_7245F6
0x7241ce  ldloc.s  4
0x7241d0  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPSite::OpenWeb()
0x7241d5  stloc.s  7
0x7241d7  ldarg.1
0x7241d8  ldind.ref
0x7241d9  ldloc.s  4
0x7241db  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSite::get_ID()
0x7241e0  callvirt instance void Microsoft.SharePoint.SharedWithMeRemovedItem::set_SiteId(valuetype [mscorlib]System.Guid value)
0x7241e5  ldarg.1
0x7241e6  ldind.ref
0x7241e7  ldloc.s  7
0x7241e9  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPWeb::get_ID()
0x7241ee  callvirt instance void Microsoft.SharePoint.SharedWithMeRemovedItem::set_WebId(valuetype [mscorlib]System.Guid value)
0x7241f3  ldloc.s  7
0x7241f5  ldarg.0
0x7241f6  callvirt instance class Microsoft.SharePoint.SPListItem Microsoft.SharePoint.SPWeb::GetListItem(string strUrl)
0x7241fb  stloc.3
0x7241fc  leave.s  loc_72420A
0x7241fe  ldloc.s  7
0x724200  brfalse.s loc_724209
0x724202  ldloc.s  7
0x724204  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x724209  endfinally
0x72420a  leave.s  loc_724236
0x72420c  stloc.s  8
0x72420e  ldc.i4   0x15D7863
0x724213  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x724218  ldc.i4.s 0x32
0x72421a  ldstr    aDocumentsharin_24// "DocumentSharingManager.RemoveItemFromSh"...
0x72421f  ldc.i4.1
0x724220  newarr   [mscorlib]System.Object
0x724225  stloc.s  0x12
0x724227  ldloc.s  0x12
0x724229  ldc.i4.0
0x72422a  ldloc.s  8
0x72422c  stelem.ref
0x72422d  ldloc.s  0x12
0x72422f  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x724234  leave.s  loc_724236
0x724236  leave.s  loc_724244
0x724238  ldloc.s  4
0x72423a  brfalse.s loc_724243
0x72423c  ldloc.s  4
0x72423e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x724243  endfinally
0x724244  ldloc.3
0x724245  brtrue.s loc_724295
0x724247  ldstr    aSharedwithmeer_0// "SharedWithMeError_InvalidListItem"
0x72424c  ldc.i4.0
0x72424d  newarr   [mscorlib]System.Object
0x724252  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x724257  ldc.i4.m1
0x724258  newobj   instance void Microsoft.SharePoint.Sharing.SharedWithMeViewItemRemovalResult::.ctor(string errorMessage, valuetype Microsoft.SharePoint.Sharing.RemoveItemsFromSharedWithMeViewErrorCode errorCode)
0x72425d  stloc.1
0x72425e  ldloc.2
0x72425f  ldc.i4   0x10524D8
0x724264  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x724269  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x72426e  ldstr    aDocumentsharin_25// "DocumentSharingManager.RemoveItemFromSh"...
0x724273  ldc.i4.1
0x724274  newarr   [mscorlib]System.Object
0x724279  stloc.s  0x13
0x72427b  ldloc.s  0x13
0x72427d  ldc.i4.0
0x72427e  ldarg.0
0x72427f  stelem.ref
0x724280  ldloc.s  0x13
0x724282  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x724287  ldnull
0x724288  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x72428d  ldloc.1
0x72428e  stloc.s  0xF
0x724290  leave    loc_7245F6
0x724295  ldloc.3
0x724296  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPListItem::get_ParentList()
0x72429b  callvirt instance class Microsoft.SharePoint.SPFieldCollection Microsoft.SharePoint.SPList::get_Fields()
0x7242a0  ldstr    aEf991a83108d44// "{EF991A83-108D-4407-8EE5-CCC0C3D836B9}"
0x7242a5  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7242aa  ldc.i4.0
0x7242ab  callvirt instance class Microsoft.SharePoint.SPField Microsoft.SharePoint.SPFieldCollection::GetFieldById(valuetype [mscorlib]System.Guid fieldId, bool bThrowException)
0x7242b0  stloc.s  9
0x7242b2  ldloc.s  9
0x7242b4  brtrue   loc_72433A
0x7242b9  ldc.i4   0x10DA014
0x7242be  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x7242c3  ldc.i4.s 0x32
0x7242c5  ldstr    aDocumentsharin_26// "DocumentSharingManager.RemoveItemFromSh"...
0x7242ca  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x7242cf  ldloc.3
0x7242d0  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPListItem::get_ParentList()
0x7242d5  callvirt instance class Microsoft.SharePoint.SPFieldCollection Microsoft.SharePoint.SPList::get_Fields()
0x7242da  ldstr    aSharedwithuser// "SharedWithUsers"
0x7242df  ldc.i4.0
0x7242e0  callvirt instance class Microsoft.SharePoint.SPField Microsoft.SharePoint.SPFieldCollection::GetFieldByInternalName(string strName, bool bThrowException)
0x7242e5  stloc.s  9
0x7242e7  ldloc.s  9
0x7242e9  brtrue.s loc_72433A
0x7242eb  ldstr    aSharedwithmeer_1// "SharedWithMeError_InvalidItemSharing"
0x7242f0  ldc.i4.0
0x7242f1  newarr   [mscorlib]System.Object
0x7242f6  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x7242fb  ldc.i4.s 0xFE
0x7242fd  newobj   instance void Microsoft.SharePoint.Sharing.SharedWithMeViewItemRemovalResult::.ctor(string errorMessage, valuetype Microsoft.SharePoint.Sharing.RemoveItemsFromSharedWithMeViewErrorCode errorCode)
0x724302  stloc.1
0x724303  ldloc.2
0x724304  ldc.i4   0x10524D9
0x724309  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x72430e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x724313  ldstr    aDocumentsharin_27// "DocumentSharingManager.RemoveItemFromSh"...
0x724318  ldc.i4.1
0x724319  newarr   [mscorlib]System.Object
0x72431e  stloc.s  0x14
0x724320  ldloc.s  0x14
0x724322  ldc.i4.0
0x724323  ldarg.0
0x724324  stelem.ref
0x724325  ldloc.s  0x14
0x724327  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x72432c  ldnull
0x72432d  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x724332  ldloc.1
0x724333  stloc.s  0xF
0x724335  leave    loc_7245F6
0x72433a  ldarg.1
0x72433b  ldind.ref
0x72433c  ldloc.3
0x72433d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPListItem::get_UniqueId()
0x724342  callvirt instance void Microsoft.SharePoint.SharedWithMeRemovedItem::set_UniqueId(valuetype [mscorlib]System.Guid value)
0x724347  ldarg.1
0x724348  ldind.ref
0x724349  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x72434e  callvirt instance void Microsoft.SharePoint.SharedWithMeRemovedItem::set_DateRemoved(valuetype [mscorlib]System.DateTime value)
0x724353  ldloc.3
0x724354  ldloc.s  9
0x724356  callvirt instance string Microsoft.SharePoint.SPField::get_InternalName()
0x72435b  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0x724360  stloc.s  0xA
0x724362  ldloc.s  0xA
0x724364  brtrue.s loc_7243B5
0x724366  ldstr    aSharedwithmeer_1// "SharedWithMeError_InvalidItemSharing"
0x72436b  ldc.i4.0
0x72436c  newarr   [mscorlib]System.Object
0x724371  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x724376  ldc.i4.s 0xFE
0x724378  newobj   instance void Microsoft.SharePoint.Sharing.SharedWithMeViewItemRemovalResult::.ctor(string errorMessage, valuetype Microsoft.SharePoint.Sharing.RemoveItemsFromSharedWithMeViewErrorCode errorCode)
0x72437d  stloc.1
0x72437e  ldloc.2
0x72437f  ldc.i4   0x10524DA
0x724384  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x724389  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x72438e  ldstr    aDocumentsharin_28// "DocumentSharingManager.RemoveItemFromSh"...
0x724393  ldc.i4.1
0x724394  newarr   [mscorlib]System.Object
0x724399  stloc.s  0x15
0x72439b  ldloc.s  0x15
0x72439d  ldc.i4.0
0x72439e  ldarg.0
0x72439f  stelem.ref
0x7243a0  ldloc.s  0x15
0x7243a2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7243a7  ldnull
0x7243a8  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x7243ad  ldloc.1
0x7243ae  stloc.s  0xF
0x7243b0  leave    loc_7245F6
0x7243b5  ldloc.s  0xA
0x7243b7  isinst   Microsoft.SharePoint.SPFieldUserValueCollection
0x7243bc  stloc.s  0xB
0x7243be  ldloc.s  0xB
0x7243c0  brtrue.s loc_724411
0x7243c2  ldstr    aSharedwithmeer_1// "SharedWithMeError_InvalidItemSharing"
0x7243c7  ldc.i4.0
0x7243c8  newarr   [mscorlib]System.Object
0x7243cd  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x7243d2  ldc.i4.s 0xFE
0x7243d4  newobj   instance void Microsoft.SharePoint.Sharing.SharedWithMeViewItemRemovalResult::.ctor(string errorMessage, valuetype Microsoft.SharePoint.Sharing.RemoveItemsFromSharedWithMeViewErrorCode errorCode)
0x7243d9  stloc.1
0x7243da  ldloc.2
0x7243db  ldc.i4   0x10524DB
0x7243e0  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x7243e5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7243ea  ldstr    aDocumentsharin_29// "DocumentSharingManager.RemoveItemFromSh"...
0x7243ef  ldc.i4.1
0x7243f0  newarr   [mscorlib]System.Object
0x7243f5  stloc.s  0x16
0x7243f7  ldloc.s  0x16
0x7243f9  ldc.i4.0
0x7243fa  ldarg.0
0x7243fb  stelem.ref
0x7243fc  ldloc.s  0x16
0x7243fe  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x724403  ldnull
0x724404  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x724409  ldloc.1
0x72440a  stloc.s  0xF
0x72440c  leave    loc_7245F6
0x724411  ldc.i4   0x10524DC
0x724416  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x72441b  ldc.i4.s 0x32
0x72441d  ldstr    aDocumentsharin_30// "DocumentSharingManager.RemoveItemFromSh"...
0x724422  ldloc.s  0xB
0x724424  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.SPFieldUserValue>::get_Count()
0x724429  box      [mscorlib]System.Int32
0x72442e  ldstr    aUsers_2// " users."
0x724433  call     string [mscorlib]System.String::Concat(object, object, object)
0x724438  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
  ... truncated ...
```
