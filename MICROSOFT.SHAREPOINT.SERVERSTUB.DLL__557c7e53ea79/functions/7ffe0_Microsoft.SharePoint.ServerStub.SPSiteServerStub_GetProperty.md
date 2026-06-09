# Microsoft.SharePoint.ServerStub.SPSiteServerStub::GetProperty

- ea: `0x7ffe0`
- end: `0x8095d`
- name: `Microsoft.SharePoint.ServerStub.SPSiteServerStub::GetProperty`
- size: `2429`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7ffe0`

## string_xrefs

- `0x800f1`: `CurrentChangeToken`
- `0x8059d`: `CurrentChangeToken`
- `0x80236`: `ServerRelativePath`
- `0x807b4`: `ServerRelativePath`
- `0x801e8`: `ReadOnly`
- `0x80738`: `ReadOnly`
- `0x801ce`: `ResourcePath`
- `0x80712`: `ResourcePath`
- `0x8025d`: `ShareByLinkEnabled`
- `0x807f2`: `ShareByLinkEnabled`
- `0x80037`: `AllowCreateDeclarativeWorkflow`
- `0x8043f`: `AllowCreateDeclarativeWorkflow`
- `0x80067`: `AllowRevertFromTemplate`
- `0x8049f`: `AllowRevertFromTemplate`
- `0x80073`: `AllowSaveDeclarativeWorkflowAsTemplate`
- `0x804b7`: `AllowSaveDeclarativeWorkflowAsTemplate`
- `0x8008b`: `AllowSelfServiceUpgrade`
- `0x804e7`: `AllowSelfServiceUpgrade`
- `0x80097`: `AllowSelfServiceUpgradeEvaluation`
- `0x804ff`: `AllowSelfServiceUpgradeEvaluation`
- `0x800d7`: `CommentsOnSitePagesDisabled`
- `0x8056d`: `CommentsOnSitePagesDisabled`
- `0x800e4`: `CompatibilityLevel`
- `0x80585`: `CompatibilityLevel`
- `0x80118`: `DisableCompanyWideSharingLinks`
- `0x805db`: `DisableCompanyWideSharingLinks`
- `0x801db`: `PrimaryUri`
- `0x80725`: `PrimaryUri`
- `0x80284`: `StatusBarLink`
- `0x8083a`: `StatusBarLink`
- `0x802b8`: `UIVersionConfigurationEnabled`
- `0x80890`: `UIVersionConfigurationEnabled`
- `0x802df`: `UpgradeScheduled`
- `0x808d3`: `UpgradeScheduled`
- `0x802ec`: `UpgradeScheduledDate`
- `0x808eb`: `UpgradeScheduledDate`

## pseudocode

```c

```

## disassembly

```asm
0x7ffe0  ldarg.2
0x7ffe1  brtrue.s loc_7FFEE
0x7ffe3  ldstr    aPropname// "propName"
0x7ffe8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7ffed  throw
0x7ffee  ldarg.3
0x7ffef  brtrue.s loc_7FFFC
0x7fff1  ldstr    aProxycontext// "proxyContext"
0x7fff6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7fffb  throw
0x7fffc  ldarg.1
0x7fffd  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPSite
0x80002  stloc.0
0x80003  ldloc.0
0x80004  brtrue.s loc_80011
0x80006  ldstr    aTarget// "target"
0x8000b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x80010  throw
0x80011  ldarg.0
0x80012  ldarg.2
0x80013  ldarg.3
0x80014  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80019  starg.s  2
0x8001b  ldarg.2
0x8001c  dup
0x8001d  stloc.1
0x8001e  brfalse  loc_80953
0x80023  volatile.
0x80025  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60015af-1
0x8002a  brtrue   loc_80333
0x8002f  ldc.i4.s 0x3B
0x80031  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x80036  dup
0x80037  ldstr    aAllowcreatedec// "AllowCreateDeclarativeWorkflow"
0x8003c  ldc.i4.0
0x8003d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80042  dup
0x80043  ldstr    aAllowdesigner// "AllowDesigner"
0x80048  ldc.i4.1
0x80049  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8004e  dup
0x8004f  ldstr    aAllowexternale// "AllowExternalEmbeddingWrapper"
0x80054  ldc.i4.2
0x80055  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8005a  dup
0x8005b  ldstr    aAllowmasterpag// "AllowMasterPageEditing"
0x80060  ldc.i4.3
0x80061  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80066  dup
0x80067  ldstr    aAllowrevertfro// "AllowRevertFromTemplate"
0x8006c  ldc.i4.4
0x8006d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80072  dup
0x80073  ldstr    aAllowsavedecla// "AllowSaveDeclarativeWorkflowAsTemplate"
0x80078  ldc.i4.5
0x80079  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8007e  dup
0x8007f  ldstr    aAllowsavepubli// "AllowSavePublishDeclarativeWorkflow"
0x80084  ldc.i4.6
0x80085  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8008a  dup
0x8008b  ldstr    aAllowselfservi// "AllowSelfServiceUpgrade"
0x80090  ldc.i4.7
0x80091  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80096  dup
0x80097  ldstr    aAllowselfservi_0// "AllowSelfServiceUpgradeEvaluation"
0x8009c  ldc.i4.8
0x8009d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x800a2  dup
0x800a3  ldstr    aAudit// "Audit"
0x800a8  ldc.i4.s 9
0x800aa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x800af  dup
0x800b0  ldstr    aAuditlogtrimmi// "AuditLogTrimmingRetention"
0x800b5  ldc.i4.s 0xA
0x800b7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x800bc  dup
0x800bd  ldstr    aCanupgrade// "CanUpgrade"
0x800c2  ldc.i4.s 0xB
0x800c4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x800c9  dup
0x800ca  ldstr    aClassification// "Classification"
0x800cf  ldc.i4.s 0xC
0x800d1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x800d6  dup
0x800d7  ldstr    aCommentsonsite// "CommentsOnSitePagesDisabled"
0x800dc  ldc.i4.s 0xD
0x800de  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x800e3  dup
0x800e4  ldstr    aCompatibilityl_0// "CompatibilityLevel"
0x800e9  ldc.i4.s 0xE
0x800eb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x800f0  dup
0x800f1  ldstr    aCurrentchanget// "CurrentChangeToken"
0x800f6  ldc.i4.s 0xF
0x800f8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x800fd  dup
0x800fe  ldstr    aCustomscriptsa// "CustomScriptSafeDomains"
0x80103  ldc.i4.s 0x10
0x80105  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8010a  dup
0x8010b  ldstr    aDisableappview// "DisableAppViews"
0x80110  ldc.i4.s 0x11
0x80112  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80117  dup
0x80118  ldstr    aDisablecompany// "DisableCompanyWideSharingLinks"
0x8011d  ldc.i4.s 0x12
0x8011f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80124  dup
0x80125  ldstr    aDisableflows// "DisableFlows"
0x8012a  ldc.i4.s 0x13
0x8012c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80131  dup
0x80132  ldstr    aEventreceivers// "EventReceivers"
0x80137  ldc.i4.s 0x14
0x80139  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8013e  dup
0x8013f  ldstr    aExternalsharin// "ExternalSharingTipsEnabled"
0x80144  ldc.i4.s 0x15
0x80146  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8014b  dup
0x8014c  ldstr    aFeatures// "Features"
0x80151  ldc.i4.s 0x16
0x80153  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80158  dup
0x80159  ldstr    aGeolocation// "GeoLocation"
0x8015e  ldc.i4.s 0x17
0x80160  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80165  dup
0x80166  ldstr    aGroupid// "GroupId"
0x8016b  ldc.i4.s 0x18
0x8016d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80172  dup
0x80173  ldstr    aHubsiteid_0// "HubSiteId"
0x80178  ldc.i4.s 0x19
0x8017a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8017f  dup
0x80180  ldstr    aId_0// "Id"
0x80185  ldc.i4.s 0x1A
0x80187  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8018c  dup
0x8018d  ldstr    aIshubsite// "IsHubSite"
0x80192  ldc.i4.s 0x1B
0x80194  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80199  dup
0x8019a  ldstr    aLockissue// "LockIssue"
0x8019f  ldc.i4.s 0x1C
0x801a1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x801a6  dup
0x801a7  ldstr    aMaxitemsperthr// "MaxItemsPerThrottledOperation"
0x801ac  ldc.i4.s 0x1D
0x801ae  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x801b3  dup
0x801b4  ldstr    aNeedsb2bupgrad// "NeedsB2BUpgrade"
0x801b9  ldc.i4.s 0x1E
0x801bb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x801c0  dup
0x801c1  ldstr    aOwner// "Owner"
0x801c6  ldc.i4.s 0x1F
0x801c8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x801cd  dup
0x801ce  ldstr    aResourcepath// "ResourcePath"
0x801d3  ldc.i4.s 0x20
0x801d5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x801da  dup
0x801db  ldstr    aPrimaryuri// "PrimaryUri"
0x801e0  ldc.i4.s 0x21
0x801e2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x801e7  dup
0x801e8  ldstr    aReadonly// "ReadOnly"
0x801ed  ldc.i4.s 0x22
0x801ef  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x801f4  dup
0x801f5  ldstr    aRecyclebin// "RecycleBin"
0x801fa  ldc.i4.s 0x23
0x801fc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80201  dup
0x80202  ldstr    aRequireddesign// "RequiredDesignerVersion"
0x80207  ldc.i4.s 0x24
0x80209  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8020e  dup
0x8020f  ldstr    aRootweb// "RootWeb"
0x80214  ldc.i4.s 0x25
0x80216  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8021b  dup
0x8021c  ldstr    aSandboxedcodea// "SandboxedCodeActivationCapability"
0x80221  ldc.i4.s 0x26
0x80223  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80228  dup
0x80229  ldstr    aSecondaryconta// "SecondaryContact"
0x8022e  ldc.i4.s 0x27
0x80230  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80235  dup
0x80236  ldstr    aServerrelative_0// "ServerRelativePath"
0x8023b  ldc.i4.s 0x28
0x8023d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80242  dup
0x80243  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x80248  ldc.i4.s 0x29
0x8024a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8024f  dup
0x80250  ldstr    aSharebyemailen// "ShareByEmailEnabled"
0x80255  ldc.i4.s 0x2A
0x80257  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8025c  dup
0x8025d  ldstr    aSharebylinkena// "ShareByLinkEnabled"
0x80262  ldc.i4.s 0x2B
0x80264  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80269  dup
0x8026a  ldstr    aShowpeoplepick// "ShowPeoplePickerSuggestionsForGuestUser"...
0x8026f  ldc.i4.s 0x2C
0x80271  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80276  dup
0x80277  ldstr    aShowurlstructu// "ShowUrlStructure"
0x8027c  ldc.i4.s 0x2D
0x8027e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80283  dup
0x80284  ldstr    aStatusbarlink// "StatusBarLink"
0x80289  ldc.i4.s 0x2E
0x8028b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80290  dup
0x80291  ldstr    aStatusbartext// "StatusBarText"
0x80296  ldc.i4.s 0x2F
0x80298  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8029d  dup
0x8029e  ldstr    aThicketsupport// "ThicketSupportDisabled"
0x802a3  ldc.i4.s 0x30
0x802a5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x802aa  dup
0x802ab  ldstr    aTrimauditlog// "TrimAuditLog"
0x802b0  ldc.i4.s 0x31
0x802b2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x802b7  dup
0x802b8  ldstr    aUiversionconfi// "UIVersionConfigurationEnabled"
0x802bd  ldc.i4.s 0x32
0x802bf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x802c4  dup
0x802c5  ldstr    aUpgradeinfo// "UpgradeInfo"
0x802ca  ldc.i4.s 0x33
0x802cc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x802d1  dup
0x802d2  ldstr    aUpgradereminde// "UpgradeReminderDate"
0x802d7  ldc.i4.s 0x34
0x802d9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x802de  dup
0x802df  ldstr    aUpgradeschedul// "UpgradeScheduled"
0x802e4  ldc.i4.s 0x35
0x802e6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x802eb  dup
0x802ec  ldstr    aUpgradeschedul_0// "UpgradeScheduledDate"
0x802f1  ldc.i4.s 0x36
0x802f3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x802f8  dup
0x802f9  ldstr    aUpgrading// "Upgrading"
0x802fe  ldc.i4.s 0x37
0x80300  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80305  dup
0x80306  ldstr    aUrl// "Url"
0x8030b  ldc.i4.s 0x38
0x8030d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80312  dup
0x80313  ldstr    aUsage// "Usage"
0x80318  ldc.i4.s 0x39
0x8031a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8031f  dup
0x80320  ldstr    aUsercustomacti// "UserCustomActions"
0x80325  ldc.i4.s 0x3A
0x80327  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8032c  volatile.
0x8032e  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60015af-1
0x80333  volatile.
0x80335  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60015af-1
0x8033a  ldloc.1
0x8033b  ldloca.s 2
0x8033d  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x80342  brfalse  loc_80953
0x80347  ldloc.2
0x80348  switch   loc_8043E, loc_80456, loc_8046E, loc_80486, loc_8049E, loc_804B6, loc_804CE, loc_804E6, loc_804FE, loc_80516, loc_80529, loc_80541, loc_80559, loc_8056C, loc_80584, loc_8059C, loc_805AF, loc_805C2, loc_805DA, loc_805F2, loc_8060A, loc_8061D, loc_80635, loc_80648, loc_8065B, loc_80673, loc_8068B, loc_806A3, loc_806BB, loc_806CE, loc_806E6, loc_806FE, loc_80711, loc_80724, loc_80737, loc_8074F, loc_80762, loc_80775, loc_80788, loc_807A0, loc_807B3, loc_807C6, loc_807D9, loc_807F1, loc_80809, loc_80821, loc_80839, loc_8084C, loc_8085F, loc_80877, loc_8088F, loc_808A7, loc_808BA, loc_808D2, loc_808EA \
0x80439  br       loc_80953
0x8043e  ldarg.0
0x8043f  ldstr    aAllowcreatedec// "AllowCreateDeclarativeWorkflow"
0x80444  ldarg.3
0x80445  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8044a  ldloc.0
0x8044b  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_AllowCreateDeclarativeWorkflow()
0x80450  box      [mscorlib]System.Boolean
0x80455  ret
0x80456  ldarg.0
0x80457  ldstr    aAllowdesigner// "AllowDesigner"
0x8045c  ldarg.3
0x8045d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80462  ldloc.0
0x80463  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_AllowDesigner()
0x80468  box      [mscorlib]System.Boolean
0x8046d  ret
0x8046e  ldarg.0
0x8046f  ldstr    aAllowexternale// "AllowExternalEmbeddingWrapper"
0x80474  ldarg.3
0x80475  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8047a  ldloc.0
  ... truncated ...
```
