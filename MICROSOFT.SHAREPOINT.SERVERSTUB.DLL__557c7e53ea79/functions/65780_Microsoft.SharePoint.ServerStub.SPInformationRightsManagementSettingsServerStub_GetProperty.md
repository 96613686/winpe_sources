# Microsoft.SharePoint.ServerStub.SPInformationRightsManagementSettingsServerStub::GetProperty

- ea: `0x65780`
- end: `0x65a50`
- name: `Microsoft.SharePoint.ServerStub.SPInformationRightsManagementSettingsServerStub::GetProperty`
- size: `720`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x65780`

## string_xrefs

- `0x657ef`: `AllowWriteCopy`
- `0x65923`: `AllowWriteCopy`
- `0x65807`: `DocumentAccessExpireDays`
- `0x65953`: `DocumentAccessExpireDays`
- `0x6581f`: `EnableDocumentAccessExpire`
- `0x65983`: `EnableDocumentAccessExpire`
- `0x65843`: `EnableLicenseCacheExpire`
- `0x659cb`: `EnableLicenseCacheExpire`
- `0x6585d`: `LicenseCacheExpireDays`
- `0x659f6`: `LicenseCacheExpireDays`
- `0x65884`: `TemplateId`
- `0x65a34`: `TemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x65780  ldarg.2
0x65781  brtrue.s loc_6578E
0x65783  ldstr    aPropname// "propName"
0x65788  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6578d  throw
0x6578e  ldarg.3
0x6578f  brtrue.s loc_6579C
0x65791  ldstr    aProxycontext// "proxyContext"
0x65796  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6579b  throw
0x6579c  ldarg.1
0x6579d  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings
0x657a2  stloc.0
0x657a3  ldloc.0
0x657a4  brtrue.s loc_657B1
0x657a6  ldstr    aTarget// "target"
0x657ab  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x657b0  throw
0x657b1  ldarg.0
0x657b2  ldarg.2
0x657b3  ldarg.3
0x657b4  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x657b9  starg.s  2
0x657bb  ldarg.2
0x657bc  dup
0x657bd  stloc.1
0x657be  brfalse  loc_65A46
0x657c3  volatile.
0x657c5  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60011d3-1
0x657ca  brtrue   loc_65897
0x657cf  ldc.i4.s 0xF
0x657d1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x657d6  dup
0x657d7  ldstr    aAllowprint// "AllowPrint"
0x657dc  ldc.i4.0
0x657dd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x657e2  dup
0x657e3  ldstr    aAllowscript// "AllowScript"
0x657e8  ldc.i4.1
0x657e9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x657ee  dup
0x657ef  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x657f4  ldc.i4.2
0x657f5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x657fa  dup
0x657fb  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x65800  ldc.i4.3
0x65801  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65806  dup
0x65807  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x6580c  ldc.i4.4
0x6580d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65812  dup
0x65813  ldstr    aDocumentlibrar// "DocumentLibraryProtectionExpireDate"
0x65818  ldc.i4.5
0x65819  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6581e  dup
0x6581f  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x65824  ldc.i4.6
0x65825  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6582a  dup
0x6582b  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x65830  ldc.i4.7
0x65831  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65836  dup
0x65837  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x6583c  ldc.i4.8
0x6583d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65842  dup
0x65843  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x65848  ldc.i4.s 9
0x6584a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6584f  dup
0x65850  ldstr    aGroupname// "GroupName"
0x65855  ldc.i4.s 0xA
0x65857  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6585c  dup
0x6585d  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x65862  ldc.i4.s 0xB
0x65864  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65869  dup
0x6586a  ldstr    aPolicydescript// "PolicyDescription"
0x6586f  ldc.i4.s 0xC
0x65871  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65876  dup
0x65877  ldstr    aPolicytitle// "PolicyTitle"
0x6587c  ldc.i4.s 0xD
0x6587e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65883  dup
0x65884  ldstr    aTemplateid// "TemplateId"
0x65889  ldc.i4.s 0xE
0x6588b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65890  volatile.
0x65892  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60011d3-1
0x65897  volatile.
0x65899  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60011d3-1
0x6589e  ldloc.1
0x6589f  ldloca.s 2
0x658a1  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x658a6  brfalse  loc_65A46
0x658ab  ldloc.2
0x658ac  switch   loc_658F2, loc_6590A, loc_65922, loc_6593A, loc_65952, loc_6596A, loc_65982, loc_6599A, loc_659B2, loc_659CA, loc_659E2, loc_659F5, loc_65A0D, loc_65A20, loc_65A33
0x658ed  br       loc_65A46
0x658f2  ldarg.0
0x658f3  ldstr    aAllowprint// "AllowPrint"
0x658f8  ldarg.3
0x658f9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x658fe  ldloc.0
0x658ff  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_AllowPrint()
0x65904  box      [mscorlib]System.Boolean
0x65909  ret
0x6590a  ldarg.0
0x6590b  ldstr    aAllowscript// "AllowScript"
0x65910  ldarg.3
0x65911  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65916  ldloc.0
0x65917  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_AllowScript()
0x6591c  box      [mscorlib]System.Boolean
0x65921  ret
0x65922  ldarg.0
0x65923  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x65928  ldarg.3
0x65929  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6592e  ldloc.0
0x6592f  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_AllowWriteCopy()
0x65934  box      [mscorlib]System.Boolean
0x65939  ret
0x6593a  ldarg.0
0x6593b  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x65940  ldarg.3
0x65941  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65946  ldloc.0
0x65947  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_DisableDocumentBrowserView()
0x6594c  box      [mscorlib]System.Boolean
0x65951  ret
0x65952  ldarg.0
0x65953  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x65958  ldarg.3
0x65959  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6595e  ldloc.0
0x6595f  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_DocumentAccessExpireDays()
0x65964  box      [mscorlib]System.Int32
0x65969  ret
0x6596a  ldarg.0
0x6596b  ldstr    aDocumentlibrar// "DocumentLibraryProtectionExpireDate"
0x65970  ldarg.3
0x65971  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65976  ldloc.0
0x65977  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_DocumentLibraryProtectionExpireDate()
0x6597c  box      [mscorlib]System.DateTime
0x65981  ret
0x65982  ldarg.0
0x65983  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x65988  ldarg.3
0x65989  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6598e  ldloc.0
0x6598f  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_EnableDocumentAccessExpire()
0x65994  box      [mscorlib]System.Boolean
0x65999  ret
0x6599a  ldarg.0
0x6599b  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x659a0  ldarg.3
0x659a1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x659a6  ldloc.0
0x659a7  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_EnableDocumentBrowserPublishingView()
0x659ac  box      [mscorlib]System.Boolean
0x659b1  ret
0x659b2  ldarg.0
0x659b3  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x659b8  ldarg.3
0x659b9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x659be  ldloc.0
0x659bf  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_EnableGroupProtection()
0x659c4  box      [mscorlib]System.Boolean
0x659c9  ret
0x659ca  ldarg.0
0x659cb  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x659d0  ldarg.3
0x659d1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x659d6  ldloc.0
0x659d7  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_EnableLicenseCacheExpire()
0x659dc  box      [mscorlib]System.Boolean
0x659e1  ret
0x659e2  ldarg.0
0x659e3  ldstr    aGroupname// "GroupName"
0x659e8  ldarg.3
0x659e9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x659ee  ldloc.0
0x659ef  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_GroupName()
0x659f4  ret
0x659f5  ldarg.0
0x659f6  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x659fb  ldarg.3
0x659fc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65a01  ldloc.0
0x65a02  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_LicenseCacheExpireDays()
0x65a07  box      [mscorlib]System.Int32
0x65a0c  ret
0x65a0d  ldarg.0
0x65a0e  ldstr    aPolicydescript// "PolicyDescription"
0x65a13  ldarg.3
0x65a14  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65a19  ldloc.0
0x65a1a  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_PolicyDescription()
0x65a1f  ret
0x65a20  ldarg.0
0x65a21  ldstr    aPolicytitle// "PolicyTitle"
0x65a26  ldarg.3
0x65a27  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65a2c  ldloc.0
0x65a2d  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_PolicyTitle()
0x65a32  ret
0x65a33  ldarg.0
0x65a34  ldstr    aTemplateid// "TemplateId"
0x65a39  ldarg.3
0x65a3a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65a3f  ldloc.0
0x65a40  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_TemplateId()
0x65a45  ret
0x65a46  ldarg.0
0x65a47  ldarg.1
0x65a48  ldarg.2
0x65a49  ldarg.3
0x65a4a  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65a4f  ret
```
