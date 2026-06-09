# Microsoft.SharePoint.ServerStub.SPInformationRightsManagementSettingsServerStub::SetProperty_0

- ea: `0x66810`
- end: `0x66b16`
- name: `Microsoft.SharePoint.ServerStub.SPInformationRightsManagementSettingsServerStub::SetProperty_0`
- size: `774`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x66810`

## string_xrefs

- `0x66881`: `AllowWriteCopy`
- `0x669b9`: `AllowWriteCopy`
- `0x66899`: `DocumentAccessExpireDays`
- `0x669ed`: `DocumentAccessExpireDays`
- `0x668b1`: `EnableDocumentAccessExpire`
- `0x66a21`: `EnableDocumentAccessExpire`
- `0x668d5`: `EnableLicenseCacheExpire`
- `0x66a6f`: `EnableLicenseCacheExpire`
- `0x668ef`: `LicenseCacheExpireDays`
- `0x66aa3`: `LicenseCacheExpireDays`
- `0x66916`: `TemplateId`
- `0x66af1`: `TemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x66810  ldarg.s  4
0x66812  brtrue.s loc_6681F
0x66814  ldstr    aProxycontext// "proxyContext"
0x66819  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6681e  throw
0x6681f  ldarg.1
0x66820  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings
0x66825  stloc.0
0x66826  ldloc.0
0x66827  brtrue.s loc_66834
0x66829  ldstr    aTarget// "target"
0x6682e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x66833  throw
0x66834  ldarg.2
0x66835  brtrue.s loc_66842
0x66837  ldstr    aPropname// "propName"
0x6683c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x66841  throw
0x66842  ldarg.0
0x66843  ldarg.2
0x66844  ldarg.s  4
0x66846  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6684b  starg.s  2
0x6684d  ldarg.2
0x6684e  dup
0x6684f  stloc.1
0x66850  brfalse  loc_66B0A
0x66855  volatile.
0x66857  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60011de-1
0x6685c  brtrue   loc_66929
0x66861  ldc.i4.s 0xF
0x66863  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x66868  dup
0x66869  ldstr    aAllowprint// "AllowPrint"
0x6686e  ldc.i4.0
0x6686f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x66874  dup
0x66875  ldstr    aAllowscript// "AllowScript"
0x6687a  ldc.i4.1
0x6687b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x66880  dup
0x66881  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x66886  ldc.i4.2
0x66887  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6688c  dup
0x6688d  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x66892  ldc.i4.3
0x66893  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x66898  dup
0x66899  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x6689e  ldc.i4.4
0x6689f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x668a4  dup
0x668a5  ldstr    aDocumentlibrar// "DocumentLibraryProtectionExpireDate"
0x668aa  ldc.i4.5
0x668ab  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x668b0  dup
0x668b1  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x668b6  ldc.i4.6
0x668b7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x668bc  dup
0x668bd  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x668c2  ldc.i4.7
0x668c3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x668c8  dup
0x668c9  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x668ce  ldc.i4.8
0x668cf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x668d4  dup
0x668d5  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x668da  ldc.i4.s 9
0x668dc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x668e1  dup
0x668e2  ldstr    aGroupname// "GroupName"
0x668e7  ldc.i4.s 0xA
0x668e9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x668ee  dup
0x668ef  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x668f4  ldc.i4.s 0xB
0x668f6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x668fb  dup
0x668fc  ldstr    aPolicydescript// "PolicyDescription"
0x66901  ldc.i4.s 0xC
0x66903  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x66908  dup
0x66909  ldstr    aPolicytitle// "PolicyTitle"
0x6690e  ldc.i4.s 0xD
0x66910  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x66915  dup
0x66916  ldstr    aTemplateid// "TemplateId"
0x6691b  ldc.i4.s 0xE
0x6691d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x66922  volatile.
0x66924  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60011de-1
0x66929  volatile.
0x6692b  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60011de-1
0x66930  ldloc.1
0x66931  ldloca.s 2
0x66933  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x66938  brfalse  loc_66B0A
0x6693d  ldloc.2
0x6693e  switch   loc_66984, loc_6699E, loc_669B8, loc_669D2, loc_669EC, loc_66A06, loc_66A20, loc_66A3A, loc_66A54, loc_66A6E, loc_66A88, loc_66AA2, loc_66ABC, loc_66AD6, loc_66AF0
0x6697f  br       loc_66B0A
0x66984  ldarg.0
0x66985  ldstr    aAllowprint// "AllowPrint"
0x6698a  ldarg.s  4
0x6698c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66991  ldloc.0
0x66992  ldarg.3
0x66993  callvirt T0x2B00000A
0x66998  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_AllowPrint(bool)
0x6699d  ret
0x6699e  ldarg.0
0x6699f  ldstr    aAllowscript// "AllowScript"
0x669a4  ldarg.s  4
0x669a6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x669ab  ldloc.0
0x669ac  ldarg.3
0x669ad  callvirt T0x2B00000A
0x669b2  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_AllowScript(bool)
0x669b7  ret
0x669b8  ldarg.0
0x669b9  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x669be  ldarg.s  4
0x669c0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x669c5  ldloc.0
0x669c6  ldarg.3
0x669c7  callvirt T0x2B00000A
0x669cc  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_AllowWriteCopy(bool)
0x669d1  ret
0x669d2  ldarg.0
0x669d3  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x669d8  ldarg.s  4
0x669da  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x669df  ldloc.0
0x669e0  ldarg.3
0x669e1  callvirt T0x2B00000A
0x669e6  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_DisableDocumentBrowserView(bool)
0x669eb  ret
0x669ec  ldarg.0
0x669ed  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x669f2  ldarg.s  4
0x669f4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x669f9  ldloc.0
0x669fa  ldarg.3
0x669fb  callvirt T0x2B000009
0x66a00  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_DocumentAccessExpireDays(int32)
0x66a05  ret
0x66a06  ldarg.0
0x66a07  ldstr    aDocumentlibrar// "DocumentLibraryProtectionExpireDate"
0x66a0c  ldarg.s  4
0x66a0e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66a13  ldloc.0
0x66a14  ldarg.3
0x66a15  callvirt T0x2B000045
0x66a1a  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_DocumentLibraryProtectionExpireDate(valuetype [mscorlib]System.DateTime)
0x66a1f  ret
0x66a20  ldarg.0
0x66a21  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x66a26  ldarg.s  4
0x66a28  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66a2d  ldloc.0
0x66a2e  ldarg.3
0x66a2f  callvirt T0x2B00000A
0x66a34  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_EnableDocumentAccessExpire(bool)
0x66a39  ret
0x66a3a  ldarg.0
0x66a3b  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x66a40  ldarg.s  4
0x66a42  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66a47  ldloc.0
0x66a48  ldarg.3
0x66a49  callvirt T0x2B00000A
0x66a4e  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_EnableDocumentBrowserPublishingView(bool)
0x66a53  ret
0x66a54  ldarg.0
0x66a55  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x66a5a  ldarg.s  4
0x66a5c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66a61  ldloc.0
0x66a62  ldarg.3
0x66a63  callvirt T0x2B00000A
0x66a68  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_EnableGroupProtection(bool)
0x66a6d  ret
0x66a6e  ldarg.0
0x66a6f  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x66a74  ldarg.s  4
0x66a76  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66a7b  ldloc.0
0x66a7c  ldarg.3
0x66a7d  callvirt T0x2B00000A
0x66a82  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_EnableLicenseCacheExpire(bool)
0x66a87  ret
0x66a88  ldarg.0
0x66a89  ldstr    aGroupname// "GroupName"
0x66a8e  ldarg.s  4
0x66a90  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66a95  ldloc.0
0x66a96  ldarg.3
0x66a97  callvirt T0x2B000008
0x66a9c  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_GroupName(string)
0x66aa1  ret
0x66aa2  ldarg.0
0x66aa3  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x66aa8  ldarg.s  4
0x66aaa  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66aaf  ldloc.0
0x66ab0  ldarg.3
0x66ab1  callvirt T0x2B000009
0x66ab6  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_LicenseCacheExpireDays(int32)
0x66abb  ret
0x66abc  ldarg.0
0x66abd  ldstr    aPolicydescript// "PolicyDescription"
0x66ac2  ldarg.s  4
0x66ac4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66ac9  ldloc.0
0x66aca  ldarg.3
0x66acb  callvirt T0x2B000008
0x66ad0  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_PolicyDescription(string)
0x66ad5  ret
0x66ad6  ldarg.0
0x66ad7  ldstr    aPolicytitle// "PolicyTitle"
0x66adc  ldarg.s  4
0x66ade  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66ae3  ldloc.0
0x66ae4  ldarg.3
0x66ae5  callvirt T0x2B000008
0x66aea  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_PolicyTitle(string)
0x66aef  ret
0x66af0  ldarg.0
0x66af1  ldstr    aTemplateid// "TemplateId"
0x66af6  ldarg.s  4
0x66af8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66afd  ldloc.0
0x66afe  ldarg.3
0x66aff  callvirt T0x2B000008
0x66b04  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_TemplateId(string)
0x66b09  ret
0x66b0a  ldarg.0
0x66b0b  ldarg.1
0x66b0c  ldarg.2
0x66b0d  ldarg.3
0x66b0e  ldarg.s  4
0x66b10  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::SetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValue, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66b15  ret
```
