# Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::FeatureUpgrading

- ea: `0xa847f0`
- end: `0xa84dae`
- name: `Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::FeatureUpgrading`
- size: `1470`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1b7de0`
- `0x4edea0`
- `0x4f7860`
- `0x577070`
- `0x5c3ce0`
- `0xa4f220`
- `0xa847d0`
- `0xa847f0`
- `0xa84db0`
- `0xa84dc0`
- `0xa85120`
- `0xa85140`
- `0xa85310`
- `0xa85ac0`
- `0xa85ae0`
- `0xa85bf0`
- `0xa85d30`
- `0xa85ed0`
- `0xa85fe0`
- `0xa86010`
- `0xa86040`
- `0xa86080`
- `0xa860a0`
- `0xa860d0`
- `0xa860f0`
- `0xa86110`

## string_xrefs

- `0xa84871`: `UpdateContentType`
- `0xa84888`: `Begin UpdateContentType() [SPWeb Url=`
- `0xa848b5`: `End UpdateContentType()`
- `0xa8490f`: `UpdateEventReceivers`
- `0xa84926`: `Begin UpdateEventReceivers() [SPWeb Url=`
- `0xa84953`: `End UpdateEventReceivers()`
- `0xa8495e`: `UpdateMobileViews`
- `0xa84975`: `Begin UpdateMobileViews() [SPWeb Url=`
- `0xa849a2`: `End UpdateMobileViews()`
- `0xa849ad`: `UpdateOOBViews`
- `0xa849c4`: `Begin UpdateOOBViews() [SPWeb Url=`
- `0xa849f1`: `End UpdateOOBViews()`
- `0xa849fc`: `UpdateCalendarView`
- `0xa84a13`: `Begin UpdateCalendarView() [SPWeb Url=`
- `0xa84a40`: `End UpdateCalendarView()`
- `0xa84a4b`: `UpdateOOBViewsForTimeline`
- `0xa84a62`: `Begin UpdateOOBViewsForTimeline() [SPWeb Url=`
- `0xa84a8f`: `End UpdateOOBViewsForTimeline()`
- `0xa84ae9`: `UpdateDatesToBeFriendly`
- `0xa84b00`: `Begin UpdateDatesToBeFriendly() [SPWeb Url=`
- `0xa84b2d`: `End UpdateDatesToBeFriendly()`
- `0xa84b38`: `ChangeTitleDisplayNameAndUpdateNotesField`
- `0xa84b4f`: `Begin ChangeTitleDisplayNameAndUpdateNotesField() [SPWeb Url=`
- `0xa84b7c`: `End ChangeTitleDisplayNameAndUpdateNotesField()`
- `0xa84b87`: `RemoveSortOnMyTasks`
- `0xa84b9e`: `Begin RemoveSortOnMyTasks() [SPWeb Url=`
- `0xa84bcb`: `End RemoveSortOnMyTasks()`
- `0xa84bd6`: `UpdateViewsForParentIDAndCompletedStrikethrough`
- `0xa84bed`: `Begin UpdateViewsForParentIDAndCompletedStrikethrough() [SPWeb Url=`
- `0xa84c1a`: `End UpdateViewsForParentIDAndCompletedStrikethrough()`
- `0xa84c25`: `RemoveCalloutMenuAttribute`
- `0xa84c3c`: `Begin RemoveCalloutMenuAttribute() [SPWeb Url=`
- `0xa84c69`: `End RemoveCalloutMenuAttribute()`
- `0xa84c74`: `UpdateJSLinkAttributes`
- `0xa84c8b`: `Begin UpdateJSLinkAttributes() [SPWeb Url=`
- `0xa84cb8`: `End UpdateJSLinkAttributes()`
- `0xa84d10`: `RemoveDescription`
- `0xa84d27`: `Begin RemoveDescription() [SPWeb Url=`
- `0xa84d54`: `End RemoveDescription()`
- `0xa84d5f`: `UpdateAssignedToMeView`
- `0xa84d76`: `Begin UpdateAssignedToMeView() [SPWeb Url=`
- `0xa84da3`: `End UpdateAssignedToMeView()`

## pseudocode

```c

```

## disassembly

```asm
0xa847f0  ldarg.1
0xa847f1  callvirt instance class Microsoft.SharePoint.SPFeature Microsoft.SharePoint.SPFeatureReceiverProperties::get_Feature()
0xa847f6  stloc.0
0xa847f7  ldloc.0
0xa847f8  callvirt instance object Microsoft.SharePoint.SPFeature::get_Parent()
0xa847fd  isinst   Microsoft.SharePoint.SPWeb
0xa84802  stloc.1
0xa84803  ldloc.1
0xa84804  brtrue.s loc_A84821
0xa84806  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0xa8480b  ldstr    aFeatureisnotwe// "FeatureIsNotWebScope"
0xa84810  ldc.i4.0
0xa84811  newarr   [mscorlib]System.Object
0xa84816  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0xa8481b  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0xa84820  throw
0xa84821  ldarg.2
0xa84822  ldstr    aTouchcheckmark// "TouchCheckmarkField"
0xa84827  callvirt instance bool [mscorlib]System.String::Equals(string)
0xa8482c  brfalse.s loc_A84870
0xa8482e  ldarg.0
0xa8482f  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::get_Log()
0xa84834  ldc.i4   0x25871A
0xa84839  ldstr    aBeginTouchchec// "Begin TouchCheckmarkField() [SPWeb Url="
0xa8483e  ldloc.1
0xa8483f  callvirt instance string Microsoft.SharePoint.SPWeb::get_Url()
0xa84844  ldstr    asc_C681A6// "]"
0xa84849  call     string [mscorlib]System.String::Concat(string, string, string)
0xa8484e  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa84853  ldarg.0
0xa84854  ldloc.1
0xa84855  ldloc.0
0xa84856  call     instance void Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::TouchCheckmarkField(class Microsoft.SharePoint.SPWeb web, class Microsoft.SharePoint.SPFeature feature)
0xa8485b  ldarg.0
0xa8485c  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::get_Log()
0xa84861  ldc.i4   0x25871B
0xa84866  ldstr    aEndTouchcheckm// "End TouchCheckmarkField()"
0xa8486b  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa84870  ldarg.2
0xa84871  ldstr    aUpdatecontentt// "UpdateContentType"
0xa84876  callvirt instance bool [mscorlib]System.String::Equals(string)
0xa8487b  brfalse.s loc_A848BF
0xa8487d  ldarg.0
0xa8487e  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::get_Log()
0xa84883  ldc.i4   0x25871C
0xa84888  ldstr    aBeginUpdatecon_0// "Begin UpdateContentType() [SPWeb Url="
0xa8488d  ldloc.1
0xa8488e  callvirt instance string Microsoft.SharePoint.SPWeb::get_Url()
0xa84893  ldstr    asc_C681A6// "]"
0xa84898  call     string [mscorlib]System.String::Concat(string, string, string)
0xa8489d  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa848a2  ldarg.0
0xa848a3  ldloc.1
0xa848a4  ldloc.0
0xa848a5  call     instance void Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::UpdateContentType(class Microsoft.SharePoint.SPWeb web, class Microsoft.SharePoint.SPFeature feature)
0xa848aa  ldarg.0
0xa848ab  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::get_Log()
0xa848b0  ldc.i4   0x25871D
0xa848b5  ldstr    aEndUpdateconte// "End UpdateContentType()"
0xa848ba  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa848bf  ldarg.2
0xa848c0  ldstr    aPinneditemsfie// "PinnedItemsField"
0xa848c5  callvirt instance bool [mscorlib]System.String::Equals(string)
0xa848ca  brfalse.s loc_A8490E
0xa848cc  ldarg.0
0xa848cd  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::get_Log()
0xa848d2  ldc.i4   0x25871E
0xa848d7  ldstr    aBeginPinnedite// "Begin PinnedItemsField() [SPWeb Url="
0xa848dc  ldloc.1
0xa848dd  callvirt instance string Microsoft.SharePoint.SPWeb::get_Url()
0xa848e2  ldstr    asc_C681A6// "]"
0xa848e7  call     string [mscorlib]System.String::Concat(string, string, string)
0xa848ec  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa848f1  ldarg.0
0xa848f2  ldloc.1
0xa848f3  ldloc.0
0xa848f4  call     instance void Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::PinnedItemsField(class Microsoft.SharePoint.SPWeb web, class Microsoft.SharePoint.SPFeature feature)
0xa848f9  ldarg.0
0xa848fa  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::get_Log()
0xa848ff  ldc.i4   0x25871F
0xa84904  ldstr    aEndPinneditems// "End PinnedItemsField()"
0xa84909  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa8490e  ldarg.2
0xa8490f  ldstr    aUpdateeventrec// "UpdateEventReceivers"
0xa84914  callvirt instance bool [mscorlib]System.String::Equals(string)
0xa84919  brfalse.s loc_A8495D
0xa8491b  ldarg.0
0xa8491c  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::get_Log()
0xa84921  ldc.i4   0x258720
0xa84926  ldstr    aBeginUpdateeve// "Begin UpdateEventReceivers() [SPWeb Url"...
0xa8492b  ldloc.1
0xa8492c  callvirt instance string Microsoft.SharePoint.SPWeb::get_Url()
0xa84931  ldstr    asc_C681A6// "]"
0xa84936  call     string [mscorlib]System.String::Concat(string, string, string)
0xa8493b  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa84940  ldarg.0
0xa84941  ldloc.1
0xa84942  ldloc.0
0xa84943  call     instance void Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::UpdateEventReceivers(class Microsoft.SharePoint.SPWeb web, class Microsoft.SharePoint.SPFeature feature)
0xa84948  ldarg.0
0xa84949  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::get_Log()
0xa8494e  ldc.i4   0x258721
0xa84953  ldstr    aEndUpdateevent// "End UpdateEventReceivers()"
0xa84958  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa8495d  ldarg.2
0xa8495e  ldstr    aUpdatemobilevi// "UpdateMobileViews"
0xa84963  callvirt instance bool [mscorlib]System.String::Equals(string)
0xa84968  brfalse.s loc_A849AC
0xa8496a  ldarg.0
0xa8496b  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::get_Log()
0xa84970  ldc.i4   0x258722
0xa84975  ldstr    aBeginUpdatemob// "Begin UpdateMobileViews() [SPWeb Url="
0xa8497a  ldloc.1
0xa8497b  callvirt instance string Microsoft.SharePoint.SPWeb::get_Url()
0xa84980  ldstr    asc_C681A6// "]"
0xa84985  call     string [mscorlib]System.String::Concat(string, string, string)
0xa8498a  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa8498f  ldarg.0
0xa84990  ldloc.1
0xa84991  ldloc.0
0xa84992  call     instance void Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::UpdateMobileViews(class Microsoft.SharePoint.SPWeb web, class Microsoft.SharePoint.SPFeature feature)
0xa84997  ldarg.0
0xa84998  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::get_Log()
0xa8499d  ldc.i4   0x258723
0xa849a2  ldstr    aEndUpdatemobil// "End UpdateMobileViews()"
0xa849a7  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa849ac  ldarg.2
0xa849ad  ldstr    aUpdateoobviews// "UpdateOOBViews"
0xa849b2  callvirt instance bool [mscorlib]System.String::Equals(string)
0xa849b7  brfalse.s loc_A849FB
0xa849b9  ldarg.0
0xa849ba  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::get_Log()
0xa849bf  ldc.i4   0x258740
0xa849c4  ldstr    aBeginUpdateoob// "Begin UpdateOOBViews() [SPWeb Url="
0xa849c9  ldloc.1
0xa849ca  callvirt instance string Microsoft.SharePoint.SPWeb::get_Url()
0xa849cf  ldstr    asc_C681A6// "]"
0xa849d4  call     string [mscorlib]System.String::Concat(string, string, string)
0xa849d9  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa849de  ldarg.0
0xa849df  ldloc.1
0xa849e0  ldloc.0
0xa849e1  call     instance void Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::UpdateOOBViews(class Microsoft.SharePoint.SPWeb web, class Microsoft.SharePoint.SPFeature feature)
0xa849e6  ldarg.0
0xa849e7  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::get_Log()
0xa849ec  ldc.i4   0x258741
0xa849f1  ldstr    aEndUpdateoobvi// "End UpdateOOBViews()"
0xa849f6  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa849fb  ldarg.2
0xa849fc  ldstr    aUpdatecalendar// "UpdateCalendarView"
0xa84a01  callvirt instance bool [mscorlib]System.String::Equals(string)
0xa84a06  brfalse.s loc_A84A4A
0xa84a08  ldarg.0
0xa84a09  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::get_Log()
0xa84a0e  ldc.i4   0x258742
0xa84a13  ldstr    aBeginUpdatecal// "Begin UpdateCalendarView() [SPWeb Url="
0xa84a18  ldloc.1
0xa84a19  callvirt instance string Microsoft.SharePoint.SPWeb::get_Url()
0xa84a1e  ldstr    asc_C681A6// "]"
0xa84a23  call     string [mscorlib]System.String::Concat(string, string, string)
0xa84a28  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa84a2d  ldarg.0
0xa84a2e  ldloc.1
0xa84a2f  ldloc.0
0xa84a30  call     instance void Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::UpdateCalendarView(class Microsoft.SharePoint.SPWeb web, class Microsoft.SharePoint.SPFeature feature)
0xa84a35  ldarg.0
0xa84a36  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::get_Log()
0xa84a3b  ldc.i4   0x258743
0xa84a40  ldstr    aEndUpdatecalen// "End UpdateCalendarView()"
0xa84a45  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa84a4a  ldarg.2
0xa84a4b  ldstr    aUpdateoobviews_0// "UpdateOOBViewsForTimeline"
0xa84a50  callvirt instance bool [mscorlib]System.String::Equals(string)
0xa84a55  brfalse.s loc_A84A99
0xa84a57  ldarg.0
0xa84a58  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::get_Log()
0xa84a5d  ldc.i4   0x258744
0xa84a62  ldstr    aBeginUpdateoob_0// "Begin UpdateOOBViewsForTimeline() [SPWe"...
0xa84a67  ldloc.1
0xa84a68  callvirt instance string Microsoft.SharePoint.SPWeb::get_Url()
0xa84a6d  ldstr    asc_C681A6// "]"
0xa84a72  call     string [mscorlib]System.String::Concat(string, string, string)
0xa84a77  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa84a7c  ldarg.0
0xa84a7d  ldloc.1
0xa84a7e  ldloc.0
0xa84a7f  call     instance void Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::UpdateOOBViewsForTimeline(class Microsoft.SharePoint.SPWeb web, class Microsoft.SharePoint.SPFeature feature)
0xa84a84  ldarg.0
0xa84a85  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::get_Log()
0xa84a8a  ldc.i4   0x258745
0xa84a8f  ldstr    aEndUpdateoobvi_0// "End UpdateOOBViewsForTimeline()"
0xa84a94  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa84a99  ldarg.2
0xa84a9a  ldstr    aAddpreviouslya// "AddPreviouslyAssignedTo"
0xa84a9f  callvirt instance bool [mscorlib]System.String::Equals(string)
0xa84aa4  brfalse.s loc_A84AE8
0xa84aa6  ldarg.0
0xa84aa7  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::get_Log()
0xa84aac  ldc.i4   0x258746
0xa84ab1  ldstr    aBeginAddprevio// "Begin AddPreviouslyAssignedTo() [SPWeb "...
0xa84ab6  ldloc.1
0xa84ab7  callvirt instance string Microsoft.SharePoint.SPWeb::get_Url()
0xa84abc  ldstr    asc_C681A6// "]"
0xa84ac1  call     string [mscorlib]System.String::Concat(string, string, string)
0xa84ac6  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa84acb  ldarg.0
0xa84acc  ldloc.1
0xa84acd  ldloc.0
0xa84ace  call     instance void Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::AddPreviouslyAssignedTo(class Microsoft.SharePoint.SPWeb web, class Microsoft.SharePoint.SPFeature feature)
0xa84ad3  ldarg.0
0xa84ad4  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::get_Log()
0xa84ad9  ldc.i4   0x258747
0xa84ade  ldstr    aEndAddprevious// "End AddPreviouslyAssignedTo()"
0xa84ae3  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa84ae8  ldarg.2
0xa84ae9  ldstr    aUpdatedatestob// "UpdateDatesToBeFriendly"
0xa84aee  callvirt instance bool [mscorlib]System.String::Equals(string)
0xa84af3  brfalse.s loc_A84B37
0xa84af5  ldarg.0
0xa84af6  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::get_Log()
0xa84afb  ldc.i4   0x258748
0xa84b00  ldstr    aBeginUpdatedat// "Begin UpdateDatesToBeFriendly() [SPWeb "...
0xa84b05  ldloc.1
0xa84b06  callvirt instance string Microsoft.SharePoint.SPWeb::get_Url()
0xa84b0b  ldstr    asc_C681A6// "]"
0xa84b10  call     string [mscorlib]System.String::Concat(string, string, string)
0xa84b15  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa84b1a  ldarg.0
0xa84b1b  ldloc.1
0xa84b1c  ldloc.0
0xa84b1d  call     instance void Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::UpdateDatesToBeFriendly(class Microsoft.SharePoint.SPWeb web, class Microsoft.SharePoint.SPFeature feature)
0xa84b22  ldarg.0
0xa84b23  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::get_Log()
0xa84b28  ldc.i4   0x258749
0xa84b2d  ldstr    aEndUpdatedates// "End UpdateDatesToBeFriendly()"
0xa84b32  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa84b37  ldarg.2
0xa84b38  ldstr    aChangetitledis// "ChangeTitleDisplayNameAndUpdateNotesFie"...
0xa84b3d  callvirt instance bool [mscorlib]System.String::Equals(string)
0xa84b42  brfalse.s loc_A84B86
0xa84b44  ldarg.0
0xa84b45  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::get_Log()
0xa84b4a  ldc.i4   0x25874A
0xa84b4f  ldstr    aBeginChangetit// "Begin ChangeTitleDisplayNameAndUpdateNo"...
0xa84b54  ldloc.1
0xa84b55  callvirt instance string Microsoft.SharePoint.SPWeb::get_Url()
0xa84b5a  ldstr    asc_C681A6// "]"
0xa84b5f  call     string [mscorlib]System.String::Concat(string, string, string)
0xa84b64  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa84b69  ldarg.0
0xa84b6a  ldloc.1
0xa84b6b  ldloc.0
0xa84b6c  call     instance void Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::ChangeTitleDisplayNameAndUpdateNotesField(class Microsoft.SharePoint.SPWeb web, class Microsoft.SharePoint.SPFeature feature)
0xa84b71  ldarg.0
0xa84b72  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::get_Log()
0xa84b77  ldc.i4   0x25874B
0xa84b7c  ldstr    aEndChangetitle// "End ChangeTitleDisplayNameAndUpdateNote"...
0xa84b81  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa84b86  ldarg.2
0xa84b87  ldstr    aRemovesortonmy// "RemoveSortOnMyTasks"
0xa84b8c  callvirt instance bool [mscorlib]System.String::Equals(string)
0xa84b91  brfalse.s loc_A84BD5
0xa84b93  ldarg.0
0xa84b94  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::get_Log()
0xa84b99  ldc.i4   0x25874C
0xa84b9e  ldstr    aBeginRemovesor// "Begin RemoveSortOnMyTasks() [SPWeb Url="
0xa84ba3  ldloc.1
0xa84ba4  callvirt instance string Microsoft.SharePoint.SPWeb::get_Url()
0xa84ba9  ldstr    asc_C681A6// "]"
0xa84bae  call     string [mscorlib]System.String::Concat(string, string, string)
0xa84bb3  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa84bb8  ldarg.0
0xa84bb9  ldloc.1
0xa84bba  ldloc.0
0xa84bbb  call     instance void Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::RemoveSortOnMyTasks(class Microsoft.SharePoint.SPWeb web, class Microsoft.SharePoint.SPFeature feature)
0xa84bc0  ldarg.0
0xa84bc1  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::get_Log()
0xa84bc6  ldc.i4   0x25874D
0xa84bcb  ldstr    aEndRemovesorto// "End RemoveSortOnMyTasks()"
0xa84bd0  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa84bd5  ldarg.2
0xa84bd6  ldstr    aUpdateviewsfor// "UpdateViewsForParentIDAndCompletedStrik"...
0xa84bdb  callvirt instance bool [mscorlib]System.String::Equals(string)
0xa84be0  brfalse.s loc_A84C24
0xa84be2  ldarg.0
0xa84be3  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::get_Log()
0xa84be8  ldc.i4   0x25874E
0xa84bed  ldstr    aBeginUpdatevie// "Begin UpdateViewsForParentIDAndComplete"...
0xa84bf2  ldloc.1
0xa84bf3  callvirt instance string Microsoft.SharePoint.SPWeb::get_Url()
0xa84bf8  ldstr    asc_C681A6// "]"
0xa84bfd  call     string [mscorlib]System.String::Concat(string, string, string)
0xa84c02  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa84c07  ldarg.0
0xa84c08  ldloc.1
0xa84c09  ldloc.0
0xa84c0a  call     instance void Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::UpdateViewsForParentIDAndCompletedStrikethrough(class Microsoft.SharePoint.SPWeb web, class Microsoft.SharePoint.SPFeature feature)
0xa84c0f  ldarg.0
0xa84c10  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.SPHierarchyTasksListUpgradeFeatureReceiver::get_Log()
0xa84c15  ldc.i4   0x25874F
  ... truncated ...
```
