# Microsoft.SharePoint.ServerStub.SPSiteServerStub::SetProperty_0

- ea: `0x83cb0`
- end: `0x841e5`
- name: `Microsoft.SharePoint.ServerStub.SPSiteServerStub::SetProperty_0`
- size: `1333`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x83cb0`

## string_xrefs

- `0x83d09`: `AllowCreateDeclarativeWorkflow`
- `0x83f02`: `AllowCreateDeclarativeWorkflow`
- `0x83d39`: `AllowRevertFromTemplate`
- `0x83f6a`: `AllowRevertFromTemplate`
- `0x83d45`: `AllowSaveDeclarativeWorkflowAsTemplate`
- `0x83f84`: `AllowSaveDeclarativeWorkflowAsTemplate`
- `0x83d5d`: `AllowSelfServiceUpgrade`
- `0x83fb8`: `AllowSelfServiceUpgrade`
- `0x83d69`: `AllowSelfServiceUpgradeEvaluation`
- `0x83fd2`: `AllowSelfServiceUpgradeEvaluation`
- `0x83d8f`: `CommentsOnSitePagesDisabled`
- `0x84020`: `CommentsOnSitePagesDisabled`
- `0x83da9`: `DisableCompanyWideSharingLinks`
- `0x84054`: `DisableCompanyWideSharingLinks`
- `0x83e1e`: `StatusBarLink`
- `0x8413e`: `StatusBarLink`
- `0x83e45`: `UIVersionConfigurationEnabled`
- `0x8418c`: `UIVersionConfigurationEnabled`
- `0x83e52`: `UpgradeScheduled`
- `0x841a6`: `UpgradeScheduled`
- `0x83e5f`: `UpgradeScheduledDate`
- `0x841c0`: `UpgradeScheduledDate`

## pseudocode

```c

```

## disassembly

```asm
0x83cb0  ldarg.s  4
0x83cb2  brtrue.s loc_83CBF
0x83cb4  ldstr    aProxycontext// "proxyContext"
0x83cb9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x83cbe  throw
0x83cbf  ldarg.1
0x83cc0  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPSite
0x83cc5  stloc.0
0x83cc6  ldloc.0
0x83cc7  brtrue.s loc_83CD4
0x83cc9  ldstr    aTarget// "target"
0x83cce  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x83cd3  throw
0x83cd4  ldarg.2
0x83cd5  brtrue.s loc_83CE2
0x83cd7  ldstr    aPropname// "propName"
0x83cdc  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x83ce1  throw
0x83ce2  ldarg.0
0x83ce3  ldarg.2
0x83ce4  ldarg.s  4
0x83ce6  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x83ceb  starg.s  2
0x83ced  ldarg.2
0x83cee  dup
0x83cef  stloc.1
0x83cf0  brfalse  loc_841D9
0x83cf5  volatile.
0x83cf7  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60015e5-1
0x83cfc  brtrue   loc_83E72
0x83d01  ldc.i4.s 0x1C
0x83d03  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x83d08  dup
0x83d09  ldstr    aAllowcreatedec// "AllowCreateDeclarativeWorkflow"
0x83d0e  ldc.i4.0
0x83d0f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83d14  dup
0x83d15  ldstr    aAllowdesigner// "AllowDesigner"
0x83d1a  ldc.i4.1
0x83d1b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83d20  dup
0x83d21  ldstr    aAllowexternale// "AllowExternalEmbeddingWrapper"
0x83d26  ldc.i4.2
0x83d27  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83d2c  dup
0x83d2d  ldstr    aAllowmasterpag// "AllowMasterPageEditing"
0x83d32  ldc.i4.3
0x83d33  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83d38  dup
0x83d39  ldstr    aAllowrevertfro// "AllowRevertFromTemplate"
0x83d3e  ldc.i4.4
0x83d3f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83d44  dup
0x83d45  ldstr    aAllowsavedecla// "AllowSaveDeclarativeWorkflowAsTemplate"
0x83d4a  ldc.i4.5
0x83d4b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83d50  dup
0x83d51  ldstr    aAllowsavepubli// "AllowSavePublishDeclarativeWorkflow"
0x83d56  ldc.i4.6
0x83d57  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83d5c  dup
0x83d5d  ldstr    aAllowselfservi// "AllowSelfServiceUpgrade"
0x83d62  ldc.i4.7
0x83d63  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83d68  dup
0x83d69  ldstr    aAllowselfservi_0// "AllowSelfServiceUpgradeEvaluation"
0x83d6e  ldc.i4.8
0x83d6f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83d74  dup
0x83d75  ldstr    aAuditlogtrimmi// "AuditLogTrimmingRetention"
0x83d7a  ldc.i4.s 9
0x83d7c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83d81  dup
0x83d82  ldstr    aClassification// "Classification"
0x83d87  ldc.i4.s 0xA
0x83d89  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83d8e  dup
0x83d8f  ldstr    aCommentsonsite// "CommentsOnSitePagesDisabled"
0x83d94  ldc.i4.s 0xB
0x83d96  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83d9b  dup
0x83d9c  ldstr    aDisableappview// "DisableAppViews"
0x83da1  ldc.i4.s 0xC
0x83da3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83da8  dup
0x83da9  ldstr    aDisablecompany// "DisableCompanyWideSharingLinks"
0x83dae  ldc.i4.s 0xD
0x83db0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83db5  dup
0x83db6  ldstr    aDisableflows// "DisableFlows"
0x83dbb  ldc.i4.s 0xE
0x83dbd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83dc2  dup
0x83dc3  ldstr    aNeedsb2bupgrad// "NeedsB2BUpgrade"
0x83dc8  ldc.i4.s 0xF
0x83dca  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83dcf  dup
0x83dd0  ldstr    aOwner// "Owner"
0x83dd5  ldc.i4.s 0x10
0x83dd7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83ddc  dup
0x83ddd  ldstr    aSandboxedcodea// "SandboxedCodeActivationCapability"
0x83de2  ldc.i4.s 0x11
0x83de4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83de9  dup
0x83dea  ldstr    aSecondaryconta// "SecondaryContact"
0x83def  ldc.i4.s 0x12
0x83df1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83df6  dup
0x83df7  ldstr    aSharebyemailen// "ShareByEmailEnabled"
0x83dfc  ldc.i4.s 0x13
0x83dfe  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83e03  dup
0x83e04  ldstr    aShowpeoplepick// "ShowPeoplePickerSuggestionsForGuestUser"...
0x83e09  ldc.i4.s 0x14
0x83e0b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83e10  dup
0x83e11  ldstr    aShowurlstructu// "ShowUrlStructure"
0x83e16  ldc.i4.s 0x15
0x83e18  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83e1d  dup
0x83e1e  ldstr    aStatusbarlink// "StatusBarLink"
0x83e23  ldc.i4.s 0x16
0x83e25  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83e2a  dup
0x83e2b  ldstr    aStatusbartext// "StatusBarText"
0x83e30  ldc.i4.s 0x17
0x83e32  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83e37  dup
0x83e38  ldstr    aTrimauditlog// "TrimAuditLog"
0x83e3d  ldc.i4.s 0x18
0x83e3f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83e44  dup
0x83e45  ldstr    aUiversionconfi// "UIVersionConfigurationEnabled"
0x83e4a  ldc.i4.s 0x19
0x83e4c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83e51  dup
0x83e52  ldstr    aUpgradeschedul// "UpgradeScheduled"
0x83e57  ldc.i4.s 0x1A
0x83e59  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83e5e  dup
0x83e5f  ldstr    aUpgradeschedul_0// "UpgradeScheduledDate"
0x83e64  ldc.i4.s 0x1B
0x83e66  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x83e6b  volatile.
0x83e6d  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60015e5-1
0x83e72  volatile.
0x83e74  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60015e5-1
0x83e79  ldloc.1
0x83e7a  ldloca.s 2
0x83e7c  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x83e81  brfalse  loc_841D9
0x83e86  ldloc.2
0x83e87  switch   loc_83F01, loc_83F1B, loc_83F35, loc_83F4F, loc_83F69, loc_83F83, loc_83F9D, loc_83FB7, loc_83FD1, loc_83FEB, loc_84005, loc_8401F, loc_84039, loc_84053, loc_8406D, loc_84087, loc_840A1, loc_840BB, loc_840D5, loc_840EF, loc_84109, loc_84123, loc_8413D, loc_84157, loc_84171, loc_8418B, loc_841A5, loc_841BF
0x83efc  br       loc_841D9
0x83f01  ldarg.0
0x83f02  ldstr    aAllowcreatedec// "AllowCreateDeclarativeWorkflow"
0x83f07  ldarg.s  4
0x83f09  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x83f0e  ldloc.0
0x83f0f  ldarg.3
0x83f10  callvirt T0x2B00000A
0x83f15  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_AllowCreateDeclarativeWorkflow(bool)
0x83f1a  ret
0x83f1b  ldarg.0
0x83f1c  ldstr    aAllowdesigner// "AllowDesigner"
0x83f21  ldarg.s  4
0x83f23  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x83f28  ldloc.0
0x83f29  ldarg.3
0x83f2a  callvirt T0x2B00000A
0x83f2f  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_AllowDesigner(bool)
0x83f34  ret
0x83f35  ldarg.0
0x83f36  ldstr    aAllowexternale// "AllowExternalEmbeddingWrapper"
0x83f3b  ldarg.s  4
0x83f3d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x83f42  ldloc.0
0x83f43  ldarg.3
0x83f44  callvirt T0x2B000216
0x83f49  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_AllowExternalEmbeddingWrapper(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ScriptSafeExternalEmbedding)
0x83f4e  ret
0x83f4f  ldarg.0
0x83f50  ldstr    aAllowmasterpag// "AllowMasterPageEditing"
0x83f55  ldarg.s  4
0x83f57  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x83f5c  ldloc.0
0x83f5d  ldarg.3
0x83f5e  callvirt T0x2B00000A
0x83f63  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_AllowMasterPageEditing(bool)
0x83f68  ret
0x83f69  ldarg.0
0x83f6a  ldstr    aAllowrevertfro// "AllowRevertFromTemplate"
0x83f6f  ldarg.s  4
0x83f71  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x83f76  ldloc.0
0x83f77  ldarg.3
0x83f78  callvirt T0x2B00000A
0x83f7d  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_AllowRevertFromTemplate(bool)
0x83f82  ret
0x83f83  ldarg.0
0x83f84  ldstr    aAllowsavedecla// "AllowSaveDeclarativeWorkflowAsTemplate"
0x83f89  ldarg.s  4
0x83f8b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x83f90  ldloc.0
0x83f91  ldarg.3
0x83f92  callvirt T0x2B00000A
0x83f97  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_AllowSaveDeclarativeWorkflowAsTemplate(bool)
0x83f9c  ret
0x83f9d  ldarg.0
0x83f9e  ldstr    aAllowsavepubli// "AllowSavePublishDeclarativeWorkflow"
0x83fa3  ldarg.s  4
0x83fa5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x83faa  ldloc.0
0x83fab  ldarg.3
0x83fac  callvirt T0x2B00000A
0x83fb1  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_AllowSavePublishDeclarativeWorkflow(bool)
0x83fb6  ret
0x83fb7  ldarg.0
0x83fb8  ldstr    aAllowselfservi// "AllowSelfServiceUpgrade"
0x83fbd  ldarg.s  4
0x83fbf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x83fc4  ldloc.0
0x83fc5  ldarg.3
0x83fc6  callvirt T0x2B00000A
0x83fcb  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_AllowSelfServiceUpgrade(bool)
0x83fd0  ret
0x83fd1  ldarg.0
0x83fd2  ldstr    aAllowselfservi_0// "AllowSelfServiceUpgradeEvaluation"
0x83fd7  ldarg.s  4
0x83fd9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x83fde  ldloc.0
0x83fdf  ldarg.3
0x83fe0  callvirt T0x2B00000A
0x83fe5  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_AllowSelfServiceUpgradeEvaluation(bool)
0x83fea  ret
0x83feb  ldarg.0
0x83fec  ldstr    aAuditlogtrimmi// "AuditLogTrimmingRetention"
0x83ff1  ldarg.s  4
0x83ff3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x83ff8  ldloc.0
0x83ff9  ldarg.3
0x83ffa  callvirt T0x2B000009
0x83fff  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_AuditLogTrimmingRetention(int32)
0x84004  ret
0x84005  ldarg.0
0x84006  ldstr    aClassification// "Classification"
0x8400b  ldarg.s  4
0x8400d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x84012  ldloc.0
0x84013  ldarg.3
0x84014  callvirt T0x2B000008
0x84019  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_Classification(string)
0x8401e  ret
0x8401f  ldarg.0
0x84020  ldstr    aCommentsonsite// "CommentsOnSitePagesDisabled"
0x84025  ldarg.s  4
0x84027  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8402c  ldloc.0
0x8402d  ldarg.3
0x8402e  callvirt T0x2B00000A
0x84033  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_CommentsOnSitePagesDisabled(bool)
0x84038  ret
0x84039  ldarg.0
0x8403a  ldstr    aDisableappview// "DisableAppViews"
0x8403f  ldarg.s  4
0x84041  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x84046  ldloc.0
0x84047  ldarg.3
0x84048  callvirt T0x2B00000A
0x8404d  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_DisableAppViews(bool)
0x84052  ret
0x84053  ldarg.0
0x84054  ldstr    aDisablecompany// "DisableCompanyWideSharingLinks"
0x84059  ldarg.s  4
0x8405b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x84060  ldloc.0
0x84061  ldarg.3
0x84062  callvirt T0x2B00000A
0x84067  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_DisableCompanyWideSharingLinks(bool)
0x8406c  ret
0x8406d  ldarg.0
0x8406e  ldstr    aDisableflows// "DisableFlows"
0x84073  ldarg.s  4
0x84075  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8407a  ldloc.0
0x8407b  ldarg.3
0x8407c  callvirt T0x2B00000A
0x84081  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_DisableFlows(bool)
0x84086  ret
0x84087  ldarg.0
0x84088  ldstr    aNeedsb2bupgrad// "NeedsB2BUpgrade"
0x8408d  ldarg.s  4
0x8408f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x84094  ldloc.0
0x84095  ldarg.3
0x84096  callvirt T0x2B00000A
0x8409b  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_NeedsB2BUpgrade(bool)
0x840a0  ret
0x840a1  ldarg.0
  ... truncated ...
```
