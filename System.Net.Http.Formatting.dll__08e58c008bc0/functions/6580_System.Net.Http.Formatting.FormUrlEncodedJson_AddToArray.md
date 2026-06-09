# System.Net.Http.Formatting.FormUrlEncodedJson::AddToArray

- ea: `0x6580`
- end: `0x65d5`
- name: `System.Net.Http.Formatting.FormUrlEncodedJson::AddToArray`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6360`

## callees

- `0x3390`
- `0x6580`
- `0x65e0`
- `0x6890`
- `0xb330`

## pseudocode

```c

```

## disassembly

```asm
0x6580  ldarg.1
0x6581  ldarg.1
0x6582  ldlen
0x6583  conv.i4
0x6584  ldc.i4.2
0x6585  sub
0x6586  ldelem.ref
0x6587  stloc.0
0x6588  ldarg.0
0x6589  ldloc.0
0x658a  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0x658f  isinst   [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject
0x6594  stloc.1
0x6595  ldloc.1
0x6596  brtrue.s loc_65B9
0x6598  ldarg.3
0x6599  brfalse.s loc_65B7
0x659b  call     string System.Net.Http.Properties.Resources::get_FormUrlEncodedMismatchingTypes()
0x65a0  ldarg.1
0x65a1  ldarg.1
0x65a2  ldlen
0x65a3  conv.i4
0x65a4  ldc.i4.1
0x65a5  sub
0x65a6  call     string System.Net.Http.Formatting.FormUrlEncodedJson::BuildPathString(string[] path, int32 i)
0x65ab  ldc.i4.0
0x65ac  newarr   [mscorlib]System.Object
0x65b1  call     class [mscorlib]System.ArgumentException System.Web.Http.Error::Argument(string parameterName, string messageFormat, object[] messageArgs)
0x65b6  throw
0x65b7  ldc.i4.0
0x65b8  ret
0x65b9  ldloc.1
0x65ba  ldarg.3
0x65bb  call     string System.Net.Http.Formatting.FormUrlEncodedJson::GetIndex(class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject jsonObject, bool throwOnError)
0x65c0  stloc.2
0x65c1  ldloc.2
0x65c2  brtrue.s loc_65C6
0x65c4  ldc.i4.0
0x65c5  ret
0x65c6  ldloc.1
0x65c7  ldloc.2
0x65c8  ldarg.2
0x65c9  call     class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::op_Implicit(string)
0x65ce  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::Add(string, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken)
0x65d3  ldc.i4.1
0x65d4  ret
```
