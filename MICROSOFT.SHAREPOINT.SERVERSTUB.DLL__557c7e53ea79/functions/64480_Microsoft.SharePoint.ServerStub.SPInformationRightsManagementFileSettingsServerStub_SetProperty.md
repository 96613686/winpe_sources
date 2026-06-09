# Microsoft.SharePoint.ServerStub.SPInformationRightsManagementFileSettingsServerStub::SetProperty

- ea: `0x64480`
- end: `0x647a4`
- name: `Microsoft.SharePoint.ServerStub.SPInformationRightsManagementFileSettingsServerStub::SetProperty`
- size: `804`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x64480`

## string_xrefs

- `0x644f1`: `AllowWriteCopy`
- `0x6462d`: `AllowWriteCopy`
- `0x64509`: `DocumentAccessExpireDays`
- `0x64665`: `DocumentAccessExpireDays`
- `0x64515`: `EnableDocumentAccessExpire`
- `0x64681`: `EnableDocumentAccessExpire`
- `0x64539`: `EnableLicenseCacheExpire`
- `0x646d5`: `EnableLicenseCacheExpire`
- `0x6455f`: `LicenseCacheExpireDays`
- `0x64729`: `LicenseCacheExpireDays`
- `0x64586`: `TemplateId`
- `0x6477d`: `TemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x64480  ldarg.s  4
0x64482  brtrue.s loc_6448F
0x64484  ldstr    aProxycontext// "proxyContext"
0x64489  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6448e  throw
0x6448f  ldarg.1
0x64490  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings
0x64495  stloc.0
0x64496  ldloc.0
0x64497  brtrue.s loc_644A4
0x64499  ldstr    aTarget// "target"
0x6449e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x644a3  throw
0x644a4  ldarg.2
0x644a5  brtrue.s loc_644B2
0x644a7  ldstr    aPropname// "propName"
0x644ac  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x644b1  throw
0x644b2  ldarg.0
0x644b3  ldarg.2
0x644b4  ldarg.s  4
0x644b6  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x644bb  starg.s  2
0x644bd  ldarg.2
0x644be  dup
0x644bf  stloc.1
0x644c0  brfalse  loc_64798
0x644c5  volatile.
0x644c7  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60011be-1
0x644cc  brtrue   loc_64599
0x644d1  ldc.i4.s 0xF
0x644d3  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x644d8  dup
0x644d9  ldstr    aAllowprint// "AllowPrint"
0x644de  ldc.i4.0
0x644df  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x644e4  dup
0x644e5  ldstr    aAllowscript// "AllowScript"
0x644ea  ldc.i4.1
0x644eb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x644f0  dup
0x644f1  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x644f6  ldc.i4.2
0x644f7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x644fc  dup
0x644fd  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x64502  ldc.i4.3
0x64503  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64508  dup
0x64509  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x6450e  ldc.i4.4
0x6450f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64514  dup
0x64515  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x6451a  ldc.i4.5
0x6451b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64520  dup
0x64521  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x64526  ldc.i4.6
0x64527  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6452c  dup
0x6452d  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x64532  ldc.i4.7
0x64533  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64538  dup
0x64539  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x6453e  ldc.i4.8
0x6453f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64544  dup
0x64545  ldstr    aGroupname// "GroupName"
0x6454a  ldc.i4.s 9
0x6454c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64551  dup
0x64552  ldstr    aIrmenabled// "IrmEnabled"
0x64557  ldc.i4.s 0xA
0x64559  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6455e  dup
0x6455f  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x64564  ldc.i4.s 0xB
0x64566  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6456b  dup
0x6456c  ldstr    aPolicydescript// "PolicyDescription"
0x64571  ldc.i4.s 0xC
0x64573  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64578  dup
0x64579  ldstr    aPolicytitle// "PolicyTitle"
0x6457e  ldc.i4.s 0xD
0x64580  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64585  dup
0x64586  ldstr    aTemplateid// "TemplateId"
0x6458b  ldc.i4.s 0xE
0x6458d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64592  volatile.
0x64594  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60011be-1
0x64599  volatile.
0x6459b  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60011be-1
0x645a0  ldloc.1
0x645a1  ldloca.s 2
0x645a3  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x645a8  brfalse  loc_64798
0x645ad  ldloc.2
0x645ae  switch   loc_645F4, loc_64610, loc_6462C, loc_64648, loc_64664, loc_64680, loc_6469C, loc_646B8, loc_646D4, loc_646F0, loc_6470C, loc_64728, loc_64744, loc_64760, loc_6477C
0x645ef  br       loc_64798
0x645f4  ldarg.0
0x645f5  ldstr    aAllowprint// "AllowPrint"
0x645fa  ldarg.s  4
0x645fc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64601  ldloc.0
0x64602  ldarg.3
0x64603  ldarg.s  4
0x64605  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6460a  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_AllowPrint(bool)
0x6460f  ret
0x64610  ldarg.0
0x64611  ldstr    aAllowscript// "AllowScript"
0x64616  ldarg.s  4
0x64618  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6461d  ldloc.0
0x6461e  ldarg.3
0x6461f  ldarg.s  4
0x64621  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64626  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_AllowScript(bool)
0x6462b  ret
0x6462c  ldarg.0
0x6462d  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x64632  ldarg.s  4
0x64634  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64639  ldloc.0
0x6463a  ldarg.3
0x6463b  ldarg.s  4
0x6463d  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64642  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_AllowWriteCopy(bool)
0x64647  ret
0x64648  ldarg.0
0x64649  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x6464e  ldarg.s  4
0x64650  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64655  ldloc.0
0x64656  ldarg.3
0x64657  ldarg.s  4
0x64659  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6465e  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_DisableDocumentBrowserView(bool)
0x64663  ret
0x64664  ldarg.0
0x64665  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x6466a  ldarg.s  4
0x6466c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64671  ldloc.0
0x64672  ldarg.3
0x64673  ldarg.s  4
0x64675  call     int32 [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToInt32(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6467a  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_DocumentAccessExpireDays(int32)
0x6467f  ret
0x64680  ldarg.0
0x64681  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x64686  ldarg.s  4
0x64688  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6468d  ldloc.0
0x6468e  ldarg.3
0x6468f  ldarg.s  4
0x64691  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64696  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_EnableDocumentAccessExpire(bool)
0x6469b  ret
0x6469c  ldarg.0
0x6469d  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x646a2  ldarg.s  4
0x646a4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x646a9  ldloc.0
0x646aa  ldarg.3
0x646ab  ldarg.s  4
0x646ad  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x646b2  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_EnableDocumentBrowserPublishingView(bool)
0x646b7  ret
0x646b8  ldarg.0
0x646b9  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x646be  ldarg.s  4
0x646c0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x646c5  ldloc.0
0x646c6  ldarg.3
0x646c7  ldarg.s  4
0x646c9  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x646ce  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_EnableGroupProtection(bool)
0x646d3  ret
0x646d4  ldarg.0
0x646d5  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x646da  ldarg.s  4
0x646dc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x646e1  ldloc.0
0x646e2  ldarg.3
0x646e3  ldarg.s  4
0x646e5  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x646ea  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_EnableLicenseCacheExpire(bool)
0x646ef  ret
0x646f0  ldarg.0
0x646f1  ldstr    aGroupname// "GroupName"
0x646f6  ldarg.s  4
0x646f8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x646fd  ldloc.0
0x646fe  ldarg.3
0x646ff  ldarg.s  4
0x64701  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64706  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_GroupName(string)
0x6470b  ret
0x6470c  ldarg.0
0x6470d  ldstr    aIrmenabled// "IrmEnabled"
0x64712  ldarg.s  4
0x64714  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64719  ldloc.0
0x6471a  ldarg.3
0x6471b  ldarg.s  4
0x6471d  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64722  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_IrmEnabled(bool)
0x64727  ret
0x64728  ldarg.0
0x64729  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x6472e  ldarg.s  4
0x64730  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64735  ldloc.0
0x64736  ldarg.3
0x64737  ldarg.s  4
0x64739  call     int32 [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToInt32(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6473e  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_LicenseCacheExpireDays(int32)
0x64743  ret
0x64744  ldarg.0
0x64745  ldstr    aPolicydescript// "PolicyDescription"
0x6474a  ldarg.s  4
0x6474c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64751  ldloc.0
0x64752  ldarg.3
0x64753  ldarg.s  4
0x64755  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6475a  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_PolicyDescription(string)
0x6475f  ret
0x64760  ldarg.0
0x64761  ldstr    aPolicytitle// "PolicyTitle"
0x64766  ldarg.s  4
0x64768  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6476d  ldloc.0
0x6476e  ldarg.3
0x6476f  ldarg.s  4
0x64771  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64776  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_PolicyTitle(string)
0x6477b  ret
0x6477c  ldarg.0
0x6477d  ldstr    aTemplateid// "TemplateId"
0x64782  ldarg.s  4
0x64784  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64789  ldloc.0
0x6478a  ldarg.3
0x6478b  ldarg.s  4
0x6478d  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64792  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::set_TemplateId(string)
0x64797  ret
0x64798  ldarg.0
0x64799  ldarg.1
0x6479a  ldarg.2
0x6479b  ldarg.3
0x6479c  ldarg.s  4
0x6479e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::SetProperty(object, string, class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x647a3  ret
```
