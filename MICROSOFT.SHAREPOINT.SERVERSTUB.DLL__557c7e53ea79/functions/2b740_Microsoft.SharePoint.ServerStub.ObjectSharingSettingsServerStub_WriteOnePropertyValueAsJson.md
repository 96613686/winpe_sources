# Microsoft.SharePoint.ServerStub.ObjectSharingSettingsServerStub::WriteOnePropertyValueAsJson

- ea: `0x2b740`
- end: `0x2c58e`
- name: `Microsoft.SharePoint.ServerStub.ObjectSharingSettingsServerStub::WriteOnePropertyValueAsJson`
- size: `3662`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x2b740`

## string_xrefs

- `0x2b778`: `AccessRequestMode`
- `0x2ba54`: `AccessRequestMode`
- `0x2b790`: `CanCurrentUserManageOrganizationReadonlyLink`
- `0x2bae8`: `CanCurrentUserManageOrganizationReadonlyLink`
- `0x2b79c`: `CanCurrentUserManageOrganizationReadWriteLink`
- `0x2bb32`: `CanCurrentUserManageOrganizationReadWriteLink`
- `0x2b7a8`: `CanCurrentUserManageReadonlyLink`
- `0x2bb7c`: `CanCurrentUserManageReadonlyLink`
- `0x2b7b4`: `CanCurrentUserManageReadWriteLink`
- `0x2bbc6`: `CanCurrentUserManageReadWriteLink`
- `0x2b7c0`: `CanCurrentUserRetrieveOrganizationReadonlyLink`
- `0x2bc10`: `CanCurrentUserRetrieveOrganizationReadonlyLink`
- `0x2b7cc`: `CanCurrentUserRetrieveOrganizationReadWriteLink`
- `0x2bc5a`: `CanCurrentUserRetrieveOrganizationReadWriteLink`
- `0x2b7d8`: `CanCurrentUserRetrieveReadonlyLink`
- `0x2bca4`: `CanCurrentUserRetrieveReadonlyLink`
- `0x2b7e4`: `CanCurrentUserRetrieveReadWriteLink`
- `0x2bcee`: `CanCurrentUserRetrieveReadWriteLink`
- `0x2b818`: `CanSendLink`
- `0x2be16`: `CanSendLink`
- `0x2b832`: `DefaultShareLinkPermission`
- `0x2beaa`: `DefaultShareLinkPermission`
- `0x2b83f`: `DefaultShareLinkType`
- `0x2bef4`: `DefaultShareLinkType`
- `0x2b866`: `HasReadRole`
- `0x2bfd2`: `HasReadRole`
- `0x2b873`: `InheritingWebLink`
- `0x2c01c`: `InheritingWebLink`
- `0x2b8f5`: `RequiredAnonymousLinkExpirationInDays`
- `0x2c307`: `RequiredAnonymousLinkExpirationInDays`
- `0x2b950`: `SupportsAclPropagation`
- `0x2c51b`: `SupportsAclPropagation`

## pseudocode

```c

```

## disassembly

```asm
0x2b740  ldc.i4.0
0x2b741  stloc.0
0x2b742  ldarg.2
0x2b743  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings
0x2b748  stloc.1
0x2b749  ldloc.1
0x2b74a  brtrue.s loc_2B757
0x2b74c  ldstr    aTarget// "target"
0x2b751  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2b756  throw
0x2b757  ldarg.3
0x2b758  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x2b75d  dup
0x2b75e  stloc.2
0x2b75f  brfalse  loc_2C580
0x2b764  volatile.
0x2b766  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000889-1
0x2b76b  brtrue   loc_2B970
0x2b770  ldc.i4.s 0x27
0x2b772  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x2b777  dup
0x2b778  ldstr    aAccessrequestm// "AccessRequestMode"
0x2b77d  ldc.i4.0
0x2b77e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b783  dup
0x2b784  ldstr    aBlockpeoplepic// "BlockPeoplePickerAndSharing"
0x2b789  ldc.i4.1
0x2b78a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b78f  dup
0x2b790  ldstr    aCancurrentuser// "CanCurrentUserManageOrganizationReadonl"...
0x2b795  ldc.i4.2
0x2b796  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b79b  dup
0x2b79c  ldstr    aCancurrentuser_0// "CanCurrentUserManageOrganizationReadWri"...
0x2b7a1  ldc.i4.3
0x2b7a2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b7a7  dup
0x2b7a8  ldstr    aCancurrentuser_1// "CanCurrentUserManageReadonlyLink"
0x2b7ad  ldc.i4.4
0x2b7ae  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b7b3  dup
0x2b7b4  ldstr    aCancurrentuser_2// "CanCurrentUserManageReadWriteLink"
0x2b7b9  ldc.i4.5
0x2b7ba  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b7bf  dup
0x2b7c0  ldstr    aCancurrentuser_3// "CanCurrentUserRetrieveOrganizationReado"...
0x2b7c5  ldc.i4.6
0x2b7c6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b7cb  dup
0x2b7cc  ldstr    aCancurrentuser_4// "CanCurrentUserRetrieveOrganizationReadW"...
0x2b7d1  ldc.i4.7
0x2b7d2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b7d7  dup
0x2b7d8  ldstr    aCancurrentuser_5// "CanCurrentUserRetrieveReadonlyLink"
0x2b7dd  ldc.i4.8
0x2b7de  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b7e3  dup
0x2b7e4  ldstr    aCancurrentuser_6// "CanCurrentUserRetrieveReadWriteLink"
0x2b7e9  ldc.i4.s 9
0x2b7eb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b7f0  dup
0x2b7f1  ldstr    aCancurrentuser_7// "CanCurrentUserShareExternally"
0x2b7f6  ldc.i4.s 0xA
0x2b7f8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b7fd  dup
0x2b7fe  ldstr    aCancurrentuser_8// "CanCurrentUserShareInternally"
0x2b803  ldc.i4.s 0xB
0x2b805  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b80a  dup
0x2b80b  ldstr    aCansendemail// "CanSendEmail"
0x2b810  ldc.i4.s 0xC
0x2b812  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b817  dup
0x2b818  ldstr    aCansendlink// "CanSendLink"
0x2b81d  ldc.i4.s 0xD
0x2b81f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b824  dup
0x2b825  ldstr    aCansharefolder// "CanShareFolder"
0x2b82a  ldc.i4.s 0xE
0x2b82c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b831  dup
0x2b832  ldstr    aDefaultshareli// "DefaultShareLinkPermission"
0x2b837  ldc.i4.s 0xF
0x2b839  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b83e  dup
0x2b83f  ldstr    aDefaultshareli_0// "DefaultShareLinkType"
0x2b844  ldc.i4.s 0x10
0x2b846  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b84b  dup
0x2b84c  ldstr    aGroupslist// "GroupsList"
0x2b851  ldc.i4.s 0x11
0x2b853  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b858  dup
0x2b859  ldstr    aHaseditrole// "HasEditRole"
0x2b85e  ldc.i4.s 0x12
0x2b860  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b865  dup
0x2b866  ldstr    aHasreadrole// "HasReadRole"
0x2b86b  ldc.i4.s 0x13
0x2b86d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b872  dup
0x2b873  ldstr    aInheritingwebl// "InheritingWebLink"
0x2b878  ldc.i4.s 0x14
0x2b87a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b87f  dup
0x2b880  ldstr    aIsguestuser// "IsGuestUser"
0x2b885  ldc.i4.s 0x15
0x2b887  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b88c  dup
0x2b88d  ldstr    aIspicturelibra// "IsPictureLibrary"
0x2b892  ldc.i4.s 0x16
0x2b894  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b899  dup
0x2b89a  ldstr    aIsusersiteadmi// "IsUserSiteAdmin"
0x2b89f  ldc.i4.s 0x17
0x2b8a1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b8a6  dup
0x2b8a7  ldstr    aItemid_0// "ItemId"
0x2b8ac  ldc.i4.s 0x18
0x2b8ae  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b8b3  dup
0x2b8b4  ldstr    aItemname// "ItemName"
0x2b8b9  ldc.i4.s 0x19
0x2b8bb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b8c0  dup
0x2b8c1  ldstr    aItemurl// "ItemUrl"
0x2b8c6  ldc.i4.s 0x1A
0x2b8c8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b8cd  dup
0x2b8ce  ldstr    aListid_0// "ListId"
0x2b8d3  ldc.i4.s 0x1B
0x2b8d5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b8da  dup
0x2b8db  ldstr    aObjectsharingi// "ObjectSharingInformation"
0x2b8e0  ldc.i4.s 0x1C
0x2b8e2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b8e7  dup
0x2b8e8  ldstr    aPermissionsonl// "PermissionsOnlyMode"
0x2b8ed  ldc.i4.s 0x1D
0x2b8ef  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b8f4  dup
0x2b8f5  ldstr    aRequiredanonym// "RequiredAnonymousLinkExpirationInDays"
0x2b8fa  ldc.i4.s 0x1E
0x2b8fc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b901  dup
0x2b902  ldstr    aRoles// "Roles"
0x2b907  ldc.i4.s 0x1F
0x2b909  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b90e  dup
0x2b90f  ldstr    aSharebyemailen// "ShareByEmailEnabled"
0x2b914  ldc.i4.s 0x20
0x2b916  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b91b  dup
0x2b91c  ldstr    aSharepointsett// "SharePointSettings"
0x2b921  ldc.i4.s 0x21
0x2b923  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b928  dup
0x2b929  ldstr    aSharingpermiss// "SharingPermissions"
0x2b92e  ldc.i4.s 0x22
0x2b930  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b935  dup
0x2b936  ldstr    aShowexternalsh// "ShowExternalSharingWarning"
0x2b93b  ldc.i4.s 0x23
0x2b93d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b942  dup
0x2b943  ldstr    aSimplifiedrole// "SimplifiedRoles"
0x2b948  ldc.i4.s 0x24
0x2b94a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b94f  dup
0x2b950  ldstr    aSupportsaclpro// "SupportsAclPropagation"
0x2b955  ldc.i4.s 0x25
0x2b957  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b95c  dup
0x2b95d  ldstr    aWeburl// "WebUrl"
0x2b962  ldc.i4.s 0x26
0x2b964  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2b969  volatile.
0x2b96b  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000889-1
0x2b970  volatile.
0x2b972  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000889-1
0x2b977  ldloc.2
0x2b978  ldloca.s 3
0x2b97a  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x2b97f  brfalse  loc_2C580
0x2b984  ldloc.3
0x2b985  switch   loc_2BA2B, loc_2BA75, loc_2BABF, loc_2BB09, loc_2BB53, loc_2BB9D, loc_2BBE7, loc_2BC31, loc_2BC7B, loc_2BCC5, loc_2BD0F, loc_2BD59, loc_2BDA3, loc_2BDED, loc_2BE37, loc_2BE81, loc_2BECB, loc_2BF15, loc_2BF5F, loc_2BFA9, loc_2BFF3, loc_2C03D, loc_2C087, loc_2C0D1, loc_2C11B, loc_2C165, loc_2C1AF, loc_2C1F9, loc_2C243, loc_2C294, loc_2C2DE, loc_2C328, loc_2C372, loc_2C3BC, loc_2C40D, loc_2C45E, loc_2C4A8, loc_2C4F2, loc_2C539
0x2ba26  br       loc_2C580
0x2ba2b  ldarg.3
0x2ba2c  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x2ba31  stloc.s  4
0x2ba33  ldloca.s 4
0x2ba35  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x2ba3a  brfalse.s loc_2BA53
0x2ba3c  ldarg.3
0x2ba3d  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x2ba42  stloc.s  5
0x2ba44  ldloca.s 5
0x2ba46  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x2ba4b  brtrue.s loc_2BA53
0x2ba4d  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x2ba52  throw
0x2ba53  ldarg.0
0x2ba54  ldstr    aAccessrequestm// "AccessRequestMode"
0x2ba59  ldarg.s  4
0x2ba5b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2ba60  ldc.i4.1
0x2ba61  stloc.0
0x2ba62  ldarg.1
0x2ba63  ldloc.1
0x2ba64  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_AccessRequestMode()
0x2ba69  ldarg.s  4
0x2ba6b  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2ba70  br       loc_2C58C
0x2ba75  ldarg.3
0x2ba76  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x2ba7b  stloc.s  6
0x2ba7d  ldloca.s 6
0x2ba7f  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x2ba84  brfalse.s loc_2BA9D
0x2ba86  ldarg.3
0x2ba87  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x2ba8c  stloc.s  7
0x2ba8e  ldloca.s 7
0x2ba90  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x2ba95  brtrue.s loc_2BA9D
0x2ba97  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x2ba9c  throw
0x2ba9d  ldarg.0
0x2ba9e  ldstr    aBlockpeoplepic// "BlockPeoplePickerAndSharing"
0x2baa3  ldarg.s  4
0x2baa5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2baaa  ldc.i4.1
0x2baab  stloc.0
0x2baac  ldarg.1
0x2baad  ldloc.1
0x2baae  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_BlockPeoplePickerAndSharing()
0x2bab3  ldarg.s  4
0x2bab5  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2baba  br       loc_2C58C
0x2babf  ldarg.3
0x2bac0  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x2bac5  stloc.s  8
0x2bac7  ldloca.s 8
0x2bac9  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x2bace  brfalse.s loc_2BAE7
0x2bad0  ldarg.3
0x2bad1  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x2bad6  stloc.s  9
0x2bad8  ldloca.s 9
0x2bada  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x2badf  brtrue.s loc_2BAE7
0x2bae1  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x2bae6  throw
0x2bae7  ldarg.0
0x2bae8  ldstr    aCancurrentuser// "CanCurrentUserManageOrganizationReadonl"...
0x2baed  ldarg.s  4
0x2baef  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2baf4  ldc.i4.1
0x2baf5  stloc.0
0x2baf6  ldarg.1
0x2baf7  ldloc.1
0x2baf8  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_CanCurrentUserManageOrganizationReadonlyLink()
0x2bafd  ldarg.s  4
0x2baff  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2bb04  br       loc_2C58C
0x2bb09  ldarg.3
0x2bb0a  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x2bb0f  stloc.s  0xA
0x2bb11  ldloca.s 0xA
0x2bb13  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x2bb18  brfalse.s loc_2BB31
0x2bb1a  ldarg.3
0x2bb1b  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x2bb20  stloc.s  0xB
0x2bb22  ldloca.s 0xB
0x2bb24  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x2bb29  brtrue.s loc_2BB31
0x2bb2b  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x2bb30  throw
0x2bb31  ldarg.0
0x2bb32  ldstr    aCancurrentuser_0// "CanCurrentUserManageOrganizationReadWri"...
0x2bb37  ldarg.s  4
0x2bb39  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2bb3e  ldc.i4.1
0x2bb3f  stloc.0
0x2bb40  ldarg.1
0x2bb41  ldloc.1
0x2bb42  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_CanCurrentUserManageOrganizationReadWriteLink()
0x2bb47  ldarg.s  4
0x2bb49  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2bb4e  br       loc_2C58C
0x2bb53  ldarg.3
0x2bb54  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x2bb59  stloc.s  0xC
0x2bb5b  ldloca.s 0xC
0x2bb5d  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x2bb62  brfalse.s loc_2BB7B
0x2bb64  ldarg.3
0x2bb65  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x2bb6a  stloc.s  0xD
  ... truncated ...
```
