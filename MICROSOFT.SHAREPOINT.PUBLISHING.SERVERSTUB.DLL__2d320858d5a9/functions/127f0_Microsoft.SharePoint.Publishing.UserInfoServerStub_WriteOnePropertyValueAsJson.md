# Microsoft.SharePoint.Publishing.UserInfoServerStub::WriteOnePropertyValueAsJson

- ea: `0x127f0`
- end: `0x12982`
- name: `Microsoft.SharePoint.Publishing.UserInfoServerStub::WriteOnePropertyValueAsJson`
- size: `402`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x127f0`

## pseudocode

```c

```

## disassembly

```asm
0x127f0  ldc.i4.0
0x127f1  stloc.0
0x127f2  ldarg.2
0x127f3  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.UserInfo
0x127f8  stloc.1
0x127f9  ldloc.1
0x127fa  brtrue.s loc_12807
0x127fc  ldstr    aTarget// "target"
0x12801  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x12806  throw
0x12807  ldarg.3
0x12808  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x1280d  dup
0x1280e  stloc.2
0x1280f  brfalse  loc_12974
0x12814  ldloc.2
0x12815  ldstr    aAccountname// "AccountName"
0x1281a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1281f  brtrue.s loc_12853
0x12821  ldloc.2
0x12822  ldstr    aAcronym// "Acronym"
0x12827  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1282c  brtrue.s loc_1289C
0x1282e  ldloc.2
0x1282f  ldstr    aColor// "Color"
0x12834  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12839  brtrue   loc_128E6
0x1283e  ldloc.2
0x1283f  ldstr    aName// "Name"
0x12844  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12849  brtrue   loc_1292D
0x1284e  br       loc_12974
0x12853  ldarg.3
0x12854  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x12859  stloc.3
0x1285a  ldloca.s 3
0x1285c  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x12861  brfalse.s loc_1287A
0x12863  ldarg.3
0x12864  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x12869  stloc.s  4
0x1286b  ldloca.s 4
0x1286d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x12872  brtrue.s loc_1287A
0x12874  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x12879  throw
0x1287a  ldarg.0
0x1287b  ldstr    aAccountname// "AccountName"
0x12880  ldarg.s  4
0x12882  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x12887  ldc.i4.1
0x12888  stloc.0
0x12889  ldarg.1
0x1288a  ldloc.1
0x1288b  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.UserInfo::get_AccountName()
0x12890  ldarg.s  4
0x12892  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x12897  br       loc_12980
0x1289c  ldarg.3
0x1289d  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x128a2  stloc.s  5
0x128a4  ldloca.s 5
0x128a6  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x128ab  brfalse.s loc_128C4
0x128ad  ldarg.3
0x128ae  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x128b3  stloc.s  6
0x128b5  ldloca.s 6
0x128b7  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x128bc  brtrue.s loc_128C4
0x128be  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x128c3  throw
0x128c4  ldarg.0
0x128c5  ldstr    aAcronym// "Acronym"
0x128ca  ldarg.s  4
0x128cc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x128d1  ldc.i4.1
0x128d2  stloc.0
0x128d3  ldarg.1
0x128d4  ldloc.1
0x128d5  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.UserInfo::get_Acronym()
0x128da  ldarg.s  4
0x128dc  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x128e1  br       loc_12980
0x128e6  ldarg.3
0x128e7  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x128ec  stloc.s  7
0x128ee  ldloca.s 7
0x128f0  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x128f5  brfalse.s loc_1290E
0x128f7  ldarg.3
0x128f8  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x128fd  stloc.s  8
0x128ff  ldloca.s 8
0x12901  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x12906  brtrue.s loc_1290E
0x12908  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x1290d  throw
0x1290e  ldarg.0
0x1290f  ldstr    aColor// "Color"
0x12914  ldarg.s  4
0x12916  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1291b  ldc.i4.1
0x1291c  stloc.0
0x1291d  ldarg.1
0x1291e  ldloc.1
0x1291f  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.UserInfo::get_Color()
0x12924  ldarg.s  4
0x12926  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1292b  br.s     loc_12980
0x1292d  ldarg.3
0x1292e  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x12933  stloc.s  9
0x12935  ldloca.s 9
0x12937  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1293c  brfalse.s loc_12955
0x1293e  ldarg.3
0x1293f  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x12944  stloc.s  0xA
0x12946  ldloca.s 0xA
0x12948  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x1294d  brtrue.s loc_12955
0x1294f  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x12954  throw
0x12955  ldarg.0
0x12956  ldstr    aName// "Name"
0x1295b  ldarg.s  4
0x1295d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x12962  ldc.i4.1
0x12963  stloc.0
0x12964  ldarg.1
0x12965  ldloc.1
0x12966  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.UserInfo::get_Name()
0x1296b  ldarg.s  4
0x1296d  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x12972  br.s     loc_12980
0x12974  ldarg.0
0x12975  ldarg.1
0x12976  ldarg.2
0x12977  ldarg.3
0x12978  ldarg.s  4
0x1297a  call     instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteOnePropertyValueAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1297f  stloc.0
0x12980  ldloc.0
0x12981  ret
```
