# System.Net.Http.UriExtensions::TryReadQueryAs

- ea: `0x2fa0`
- end: `0x2fff`
- name: `System.Net.Http.UriExtensions::TryReadQueryAs`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x2fa0`
- `0x5ef0`
- `0x6100`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x2fa0  ldarg.0
0x2fa1  ldnull
0x2fa2  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x2fa7  brfalse.s loc_2FB4
0x2fa9  ldstr    aAddress// "address"
0x2fae  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x2fb3  throw
0x2fb4  ldarg.1
0x2fb5  ldnull
0x2fb6  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2fbb  brfalse.s loc_2FC8
0x2fbd  ldstr    aType// "type"
0x2fc2  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x2fc7  throw
0x2fc8  ldarg.0
0x2fc9  newobj   instance void System.Net.Http.Formatting.FormDataCollection::.ctor(class [System]System.Uri uri)
0x2fce  ldloca.s 0
0x2fd0  call     bool System.Net.Http.Formatting.FormUrlEncodedJson::TryParse(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> nameValuePairs, [out] class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject& value)
0x2fd5  brfalse.s loc_2FFA
0x2fd7  ldloc.0
0x2fd8  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JTokenReader::.ctor(class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken)
0x2fdd  stloc.1
0x2fde  ldarg.2
0x2fdf  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::.ctor()
0x2fe4  ldloc.1
0x2fe5  ldarg.1
0x2fe6  call     instance object [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::Deserialize(class [Newtonsoft.Json]Newtonsoft.Json.JsonReader, class [mscorlib]System.Type)
0x2feb  stind.ref
0x2fec  leave.s  loc_2FF8
0x2fee  ldloc.1
0x2fef  brfalse.s loc_2FF7
0x2ff1  ldloc.1
0x2ff2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2ff7  endfinally
0x2ff8  ldc.i4.1
0x2ff9  ret
0x2ffa  ldarg.2
0x2ffb  ldnull
0x2ffc  stind.ref
0x2ffd  ldc.i4.0
0x2ffe  ret
```
