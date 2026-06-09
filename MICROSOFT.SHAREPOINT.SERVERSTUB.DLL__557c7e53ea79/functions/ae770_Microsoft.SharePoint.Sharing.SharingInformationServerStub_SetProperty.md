# Microsoft.SharePoint.Sharing.SharingInformationServerStub::SetProperty

- ea: `0xae770`
- end: `0xaeb48`
- name: `Microsoft.SharePoint.Sharing.SharingInformationServerStub::SetProperty`
- size: `984`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xae770`

## string_xrefs

- `0xae7c9`: `anonymousLinkExpirationRestrictionDays`
- `0xae929`: `anonymousLinkExpirationRestrictionDays`
- `0xae7f9`: `canRequestAccessForGrantAccess`
- `0xae999`: `canRequestAccessForGrantAccess`
- `0xae829`: `defaultLinkKind`
- `0xaea09`: `defaultLinkKind`
- `0xae835`: `defaultShareLinkPermission`
- `0xaea25`: `defaultShareLinkPermission`
- `0xae85c`: `microserviceShareUiUrl`
- `0xaea79`: `microserviceShareUiUrl`

## pseudocode

```c

```

## disassembly

```asm
0xae770  ldarg.s  4
0xae772  brtrue.s loc_AE77F
0xae774  ldstr    aProxycontext// "proxyContext"
0xae779  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xae77e  throw
0xae77f  ldarg.1
0xae780  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation
0xae785  stloc.0
0xae786  ldloc.0
0xae787  brtrue.s loc_AE794
0xae789  ldstr    aTarget// "target"
0xae78e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xae793  throw
0xae794  ldarg.2
0xae795  brtrue.s loc_AE7A2
0xae797  ldstr    aPropname// "propName"
0xae79c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xae7a1  throw
0xae7a2  ldarg.0
0xae7a3  ldarg.2
0xae7a4  ldarg.s  4
0xae7a6  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae7ab  starg.s  2
0xae7ad  ldarg.2
0xae7ae  dup
0xae7af  stloc.1
0xae7b0  brfalse  loc_AEB3C
0xae7b5  volatile.
0xae7b7  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001c7c-1
0xae7bc  brtrue   loc_AE8BD
0xae7c1  ldc.i4.s 0x13
0xae7c3  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xae7c8  dup
0xae7c9  ldstr    aAnonymouslinke// "anonymousLinkExpirationRestrictionDays"
0xae7ce  ldc.i4.0
0xae7cf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae7d4  dup
0xae7d5  ldstr    aBlockpeoplepic_0// "blockPeoplePickerAndSharing"
0xae7da  ldc.i4.1
0xae7db  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae7e0  dup
0xae7e1  ldstr    aCanaddexternal// "canAddExternalPrincipal"
0xae7e6  ldc.i4.2
0xae7e7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae7ec  dup
0xae7ed  ldstr    aCanaddinternal// "canAddInternalPrincipal"
0xae7f2  ldc.i4.3
0xae7f3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae7f8  dup
0xae7f9  ldstr    aCanrequestacce// "canRequestAccessForGrantAccess"
0xae7fe  ldc.i4.4
0xae7ff  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae804  dup
0xae805  ldstr    aCansendemail_0// "canSendEmail"
0xae80a  ldc.i4.5
0xae80b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae810  dup
0xae811  ldstr    aCanusesimplifi// "canUseSimplifiedRoles"
0xae816  ldc.i4.6
0xae817  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae81c  dup
0xae81d  ldstr    aCurrentrole// "currentRole"
0xae822  ldc.i4.7
0xae823  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae828  dup
0xae829  ldstr    aDefaultlinkkin// "defaultLinkKind"
0xae82e  ldc.i4.8
0xae82f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae834  dup
0xae835  ldstr    aDefaultshareli_1// "defaultShareLinkPermission"
0xae83a  ldc.i4.s 9
0xae83c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae841  dup
0xae842  ldstr    aDirecturl// "directUrl"
0xae847  ldc.i4.s 0xA
0xae849  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae84e  dup
0xae84f  ldstr    aHasuniquepermi// "hasUniquePermissions"
0xae854  ldc.i4.s 0xB
0xae856  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae85b  dup
0xae85c  ldstr    aMicroservicesh// "microserviceShareUiUrl"
0xae861  ldc.i4.s 0xC
0xae863  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae868  dup
0xae869  ldstr    aSharedobjectty// "sharedObjectType"
0xae86e  ldc.i4.s 0xD
0xae870  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae875  dup
0xae876  ldstr    aShareuiurl// "shareUiUrl"
0xae87b  ldc.i4.s 0xE
0xae87d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae882  dup
0xae883  ldstr    aSharingabiliti// "sharingAbilities"
0xae888  ldc.i4.s 0xF
0xae88a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae88f  dup
0xae890  ldstr    aSharingstatus// "sharingStatus"
0xae895  ldc.i4.s 0x10
0xae897  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae89c  dup
0xae89d  ldstr    aShowexternalsh_0// "showExternalSharingWarning"
0xae8a2  ldc.i4.s 0x11
0xae8a4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae8a9  dup
0xae8aa  ldstr    aWeburl_0// "webUrl"
0xae8af  ldc.i4.s 0x12
0xae8b1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae8b6  volatile.
0xae8b8  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001c7c-1
0xae8bd  volatile.
0xae8bf  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001c7c-1
0xae8c4  ldloc.1
0xae8c5  ldloca.s 2
0xae8c7  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xae8cc  brfalse  loc_AEB3C
0xae8d1  ldloc.2
0xae8d2  switch   loc_AE928, loc_AE944, loc_AE960, loc_AE97C, loc_AE998, loc_AE9B4, loc_AE9D0, loc_AE9EC, loc_AEA08, loc_AEA24, loc_AEA40, loc_AEA5C, loc_AEA78, loc_AEA94, loc_AEAB0, loc_AEACC, loc_AEAE8, loc_AEB04, loc_AEB20
0xae923  br       loc_AEB3C
0xae928  ldarg.0
0xae929  ldstr    aAnonymouslinke// "anonymousLinkExpirationRestrictionDays"
0xae92e  ldarg.s  4
0xae930  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae935  ldloc.0
0xae936  ldarg.3
0xae937  ldarg.s  4
0xae939  call     int32 [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToInt32(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae93e  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_AnonymousLinkExpirationRestrictionDays(int32)
0xae943  ret
0xae944  ldarg.0
0xae945  ldstr    aBlockpeoplepic_0// "blockPeoplePickerAndSharing"
0xae94a  ldarg.s  4
0xae94c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae951  ldloc.0
0xae952  ldarg.3
0xae953  ldarg.s  4
0xae955  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae95a  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_BlockPeoplePickerAndSharing(bool)
0xae95f  ret
0xae960  ldarg.0
0xae961  ldstr    aCanaddexternal// "canAddExternalPrincipal"
0xae966  ldarg.s  4
0xae968  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae96d  ldloc.0
0xae96e  ldarg.3
0xae96f  ldarg.s  4
0xae971  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae976  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_CanAddExternalPrincipal(bool)
0xae97b  ret
0xae97c  ldarg.0
0xae97d  ldstr    aCanaddinternal// "canAddInternalPrincipal"
0xae982  ldarg.s  4
0xae984  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae989  ldloc.0
0xae98a  ldarg.3
0xae98b  ldarg.s  4
0xae98d  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae992  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_CanAddInternalPrincipal(bool)
0xae997  ret
0xae998  ldarg.0
0xae999  ldstr    aCanrequestacce// "canRequestAccessForGrantAccess"
0xae99e  ldarg.s  4
0xae9a0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae9a5  ldloc.0
0xae9a6  ldarg.3
0xae9a7  ldarg.s  4
0xae9a9  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae9ae  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_CanRequestAccessForGrantAccess(bool)
0xae9b3  ret
0xae9b4  ldarg.0
0xae9b5  ldstr    aCansendemail_0// "canSendEmail"
0xae9ba  ldarg.s  4
0xae9bc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae9c1  ldloc.0
0xae9c2  ldarg.3
0xae9c3  ldarg.s  4
0xae9c5  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae9ca  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_CanSendEmail(bool)
0xae9cf  ret
0xae9d0  ldarg.0
0xae9d1  ldstr    aCanusesimplifi// "canUseSimplifiedRoles"
0xae9d6  ldarg.s  4
0xae9d8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae9dd  ldloc.0
0xae9de  ldarg.3
0xae9df  ldarg.s  4
0xae9e1  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae9e6  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_CanUseSimplifiedRoles(bool)
0xae9eb  ret
0xae9ec  ldarg.0
0xae9ed  ldstr    aCurrentrole// "currentRole"
0xae9f2  ldarg.s  4
0xae9f4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae9f9  ldloc.0
0xae9fa  ldarg.3
0xae9fb  ldarg.s  4
0xae9fd  call     T0x2B000292
0xaea02  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_CurrentRole(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Role)
0xaea07  ret
0xaea08  ldarg.0
0xaea09  ldstr    aDefaultlinkkin// "defaultLinkKind"
0xaea0e  ldarg.s  4
0xaea10  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaea15  ldloc.0
0xaea16  ldarg.3
0xaea17  ldarg.s  4
0xaea19  call     T0x2B000115
0xaea1e  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_DefaultLinkKind(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkKind)
0xaea23  ret
0xaea24  ldarg.0
0xaea25  ldstr    aDefaultshareli_1// "defaultShareLinkPermission"
0xaea2a  ldarg.s  4
0xaea2c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaea31  ldloc.0
0xaea32  ldarg.3
0xaea33  ldarg.s  4
0xaea35  call     T0x2B000292
0xaea3a  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_DefaultShareLinkPermission(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Role)
0xaea3f  ret
0xaea40  ldarg.0
0xaea41  ldstr    aDirecturl// "directUrl"
0xaea46  ldarg.s  4
0xaea48  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaea4d  ldloc.0
0xaea4e  ldarg.3
0xaea4f  ldarg.s  4
0xaea51  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaea56  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_DirectUrl(string)
0xaea5b  ret
0xaea5c  ldarg.0
0xaea5d  ldstr    aHasuniquepermi// "hasUniquePermissions"
0xaea62  ldarg.s  4
0xaea64  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaea69  ldloc.0
0xaea6a  ldarg.3
0xaea6b  ldarg.s  4
0xaea6d  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaea72  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_HasUniquePermissions(bool)
0xaea77  ret
0xaea78  ldarg.0
0xaea79  ldstr    aMicroservicesh// "microserviceShareUiUrl"
0xaea7e  ldarg.s  4
0xaea80  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaea85  ldloc.0
0xaea86  ldarg.3
0xaea87  ldarg.s  4
0xaea89  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaea8e  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_MicroserviceShareUiUrl(string)
0xaea93  ret
0xaea94  ldarg.0
0xaea95  ldstr    aSharedobjectty// "sharedObjectType"
0xaea9a  ldarg.s  4
0xaea9c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaeaa1  ldloc.0
0xaeaa2  ldarg.3
0xaeaa3  ldarg.s  4
0xaeaa5  call     T0x2B000116
0xaeaaa  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_SharedObjectType(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SPSharedObjectType)
0xaeaaf  ret
0xaeab0  ldarg.0
0xaeab1  ldstr    aShareuiurl// "shareUiUrl"
0xaeab6  ldarg.s  4
0xaeab8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaeabd  ldloc.0
0xaeabe  ldarg.3
0xaeabf  ldarg.s  4
0xaeac1  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaeac6  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_ShareUiUrl(string)
0xaeacb  ret
0xaeacc  ldarg.0
0xaeacd  ldstr    aSharingabiliti// "sharingAbilities"
0xaead2  ldarg.s  4
0xaead4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaead9  ldloc.0
0xaeada  ldarg.3
0xaeadb  ldarg.s  4
0xaeadd  call     T0x2B00029E
0xaeae2  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_SharingAbilities(class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingAbilities)
0xaeae7  ret
0xaeae8  ldarg.0
0xaeae9  ldstr    aSharingstatus// "sharingStatus"
0xaeaee  ldarg.s  4
0xaeaf0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaeaf5  ldloc.0
0xaeaf6  ldarg.3
0xaeaf7  ldarg.s  4
0xaeaf9  call     T0x2B00029F
0xaeafe  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_SharingStatus(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingStatus)
0xaeb03  ret
0xaeb04  ldarg.0
0xaeb05  ldstr    aShowexternalsh_0// "showExternalSharingWarning"
0xaeb0a  ldarg.s  4
0xaeb0c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaeb11  ldloc.0
0xaeb12  ldarg.3
0xaeb13  ldarg.s  4
0xaeb15  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaeb1a  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_ShowExternalSharingWarning(bool)
0xaeb1f  ret
0xaeb20  ldarg.0
  ... truncated ...
```
