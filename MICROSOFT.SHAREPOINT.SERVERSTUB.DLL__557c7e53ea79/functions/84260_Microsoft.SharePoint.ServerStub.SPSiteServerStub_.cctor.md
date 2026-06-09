# Microsoft.SharePoint.ServerStub.SPSiteServerStub::.cctor

- ea: `0x84260`
- end: `0x844ec`
- name: `Microsoft.SharePoint.ServerStub.SPSiteServerStub::.cctor`
- size: `652`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x842e0`: `CurrentChangeToken`
- `0x84382`: `ServerRelativePath`
- `0x8449f`: `ServerRelativePath`
- `0x84367`: `ReadOnly`
- `0x84355`: `ResourcePath`
- `0x8439d`: `ShareByLinkEnabled`
- `0x8426a`: `AllowCreateDeclarativeWorkflow`
- `0x8428a`: `AllowRevertFromTemplate`
- `0x84292`: `AllowSaveDeclarativeWorkflowAsTemplate`
- `0x842a2`: `AllowSelfServiceUpgrade`
- `0x842aa`: `AllowSelfServiceUpgradeEvaluation`
- `0x842ce`: `CommentsOnSitePagesDisabled`
- `0x84497`: `CommentsOnSitePagesDisabled`
- `0x842d7`: `CompatibilityLevel`
- `0x842f2`: `DisableCompanyWideSharingLinks`
- `0x8435e`: `PrimaryUri`
- `0x843b8`: `StatusBarLink`
- `0x844af`: `StatusBarLink`
- `0x843dc`: `UIVersionConfigurationEnabled`
- `0x843f7`: `UpgradeScheduled`
- `0x84400`: `UpgradeScheduledDate`

## pseudocode

```c

```

## disassembly

```asm
0x84260  ldc.i4.s 0x32
0x84262  newarr   [mscorlib]System.String
0x84267  stloc.0
0x84268  ldloc.0
0x84269  ldc.i4.0
0x8426a  ldstr    aAllowcreatedec// "AllowCreateDeclarativeWorkflow"
0x8426f  stelem.ref
0x84270  ldloc.0
0x84271  ldc.i4.1
0x84272  ldstr    aAllowdesigner// "AllowDesigner"
0x84277  stelem.ref
0x84278  ldloc.0
0x84279  ldc.i4.2
0x8427a  ldstr    aAllowexternale// "AllowExternalEmbeddingWrapper"
0x8427f  stelem.ref
0x84280  ldloc.0
0x84281  ldc.i4.3
0x84282  ldstr    aAllowmasterpag// "AllowMasterPageEditing"
0x84287  stelem.ref
0x84288  ldloc.0
0x84289  ldc.i4.4
0x8428a  ldstr    aAllowrevertfro// "AllowRevertFromTemplate"
0x8428f  stelem.ref
0x84290  ldloc.0
0x84291  ldc.i4.5
0x84292  ldstr    aAllowsavedecla// "AllowSaveDeclarativeWorkflowAsTemplate"
0x84297  stelem.ref
0x84298  ldloc.0
0x84299  ldc.i4.6
0x8429a  ldstr    aAllowsavepubli// "AllowSavePublishDeclarativeWorkflow"
0x8429f  stelem.ref
0x842a0  ldloc.0
0x842a1  ldc.i4.7
0x842a2  ldstr    aAllowselfservi// "AllowSelfServiceUpgrade"
0x842a7  stelem.ref
0x842a8  ldloc.0
0x842a9  ldc.i4.8
0x842aa  ldstr    aAllowselfservi_0// "AllowSelfServiceUpgradeEvaluation"
0x842af  stelem.ref
0x842b0  ldloc.0
0x842b1  ldc.i4.s 9
0x842b3  ldstr    aAuditlogtrimmi// "AuditLogTrimmingRetention"
0x842b8  stelem.ref
0x842b9  ldloc.0
0x842ba  ldc.i4.s 0xA
0x842bc  ldstr    aCanupgrade// "CanUpgrade"
0x842c1  stelem.ref
0x842c2  ldloc.0
0x842c3  ldc.i4.s 0xB
0x842c5  ldstr    aClassification// "Classification"
0x842ca  stelem.ref
0x842cb  ldloc.0
0x842cc  ldc.i4.s 0xC
0x842ce  ldstr    aCommentsonsite// "CommentsOnSitePagesDisabled"
0x842d3  stelem.ref
0x842d4  ldloc.0
0x842d5  ldc.i4.s 0xD
0x842d7  ldstr    aCompatibilityl_0// "CompatibilityLevel"
0x842dc  stelem.ref
0x842dd  ldloc.0
0x842de  ldc.i4.s 0xE
0x842e0  ldstr    aCurrentchanget// "CurrentChangeToken"
0x842e5  stelem.ref
0x842e6  ldloc.0
0x842e7  ldc.i4.s 0xF
0x842e9  ldstr    aDisableappview// "DisableAppViews"
0x842ee  stelem.ref
0x842ef  ldloc.0
0x842f0  ldc.i4.s 0x10
0x842f2  ldstr    aDisablecompany// "DisableCompanyWideSharingLinks"
0x842f7  stelem.ref
0x842f8  ldloc.0
0x842f9  ldc.i4.s 0x11
0x842fb  ldstr    aDisableflows// "DisableFlows"
0x84300  stelem.ref
0x84301  ldloc.0
0x84302  ldc.i4.s 0x12
0x84304  ldstr    aExternalsharin// "ExternalSharingTipsEnabled"
0x84309  stelem.ref
0x8430a  ldloc.0
0x8430b  ldc.i4.s 0x13
0x8430d  ldstr    aGeolocation// "GeoLocation"
0x84312  stelem.ref
0x84313  ldloc.0
0x84314  ldc.i4.s 0x14
0x84316  ldstr    aGroupid// "GroupId"
0x8431b  stelem.ref
0x8431c  ldloc.0
0x8431d  ldc.i4.s 0x15
0x8431f  ldstr    aHubsiteid_0// "HubSiteId"
0x84324  stelem.ref
0x84325  ldloc.0
0x84326  ldc.i4.s 0x16
0x84328  ldstr    aId_0// "Id"
0x8432d  stelem.ref
0x8432e  ldloc.0
0x8432f  ldc.i4.s 0x17
0x84331  ldstr    aIshubsite// "IsHubSite"
0x84336  stelem.ref
0x84337  ldloc.0
0x84338  ldc.i4.s 0x18
0x8433a  ldstr    aLockissue// "LockIssue"
0x8433f  stelem.ref
0x84340  ldloc.0
0x84341  ldc.i4.s 0x19
0x84343  ldstr    aMaxitemsperthr// "MaxItemsPerThrottledOperation"
0x84348  stelem.ref
0x84349  ldloc.0
0x8434a  ldc.i4.s 0x1A
0x8434c  ldstr    aNeedsb2bupgrad// "NeedsB2BUpgrade"
0x84351  stelem.ref
0x84352  ldloc.0
0x84353  ldc.i4.s 0x1B
0x84355  ldstr    aResourcepath// "ResourcePath"
0x8435a  stelem.ref
0x8435b  ldloc.0
0x8435c  ldc.i4.s 0x1C
0x8435e  ldstr    aPrimaryuri// "PrimaryUri"
0x84363  stelem.ref
0x84364  ldloc.0
0x84365  ldc.i4.s 0x1D
0x84367  ldstr    aReadonly// "ReadOnly"
0x8436c  stelem.ref
0x8436d  ldloc.0
0x8436e  ldc.i4.s 0x1E
0x84370  ldstr    aRequireddesign// "RequiredDesignerVersion"
0x84375  stelem.ref
0x84376  ldloc.0
0x84377  ldc.i4.s 0x1F
0x84379  ldstr    aSandboxedcodea// "SandboxedCodeActivationCapability"
0x8437e  stelem.ref
0x8437f  ldloc.0
0x84380  ldc.i4.s 0x20
0x84382  ldstr    aServerrelative_0// "ServerRelativePath"
0x84387  stelem.ref
0x84388  ldloc.0
0x84389  ldc.i4.s 0x21
0x8438b  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x84390  stelem.ref
0x84391  ldloc.0
0x84392  ldc.i4.s 0x22
0x84394  ldstr    aSharebyemailen// "ShareByEmailEnabled"
0x84399  stelem.ref
0x8439a  ldloc.0
0x8439b  ldc.i4.s 0x23
0x8439d  ldstr    aSharebylinkena// "ShareByLinkEnabled"
0x843a2  stelem.ref
0x843a3  ldloc.0
0x843a4  ldc.i4.s 0x24
0x843a6  ldstr    aShowpeoplepick// "ShowPeoplePickerSuggestionsForGuestUser"...
0x843ab  stelem.ref
0x843ac  ldloc.0
0x843ad  ldc.i4.s 0x25
0x843af  ldstr    aShowurlstructu// "ShowUrlStructure"
0x843b4  stelem.ref
0x843b5  ldloc.0
0x843b6  ldc.i4.s 0x26
0x843b8  ldstr    aStatusbarlink// "StatusBarLink"
0x843bd  stelem.ref
0x843be  ldloc.0
0x843bf  ldc.i4.s 0x27
0x843c1  ldstr    aStatusbartext// "StatusBarText"
0x843c6  stelem.ref
0x843c7  ldloc.0
0x843c8  ldc.i4.s 0x28
0x843ca  ldstr    aThicketsupport// "ThicketSupportDisabled"
0x843cf  stelem.ref
0x843d0  ldloc.0
0x843d1  ldc.i4.s 0x29
0x843d3  ldstr    aTrimauditlog// "TrimAuditLog"
0x843d8  stelem.ref
0x843d9  ldloc.0
0x843da  ldc.i4.s 0x2A
0x843dc  ldstr    aUiversionconfi// "UIVersionConfigurationEnabled"
0x843e1  stelem.ref
0x843e2  ldloc.0
0x843e3  ldc.i4.s 0x2B
0x843e5  ldstr    aUpgradeinfo// "UpgradeInfo"
0x843ea  stelem.ref
0x843eb  ldloc.0
0x843ec  ldc.i4.s 0x2C
0x843ee  ldstr    aUpgradereminde// "UpgradeReminderDate"
0x843f3  stelem.ref
0x843f4  ldloc.0
0x843f5  ldc.i4.s 0x2D
0x843f7  ldstr    aUpgradeschedul// "UpgradeScheduled"
0x843fc  stelem.ref
0x843fd  ldloc.0
0x843fe  ldc.i4.s 0x2E
0x84400  ldstr    aUpgradeschedul_0// "UpgradeScheduledDate"
0x84405  stelem.ref
0x84406  ldloc.0
0x84407  ldc.i4.s 0x2F
0x84409  ldstr    aUpgrading// "Upgrading"
0x8440e  stelem.ref
0x8440f  ldloc.0
0x84410  ldc.i4.s 0x30
0x84412  ldstr    aUrl// "Url"
0x84417  stelem.ref
0x84418  ldloc.0
0x84419  ldc.i4.s 0x31
0x8441b  ldstr    aUsage// "Usage"
0x84420  stelem.ref
0x84421  ldloc.0
0x84422  stsfld   string[] Microsoft.SharePoint.ServerStub.SPSiteServerStub::s_valueProperties
0x84427  ldc.i4.s 9
0x84429  newarr   [mscorlib]System.String
0x8442e  stloc.1
0x8442f  ldloc.1
0x84430  ldc.i4.0
0x84431  ldstr    aAudit// "Audit"
0x84436  stelem.ref
0x84437  ldloc.1
0x84438  ldc.i4.1
0x84439  ldstr    aCustomscriptsa// "CustomScriptSafeDomains"
0x8443e  stelem.ref
0x8443f  ldloc.1
0x84440  ldc.i4.2
0x84441  ldstr    aEventreceivers// "EventReceivers"
0x84446  stelem.ref
0x84447  ldloc.1
0x84448  ldc.i4.3
0x84449  ldstr    aFeatures// "Features"
0x8444e  stelem.ref
0x8444f  ldloc.1
0x84450  ldc.i4.4
0x84451  ldstr    aOwner// "Owner"
0x84456  stelem.ref
0x84457  ldloc.1
0x84458  ldc.i4.5
0x84459  ldstr    aRecyclebin// "RecycleBin"
0x8445e  stelem.ref
0x8445f  ldloc.1
0x84460  ldc.i4.6
0x84461  ldstr    aRootweb// "RootWeb"
0x84466  stelem.ref
0x84467  ldloc.1
0x84468  ldc.i4.7
0x84469  ldstr    aSecondaryconta// "SecondaryContact"
0x8446e  stelem.ref
0x8446f  ldloc.1
0x84470  ldc.i4.8
0x84471  ldstr    aUsercustomacti// "UserCustomActions"
0x84476  stelem.ref
0x84477  ldloc.1
0x84478  stsfld   string[] Microsoft.SharePoint.ServerStub.SPSiteServerStub::s_refProperties
0x8447d  ldc.i4.s 0xA
0x8447f  newarr   [mscorlib]System.String
0x84484  stloc.2
0x84485  ldloc.2
0x84486  ldc.i4.0
0x84487  ldstr    aAllowexternale// "AllowExternalEmbeddingWrapper"
0x8448c  stelem.ref
0x8448d  ldloc.2
0x8448e  ldc.i4.1
0x8448f  ldstr    aCanupgrade// "CanUpgrade"
0x84494  stelem.ref
0x84495  ldloc.2
0x84496  ldc.i4.2
0x84497  ldstr    aCommentsonsite// "CommentsOnSitePagesDisabled"
0x8449c  stelem.ref
0x8449d  ldloc.2
0x8449e  ldc.i4.3
0x8449f  ldstr    aServerrelative_0// "ServerRelativePath"
0x844a4  stelem.ref
0x844a5  ldloc.2
0x844a6  ldc.i4.4
0x844a7  ldstr    aShowpeoplepick// "ShowPeoplePickerSuggestionsForGuestUser"...
0x844ac  stelem.ref
0x844ad  ldloc.2
0x844ae  ldc.i4.5
0x844af  ldstr    aStatusbarlink// "StatusBarLink"
0x844b4  stelem.ref
0x844b5  ldloc.2
0x844b6  ldc.i4.6
0x844b7  ldstr    aStatusbartext// "StatusBarText"
0x844bc  stelem.ref
0x844bd  ldloc.2
0x844be  ldc.i4.7
0x844bf  ldstr    aThicketsupport// "ThicketSupportDisabled"
0x844c4  stelem.ref
0x844c5  ldloc.2
0x844c6  ldc.i4.8
0x844c7  ldstr    aUpgradeinfo// "UpgradeInfo"
0x844cc  stelem.ref
0x844cd  ldloc.2
0x844ce  ldc.i4.s 9
0x844d0  ldstr    aUsage// "Usage"
0x844d5  stelem.ref
0x844d6  ldloc.2
0x844d7  stsfld   string[] Microsoft.SharePoint.ServerStub.SPSiteServerStub::s_excludeFromDefaultRetrieveProperties
0x844dc  ldstr    aE1bb82e80d1e4e// "{e1bb82e8-0d1e-4e52-b90c-684802ab4ef6}"
0x844e1  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x844e6  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ServerStub.SPSiteServerStub::s_targetTypeId
0x844eb  ret
```
