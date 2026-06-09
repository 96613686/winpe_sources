# Microsoft.SharePoint.ServerStub.SPInformationRightsManagementSettingsServerStub::WriteOnePropertyValueAsJson

- ea: `0x65db0`
- end: `0x66361`
- name: `Microsoft.SharePoint.ServerStub.SPInformationRightsManagementSettingsServerStub::WriteOnePropertyValueAsJson`
- size: `1457`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x65db0`

## string_xrefs

- `0x65e00`: `AllowWriteCopy`
- `0x65fc0`: `AllowWriteCopy`
- `0x65e18`: `DocumentAccessExpireDays`
- `0x66054`: `DocumentAccessExpireDays`
- `0x65e30`: `EnableDocumentAccessExpire`
- `0x660e8`: `EnableDocumentAccessExpire`
- `0x65e54`: `EnableLicenseCacheExpire`
- `0x661c6`: `EnableLicenseCacheExpire`
- `0x65e6e`: `LicenseCacheExpireDays`
- `0x6625a`: `LicenseCacheExpireDays`
- `0x65e95`: `TemplateId`
- `0x66335`: `TemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x65db0  ldc.i4.0
0x65db1  stloc.0
0x65db2  ldarg.2
0x65db3  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings
0x65db8  stloc.1
0x65db9  ldloc.1
0x65dba  brtrue.s loc_65DC7
0x65dbc  ldstr    aTarget// "target"
0x65dc1  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x65dc6  throw
0x65dc7  ldarg.3
0x65dc8  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x65dcd  dup
0x65dce  stloc.2
0x65dcf  brfalse  loc_66353
0x65dd4  volatile.
0x65dd6  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60011d6-1
0x65ddb  brtrue   loc_65EA8
0x65de0  ldc.i4.s 0xF
0x65de2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x65de7  dup
0x65de8  ldstr    aAllowprint// "AllowPrint"
0x65ded  ldc.i4.0
0x65dee  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65df3  dup
0x65df4  ldstr    aAllowscript// "AllowScript"
0x65df9  ldc.i4.1
0x65dfa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65dff  dup
0x65e00  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x65e05  ldc.i4.2
0x65e06  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65e0b  dup
0x65e0c  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x65e11  ldc.i4.3
0x65e12  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65e17  dup
0x65e18  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x65e1d  ldc.i4.4
0x65e1e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65e23  dup
0x65e24  ldstr    aDocumentlibrar// "DocumentLibraryProtectionExpireDate"
0x65e29  ldc.i4.5
0x65e2a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65e2f  dup
0x65e30  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x65e35  ldc.i4.6
0x65e36  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65e3b  dup
0x65e3c  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x65e41  ldc.i4.7
0x65e42  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65e47  dup
0x65e48  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x65e4d  ldc.i4.8
0x65e4e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65e53  dup
0x65e54  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x65e59  ldc.i4.s 9
0x65e5b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65e60  dup
0x65e61  ldstr    aGroupname// "GroupName"
0x65e66  ldc.i4.s 0xA
0x65e68  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65e6d  dup
0x65e6e  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x65e73  ldc.i4.s 0xB
0x65e75  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65e7a  dup
0x65e7b  ldstr    aPolicydescript// "PolicyDescription"
0x65e80  ldc.i4.s 0xC
0x65e82  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65e87  dup
0x65e88  ldstr    aPolicytitle// "PolicyTitle"
0x65e8d  ldc.i4.s 0xD
0x65e8f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65e94  dup
0x65e95  ldstr    aTemplateid// "TemplateId"
0x65e9a  ldc.i4.s 0xE
0x65e9c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65ea1  volatile.
0x65ea3  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60011d6-1
0x65ea8  volatile.
0x65eaa  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60011d6-1
0x65eaf  ldloc.2
0x65eb0  ldloca.s 3
0x65eb2  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x65eb7  brfalse  loc_66353
0x65ebc  ldloc.3
0x65ebd  switch   loc_65F03, loc_65F4D, loc_65F97, loc_65FE1, loc_6602B, loc_66075, loc_660BF, loc_66109, loc_66153, loc_6619D, loc_661E7, loc_66231, loc_6627B, loc_662C5, loc_6630C
0x65efe  br       loc_66353
0x65f03  ldarg.3
0x65f04  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x65f09  stloc.s  4
0x65f0b  ldloca.s 4
0x65f0d  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x65f12  brfalse.s loc_65F2B
0x65f14  ldarg.3
0x65f15  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x65f1a  stloc.s  5
0x65f1c  ldloca.s 5
0x65f1e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x65f23  brtrue.s loc_65F2B
0x65f25  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x65f2a  throw
0x65f2b  ldarg.0
0x65f2c  ldstr    aAllowprint// "AllowPrint"
0x65f31  ldarg.s  4
0x65f33  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65f38  ldc.i4.1
0x65f39  stloc.0
0x65f3a  ldarg.1
0x65f3b  ldloc.1
0x65f3c  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_AllowPrint()
0x65f41  ldarg.s  4
0x65f43  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65f48  br       loc_6635F
0x65f4d  ldarg.3
0x65f4e  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x65f53  stloc.s  6
0x65f55  ldloca.s 6
0x65f57  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x65f5c  brfalse.s loc_65F75
0x65f5e  ldarg.3
0x65f5f  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x65f64  stloc.s  7
0x65f66  ldloca.s 7
0x65f68  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x65f6d  brtrue.s loc_65F75
0x65f6f  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x65f74  throw
0x65f75  ldarg.0
0x65f76  ldstr    aAllowscript// "AllowScript"
0x65f7b  ldarg.s  4
0x65f7d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65f82  ldc.i4.1
0x65f83  stloc.0
0x65f84  ldarg.1
0x65f85  ldloc.1
0x65f86  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_AllowScript()
0x65f8b  ldarg.s  4
0x65f8d  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65f92  br       loc_6635F
0x65f97  ldarg.3
0x65f98  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x65f9d  stloc.s  8
0x65f9f  ldloca.s 8
0x65fa1  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x65fa6  brfalse.s loc_65FBF
0x65fa8  ldarg.3
0x65fa9  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x65fae  stloc.s  9
0x65fb0  ldloca.s 9
0x65fb2  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x65fb7  brtrue.s loc_65FBF
0x65fb9  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x65fbe  throw
0x65fbf  ldarg.0
0x65fc0  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x65fc5  ldarg.s  4
0x65fc7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65fcc  ldc.i4.1
0x65fcd  stloc.0
0x65fce  ldarg.1
0x65fcf  ldloc.1
0x65fd0  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_AllowWriteCopy()
0x65fd5  ldarg.s  4
0x65fd7  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65fdc  br       loc_6635F
0x65fe1  ldarg.3
0x65fe2  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x65fe7  stloc.s  0xA
0x65fe9  ldloca.s 0xA
0x65feb  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x65ff0  brfalse.s loc_66009
0x65ff2  ldarg.3
0x65ff3  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x65ff8  stloc.s  0xB
0x65ffa  ldloca.s 0xB
0x65ffc  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x66001  brtrue.s loc_66009
0x66003  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x66008  throw
0x66009  ldarg.0
0x6600a  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x6600f  ldarg.s  4
0x66011  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66016  ldc.i4.1
0x66017  stloc.0
0x66018  ldarg.1
0x66019  ldloc.1
0x6601a  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_DisableDocumentBrowserView()
0x6601f  ldarg.s  4
0x66021  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66026  br       loc_6635F
0x6602b  ldarg.3
0x6602c  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x66031  stloc.s  0xC
0x66033  ldloca.s 0xC
0x66035  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x6603a  brfalse.s loc_66053
0x6603c  ldarg.3
0x6603d  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x66042  stloc.s  0xD
0x66044  ldloca.s 0xD
0x66046  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x6604b  brtrue.s loc_66053
0x6604d  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x66052  throw
0x66053  ldarg.0
0x66054  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x66059  ldarg.s  4
0x6605b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66060  ldc.i4.1
0x66061  stloc.0
0x66062  ldarg.1
0x66063  ldloc.1
0x66064  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_DocumentAccessExpireDays()
0x66069  ldarg.s  4
0x6606b  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66070  br       loc_6635F
0x66075  ldarg.3
0x66076  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6607b  stloc.s  0xE
0x6607d  ldloca.s 0xE
0x6607f  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x66084  brfalse.s loc_6609D
0x66086  ldarg.3
0x66087  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6608c  stloc.s  0xF
0x6608e  ldloca.s 0xF
0x66090  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x66095  brtrue.s loc_6609D
0x66097  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x6609c  throw
0x6609d  ldarg.0
0x6609e  ldstr    aDocumentlibrar// "DocumentLibraryProtectionExpireDate"
0x660a3  ldarg.s  4
0x660a5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x660aa  ldc.i4.1
0x660ab  stloc.0
0x660ac  ldarg.1
0x660ad  ldloc.1
0x660ae  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_DocumentLibraryProtectionExpireDate()
0x660b3  ldarg.s  4
0x660b5  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x660ba  br       loc_6635F
0x660bf  ldarg.3
0x660c0  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x660c5  stloc.s  0x10
0x660c7  ldloca.s 0x10
0x660c9  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x660ce  brfalse.s loc_660E7
0x660d0  ldarg.3
0x660d1  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x660d6  stloc.s  0x11
0x660d8  ldloca.s 0x11
0x660da  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x660df  brtrue.s loc_660E7
0x660e1  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x660e6  throw
0x660e7  ldarg.0
0x660e8  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x660ed  ldarg.s  4
0x660ef  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x660f4  ldc.i4.1
0x660f5  stloc.0
0x660f6  ldarg.1
0x660f7  ldloc.1
0x660f8  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_EnableDocumentAccessExpire()
0x660fd  ldarg.s  4
0x660ff  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66104  br       loc_6635F
0x66109  ldarg.3
0x6610a  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6610f  stloc.s  0x12
0x66111  ldloca.s 0x12
0x66113  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x66118  brfalse.s loc_66131
0x6611a  ldarg.3
0x6611b  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x66120  stloc.s  0x13
0x66122  ldloca.s 0x13
0x66124  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x66129  brtrue.s loc_66131
0x6612b  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x66130  throw
0x66131  ldarg.0
0x66132  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x66137  ldarg.s  4
0x66139  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6613e  ldc.i4.1
0x6613f  stloc.0
0x66140  ldarg.1
0x66141  ldloc.1
0x66142  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_EnableDocumentBrowserPublishingView()
0x66147  ldarg.s  4
0x66149  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6614e  br       loc_6635F
0x66153  ldarg.3
  ... truncated ...
```
