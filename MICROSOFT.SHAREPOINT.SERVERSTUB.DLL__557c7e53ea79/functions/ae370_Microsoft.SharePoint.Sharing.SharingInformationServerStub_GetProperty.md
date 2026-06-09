# Microsoft.SharePoint.Sharing.SharingInformationServerStub::GetProperty

- ea: `0xae370`
- end: `0xae76f`
- name: `Microsoft.SharePoint.Sharing.SharingInformationServerStub::GetProperty`
- size: `1023`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xae370`

## string_xrefs

- `0xae3c7`: `accessRequestSettings`
- `0xae56b`: `accessRequestSettings`
- `0xae3d3`: `anonymousLinkExpirationRestrictionDays`
- `0xae57e`: `anonymousLinkExpirationRestrictionDays`
- `0xae403`: `canRequestAccessForGrantAccess`
- `0xae5de`: `canRequestAccessForGrantAccess`
- `0xae433`: `defaultLinkKind`
- `0xae63e`: `defaultLinkKind`
- `0xae440`: `defaultShareLinkPermission`
- `0xae656`: `defaultShareLinkPermission`
- `0xae474`: `microserviceShareUiUrl`
- `0xae6ac`: `microserviceShareUiUrl`

## pseudocode

```c

```

## disassembly

```asm
0xae370  ldarg.2
0xae371  brtrue.s loc_AE37E
0xae373  ldstr    aPropname// "propName"
0xae378  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xae37d  throw
0xae37e  ldarg.3
0xae37f  brtrue.s loc_AE38C
0xae381  ldstr    aProxycontext// "proxyContext"
0xae386  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xae38b  throw
0xae38c  ldarg.1
0xae38d  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation
0xae392  stloc.0
0xae393  ldloc.0
0xae394  brtrue.s loc_AE3A1
0xae396  ldstr    aTarget// "target"
0xae39b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xae3a0  throw
0xae3a1  ldarg.0
0xae3a2  ldarg.2
0xae3a3  ldarg.3
0xae3a4  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae3a9  starg.s  2
0xae3ab  ldarg.2
0xae3ac  dup
0xae3ad  stloc.1
0xae3ae  brfalse  loc_AE765
0xae3b3  volatile.
0xae3b5  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001c7b-1
0xae3ba  brtrue   loc_AE4EF
0xae3bf  ldc.i4.s 0x17
0xae3c1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xae3c6  dup
0xae3c7  ldstr    aAccessrequests// "accessRequestSettings"
0xae3cc  ldc.i4.0
0xae3cd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae3d2  dup
0xae3d3  ldstr    aAnonymouslinke// "anonymousLinkExpirationRestrictionDays"
0xae3d8  ldc.i4.1
0xae3d9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae3de  dup
0xae3df  ldstr    aBlockpeoplepic_0// "blockPeoplePickerAndSharing"
0xae3e4  ldc.i4.2
0xae3e5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae3ea  dup
0xae3eb  ldstr    aCanaddexternal// "canAddExternalPrincipal"
0xae3f0  ldc.i4.3
0xae3f1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae3f6  dup
0xae3f7  ldstr    aCanaddinternal// "canAddInternalPrincipal"
0xae3fc  ldc.i4.4
0xae3fd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae402  dup
0xae403  ldstr    aCanrequestacce// "canRequestAccessForGrantAccess"
0xae408  ldc.i4.5
0xae409  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae40e  dup
0xae40f  ldstr    aCansendemail_0// "canSendEmail"
0xae414  ldc.i4.6
0xae415  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae41a  dup
0xae41b  ldstr    aCanusesimplifi// "canUseSimplifiedRoles"
0xae420  ldc.i4.7
0xae421  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae426  dup
0xae427  ldstr    aCurrentrole// "currentRole"
0xae42c  ldc.i4.8
0xae42d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae432  dup
0xae433  ldstr    aDefaultlinkkin// "defaultLinkKind"
0xae438  ldc.i4.s 9
0xae43a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae43f  dup
0xae440  ldstr    aDefaultshareli_1// "defaultShareLinkPermission"
0xae445  ldc.i4.s 0xA
0xae447  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae44c  dup
0xae44d  ldstr    aDirecturl// "directUrl"
0xae452  ldc.i4.s 0xB
0xae454  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae459  dup
0xae45a  ldstr    aDomainrestrict_3// "domainRestrictionSettings"
0xae45f  ldc.i4.s 0xC
0xae461  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae466  dup
0xae467  ldstr    aHasuniquepermi// "hasUniquePermissions"
0xae46c  ldc.i4.s 0xD
0xae46e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae473  dup
0xae474  ldstr    aMicroservicesh// "microserviceShareUiUrl"
0xae479  ldc.i4.s 0xE
0xae47b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae480  dup
0xae481  ldstr    aPermissionsinf// "permissionsInformation"
0xae486  ldc.i4.s 0xF
0xae488  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae48d  dup
0xae48e  ldstr    aPickersettings// "pickerSettings"
0xae493  ldc.i4.s 0x10
0xae495  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae49a  dup
0xae49b  ldstr    aSharedobjectty// "sharedObjectType"
0xae4a0  ldc.i4.s 0x11
0xae4a2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae4a7  dup
0xae4a8  ldstr    aShareuiurl// "shareUiUrl"
0xae4ad  ldc.i4.s 0x12
0xae4af  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae4b4  dup
0xae4b5  ldstr    aSharingabiliti// "sharingAbilities"
0xae4ba  ldc.i4.s 0x13
0xae4bc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae4c1  dup
0xae4c2  ldstr    aSharingstatus// "sharingStatus"
0xae4c7  ldc.i4.s 0x14
0xae4c9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae4ce  dup
0xae4cf  ldstr    aShowexternalsh_0// "showExternalSharingWarning"
0xae4d4  ldc.i4.s 0x15
0xae4d6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae4db  dup
0xae4dc  ldstr    aWeburl_0// "webUrl"
0xae4e1  ldc.i4.s 0x16
0xae4e3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xae4e8  volatile.
0xae4ea  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001c7b-1
0xae4ef  volatile.
0xae4f1  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001c7b-1
0xae4f6  ldloc.1
0xae4f7  ldloca.s 2
0xae4f9  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xae4fe  brfalse  loc_AE765
0xae503  ldloc.2
0xae504  switch   loc_AE56A, loc_AE57D, loc_AE595, loc_AE5AD, loc_AE5C5, loc_AE5DD, loc_AE5F5, loc_AE60D, loc_AE625, loc_AE63D, loc_AE655, loc_AE66D, loc_AE680, loc_AE693, loc_AE6AB, loc_AE6BE, loc_AE6D1, loc_AE6E4, loc_AE6FC, loc_AE70F, loc_AE722, loc_AE73A, loc_AE752
0xae565  br       loc_AE765
0xae56a  ldarg.0
0xae56b  ldstr    aAccessrequests// "accessRequestSettings"
0xae570  ldarg.3
0xae571  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae576  ldloc.0
0xae577  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.AccessRequestSettings [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_AccessRequestSettings()
0xae57c  ret
0xae57d  ldarg.0
0xae57e  ldstr    aAnonymouslinke// "anonymousLinkExpirationRestrictionDays"
0xae583  ldarg.3
0xae584  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae589  ldloc.0
0xae58a  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_AnonymousLinkExpirationRestrictionDays()
0xae58f  box      [mscorlib]System.Int32
0xae594  ret
0xae595  ldarg.0
0xae596  ldstr    aBlockpeoplepic_0// "blockPeoplePickerAndSharing"
0xae59b  ldarg.3
0xae59c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae5a1  ldloc.0
0xae5a2  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_BlockPeoplePickerAndSharing()
0xae5a7  box      [mscorlib]System.Boolean
0xae5ac  ret
0xae5ad  ldarg.0
0xae5ae  ldstr    aCanaddexternal// "canAddExternalPrincipal"
0xae5b3  ldarg.3
0xae5b4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae5b9  ldloc.0
0xae5ba  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_CanAddExternalPrincipal()
0xae5bf  box      [mscorlib]System.Boolean
0xae5c4  ret
0xae5c5  ldarg.0
0xae5c6  ldstr    aCanaddinternal// "canAddInternalPrincipal"
0xae5cb  ldarg.3
0xae5cc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae5d1  ldloc.0
0xae5d2  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_CanAddInternalPrincipal()
0xae5d7  box      [mscorlib]System.Boolean
0xae5dc  ret
0xae5dd  ldarg.0
0xae5de  ldstr    aCanrequestacce// "canRequestAccessForGrantAccess"
0xae5e3  ldarg.3
0xae5e4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae5e9  ldloc.0
0xae5ea  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_CanRequestAccessForGrantAccess()
0xae5ef  box      [mscorlib]System.Boolean
0xae5f4  ret
0xae5f5  ldarg.0
0xae5f6  ldstr    aCansendemail_0// "canSendEmail"
0xae5fb  ldarg.3
0xae5fc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae601  ldloc.0
0xae602  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_CanSendEmail()
0xae607  box      [mscorlib]System.Boolean
0xae60c  ret
0xae60d  ldarg.0
0xae60e  ldstr    aCanusesimplifi// "canUseSimplifiedRoles"
0xae613  ldarg.3
0xae614  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae619  ldloc.0
0xae61a  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_CanUseSimplifiedRoles()
0xae61f  box      [mscorlib]System.Boolean
0xae624  ret
0xae625  ldarg.0
0xae626  ldstr    aCurrentrole// "currentRole"
0xae62b  ldarg.3
0xae62c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae631  ldloc.0
0xae632  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Role [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_CurrentRole()
0xae637  box      [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Role
0xae63c  ret
0xae63d  ldarg.0
0xae63e  ldstr    aDefaultlinkkin// "defaultLinkKind"
0xae643  ldarg.3
0xae644  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae649  ldloc.0
0xae64a  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkKind [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_DefaultLinkKind()
0xae64f  box      [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkKind
0xae654  ret
0xae655  ldarg.0
0xae656  ldstr    aDefaultshareli_1// "defaultShareLinkPermission"
0xae65b  ldarg.3
0xae65c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae661  ldloc.0
0xae662  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Role [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_DefaultShareLinkPermission()
0xae667  box      [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Role
0xae66c  ret
0xae66d  ldarg.0
0xae66e  ldstr    aDirecturl// "directUrl"
0xae673  ldarg.3
0xae674  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae679  ldloc.0
0xae67a  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_DirectUrl()
0xae67f  ret
0xae680  ldarg.0
0xae681  ldstr    aDomainrestrict_3// "domainRestrictionSettings"
0xae686  ldarg.3
0xae687  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae68c  ldloc.0
0xae68d  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.DomainRestrictionSettings [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_DomainRestrictionSettings()
0xae692  ret
0xae693  ldarg.0
0xae694  ldstr    aHasuniquepermi// "hasUniquePermissions"
0xae699  ldarg.3
0xae69a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae69f  ldloc.0
0xae6a0  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_HasUniquePermissions()
0xae6a5  box      [mscorlib]System.Boolean
0xae6aa  ret
0xae6ab  ldarg.0
0xae6ac  ldstr    aMicroservicesh// "microserviceShareUiUrl"
0xae6b1  ldarg.3
0xae6b2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae6b7  ldloc.0
0xae6b8  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_MicroserviceShareUiUrl()
0xae6bd  ret
0xae6be  ldarg.0
0xae6bf  ldstr    aPermissionsinf// "permissionsInformation"
0xae6c4  ldarg.3
0xae6c5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae6ca  ldloc.0
0xae6cb  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.PermissionCollection [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_PermissionsInformation()
0xae6d0  ret
0xae6d1  ldarg.0
0xae6d2  ldstr    aPickersettings// "pickerSettings"
0xae6d7  ldarg.3
0xae6d8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae6dd  ldloc.0
0xae6de  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.PickerSettings [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_PickerSettings()
0xae6e3  ret
0xae6e4  ldarg.0
0xae6e5  ldstr    aSharedobjectty// "sharedObjectType"
0xae6ea  ldarg.3
0xae6eb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae6f0  ldloc.0
0xae6f1  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SPSharedObjectType [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_SharedObjectType()
0xae6f6  box      [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SPSharedObjectType
0xae6fb  ret
0xae6fc  ldarg.0
0xae6fd  ldstr    aShareuiurl// "shareUiUrl"
0xae702  ldarg.3
0xae703  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae708  ldloc.0
0xae709  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_ShareUiUrl()
0xae70e  ret
0xae70f  ldarg.0
0xae710  ldstr    aSharingabiliti// "sharingAbilities"
0xae715  ldarg.3
0xae716  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae71b  ldloc.0
0xae71c  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingAbilities [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_SharingAbilities()
0xae721  ret
0xae722  ldarg.0
0xae723  ldstr    aSharingstatus// "sharingStatus"
0xae728  ldarg.3
0xae729  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae72e  ldloc.0
0xae72f  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingStatus [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_SharingStatus()
0xae734  box      [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingStatus
0xae739  ret
0xae73a  ldarg.0
0xae73b  ldstr    aShowexternalsh_0// "showExternalSharingWarning"
0xae740  ldarg.3
0xae741  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xae746  ldloc.0
  ... truncated ...
```
