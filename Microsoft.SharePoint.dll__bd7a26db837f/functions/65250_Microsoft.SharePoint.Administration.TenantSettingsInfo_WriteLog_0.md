# Microsoft.SharePoint.Administration.TenantSettingsInfo::WriteLog_0

- ea: `0x65250`
- end: `0x656c6`
- name: `Microsoft.SharePoint.Administration.TenantSettingsInfo::WriteLog_0`
- size: `1142`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x37a3a0`

## string_xrefs

- `0x65274`: `AnonymousLinkExpiration`
- `0x652de`: `ExternalSharingHelpLinkPresent`
- `0x652f0`: `InfoPath_AllowUserFormBrowser_Enabling`
- `0x65302`: `InfoPath_AllowUserFormBrowser_Rendering`
- `0x65314`: `InfoPath_ExemptUserAgents_Customize`
- `0x65446`: `SSCShowNewGroupManagedPathPresent`
- `0x65502`: `SSCShowNewGroupManagedPathIsDefault`
- `0x655b9`: `TenantIsAccessOn`
- `0x655cb`: `TenantAccessAllowNewApp`
- `0x655dd`: `DefaultSharingLinkType`
- `0x65628`: `ODBAccessRequests`
- `0x65635`: `BlockAccessOnUnmanagedDevices`
- `0x65647`: `LimitedAccessOnUnmanagedDevices`
- `0x6566b`: `FolderAnonymousLinkPermission`
- `0x65678`: `FileAnonymousLinkPermission`
- `0x65685`: `TenantIsAccessExtended`
- `0x65697`: `TenantIsAccessEngaged`

## pseudocode

```c

```

## disassembly

```asm
0x65250  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x65255  stloc.0
0x65256  ldloc.0
0x65257  ldstr    aSiteid_0// "SiteId"
0x6525c  ldarg.0
0x6525d  box      [mscorlib]System.Guid
0x65262  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65267  ldloc.0
0x65268  ldstr    aSharingcapabil// "SharingCapability"
0x6526d  ldarg.1
0x6526e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65273  ldloc.0
0x65274  ldstr    aAnonymouslinke// "AnonymousLinkExpiration"
0x65279  ldarg.2
0x6527a  box      [mscorlib]System.Int32
0x6527f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65284  ldloc.0
0x65285  ldstr    aAutodisablepre// "AutoDisablePreviewFeatures"
0x6528a  ldarg.3
0x6528b  box      [mscorlib]System.Boolean
0x65290  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65295  ldloc.0
0x65296  ldstr    aBccexternalsha// "BCCExternalSharingInvitations"
0x6529b  ldarg.s  4
0x6529d  box      [mscorlib]System.Boolean
0x652a2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x652a7  ldloc.0
0x652a8  ldstr    aBlockmsofbaand// "BlockMsoFbaAndIdcrlChallenges"
0x652ad  ldarg.s  5
0x652af  box      [mscorlib]System.Boolean
0x652b4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x652b9  ldloc.0
0x652ba  ldstr    aCancontrolsite// "CanControlSiteCreationMode"
0x652bf  ldarg.s  6
0x652c1  box      [mscorlib]System.Boolean
0x652c6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x652cb  ldloc.0
0x652cc  ldstr    aDutyofcarepeop// "DutyOfCarePeoplePicker"
0x652d1  ldarg.s  7
0x652d3  box      [mscorlib]System.Boolean
0x652d8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x652dd  ldloc.0
0x652de  ldstr    aExternalsharin// "ExternalSharingHelpLinkPresent"
0x652e3  ldarg.s  8
0x652e5  box      [mscorlib]System.Boolean
0x652ea  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x652ef  ldloc.0
0x652f0  ldstr    aInfopathAllowu// "InfoPath_AllowUserFormBrowser_Enabling"
0x652f5  ldarg.s  9
0x652f7  box      [mscorlib]System.Boolean
0x652fc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65301  ldloc.0
0x65302  ldstr    aInfopathAllowu_0// "InfoPath_AllowUserFormBrowser_Rendering"
0x65307  ldarg.s  0xA
0x65309  box      [mscorlib]System.Boolean
0x6530e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65313  ldloc.0
0x65314  ldstr    aInfopathExempt// "InfoPath_ExemptUserAgents_Customize"
0x65319  ldarg.s  0xB
0x6531b  box      [mscorlib]System.Boolean
0x65320  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65325  ldloc.0
0x65326  ldstr    aIpfsformstenan// "IPFSFormsTenantAdminEnabled"
0x6532b  ldarg.s  0xC
0x6532d  box      [mscorlib]System.Boolean
0x65332  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65337  ldloc.0
0x65338  ldstr    aOfficeclientad// "OfficeClientADALDisabled"
0x6533d  ldarg.s  0xD
0x6533f  box      [mscorlib]System.Boolean
0x65344  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65349  ldloc.0
0x6534a  ldstr    aProvisionshare// "ProvisionSharedWithEveryoneFolder"
0x6534f  ldarg.s  0xE
0x65351  box      [mscorlib]System.Boolean
0x65356  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x6535b  ldloc.0
0x6535c  ldstr    aRequireaccepti// "RequireAcceptingAccountMatchInvitedAcco"...
0x65361  ldarg.s  0xF
0x65363  box      [mscorlib]System.Boolean
0x65368  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x6536d  ldloc.0
0x6536e  ldstr    aRestrictunmana// "RestrictUnmanagedSyncClientForTenant"
0x65373  ldarg.s  0x10
0x65375  box      [mscorlib]System.Boolean
0x6537a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x6537f  ldloc.0
0x65380  ldstr    aShoweveryonecl// "ShowEveryoneClaim"
0x65385  ldarg.s  0x11
0x65387  box      [mscorlib]System.Boolean
0x6538c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65391  ldloc.0
0x65392  ldstr    aShowalluserscl// "ShowAllUsersClaim"
0x65397  ldarg.s  0x12
0x65399  box      [mscorlib]System.Boolean
0x6539e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x653a3  ldloc.0
0x653a4  ldstr    aShoweveryoneex// "ShowEveryoneExceptUsersClaim"
0x653a9  ldarg.s  0x13
0x653ab  box      [mscorlib]System.Boolean
0x653b0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x653b5  ldloc.0
0x653b6  ldstr    aSigninaccelera// "SignInAccelerationDomainPresent"
0x653bb  ldarg.s  0x14
0x653bd  box      [mscorlib]System.Boolean
0x653c2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x653c7  ldloc.0
0x653c8  ldstr    aSitecreationmo// "SiteCreationMode"
0x653cd  ldarg.s  0x15
0x653cf  box      [mscorlib]System.Int32
0x653d4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x653d9  ldloc.0
0x653da  ldstr    aSpsocialenable// "SPSocialEnabled"
0x653df  ldarg.s  0x16
0x653e1  box      [mscorlib]System.Boolean
0x653e6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x653eb  ldloc.0
0x653ec  ldstr    aSsc2ndadmin// "SSC2ndAdmin"
0x653f1  ldarg.s  0x17
0x653f3  box      [mscorlib]System.Boolean
0x653f8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x653fd  ldloc.0
0x653fe  ldstr    aSscformurlpres// "SSCFormUrlPresent"
0x65403  ldarg.s  0x18
0x65405  box      [mscorlib]System.Boolean
0x6540a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x6540f  ldloc.0
0x65410  ldstr    aSscparenturlpr// "SSCParentUrlPresent"
0x65415  ldarg.s  0x19
0x65417  box      [mscorlib]System.Boolean
0x6541c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65421  ldloc.0
0x65422  ldstr    aSscshow// "SSCShow"
0x65427  ldarg.s  0x1A
0x65429  box      [mscorlib]System.Boolean
0x6542e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65433  ldloc.0
0x65434  ldstr    aSscshownewgrou// "SSCShowNewGroup"
0x65439  ldarg.s  0x1B
0x6543b  box      [mscorlib]System.Boolean
0x65440  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65445  ldloc.0
0x65446  ldstr    aSscshownewgrou_0// "SSCShowNewGroupManagedPathPresent"
0x6544b  ldarg.s  0x1C
0x6544d  box      [mscorlib]System.Boolean
0x65452  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65457  ldloc.0
0x65458  ldstr    aTenantcancontr// "TenantCanControlSiteCreationMode"
0x6545d  ldarg.s  0x1D
0x6545f  box      [mscorlib]System.Boolean
0x65464  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65469  ldloc.0
0x6546a  ldstr    aTenantenablewe// "TenantEnableWebDavCookieIssuance"
0x6546f  ldarg.s  0x1E
0x65471  box      [mscorlib]System.Boolean
0x65476  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x6547b  ldloc.0
0x6547c  ldstr    aTenantwhrvalue// "TenantWhrValuePresent"
0x65481  ldarg.s  0x1F
0x65483  box      [mscorlib]System.Boolean
0x65488  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x6548d  ldloc.0
0x6548e  ldstr    aUsepersistentc// "UsePersistentCookiesForExplorerView"
0x65493  ldarg.s  0x20
0x65495  box      [mscorlib]System.Boolean
0x6549a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x6549f  ldloc.0
0x654a0  ldstr    aWorkflowconnec// "WorkflowConnectedState"
0x654a5  ldarg.s  0x21
0x654a7  box      [mscorlib]System.Int32
0x654ac  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x654b1  ldloc.0
0x654b2  ldstr    aYammerenabled// "YammerEnabled"
0x654b7  ldarg.s  0x22
0x654b9  box      [mscorlib]System.Boolean
0x654be  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x654c3  ldloc.0
0x654c4  ldstr    aOdbnewuxoff// "ODBNewUXOff"
0x654c9  ldarg.s  0x23
0x654cb  box      [mscorlib]System.Boolean
0x654d0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x654d5  ldloc.0
0x654d6  ldstr    aSplistnewuxoff// "SPListNewUXOff"
0x654db  ldarg.s  0x24
0x654dd  box      [mscorlib]System.Boolean
0x654e2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x654e7  ldloc.0
0x654e8  ldstr    aSiteprefixnoac// "SitePrefixNoACPMap"
0x654ed  ldarg.s  0x25
0x654ef  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x654f4  ldloc.0
0x654f5  ldstr    aGroupcreationn// "GroupCreationNewUX"
0x654fa  ldarg.s  0x26
0x654fc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65501  ldloc.0
0x65502  ldstr    aSscshownewgrou_1// "SSCShowNewGroupManagedPathIsDefault"
0x65507  ldarg.s  0x27
0x65509  box      [mscorlib]System.Boolean
0x6550e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65513  ldloc.0
0x65514  ldstr    aPolicyoption// "PolicyOption"
0x65519  ldarg.s  0x28
0x6551b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65520  ldloc.0
0x65521  ldstr    aAllowsiteconfi// "AllowSiteConfidentiality"
0x65526  ldarg.s  0x29
0x65528  box      [mscorlib]System.Boolean
0x6552d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65532  ldloc.0
0x65533  ldstr    aPoundpercent// "PoundPercent"
0x65538  ldarg.s  0x2A
0x6553a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x6553f  ldloc.0
0x65540  ldstr    aIpaddressenfor// "IPAddressEnforcement"
0x65545  ldarg.s  0x2B
0x65547  box      [mscorlib]System.Boolean
0x6554c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65551  ldloc.0
0x65552  ldstr    aIdlesessionsig// "IdleSessionSignOutForUnmanagedDevices"
0x65557  ldarg.s  0x2C
0x65559  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x6555e  ldloc.0
0x6555f  ldstr    aBlockdownloado// "BlockDownloadOfViewableFilesOnUnmanaged"...
0x65564  ldarg.s  0x2D
0x65566  box      [mscorlib]System.Boolean
0x6556b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65570  ldloc.0
0x65571  ldstr    aBlockdownloado_0// "BlockDownloadOfAllFilesOnUnmanagedDevic"...
0x65576  ldarg.s  0x2E
0x65578  box      [mscorlib]System.Boolean
0x6557d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65582  ldloc.0
0x65583  ldstr    aOptoutofgroove// "OptOutOfGrooveBlock"
0x65588  ldarg.s  0x2F
0x6558a  box      [mscorlib]System.Boolean
0x6558f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65594  ldloc.0
0x65595  ldstr    aOptedoutviaadm// "OptedOutViaAdminPowershell"
0x6559a  ldarg.s  0x30
0x6559c  box      [mscorlib]System.Boolean
0x655a1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x655a6  ldloc.0
0x655a7  ldstr    aPermissivebrow// "PermissiveBrowserFileHandlingOverride"
0x655ac  ldarg.s  0x31
0x655ae  box      [mscorlib]System.Boolean
0x655b3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x655b8  ldloc.0
0x655b9  ldstr    aTenantisaccess// "TenantIsAccessOn"
0x655be  ldarg.s  0x32
0x655c0  box      [mscorlib]System.Boolean
0x655c5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x655ca  ldloc.0
0x655cb  ldstr    aTenantaccessal// "TenantAccessAllowNewApp"
0x655d0  ldarg.s  0x33
0x655d2  box      [mscorlib]System.Boolean
0x655d7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x655dc  ldloc.0
0x655dd  ldstr    aDefaultsharing// "DefaultSharingLinkType"
0x655e2  ldarg.s  0x34
0x655e4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x655e9  ldloc.0
0x655ea  ldstr    aGuestsharinggr// "GuestSharingGroupAllowListSettingPopula"...
0x655ef  ldarg.s  0x35
0x655f1  box      [mscorlib]System.Boolean
0x655f6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x655fb  ldloc.0
0x655fc  ldstr    aWhocanshareall// "WhoCanShareAllowListSettingPopulated"
0x65601  ldarg.s  0x36
0x65603  box      [mscorlib]System.Boolean
0x65608  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x6560d  ldloc.0
0x6560e  ldstr    aDomainrestrict// "DomainRestrictionModeProp"
0x65613  ldarg.s  0x37
0x65615  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x6561a  ldloc.0
0x6561b  ldstr    aOdbmemberscans// "ODBMembersCanShare"
0x65620  ldarg.s  0x38
0x65622  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65627  ldloc.0
0x65628  ldstr    aOdbaccessreque// "ODBAccessRequests"
0x6562d  ldarg.s  0x39
0x6562f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65634  ldloc.0
0x65635  ldstr    aBlockaccessonu// "BlockAccessOnUnmanagedDevices"
0x6563a  ldarg.s  0x3A
0x6563c  box      [mscorlib]System.Boolean
0x65641  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65646  ldloc.0
0x65647  ldstr    aLimitedaccesso// "LimitedAccessOnUnmanagedDevices"
0x6564c  ldarg.s  0x3B
0x6564e  box      [mscorlib]System.Boolean
0x65653  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x65658  ldloc.0
0x65659  ldstr    aViewonlyforblo// "ViewOnlyForBlockDownloadPolicy"
0x6565e  ldarg.s  0x3C
0x65660  box      [mscorlib]System.Boolean
0x65665  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x6566a  ldloc.0
0x6566b  ldstr    aFolderanonymou// "FolderAnonymousLinkPermission"
0x65670  ldarg.s  0x3D
  ... truncated ...
```
