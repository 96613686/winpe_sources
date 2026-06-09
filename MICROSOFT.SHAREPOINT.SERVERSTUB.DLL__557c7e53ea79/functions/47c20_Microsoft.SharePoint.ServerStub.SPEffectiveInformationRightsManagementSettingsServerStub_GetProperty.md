# Microsoft.SharePoint.ServerStub.SPEffectiveInformationRightsManagementSettingsServerStub::GetProperty

- ea: `0x47c20`
- end: `0x47f42`
- name: `Microsoft.SharePoint.ServerStub.SPEffectiveInformationRightsManagementSettingsServerStub::GetProperty`
- size: `802`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x47c20`

## string_xrefs

- `0x47c8f`: `AllowWriteCopy`
- `0x47de5`: `AllowWriteCopy`
- `0x47ca7`: `DocumentAccessExpireDays`
- `0x47e15`: `DocumentAccessExpireDays`
- `0x47cbf`: `EnableDocumentAccessExpire`
- `0x47e45`: `EnableDocumentAccessExpire`
- `0x47ce3`: `EnableLicenseCacheExpire`
- `0x47e8d`: `EnableLicenseCacheExpire`
- `0x47d0a`: `LicenseCacheExpireDays`
- `0x47ed0`: `LicenseCacheExpireDays`
- `0x47d3e`: `TemplateId`
- `0x47f26`: `TemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x47c20  ldarg.2
0x47c21  brtrue.s loc_47C2E
0x47c23  ldstr    aPropname// "propName"
0x47c28  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x47c2d  throw
0x47c2e  ldarg.3
0x47c2f  brtrue.s loc_47C3C
0x47c31  ldstr    aProxycontext// "proxyContext"
0x47c36  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x47c3b  throw
0x47c3c  ldarg.1
0x47c3d  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings
0x47c42  stloc.0
0x47c43  ldloc.0
0x47c44  brtrue.s loc_47C51
0x47c46  ldstr    aTarget// "target"
0x47c4b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x47c50  throw
0x47c51  ldarg.0
0x47c52  ldarg.2
0x47c53  ldarg.3
0x47c54  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x47c59  starg.s  2
0x47c5b  ldarg.2
0x47c5c  dup
0x47c5d  stloc.1
0x47c5e  brfalse  loc_47F38
0x47c63  volatile.
0x47c65  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000d4a-1
0x47c6a  brtrue   loc_47D51
0x47c6f  ldc.i4.s 0x11
0x47c71  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x47c76  dup
0x47c77  ldstr    aAllowprint// "AllowPrint"
0x47c7c  ldc.i4.0
0x47c7d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x47c82  dup
0x47c83  ldstr    aAllowscript// "AllowScript"
0x47c88  ldc.i4.1
0x47c89  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x47c8e  dup
0x47c8f  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x47c94  ldc.i4.2
0x47c95  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x47c9a  dup
0x47c9b  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x47ca0  ldc.i4.3
0x47ca1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x47ca6  dup
0x47ca7  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x47cac  ldc.i4.4
0x47cad  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x47cb2  dup
0x47cb3  ldstr    aDocumentlibrar// "DocumentLibraryProtectionExpireDate"
0x47cb8  ldc.i4.5
0x47cb9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x47cbe  dup
0x47cbf  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x47cc4  ldc.i4.6
0x47cc5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x47cca  dup
0x47ccb  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x47cd0  ldc.i4.7
0x47cd1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x47cd6  dup
0x47cd7  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x47cdc  ldc.i4.8
0x47cdd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x47ce2  dup
0x47ce3  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x47ce8  ldc.i4.s 9
0x47cea  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x47cef  dup
0x47cf0  ldstr    aGroupname// "GroupName"
0x47cf5  ldc.i4.s 0xA
0x47cf7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x47cfc  dup
0x47cfd  ldstr    aIrmenabled// "IrmEnabled"
0x47d02  ldc.i4.s 0xB
0x47d04  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x47d09  dup
0x47d0a  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x47d0f  ldc.i4.s 0xC
0x47d11  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x47d16  dup
0x47d17  ldstr    aPolicydescript// "PolicyDescription"
0x47d1c  ldc.i4.s 0xD
0x47d1e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x47d23  dup
0x47d24  ldstr    aPolicytitle// "PolicyTitle"
0x47d29  ldc.i4.s 0xE
0x47d2b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x47d30  dup
0x47d31  ldstr    aSettingsource// "SettingSource"
0x47d36  ldc.i4.s 0xF
0x47d38  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x47d3d  dup
0x47d3e  ldstr    aTemplateid// "TemplateId"
0x47d43  ldc.i4.s 0x10
0x47d45  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x47d4a  volatile.
0x47d4c  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000d4a-1
0x47d51  volatile.
0x47d53  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000d4a-1
0x47d58  ldloc.1
0x47d59  ldloca.s 2
0x47d5b  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x47d60  brfalse  loc_47F38
0x47d65  ldloc.2
0x47d66  switch   loc_47DB4, loc_47DCC, loc_47DE4, loc_47DFC, loc_47E14, loc_47E2C, loc_47E44, loc_47E5C, loc_47E74, loc_47E8C, loc_47EA4, loc_47EB7, loc_47ECF, loc_47EE7, loc_47EFA, loc_47F0D, loc_47F25
0x47daf  br       loc_47F38
0x47db4  ldarg.0
0x47db5  ldstr    aAllowprint// "AllowPrint"
0x47dba  ldarg.3
0x47dbb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x47dc0  ldloc.0
0x47dc1  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_AllowPrint()
0x47dc6  box      [mscorlib]System.Boolean
0x47dcb  ret
0x47dcc  ldarg.0
0x47dcd  ldstr    aAllowscript// "AllowScript"
0x47dd2  ldarg.3
0x47dd3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x47dd8  ldloc.0
0x47dd9  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_AllowScript()
0x47dde  box      [mscorlib]System.Boolean
0x47de3  ret
0x47de4  ldarg.0
0x47de5  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x47dea  ldarg.3
0x47deb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x47df0  ldloc.0
0x47df1  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_AllowWriteCopy()
0x47df6  box      [mscorlib]System.Boolean
0x47dfb  ret
0x47dfc  ldarg.0
0x47dfd  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x47e02  ldarg.3
0x47e03  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x47e08  ldloc.0
0x47e09  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_DisableDocumentBrowserView()
0x47e0e  box      [mscorlib]System.Boolean
0x47e13  ret
0x47e14  ldarg.0
0x47e15  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x47e1a  ldarg.3
0x47e1b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x47e20  ldloc.0
0x47e21  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_DocumentAccessExpireDays()
0x47e26  box      [mscorlib]System.Int32
0x47e2b  ret
0x47e2c  ldarg.0
0x47e2d  ldstr    aDocumentlibrar// "DocumentLibraryProtectionExpireDate"
0x47e32  ldarg.3
0x47e33  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x47e38  ldloc.0
0x47e39  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_DocumentLibraryProtectionExpireDate()
0x47e3e  box      [mscorlib]System.DateTime
0x47e43  ret
0x47e44  ldarg.0
0x47e45  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x47e4a  ldarg.3
0x47e4b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x47e50  ldloc.0
0x47e51  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_EnableDocumentAccessExpire()
0x47e56  box      [mscorlib]System.Boolean
0x47e5b  ret
0x47e5c  ldarg.0
0x47e5d  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x47e62  ldarg.3
0x47e63  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x47e68  ldloc.0
0x47e69  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_EnableDocumentBrowserPublishingView()
0x47e6e  box      [mscorlib]System.Boolean
0x47e73  ret
0x47e74  ldarg.0
0x47e75  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x47e7a  ldarg.3
0x47e7b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x47e80  ldloc.0
0x47e81  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_EnableGroupProtection()
0x47e86  box      [mscorlib]System.Boolean
0x47e8b  ret
0x47e8c  ldarg.0
0x47e8d  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x47e92  ldarg.3
0x47e93  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x47e98  ldloc.0
0x47e99  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_EnableLicenseCacheExpire()
0x47e9e  box      [mscorlib]System.Boolean
0x47ea3  ret
0x47ea4  ldarg.0
0x47ea5  ldstr    aGroupname// "GroupName"
0x47eaa  ldarg.3
0x47eab  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x47eb0  ldloc.0
0x47eb1  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_GroupName()
0x47eb6  ret
0x47eb7  ldarg.0
0x47eb8  ldstr    aIrmenabled// "IrmEnabled"
0x47ebd  ldarg.3
0x47ebe  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x47ec3  ldloc.0
0x47ec4  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_IrmEnabled()
0x47ec9  box      [mscorlib]System.Boolean
0x47ece  ret
0x47ecf  ldarg.0
0x47ed0  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x47ed5  ldarg.3
0x47ed6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x47edb  ldloc.0
0x47edc  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_LicenseCacheExpireDays()
0x47ee1  box      [mscorlib]System.Int32
0x47ee6  ret
0x47ee7  ldarg.0
0x47ee8  ldstr    aPolicydescript// "PolicyDescription"
0x47eed  ldarg.3
0x47eee  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x47ef3  ldloc.0
0x47ef4  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_PolicyDescription()
0x47ef9  ret
0x47efa  ldarg.0
0x47efb  ldstr    aPolicytitle// "PolicyTitle"
0x47f00  ldarg.3
0x47f01  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x47f06  ldloc.0
0x47f07  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_PolicyTitle()
0x47f0c  ret
0x47f0d  ldarg.0
0x47f0e  ldstr    aSettingsource// "SettingSource"
0x47f13  ldarg.3
0x47f14  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x47f19  ldloc.0
0x47f1a  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettingsSource [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_SettingSource()
0x47f1f  box      [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettingsSource
0x47f24  ret
0x47f25  ldarg.0
0x47f26  ldstr    aTemplateid// "TemplateId"
0x47f2b  ldarg.3
0x47f2c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x47f31  ldloc.0
0x47f32  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_TemplateId()
0x47f37  ret
0x47f38  ldarg.0
0x47f39  ldarg.1
0x47f3a  ldarg.2
0x47f3b  ldarg.3
0x47f3c  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x47f41  ret
```
