# Microsoft.SharePoint.ServerStub.SPInformationRightsManagementSettingsServerStub::SetProperty

- ea: `0x65a50`
- end: `0x65d74`
- name: `Microsoft.SharePoint.ServerStub.SPInformationRightsManagementSettingsServerStub::SetProperty`
- size: `804`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x65a50`

## string_xrefs

- `0x65ac1`: `AllowWriteCopy`
- `0x65bfd`: `AllowWriteCopy`
- `0x65ad9`: `DocumentAccessExpireDays`
- `0x65c35`: `DocumentAccessExpireDays`
- `0x65af1`: `EnableDocumentAccessExpire`
- `0x65c6d`: `EnableDocumentAccessExpire`
- `0x65b15`: `EnableLicenseCacheExpire`
- `0x65cc1`: `EnableLicenseCacheExpire`
- `0x65b2f`: `LicenseCacheExpireDays`
- `0x65cf9`: `LicenseCacheExpireDays`
- `0x65b56`: `TemplateId`
- `0x65d4d`: `TemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x65a50  ldarg.s  4
0x65a52  brtrue.s loc_65A5F
0x65a54  ldstr    aProxycontext// "proxyContext"
0x65a59  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x65a5e  throw
0x65a5f  ldarg.1
0x65a60  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings
0x65a65  stloc.0
0x65a66  ldloc.0
0x65a67  brtrue.s loc_65A74
0x65a69  ldstr    aTarget// "target"
0x65a6e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x65a73  throw
0x65a74  ldarg.2
0x65a75  brtrue.s loc_65A82
0x65a77  ldstr    aPropname// "propName"
0x65a7c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x65a81  throw
0x65a82  ldarg.0
0x65a83  ldarg.2
0x65a84  ldarg.s  4
0x65a86  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65a8b  starg.s  2
0x65a8d  ldarg.2
0x65a8e  dup
0x65a8f  stloc.1
0x65a90  brfalse  loc_65D68
0x65a95  volatile.
0x65a97  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60011d4-1
0x65a9c  brtrue   loc_65B69
0x65aa1  ldc.i4.s 0xF
0x65aa3  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x65aa8  dup
0x65aa9  ldstr    aAllowprint// "AllowPrint"
0x65aae  ldc.i4.0
0x65aaf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65ab4  dup
0x65ab5  ldstr    aAllowscript// "AllowScript"
0x65aba  ldc.i4.1
0x65abb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65ac0  dup
0x65ac1  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x65ac6  ldc.i4.2
0x65ac7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65acc  dup
0x65acd  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x65ad2  ldc.i4.3
0x65ad3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65ad8  dup
0x65ad9  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x65ade  ldc.i4.4
0x65adf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65ae4  dup
0x65ae5  ldstr    aDocumentlibrar// "DocumentLibraryProtectionExpireDate"
0x65aea  ldc.i4.5
0x65aeb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65af0  dup
0x65af1  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x65af6  ldc.i4.6
0x65af7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65afc  dup
0x65afd  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x65b02  ldc.i4.7
0x65b03  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65b08  dup
0x65b09  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x65b0e  ldc.i4.8
0x65b0f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65b14  dup
0x65b15  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x65b1a  ldc.i4.s 9
0x65b1c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65b21  dup
0x65b22  ldstr    aGroupname// "GroupName"
0x65b27  ldc.i4.s 0xA
0x65b29  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65b2e  dup
0x65b2f  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x65b34  ldc.i4.s 0xB
0x65b36  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65b3b  dup
0x65b3c  ldstr    aPolicydescript// "PolicyDescription"
0x65b41  ldc.i4.s 0xC
0x65b43  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65b48  dup
0x65b49  ldstr    aPolicytitle// "PolicyTitle"
0x65b4e  ldc.i4.s 0xD
0x65b50  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65b55  dup
0x65b56  ldstr    aTemplateid// "TemplateId"
0x65b5b  ldc.i4.s 0xE
0x65b5d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65b62  volatile.
0x65b64  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60011d4-1
0x65b69  volatile.
0x65b6b  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60011d4-1
0x65b70  ldloc.1
0x65b71  ldloca.s 2
0x65b73  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x65b78  brfalse  loc_65D68
0x65b7d  ldloc.2
0x65b7e  switch   loc_65BC4, loc_65BE0, loc_65BFC, loc_65C18, loc_65C34, loc_65C50, loc_65C6C, loc_65C88, loc_65CA4, loc_65CC0, loc_65CDC, loc_65CF8, loc_65D14, loc_65D30, loc_65D4C
0x65bbf  br       loc_65D68
0x65bc4  ldarg.0
0x65bc5  ldstr    aAllowprint// "AllowPrint"
0x65bca  ldarg.s  4
0x65bcc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65bd1  ldloc.0
0x65bd2  ldarg.3
0x65bd3  ldarg.s  4
0x65bd5  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65bda  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_AllowPrint(bool)
0x65bdf  ret
0x65be0  ldarg.0
0x65be1  ldstr    aAllowscript// "AllowScript"
0x65be6  ldarg.s  4
0x65be8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65bed  ldloc.0
0x65bee  ldarg.3
0x65bef  ldarg.s  4
0x65bf1  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65bf6  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_AllowScript(bool)
0x65bfb  ret
0x65bfc  ldarg.0
0x65bfd  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x65c02  ldarg.s  4
0x65c04  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65c09  ldloc.0
0x65c0a  ldarg.3
0x65c0b  ldarg.s  4
0x65c0d  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65c12  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_AllowWriteCopy(bool)
0x65c17  ret
0x65c18  ldarg.0
0x65c19  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x65c1e  ldarg.s  4
0x65c20  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65c25  ldloc.0
0x65c26  ldarg.3
0x65c27  ldarg.s  4
0x65c29  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65c2e  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_DisableDocumentBrowserView(bool)
0x65c33  ret
0x65c34  ldarg.0
0x65c35  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x65c3a  ldarg.s  4
0x65c3c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65c41  ldloc.0
0x65c42  ldarg.3
0x65c43  ldarg.s  4
0x65c45  call     int32 [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToInt32(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65c4a  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_DocumentAccessExpireDays(int32)
0x65c4f  ret
0x65c50  ldarg.0
0x65c51  ldstr    aDocumentlibrar// "DocumentLibraryProtectionExpireDate"
0x65c56  ldarg.s  4
0x65c58  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65c5d  ldloc.0
0x65c5e  ldarg.3
0x65c5f  ldarg.s  4
0x65c61  call     valuetype [mscorlib]System.DateTime [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToDateTime(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65c66  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_DocumentLibraryProtectionExpireDate(valuetype [mscorlib]System.DateTime)
0x65c6b  ret
0x65c6c  ldarg.0
0x65c6d  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x65c72  ldarg.s  4
0x65c74  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65c79  ldloc.0
0x65c7a  ldarg.3
0x65c7b  ldarg.s  4
0x65c7d  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65c82  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_EnableDocumentAccessExpire(bool)
0x65c87  ret
0x65c88  ldarg.0
0x65c89  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x65c8e  ldarg.s  4
0x65c90  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65c95  ldloc.0
0x65c96  ldarg.3
0x65c97  ldarg.s  4
0x65c99  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65c9e  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_EnableDocumentBrowserPublishingView(bool)
0x65ca3  ret
0x65ca4  ldarg.0
0x65ca5  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x65caa  ldarg.s  4
0x65cac  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65cb1  ldloc.0
0x65cb2  ldarg.3
0x65cb3  ldarg.s  4
0x65cb5  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65cba  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_EnableGroupProtection(bool)
0x65cbf  ret
0x65cc0  ldarg.0
0x65cc1  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x65cc6  ldarg.s  4
0x65cc8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65ccd  ldloc.0
0x65cce  ldarg.3
0x65ccf  ldarg.s  4
0x65cd1  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65cd6  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_EnableLicenseCacheExpire(bool)
0x65cdb  ret
0x65cdc  ldarg.0
0x65cdd  ldstr    aGroupname// "GroupName"
0x65ce2  ldarg.s  4
0x65ce4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65ce9  ldloc.0
0x65cea  ldarg.3
0x65ceb  ldarg.s  4
0x65ced  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65cf2  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_GroupName(string)
0x65cf7  ret
0x65cf8  ldarg.0
0x65cf9  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x65cfe  ldarg.s  4
0x65d00  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65d05  ldloc.0
0x65d06  ldarg.3
0x65d07  ldarg.s  4
0x65d09  call     int32 [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToInt32(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65d0e  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_LicenseCacheExpireDays(int32)
0x65d13  ret
0x65d14  ldarg.0
0x65d15  ldstr    aPolicydescript// "PolicyDescription"
0x65d1a  ldarg.s  4
0x65d1c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65d21  ldloc.0
0x65d22  ldarg.3
0x65d23  ldarg.s  4
0x65d25  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65d2a  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_PolicyDescription(string)
0x65d2f  ret
0x65d30  ldarg.0
0x65d31  ldstr    aPolicytitle// "PolicyTitle"
0x65d36  ldarg.s  4
0x65d38  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65d3d  ldloc.0
0x65d3e  ldarg.3
0x65d3f  ldarg.s  4
0x65d41  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65d46  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_PolicyTitle(string)
0x65d4b  ret
0x65d4c  ldarg.0
0x65d4d  ldstr    aTemplateid// "TemplateId"
0x65d52  ldarg.s  4
0x65d54  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65d59  ldloc.0
0x65d5a  ldarg.3
0x65d5b  ldarg.s  4
0x65d5d  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65d62  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::set_TemplateId(string)
0x65d67  ret
0x65d68  ldarg.0
0x65d69  ldarg.1
0x65d6a  ldarg.2
0x65d6b  ldarg.3
0x65d6c  ldarg.s  4
0x65d6e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::SetProperty(object, string, class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65d73  ret
```
