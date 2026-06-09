# Microsoft.SharePoint.ServerStub.SPEffectiveInformationRightsManagementSettingsServerStub::WriteOnePropertyValueAsJson

- ea: `0x47f80`
- end: `0x485e7`
- name: `Microsoft.SharePoint.ServerStub.SPEffectiveInformationRightsManagementSettingsServerStub::WriteOnePropertyValueAsJson`
- size: `1639`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x47f80`

## string_xrefs

- `0x47fd0`: `AllowWriteCopy`
- `0x481b2`: `AllowWriteCopy`
- `0x47fe8`: `DocumentAccessExpireDays`
- `0x48246`: `DocumentAccessExpireDays`
- `0x48000`: `EnableDocumentAccessExpire`
- `0x482da`: `EnableDocumentAccessExpire`
- `0x48024`: `EnableLicenseCacheExpire`
- `0x483b8`: `EnableLicenseCacheExpire`
- `0x4804b`: `LicenseCacheExpireDays`
- `0x48496`: `LicenseCacheExpireDays`
- `0x4807f`: `TemplateId`
- `0x485bb`: `TemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x47f80  ldc.i4.0
0x47f81  stloc.0
0x47f82  ldarg.2
0x47f83  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings
0x47f88  stloc.1
0x47f89  ldloc.1
0x47f8a  brtrue.s loc_47F97
0x47f8c  ldstr    aTarget// "target"
0x47f91  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x47f96  throw
0x47f97  ldarg.3
0x47f98  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x47f9d  dup
0x47f9e  stloc.2
0x47f9f  brfalse  loc_485D9
0x47fa4  volatile.
0x47fa6  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000d4c-1
0x47fab  brtrue   loc_48092
0x47fb0  ldc.i4.s 0x11
0x47fb2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x47fb7  dup
0x47fb8  ldstr    aAllowprint// "AllowPrint"
0x47fbd  ldc.i4.0
0x47fbe  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x47fc3  dup
0x47fc4  ldstr    aAllowscript// "AllowScript"
0x47fc9  ldc.i4.1
0x47fca  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x47fcf  dup
0x47fd0  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x47fd5  ldc.i4.2
0x47fd6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x47fdb  dup
0x47fdc  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x47fe1  ldc.i4.3
0x47fe2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x47fe7  dup
0x47fe8  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x47fed  ldc.i4.4
0x47fee  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x47ff3  dup
0x47ff4  ldstr    aDocumentlibrar// "DocumentLibraryProtectionExpireDate"
0x47ff9  ldc.i4.5
0x47ffa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x47fff  dup
0x48000  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x48005  ldc.i4.6
0x48006  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4800b  dup
0x4800c  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x48011  ldc.i4.7
0x48012  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x48017  dup
0x48018  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x4801d  ldc.i4.8
0x4801e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x48023  dup
0x48024  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x48029  ldc.i4.s 9
0x4802b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x48030  dup
0x48031  ldstr    aGroupname// "GroupName"
0x48036  ldc.i4.s 0xA
0x48038  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4803d  dup
0x4803e  ldstr    aIrmenabled// "IrmEnabled"
0x48043  ldc.i4.s 0xB
0x48045  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4804a  dup
0x4804b  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x48050  ldc.i4.s 0xC
0x48052  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x48057  dup
0x48058  ldstr    aPolicydescript// "PolicyDescription"
0x4805d  ldc.i4.s 0xD
0x4805f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x48064  dup
0x48065  ldstr    aPolicytitle// "PolicyTitle"
0x4806a  ldc.i4.s 0xE
0x4806c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x48071  dup
0x48072  ldstr    aSettingsource// "SettingSource"
0x48077  ldc.i4.s 0xF
0x48079  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4807e  dup
0x4807f  ldstr    aTemplateid// "TemplateId"
0x48084  ldc.i4.s 0x10
0x48086  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4808b  volatile.
0x4808d  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000d4c-1
0x48092  volatile.
0x48094  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000d4c-1
0x48099  ldloc.2
0x4809a  ldloca.s 3
0x4809c  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x480a1  brfalse  loc_485D9
0x480a6  ldloc.3
0x480a7  switch   loc_480F5, loc_4813F, loc_48189, loc_481D3, loc_4821D, loc_48267, loc_482B1, loc_482FB, loc_48345, loc_4838F, loc_483D9, loc_48423, loc_4846D, loc_484B7, loc_48501, loc_4854B, loc_48592
0x480f0  br       loc_485D9
0x480f5  ldarg.3
0x480f6  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x480fb  stloc.s  4
0x480fd  ldloca.s 4
0x480ff  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x48104  brfalse.s loc_4811D
0x48106  ldarg.3
0x48107  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x4810c  stloc.s  5
0x4810e  ldloca.s 5
0x48110  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x48115  brtrue.s loc_4811D
0x48117  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x4811c  throw
0x4811d  ldarg.0
0x4811e  ldstr    aAllowprint// "AllowPrint"
0x48123  ldarg.s  4
0x48125  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4812a  ldc.i4.1
0x4812b  stloc.0
0x4812c  ldarg.1
0x4812d  ldloc.1
0x4812e  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_AllowPrint()
0x48133  ldarg.s  4
0x48135  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4813a  br       loc_485E5
0x4813f  ldarg.3
0x48140  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x48145  stloc.s  6
0x48147  ldloca.s 6
0x48149  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x4814e  brfalse.s loc_48167
0x48150  ldarg.3
0x48151  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x48156  stloc.s  7
0x48158  ldloca.s 7
0x4815a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x4815f  brtrue.s loc_48167
0x48161  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x48166  throw
0x48167  ldarg.0
0x48168  ldstr    aAllowscript// "AllowScript"
0x4816d  ldarg.s  4
0x4816f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x48174  ldc.i4.1
0x48175  stloc.0
0x48176  ldarg.1
0x48177  ldloc.1
0x48178  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_AllowScript()
0x4817d  ldarg.s  4
0x4817f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x48184  br       loc_485E5
0x48189  ldarg.3
0x4818a  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x4818f  stloc.s  8
0x48191  ldloca.s 8
0x48193  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x48198  brfalse.s loc_481B1
0x4819a  ldarg.3
0x4819b  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x481a0  stloc.s  9
0x481a2  ldloca.s 9
0x481a4  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x481a9  brtrue.s loc_481B1
0x481ab  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x481b0  throw
0x481b1  ldarg.0
0x481b2  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x481b7  ldarg.s  4
0x481b9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x481be  ldc.i4.1
0x481bf  stloc.0
0x481c0  ldarg.1
0x481c1  ldloc.1
0x481c2  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_AllowWriteCopy()
0x481c7  ldarg.s  4
0x481c9  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x481ce  br       loc_485E5
0x481d3  ldarg.3
0x481d4  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x481d9  stloc.s  0xA
0x481db  ldloca.s 0xA
0x481dd  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x481e2  brfalse.s loc_481FB
0x481e4  ldarg.3
0x481e5  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x481ea  stloc.s  0xB
0x481ec  ldloca.s 0xB
0x481ee  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x481f3  brtrue.s loc_481FB
0x481f5  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x481fa  throw
0x481fb  ldarg.0
0x481fc  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x48201  ldarg.s  4
0x48203  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x48208  ldc.i4.1
0x48209  stloc.0
0x4820a  ldarg.1
0x4820b  ldloc.1
0x4820c  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_DisableDocumentBrowserView()
0x48211  ldarg.s  4
0x48213  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x48218  br       loc_485E5
0x4821d  ldarg.3
0x4821e  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x48223  stloc.s  0xC
0x48225  ldloca.s 0xC
0x48227  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x4822c  brfalse.s loc_48245
0x4822e  ldarg.3
0x4822f  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x48234  stloc.s  0xD
0x48236  ldloca.s 0xD
0x48238  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x4823d  brtrue.s loc_48245
0x4823f  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x48244  throw
0x48245  ldarg.0
0x48246  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x4824b  ldarg.s  4
0x4824d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x48252  ldc.i4.1
0x48253  stloc.0
0x48254  ldarg.1
0x48255  ldloc.1
0x48256  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_DocumentAccessExpireDays()
0x4825b  ldarg.s  4
0x4825d  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x48262  br       loc_485E5
0x48267  ldarg.3
0x48268  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x4826d  stloc.s  0xE
0x4826f  ldloca.s 0xE
0x48271  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x48276  brfalse.s loc_4828F
0x48278  ldarg.3
0x48279  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x4827e  stloc.s  0xF
0x48280  ldloca.s 0xF
0x48282  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x48287  brtrue.s loc_4828F
0x48289  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x4828e  throw
0x4828f  ldarg.0
0x48290  ldstr    aDocumentlibrar// "DocumentLibraryProtectionExpireDate"
0x48295  ldarg.s  4
0x48297  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4829c  ldc.i4.1
0x4829d  stloc.0
0x4829e  ldarg.1
0x4829f  ldloc.1
0x482a0  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_DocumentLibraryProtectionExpireDate()
0x482a5  ldarg.s  4
0x482a7  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x482ac  br       loc_485E5
0x482b1  ldarg.3
0x482b2  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x482b7  stloc.s  0x10
0x482b9  ldloca.s 0x10
0x482bb  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x482c0  brfalse.s loc_482D9
0x482c2  ldarg.3
0x482c3  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x482c8  stloc.s  0x11
0x482ca  ldloca.s 0x11
0x482cc  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x482d1  brtrue.s loc_482D9
0x482d3  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x482d8  throw
0x482d9  ldarg.0
0x482da  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x482df  ldarg.s  4
0x482e1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x482e6  ldc.i4.1
0x482e7  stloc.0
0x482e8  ldarg.1
0x482e9  ldloc.1
0x482ea  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_EnableDocumentAccessExpire()
0x482ef  ldarg.s  4
0x482f1  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x482f6  br       loc_485E5
0x482fb  ldarg.3
0x482fc  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x48301  stloc.s  0x12
0x48303  ldloca.s 0x12
0x48305  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x4830a  brfalse.s loc_48323
0x4830c  ldarg.3
0x4830d  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x48312  stloc.s  0x13
0x48314  ldloca.s 0x13
0x48316  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x4831b  brtrue.s loc_48323
0x4831d  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x48322  throw
0x48323  ldarg.0
0x48324  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x48329  ldarg.s  4
0x4832b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x48330  ldc.i4.1
  ... truncated ...
```
