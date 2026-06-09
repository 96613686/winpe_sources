# Microsoft.SharePoint.ServerStub.SPInformationRightsManagementFileSettingsServerStub::SetProperty_0

- ea: `0x65240`
- end: `0x65546`
- name: `Microsoft.SharePoint.ServerStub.SPInformationRightsManagementFileSettingsServerStub::SetProperty_0`
- size: `774`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x65240`

## string_xrefs

- `0x652b1`: `AllowWriteCopy`
- `0x653e9`: `AllowWriteCopy`
- `0x652c9`: `DocumentAccessExpireDays`
- `0x6541d`: `DocumentAccessExpireDays`
- `0x652d5`: `EnableDocumentAccessExpire`
- `0x65437`: `EnableDocumentAccessExpire`
- `0x652f9`: `EnableLicenseCacheExpire`
- `0x65485`: `EnableLicenseCacheExpire`
- `0x6531f`: `LicenseCacheExpireDays`
- `0x654d3`: `LicenseCacheExpireDays`
- `0x65346`: `TemplateId`
- `0x65521`: `TemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x65240  ldarg.s  4
0x65242  brtrue.s loc_6524F
0x65244  ldstr    aProxycontext// "proxyContext"
0x65249  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6524e  throw
0x6524f  ldarg.1
0x65250  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings
0x65255  stloc.0
0x65256  ldloc.0
0x65257  brtrue.s loc_65264
0x65259  ldstr    aTarget// "target"
0x6525e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x65263  throw
0x65264  ldarg.2
0x65265  brtrue.s loc_65272
0x65267  ldstr    aPropname// "propName"
0x6526c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x65271  throw
0x65272  ldarg.0
0x65273  ldarg.2
0x65274  ldarg.s  4
0x65276  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6527b  starg.s  2
0x6527d  ldarg.2
0x6527e  dup
0x6527f  stloc.1
0x65280  brfalse  loc_6553A
0x65285  volatile.
0x65287  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60011c8-1
0x6528c  brtrue   loc_65359
0x65291  ldc.i4.s 0xF
0x65293  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x65298  dup
0x65299  ldstr    aAllowprint// "AllowPrint"
0x6529e  ldc.i4.0
0x6529f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x652a4  dup
0x652a5  ldstr    aAllowscript// "AllowScript"
0x652aa  ldc.i4.1
0x652ab  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x652b0  dup
0x652b1  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x652b6  ldc.i4.2
0x652b7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x652bc  dup
0x652bd  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x652c2  ldc.i4.3
0x652c3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x652c8  dup
0x652c9  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x652ce  ldc.i4.4
0x652cf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x652d4  dup
0x652d5  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x652da  ldc.i4.5
0x652db  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x652e0  dup
0x652e1  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x652e6  ldc.i4.6
0x652e7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x652ec  dup
0x652ed  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x652f2  ldc.i4.7
0x652f3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x652f8  dup
0x652f9  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x652fe  ldc.i4.8
0x652ff  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65304  dup
0x65305  ldstr    aGroupname// "GroupName"
0x6530a  ldc.i4.s 9
0x6530c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65311  dup
0x65312  ldstr    aIrmenabled// "IrmEnabled"
0x65317  ldc.i4.s 0xA
0x65319  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6531e  dup
0x6531f  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x65324  ldc.i4.s 0xB
0x65326  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6532b  dup
0x6532c  ldstr    aPolicydescript// "PolicyDescription"
0x65331  ldc.i4.s 0xC
0x65333  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65338  dup
0x65339  ldstr    aPolicytitle// "PolicyTitle"
0x6533e  ldc.i4.s 0xD
0x65340  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65345  dup
0x65346  ldstr    aTemplateid// "TemplateId"
0x6534b  ldc.i4.s 0xE
0x6534d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65352  volatile.
0x65354  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60011c8-1
0x65359  volatile.
0x6535b  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60011c8-1
0x65360  ldloc.1
0x65361  ldloca.s 2
0x65363  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x65368  brfalse  loc_6553A
0x6536d  ldloc.2
0x6536e  switch   loc_653B4, loc_653CE, loc_653E8, loc_65402, loc_6541C, loc_65436, loc_65450, loc_6546A, loc_65484, loc_6549E, loc_654B8, loc_654D2, loc_654EC, loc_65506, loc_65520
0x653af  br       loc_6553A
0x653b4  ldarg.0
0x653b5  ldstr    aAllowprint// "AllowPrint"
0x653ba  ldarg.s  4
0x653bc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x653c1  ldloc.0
0x653c2  ldarg.3
0x653c3  callvirt T0x2B00000A
0x653c8  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_AllowPrint(bool)
0x653cd  ret
0x653ce  ldarg.0
0x653cf  ldstr    aAllowscript// "AllowScript"
0x653d4  ldarg.s  4
0x653d6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x653db  ldloc.0
0x653dc  ldarg.3
0x653dd  callvirt T0x2B00000A
0x653e2  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_AllowScript(bool)
0x653e7  ret
0x653e8  ldarg.0
0x653e9  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x653ee  ldarg.s  4
0x653f0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x653f5  ldloc.0
0x653f6  ldarg.3
0x653f7  callvirt T0x2B00000A
0x653fc  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_AllowWriteCopy(bool)
0x65401  ret
0x65402  ldarg.0
0x65403  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x65408  ldarg.s  4
0x6540a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6540f  ldloc.0
0x65410  ldarg.3
0x65411  callvirt T0x2B00000A
0x65416  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_DisableDocumentBrowserView(bool)
0x6541b  ret
0x6541c  ldarg.0
0x6541d  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x65422  ldarg.s  4
0x65424  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65429  ldloc.0
0x6542a  ldarg.3
0x6542b  callvirt T0x2B000009
0x65430  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_DocumentAccessExpireDays(int32)
0x65435  ret
0x65436  ldarg.0
0x65437  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x6543c  ldarg.s  4
0x6543e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65443  ldloc.0
0x65444  ldarg.3
0x65445  callvirt T0x2B00000A
0x6544a  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_EnableDocumentAccessExpire(bool)
0x6544f  ret
0x65450  ldarg.0
0x65451  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x65456  ldarg.s  4
0x65458  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6545d  ldloc.0
0x6545e  ldarg.3
0x6545f  callvirt T0x2B00000A
0x65464  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_EnableDocumentBrowserPublishingView(bool)
0x65469  ret
0x6546a  ldarg.0
0x6546b  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x65470  ldarg.s  4
0x65472  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65477  ldloc.0
0x65478  ldarg.3
0x65479  callvirt T0x2B00000A
0x6547e  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_EnableGroupProtection(bool)
0x65483  ret
0x65484  ldarg.0
0x65485  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x6548a  ldarg.s  4
0x6548c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65491  ldloc.0
0x65492  ldarg.3
0x65493  callvirt T0x2B00000A
0x65498  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_EnableLicenseCacheExpire(bool)
0x6549d  ret
0x6549e  ldarg.0
0x6549f  ldstr    aGroupname// "GroupName"
0x654a4  ldarg.s  4
0x654a6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x654ab  ldloc.0
0x654ac  ldarg.3
0x654ad  callvirt T0x2B000008
0x654b2  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_GroupName(string)
0x654b7  ret
0x654b8  ldarg.0
0x654b9  ldstr    aIrmenabled// "IrmEnabled"
0x654be  ldarg.s  4
0x654c0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x654c5  ldloc.0
0x654c6  ldarg.3
0x654c7  callvirt T0x2B00000A
0x654cc  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_IrmEnabled(bool)
0x654d1  ret
0x654d2  ldarg.0
0x654d3  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x654d8  ldarg.s  4
0x654da  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x654df  ldloc.0
0x654e0  ldarg.3
0x654e1  callvirt T0x2B000009
0x654e6  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_LicenseCacheExpireDays(int32)
0x654eb  ret
0x654ec  ldarg.0
0x654ed  ldstr    aPolicydescript// "PolicyDescription"
0x654f2  ldarg.s  4
0x654f4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x654f9  ldloc.0
0x654fa  ldarg.3
0x654fb  callvirt T0x2B000008
0x65500  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_PolicyDescription(string)
0x65505  ret
0x65506  ldarg.0
0x65507  ldstr    aPolicytitle// "PolicyTitle"
0x6550c  ldarg.s  4
0x6550e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65513  ldloc.0
0x65514  ldarg.3
0x65515  callvirt T0x2B000008
0x6551a  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_PolicyTitle(string)
0x6551f  ret
0x65520  ldarg.0
0x65521  ldstr    aTemplateid// "TemplateId"
0x65526  ldarg.s  4
0x65528  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6552d  ldloc.0
0x6552e  ldarg.3
0x6552f  callvirt T0x2B000008
0x65534  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_TemplateId(string)
0x65539  ret
0x6553a  ldarg.0
0x6553b  ldarg.1
0x6553c  ldarg.2
0x6553d  ldarg.3
0x6553e  ldarg.s  4
0x65540  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::SetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValue, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65545  ret
```
