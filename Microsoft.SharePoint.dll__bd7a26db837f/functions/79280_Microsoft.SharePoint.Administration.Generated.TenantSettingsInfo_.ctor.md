# Microsoft.SharePoint.Administration.Generated.TenantSettingsInfo::.ctor

- ea: `0x79280`
- end: `0x79c78`
- name: `Microsoft.SharePoint.Administration.Generated.TenantSettingsInfo::.ctor`
- size: `2552`
- prototype: ``
- caller_count: `1`
- callee_count: `69`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ddb0`

## callees

- `0x6edf0`
- `0x78a50`
- `0x78a70`
- `0x78a90`
- `0x78ab0`
- `0x78ad0`
- `0x78af0`
- `0x78b10`
- `0x78b30`
- `0x78b50`
- `0x78b70`
- `0x78b90`
- `0x78bb0`
- `0x78bd0`
- `0x78bf0`
- `0x78c10`
- `0x78c30`
- `0x78c50`
- `0x78c70`
- `0x78c90`
- `0x78cb0`
- `0x78cd0`
- `0x78cf0`
- `0x78d10`
- `0x78d30`
- `0x78d50`
- `0x78d70`
- `0x78d90`
- `0x78db0`
- `0x78dd0`
- `0x78df0`
- `0x78e10`
- `0x78e30`
- `0x78e50`
- `0x78e70`
- `0x78e90`
- `0x78eb0`
- `0x78ed0`
- `0x78ef0`
- `0x78f10`
- `0x78f30`
- `0x78f50`
- `0x78f70`
- `0x78f90`
- `0x78fb0`
- `0x78fd0`
- `0x78ff0`
- `0x79010`
- `0x79030`
- `0x79050`

## string_xrefs

- `0x792d5`: `AnonymousLinkExpiration`
- `0x793c5`: `ExternalSharingHelpLinkPresent`
- `0x793ed`: `InfoPath_AllowUserFormBrowser_Enabling`
- `0x79415`: `InfoPath_AllowUserFormBrowser_Rendering`
- `0x7943d`: `InfoPath_ExemptUserAgents_Customize`
- `0x796e5`: `SSCShowNewGroupManagedPathPresent`
- `0x7988d`: `SSCShowNewGroupManagedPathIsDefault`
- `0x79a2d`: `TenantIsAccessOn`
- `0x79a55`: `TenantAccessAllowNewApp`
- `0x79a7d`: `DefaultSharingLinkType`
- `0x79b2d`: `ODBAccessRequests`
- `0x79b4d`: `BlockAccessOnUnmanagedDevices`
- `0x79b75`: `LimitedAccessOnUnmanagedDevices`
- `0x79bc5`: `FolderAnonymousLinkPermission`
- `0x79be5`: `FileAnonymousLinkPermission`
- `0x79c05`: `TenantIsAccessExtended`
- `0x79c2d`: `TenantIsAccessEngaged`

## pseudocode

```c

```

## disassembly

```asm
0x79280  ldarg.0
0x79281  ldarg.1
0x79282  call     instance void Microsoft.SharePoint.Administration.Generated.BaseSlapiEvent::.ctor(class Microsoft.SharePoint.Administration.SPLogEventUsageEntry entry)
0x79287  ldarg.1
0x79288  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x7928d  ldstr    aSiteid_0// "SiteId"
0x79292  ldloca.s 0
0x79294  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x79299  brfalse.s loc_792AF
0x7929b  ldloc.0
0x7929c  isinst   [mscorlib]System.Guid
0x792a1  brfalse.s loc_792AF
0x792a3  ldarg.0
0x792a4  ldloc.0
0x792a5  unbox.any [mscorlib]System.Guid
0x792aa  call     instance void Microsoft.SharePoint.Administration.Generated.TenantSettingsInfo::set_SiteId(valuetype [mscorlib]System.Guid value)
0x792af  ldarg.1
0x792b0  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x792b5  ldstr    aSharingcapabil// "SharingCapability"
0x792ba  ldloca.s 0
0x792bc  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x792c1  brfalse.s loc_792CF
0x792c3  ldarg.0
0x792c4  ldloc.0
0x792c5  isinst   [mscorlib]System.String
0x792ca  call     instance void Microsoft.SharePoint.Administration.Generated.TenantSettingsInfo::set_SharingCapability(string value)
0x792cf  ldarg.1
0x792d0  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x792d5  ldstr    aAnonymouslinke// "AnonymousLinkExpiration"
0x792da  ldloca.s 0
0x792dc  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x792e1  brfalse.s loc_792F7
0x792e3  ldloc.0
0x792e4  isinst   [mscorlib]System.Int32
0x792e9  brfalse.s loc_792F7
0x792eb  ldarg.0
0x792ec  ldloc.0
0x792ed  unbox.any [mscorlib]System.Int32
0x792f2  call     instance void Microsoft.SharePoint.Administration.Generated.TenantSettingsInfo::set_AnonymousLinkExpiration(int32 value)
0x792f7  ldarg.1
0x792f8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x792fd  ldstr    aAutodisablepre// "AutoDisablePreviewFeatures"
0x79302  ldloca.s 0
0x79304  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x79309  brfalse.s loc_7931F
0x7930b  ldloc.0
0x7930c  isinst   [mscorlib]System.Boolean
0x79311  brfalse.s loc_7931F
0x79313  ldarg.0
0x79314  ldloc.0
0x79315  unbox.any [mscorlib]System.Boolean
0x7931a  call     instance void Microsoft.SharePoint.Administration.Generated.TenantSettingsInfo::set_AutoDisablePreviewFeatures(bool value)
0x7931f  ldarg.1
0x79320  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x79325  ldstr    aBccexternalsha// "BCCExternalSharingInvitations"
0x7932a  ldloca.s 0
0x7932c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x79331  brfalse.s loc_79347
0x79333  ldloc.0
0x79334  isinst   [mscorlib]System.Boolean
0x79339  brfalse.s loc_79347
0x7933b  ldarg.0
0x7933c  ldloc.0
0x7933d  unbox.any [mscorlib]System.Boolean
0x79342  call     instance void Microsoft.SharePoint.Administration.Generated.TenantSettingsInfo::set_BCCExternalSharingInvitations(bool value)
0x79347  ldarg.1
0x79348  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x7934d  ldstr    aBlockmsofbaand// "BlockMsoFbaAndIdcrlChallenges"
0x79352  ldloca.s 0
0x79354  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x79359  brfalse.s loc_7936F
0x7935b  ldloc.0
0x7935c  isinst   [mscorlib]System.Boolean
0x79361  brfalse.s loc_7936F
0x79363  ldarg.0
0x79364  ldloc.0
0x79365  unbox.any [mscorlib]System.Boolean
0x7936a  call     instance void Microsoft.SharePoint.Administration.Generated.TenantSettingsInfo::set_BlockMsoFbaAndIdcrlChallenges(bool value)
0x7936f  ldarg.1
0x79370  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x79375  ldstr    aCancontrolsite// "CanControlSiteCreationMode"
0x7937a  ldloca.s 0
0x7937c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x79381  brfalse.s loc_79397
0x79383  ldloc.0
0x79384  isinst   [mscorlib]System.Boolean
0x79389  brfalse.s loc_79397
0x7938b  ldarg.0
0x7938c  ldloc.0
0x7938d  unbox.any [mscorlib]System.Boolean
0x79392  call     instance void Microsoft.SharePoint.Administration.Generated.TenantSettingsInfo::set_CanControlSiteCreationMode(bool value)
0x79397  ldarg.1
0x79398  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x7939d  ldstr    aDutyofcarepeop// "DutyOfCarePeoplePicker"
0x793a2  ldloca.s 0
0x793a4  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x793a9  brfalse.s loc_793BF
0x793ab  ldloc.0
0x793ac  isinst   [mscorlib]System.Boolean
0x793b1  brfalse.s loc_793BF
0x793b3  ldarg.0
0x793b4  ldloc.0
0x793b5  unbox.any [mscorlib]System.Boolean
0x793ba  call     instance void Microsoft.SharePoint.Administration.Generated.TenantSettingsInfo::set_DutyOfCarePeoplePicker(bool value)
0x793bf  ldarg.1
0x793c0  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x793c5  ldstr    aExternalsharin// "ExternalSharingHelpLinkPresent"
0x793ca  ldloca.s 0
0x793cc  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x793d1  brfalse.s loc_793E7
0x793d3  ldloc.0
0x793d4  isinst   [mscorlib]System.Boolean
0x793d9  brfalse.s loc_793E7
0x793db  ldarg.0
0x793dc  ldloc.0
0x793dd  unbox.any [mscorlib]System.Boolean
0x793e2  call     instance void Microsoft.SharePoint.Administration.Generated.TenantSettingsInfo::set_ExternalSharingHelpLinkPresent(bool value)
0x793e7  ldarg.1
0x793e8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x793ed  ldstr    aInfopathAllowu// "InfoPath_AllowUserFormBrowser_Enabling"
0x793f2  ldloca.s 0
0x793f4  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x793f9  brfalse.s loc_7940F
0x793fb  ldloc.0
0x793fc  isinst   [mscorlib]System.Boolean
0x79401  brfalse.s loc_7940F
0x79403  ldarg.0
0x79404  ldloc.0
0x79405  unbox.any [mscorlib]System.Boolean
0x7940a  call     instance void Microsoft.SharePoint.Administration.Generated.TenantSettingsInfo::set_InfoPath_AllowUserFormBrowser_Enabling(bool value)
0x7940f  ldarg.1
0x79410  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x79415  ldstr    aInfopathAllowu_0// "InfoPath_AllowUserFormBrowser_Rendering"
0x7941a  ldloca.s 0
0x7941c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x79421  brfalse.s loc_79437
0x79423  ldloc.0
0x79424  isinst   [mscorlib]System.Boolean
0x79429  brfalse.s loc_79437
0x7942b  ldarg.0
0x7942c  ldloc.0
0x7942d  unbox.any [mscorlib]System.Boolean
0x79432  call     instance void Microsoft.SharePoint.Administration.Generated.TenantSettingsInfo::set_InfoPath_AllowUserFormBrowser_Rendering(bool value)
0x79437  ldarg.1
0x79438  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x7943d  ldstr    aInfopathExempt// "InfoPath_ExemptUserAgents_Customize"
0x79442  ldloca.s 0
0x79444  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x79449  brfalse.s loc_7945F
0x7944b  ldloc.0
0x7944c  isinst   [mscorlib]System.Boolean
0x79451  brfalse.s loc_7945F
0x79453  ldarg.0
0x79454  ldloc.0
0x79455  unbox.any [mscorlib]System.Boolean
0x7945a  call     instance void Microsoft.SharePoint.Administration.Generated.TenantSettingsInfo::set_InfoPath_ExemptUserAgents_Customize(bool value)
0x7945f  ldarg.1
0x79460  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x79465  ldstr    aIpfsformstenan// "IPFSFormsTenantAdminEnabled"
0x7946a  ldloca.s 0
0x7946c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x79471  brfalse.s loc_79487
0x79473  ldloc.0
0x79474  isinst   [mscorlib]System.Boolean
0x79479  brfalse.s loc_79487
0x7947b  ldarg.0
0x7947c  ldloc.0
0x7947d  unbox.any [mscorlib]System.Boolean
0x79482  call     instance void Microsoft.SharePoint.Administration.Generated.TenantSettingsInfo::set_IPFSFormsTenantAdminEnabled(bool value)
0x79487  ldarg.1
0x79488  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x7948d  ldstr    aOfficeclientad// "OfficeClientADALDisabled"
0x79492  ldloca.s 0
0x79494  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x79499  brfalse.s loc_794AF
0x7949b  ldloc.0
0x7949c  isinst   [mscorlib]System.Boolean
0x794a1  brfalse.s loc_794AF
0x794a3  ldarg.0
0x794a4  ldloc.0
0x794a5  unbox.any [mscorlib]System.Boolean
0x794aa  call     instance void Microsoft.SharePoint.Administration.Generated.TenantSettingsInfo::set_OfficeClientADALDisabled(bool value)
0x794af  ldarg.1
0x794b0  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x794b5  ldstr    aProvisionshare// "ProvisionSharedWithEveryoneFolder"
0x794ba  ldloca.s 0
0x794bc  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x794c1  brfalse.s loc_794D7
0x794c3  ldloc.0
0x794c4  isinst   [mscorlib]System.Boolean
0x794c9  brfalse.s loc_794D7
0x794cb  ldarg.0
0x794cc  ldloc.0
0x794cd  unbox.any [mscorlib]System.Boolean
0x794d2  call     instance void Microsoft.SharePoint.Administration.Generated.TenantSettingsInfo::set_ProvisionSharedWithEveryoneFolder(bool value)
0x794d7  ldarg.1
0x794d8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x794dd  ldstr    aRequireaccepti// "RequireAcceptingAccountMatchInvitedAcco"...
0x794e2  ldloca.s 0
0x794e4  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x794e9  brfalse.s loc_794FF
0x794eb  ldloc.0
0x794ec  isinst   [mscorlib]System.Boolean
0x794f1  brfalse.s loc_794FF
0x794f3  ldarg.0
0x794f4  ldloc.0
0x794f5  unbox.any [mscorlib]System.Boolean
0x794fa  call     instance void Microsoft.SharePoint.Administration.Generated.TenantSettingsInfo::set_RequireAcceptingAccountMatchInvitedAccount(bool value)
0x794ff  ldarg.1
0x79500  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x79505  ldstr    aRestrictunmana// "RestrictUnmanagedSyncClientForTenant"
0x7950a  ldloca.s 0
0x7950c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x79511  brfalse.s loc_79527
0x79513  ldloc.0
0x79514  isinst   [mscorlib]System.Boolean
0x79519  brfalse.s loc_79527
0x7951b  ldarg.0
0x7951c  ldloc.0
0x7951d  unbox.any [mscorlib]System.Boolean
0x79522  call     instance void Microsoft.SharePoint.Administration.Generated.TenantSettingsInfo::set_RestrictUnmanagedSyncClientForTenant(bool value)
0x79527  ldarg.1
0x79528  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x7952d  ldstr    aShoweveryonecl// "ShowEveryoneClaim"
0x79532  ldloca.s 0
0x79534  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x79539  brfalse.s loc_7954F
0x7953b  ldloc.0
0x7953c  isinst   [mscorlib]System.Boolean
0x79541  brfalse.s loc_7954F
0x79543  ldarg.0
0x79544  ldloc.0
0x79545  unbox.any [mscorlib]System.Boolean
0x7954a  call     instance void Microsoft.SharePoint.Administration.Generated.TenantSettingsInfo::set_ShowEveryoneClaim(bool value)
0x7954f  ldarg.1
0x79550  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x79555  ldstr    aShowalluserscl// "ShowAllUsersClaim"
0x7955a  ldloca.s 0
0x7955c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x79561  brfalse.s loc_79577
0x79563  ldloc.0
0x79564  isinst   [mscorlib]System.Boolean
0x79569  brfalse.s loc_79577
0x7956b  ldarg.0
0x7956c  ldloc.0
0x7956d  unbox.any [mscorlib]System.Boolean
0x79572  call     instance void Microsoft.SharePoint.Administration.Generated.TenantSettingsInfo::set_ShowAllUsersClaim(bool value)
0x79577  ldarg.1
0x79578  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x7957d  ldstr    aShoweveryoneex// "ShowEveryoneExceptUsersClaim"
0x79582  ldloca.s 0
0x79584  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x79589  brfalse.s loc_7959F
0x7958b  ldloc.0
0x7958c  isinst   [mscorlib]System.Boolean
0x79591  brfalse.s loc_7959F
0x79593  ldarg.0
0x79594  ldloc.0
0x79595  unbox.any [mscorlib]System.Boolean
0x7959a  call     instance void Microsoft.SharePoint.Administration.Generated.TenantSettingsInfo::set_ShowEveryoneExceptUsersClaim(bool value)
0x7959f  ldarg.1
0x795a0  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x795a5  ldstr    aSigninaccelera// "SignInAccelerationDomainPresent"
0x795aa  ldloca.s 0
0x795ac  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x795b1  brfalse.s loc_795C7
0x795b3  ldloc.0
0x795b4  isinst   [mscorlib]System.Boolean
0x795b9  brfalse.s loc_795C7
0x795bb  ldarg.0
0x795bc  ldloc.0
0x795bd  unbox.any [mscorlib]System.Boolean
0x795c2  call     instance void Microsoft.SharePoint.Administration.Generated.TenantSettingsInfo::set_SignInAccelerationDomainPresent(bool value)
0x795c7  ldarg.1
0x795c8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x795cd  ldstr    aSitecreationmo// "SiteCreationMode"
0x795d2  ldloca.s 0
0x795d4  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x795d9  brfalse.s loc_795EF
0x795db  ldloc.0
0x795dc  isinst   [mscorlib]System.Int32
0x795e1  brfalse.s loc_795EF
0x795e3  ldarg.0
0x795e4  ldloc.0
0x795e5  unbox.any [mscorlib]System.Int32
0x795ea  call     instance void Microsoft.SharePoint.Administration.Generated.TenantSettingsInfo::set_SiteCreationMode(int32 value)
0x795ef  ldarg.1
0x795f0  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x795f5  ldstr    aSpsocialenable// "SPSocialEnabled"
0x795fa  ldloca.s 0
0x795fc  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x79601  brfalse.s loc_79617
0x79603  ldloc.0
0x79604  isinst   [mscorlib]System.Boolean
0x79609  brfalse.s loc_79617
0x7960b  ldarg.0
0x7960c  ldloc.0
0x7960d  unbox.any [mscorlib]System.Boolean
0x79612  call     instance void Microsoft.SharePoint.Administration.Generated.TenantSettingsInfo::set_SPSocialEnabled(bool value)
0x79617  ldarg.1
  ... truncated ...
```
