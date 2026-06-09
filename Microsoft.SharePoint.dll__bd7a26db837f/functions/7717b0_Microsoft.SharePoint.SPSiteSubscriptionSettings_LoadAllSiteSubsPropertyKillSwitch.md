# Microsoft.SharePoint.SPSiteSubscriptionSettings::LoadAllSiteSubsPropertyKillSwitch

- ea: `0x7717b0`
- end: `0x77229a`
- name: `Microsoft.SharePoint.SPSiteSubscriptionSettings::LoadAllSiteSubsPropertyKillSwitch`
- size: `2794`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x7722c0`

## string_xrefs

- `0x771d9e`: `InfoPath_AllowUserFormBrowser_Enabling`
- `0x771d89`: `InfoPath_AllowUserFormBrowser_Rendering`
- `0x771db3`: `InfoPath_ExemptUserAgents_Customize`
- `0x771be5`: `DefaultSharingLinkType`
- `0x771ba6`: `ODBAccessRequests`
- `0x771bfa`: `FolderAnonymousLinkPermission`
- `0x771c0f`: `FileAnonymousLinkPermission`
- `0x771834`: `UserAccountDirectoryPath`
- `0x7719c3`: `ExternalService_ExchangeOnlineDomain`
- `0x771999`: `ExchangeSiteMailboxOWATemplate`
- `0x7719ed`: `ExternalService_ExchangeSiteMailboxOWATemplate`
- `0x771984`: `ExchangeSiteMailboxECPTemplate`
- `0x7719d8`: `ExternalService_ExchangeSiteMailboxECPTemplate`
- `0x77220c`: `ClientSideAppUpdateTime`
- `0x771aaa`: `ExternalSharingHelpLink`
- `0x771b3d`: `IPAddressWACTokenLifetime`
- `0x771ccc`: `RequireAnonymousLinksExpireInDays`
- `0x772110`: `AnonymousLinksExpirationModifiedDate`
- `0x771fc0`: `SSCShowNewGroupManagedPath`
- `0x7717cb`: `CompatRangeKey`
- `0x771888`: `ExternServicesOff`
- `0x771e1c`: `CtrlCreateMode`
- `0x771e46`: `WorkflowServiceAddress`
- `0x771e5b`: `WorkflowServiceAccessControlUri`
- `0x771e70`: `WorkflowServiceSecurityIssuerName`
- `0x771e85`: `WorkflowServiceSecurityIssuerToken`
- `0x771e9a`: `WorkflowServicePrincipalName`
- `0x771ed9`: `SecurityState`
- `0x771fd5`: `NoAccessRedirectUrl`
- `0x7720a7`: `CloudVideoServiceUrl`
- `0x7720bc`: `CloudVideoServiceAccountId`
- `0x7720d1`: `HasPointPublishingCommunitySiteBeenCreatedProperty`
- `0x772164`: `PublicCdnAllowedExtensions`
- `0x772179`: `SdnHiveConfiguration`
- `0x772221`: `GoldenLoopEnabled`
- `0x772275`: `ReadyForBringYourOwnKey`

## pseudocode

```c

```

## disassembly

```asm
0x7717b0  ldarg.0
0x7717b1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x7717b6  ldstr    aBsqmenabled// "BSqmEnabled"
0x7717bb  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::BSqmEnabledPropertyKillSwitchGuid
0x7717c0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x7717c5  ldarg.0
0x7717c6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x7717cb  ldstr    aCompatrangekey// "CompatRangeKey"
0x7717d0  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::CompatRangeKeyPropertyKillSwitchGuid
0x7717d5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x7717da  ldarg.0
0x7717db  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x7717e0  ldstr    aMsSpAuthrealm// "MS.SP.AuthRealm"
0x7717e5  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::MSSPAuthRealmPropertyKillSwitchGuid
0x7717ea  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x7717ef  ldarg.0
0x7717f0  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x7717f5  ldstr    aPortalurl// "PortalUrl"
0x7717fa  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::PortalUrlPropertyKillSwitchGuid
0x7717ff  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771804  ldarg.0
0x771805  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x77180a  ldstr    aTenantadminist// "TenantAdministrationSiteId"
0x77180f  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::TenantAdministrationSiteIdPropertyKillSwitchGuid
0x771814  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771819  ldarg.0
0x77181a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x77181f  ldstr    aTenantlicenses// "TenantLicenses"
0x771824  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::TenantLicensesPropertyKillSwitchGuid
0x771829  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x77182e  ldarg.0
0x77182f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771834  ldstr    aUseraccountdir// "UserAccountDirectoryPath"
0x771839  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::UserAccountDirectoryPathPropertyKillSwitchGuid
0x77183e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771843  ldarg.0
0x771844  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771849  ldstr    aSitepagesenabl// "SitePagesEnabled"
0x77184e  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::SitePagesPropertyKillSwitchGuid
0x771853  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771858  ldarg.0
0x771859  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x77185e  ldstr    aTenantpreview// "TenantPreview"
0x771863  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::TenantPreviewPropertyKillSwitchGuid
0x771868  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x77186d  ldarg.0
0x77186e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771873  ldstr    aIpaddressenfor// "IPAddressEnforcement"
0x771878  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::IPAddressEnforcementPropertyKillSwitchGuid
0x77187d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771882  ldarg.0
0x771883  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771888  ldstr    aExternservices// "ExternServicesOff"
0x77188d  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::ExternServicesOffPropertyKillSwitchGuid
0x771892  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771897  ldarg.0
0x771898  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x77189d  ldstr    aSiteprefixshar// "SitePrefixSharingMap"
0x7718a2  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::SitePrefixSharingMapPropertyKillSwitchGuid
0x7718a7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x7718ac  ldarg.0
0x7718ad  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x7718b2  ldstr    aCollaborationt// "CollaborationTypeKey"
0x7718b7  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::CollaborationTypeKeyPropertyKillSwitchGuid
0x7718bc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x7718c1  ldarg.0
0x7718c2  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x7718c7  ldstr    aAllowstoreoe// "__AllowStoreOE"
0x7718cc  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::__AllowStoreOEPropertyKillSwitchGuid
0x7718d1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x7718d6  ldarg.0
0x7718d7  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x7718dc  ldstr    aSscparenturl// "SSCParentUrl"
0x7718e1  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::SSCParentUrlPropertyKillSwitchGuid
0x7718e6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x7718eb  ldarg.0
0x7718ec  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x7718f1  ldstr    aSiteprefixnoac// "SitePrefixNoACPMap"
0x7718f6  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::SitePrefixNoACPMapPropertyKillSwitchGuid
0x7718fb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771900  ldarg.0
0x771901  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771906  ldstr    aPolicycenterur// "PolicyCenterUrl"
0x77190b  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::PolicyCenterUrlPropertyKillSwitchGuid
0x771910  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771915  ldarg.0
0x771916  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x77191b  ldstr    aMsotenantid// "MsoTenantId"
0x771920  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::MsoTenantIdPropertyKillSwitchGuid
0x771925  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x77192a  ldarg.0
0x77192b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771930  ldstr    aIshybridunifie// "IsHybridUnifiedPolicyEnabled"
0x771935  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::IsHybridUnifiedPolicyEnabledPropertyKillSwitchGuid
0x77193a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x77193f  ldarg.0
0x771940  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771945  ldstr    aOauthrealm// "OAuthRealm"
0x77194a  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::OAuthRealmPropertyKillSwitchGuid
0x77194f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771954  ldarg.0
0x771955  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x77195a  ldstr    aExchangesitema// "ExchangeSiteMailboxEnableAutodiscover"
0x77195f  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::ExchangeSiteMailboxEnableAutodiscoverPropertyKillSwitchGuid
0x771964  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771969  ldarg.0
0x77196a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x77196f  ldstr    aExchangeautodi// "ExchangeAutodiscoverDomain"
0x771974  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::ExchangeAutodiscoverDomainPropertyKillSwitchGuid
0x771979  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x77197e  ldarg.0
0x77197f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771984  ldstr    aExchangesitema_1// "ExchangeSiteMailboxECPTemplate"
0x771989  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::ExchangeSiteMailboxECPTemplatePropertyKillSwitchGuid
0x77198e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771993  ldarg.0
0x771994  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771999  ldstr    aExchangesitema_0// "ExchangeSiteMailboxOWATemplate"
0x77199e  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::ExchangeSiteMailboxOWATemplatePropertyKillSwitchGuid
0x7719a3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x7719a8  ldarg.0
0x7719a9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x7719ae  ldstr    aExchangeteamma// "ExchangeTeamMailboxDomain"
0x7719b3  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::ExchangeTeamMailboxDomainPropertyKillSwitchGuid
0x7719b8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x7719bd  ldarg.0
0x7719be  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x7719c3  ldstr    aExternalservic// "ExternalService_ExchangeOnlineDomain"
0x7719c8  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::ExternalService_ExchangeOnlineDomainPropertyKillSwitchGuid
0x7719cd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x7719d2  ldarg.0
0x7719d3  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x7719d8  ldstr    aExternalservic_1// "ExternalService_ExchangeSiteMailboxECPT"...
0x7719dd  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::ExternalService_ExchangeSiteMailboxECPTemplatePropertyKillSwitchGuid
0x7719e2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x7719e7  ldarg.0
0x7719e8  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x7719ed  ldstr    aExternalservic_0// "ExternalService_ExchangeSiteMailboxOWAT"...
0x7719f2  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::ExternalService_ExchangeSiteMailboxOWATemplatePropertyKillSwitchGuid
0x7719f7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x7719fc  ldarg.0
0x7719fd  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771a02  ldstr    aExchangeteamma_0// "ExchangeTeamMailboxEmailAddress"
0x771a07  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::ExchangeTeamMailboxEmailAddressPropertyKillSwitchGuid
0x771a0c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771a11  ldarg.0
0x771a12  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771a17  ldstr    aExchangeteamma_1// "ExchangeTeamMailboxSiteCollectionUrl"
0x771a1c  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::ExchangeTeamMailboxSiteCollectionUrlPropertyKillSwitchGuid
0x771a21  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771a26  ldarg.0
0x771a27  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771a2c  ldstr    aExchangeteamma_2// "ExchangeTeamMailboxSiteID"
0x771a31  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::ExchangeTeamMailboxSiteIDPropertyKillSwitchGuid
0x771a36  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771a3b  ldarg.0
0x771a3c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771a41  ldstr    aExchangeteamma_3// "ExchangeTeamMailboxOWAUrl"
0x771a46  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::ExchangeTeamMailboxOWAUrlPropertyKillSwitchGuid
0x771a4b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771a50  ldarg.0
0x771a51  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771a56  ldstr    aSharingeverena// "SharingEverEnabled"
0x771a5b  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::SharingEverEnabledPropertyKillSwitchGuid
0x771a60  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771a65  ldarg.0
0x771a66  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771a6b  ldstr    aGuestsharingen// "GuestSharingEnabled"
0x771a70  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::GuestSharingEnabledPropertyKillSwitchGuid
0x771a75  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771a7a  ldarg.0
0x771a7b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771a80  ldstr    aShowexternalsh// "ShowExternalSharingWarning"
0x771a85  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::ShowExternalSharingWarningPropertyKillSwitchGuid
0x771a8a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771a8f  ldarg.0
0x771a90  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771a95  ldstr    aShowexternalsh_0// "ShowExternalSharingTips"
0x771a9a  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::ShowExternalSharingTipsPropertyKillSwitchGuid
0x771a9f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771aa4  ldarg.0
0x771aa5  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771aaa  ldstr    aExternalsharin_2// "ExternalSharingHelpLink"
0x771aaf  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::ExternalSharingHelpLinkPropertyKillSwitchGuid
0x771ab4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771ab9  ldarg.0
0x771aba  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771abf  ldstr    aAlluserclaimen// "AllUserClaimEnabled"
0x771ac4  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::AllUserClaimEnabledPropertyKillSwitchGuid
0x771ac9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771ace  ldarg.0
0x771acf  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771ad4  ldstr    aEveryoneclaime// "EveryoneClaimEnabled"
0x771ad9  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::EveryoneClaimEnabledPropertyKillSwitchGuid
0x771ade  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771ae3  ldarg.0
0x771ae4  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771ae9  ldstr    aOfficeclientad// "OfficeClientADALDisabled"
0x771aee  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::OfficeClientADALDisabledPropertyKillSwitchGuid
0x771af3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771af8  ldarg.0
0x771af9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771afe  ldstr    aDutyofcarepeop// "DutyOfCarePeoplePicker"
0x771b03  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::DutyOfCarePeoplePickerPropertyKillSwitchGuid
0x771b08  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771b0d  ldarg.0
0x771b0e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771b13  ldstr    aSpoBlockmsofba// "SPO-BlockMsoFbaAndIdcrlChallenges"
0x771b18  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::BlockMsoFbaAndIdcrlChallengesPropertyKillSwitchGuid
0x771b1d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771b22  ldarg.0
0x771b23  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771b28  ldstr    aIpaddressallow// "IPAddressAllowList"
0x771b2d  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::IPAddressAllowListPropertyKillSwitchGuid
0x771b32  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771b37  ldarg.0
0x771b38  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771b3d  ldstr    aIpaddresswacto// "IPAddressWACTokenLifetime"
0x771b42  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::IPAddressWACTokenLifetimePropertyKillSwitchGuid
0x771b47  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771b4c  ldarg.0
0x771b4d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771b52  ldstr    aShowpeoplepick// "ShowPeoplePickerSuggestionsForGuestUser"...
0x771b57  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::ShowPeoplePickerSuggestionsForGuestUsersPropertyKillSwitchGuid
0x771b5c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771b61  ldarg.0
0x771b62  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771b67  ldstr    aEveryoneexcept// "EveryoneExceptExternalClaimEnabled"
0x771b6c  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::EveryoneExceptExternalClaimEnabledPropertyKillSwitchGuid
0x771b71  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771b76  ldarg.0
0x771b77  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771b7c  ldstr    aPreventexterna// "PreventExternalUsersFromResharing"
0x771b81  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::PreventExternalUsersFromResharingPropertyKillSwitchGuid
0x771b86  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771b8b  ldarg.0
0x771b8c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771b91  ldstr    aOdbmemberscans// "ODBMembersCanShare"
0x771b96  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::ODBMembersCanSharePropertyKillSwitchGuid
0x771b9b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771ba0  ldarg.0
0x771ba1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771ba6  ldstr    aOdbaccessreque// "ODBAccessRequests"
0x771bab  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::ODBAccessRequestsPropertyKillSwitchGuid
0x771bb0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771bb5  ldarg.0
0x771bb6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771bbb  ldstr    aRequireaccepti// "RequireAcceptingAccountMatchInvitedAcco"...
0x771bc0  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::RequireAcceptingAccountMatchInvitedAccountPropertyKillSwitchGuid
0x771bc5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771bca  ldarg.0
0x771bcb  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771bd0  ldstr    aProvisionshare// "ProvisionSharedWithEveryoneFolder"
0x771bd5  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::ProvisionSharedWithEveryoneFolderPropertyKillSwitchGuid
0x771bda  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771bdf  ldarg.0
0x771be0  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771be5  ldstr    aDefaultsharing// "DefaultSharingLinkType"
0x771bea  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::DefaultSharingLinkTypePropertyKillSwitchGuid
0x771bef  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771bf4  ldarg.0
0x771bf5  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771bfa  ldstr    aFolderanonymou// "FolderAnonymousLinkPermission"
0x771bff  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::FolderAnonymousLinkPermissionPropertyKillSwitchGuid
0x771c04  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771c09  ldarg.0
0x771c0a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771c0f  ldstr    aFileanonymousl// "FileAnonymousLinkPermission"
0x771c14  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::FileAnonymousLinkPermissionPropertyKillSwitchGuid
0x771c19  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771c1e  ldarg.0
0x771c1f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771c24  ldstr    aWhocanshareall_0// "WhoCanShareAllowList"
0x771c29  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::WhoCanShareAllowListPropertyKillSwitchGuid
0x771c2e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771c33  ldarg.0
0x771c34  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771c39  ldstr    aOwnernotificat// "OwnerNotificationReshare"
0x771c3e  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::OwnerNotificationResharePropertyKillSwitchGuid
0x771c43  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771c48  ldarg.0
0x771c49  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771c4e  ldstr    aOwnernotificat_0// "OwnerNotificationAccept"
0x771c53  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::OwnerNotificationAcceptPropertyKillSwitchGuid
0x771c58  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771c5d  ldarg.0
0x771c5e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771c63  ldstr    aTenantwhrvalue_0// "TenantWhrValue"
0x771c68  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::TenantWhrValuePropertyKillSwitchGuid
0x771c6d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771c72  ldarg.0
0x771c73  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771c78  ldstr    aEnableguestsig// "EnableGuestSignInAcceleration"
0x771c7d  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::EnableGuestSignInAccelerationPropertyKillSwitchGuid
0x771c82  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x771c87  ldarg.0
0x771c88  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSiteSubscriptionSettings::m_PropertyKillSwitchDictionary
0x771c8d  ldstr    aTenantenablewe// "TenantEnableWebDavCookieIssuance"
0x771c92  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionSettings::TenantEnableWebDavCookieIssuancePropertyKillSwitchGuid
0x771c97  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
  ... truncated ...
```
