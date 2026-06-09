# Microsoft.SharePoint.ServerStub.ObjectSharingSettingsServerStub::.cctor

- ea: `0x2ce70`
- end: `0x2cfee`
- name: `Microsoft.SharePoint.ServerStub.ObjectSharingSettingsServerStub::.cctor`
- size: `382`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## string_xrefs

- `0x2ce7a`: `AccessRequestMode`
- `0x2ce8a`: `CanCurrentUserManageOrganizationReadonlyLink`
- `0x2ce92`: `CanCurrentUserManageOrganizationReadWriteLink`
- `0x2ce9a`: `CanCurrentUserManageReadonlyLink`
- `0x2cea2`: `CanCurrentUserManageReadWriteLink`
- `0x2ceaa`: `CanCurrentUserRetrieveOrganizationReadonlyLink`
- `0x2ceb2`: `CanCurrentUserRetrieveOrganizationReadWriteLink`
- `0x2ceba`: `CanCurrentUserRetrieveReadonlyLink`
- `0x2cec3`: `CanCurrentUserRetrieveReadWriteLink`
- `0x2cee7`: `CanSendLink`
- `0x2cef9`: `DefaultShareLinkPermission`
- `0x2cf02`: `DefaultShareLinkType`
- `0x2cf1d`: `HasReadRole`
- `0x2cf26`: `InheritingWebLink`
- `0x2cf77`: `RequiredAnonymousLinkExpirationInDays`
- `0x2cfa4`: `SupportsAclPropagation`

## pseudocode

```c

```

## disassembly

```asm
0x2ce70  ldc.i4.s 0x24
0x2ce72  newarr   [mscorlib]System.String
0x2ce77  stloc.0
0x2ce78  ldloc.0
0x2ce79  ldc.i4.0
0x2ce7a  ldstr    aAccessrequestm// "AccessRequestMode"
0x2ce7f  stelem.ref
0x2ce80  ldloc.0
0x2ce81  ldc.i4.1
0x2ce82  ldstr    aBlockpeoplepic// "BlockPeoplePickerAndSharing"
0x2ce87  stelem.ref
0x2ce88  ldloc.0
0x2ce89  ldc.i4.2
0x2ce8a  ldstr    aCancurrentuser// "CanCurrentUserManageOrganizationReadonl"...
0x2ce8f  stelem.ref
0x2ce90  ldloc.0
0x2ce91  ldc.i4.3
0x2ce92  ldstr    aCancurrentuser_0// "CanCurrentUserManageOrganizationReadWri"...
0x2ce97  stelem.ref
0x2ce98  ldloc.0
0x2ce99  ldc.i4.4
0x2ce9a  ldstr    aCancurrentuser_1// "CanCurrentUserManageReadonlyLink"
0x2ce9f  stelem.ref
0x2cea0  ldloc.0
0x2cea1  ldc.i4.5
0x2cea2  ldstr    aCancurrentuser_2// "CanCurrentUserManageReadWriteLink"
0x2cea7  stelem.ref
0x2cea8  ldloc.0
0x2cea9  ldc.i4.6
0x2ceaa  ldstr    aCancurrentuser_3// "CanCurrentUserRetrieveOrganizationReado"...
0x2ceaf  stelem.ref
0x2ceb0  ldloc.0
0x2ceb1  ldc.i4.7
0x2ceb2  ldstr    aCancurrentuser_4// "CanCurrentUserRetrieveOrganizationReadW"...
0x2ceb7  stelem.ref
0x2ceb8  ldloc.0
0x2ceb9  ldc.i4.8
0x2ceba  ldstr    aCancurrentuser_5// "CanCurrentUserRetrieveReadonlyLink"
0x2cebf  stelem.ref
0x2cec0  ldloc.0
0x2cec1  ldc.i4.s 9
0x2cec3  ldstr    aCancurrentuser_6// "CanCurrentUserRetrieveReadWriteLink"
0x2cec8  stelem.ref
0x2cec9  ldloc.0
0x2ceca  ldc.i4.s 0xA
0x2cecc  ldstr    aCancurrentuser_7// "CanCurrentUserShareExternally"
0x2ced1  stelem.ref
0x2ced2  ldloc.0
0x2ced3  ldc.i4.s 0xB
0x2ced5  ldstr    aCancurrentuser_8// "CanCurrentUserShareInternally"
0x2ceda  stelem.ref
0x2cedb  ldloc.0
0x2cedc  ldc.i4.s 0xC
0x2cede  ldstr    aCansendemail// "CanSendEmail"
0x2cee3  stelem.ref
0x2cee4  ldloc.0
0x2cee5  ldc.i4.s 0xD
0x2cee7  ldstr    aCansendlink// "CanSendLink"
0x2ceec  stelem.ref
0x2ceed  ldloc.0
0x2ceee  ldc.i4.s 0xE
0x2cef0  ldstr    aCansharefolder// "CanShareFolder"
0x2cef5  stelem.ref
0x2cef6  ldloc.0
0x2cef7  ldc.i4.s 0xF
0x2cef9  ldstr    aDefaultshareli// "DefaultShareLinkPermission"
0x2cefe  stelem.ref
0x2ceff  ldloc.0
0x2cf00  ldc.i4.s 0x10
0x2cf02  ldstr    aDefaultshareli_0// "DefaultShareLinkType"
0x2cf07  stelem.ref
0x2cf08  ldloc.0
0x2cf09  ldc.i4.s 0x11
0x2cf0b  ldstr    aGroupslist// "GroupsList"
0x2cf10  stelem.ref
0x2cf11  ldloc.0
0x2cf12  ldc.i4.s 0x12
0x2cf14  ldstr    aHaseditrole// "HasEditRole"
0x2cf19  stelem.ref
0x2cf1a  ldloc.0
0x2cf1b  ldc.i4.s 0x13
0x2cf1d  ldstr    aHasreadrole// "HasReadRole"
0x2cf22  stelem.ref
0x2cf23  ldloc.0
0x2cf24  ldc.i4.s 0x14
0x2cf26  ldstr    aInheritingwebl// "InheritingWebLink"
0x2cf2b  stelem.ref
0x2cf2c  ldloc.0
0x2cf2d  ldc.i4.s 0x15
0x2cf2f  ldstr    aIsguestuser// "IsGuestUser"
0x2cf34  stelem.ref
0x2cf35  ldloc.0
0x2cf36  ldc.i4.s 0x16
0x2cf38  ldstr    aIspicturelibra// "IsPictureLibrary"
0x2cf3d  stelem.ref
0x2cf3e  ldloc.0
0x2cf3f  ldc.i4.s 0x17
0x2cf41  ldstr    aIsusersiteadmi// "IsUserSiteAdmin"
0x2cf46  stelem.ref
0x2cf47  ldloc.0
0x2cf48  ldc.i4.s 0x18
0x2cf4a  ldstr    aItemid_0// "ItemId"
0x2cf4f  stelem.ref
0x2cf50  ldloc.0
0x2cf51  ldc.i4.s 0x19
0x2cf53  ldstr    aItemname// "ItemName"
0x2cf58  stelem.ref
0x2cf59  ldloc.0
0x2cf5a  ldc.i4.s 0x1A
0x2cf5c  ldstr    aItemurl// "ItemUrl"
0x2cf61  stelem.ref
0x2cf62  ldloc.0
0x2cf63  ldc.i4.s 0x1B
0x2cf65  ldstr    aListid_0// "ListId"
0x2cf6a  stelem.ref
0x2cf6b  ldloc.0
0x2cf6c  ldc.i4.s 0x1C
0x2cf6e  ldstr    aPermissionsonl// "PermissionsOnlyMode"
0x2cf73  stelem.ref
0x2cf74  ldloc.0
0x2cf75  ldc.i4.s 0x1D
0x2cf77  ldstr    aRequiredanonym// "RequiredAnonymousLinkExpirationInDays"
0x2cf7c  stelem.ref
0x2cf7d  ldloc.0
0x2cf7e  ldc.i4.s 0x1E
0x2cf80  ldstr    aRoles// "Roles"
0x2cf85  stelem.ref
0x2cf86  ldloc.0
0x2cf87  ldc.i4.s 0x1F
0x2cf89  ldstr    aSharebyemailen// "ShareByEmailEnabled"
0x2cf8e  stelem.ref
0x2cf8f  ldloc.0
0x2cf90  ldc.i4.s 0x20
0x2cf92  ldstr    aShowexternalsh// "ShowExternalSharingWarning"
0x2cf97  stelem.ref
0x2cf98  ldloc.0
0x2cf99  ldc.i4.s 0x21
0x2cf9b  ldstr    aSimplifiedrole// "SimplifiedRoles"
0x2cfa0  stelem.ref
0x2cfa1  ldloc.0
0x2cfa2  ldc.i4.s 0x22
0x2cfa4  ldstr    aSupportsaclpro// "SupportsAclPropagation"
0x2cfa9  stelem.ref
0x2cfaa  ldloc.0
0x2cfab  ldc.i4.s 0x23
0x2cfad  ldstr    aWeburl// "WebUrl"
0x2cfb2  stelem.ref
0x2cfb3  ldloc.0
0x2cfb4  stsfld   string[] Microsoft.SharePoint.ServerStub.ObjectSharingSettingsServerStub::s_valueProperties
0x2cfb9  ldc.i4.3
0x2cfba  newarr   [mscorlib]System.String
0x2cfbf  stloc.1
0x2cfc0  ldloc.1
0x2cfc1  ldc.i4.0
0x2cfc2  ldstr    aObjectsharingi// "ObjectSharingInformation"
0x2cfc7  stelem.ref
0x2cfc8  ldloc.1
0x2cfc9  ldc.i4.1
0x2cfca  ldstr    aSharepointsett// "SharePointSettings"
0x2cfcf  stelem.ref
0x2cfd0  ldloc.1
0x2cfd1  ldc.i4.2
0x2cfd2  ldstr    aSharingpermiss// "SharingPermissions"
0x2cfd7  stelem.ref
0x2cfd8  ldloc.1
0x2cfd9  stsfld   string[] Microsoft.SharePoint.ServerStub.ObjectSharingSettingsServerStub::s_refProperties
0x2cfde  ldstr    a9ca08afe29fa4f// "{9ca08afe-29fa-4faf-86af-5bcb06e41969}"
0x2cfe3  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x2cfe8  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ServerStub.ObjectSharingSettingsServerStub::s_targetTypeId
0x2cfed  ret
```
