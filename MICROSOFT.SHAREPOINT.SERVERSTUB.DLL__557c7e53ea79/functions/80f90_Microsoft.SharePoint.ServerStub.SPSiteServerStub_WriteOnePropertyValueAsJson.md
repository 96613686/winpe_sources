# Microsoft.SharePoint.ServerStub.SPSiteServerStub::WriteOnePropertyValueAsJson

- ea: `0x80f90`
- end: `0x82524`
- name: `Microsoft.SharePoint.ServerStub.SPSiteServerStub::WriteOnePropertyValueAsJson`
- size: `5524`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x80f90`

## string_xrefs

- `0x81082`: `CurrentChangeToken`
- `0x81855`: `CurrentChangeToken`
- `0x811c7`: `ServerRelativePath`
- `0x81fc0`: `ServerRelativePath`
- `0x81179`: `ReadOnly`
- `0x81def`: `ReadOnly`
- `0x8115f`: `ResourcePath`
- `0x81d5b`: `ResourcePath`
- `0x811ee`: `ShareByLinkEnabled`
- `0x8209e`: `ShareByLinkEnabled`
- `0x80fc8`: `AllowCreateDeclarativeWorkflow`
- `0x813f8`: `AllowCreateDeclarativeWorkflow`
- `0x80ff8`: `AllowRevertFromTemplate`
- `0x81520`: `AllowRevertFromTemplate`
- `0x81004`: `AllowSaveDeclarativeWorkflowAsTemplate`
- `0x8156a`: `AllowSaveDeclarativeWorkflowAsTemplate`
- `0x8101c`: `AllowSelfServiceUpgrade`
- `0x815fe`: `AllowSelfServiceUpgrade`
- `0x81028`: `AllowSelfServiceUpgradeEvaluation`
- `0x81648`: `AllowSelfServiceUpgradeEvaluation`
- `0x81068`: `CommentsOnSitePagesDisabled`
- `0x817c1`: `CommentsOnSitePagesDisabled`
- `0x81075`: `CompatibilityLevel`
- `0x8180b`: `CompatibilityLevel`
- `0x810a9`: `DisableCompanyWideSharingLinks`
- `0x8193a`: `DisableCompanyWideSharingLinks`
- `0x8116c`: `PrimaryUri`
- `0x81da5`: `PrimaryUri`
- `0x81215`: `StatusBarLink`
- `0x8217c`: `StatusBarLink`
- `0x81249`: `UIVersionConfigurationEnabled`
- `0x822a4`: `UIVersionConfigurationEnabled`
- `0x81270`: `UpgradeScheduled`
- `0x82382`: `UpgradeScheduled`
- `0x8127d`: `UpgradeScheduledDate`
- `0x823cc`: `UpgradeScheduledDate`

## pseudocode

```c

```

## disassembly

```asm
0x80f90  ldc.i4.0
0x80f91  stloc.0
0x80f92  ldarg.2
0x80f93  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPSite
0x80f98  stloc.1
0x80f99  ldloc.1
0x80f9a  brtrue.s loc_80FA7
0x80f9c  ldstr    aTarget// "target"
0x80fa1  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x80fa6  throw
0x80fa7  ldarg.3
0x80fa8  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x80fad  dup
0x80fae  stloc.2
0x80faf  brfalse  loc_82516
0x80fb4  volatile.
0x80fb6  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60015b5-1
0x80fbb  brtrue   loc_812C4
0x80fc0  ldc.i4.s 0x3B
0x80fc2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x80fc7  dup
0x80fc8  ldstr    aAllowcreatedec// "AllowCreateDeclarativeWorkflow"
0x80fcd  ldc.i4.0
0x80fce  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80fd3  dup
0x80fd4  ldstr    aAllowdesigner// "AllowDesigner"
0x80fd9  ldc.i4.1
0x80fda  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80fdf  dup
0x80fe0  ldstr    aAllowexternale// "AllowExternalEmbeddingWrapper"
0x80fe5  ldc.i4.2
0x80fe6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80feb  dup
0x80fec  ldstr    aAllowmasterpag// "AllowMasterPageEditing"
0x80ff1  ldc.i4.3
0x80ff2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80ff7  dup
0x80ff8  ldstr    aAllowrevertfro// "AllowRevertFromTemplate"
0x80ffd  ldc.i4.4
0x80ffe  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81003  dup
0x81004  ldstr    aAllowsavedecla// "AllowSaveDeclarativeWorkflowAsTemplate"
0x81009  ldc.i4.5
0x8100a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8100f  dup
0x81010  ldstr    aAllowsavepubli// "AllowSavePublishDeclarativeWorkflow"
0x81015  ldc.i4.6
0x81016  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8101b  dup
0x8101c  ldstr    aAllowselfservi// "AllowSelfServiceUpgrade"
0x81021  ldc.i4.7
0x81022  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81027  dup
0x81028  ldstr    aAllowselfservi_0// "AllowSelfServiceUpgradeEvaluation"
0x8102d  ldc.i4.8
0x8102e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81033  dup
0x81034  ldstr    aAudit// "Audit"
0x81039  ldc.i4.s 9
0x8103b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81040  dup
0x81041  ldstr    aAuditlogtrimmi// "AuditLogTrimmingRetention"
0x81046  ldc.i4.s 0xA
0x81048  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8104d  dup
0x8104e  ldstr    aCanupgrade// "CanUpgrade"
0x81053  ldc.i4.s 0xB
0x81055  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8105a  dup
0x8105b  ldstr    aClassification// "Classification"
0x81060  ldc.i4.s 0xC
0x81062  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81067  dup
0x81068  ldstr    aCommentsonsite// "CommentsOnSitePagesDisabled"
0x8106d  ldc.i4.s 0xD
0x8106f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81074  dup
0x81075  ldstr    aCompatibilityl_0// "CompatibilityLevel"
0x8107a  ldc.i4.s 0xE
0x8107c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81081  dup
0x81082  ldstr    aCurrentchanget// "CurrentChangeToken"
0x81087  ldc.i4.s 0xF
0x81089  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8108e  dup
0x8108f  ldstr    aCustomscriptsa// "CustomScriptSafeDomains"
0x81094  ldc.i4.s 0x10
0x81096  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8109b  dup
0x8109c  ldstr    aDisableappview// "DisableAppViews"
0x810a1  ldc.i4.s 0x11
0x810a3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x810a8  dup
0x810a9  ldstr    aDisablecompany// "DisableCompanyWideSharingLinks"
0x810ae  ldc.i4.s 0x12
0x810b0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x810b5  dup
0x810b6  ldstr    aDisableflows// "DisableFlows"
0x810bb  ldc.i4.s 0x13
0x810bd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x810c2  dup
0x810c3  ldstr    aEventreceivers// "EventReceivers"
0x810c8  ldc.i4.s 0x14
0x810ca  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x810cf  dup
0x810d0  ldstr    aExternalsharin// "ExternalSharingTipsEnabled"
0x810d5  ldc.i4.s 0x15
0x810d7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x810dc  dup
0x810dd  ldstr    aFeatures// "Features"
0x810e2  ldc.i4.s 0x16
0x810e4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x810e9  dup
0x810ea  ldstr    aGeolocation// "GeoLocation"
0x810ef  ldc.i4.s 0x17
0x810f1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x810f6  dup
0x810f7  ldstr    aGroupid// "GroupId"
0x810fc  ldc.i4.s 0x18
0x810fe  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81103  dup
0x81104  ldstr    aHubsiteid_0// "HubSiteId"
0x81109  ldc.i4.s 0x19
0x8110b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81110  dup
0x81111  ldstr    aId_0// "Id"
0x81116  ldc.i4.s 0x1A
0x81118  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8111d  dup
0x8111e  ldstr    aIshubsite// "IsHubSite"
0x81123  ldc.i4.s 0x1B
0x81125  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8112a  dup
0x8112b  ldstr    aLockissue// "LockIssue"
0x81130  ldc.i4.s 0x1C
0x81132  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81137  dup
0x81138  ldstr    aMaxitemsperthr// "MaxItemsPerThrottledOperation"
0x8113d  ldc.i4.s 0x1D
0x8113f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81144  dup
0x81145  ldstr    aNeedsb2bupgrad// "NeedsB2BUpgrade"
0x8114a  ldc.i4.s 0x1E
0x8114c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81151  dup
0x81152  ldstr    aOwner// "Owner"
0x81157  ldc.i4.s 0x1F
0x81159  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8115e  dup
0x8115f  ldstr    aResourcepath// "ResourcePath"
0x81164  ldc.i4.s 0x20
0x81166  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8116b  dup
0x8116c  ldstr    aPrimaryuri// "PrimaryUri"
0x81171  ldc.i4.s 0x21
0x81173  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81178  dup
0x81179  ldstr    aReadonly// "ReadOnly"
0x8117e  ldc.i4.s 0x22
0x81180  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81185  dup
0x81186  ldstr    aRecyclebin// "RecycleBin"
0x8118b  ldc.i4.s 0x23
0x8118d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81192  dup
0x81193  ldstr    aRequireddesign// "RequiredDesignerVersion"
0x81198  ldc.i4.s 0x24
0x8119a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8119f  dup
0x811a0  ldstr    aRootweb// "RootWeb"
0x811a5  ldc.i4.s 0x25
0x811a7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x811ac  dup
0x811ad  ldstr    aSandboxedcodea// "SandboxedCodeActivationCapability"
0x811b2  ldc.i4.s 0x26
0x811b4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x811b9  dup
0x811ba  ldstr    aSecondaryconta// "SecondaryContact"
0x811bf  ldc.i4.s 0x27
0x811c1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x811c6  dup
0x811c7  ldstr    aServerrelative_0// "ServerRelativePath"
0x811cc  ldc.i4.s 0x28
0x811ce  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x811d3  dup
0x811d4  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x811d9  ldc.i4.s 0x29
0x811db  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x811e0  dup
0x811e1  ldstr    aSharebyemailen// "ShareByEmailEnabled"
0x811e6  ldc.i4.s 0x2A
0x811e8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x811ed  dup
0x811ee  ldstr    aSharebylinkena// "ShareByLinkEnabled"
0x811f3  ldc.i4.s 0x2B
0x811f5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x811fa  dup
0x811fb  ldstr    aShowpeoplepick// "ShowPeoplePickerSuggestionsForGuestUser"...
0x81200  ldc.i4.s 0x2C
0x81202  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81207  dup
0x81208  ldstr    aShowurlstructu// "ShowUrlStructure"
0x8120d  ldc.i4.s 0x2D
0x8120f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81214  dup
0x81215  ldstr    aStatusbarlink// "StatusBarLink"
0x8121a  ldc.i4.s 0x2E
0x8121c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81221  dup
0x81222  ldstr    aStatusbartext// "StatusBarText"
0x81227  ldc.i4.s 0x2F
0x81229  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8122e  dup
0x8122f  ldstr    aThicketsupport// "ThicketSupportDisabled"
0x81234  ldc.i4.s 0x30
0x81236  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8123b  dup
0x8123c  ldstr    aTrimauditlog// "TrimAuditLog"
0x81241  ldc.i4.s 0x31
0x81243  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81248  dup
0x81249  ldstr    aUiversionconfi// "UIVersionConfigurationEnabled"
0x8124e  ldc.i4.s 0x32
0x81250  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81255  dup
0x81256  ldstr    aUpgradeinfo// "UpgradeInfo"
0x8125b  ldc.i4.s 0x33
0x8125d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81262  dup
0x81263  ldstr    aUpgradereminde// "UpgradeReminderDate"
0x81268  ldc.i4.s 0x34
0x8126a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8126f  dup
0x81270  ldstr    aUpgradeschedul// "UpgradeScheduled"
0x81275  ldc.i4.s 0x35
0x81277  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8127c  dup
0x8127d  ldstr    aUpgradeschedul_0// "UpgradeScheduledDate"
0x81282  ldc.i4.s 0x36
0x81284  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81289  dup
0x8128a  ldstr    aUpgrading// "Upgrading"
0x8128f  ldc.i4.s 0x37
0x81291  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x81296  dup
0x81297  ldstr    aUrl// "Url"
0x8129c  ldc.i4.s 0x38
0x8129e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x812a3  dup
0x812a4  ldstr    aUsage// "Usage"
0x812a9  ldc.i4.s 0x39
0x812ab  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x812b0  dup
0x812b1  ldstr    aUsercustomacti// "UserCustomActions"
0x812b6  ldc.i4.s 0x3A
0x812b8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x812bd  volatile.
0x812bf  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60015b5-1
0x812c4  volatile.
0x812c6  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60015b5-1
0x812cb  ldloc.2
0x812cc  ldloca.s 3
0x812ce  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x812d3  brfalse  loc_82516
0x812d8  ldloc.3
0x812d9  switch   loc_813CF, loc_81419, loc_81463, loc_814AD, loc_814F7, loc_81541, loc_8158B, loc_815D5, loc_8161F, loc_81669, loc_816BA, loc_81704, loc_8174E, loc_81798, loc_817E2, loc_8182C, loc_81876, loc_818C7, loc_81911, loc_8195B, loc_819A5, loc_819F6, loc_81A40, loc_81A91, loc_81ADB, loc_81B25, loc_81B6F, loc_81BB9, loc_81C03, loc_81C4D, loc_81C97, loc_81CE1, loc_81D32, loc_81D7C, loc_81DC6, loc_81E10, loc_81E61, loc_81EAB, loc_81EFC, loc_81F46, loc_81F97, loc_81FE1, loc_8202B, loc_82075, loc_820BF, loc_82109, loc_82153, loc_8219D, loc_821E7, loc_82231, loc_8227B, loc_822C5, loc_8230F, loc_82359, loc_823A3 \
0x813ca  br       loc_82516
0x813cf  ldarg.3
0x813d0  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x813d5  stloc.s  4
0x813d7  ldloca.s 4
0x813d9  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x813de  brfalse.s loc_813F7
0x813e0  ldarg.3
0x813e1  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x813e6  stloc.s  5
0x813e8  ldloca.s 5
0x813ea  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x813ef  brtrue.s loc_813F7
0x813f1  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x813f6  throw
0x813f7  ldarg.0
0x813f8  ldstr    aAllowcreatedec// "AllowCreateDeclarativeWorkflow"
0x813fd  ldarg.s  4
0x813ff  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x81404  ldc.i4.1
0x81405  stloc.0
0x81406  ldarg.1
0x81407  ldloc.1
0x81408  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_AllowCreateDeclarativeWorkflow()
0x8140d  ldarg.s  4
0x8140f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x81414  br       loc_82522
0x81419  ldarg.3
0x8141a  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x8141f  stloc.s  6
0x81421  ldloca.s 6
0x81423  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x81428  brfalse.s loc_81441
0x8142a  ldarg.3
  ... truncated ...
```
