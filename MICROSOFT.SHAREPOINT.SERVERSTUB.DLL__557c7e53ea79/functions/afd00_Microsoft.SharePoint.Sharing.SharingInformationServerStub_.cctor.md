# Microsoft.SharePoint.Sharing.SharingInformationServerStub::.cctor

- ea: `0xafd00`
- end: `0xafe15`
- name: `Microsoft.SharePoint.Sharing.SharingInformationServerStub::.cctor`
- size: `277`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0xafd0a`: `accessRequestSettings`
- `0xafde9`: `accessRequestSettings`
- `0xafd12`: `anonymousLinkExpirationRestrictionDays`
- `0xafd32`: `canRequestAccessForGrantAccess`
- `0xafd53`: `defaultLinkKind`
- `0xafd5c`: `defaultShareLinkPermission`
- `0xafd80`: `microserviceShareUiUrl`

## pseudocode

```c

```

## disassembly

```asm
0xafd00  ldc.i4.s 0x16
0xafd02  newarr   [mscorlib]System.String
0xafd07  stloc.0
0xafd08  ldloc.0
0xafd09  ldc.i4.0
0xafd0a  ldstr    aAccessrequests// "accessRequestSettings"
0xafd0f  stelem.ref
0xafd10  ldloc.0
0xafd11  ldc.i4.1
0xafd12  ldstr    aAnonymouslinke// "anonymousLinkExpirationRestrictionDays"
0xafd17  stelem.ref
0xafd18  ldloc.0
0xafd19  ldc.i4.2
0xafd1a  ldstr    aBlockpeoplepic_0// "blockPeoplePickerAndSharing"
0xafd1f  stelem.ref
0xafd20  ldloc.0
0xafd21  ldc.i4.3
0xafd22  ldstr    aCanaddexternal// "canAddExternalPrincipal"
0xafd27  stelem.ref
0xafd28  ldloc.0
0xafd29  ldc.i4.4
0xafd2a  ldstr    aCanaddinternal// "canAddInternalPrincipal"
0xafd2f  stelem.ref
0xafd30  ldloc.0
0xafd31  ldc.i4.5
0xafd32  ldstr    aCanrequestacce// "canRequestAccessForGrantAccess"
0xafd37  stelem.ref
0xafd38  ldloc.0
0xafd39  ldc.i4.6
0xafd3a  ldstr    aCansendemail_0// "canSendEmail"
0xafd3f  stelem.ref
0xafd40  ldloc.0
0xafd41  ldc.i4.7
0xafd42  ldstr    aCanusesimplifi// "canUseSimplifiedRoles"
0xafd47  stelem.ref
0xafd48  ldloc.0
0xafd49  ldc.i4.8
0xafd4a  ldstr    aCurrentrole// "currentRole"
0xafd4f  stelem.ref
0xafd50  ldloc.0
0xafd51  ldc.i4.s 9
0xafd53  ldstr    aDefaultlinkkin// "defaultLinkKind"
0xafd58  stelem.ref
0xafd59  ldloc.0
0xafd5a  ldc.i4.s 0xA
0xafd5c  ldstr    aDefaultshareli_1// "defaultShareLinkPermission"
0xafd61  stelem.ref
0xafd62  ldloc.0
0xafd63  ldc.i4.s 0xB
0xafd65  ldstr    aDirecturl// "directUrl"
0xafd6a  stelem.ref
0xafd6b  ldloc.0
0xafd6c  ldc.i4.s 0xC
0xafd6e  ldstr    aDomainrestrict_3// "domainRestrictionSettings"
0xafd73  stelem.ref
0xafd74  ldloc.0
0xafd75  ldc.i4.s 0xD
0xafd77  ldstr    aHasuniquepermi// "hasUniquePermissions"
0xafd7c  stelem.ref
0xafd7d  ldloc.0
0xafd7e  ldc.i4.s 0xE
0xafd80  ldstr    aMicroservicesh// "microserviceShareUiUrl"
0xafd85  stelem.ref
0xafd86  ldloc.0
0xafd87  ldc.i4.s 0xF
0xafd89  ldstr    aPermissionsinf// "permissionsInformation"
0xafd8e  stelem.ref
0xafd8f  ldloc.0
0xafd90  ldc.i4.s 0x10
0xafd92  ldstr    aSharedobjectty// "sharedObjectType"
0xafd97  stelem.ref
0xafd98  ldloc.0
0xafd99  ldc.i4.s 0x11
0xafd9b  ldstr    aShareuiurl// "shareUiUrl"
0xafda0  stelem.ref
0xafda1  ldloc.0
0xafda2  ldc.i4.s 0x12
0xafda4  ldstr    aSharingabiliti// "sharingAbilities"
0xafda9  stelem.ref
0xafdaa  ldloc.0
0xafdab  ldc.i4.s 0x13
0xafdad  ldstr    aSharingstatus// "sharingStatus"
0xafdb2  stelem.ref
0xafdb3  ldloc.0
0xafdb4  ldc.i4.s 0x14
0xafdb6  ldstr    aShowexternalsh_0// "showExternalSharingWarning"
0xafdbb  stelem.ref
0xafdbc  ldloc.0
0xafdbd  ldc.i4.s 0x15
0xafdbf  ldstr    aWeburl_0// "webUrl"
0xafdc4  stelem.ref
0xafdc5  ldloc.0
0xafdc6  stsfld   string[] Microsoft.SharePoint.Sharing.SharingInformationServerStub::s_valueProperties
0xafdcb  ldc.i4.1
0xafdcc  newarr   [mscorlib]System.String
0xafdd1  stloc.1
0xafdd2  ldloc.1
0xafdd3  ldc.i4.0
0xafdd4  ldstr    aPickersettings// "pickerSettings"
0xafdd9  stelem.ref
0xafdda  ldloc.1
0xafddb  stsfld   string[] Microsoft.SharePoint.Sharing.SharingInformationServerStub::s_refProperties
0xafde0  ldc.i4.3
0xafde1  newarr   [mscorlib]System.String
0xafde6  stloc.2
0xafde7  ldloc.2
0xafde8  ldc.i4.0
0xafde9  ldstr    aAccessrequests// "accessRequestSettings"
0xafdee  stelem.ref
0xafdef  ldloc.2
0xafdf0  ldc.i4.1
0xafdf1  ldstr    aDomainrestrict_3// "domainRestrictionSettings"
0xafdf6  stelem.ref
0xafdf7  ldloc.2
0xafdf8  ldc.i4.2
0xafdf9  ldstr    aPermissionsinf// "permissionsInformation"
0xafdfe  stelem.ref
0xafdff  ldloc.2
0xafe00  stsfld   string[] Microsoft.SharePoint.Sharing.SharingInformationServerStub::s_excludeFromDefaultRetrieveProperties
0xafe05  ldstr    aA683ddd779304d// "{a683ddd7-7930-4dcc-88fe-dc326c5e514e}"
0xafe0a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xafe0f  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Sharing.SharingInformationServerStub::s_targetTypeId
0xafe14  ret
```
