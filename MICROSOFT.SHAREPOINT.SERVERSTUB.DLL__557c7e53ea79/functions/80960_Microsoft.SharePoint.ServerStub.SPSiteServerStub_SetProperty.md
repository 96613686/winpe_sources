# Microsoft.SharePoint.ServerStub.SPSiteServerStub::SetProperty

- ea: `0x80960`
- end: `0x80ecd`
- name: `Microsoft.SharePoint.ServerStub.SPSiteServerStub::SetProperty`
- size: `1389`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x80960`

## string_xrefs

- `0x809b9`: `AllowCreateDeclarativeWorkflow`
- `0x80bb2`: `AllowCreateDeclarativeWorkflow`
- `0x809e9`: `AllowRevertFromTemplate`
- `0x80c22`: `AllowRevertFromTemplate`
- `0x809f5`: `AllowSaveDeclarativeWorkflowAsTemplate`
- `0x80c3e`: `AllowSaveDeclarativeWorkflowAsTemplate`
- `0x80a0d`: `AllowSelfServiceUpgrade`
- `0x80c76`: `AllowSelfServiceUpgrade`
- `0x80a19`: `AllowSelfServiceUpgradeEvaluation`
- `0x80c92`: `AllowSelfServiceUpgradeEvaluation`
- `0x80a3f`: `CommentsOnSitePagesDisabled`
- `0x80ce6`: `CommentsOnSitePagesDisabled`
- `0x80a59`: `DisableCompanyWideSharingLinks`
- `0x80d1e`: `DisableCompanyWideSharingLinks`
- `0x80ace`: `StatusBarLink`
- `0x80e1a`: `StatusBarLink`
- `0x80af5`: `UIVersionConfigurationEnabled`
- `0x80e6e`: `UIVersionConfigurationEnabled`
- `0x80b02`: `UpgradeScheduled`
- `0x80e8a`: `UpgradeScheduled`
- `0x80b0f`: `UpgradeScheduledDate`
- `0x80ea6`: `UpgradeScheduledDate`

## pseudocode

```c

```

## disassembly

```asm
0x80960  ldarg.s  4
0x80962  brtrue.s loc_8096F
0x80964  ldstr    aProxycontext// "proxyContext"
0x80969  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8096e  throw
0x8096f  ldarg.1
0x80970  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPSite
0x80975  stloc.0
0x80976  ldloc.0
0x80977  brtrue.s loc_80984
0x80979  ldstr    aTarget// "target"
0x8097e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x80983  throw
0x80984  ldarg.2
0x80985  brtrue.s loc_80992
0x80987  ldstr    aPropname// "propName"
0x8098c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x80991  throw
0x80992  ldarg.0
0x80993  ldarg.2
0x80994  ldarg.s  4
0x80996  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8099b  starg.s  2
0x8099d  ldarg.2
0x8099e  dup
0x8099f  stloc.1
0x809a0  brfalse  loc_80EC1
0x809a5  volatile.
0x809a7  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60015b0-1
0x809ac  brtrue   loc_80B22
0x809b1  ldc.i4.s 0x1C
0x809b3  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x809b8  dup
0x809b9  ldstr    aAllowcreatedec// "AllowCreateDeclarativeWorkflow"
0x809be  ldc.i4.0
0x809bf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x809c4  dup
0x809c5  ldstr    aAllowdesigner// "AllowDesigner"
0x809ca  ldc.i4.1
0x809cb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x809d0  dup
0x809d1  ldstr    aAllowexternale// "AllowExternalEmbeddingWrapper"
0x809d6  ldc.i4.2
0x809d7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x809dc  dup
0x809dd  ldstr    aAllowmasterpag// "AllowMasterPageEditing"
0x809e2  ldc.i4.3
0x809e3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x809e8  dup
0x809e9  ldstr    aAllowrevertfro// "AllowRevertFromTemplate"
0x809ee  ldc.i4.4
0x809ef  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x809f4  dup
0x809f5  ldstr    aAllowsavedecla// "AllowSaveDeclarativeWorkflowAsTemplate"
0x809fa  ldc.i4.5
0x809fb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80a00  dup
0x80a01  ldstr    aAllowsavepubli// "AllowSavePublishDeclarativeWorkflow"
0x80a06  ldc.i4.6
0x80a07  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80a0c  dup
0x80a0d  ldstr    aAllowselfservi// "AllowSelfServiceUpgrade"
0x80a12  ldc.i4.7
0x80a13  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80a18  dup
0x80a19  ldstr    aAllowselfservi_0// "AllowSelfServiceUpgradeEvaluation"
0x80a1e  ldc.i4.8
0x80a1f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80a24  dup
0x80a25  ldstr    aAuditlogtrimmi// "AuditLogTrimmingRetention"
0x80a2a  ldc.i4.s 9
0x80a2c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80a31  dup
0x80a32  ldstr    aClassification// "Classification"
0x80a37  ldc.i4.s 0xA
0x80a39  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80a3e  dup
0x80a3f  ldstr    aCommentsonsite// "CommentsOnSitePagesDisabled"
0x80a44  ldc.i4.s 0xB
0x80a46  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80a4b  dup
0x80a4c  ldstr    aDisableappview// "DisableAppViews"
0x80a51  ldc.i4.s 0xC
0x80a53  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80a58  dup
0x80a59  ldstr    aDisablecompany// "DisableCompanyWideSharingLinks"
0x80a5e  ldc.i4.s 0xD
0x80a60  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80a65  dup
0x80a66  ldstr    aDisableflows// "DisableFlows"
0x80a6b  ldc.i4.s 0xE
0x80a6d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80a72  dup
0x80a73  ldstr    aNeedsb2bupgrad// "NeedsB2BUpgrade"
0x80a78  ldc.i4.s 0xF
0x80a7a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80a7f  dup
0x80a80  ldstr    aOwner// "Owner"
0x80a85  ldc.i4.s 0x10
0x80a87  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80a8c  dup
0x80a8d  ldstr    aSandboxedcodea// "SandboxedCodeActivationCapability"
0x80a92  ldc.i4.s 0x11
0x80a94  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80a99  dup
0x80a9a  ldstr    aSecondaryconta// "SecondaryContact"
0x80a9f  ldc.i4.s 0x12
0x80aa1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80aa6  dup
0x80aa7  ldstr    aSharebyemailen// "ShareByEmailEnabled"
0x80aac  ldc.i4.s 0x13
0x80aae  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80ab3  dup
0x80ab4  ldstr    aShowpeoplepick// "ShowPeoplePickerSuggestionsForGuestUser"...
0x80ab9  ldc.i4.s 0x14
0x80abb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80ac0  dup
0x80ac1  ldstr    aShowurlstructu// "ShowUrlStructure"
0x80ac6  ldc.i4.s 0x15
0x80ac8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80acd  dup
0x80ace  ldstr    aStatusbarlink// "StatusBarLink"
0x80ad3  ldc.i4.s 0x16
0x80ad5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80ada  dup
0x80adb  ldstr    aStatusbartext// "StatusBarText"
0x80ae0  ldc.i4.s 0x17
0x80ae2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80ae7  dup
0x80ae8  ldstr    aTrimauditlog// "TrimAuditLog"
0x80aed  ldc.i4.s 0x18
0x80aef  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80af4  dup
0x80af5  ldstr    aUiversionconfi// "UIVersionConfigurationEnabled"
0x80afa  ldc.i4.s 0x19
0x80afc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80b01  dup
0x80b02  ldstr    aUpgradeschedul// "UpgradeScheduled"
0x80b07  ldc.i4.s 0x1A
0x80b09  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80b0e  dup
0x80b0f  ldstr    aUpgradeschedul_0// "UpgradeScheduledDate"
0x80b14  ldc.i4.s 0x1B
0x80b16  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x80b1b  volatile.
0x80b1d  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60015b0-1
0x80b22  volatile.
0x80b24  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60015b0-1
0x80b29  ldloc.1
0x80b2a  ldloca.s 2
0x80b2c  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x80b31  brfalse  loc_80EC1
0x80b36  ldloc.2
0x80b37  switch   loc_80BB1, loc_80BCD, loc_80BE9, loc_80C05, loc_80C21, loc_80C3D, loc_80C59, loc_80C75, loc_80C91, loc_80CAD, loc_80CC9, loc_80CE5, loc_80D01, loc_80D1D, loc_80D39, loc_80D55, loc_80D71, loc_80D8D, loc_80DA9, loc_80DC5, loc_80DE1, loc_80DFD, loc_80E19, loc_80E35, loc_80E51, loc_80E6D, loc_80E89, loc_80EA5
0x80bac  br       loc_80EC1
0x80bb1  ldarg.0
0x80bb2  ldstr    aAllowcreatedec// "AllowCreateDeclarativeWorkflow"
0x80bb7  ldarg.s  4
0x80bb9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80bbe  ldloc.0
0x80bbf  ldarg.3
0x80bc0  ldarg.s  4
0x80bc2  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80bc7  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_AllowCreateDeclarativeWorkflow(bool)
0x80bcc  ret
0x80bcd  ldarg.0
0x80bce  ldstr    aAllowdesigner// "AllowDesigner"
0x80bd3  ldarg.s  4
0x80bd5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80bda  ldloc.0
0x80bdb  ldarg.3
0x80bdc  ldarg.s  4
0x80bde  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80be3  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_AllowDesigner(bool)
0x80be8  ret
0x80be9  ldarg.0
0x80bea  ldstr    aAllowexternale// "AllowExternalEmbeddingWrapper"
0x80bef  ldarg.s  4
0x80bf1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80bf6  ldloc.0
0x80bf7  ldarg.3
0x80bf8  ldarg.s  4
0x80bfa  call     T0x2B000209
0x80bff  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_AllowExternalEmbeddingWrapper(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ScriptSafeExternalEmbedding)
0x80c04  ret
0x80c05  ldarg.0
0x80c06  ldstr    aAllowmasterpag// "AllowMasterPageEditing"
0x80c0b  ldarg.s  4
0x80c0d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80c12  ldloc.0
0x80c13  ldarg.3
0x80c14  ldarg.s  4
0x80c16  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80c1b  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_AllowMasterPageEditing(bool)
0x80c20  ret
0x80c21  ldarg.0
0x80c22  ldstr    aAllowrevertfro// "AllowRevertFromTemplate"
0x80c27  ldarg.s  4
0x80c29  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80c2e  ldloc.0
0x80c2f  ldarg.3
0x80c30  ldarg.s  4
0x80c32  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80c37  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_AllowRevertFromTemplate(bool)
0x80c3c  ret
0x80c3d  ldarg.0
0x80c3e  ldstr    aAllowsavedecla// "AllowSaveDeclarativeWorkflowAsTemplate"
0x80c43  ldarg.s  4
0x80c45  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80c4a  ldloc.0
0x80c4b  ldarg.3
0x80c4c  ldarg.s  4
0x80c4e  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80c53  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_AllowSaveDeclarativeWorkflowAsTemplate(bool)
0x80c58  ret
0x80c59  ldarg.0
0x80c5a  ldstr    aAllowsavepubli// "AllowSavePublishDeclarativeWorkflow"
0x80c5f  ldarg.s  4
0x80c61  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80c66  ldloc.0
0x80c67  ldarg.3
0x80c68  ldarg.s  4
0x80c6a  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80c6f  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_AllowSavePublishDeclarativeWorkflow(bool)
0x80c74  ret
0x80c75  ldarg.0
0x80c76  ldstr    aAllowselfservi// "AllowSelfServiceUpgrade"
0x80c7b  ldarg.s  4
0x80c7d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80c82  ldloc.0
0x80c83  ldarg.3
0x80c84  ldarg.s  4
0x80c86  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80c8b  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_AllowSelfServiceUpgrade(bool)
0x80c90  ret
0x80c91  ldarg.0
0x80c92  ldstr    aAllowselfservi_0// "AllowSelfServiceUpgradeEvaluation"
0x80c97  ldarg.s  4
0x80c99  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80c9e  ldloc.0
0x80c9f  ldarg.3
0x80ca0  ldarg.s  4
0x80ca2  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80ca7  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_AllowSelfServiceUpgradeEvaluation(bool)
0x80cac  ret
0x80cad  ldarg.0
0x80cae  ldstr    aAuditlogtrimmi// "AuditLogTrimmingRetention"
0x80cb3  ldarg.s  4
0x80cb5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80cba  ldloc.0
0x80cbb  ldarg.3
0x80cbc  ldarg.s  4
0x80cbe  call     int32 [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToInt32(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80cc3  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_AuditLogTrimmingRetention(int32)
0x80cc8  ret
0x80cc9  ldarg.0
0x80cca  ldstr    aClassification// "Classification"
0x80ccf  ldarg.s  4
0x80cd1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80cd6  ldloc.0
0x80cd7  ldarg.3
0x80cd8  ldarg.s  4
0x80cda  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80cdf  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_Classification(string)
0x80ce4  ret
0x80ce5  ldarg.0
0x80ce6  ldstr    aCommentsonsite// "CommentsOnSitePagesDisabled"
0x80ceb  ldarg.s  4
0x80ced  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80cf2  ldloc.0
0x80cf3  ldarg.3
0x80cf4  ldarg.s  4
0x80cf6  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80cfb  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_CommentsOnSitePagesDisabled(bool)
0x80d00  ret
0x80d01  ldarg.0
0x80d02  ldstr    aDisableappview// "DisableAppViews"
0x80d07  ldarg.s  4
0x80d09  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80d0e  ldloc.0
0x80d0f  ldarg.3
0x80d10  ldarg.s  4
0x80d12  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80d17  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_DisableAppViews(bool)
0x80d1c  ret
0x80d1d  ldarg.0
0x80d1e  ldstr    aDisablecompany// "DisableCompanyWideSharingLinks"
0x80d23  ldarg.s  4
0x80d25  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80d2a  ldloc.0
0x80d2b  ldarg.3
0x80d2c  ldarg.s  4
0x80d2e  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80d33  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::set_DisableCompanyWideSharingLinks(bool)
0x80d38  ret
0x80d39  ldarg.0
0x80d3a  ldstr    aDisableflows// "DisableFlows"
0x80d3f  ldarg.s  4
0x80d41  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x80d46  ldloc.0
  ... truncated ...
```
