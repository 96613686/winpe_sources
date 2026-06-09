# Microsoft.SharePoint.ObjectSharingContext::ShareLink

- ea: `0x72bb10`
- end: `0x72c7e3`
- name: `Microsoft.SharePoint.ObjectSharingContext::ShareLink`
- size: `3283`
- prototype: ``
- caller_count: `1`
- callee_count: `77`
- tags: `file_ops, broker_com_uri`

## callers

- `0x73d130`

## callees

- `0x1a16c0`
- `0x1b57a0`
- `0x1b6af0`
- `0x1b8600`
- `0x3192a0`
- `0x400250`
- `0x4002b0`
- `0x472c20`
- `0x4cd8e0`
- `0x4cd940`
- `0x50ba60`
- `0x52a050`
- `0x577070`
- `0x583fa0`
- `0x5b36f0`
- `0x5b37e0`
- `0x5c10e0`
- `0x678580`
- `0x6c9890`
- `0x71ad90`
- `0x725030`
- `0x725090`
- `0x7253d0`
- `0x725750`
- `0x7258c0`
- `0x7266d0`
- `0x727730`
- `0x728770`
- `0x7287b0`
- `0x7292e0`
- `0x729320`
- `0x7294f0`
- `0x729580`
- `0x72bb10`
- `0x72c7f0`
- `0x7331f0`
- `0x7332e0`
- `0x733d40`
- `0x733f40`
- `0x734020`
- `0x7384f0`
- `0x738c00`
- `0x738c20`
- `0x738cb0`
- `0x738d50`
- `0x738d60`
- `0x738d70`
- `0x738e30`
- `0x740ef0`
- `0x740f10`

## string_xrefs

- `0x72be97`: `AccessDenied`
- `0x72bb5b`: `ShareByLinkFailureReason`
- `0x72bb9e`: `ShareByLinkFailureReason`
- `0x72bccb`: `ShareByLinkFailureReason`
- `0x72bd85`: `ShareByLinkFailureReason`
- `0x72be24`: `ShareByLinkFailureReason`
- `0x72beb9`: `ShareByLinkFailureReason`
- `0x72bb45`: `ShareLink was called with a securable object that is not an SPListItem`
- `0x72bb88`: `ShareLink was called with an SPListItem that is not an ISPShareableByLinkObject.`
- `0x72bc57`: `ShareLinkExternalEmailCount`
- `0x72bc9a`: `ShareLink: Called method with unvalidated email addresses and link type is set to Organization.`
- `0x72bd6d`: `ShareLink: Called method on object that is not shareable by link.`
- `0x72bdf3`: `ShareLink: Called method with external users that already exist in the site collection and link type set to Organization.`
- `0x72be88`: `ObjectSharingContext::ShareLink(): External Users with no Manage Permissions are not allowed to reshare.`
- `0x72bee5`: `ObjectSharingContext::ShareLink(): Resolved users have existing guest users is {0}.`
- `0x72bf83`: `ObjectSharingContext.ShareLink: validating external sharing throttle limit`
- `0x72c1ac`: `Sharing_PreventInviteesToRemoveFromBeingPreRedeemed`
- `0x72c1ef`: `ObjectSharingContext.ShareLink: cannot both add and remove the same invitee in a single ShareLink event`
- `0x72c225`: `Sharing_MoveGettingExistingShareIntoImplementationWhenCreatingLink`
- `0x72c3dc`: `Checkpoint-OSCShareLink-BeginResolveEntities2`
- `0x72c3fb`: `ShareLink: The specified sharing link kind doesn't exist or couldn't be created. SharingLinkKind = [{0}]. createLinkIfMissing = [{1}].`
- `0x72c547`: `Checkpoint-OSCShareLink-AfterResolveEntities2`
- `0x72c5bd`: `Checkpoint-OSCShareLink-AfterPreRedeemUsers`
- `0x72c5e1`: `Checkpoint-OSCShareLink-AfterSWD2`
- `0x72c66a`: `Checkpoint-OSCShareLink-AfterSendEmail2`
- `0x72c6d6`: `ObjectSharingContext.ShareLink: {0} new external users counted for anonymous link.`
- `0x72c77b`: `ObjectSharingContext.ShareLink: Logging ShareLink to Activities Table. InternalUsersCount: {0}; ExternalUsersCount: {1}`
- `0x72c7d6`: `Checkpoint-OSCShareLink-AfterRecordSharingActivity2`

## pseudocode

```c

```

## disassembly

```asm
0x72bb10  ldnull
0x72bb11  stloc.s  0x28
0x72bb13  newobj   instance void <>c__DisplayClass54::.ctor()
0x72bb18  stloc.s  0x29
0x72bb1a  ldloc.s  0x29
0x72bb1c  ldarg.1
0x72bb1d  stfld    class Microsoft.SharePoint.Sharing.SPShareSettings <>c__DisplayClass54::settings
0x72bb22  ldloc.s  0x29
0x72bb24  ldarg.0
0x72bb25  stfld    class Microsoft.SharePoint.ObjectSharingContext <>c__DisplayClass54::<>4__this
0x72bb2a  ldarg.0
0x72bb2b  callvirt instance class Microsoft.SharePoint.SPSecurableObject Microsoft.SharePoint.SharingBase::get_Securable()
0x72bb30  isinst   Microsoft.SharePoint.SPListItem
0x72bb35  stloc.0
0x72bb36  ldloc.0
0x72bb37  brtrue.s loc_72BB72
0x72bb39  ldc.i4   0x141E881
0x72bb3e  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x72bb43  ldc.i4.s 0x32
0x72bb45  ldstr    aSharelinkWasCa// "ShareLink was called with a securable o"...
0x72bb4a  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x72bb4f  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0x72bb54  stloc.1
0x72bb55  ldloc.1
0x72bb56  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x72bb5b  ldstr    aSharebylinkfai// "ShareByLinkFailureReason"
0x72bb60  ldc.i4.4
0x72bb61  box      Microsoft.SharePoint.Sharing.ShareByLinkFailureReason
0x72bb66  callvirt instance string [mscorlib]System.Object::ToString()
0x72bb6b  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x72bb70  ldloc.1
0x72bb71  throw
0x72bb72  ldloc.0
0x72bb73  call     class Microsoft.SharePoint.Sharing.ISPShareableByLinkObject Microsoft.SharePoint.Sharing.SPShareByLinkHelper::GetISPShareableByLinkObject(class Microsoft.SharePoint.SPListItem item)
0x72bb78  stloc.2
0x72bb79  ldloc.2
0x72bb7a  brtrue.s loc_72BBB6
0x72bb7c  ldc.i4   0x141E882
0x72bb81  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x72bb86  ldc.i4.s 0x32
0x72bb88  ldstr    aSharelinkWasCa_0// "ShareLink was called with an SPListItem"...
0x72bb8d  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x72bb92  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0x72bb97  stloc.3
0x72bb98  ldloc.3
0x72bb99  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x72bb9e  ldstr    aSharebylinkfai// "ShareByLinkFailureReason"
0x72bba3  ldc.i4.s 0xB
0x72bba5  box      Microsoft.SharePoint.Sharing.ShareByLinkFailureReason
0x72bbaa  callvirt instance string [mscorlib]System.Object::ToString()
0x72bbaf  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x72bbb4  ldloc.3
0x72bbb5  throw
0x72bbb6  ldloc.s  0x29
0x72bbb8  ldnull
0x72bbb9  stfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass54::userLoginsList
0x72bbbe  ldnull
0x72bbbf  stloc.s  4
0x72bbc1  ldnull
0x72bbc2  stloc.s  5
0x72bbc4  ldloc.s  0x29
0x72bbc6  ldnull
0x72bbc7  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.SPUserInfo> <>c__DisplayClass54::userInfoList
0x72bbcc  ldloc.s  0x29
0x72bbce  ldnull
0x72bbcf  stfld    class Microsoft.SharePoint.SPUserCollection <>c__DisplayClass54::resolvedUsers
0x72bbd4  ldloc.s  0x29
0x72bbd6  ldfld    class Microsoft.SharePoint.Sharing.SPShareSettings <>c__DisplayClass54::settings
0x72bbdb  callvirt instance bool Microsoft.SharePoint.Sharing.SPShareSettings::get_AllowAnonymousAccess()
0x72bbe0  brtrue.s loc_72BBF0
0x72bbe2  ldloc.s  0x29
0x72bbe4  ldfld    class Microsoft.SharePoint.Sharing.SPShareSettings <>c__DisplayClass54::settings
0x72bbe9  callvirt instance bool Microsoft.SharePoint.Sharing.SPShareSettings::get_AllowExternalUserAccess()
0x72bbee  br.s     loc_72BBF1
0x72bbf0  ldc.i4.1
0x72bbf1  stloc.s  6
0x72bbf3  ldarg.0
0x72bbf4  call     instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SharingBase::get_Web()
0x72bbf9  callvirt instance class Microsoft.SharePoint.SPUser Microsoft.SharePoint.SPWeb::get_CurrentUser()
0x72bbfe  call     bool Microsoft.SharePoint.SPPreventExternalUsersFromResharingUtility::IsUserExternalUser(class Microsoft.SharePoint.SPUser user)
0x72bc03  ldc.i4.0
0x72bc04  ceq
0x72bc06  stloc.s  7
0x72bc08  ldarg.2
0x72bc09  brfalse  loc_72C14B
0x72bc0e  ldarg.2
0x72bc0f  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x72bc14  ldc.i4.0
0x72bc15  ble      loc_72C14B
0x72bc1a  ldarg.2
0x72bc1b  ldloc.s  0x29
0x72bc1d  ldflda   class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass54::userLoginsList
0x72bc22  ldloca.s 4
0x72bc24  ldloca.s 5
0x72bc26  ldloc.s  0x29
0x72bc28  ldflda   class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.SPUserInfo> <>c__DisplayClass54::userInfoList
0x72bc2d  call     void Microsoft.SharePoint.SPSharingPermissionsHelper::GetUserAndGroupInfoFromResolvedEntities(class [mscorlib]System.Collections.ArrayList resolvedEntities, [out] class [mscorlib]System.Collections.Generic.List`1<string>& userLoginsList, [out] class [mscorlib]System.Collections.Generic.List`1<string>& groupList, [out] class [mscorlib]System.Collections.Generic.List`1<string>& externalUsersList, [out] class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.SPUserInfo>& userInfoList)
0x72bc32  ldloc.s  0x29
0x72bc34  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.SPUserInfo> <>c__DisplayClass54::userInfoList
0x72bc39  call     bool Microsoft.SharePoint.SPSharingUtility::HasExistingGuestUsers(class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.SPUserInfo> userInfos)
0x72bc3e  stloc.s  8
0x72bc40  ldloc.s  5
0x72bc42  brfalse.s loc_72BC50
0x72bc44  ldloc.s  5
0x72bc46  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x72bc4b  ldc.i4.0
0x72bc4c  cgt
0x72bc4e  br.s     loc_72BC51
0x72bc50  ldc.i4.0
0x72bc51  stloc.s  9
0x72bc53  ldloc.s  9
0x72bc55  brfalse.s loc_72BC82
0x72bc57  ldstr    aSharelinkexter// "ShareLinkExternalEmailCount"
0x72bc5c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x72bc61  stloc.s  0xA
0x72bc63  ldloc.s  0xA
0x72bc65  ldstr    aExternalemailc// "ExternalEmailCount"
0x72bc6a  ldloc.s  5
0x72bc6c  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x72bc71  box      [mscorlib]System.Int32
0x72bc76  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x72bc7b  ldloc.s  0xA
0x72bc7d  call     void Microsoft.SharePoint.Administration.SPUserEngagement::WriteLog(string engagementName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x72bc82  ldloc.s  8
0x72bc84  brtrue.s loc_72BC8A
0x72bc86  ldloc.s  9
0x72bc88  brfalse.s loc_72BCE4
0x72bc8a  ldloc.s  6
0x72bc8c  brtrue.s loc_72BCE4
0x72bc8e  ldc.i4   0x168A163
0x72bc93  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x72bc98  ldc.i4.s 0x32
0x72bc9a  ldstr    aSharelinkCalle// "ShareLink: Called method with unvalidat"...
0x72bc9f  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x72bca4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x72bca9  ldstr    aEmailrecipient// "EmailRecipientExternalUser"
0x72bcae  ldc.i4.0
0x72bcaf  newarr   [mscorlib]System.Object
0x72bcb4  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x72bcb9  stloc.s  0xB
0x72bcbb  ldloc.s  0xB
0x72bcbd  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x72bcc2  stloc.s  0xC
0x72bcc4  ldloc.s  0xC
0x72bcc6  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x72bccb  ldstr    aSharebylinkfai// "ShareByLinkFailureReason"
0x72bcd0  ldc.i4.s 0x12
0x72bcd2  box      Microsoft.SharePoint.Sharing.ShareByLinkFailureReason
0x72bcd7  callvirt instance string [mscorlib]System.Object::ToString()
0x72bcdc  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x72bce1  ldloc.s  0xC
0x72bce3  throw
0x72bce4  ldloc.s  0x29
0x72bce6  ldfld    class Microsoft.SharePoint.Sharing.SPShareSettings <>c__DisplayClass54::settings
0x72bceb  callvirt instance valuetype Microsoft.SharePoint.SharingLinkKind Microsoft.SharePoint.Sharing.SPShareSettings::get_ShareKind()
0x72bcf0  ldc.i4.3
0x72bcf1  beq.s    loc_72BD2E
0x72bcf3  ldloc.s  0x29
0x72bcf5  ldfld    class Microsoft.SharePoint.Sharing.SPShareSettings <>c__DisplayClass54::settings
0x72bcfa  callvirt instance valuetype Microsoft.SharePoint.SharingLinkKind Microsoft.SharePoint.Sharing.SPShareSettings::get_ShareKind()
0x72bcff  ldc.i4.5
0x72bd00  beq.s    loc_72BD2E
0x72bd02  ldloc.s  0x29
0x72bd04  ldfld    class Microsoft.SharePoint.Sharing.SPShareSettings <>c__DisplayClass54::settings
0x72bd09  callvirt instance valuetype Microsoft.SharePoint.SharingLinkKind Microsoft.SharePoint.Sharing.SPShareSettings::get_ShareKind()
0x72bd0e  ldc.i4.6
0x72bd0f  bne.un.s loc_72BD2B
0x72bd11  ldloc.s  0x29
0x72bd13  ldfld    class Microsoft.SharePoint.Sharing.SPShareSettings <>c__DisplayClass54::settings
0x72bd18  callvirt instance class Microsoft.SharePoint.SPRoleDefinition Microsoft.SharePoint.Sharing.SPShareSettings::get_RoleDefinition()
0x72bd1d  callvirt instance valuetype Microsoft.SharePoint.SPBasePermissions Microsoft.SharePoint.SPRoleDefinition::get_BasePermissions()
0x72bd22  ldc.i4.4
0x72bd23  conv.i8
0x72bd24  and
0x72bd25  ldc.i4.4
0x72bd26  conv.i8
0x72bd27  ceq
0x72bd29  br.s     loc_72BD2F
0x72bd2b  ldc.i4.0
0x72bd2c  br.s     loc_72BD2F
0x72bd2e  ldc.i4.1
0x72bd2f  stloc.s  0xD
0x72bd31  ldloc.2
0x72bd32  ldloc.s  0xD
0x72bd34  ldloc.s  0x29
0x72bd36  ldfld    class Microsoft.SharePoint.Sharing.SPShareSettings <>c__DisplayClass54::settings
0x72bd3b  callvirt instance bool Microsoft.SharePoint.Sharing.SPShareSettings::get_AllowAnonymousAccess()
0x72bd40  ldloc.s  0x29
0x72bd42  ldfld    class Microsoft.SharePoint.Sharing.SPShareSettings <>c__DisplayClass54::settings
0x72bd47  callvirt instance bool Microsoft.SharePoint.Sharing.SPShareSettings::get_AllowExternalUserAccess()
0x72bd4c  ldloc.s  0x29
0x72bd4e  ldfld    class Microsoft.SharePoint.Sharing.SPShareSettings <>c__DisplayClass54::settings
0x72bd53  callvirt instance bool Microsoft.SharePoint.Sharing.SPShareSettings::get_RestrictShareMembership()
0x72bd58  ldloca.s 0xE
0x72bd5a  call     bool Microsoft.SharePoint.Sharing.SPShareByLinkImplementation::IsShareableByLink(class Microsoft.SharePoint.Sharing.ISPShareableByLinkObject shareableObject, bool allowEditing, bool allowAnonymousAccess, bool allowExternalAccess, bool peopleSharingLink, [out] valuetype Microsoft.SharePoint.Sharing.ShareByLinkFailureReason& failureReason)
0x72bd5f  brtrue.s loc_72BD9E
0x72bd61  ldc.i4   0x17CE75A
0x72bd66  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x72bd6b  ldc.i4.s 0x32
0x72bd6d  ldstr    aSharelinkCalle_0// "ShareLink: Called method on object that"...
0x72bd72  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x72bd77  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0x72bd7c  stloc.s  0xF
0x72bd7e  ldloc.s  0xF
0x72bd80  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x72bd85  ldstr    aSharebylinkfai// "ShareByLinkFailureReason"
0x72bd8a  ldloc.s  0xE
0x72bd8c  box      Microsoft.SharePoint.Sharing.ShareByLinkFailureReason
0x72bd91  callvirt instance string [mscorlib]System.Object::ToString()
0x72bd96  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x72bd9b  ldloc.s  0xF
0x72bd9d  throw
0x72bd9e  ldloc.s  0x29
0x72bda0  ldarg.0
0x72bda1  ldloc.s  0x29
0x72bda3  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass54::userLoginsList
0x72bda8  ldloc.s  0x29
0x72bdaa  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.SPUserInfo> <>c__DisplayClass54::userInfoList
0x72bdaf  call     instance class Microsoft.SharePoint.SPUserCollection Microsoft.SharePoint.ObjectSharingContext::InitResolvedUserCollection(class [mscorlib]System.Collections.Generic.List`1<string> userLoginsList, class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.SPUserInfo> userInfoList)
0x72bdb4  stfld    class Microsoft.SharePoint.SPUserCollection <>c__DisplayClass54::resolvedUsers
0x72bdb9  ldloc.s  6
0x72bdbb  brtrue   loc_72BE5D
0x72bdc0  ldloc.s  0x29
0x72bdc2  ldfld    class Microsoft.SharePoint.SPUserCollection <>c__DisplayClass54::resolvedUsers
0x72bdc7  callvirt instance class [mscorlib]System.Collections.IEnumerator Microsoft.SharePoint.SPBaseCollection::GetEnumerator()
0x72bdcc  stloc.s  0x2A
0x72bdce  br.s     loc_72BE3D
0x72bdd0  ldloc.s  0x2A
0x72bdd2  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x72bdd7  castclass Microsoft.SharePoint.SPUser
0x72bddc  stloc.s  0x10
0x72bdde  ldloc.s  0x10
0x72bde0  callvirt instance bool Microsoft.SharePoint.SPUser::get_IsShareByEmailGuestUser()
0x72bde5  brfalse.s loc_72BE3D
0x72bde7  ldc.i4   0x168A180
0x72bdec  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x72bdf1  ldc.i4.s 0x32
0x72bdf3  ldstr    aSharelinkCalle_1// "ShareLink: Called method with external "...
0x72bdf8  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x72bdfd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x72be02  ldstr    aEmailrecipient// "EmailRecipientExternalUser"
0x72be07  ldc.i4.0
0x72be08  newarr   [mscorlib]System.Object
0x72be0d  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x72be12  stloc.s  0x11
0x72be14  ldloc.s  0x11
0x72be16  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x72be1b  stloc.s  0x12
0x72be1d  ldloc.s  0x12
0x72be1f  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x72be24  ldstr    aSharebylinkfai// "ShareByLinkFailureReason"
0x72be29  ldc.i4.s 0x12
0x72be2b  box      Microsoft.SharePoint.Sharing.ShareByLinkFailureReason
0x72be30  callvirt instance string [mscorlib]System.Object::ToString()
0x72be35  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x72be3a  ldloc.s  0x12
0x72be3c  throw
0x72be3d  ldloc.s  0x2A
0x72be3f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x72be44  brtrue.s loc_72BDD0
0x72be46  leave.s  loc_72BE5D
0x72be48  ldloc.s  0x2A
0x72be4a  isinst   [mscorlib]System.IDisposable
0x72be4f  stloc.s  0x2B
0x72be51  ldloc.s  0x2B
0x72be53  brfalse.s loc_72BE5C
0x72be55  ldloc.s  0x2B
0x72be57  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x72be5c  endfinally
0x72be5d  call     bool Microsoft.SharePoint.SPGlobal::get_IsSPO()
0x72be62  brfalse.s loc_72BED2
0x72be64  call     bool Microsoft.SharePoint.SPPreventExternalUsersFromResharingUtility::IsPreventExternalUsersFromResharingFlightOn()
0x72be69  brfalse.s loc_72BED2
0x72be6b  ldarg.0
0x72be6c  callvirt instance class Microsoft.SharePoint.SPSecurableObject Microsoft.SharePoint.SharingBase::get_Securable()
0x72be71  call     bool Microsoft.SharePoint.SPPreventExternalUsersFromResharingUtility::CanUserShareSecurable(class Microsoft.SharePoint.SPSecurableObject securable)
0x72be76  stloc.s  0x13
0x72be78  ldloc.s  0x13
0x72be7a  brtrue.s loc_72BED2
0x72be7c  ldc.i4   0x17CE75B
0x72be81  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x72be86  ldc.i4.s 0xA
0x72be88  ldstr    aObjectsharingc_31// "ObjectSharingContext::ShareLink(): Exte"...
0x72be8d  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x72be92  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x72be97  ldstr    aAccessdenied// "AccessDenied"
0x72be9c  ldc.i4.0
0x72be9d  newarr   [mscorlib]System.Object
0x72bea2  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x72bea7  stloc.s  0x14
0x72bea9  ldloc.s  0x14
0x72beab  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x72beb0  stloc.s  0x15
0x72beb2  ldloc.s  0x15
0x72beb4  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x72beb9  ldstr    aSharebylinkfai// "ShareByLinkFailureReason"
0x72bebe  ldc.i4.s 0xD
0x72bec0  box      Microsoft.SharePoint.Sharing.ShareByLinkFailureReason
0x72bec5  callvirt instance string [mscorlib]System.Object::ToString()
0x72beca  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
  ... truncated ...
```
