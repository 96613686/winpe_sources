# Microsoft.SharePoint.ServerStub.SPInformationRightsManagementFileSettingsServerStub::WriteOnePropertyValueAsJson

- ea: `0x647e0`
- end: `0x64d91`
- name: `Microsoft.SharePoint.ServerStub.SPInformationRightsManagementFileSettingsServerStub::WriteOnePropertyValueAsJson`
- size: `1457`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x647e0`

## string_xrefs

- `0x64830`: `AllowWriteCopy`
- `0x649f0`: `AllowWriteCopy`
- `0x64848`: `DocumentAccessExpireDays`
- `0x64a84`: `DocumentAccessExpireDays`
- `0x64854`: `EnableDocumentAccessExpire`
- `0x64ace`: `EnableDocumentAccessExpire`
- `0x64878`: `EnableLicenseCacheExpire`
- `0x64bac`: `EnableLicenseCacheExpire`
- `0x6489e`: `LicenseCacheExpireDays`
- `0x64c8a`: `LicenseCacheExpireDays`
- `0x648c5`: `TemplateId`
- `0x64d65`: `TemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x647e0  ldc.i4.0
0x647e1  stloc.0
0x647e2  ldarg.2
0x647e3  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings
0x647e8  stloc.1
0x647e9  ldloc.1
0x647ea  brtrue.s loc_647F7
0x647ec  ldstr    aTarget// "target"
0x647f1  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x647f6  throw
0x647f7  ldarg.3
0x647f8  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x647fd  dup
0x647fe  stloc.2
0x647ff  brfalse  loc_64D83
0x64804  volatile.
0x64806  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60011c0-1
0x6480b  brtrue   loc_648D8
0x64810  ldc.i4.s 0xF
0x64812  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x64817  dup
0x64818  ldstr    aAllowprint// "AllowPrint"
0x6481d  ldc.i4.0
0x6481e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64823  dup
0x64824  ldstr    aAllowscript// "AllowScript"
0x64829  ldc.i4.1
0x6482a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6482f  dup
0x64830  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x64835  ldc.i4.2
0x64836  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6483b  dup
0x6483c  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x64841  ldc.i4.3
0x64842  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64847  dup
0x64848  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x6484d  ldc.i4.4
0x6484e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64853  dup
0x64854  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x64859  ldc.i4.5
0x6485a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6485f  dup
0x64860  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x64865  ldc.i4.6
0x64866  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6486b  dup
0x6486c  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x64871  ldc.i4.7
0x64872  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64877  dup
0x64878  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x6487d  ldc.i4.8
0x6487e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64883  dup
0x64884  ldstr    aGroupname// "GroupName"
0x64889  ldc.i4.s 9
0x6488b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x64890  dup
0x64891  ldstr    aIrmenabled// "IrmEnabled"
0x64896  ldc.i4.s 0xA
0x64898  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6489d  dup
0x6489e  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x648a3  ldc.i4.s 0xB
0x648a5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x648aa  dup
0x648ab  ldstr    aPolicydescript// "PolicyDescription"
0x648b0  ldc.i4.s 0xC
0x648b2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x648b7  dup
0x648b8  ldstr    aPolicytitle// "PolicyTitle"
0x648bd  ldc.i4.s 0xD
0x648bf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x648c4  dup
0x648c5  ldstr    aTemplateid// "TemplateId"
0x648ca  ldc.i4.s 0xE
0x648cc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x648d1  volatile.
0x648d3  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60011c0-1
0x648d8  volatile.
0x648da  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60011c0-1
0x648df  ldloc.2
0x648e0  ldloca.s 3
0x648e2  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x648e7  brfalse  loc_64D83
0x648ec  ldloc.3
0x648ed  switch   loc_64933, loc_6497D, loc_649C7, loc_64A11, loc_64A5B, loc_64AA5, loc_64AEF, loc_64B39, loc_64B83, loc_64BCD, loc_64C17, loc_64C61, loc_64CAB, loc_64CF5, loc_64D3C
0x6492e  br       loc_64D83
0x64933  ldarg.3
0x64934  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x64939  stloc.s  4
0x6493b  ldloca.s 4
0x6493d  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x64942  brfalse.s loc_6495B
0x64944  ldarg.3
0x64945  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6494a  stloc.s  5
0x6494c  ldloca.s 5
0x6494e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x64953  brtrue.s loc_6495B
0x64955  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x6495a  throw
0x6495b  ldarg.0
0x6495c  ldstr    aAllowprint// "AllowPrint"
0x64961  ldarg.s  4
0x64963  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64968  ldc.i4.1
0x64969  stloc.0
0x6496a  ldarg.1
0x6496b  ldloc.1
0x6496c  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_AllowPrint()
0x64971  ldarg.s  4
0x64973  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64978  br       loc_64D8F
0x6497d  ldarg.3
0x6497e  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x64983  stloc.s  6
0x64985  ldloca.s 6
0x64987  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x6498c  brfalse.s loc_649A5
0x6498e  ldarg.3
0x6498f  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x64994  stloc.s  7
0x64996  ldloca.s 7
0x64998  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x6499d  brtrue.s loc_649A5
0x6499f  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x649a4  throw
0x649a5  ldarg.0
0x649a6  ldstr    aAllowscript// "AllowScript"
0x649ab  ldarg.s  4
0x649ad  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x649b2  ldc.i4.1
0x649b3  stloc.0
0x649b4  ldarg.1
0x649b5  ldloc.1
0x649b6  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_AllowScript()
0x649bb  ldarg.s  4
0x649bd  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x649c2  br       loc_64D8F
0x649c7  ldarg.3
0x649c8  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x649cd  stloc.s  8
0x649cf  ldloca.s 8
0x649d1  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x649d6  brfalse.s loc_649EF
0x649d8  ldarg.3
0x649d9  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x649de  stloc.s  9
0x649e0  ldloca.s 9
0x649e2  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x649e7  brtrue.s loc_649EF
0x649e9  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x649ee  throw
0x649ef  ldarg.0
0x649f0  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x649f5  ldarg.s  4
0x649f7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x649fc  ldc.i4.1
0x649fd  stloc.0
0x649fe  ldarg.1
0x649ff  ldloc.1
0x64a00  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_AllowWriteCopy()
0x64a05  ldarg.s  4
0x64a07  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64a0c  br       loc_64D8F
0x64a11  ldarg.3
0x64a12  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x64a17  stloc.s  0xA
0x64a19  ldloca.s 0xA
0x64a1b  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x64a20  brfalse.s loc_64A39
0x64a22  ldarg.3
0x64a23  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x64a28  stloc.s  0xB
0x64a2a  ldloca.s 0xB
0x64a2c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x64a31  brtrue.s loc_64A39
0x64a33  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x64a38  throw
0x64a39  ldarg.0
0x64a3a  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x64a3f  ldarg.s  4
0x64a41  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64a46  ldc.i4.1
0x64a47  stloc.0
0x64a48  ldarg.1
0x64a49  ldloc.1
0x64a4a  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_DisableDocumentBrowserView()
0x64a4f  ldarg.s  4
0x64a51  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64a56  br       loc_64D8F
0x64a5b  ldarg.3
0x64a5c  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x64a61  stloc.s  0xC
0x64a63  ldloca.s 0xC
0x64a65  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x64a6a  brfalse.s loc_64A83
0x64a6c  ldarg.3
0x64a6d  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x64a72  stloc.s  0xD
0x64a74  ldloca.s 0xD
0x64a76  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x64a7b  brtrue.s loc_64A83
0x64a7d  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x64a82  throw
0x64a83  ldarg.0
0x64a84  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x64a89  ldarg.s  4
0x64a8b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64a90  ldc.i4.1
0x64a91  stloc.0
0x64a92  ldarg.1
0x64a93  ldloc.1
0x64a94  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_DocumentAccessExpireDays()
0x64a99  ldarg.s  4
0x64a9b  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64aa0  br       loc_64D8F
0x64aa5  ldarg.3
0x64aa6  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x64aab  stloc.s  0xE
0x64aad  ldloca.s 0xE
0x64aaf  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x64ab4  brfalse.s loc_64ACD
0x64ab6  ldarg.3
0x64ab7  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x64abc  stloc.s  0xF
0x64abe  ldloca.s 0xF
0x64ac0  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x64ac5  brtrue.s loc_64ACD
0x64ac7  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x64acc  throw
0x64acd  ldarg.0
0x64ace  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x64ad3  ldarg.s  4
0x64ad5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64ada  ldc.i4.1
0x64adb  stloc.0
0x64adc  ldarg.1
0x64add  ldloc.1
0x64ade  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_EnableDocumentAccessExpire()
0x64ae3  ldarg.s  4
0x64ae5  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64aea  br       loc_64D8F
0x64aef  ldarg.3
0x64af0  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x64af5  stloc.s  0x10
0x64af7  ldloca.s 0x10
0x64af9  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x64afe  brfalse.s loc_64B17
0x64b00  ldarg.3
0x64b01  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x64b06  stloc.s  0x11
0x64b08  ldloca.s 0x11
0x64b0a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x64b0f  brtrue.s loc_64B17
0x64b11  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x64b16  throw
0x64b17  ldarg.0
0x64b18  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x64b1d  ldarg.s  4
0x64b1f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64b24  ldc.i4.1
0x64b25  stloc.0
0x64b26  ldarg.1
0x64b27  ldloc.1
0x64b28  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_EnableDocumentBrowserPublishingView()
0x64b2d  ldarg.s  4
0x64b2f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64b34  br       loc_64D8F
0x64b39  ldarg.3
0x64b3a  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x64b3f  stloc.s  0x12
0x64b41  ldloca.s 0x12
0x64b43  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x64b48  brfalse.s loc_64B61
0x64b4a  ldarg.3
0x64b4b  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x64b50  stloc.s  0x13
0x64b52  ldloca.s 0x13
0x64b54  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x64b59  brtrue.s loc_64B61
0x64b5b  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x64b60  throw
0x64b61  ldarg.0
0x64b62  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x64b67  ldarg.s  4
0x64b69  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64b6e  ldc.i4.1
0x64b6f  stloc.0
0x64b70  ldarg.1
0x64b71  ldloc.1
0x64b72  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_EnableGroupProtection()
0x64b77  ldarg.s  4
0x64b79  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64b7e  br       loc_64D8F
0x64b83  ldarg.3
  ... truncated ...
```
