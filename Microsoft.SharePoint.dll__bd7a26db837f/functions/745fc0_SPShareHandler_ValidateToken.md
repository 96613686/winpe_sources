# SPShareHandler::ValidateToken

- ea: `0x745fc0`
- end: `0x74652e`
- name: `SPShareHandler::ValidateToken`
- size: `1390`
- prototype: ``
- caller_count: `2`
- callee_count: `45`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x743d40`
- `0xbdf510`

## callees

- `0x26f690`
- `0x270110`
- `0x50b9f0`
- `0x50ba00`
- `0x52a050`
- `0x53e9a0`
- `0x5b3970`
- `0x5b6640`
- `0x5c24f0`
- `0x5c4b20`
- `0x5d2f30`
- `0x6c9890`
- `0x741450`
- `0x7415e0`
- `0x7418a0`
- `0x741bb0`
- `0x741c90`
- `0x741d50`
- `0x745120`
- `0x745130`
- `0x7454e0`
- `0x745520`
- `0x745c60`
- `0x745e60`
- `0x745fc0`
- `0x746530`
- `0x7467c0`
- `0x746a10`
- `0x746b30`
- `0x747980`
- `0x749130`
- `0x75ac80`
- `0x75adb0`
- `0x75add0`
- `0x75eef0`
- `0x75ef20`
- `0x75ef80`
- `0x75f1b0`
- `0x75f460`
- `0x75f4a0`
- `0x7be4d0`
- `0x7be510`
- `0x7beb40`
- `0x93dab0`
- `0x957b70`

## string_xrefs

- `0x745fc0`: `SPShareByLinkHandler.ValidateToken`
- `0x745ffd`: `SPShareByLinkHandler.ValidateToken: Not share by link request.`
- `0x746066`: `SPShareByLinkHandler.ValidateToken: Shared object not found`
- `0x74617c`: `SPShareByLinkHandler.ValidateToken: Share specified by Share Token could not be found`
- `0x7461c3`: `IsSharingLinksEnabled Check`
- `0x746202`: `SPShareByLinkHandler.ValidateToken: Requested Organization link while CompanyWideSharingLinks is DISABLED.`
- `0x746244`: `SPShareByLinkHandler.ValidateToken: Sharing disabled at SPSite level - SPSite.ShareByLinkEnabled is false`
- `0x746294`: `SPShareByLinkHandler.ValidateToken: Could not validate Token or AuthKey`
- `0x7462bb`: `SPShareByLinkHandler::ValidateToken - Validate sharing link token using sharing objects.`
- `0x7462d4`: `SPShareByLinkHandler.ValidateToken: Could not validate the shareable object.`
- `0x746404`: `SPShareByLinkHandler.ValidateToken: No valid {0} {1} link found`
- `0x746490`: `SPShareByLinkHandler.ValidateToken: failed expiration validation`
- `0x7464d2`: `LinkKind`

## pseudocode

```c

```

## disassembly

```asm
0x745fc0  ldstr    aSpsharebylinkh_64// "SPShareByLinkHandler.ValidateToken"
0x745fc5  ldc.i4   0x1351861
0x745fca  ldc.i4   0x1351862
0x745fcf  ldc.i4   0x1351863
0x745fd4  ldc.i4.0
0x745fd5  ldnull
0x745fd6  newobj   instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitor::.ctor(string scenarioName, unsigned int32 startTag, unsigned int32 successTag, unsigned int32 unexpectedFailureTag, [opt] valuetype Microsoft.SharePoint.Administration.SPLogType logType, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x745fdb  stloc.0
0x745fdc  ldarg.2
0x745fdd  ldarg.0
0x745fde  ldfld    class Microsoft.SharePoint.Sharing.ISPShareableByLinkObject SPShareHandler::m_shareableObject
0x745fe3  stind.ref
0x745fe4  ldarg.0
0x745fe5  call     instance class Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters SPShareHandler::get_ParsedParameters()
0x745fea  callvirt instance bool Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::get_IsShareByLinkRequest()
0x745fef  brtrue.s loc_74600D
0x745ff1  ldc.i4   0x17CF6C4
0x745ff6  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x745ffb  ldc.i4.s 0xA
0x745ffd  ldstr    aSpsharebylinkh_65// "SPShareByLinkHandler.ValidateToken: Not"...
0x746002  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x746007  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0x74600c  throw
0x74600d  ldarg.0
0x74600e  ldfld    class Microsoft.SharePoint.Sharing.SPSharingManager SPShareHandler::sharingManager
0x746013  brtrue.s loc_746028
0x746015  call     bool Microsoft.SharePoint.Sharing.SPSharingManager::IsDeepReferenceStorageManagerKillswitchActive()
0x74601a  brtrue.s loc_746028
0x74601c  ldarg.0
0x74601d  ldarg.1
0x74601e  newobj   instance void Microsoft.SharePoint.Sharing.SPSharingManager::.ctor(class Microsoft.SharePoint.SPWeb systemWeb)
0x746023  stfld    class Microsoft.SharePoint.Sharing.SPSharingManager SPShareHandler::sharingManager
0x746028  ldc.i4.0
0x746029  stloc.1
0x74602a  ldarg.0
0x74602b  call     instance class Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters SPShareHandler::get_ParsedParameters()
0x746030  callvirt instance bool Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::get_IsShareTokenEnabledLink()
0x746035  brfalse  loc_7461B1
0x74603a  ldarg.0
0x74603b  ldarg.1
0x74603c  ldarg.0
0x74603d  call     instance valuetype [mscorlib]System.Guid SPShareHandler::get_SharedObjectUniqueId()
0x746042  ldarg.0
0x746043  ldfld    bool SPShareHandler::m_isFolder
0x746048  ldarg.0
0x746049  call     instance class Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters SPShareHandler::get_ParsedParameters()
0x74604e  callvirt instance string Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::get_AuthKey()
0x746053  call     instance class Microsoft.SharePoint.Sharing.SPShare SPShareHandler::GetStoredShareByAuthKey(class Microsoft.SharePoint.SPWeb elevatedWeb, valuetype [mscorlib]System.Guid objectUniqueId, bool objectIsFolder, string authKey)
0x746058  brfalse  loc_74617C
0x74605d  ldarg.0
0x74605e  ldarg.1
0x74605f  call     instance bool SPShareHandler::ValidateShareableObject(class Microsoft.SharePoint.SPWeb web)
0x746064  brtrue.s loc_74609B
0x746066  ldstr    aSpsharebylinkh_66// "SPShareByLinkHandler.ValidateToken: Sha"...
0x74606b  stloc.2
0x74606c  ldc.i4   0x17CF6C5
0x746071  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x746076  ldc.i4.s 0x14
0x746078  ldloc.2
0x746079  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x74607e  ldloc.0
0x74607f  ldc.i4   0x138F4A1
0x746084  ldloc.2
0x746085  ldnull
0x746086  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x74608b  ldarg.0
0x74608c  ldc.i4.s 0x18
0x74608e  call     instance void SPShareHandler::set_Error(valuetype ErrorReason value)
0x746093  ldc.i4.0
0x746094  stloc.s  0xB
0x746096  leave    loc_74652B
0x74609b  ldarg.0
0x74609c  ldarg.0
0x74609d  ldfld    class Microsoft.SharePoint.Sharing.SPShare SPShareHandler::m_activeShare
0x7460a2  callvirt instance valuetype Microsoft.SharePoint.SharingLinkKind Microsoft.SharePoint.Sharing.SPShare::get_ShareKind()
0x7460a7  stfld    valuetype Microsoft.SharePoint.SharingLinkKind SPShareHandler::m_linkKind
0x7460ac  ldarg.0
0x7460ad  ldarg.0
0x7460ae  ldfld    class Microsoft.SharePoint.Sharing.SPShare SPShareHandler::m_activeShare
0x7460b3  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.SharePoint.Sharing.SPShare::get_ExpirationDateTime()
0x7460b8  stloc.s  0xC
0x7460ba  ldloca.s 0xC
0x7460bc  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x7460c1  brtrue.s loc_7460CA
0x7460c3  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x7460c8  br.s     loc_7460D1
0x7460ca  ldloca.s 0xC
0x7460cc  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::GetValueOrDefault()
0x7460d1  stfld    valuetype [mscorlib]System.DateTime SPShareHandler::m_expirationTime
0x7460d6  ldarg.0
0x7460d7  ldarg.0
0x7460d8  ldfld    class Microsoft.SharePoint.Sharing.SPShare SPShareHandler::m_activeShare
0x7460dd  ldarg.0
0x7460de  ldflda   valuetype SharingType SPShareHandler::m_type
0x7460e3  ldarg.0
0x7460e4  ldflda   bool SPShareHandler::m_isReadWrite
0x7460e9  call     instance void SPShareHandler::GetShareTypeAndAccessLevel(class Microsoft.SharePoint.Sharing.SPShare share, [out] valuetype SharingType& sharingType, [out] bool& isWriteAccess)
0x7460ee  ldarg.0
0x7460ef  ldfld    class Microsoft.SharePoint.Sharing.SPShare SPShareHandler::m_activeShare
0x7460f4  callvirt instance bool Microsoft.SharePoint.Sharing.SPShare::get_AllowAnonymous()
0x7460f9  brfalse  loc_7461B1
0x7460fe  ldarg.0
0x7460ff  ldfld    class Microsoft.SharePoint.Sharing.ISPShareableByLinkObject SPShareHandler::m_shareableObject
0x746104  callvirt instance bool Microsoft.SharePoint.Sharing.ISPShareableByLinkObject::get_IsContainer()
0x746109  brfalse.s loc_74612D
0x74610b  ldarg.0
0x74610c  ldfld    class Microsoft.SharePoint.Sharing.ISPShareableByLinkObject SPShareHandler::m_shareableObject
0x746111  callvirt instance class Microsoft.SharePoint.SPListItem Microsoft.SharePoint.Sharing.ISPShareableByLinkObject::get_Item()
0x746116  brfalse.s loc_74612D
0x746118  ldarg.0
0x746119  ldfld    class Microsoft.SharePoint.Sharing.ISPShareableByLinkObject SPShareHandler::m_shareableObject
0x74611e  callvirt instance class Microsoft.SharePoint.SPListItem Microsoft.SharePoint.Sharing.ISPShareableByLinkObject::get_Item()
0x746123  callvirt instance bool Microsoft.SharePoint.SPListItem::get_ServerRedirected()
0x746128  brfalse  loc_7461B1
0x74612d  ldarg.0
0x74612e  ldfld    class Microsoft.SharePoint.Sharing.SPShare SPShareHandler::m_activeShare
0x746133  callvirt instance bool Microsoft.SharePoint.Sharing.SPShare::get_HasLinkClaim()
0x746138  brtrue.s loc_7461B1
0x74613a  ldarg.0
0x74613b  ldfld    bool SPShareHandler::m_isReadWrite
0x746140  ldarg.0
0x746141  call     instance valuetype [mscorlib]System.Guid SPShareHandler::get_SharedObjectUniqueId()
0x746146  ldarg.0
0x746147  ldfld    valuetype SharingType SPShareHandler::m_type
0x74614c  call     string Microsoft.SharePoint.Sharing.SPShareByLinkHelper::GetGuestUserLogin(bool isReadWrite, valuetype [mscorlib]System.Guid uniqueId, valuetype SharingType type)
0x746151  stloc.3
0x746152  ldarg.1
0x746153  callvirt instance class Microsoft.SharePoint.SPUserCollection Microsoft.SharePoint.SPWeb::get_SiteUsers()
0x746158  ldloc.3
0x746159  callvirt instance class Microsoft.SharePoint.SPUser Microsoft.SharePoint.SPUserCollection::GetByLoginNoThrow(string loginName)
0x74615e  stloc.s  4
0x746160  ldarg.0
0x746161  ldloc.s  4
0x746163  callvirt instance int32 Microsoft.SharePoint.SPMember::get_ID()
0x746168  stfld    int32 SPShareHandler::m_guestUserId
0x74616d  ldarg.0
0x74616e  ldloc.s  4
0x746170  callvirt instance class Microsoft.SharePoint.SPUserToken Microsoft.SharePoint.SPUser::get_UserToken()
0x746175  stfld    class Microsoft.SharePoint.SPUserToken SPShareHandler::m_guestUserToken
0x74617a  br.s     loc_7461B1
0x74617c  ldstr    aSpsharebylinkh_67// "SPShareByLinkHandler.ValidateToken: Sha"...
0x746181  stloc.2
0x746182  ldc.i4   0x17CF6C6
0x746187  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x74618c  ldc.i4.s 0x14
0x74618e  ldloc.2
0x74618f  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x746194  ldloc.0
0x746195  ldc.i4   0x138F4A3
0x74619a  ldloc.2
0x74619b  ldnull
0x74619c  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x7461a1  ldarg.0
0x7461a2  ldc.i4.s 0x12
0x7461a4  call     instance void SPShareHandler::set_Error(valuetype ErrorReason value)
0x7461a9  ldc.i4.0
0x7461aa  stloc.s  0xB
0x7461ac  leave    loc_74652B
0x7461b1  ldarg.0
0x7461b2  ldfld    class Microsoft.SharePoint.Sharing.SPShare SPShareHandler::m_activeShare
0x7461b7  brfalse.s loc_7461EA
0x7461b9  ldsfld   valuetype [mscorlib]System.Guid SPShareHandler::IsSharingLinksEnabledCheckKillswitchId
0x7461be  ldstr    a8142017// "8/14/2017"
0x7461c3  ldstr    aIssharinglinks// "IsSharingLinksEnabled Check"
0x7461c8  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x7461cd  brtrue.s loc_7461EA
0x7461cf  ldarg.0
0x7461d0  ldarg.1
0x7461d1  ldarg.0
0x7461d2  ldfld    class Microsoft.SharePoint.Sharing.SPShare SPShareHandler::m_activeShare
0x7461d7  ldloc.0
0x7461d8  call     instance bool SPShareHandler::IsSharingLinksEnabled(class Microsoft.SharePoint.SPWeb adminWeb, class Microsoft.SharePoint.Sharing.SPShare activeShare, class Microsoft.SharePoint.Utilities.SPReliabilityMonitor monitor)
0x7461dd  brtrue   loc_746279
0x7461e2  ldc.i4.0
0x7461e3  stloc.s  0xB
0x7461e5  leave    loc_74652B
0x7461ea  ldarg.0
0x7461eb  ldfld    valuetype SharingType SPShareHandler::m_type
0x7461f0  ldc.i4.2
0x7461f1  bne.un.s loc_746237
0x7461f3  ldc.i4.0
0x7461f4  stloc.s  5
0x7461f6  ldarg.1
0x7461f7  callvirt instance bool Microsoft.SharePoint.SPWeb::get_EnableCompanyWideSharingLinks()
0x7461fc  stloc.s  5
0x7461fe  ldloc.s  5
0x746200  brtrue.s loc_746279
0x746202  ldstr    aSpsharebylinkh_68// "SPShareByLinkHandler.ValidateToken: Req"...
0x746207  stloc.2
0x746208  ldc.i4   0x17CF6C7
0x74620d  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x746212  ldc.i4.s 0x32
0x746214  ldloc.2
0x746215  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x74621a  ldloc.0
0x74621b  ldc.i4   0x1351881
0x746220  ldloc.2
0x746221  ldnull
0x746222  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x746227  ldarg.0
0x746228  ldc.i4.s 0xB
0x74622a  call     instance void SPShareHandler::set_Error(valuetype ErrorReason value)
0x74622f  ldc.i4.0
0x746230  stloc.s  0xB
0x746232  leave    loc_74652B
0x746237  ldarg.1
0x746238  callvirt instance class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPWeb::get_Site()
0x74623d  callvirt instance bool Microsoft.SharePoint.SPSite::get_ShareByLinkEnabled()
0x746242  brtrue.s loc_746279
0x746244  ldstr    aSpsharebylinkh_69// "SPShareByLinkHandler.ValidateToken: Sha"...
0x746249  stloc.2
0x74624a  ldc.i4   0x17CF6C8
0x74624f  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x746254  ldc.i4.s 0x14
0x746256  ldloc.2
0x746257  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x74625c  ldloc.0
0x74625d  ldc.i4   0x1351883
0x746262  ldloc.2
0x746263  ldnull
0x746264  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x746269  ldarg.0
0x74626a  ldc.i4.s 0xC
0x74626c  call     instance void SPShareHandler::set_Error(valuetype ErrorReason value)
0x746271  ldc.i4.0
0x746272  stloc.s  0xB
0x746274  leave    loc_74652B
0x746279  ldarg.0
0x74627a  ldarg.1
0x74627b  ldloc.1
0x74627c  ldloc.0
0x74627d  call     instance bool SPShareHandler::ValidateGuestAccessToken(class Microsoft.SharePoint.SPWeb adminWeb, int32 groupId, class Microsoft.SharePoint.Utilities.SPReliabilityMonitor monitor)
0x746282  brtrue.s loc_7462AF
0x746284  ldarg.0
0x746285  ldarg.1
0x746286  ldarg.0
0x746287  call     instance valuetype Microsoft.SharePoint.SharingLinkKind SPShareHandler::get_LinkKind()
0x74628c  ldloc.0
0x74628d  call     instance bool SPShareHandler::ValidateAuthKey(class Microsoft.SharePoint.SPWeb adminWeb, valuetype Microsoft.SharePoint.SharingLinkKind linkKind, class Microsoft.SharePoint.Utilities.SPReliabilityMonitor monitor)
0x746292  brtrue.s loc_7462AF
0x746294  ldstr    aSpsharebylinkh_70// "SPShareByLinkHandler.ValidateToken: Cou"...
0x746299  stloc.2
0x74629a  ldloc.0
0x74629b  ldc.i4   0x1351884
0x7462a0  ldloc.2
0x7462a1  ldnull
0x7462a2  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x7462a7  ldc.i4.0
0x7462a8  stloc.s  0xB
0x7462aa  leave    loc_74652B
0x7462af  ldc.i4   0x17CF6C9
0x7462b4  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x7462b9  ldc.i4.s 0x32
0x7462bb  ldstr    aSpsharebylinkh_71// "SPShareByLinkHandler::ValidateToken - V"...
0x7462c0  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x7462c5  ldarg.0
0x7462c6  ldarg.1
0x7462c7  call     instance bool SPShareHandler::ValidateShareableObject(class Microsoft.SharePoint.SPWeb web)
0x7462cc  brtrue.s loc_7462E7
0x7462ce  ldloc.0
0x7462cf  ldc.i4   0x1351886
0x7462d4  ldstr    aSpsharebylinkh_72// "SPShareByLinkHandler.ValidateToken: Cou"...
0x7462d9  ldnull
0x7462da  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x7462df  ldc.i4.0
0x7462e0  stloc.s  0xB
0x7462e2  leave    loc_74652B
0x7462e7  ldarg.0
0x7462e8  call     instance class Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters SPShareHandler::get_ParsedParameters()
0x7462ed  callvirt instance string Microsoft.SharePoint.Sharing.Internal.SPSharingLinkParsedParameters::get_AuthKey()
0x7462f2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7462f7  brfalse  loc_74639B
0x7462fc  ldarg.0
0x7462fd  call     instance valuetype Microsoft.SharePoint.SharingLinkKind SPShareHandler::get_LinkKind()
0x746302  brfalse  loc_7463F7
0x746307  ldarg.0
0x746308  call     instance valuetype Microsoft.SharePoint.SharingLinkKind SPShareHandler::get_LinkKind()
0x74630d  ldc.i4.6
0x74630e  beq      loc_7463F7
0x746313  ldarg.0
0x746314  call     instance valuetype Microsoft.SharePoint.SharingLinkKind SPShareHandler::get_LinkKind()
0x746319  ldc.i4.1
0x74631a  beq      loc_7463F7
0x74631f  ldarg.0
0x746320  ldfld    class Microsoft.SharePoint.Sharing.SPShare SPShareHandler::m_activeShare
0x746325  brtrue   loc_7463F7
0x74632a  ldarg.0
0x74632b  ldfld    class Microsoft.SharePoint.Sharing.SPSharingManager SPShareHandler::sharingManager
0x746330  brfalse.s loc_746351
0x746332  ldarg.0
0x746333  ldfld    class Microsoft.SharePoint.Sharing.SPSharingManager SPShareHandler::sharingManager
0x746338  ldarg.0
0x746339  ldfld    class Microsoft.SharePoint.Sharing.ISPShareableByLinkObject SPShareHandler::m_shareableObject
0x74633e  ldarg.0
0x74633f  call     instance valuetype Microsoft.SharePoint.SharingLinkKind SPShareHandler::get_LinkKind()
0x746344  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.SharingLinkKind>::.ctor(var<u1>)
0x746349  ldc.i4.7
0x74634a  callvirt instance class Microsoft.SharePoint.Sharing.SPShareCollection Microsoft.SharePoint.Sharing.SPSharingManager::GetSPShareCollection(class Microsoft.SharePoint.Sharing.ISPShareableByLinkObject shareableObject, valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.SharingLinkKind> shareKind, [opt] valuetype Microsoft.SharePoint.Sharing.SPShareCollectionQuerySettings querySettings)
0x74634f  br.s     loc_746369
0x746351  ldarg.0
  ... truncated ...
```
