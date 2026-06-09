# Microsoft.SharePoint.ServerStub.ObjectSharingSettingsServerStub::GetProperty

- ea: `0x2b080`
- end: `0x2b705`
- name: `Microsoft.SharePoint.ServerStub.ObjectSharingSettingsServerStub::GetProperty`
- size: `1669`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x2b080`

## string_xrefs

- `0x2b0d7`: `AccessRequestMode`
- `0x2b38b`: `AccessRequestMode`
- `0x2b0ef`: `CanCurrentUserManageOrganizationReadonlyLink`
- `0x2b3bb`: `CanCurrentUserManageOrganizationReadonlyLink`
- `0x2b0fb`: `CanCurrentUserManageOrganizationReadWriteLink`
- `0x2b3d3`: `CanCurrentUserManageOrganizationReadWriteLink`
- `0x2b107`: `CanCurrentUserManageReadonlyLink`
- `0x2b3eb`: `CanCurrentUserManageReadonlyLink`
- `0x2b113`: `CanCurrentUserManageReadWriteLink`
- `0x2b403`: `CanCurrentUserManageReadWriteLink`
- `0x2b11f`: `CanCurrentUserRetrieveOrganizationReadonlyLink`
- `0x2b41b`: `CanCurrentUserRetrieveOrganizationReadonlyLink`
- `0x2b12b`: `CanCurrentUserRetrieveOrganizationReadWriteLink`
- `0x2b433`: `CanCurrentUserRetrieveOrganizationReadWriteLink`
- `0x2b137`: `CanCurrentUserRetrieveReadonlyLink`
- `0x2b44b`: `CanCurrentUserRetrieveReadonlyLink`
- `0x2b143`: `CanCurrentUserRetrieveReadWriteLink`
- `0x2b463`: `CanCurrentUserRetrieveReadWriteLink`
- `0x2b177`: `CanSendLink`
- `0x2b4c3`: `CanSendLink`
- `0x2b191`: `DefaultShareLinkPermission`
- `0x2b4f3`: `DefaultShareLinkPermission`
- `0x2b19e`: `DefaultShareLinkType`
- `0x2b50b`: `DefaultShareLinkType`
- `0x2b1c5`: `HasReadRole`
- `0x2b54e`: `HasReadRole`
- `0x2b1d2`: `InheritingWebLink`
- `0x2b566`: `InheritingWebLink`
- `0x2b254`: `RequiredAnonymousLinkExpirationInDays`
- `0x2b63d`: `RequiredAnonymousLinkExpirationInDays`
- `0x2b2af`: `SupportsAclPropagation`
- `0x2b6d1`: `SupportsAclPropagation`

## pseudocode

```c

```

## disassembly

```asm
0x2b080  ldarg.2
0x2b081  brtrue.s loc_2B08E
0x2b083  ldstr    aPropname// "propName"
0x2b088  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2b08d  throw
0x2b08e  ldarg.3
0x2b08f  brtrue.s loc_2B09C
0x2b091  ldstr    aProxycontext// "proxyContext"
0x2b096  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2b09b  throw
0x2b09c  ldarg.1
0x2b09d  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings
0x2b0a2  stloc.0
0x2b0a3  ldloc.0
0x2b0a4  brtrue.s loc_2B0B1
0x2b0a6  ldstr    aTarget// "target"
0x2b0ab  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2b0b0  throw
0x2b0b1  ldarg.0
0x2b0b2  ldarg.2
0x2b0b3  ldarg.3
0x2b0b4  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2b0b9  starg.s  2
0x2b0bb  ldarg.2
0x2b0bc  dup
0x2b0bd  stloc.1
0x2b0be  brfalse  loc_2B6FB
0x2b0c3  volatile.
0x2b0c5  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000887-1
0x2b0ca  brtrue   loc_2B2CF
0x2b0cf  ldc.i4.s 0x27
0x2b0d1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x2b0d6  dup
0x2b0d7  ldstr    aAccessrequestm// "AccessRequestMode"
0x2b0dc  ldc.i4.0
0x2b0dd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b0e2  dup
0x2b0e3  ldstr    aBlockpeoplepic// "BlockPeoplePickerAndSharing"
0x2b0e8  ldc.i4.1
0x2b0e9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b0ee  dup
0x2b0ef  ldstr    aCancurrentuser// "CanCurrentUserManageOrganizationReadonl"...
0x2b0f4  ldc.i4.2
0x2b0f5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b0fa  dup
0x2b0fb  ldstr    aCancurrentuser_0// "CanCurrentUserManageOrganizationReadWri"...
0x2b100  ldc.i4.3
0x2b101  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b106  dup
0x2b107  ldstr    aCancurrentuser_1// "CanCurrentUserManageReadonlyLink"
0x2b10c  ldc.i4.4
0x2b10d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b112  dup
0x2b113  ldstr    aCancurrentuser_2// "CanCurrentUserManageReadWriteLink"
0x2b118  ldc.i4.5
0x2b119  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b11e  dup
0x2b11f  ldstr    aCancurrentuser_3// "CanCurrentUserRetrieveOrganizationReado"...
0x2b124  ldc.i4.6
0x2b125  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b12a  dup
0x2b12b  ldstr    aCancurrentuser_4// "CanCurrentUserRetrieveOrganizationReadW"...
0x2b130  ldc.i4.7
0x2b131  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b136  dup
0x2b137  ldstr    aCancurrentuser_5// "CanCurrentUserRetrieveReadonlyLink"
0x2b13c  ldc.i4.8
0x2b13d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b142  dup
0x2b143  ldstr    aCancurrentuser_6// "CanCurrentUserRetrieveReadWriteLink"
0x2b148  ldc.i4.s 9
0x2b14a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b14f  dup
0x2b150  ldstr    aCancurrentuser_7// "CanCurrentUserShareExternally"
0x2b155  ldc.i4.s 0xA
0x2b157  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b15c  dup
0x2b15d  ldstr    aCancurrentuser_8// "CanCurrentUserShareInternally"
0x2b162  ldc.i4.s 0xB
0x2b164  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b169  dup
0x2b16a  ldstr    aCansendemail// "CanSendEmail"
0x2b16f  ldc.i4.s 0xC
0x2b171  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b176  dup
0x2b177  ldstr    aCansendlink// "CanSendLink"
0x2b17c  ldc.i4.s 0xD
0x2b17e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b183  dup
0x2b184  ldstr    aCansharefolder// "CanShareFolder"
0x2b189  ldc.i4.s 0xE
0x2b18b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b190  dup
0x2b191  ldstr    aDefaultshareli// "DefaultShareLinkPermission"
0x2b196  ldc.i4.s 0xF
0x2b198  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b19d  dup
0x2b19e  ldstr    aDefaultshareli_0// "DefaultShareLinkType"
0x2b1a3  ldc.i4.s 0x10
0x2b1a5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b1aa  dup
0x2b1ab  ldstr    aGroupslist// "GroupsList"
0x2b1b0  ldc.i4.s 0x11
0x2b1b2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b1b7  dup
0x2b1b8  ldstr    aHaseditrole// "HasEditRole"
0x2b1bd  ldc.i4.s 0x12
0x2b1bf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b1c4  dup
0x2b1c5  ldstr    aHasreadrole// "HasReadRole"
0x2b1ca  ldc.i4.s 0x13
0x2b1cc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b1d1  dup
0x2b1d2  ldstr    aInheritingwebl// "InheritingWebLink"
0x2b1d7  ldc.i4.s 0x14
0x2b1d9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b1de  dup
0x2b1df  ldstr    aIsguestuser// "IsGuestUser"
0x2b1e4  ldc.i4.s 0x15
0x2b1e6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b1eb  dup
0x2b1ec  ldstr    aIspicturelibra// "IsPictureLibrary"
0x2b1f1  ldc.i4.s 0x16
0x2b1f3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b1f8  dup
0x2b1f9  ldstr    aIsusersiteadmi// "IsUserSiteAdmin"
0x2b1fe  ldc.i4.s 0x17
0x2b200  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b205  dup
0x2b206  ldstr    aItemid_0// "ItemId"
0x2b20b  ldc.i4.s 0x18
0x2b20d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b212  dup
0x2b213  ldstr    aItemname// "ItemName"
0x2b218  ldc.i4.s 0x19
0x2b21a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b21f  dup
0x2b220  ldstr    aItemurl// "ItemUrl"
0x2b225  ldc.i4.s 0x1A
0x2b227  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b22c  dup
0x2b22d  ldstr    aListid_0// "ListId"
0x2b232  ldc.i4.s 0x1B
0x2b234  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b239  dup
0x2b23a  ldstr    aObjectsharingi// "ObjectSharingInformation"
0x2b23f  ldc.i4.s 0x1C
0x2b241  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b246  dup
0x2b247  ldstr    aPermissionsonl// "PermissionsOnlyMode"
0x2b24c  ldc.i4.s 0x1D
0x2b24e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b253  dup
0x2b254  ldstr    aRequiredanonym// "RequiredAnonymousLinkExpirationInDays"
0x2b259  ldc.i4.s 0x1E
0x2b25b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b260  dup
0x2b261  ldstr    aRoles// "Roles"
0x2b266  ldc.i4.s 0x1F
0x2b268  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b26d  dup
0x2b26e  ldstr    aSharebyemailen// "ShareByEmailEnabled"
0x2b273  ldc.i4.s 0x20
0x2b275  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b27a  dup
0x2b27b  ldstr    aSharepointsett// "SharePointSettings"
0x2b280  ldc.i4.s 0x21
0x2b282  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b287  dup
0x2b288  ldstr    aSharingpermiss// "SharingPermissions"
0x2b28d  ldc.i4.s 0x22
0x2b28f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b294  dup
0x2b295  ldstr    aShowexternalsh// "ShowExternalSharingWarning"
0x2b29a  ldc.i4.s 0x23
0x2b29c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b2a1  dup
0x2b2a2  ldstr    aSimplifiedrole// "SimplifiedRoles"
0x2b2a7  ldc.i4.s 0x24
0x2b2a9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b2ae  dup
0x2b2af  ldstr    aSupportsaclpro// "SupportsAclPropagation"
0x2b2b4  ldc.i4.s 0x25
0x2b2b6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b2bb  dup
0x2b2bc  ldstr    aWeburl// "WebUrl"
0x2b2c1  ldc.i4.s 0x26
0x2b2c3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b2c8  volatile.
0x2b2ca  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000887-1
0x2b2cf  volatile.
0x2b2d1  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000887-1
0x2b2d6  ldloc.1
0x2b2d7  ldloca.s 2
0x2b2d9  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x2b2de  brfalse  loc_2B6FB
0x2b2e3  ldloc.2
0x2b2e4  switch   loc_2B38A, loc_2B3A2, loc_2B3BA, loc_2B3D2, loc_2B3EA, loc_2B402, loc_2B41A, loc_2B432, loc_2B44A, loc_2B462, loc_2B47A, loc_2B492, loc_2B4AA, loc_2B4C2, loc_2B4DA, loc_2B4F2, loc_2B50A, loc_2B522, loc_2B535, loc_2B54D, loc_2B565, loc_2B578, loc_2B590, loc_2B5A8, loc_2B5C0, loc_2B5D3, loc_2B5E6, loc_2B5F9, loc_2B611, loc_2B624, loc_2B63C, loc_2B654, loc_2B667, loc_2B67F, loc_2B692, loc_2B6A5, loc_2B6BD, loc_2B6D0, loc_2B6E8
0x2b385  br       loc_2B6FB
0x2b38a  ldarg.0
0x2b38b  ldstr    aAccessrequestm// "AccessRequestMode"
0x2b390  ldarg.3
0x2b391  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2b396  ldloc.0
0x2b397  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_AccessRequestMode()
0x2b39c  box      [mscorlib]System.Boolean
0x2b3a1  ret
0x2b3a2  ldarg.0
0x2b3a3  ldstr    aBlockpeoplepic// "BlockPeoplePickerAndSharing"
0x2b3a8  ldarg.3
0x2b3a9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2b3ae  ldloc.0
0x2b3af  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_BlockPeoplePickerAndSharing()
0x2b3b4  box      [mscorlib]System.Boolean
0x2b3b9  ret
0x2b3ba  ldarg.0
0x2b3bb  ldstr    aCancurrentuser// "CanCurrentUserManageOrganizationReadonl"...
0x2b3c0  ldarg.3
0x2b3c1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2b3c6  ldloc.0
0x2b3c7  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_CanCurrentUserManageOrganizationReadonlyLink()
0x2b3cc  box      [mscorlib]System.Boolean
0x2b3d1  ret
0x2b3d2  ldarg.0
0x2b3d3  ldstr    aCancurrentuser_0// "CanCurrentUserManageOrganizationReadWri"...
0x2b3d8  ldarg.3
0x2b3d9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2b3de  ldloc.0
0x2b3df  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_CanCurrentUserManageOrganizationReadWriteLink()
0x2b3e4  box      [mscorlib]System.Boolean
0x2b3e9  ret
0x2b3ea  ldarg.0
0x2b3eb  ldstr    aCancurrentuser_1// "CanCurrentUserManageReadonlyLink"
0x2b3f0  ldarg.3
0x2b3f1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2b3f6  ldloc.0
0x2b3f7  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_CanCurrentUserManageReadonlyLink()
0x2b3fc  box      [mscorlib]System.Boolean
0x2b401  ret
0x2b402  ldarg.0
0x2b403  ldstr    aCancurrentuser_2// "CanCurrentUserManageReadWriteLink"
0x2b408  ldarg.3
0x2b409  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2b40e  ldloc.0
0x2b40f  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_CanCurrentUserManageReadWriteLink()
0x2b414  box      [mscorlib]System.Boolean
0x2b419  ret
0x2b41a  ldarg.0
0x2b41b  ldstr    aCancurrentuser_3// "CanCurrentUserRetrieveOrganizationReado"...
0x2b420  ldarg.3
0x2b421  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2b426  ldloc.0
0x2b427  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_CanCurrentUserRetrieveOrganizationReadonlyLink()
0x2b42c  box      [mscorlib]System.Boolean
0x2b431  ret
0x2b432  ldarg.0
0x2b433  ldstr    aCancurrentuser_4// "CanCurrentUserRetrieveOrganizationReadW"...
0x2b438  ldarg.3
0x2b439  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2b43e  ldloc.0
0x2b43f  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_CanCurrentUserRetrieveOrganizationReadWriteLink()
0x2b444  box      [mscorlib]System.Boolean
0x2b449  ret
0x2b44a  ldarg.0
0x2b44b  ldstr    aCancurrentuser_5// "CanCurrentUserRetrieveReadonlyLink"
0x2b450  ldarg.3
0x2b451  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2b456  ldloc.0
0x2b457  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_CanCurrentUserRetrieveReadonlyLink()
0x2b45c  box      [mscorlib]System.Boolean
0x2b461  ret
0x2b462  ldarg.0
0x2b463  ldstr    aCancurrentuser_6// "CanCurrentUserRetrieveReadWriteLink"
0x2b468  ldarg.3
0x2b469  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2b46e  ldloc.0
0x2b46f  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_CanCurrentUserRetrieveReadWriteLink()
0x2b474  box      [mscorlib]System.Boolean
0x2b479  ret
0x2b47a  ldarg.0
0x2b47b  ldstr    aCancurrentuser_7// "CanCurrentUserShareExternally"
0x2b480  ldarg.3
0x2b481  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2b486  ldloc.0
0x2b487  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_CanCurrentUserShareExternally()
0x2b48c  box      [mscorlib]System.Boolean
0x2b491  ret
0x2b492  ldarg.0
0x2b493  ldstr    aCancurrentuser_8// "CanCurrentUserShareInternally"
0x2b498  ldarg.3
0x2b499  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2b49e  ldloc.0
0x2b49f  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_CanCurrentUserShareInternally()
0x2b4a4  box      [mscorlib]System.Boolean
0x2b4a9  ret
0x2b4aa  ldarg.0
0x2b4ab  ldstr    aCansendemail// "CanSendEmail"
0x2b4b0  ldarg.3
0x2b4b1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2b4b6  ldloc.0
  ... truncated ...
```
