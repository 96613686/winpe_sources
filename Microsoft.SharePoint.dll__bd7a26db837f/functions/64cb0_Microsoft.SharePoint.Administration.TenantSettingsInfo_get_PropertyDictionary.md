# Microsoft.SharePoint.Administration.TenantSettingsInfo::get_PropertyDictionary

- ea: `0x64cb0`
- end: `0x65228`
- name: `Microsoft.SharePoint.Administration.TenantSettingsInfo::get_PropertyDictionary`
- size: `1400`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x65230`

## string_xrefs

- `0x64cde`: `AnonymousLinkExpiration`
- `0x64d62`: `ExternalSharingHelpLinkPresent`
- `0x64d78`: `InfoPath_AllowUserFormBrowser_Enabling`
- `0x64d8e`: `InfoPath_AllowUserFormBrowser_Rendering`
- `0x64da4`: `InfoPath_ExemptUserAgents_Customize`
- `0x64f1a`: `SSCShowNewGroupManagedPathPresent`
- `0x65002`: `SSCShowNewGroupManagedPathIsDefault`
- `0x650e5`: `TenantIsAccessOn`
- `0x650fb`: `TenantAccessAllowNewApp`
- `0x65111`: `DefaultSharingLinkType`
- `0x65170`: `ODBAccessRequests`
- `0x65181`: `BlockAccessOnUnmanagedDevices`
- `0x65197`: `LimitedAccessOnUnmanagedDevices`
- `0x651c3`: `FolderAnonymousLinkPermission`
- `0x651d4`: `FileAnonymousLinkPermission`
- `0x651e5`: `TenantIsAccessExtended`
- `0x651fb`: `TenantIsAccessEngaged`

## pseudocode

```c

```

## disassembly

```asm
0x64cb0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x64cb5  stloc.0
0x64cb6  ldloc.0
0x64cb7  ldstr    aSiteid_0// "SiteId"
0x64cbc  ldarg.0
0x64cbd  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.TenantSettingsInfo::SiteId
0x64cc2  box      [mscorlib]System.Guid
0x64cc7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64ccc  ldloc.0
0x64ccd  ldstr    aSharingcapabil// "SharingCapability"
0x64cd2  ldarg.0
0x64cd3  ldfld    string Microsoft.SharePoint.Administration.TenantSettingsInfo::SharingCapability
0x64cd8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64cdd  ldloc.0
0x64cde  ldstr    aAnonymouslinke// "AnonymousLinkExpiration"
0x64ce3  ldarg.0
0x64ce4  ldfld    int32 Microsoft.SharePoint.Administration.TenantSettingsInfo::AnonymousLinkExpiration
0x64ce9  box      [mscorlib]System.Int32
0x64cee  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64cf3  ldloc.0
0x64cf4  ldstr    aAutodisablepre// "AutoDisablePreviewFeatures"
0x64cf9  ldarg.0
0x64cfa  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::AutoDisablePreviewFeatures
0x64cff  box      [mscorlib]System.Boolean
0x64d04  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64d09  ldloc.0
0x64d0a  ldstr    aBccexternalsha// "BCCExternalSharingInvitations"
0x64d0f  ldarg.0
0x64d10  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::BCCExternalSharingInvitations
0x64d15  box      [mscorlib]System.Boolean
0x64d1a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64d1f  ldloc.0
0x64d20  ldstr    aBlockmsofbaand// "BlockMsoFbaAndIdcrlChallenges"
0x64d25  ldarg.0
0x64d26  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::BlockMsoFbaAndIdcrlChallenges
0x64d2b  box      [mscorlib]System.Boolean
0x64d30  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64d35  ldloc.0
0x64d36  ldstr    aCancontrolsite// "CanControlSiteCreationMode"
0x64d3b  ldarg.0
0x64d3c  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::CanControlSiteCreationMode
0x64d41  box      [mscorlib]System.Boolean
0x64d46  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64d4b  ldloc.0
0x64d4c  ldstr    aDutyofcarepeop// "DutyOfCarePeoplePicker"
0x64d51  ldarg.0
0x64d52  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::DutyOfCarePeoplePicker
0x64d57  box      [mscorlib]System.Boolean
0x64d5c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64d61  ldloc.0
0x64d62  ldstr    aExternalsharin// "ExternalSharingHelpLinkPresent"
0x64d67  ldarg.0
0x64d68  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::ExternalSharingHelpLinkPresent
0x64d6d  box      [mscorlib]System.Boolean
0x64d72  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64d77  ldloc.0
0x64d78  ldstr    aInfopathAllowu// "InfoPath_AllowUserFormBrowser_Enabling"
0x64d7d  ldarg.0
0x64d7e  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::InfoPath_AllowUserFormBrowser_Enabling
0x64d83  box      [mscorlib]System.Boolean
0x64d88  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64d8d  ldloc.0
0x64d8e  ldstr    aInfopathAllowu_0// "InfoPath_AllowUserFormBrowser_Rendering"
0x64d93  ldarg.0
0x64d94  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::InfoPath_AllowUserFormBrowser_Rendering
0x64d99  box      [mscorlib]System.Boolean
0x64d9e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64da3  ldloc.0
0x64da4  ldstr    aInfopathExempt// "InfoPath_ExemptUserAgents_Customize"
0x64da9  ldarg.0
0x64daa  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::InfoPath_ExemptUserAgents_Customize
0x64daf  box      [mscorlib]System.Boolean
0x64db4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64db9  ldloc.0
0x64dba  ldstr    aIpfsformstenan// "IPFSFormsTenantAdminEnabled"
0x64dbf  ldarg.0
0x64dc0  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::IPFSFormsTenantAdminEnabled
0x64dc5  box      [mscorlib]System.Boolean
0x64dca  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64dcf  ldloc.0
0x64dd0  ldstr    aOfficeclientad// "OfficeClientADALDisabled"
0x64dd5  ldarg.0
0x64dd6  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::OfficeClientADALDisabled
0x64ddb  box      [mscorlib]System.Boolean
0x64de0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64de5  ldloc.0
0x64de6  ldstr    aProvisionshare// "ProvisionSharedWithEveryoneFolder"
0x64deb  ldarg.0
0x64dec  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::ProvisionSharedWithEveryoneFolder
0x64df1  box      [mscorlib]System.Boolean
0x64df6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64dfb  ldloc.0
0x64dfc  ldstr    aRequireaccepti// "RequireAcceptingAccountMatchInvitedAcco"...
0x64e01  ldarg.0
0x64e02  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::RequireAcceptingAccountMatchInvitedAccount
0x64e07  box      [mscorlib]System.Boolean
0x64e0c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64e11  ldloc.0
0x64e12  ldstr    aRestrictunmana// "RestrictUnmanagedSyncClientForTenant"
0x64e17  ldarg.0
0x64e18  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::RestrictUnmanagedSyncClientForTenant
0x64e1d  box      [mscorlib]System.Boolean
0x64e22  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64e27  ldloc.0
0x64e28  ldstr    aShoweveryonecl// "ShowEveryoneClaim"
0x64e2d  ldarg.0
0x64e2e  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::ShowEveryoneClaim
0x64e33  box      [mscorlib]System.Boolean
0x64e38  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64e3d  ldloc.0
0x64e3e  ldstr    aShowalluserscl// "ShowAllUsersClaim"
0x64e43  ldarg.0
0x64e44  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::ShowAllUsersClaim
0x64e49  box      [mscorlib]System.Boolean
0x64e4e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64e53  ldloc.0
0x64e54  ldstr    aShoweveryoneex// "ShowEveryoneExceptUsersClaim"
0x64e59  ldarg.0
0x64e5a  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::ShowEveryoneExceptUsersClaim
0x64e5f  box      [mscorlib]System.Boolean
0x64e64  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64e69  ldloc.0
0x64e6a  ldstr    aSigninaccelera// "SignInAccelerationDomainPresent"
0x64e6f  ldarg.0
0x64e70  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::SignInAccelerationDomainPresent
0x64e75  box      [mscorlib]System.Boolean
0x64e7a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64e7f  ldloc.0
0x64e80  ldstr    aSitecreationmo// "SiteCreationMode"
0x64e85  ldarg.0
0x64e86  ldfld    int32 Microsoft.SharePoint.Administration.TenantSettingsInfo::SiteCreationMode
0x64e8b  box      [mscorlib]System.Int32
0x64e90  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64e95  ldloc.0
0x64e96  ldstr    aSpsocialenable// "SPSocialEnabled"
0x64e9b  ldarg.0
0x64e9c  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::SPSocialEnabled
0x64ea1  box      [mscorlib]System.Boolean
0x64ea6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64eab  ldloc.0
0x64eac  ldstr    aSsc2ndadmin// "SSC2ndAdmin"
0x64eb1  ldarg.0
0x64eb2  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::SSC2ndAdmin
0x64eb7  box      [mscorlib]System.Boolean
0x64ebc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64ec1  ldloc.0
0x64ec2  ldstr    aSscformurlpres// "SSCFormUrlPresent"
0x64ec7  ldarg.0
0x64ec8  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::SSCFormUrlPresent
0x64ecd  box      [mscorlib]System.Boolean
0x64ed2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64ed7  ldloc.0
0x64ed8  ldstr    aSscparenturlpr// "SSCParentUrlPresent"
0x64edd  ldarg.0
0x64ede  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::SSCParentUrlPresent
0x64ee3  box      [mscorlib]System.Boolean
0x64ee8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64eed  ldloc.0
0x64eee  ldstr    aSscshow// "SSCShow"
0x64ef3  ldarg.0
0x64ef4  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::SSCShow
0x64ef9  box      [mscorlib]System.Boolean
0x64efe  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64f03  ldloc.0
0x64f04  ldstr    aSscshownewgrou// "SSCShowNewGroup"
0x64f09  ldarg.0
0x64f0a  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::SSCShowNewGroup
0x64f0f  box      [mscorlib]System.Boolean
0x64f14  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64f19  ldloc.0
0x64f1a  ldstr    aSscshownewgrou_0// "SSCShowNewGroupManagedPathPresent"
0x64f1f  ldarg.0
0x64f20  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::SSCShowNewGroupManagedPathPresent
0x64f25  box      [mscorlib]System.Boolean
0x64f2a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64f2f  ldloc.0
0x64f30  ldstr    aTenantcancontr// "TenantCanControlSiteCreationMode"
0x64f35  ldarg.0
0x64f36  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::TenantCanControlSiteCreationMode
0x64f3b  box      [mscorlib]System.Boolean
0x64f40  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64f45  ldloc.0
0x64f46  ldstr    aTenantenablewe// "TenantEnableWebDavCookieIssuance"
0x64f4b  ldarg.0
0x64f4c  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::TenantEnableWebDavCookieIssuance
0x64f51  box      [mscorlib]System.Boolean
0x64f56  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64f5b  ldloc.0
0x64f5c  ldstr    aTenantwhrvalue// "TenantWhrValuePresent"
0x64f61  ldarg.0
0x64f62  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::TenantWhrValuePresent
0x64f67  box      [mscorlib]System.Boolean
0x64f6c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64f71  ldloc.0
0x64f72  ldstr    aUsepersistentc// "UsePersistentCookiesForExplorerView"
0x64f77  ldarg.0
0x64f78  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::UsePersistentCookiesForExplorerView
0x64f7d  box      [mscorlib]System.Boolean
0x64f82  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64f87  ldloc.0
0x64f88  ldstr    aWorkflowconnec// "WorkflowConnectedState"
0x64f8d  ldarg.0
0x64f8e  ldfld    int32 Microsoft.SharePoint.Administration.TenantSettingsInfo::WorkflowConnectedState
0x64f93  box      [mscorlib]System.Int32
0x64f98  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64f9d  ldloc.0
0x64f9e  ldstr    aYammerenabled// "YammerEnabled"
0x64fa3  ldarg.0
0x64fa4  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::YammerEnabled
0x64fa9  box      [mscorlib]System.Boolean
0x64fae  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64fb3  ldloc.0
0x64fb4  ldstr    aOdbnewuxoff// "ODBNewUXOff"
0x64fb9  ldarg.0
0x64fba  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::ODBNewUXOff
0x64fbf  box      [mscorlib]System.Boolean
0x64fc4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64fc9  ldloc.0
0x64fca  ldstr    aSplistnewuxoff// "SPListNewUXOff"
0x64fcf  ldarg.0
0x64fd0  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::SPListNewUXOff
0x64fd5  box      [mscorlib]System.Boolean
0x64fda  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64fdf  ldloc.0
0x64fe0  ldstr    aSiteprefixnoac// "SitePrefixNoACPMap"
0x64fe5  ldarg.0
0x64fe6  ldfld    string Microsoft.SharePoint.Administration.TenantSettingsInfo::SitePrefixNoACPMap
0x64feb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64ff0  ldloc.0
0x64ff1  ldstr    aGroupcreationn// "GroupCreationNewUX"
0x64ff6  ldarg.0
0x64ff7  ldfld    string Microsoft.SharePoint.Administration.TenantSettingsInfo::GroupCreationNewUX
0x64ffc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65001  ldloc.0
0x65002  ldstr    aSscshownewgrou_1// "SSCShowNewGroupManagedPathIsDefault"
0x65007  ldarg.0
0x65008  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::SSCShowNewGroupManagedPathIsDefault
0x6500d  box      [mscorlib]System.Boolean
0x65012  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65017  ldloc.0
0x65018  ldstr    aPolicyoption// "PolicyOption"
0x6501d  ldarg.0
0x6501e  ldfld    string Microsoft.SharePoint.Administration.TenantSettingsInfo::PolicyOption
0x65023  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65028  ldloc.0
0x65029  ldstr    aAllowsiteconfi// "AllowSiteConfidentiality"
0x6502e  ldarg.0
0x6502f  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::AllowSiteConfidentiality
0x65034  box      [mscorlib]System.Boolean
0x65039  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x6503e  ldloc.0
0x6503f  ldstr    aPoundpercent// "PoundPercent"
0x65044  ldarg.0
0x65045  ldfld    string Microsoft.SharePoint.Administration.TenantSettingsInfo::PoundPercent
0x6504a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x6504f  ldloc.0
0x65050  ldstr    aIpaddressenfor// "IPAddressEnforcement"
0x65055  ldarg.0
0x65056  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::IPAddressEnforcement
0x6505b  box      [mscorlib]System.Boolean
0x65060  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65065  ldloc.0
0x65066  ldstr    aIdlesessionsig// "IdleSessionSignOutForUnmanagedDevices"
0x6506b  ldarg.0
0x6506c  ldfld    string Microsoft.SharePoint.Administration.TenantSettingsInfo::IdleSessionSignOutForUnmanagedDevices
0x65071  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65076  ldloc.0
0x65077  ldstr    aBlockdownloado// "BlockDownloadOfViewableFilesOnUnmanaged"...
0x6507c  ldarg.0
0x6507d  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::BlockDownloadOfViewableFilesOnUnmanagedDevicesPolicy
0x65082  box      [mscorlib]System.Boolean
0x65087  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x6508c  ldloc.0
0x6508d  ldstr    aBlockdownloado_0// "BlockDownloadOfAllFilesOnUnmanagedDevic"...
0x65092  ldarg.0
0x65093  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::BlockDownloadOfAllFilesOnUnmanagedDevicesPolicy
0x65098  box      [mscorlib]System.Boolean
0x6509d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x650a2  ldloc.0
0x650a3  ldstr    aOptoutofgroove// "OptOutOfGrooveBlock"
0x650a8  ldarg.0
0x650a9  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::OptOutOfGrooveBlock
0x650ae  box      [mscorlib]System.Boolean
0x650b3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x650b8  ldloc.0
0x650b9  ldstr    aOptedoutviaadm// "OptedOutViaAdminPowershell"
0x650be  ldarg.0
0x650bf  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::OptedOutViaAdminPowershell
0x650c4  box      [mscorlib]System.Boolean
0x650c9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x650ce  ldloc.0
0x650cf  ldstr    aPermissivebrow// "PermissiveBrowserFileHandlingOverride"
0x650d4  ldarg.0
0x650d5  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::PermissiveBrowserFileHandlingOverride
0x650da  box      [mscorlib]System.Boolean
0x650df  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x650e4  ldloc.0
0x650e5  ldstr    aTenantisaccess// "TenantIsAccessOn"
0x650ea  ldarg.0
0x650eb  ldfld    bool Microsoft.SharePoint.Administration.TenantSettingsInfo::TenantIsAccessOn
  ... truncated ...
```
