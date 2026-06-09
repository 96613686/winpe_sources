# Microsoft.SharePoint.Publishing.VariationLabelServerStub::WriteOnePropertyValueAsJson

- ea: `0x12e50`
- end: `0x130cd`
- name: `Microsoft.SharePoint.Publishing.VariationLabelServerStub::WriteOnePropertyValueAsJson`
- size: `637`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x12e50`

## pseudocode

```c

```

## disassembly

```asm
0x12e50  ldc.i4.0
0x12e51  stloc.0
0x12e52  ldarg.2
0x12e53  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.VariationLabel
0x12e58  stloc.1
0x12e59  ldloc.1
0x12e5a  brtrue.s loc_12E67
0x12e5c  ldstr    aTarget// "target"
0x12e61  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x12e66  throw
0x12e67  ldarg.3
0x12e68  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x12e6d  dup
0x12e6e  stloc.2
0x12e6f  brfalse  loc_130BF
0x12e74  volatile.
0x12e76  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000359-1
0x12e7b  brtrue.s loc_12ED2
0x12e7d  ldc.i4.6
0x12e7e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x12e83  dup
0x12e84  ldstr    aDisplayname// "DisplayName"
0x12e89  ldc.i4.0
0x12e8a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x12e8f  dup
0x12e90  ldstr    aIssource// "IsSource"
0x12e95  ldc.i4.1
0x12e96  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x12e9b  dup
0x12e9c  ldstr    aLanguage// "Language"
0x12ea1  ldc.i4.2
0x12ea2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x12ea7  dup
0x12ea8  ldstr    aLocale// "Locale"
0x12ead  ldc.i4.3
0x12eae  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x12eb3  dup
0x12eb4  ldstr    aTitle// "Title"
0x12eb9  ldc.i4.4
0x12eba  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x12ebf  dup
0x12ec0  ldstr    aTopweburl// "TopWebUrl"
0x12ec5  ldc.i4.5
0x12ec6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x12ecb  volatile.
0x12ecd  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000359-1
0x12ed2  volatile.
0x12ed4  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000359-1
0x12ed9  ldloc.2
0x12eda  ldloca.s 3
0x12edc  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x12ee1  brfalse  loc_130BF
0x12ee6  ldloc.3
0x12ee7  switch   loc_12F09, loc_12F53, loc_12F9D, loc_12FE7, loc_13031, loc_13078
0x12f04  br       loc_130BF
0x12f09  ldarg.3
0x12f0a  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x12f0f  stloc.s  4
0x12f11  ldloca.s 4
0x12f13  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x12f18  brfalse.s loc_12F31
0x12f1a  ldarg.3
0x12f1b  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x12f20  stloc.s  5
0x12f22  ldloca.s 5
0x12f24  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x12f29  brtrue.s loc_12F31
0x12f2b  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x12f30  throw
0x12f31  ldarg.0
0x12f32  ldstr    aDisplayname// "DisplayName"
0x12f37  ldarg.s  4
0x12f39  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x12f3e  ldc.i4.1
0x12f3f  stloc.0
0x12f40  ldarg.1
0x12f41  ldloc.1
0x12f42  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.VariationLabel::get_DisplayName()
0x12f47  ldarg.s  4
0x12f49  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x12f4e  br       loc_130CB
0x12f53  ldarg.3
0x12f54  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x12f59  stloc.s  6
0x12f5b  ldloca.s 6
0x12f5d  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x12f62  brfalse.s loc_12F7B
0x12f64  ldarg.3
0x12f65  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x12f6a  stloc.s  7
0x12f6c  ldloca.s 7
0x12f6e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x12f73  brtrue.s loc_12F7B
0x12f75  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x12f7a  throw
0x12f7b  ldarg.0
0x12f7c  ldstr    aIssource// "IsSource"
0x12f81  ldarg.s  4
0x12f83  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x12f88  ldc.i4.1
0x12f89  stloc.0
0x12f8a  ldarg.1
0x12f8b  ldloc.1
0x12f8c  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.VariationLabel::get_IsSource()
0x12f91  ldarg.s  4
0x12f93  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x12f98  br       loc_130CB
0x12f9d  ldarg.3
0x12f9e  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x12fa3  stloc.s  8
0x12fa5  ldloca.s 8
0x12fa7  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x12fac  brfalse.s loc_12FC5
0x12fae  ldarg.3
0x12faf  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x12fb4  stloc.s  9
0x12fb6  ldloca.s 9
0x12fb8  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x12fbd  brtrue.s loc_12FC5
0x12fbf  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x12fc4  throw
0x12fc5  ldarg.0
0x12fc6  ldstr    aLanguage// "Language"
0x12fcb  ldarg.s  4
0x12fcd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x12fd2  ldc.i4.1
0x12fd3  stloc.0
0x12fd4  ldarg.1
0x12fd5  ldloc.1
0x12fd6  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.VariationLabel::get_Language()
0x12fdb  ldarg.s  4
0x12fdd  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x12fe2  br       loc_130CB
0x12fe7  ldarg.3
0x12fe8  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x12fed  stloc.s  0xA
0x12fef  ldloca.s 0xA
0x12ff1  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x12ff6  brfalse.s loc_1300F
0x12ff8  ldarg.3
0x12ff9  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x12ffe  stloc.s  0xB
0x13000  ldloca.s 0xB
0x13002  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x13007  brtrue.s loc_1300F
0x13009  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x1300e  throw
0x1300f  ldarg.0
0x13010  ldstr    aLocale// "Locale"
0x13015  ldarg.s  4
0x13017  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1301c  ldc.i4.1
0x1301d  stloc.0
0x1301e  ldarg.1
0x1301f  ldloc.1
0x13020  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.VariationLabel::get_Locale()
0x13025  ldarg.s  4
0x13027  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1302c  br       loc_130CB
0x13031  ldarg.3
0x13032  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x13037  stloc.s  0xC
0x13039  ldloca.s 0xC
0x1303b  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x13040  brfalse.s loc_13059
0x13042  ldarg.3
0x13043  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x13048  stloc.s  0xD
0x1304a  ldloca.s 0xD
0x1304c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x13051  brtrue.s loc_13059
0x13053  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x13058  throw
0x13059  ldarg.0
0x1305a  ldstr    aTitle// "Title"
0x1305f  ldarg.s  4
0x13061  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x13066  ldc.i4.1
0x13067  stloc.0
0x13068  ldarg.1
0x13069  ldloc.1
0x1306a  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.VariationLabel::get_Title()
0x1306f  ldarg.s  4
0x13071  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x13076  br.s     loc_130CB
0x13078  ldarg.3
0x13079  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x1307e  stloc.s  0xE
0x13080  ldloca.s 0xE
0x13082  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x13087  brfalse.s loc_130A0
0x13089  ldarg.3
0x1308a  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x1308f  stloc.s  0xF
0x13091  ldloca.s 0xF
0x13093  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x13098  brtrue.s loc_130A0
0x1309a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x1309f  throw
0x130a0  ldarg.0
0x130a1  ldstr    aTopweburl// "TopWebUrl"
0x130a6  ldarg.s  4
0x130a8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x130ad  ldc.i4.1
0x130ae  stloc.0
0x130af  ldarg.1
0x130b0  ldloc.1
0x130b1  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.VariationLabel::get_TopWebUrl()
0x130b6  ldarg.s  4
0x130b8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x130bd  br.s     loc_130CB
0x130bf  ldarg.0
0x130c0  ldarg.1
0x130c1  ldarg.2
0x130c2  ldarg.3
0x130c3  ldarg.s  4
0x130c5  call     instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteOnePropertyValueAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x130ca  stloc.0
0x130cb  ldloc.0
0x130cc  ret
```
