# Microsoft.SharePoint.ServerStub.SPInformationRightsManagementFileSettingsServerStub::GetProperty

- ea: `0x641b0`
- end: `0x64480`
- name: `Microsoft.SharePoint.ServerStub.SPInformationRightsManagementFileSettingsServerStub::GetProperty`
- size: `720`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x641b0`

## string_xrefs

- `0x6421f`: `AllowWriteCopy`
- `0x64353`: `AllowWriteCopy`
- `0x64237`: `DocumentAccessExpireDays`
- `0x64383`: `DocumentAccessExpireDays`
- `0x64243`: `EnableDocumentAccessExpire`
- `0x6439b`: `EnableDocumentAccessExpire`
- `0x64267`: `EnableLicenseCacheExpire`
- `0x643e3`: `EnableLicenseCacheExpire`
- `0x6428d`: `LicenseCacheExpireDays`
- `0x64426`: `LicenseCacheExpireDays`
- `0x642b4`: `TemplateId`
- `0x64464`: `TemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x641b0  ldarg.2
0x641b1  brtrue.s loc_641BE
0x641b3  ldstr    aPropname// "propName"
0x641b8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x641bd  throw
0x641be  ldarg.3
0x641bf  brtrue.s loc_641CC
0x641c1  ldstr    aProxycontext// "proxyContext"
0x641c6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x641cb  throw
0x641cc  ldarg.1
0x641cd  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings
0x641d2  stloc.0
0x641d3  ldloc.0
0x641d4  brtrue.s loc_641E1
0x641d6  ldstr    aTarget// "target"
0x641db  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x641e0  throw
0x641e1  ldarg.0
0x641e2  ldarg.2
0x641e3  ldarg.3
0x641e4  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x641e9  starg.s  2
0x641eb  ldarg.2
0x641ec  dup
0x641ed  stloc.1
0x641ee  brfalse  loc_64476
0x641f3  volatile.
0x641f5  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60011bd-1
0x641fa  brtrue   loc_642C7
0x641ff  ldc.i4.s 0xF
0x64201  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x64206  dup
0x64207  ldstr    aAllowprint// "AllowPrint"
0x6420c  ldc.i4.0
0x6420d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64212  dup
0x64213  ldstr    aAllowscript// "AllowScript"
0x64218  ldc.i4.1
0x64219  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6421e  dup
0x6421f  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x64224  ldc.i4.2
0x64225  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6422a  dup
0x6422b  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x64230  ldc.i4.3
0x64231  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64236  dup
0x64237  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x6423c  ldc.i4.4
0x6423d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64242  dup
0x64243  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x64248  ldc.i4.5
0x64249  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6424e  dup
0x6424f  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x64254  ldc.i4.6
0x64255  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6425a  dup
0x6425b  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x64260  ldc.i4.7
0x64261  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64266  dup
0x64267  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x6426c  ldc.i4.8
0x6426d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64272  dup
0x64273  ldstr    aGroupname// "GroupName"
0x64278  ldc.i4.s 9
0x6427a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6427f  dup
0x64280  ldstr    aIrmenabled// "IrmEnabled"
0x64285  ldc.i4.s 0xA
0x64287  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6428c  dup
0x6428d  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x64292  ldc.i4.s 0xB
0x64294  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64299  dup
0x6429a  ldstr    aPolicydescript// "PolicyDescription"
0x6429f  ldc.i4.s 0xC
0x642a1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x642a6  dup
0x642a7  ldstr    aPolicytitle// "PolicyTitle"
0x642ac  ldc.i4.s 0xD
0x642ae  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x642b3  dup
0x642b4  ldstr    aTemplateid// "TemplateId"
0x642b9  ldc.i4.s 0xE
0x642bb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x642c0  volatile.
0x642c2  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60011bd-1
0x642c7  volatile.
0x642c9  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60011bd-1
0x642ce  ldloc.1
0x642cf  ldloca.s 2
0x642d1  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x642d6  brfalse  loc_64476
0x642db  ldloc.2
0x642dc  switch   loc_64322, loc_6433A, loc_64352, loc_6436A, loc_64382, loc_6439A, loc_643B2, loc_643CA, loc_643E2, loc_643FA, loc_6440D, loc_64425, loc_6443D, loc_64450, loc_64463
0x6431d  br       loc_64476
0x64322  ldarg.0
0x64323  ldstr    aAllowprint// "AllowPrint"
0x64328  ldarg.3
0x64329  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6432e  ldloc.0
0x6432f  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_AllowPrint()
0x64334  box      [mscorlib]System.Boolean
0x64339  ret
0x6433a  ldarg.0
0x6433b  ldstr    aAllowscript// "AllowScript"
0x64340  ldarg.3
0x64341  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64346  ldloc.0
0x64347  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_AllowScript()
0x6434c  box      [mscorlib]System.Boolean
0x64351  ret
0x64352  ldarg.0
0x64353  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x64358  ldarg.3
0x64359  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6435e  ldloc.0
0x6435f  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_AllowWriteCopy()
0x64364  box      [mscorlib]System.Boolean
0x64369  ret
0x6436a  ldarg.0
0x6436b  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x64370  ldarg.3
0x64371  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64376  ldloc.0
0x64377  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_DisableDocumentBrowserView()
0x6437c  box      [mscorlib]System.Boolean
0x64381  ret
0x64382  ldarg.0
0x64383  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x64388  ldarg.3
0x64389  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6438e  ldloc.0
0x6438f  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_DocumentAccessExpireDays()
0x64394  box      [mscorlib]System.Int32
0x64399  ret
0x6439a  ldarg.0
0x6439b  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x643a0  ldarg.3
0x643a1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x643a6  ldloc.0
0x643a7  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_EnableDocumentAccessExpire()
0x643ac  box      [mscorlib]System.Boolean
0x643b1  ret
0x643b2  ldarg.0
0x643b3  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x643b8  ldarg.3
0x643b9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x643be  ldloc.0
0x643bf  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_EnableDocumentBrowserPublishingView()
0x643c4  box      [mscorlib]System.Boolean
0x643c9  ret
0x643ca  ldarg.0
0x643cb  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x643d0  ldarg.3
0x643d1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x643d6  ldloc.0
0x643d7  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_EnableGroupProtection()
0x643dc  box      [mscorlib]System.Boolean
0x643e1  ret
0x643e2  ldarg.0
0x643e3  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x643e8  ldarg.3
0x643e9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x643ee  ldloc.0
0x643ef  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_EnableLicenseCacheExpire()
0x643f4  box      [mscorlib]System.Boolean
0x643f9  ret
0x643fa  ldarg.0
0x643fb  ldstr    aGroupname// "GroupName"
0x64400  ldarg.3
0x64401  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64406  ldloc.0
0x64407  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_GroupName()
0x6440c  ret
0x6440d  ldarg.0
0x6440e  ldstr    aIrmenabled// "IrmEnabled"
0x64413  ldarg.3
0x64414  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64419  ldloc.0
0x6441a  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_IrmEnabled()
0x6441f  box      [mscorlib]System.Boolean
0x64424  ret
0x64425  ldarg.0
0x64426  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x6442b  ldarg.3
0x6442c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64431  ldloc.0
0x64432  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_LicenseCacheExpireDays()
0x64437  box      [mscorlib]System.Int32
0x6443c  ret
0x6443d  ldarg.0
0x6443e  ldstr    aPolicydescript// "PolicyDescription"
0x64443  ldarg.3
0x64444  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64449  ldloc.0
0x6444a  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_PolicyDescription()
0x6444f  ret
0x64450  ldarg.0
0x64451  ldstr    aPolicytitle// "PolicyTitle"
0x64456  ldarg.3
0x64457  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6445c  ldloc.0
0x6445d  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_PolicyTitle()
0x64462  ret
0x64463  ldarg.0
0x64464  ldstr    aTemplateid// "TemplateId"
0x64469  ldarg.3
0x6446a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6446f  ldloc.0
0x64470  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_TemplateId()
0x64475  ret
0x64476  ldarg.0
0x64477  ldarg.1
0x64478  ldarg.2
0x64479  ldarg.3
0x6447a  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6447f  ret
```
