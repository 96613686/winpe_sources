# Microsoft.SharePoint.Publishing.AddinSettingsServerStub::WriteOnePropertyValueAsJson

- ea: `0xec0`
- end: `0x124c`
- name: `Microsoft.SharePoint.Publishing.AddinSettingsServerStub::WriteOnePropertyValueAsJson`
- size: `908`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xec0`

## pseudocode

```c

```

## disassembly

```asm
0xec0  ldc.i4.0
0xec1  stloc.0
0xec2  ldarg.2
0xec3  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinSettings
0xec8  stloc.1
0xec9  ldloc.1
0xeca  brtrue.s loc_ED7
0xecc  ldstr    aTarget// "target"
0xed1  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xed6  throw
0xed7  ldarg.3
0xed8  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0xedd  dup
0xede  stloc.2
0xedf  brfalse  loc_123E
0xee4  volatile.
0xee6  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600002a-1
0xeeb  brtrue.s loc_F67
0xeed  ldc.i4.s 9
0xeef  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xef4  dup
0xef5  ldstr    aDescription// "Description"
0xefa  ldc.i4.0
0xefb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xf00  dup
0xf01  ldstr    aEnabled// "Enabled"
0xf06  ldc.i4.1
0xf07  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xf0c  dup
0xf0d  ldstr    aHeadscript// "HeadScript"
0xf12  ldc.i4.2
0xf13  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xf18  dup
0xf19  ldstr    aHtmlendbody// "HtmlEndBody"
0xf1e  ldc.i4.3
0xf1f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xf24  dup
0xf25  ldstr    aHtmlstartbody// "HtmlStartBody"
0xf2a  ldc.i4.4
0xf2b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xf30  dup
0xf31  ldstr    aId// "Id"
0xf36  ldc.i4.5
0xf37  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xf3c  dup
0xf3d  ldstr    aMetatagpagepro// "MetaTagPagePropertyMappings"
0xf42  ldc.i4.6
0xf43  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xf48  dup
0xf49  ldstr    aNamespace// "Namespace"
0xf4e  ldc.i4.7
0xf4f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xf54  dup
0xf55  ldstr    aTitle// "Title"
0xf5a  ldc.i4.8
0xf5b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xf60  volatile.
0xf62  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600002a-1
0xf67  volatile.
0xf69  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600002a-1
0xf6e  ldloc.2
0xf6f  ldloca.s 3
0xf71  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xf76  brfalse  loc_123E
0xf7b  ldloc.3
0xf7c  switch   loc_FAA, loc_FF4, loc_103E, loc_1088, loc_10D2, loc_111C, loc_1166, loc_11B0, loc_11F7
0xfa5  br       loc_123E
0xfaa  ldarg.3
0xfab  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xfb0  stloc.s  4
0xfb2  ldloca.s 4
0xfb4  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xfb9  brfalse.s loc_FD2
0xfbb  ldarg.3
0xfbc  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xfc1  stloc.s  5
0xfc3  ldloca.s 5
0xfc5  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xfca  brtrue.s loc_FD2
0xfcc  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xfd1  throw
0xfd2  ldarg.0
0xfd3  ldstr    aDescription// "Description"
0xfd8  ldarg.s  4
0xfda  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xfdf  ldc.i4.1
0xfe0  stloc.0
0xfe1  ldarg.1
0xfe2  ldloc.1
0xfe3  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinSettings::get_Description()
0xfe8  ldarg.s  4
0xfea  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xfef  br       loc_124A
0xff4  ldarg.3
0xff5  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xffa  stloc.s  6
0xffc  ldloca.s 6
0xffe  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1003  brfalse.s loc_101C
0x1005  ldarg.3
0x1006  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x100b  stloc.s  7
0x100d  ldloca.s 7
0x100f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x1014  brtrue.s loc_101C
0x1016  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x101b  throw
0x101c  ldarg.0
0x101d  ldstr    aEnabled// "Enabled"
0x1022  ldarg.s  4
0x1024  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1029  ldc.i4.1
0x102a  stloc.0
0x102b  ldarg.1
0x102c  ldloc.1
0x102d  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinSettings::get_Enabled()
0x1032  ldarg.s  4
0x1034  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1039  br       loc_124A
0x103e  ldarg.3
0x103f  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x1044  stloc.s  8
0x1046  ldloca.s 8
0x1048  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x104d  brfalse.s loc_1066
0x104f  ldarg.3
0x1050  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x1055  stloc.s  9
0x1057  ldloca.s 9
0x1059  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x105e  brtrue.s loc_1066
0x1060  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x1065  throw
0x1066  ldarg.0
0x1067  ldstr    aHeadscript// "HeadScript"
0x106c  ldarg.s  4
0x106e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1073  ldc.i4.1
0x1074  stloc.0
0x1075  ldarg.1
0x1076  ldloc.1
0x1077  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinSettings::get_HeadScript()
0x107c  ldarg.s  4
0x107e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1083  br       loc_124A
0x1088  ldarg.3
0x1089  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x108e  stloc.s  0xA
0x1090  ldloca.s 0xA
0x1092  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1097  brfalse.s loc_10B0
0x1099  ldarg.3
0x109a  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x109f  stloc.s  0xB
0x10a1  ldloca.s 0xB
0x10a3  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x10a8  brtrue.s loc_10B0
0x10aa  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x10af  throw
0x10b0  ldarg.0
0x10b1  ldstr    aHtmlendbody// "HtmlEndBody"
0x10b6  ldarg.s  4
0x10b8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10bd  ldc.i4.1
0x10be  stloc.0
0x10bf  ldarg.1
0x10c0  ldloc.1
0x10c1  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinSettings::get_HtmlEndBody()
0x10c6  ldarg.s  4
0x10c8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10cd  br       loc_124A
0x10d2  ldarg.3
0x10d3  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x10d8  stloc.s  0xC
0x10da  ldloca.s 0xC
0x10dc  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x10e1  brfalse.s loc_10FA
0x10e3  ldarg.3
0x10e4  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x10e9  stloc.s  0xD
0x10eb  ldloca.s 0xD
0x10ed  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x10f2  brtrue.s loc_10FA
0x10f4  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x10f9  throw
0x10fa  ldarg.0
0x10fb  ldstr    aHtmlstartbody// "HtmlStartBody"
0x1100  ldarg.s  4
0x1102  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1107  ldc.i4.1
0x1108  stloc.0
0x1109  ldarg.1
0x110a  ldloc.1
0x110b  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinSettings::get_HtmlStartBody()
0x1110  ldarg.s  4
0x1112  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1117  br       loc_124A
0x111c  ldarg.3
0x111d  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x1122  stloc.s  0xE
0x1124  ldloca.s 0xE
0x1126  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x112b  brfalse.s loc_1144
0x112d  ldarg.3
0x112e  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x1133  stloc.s  0xF
0x1135  ldloca.s 0xF
0x1137  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x113c  brtrue.s loc_1144
0x113e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x1143  throw
0x1144  ldarg.0
0x1145  ldstr    aId// "Id"
0x114a  ldarg.s  4
0x114c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1151  ldc.i4.1
0x1152  stloc.0
0x1153  ldarg.1
0x1154  ldloc.1
0x1155  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinSettings::get_Id()
0x115a  ldarg.s  4
0x115c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1161  br       loc_124A
0x1166  ldarg.3
0x1167  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x116c  stloc.s  0x10
0x116e  ldloca.s 0x10
0x1170  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1175  brfalse.s loc_118E
0x1177  ldarg.3
0x1178  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x117d  stloc.s  0x11
0x117f  ldloca.s 0x11
0x1181  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x1186  brtrue.s loc_118E
0x1188  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x118d  throw
0x118e  ldarg.0
0x118f  ldstr    aMetatagpagepro// "MetaTagPagePropertyMappings"
0x1194  ldarg.s  4
0x1196  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x119b  ldc.i4.1
0x119c  stloc.0
0x119d  ldarg.1
0x119e  ldloc.1
0x119f  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinSettings::get_MetaTagPagePropertyMappings()
0x11a4  ldarg.s  4
0x11a6  call     T0x2B000005
0x11ab  br       loc_124A
0x11b0  ldarg.3
0x11b1  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x11b6  stloc.s  0x12
0x11b8  ldloca.s 0x12
0x11ba  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x11bf  brfalse.s loc_11D8
0x11c1  ldarg.3
0x11c2  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x11c7  stloc.s  0x13
0x11c9  ldloca.s 0x13
0x11cb  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x11d0  brtrue.s loc_11D8
0x11d2  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x11d7  throw
0x11d8  ldarg.0
0x11d9  ldstr    aNamespace// "Namespace"
0x11de  ldarg.s  4
0x11e0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11e5  ldc.i4.1
0x11e6  stloc.0
0x11e7  ldarg.1
0x11e8  ldloc.1
0x11e9  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinSettings::get_Namespace()
0x11ee  ldarg.s  4
0x11f0  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11f5  br.s     loc_124A
0x11f7  ldarg.3
0x11f8  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x11fd  stloc.s  0x14
0x11ff  ldloca.s 0x14
0x1201  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1206  brfalse.s loc_121F
0x1208  ldarg.3
0x1209  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x120e  stloc.s  0x15
0x1210  ldloca.s 0x15
0x1212  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x1217  brtrue.s loc_121F
0x1219  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x121e  throw
0x121f  ldarg.0
0x1220  ldstr    aTitle// "Title"
0x1225  ldarg.s  4
0x1227  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x122c  ldc.i4.1
0x122d  stloc.0
0x122e  ldarg.1
0x122f  ldloc.1
0x1230  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinSettings::get_Title()
0x1235  ldarg.s  4
0x1237  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
  ... truncated ...
```
