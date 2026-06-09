# System.Net.Http.Formatting.FormUrlEncodedJson::Insert

- ea: `0x6360`
- end: `0x6459`
- name: `System.Net.Http.Formatting.FormUrlEncodedJson::Insert`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6140`

## callees

- `0x3390`
- `0x3510`
- `0x6360`
- `0x6460`
- `0x6580`
- `0x6890`
- `0xb330`

## pseudocode

```c

```

## disassembly

```asm
0x6360  ldarg.0
0x6361  stloc.0
0x6362  ldnull
0x6363  stloc.1
0x6364  ldc.i4.0
0x6365  stloc.2
0x6366  br       loc_63FA
0x636b  ldarg.1
0x636c  ldloc.2
0x636d  ldelem.ref
0x636e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6373  brfalse.s loc_6392
0x6375  ldarg.3
0x6376  brfalse.s loc_6390
0x6378  call     string System.Net.Http.Properties.Resources::get_InvalidArrayInsert()
0x637d  ldarg.1
0x637e  ldloc.2
0x637f  call     string System.Net.Http.Formatting.FormUrlEncodedJson::BuildPathString(string[] path, int32 i)
0x6384  ldc.i4.0
0x6385  newarr   [mscorlib]System.Object
0x638a  call     class [mscorlib]System.ArgumentException System.Web.Http.Error::Argument(string parameterName, string messageFormat, object[] messageArgs)
0x638f  throw
0x6390  ldc.i4.0
0x6391  ret
0x6392  ldloc.0
0x6393  ldarg.1
0x6394  ldloc.2
0x6395  ldelem.ref
0x6396  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken>::ContainsKey(var<u1>)
0x639b  brtrue.s loc_63AD
0x639d  ldloc.0
0x639e  ldarg.1
0x639f  ldloc.2
0x63a0  ldelem.ref
0x63a1  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::.ctor()
0x63a6  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::set_Item(string, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken)
0x63ab  br.s     loc_63E5
0x63ad  ldloc.0
0x63ae  ldarg.1
0x63af  ldloc.2
0x63b0  ldelem.ref
0x63b1  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0x63b6  brfalse.s loc_63C8
0x63b8  ldloc.0
0x63b9  ldarg.1
0x63ba  ldloc.2
0x63bb  ldelem.ref
0x63bc  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0x63c1  isinst   [Newtonsoft.Json]Newtonsoft.Json.Linq.JValue
0x63c6  brfalse.s loc_63E5
0x63c8  ldarg.3
0x63c9  brfalse.s loc_63E3
0x63cb  call     string System.Net.Http.Properties.Resources::get_FormUrlEncodedMismatchingTypes()
0x63d0  ldarg.1
0x63d1  ldloc.2
0x63d2  call     string System.Net.Http.Formatting.FormUrlEncodedJson::BuildPathString(string[] path, int32 i)
0x63d7  ldc.i4.0
0x63d8  newarr   [mscorlib]System.Object
0x63dd  call     class [mscorlib]System.ArgumentException System.Web.Http.Error::Argument(string parameterName, string messageFormat, object[] messageArgs)
0x63e2  throw
0x63e3  ldc.i4.0
0x63e4  ret
0x63e5  ldloc.0
0x63e6  stloc.1
0x63e7  ldloc.0
0x63e8  ldarg.1
0x63e9  ldloc.2
0x63ea  ldelem.ref
0x63eb  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0x63f0  isinst   [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject
0x63f5  stloc.0
0x63f6  ldloc.2
0x63f7  ldc.i4.1
0x63f8  add
0x63f9  stloc.2
0x63fa  ldloc.2
0x63fb  ldarg.1
0x63fc  ldlen
0x63fd  conv.i4
0x63fe  ldc.i4.1
0x63ff  sub
0x6400  blt      loc_636B
0x6405  ldarg.1
0x6406  ldarg.1
0x6407  ldlen
0x6408  conv.i4
0x6409  ldc.i4.1
0x640a  sub
0x640b  ldelem.ref
0x640c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6411  brfalse.s loc_6426
0x6413  ldarg.1
0x6414  ldlen
0x6415  conv.i4
0x6416  ldc.i4.1
0x6417  ble.s    loc_6426
0x6419  ldloc.1
0x641a  ldarg.1
0x641b  ldarg.2
0x641c  ldarg.3
0x641d  call     bool System.Net.Http.Formatting.FormUrlEncodedJson::AddToArray(class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject parent, string[] path, string value, bool throwOnError)
0x6422  brtrue.s loc_6457
0x6424  ldc.i4.0
0x6425  ret
0x6426  ldloc.0
0x6427  brtrue.s loc_644A
0x6429  ldarg.3
0x642a  brfalse.s loc_6448
0x642c  call     string System.Net.Http.Properties.Resources::get_FormUrlEncodedMismatchingTypes()
0x6431  ldarg.1
0x6432  ldarg.1
0x6433  ldlen
0x6434  conv.i4
0x6435  ldc.i4.1
0x6436  sub
0x6437  call     string System.Net.Http.Formatting.FormUrlEncodedJson::BuildPathString(string[] path, int32 i)
0x643c  ldc.i4.0
0x643d  newarr   [mscorlib]System.Object
0x6442  call     class [mscorlib]System.ArgumentException System.Web.Http.Error::Argument(string parameterName, string messageFormat, object[] messageArgs)
0x6447  throw
0x6448  ldc.i4.0
0x6449  ret
0x644a  ldloc.0
0x644b  ldarg.1
0x644c  ldarg.2
0x644d  ldarg.3
0x644e  call     bool System.Net.Http.Formatting.FormUrlEncodedJson::AddToObject(class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject obj, string[] path, string value, bool throwOnError)
0x6453  brtrue.s loc_6457
0x6455  ldc.i4.0
0x6456  ret
0x6457  ldc.i4.1
0x6458  ret
```
