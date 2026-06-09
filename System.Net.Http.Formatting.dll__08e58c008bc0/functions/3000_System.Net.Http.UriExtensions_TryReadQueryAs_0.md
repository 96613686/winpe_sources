# System.Net.Http.UriExtensions::TryReadQueryAs_0

- ea: `0x3000`
- end: `0x303a`
- name: `System.Net.Http.UriExtensions::TryReadQueryAs_0`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x3000`
- `0x5ef0`
- `0x6100`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x3000  ldarg.0
0x3001  ldnull
0x3002  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x3007  brfalse.s loc_3014
0x3009  ldstr    aAddress// "address"
0x300e  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x3013  throw
0x3014  ldarg.0
0x3015  newobj   instance void System.Net.Http.Formatting.FormDataCollection::.ctor(class [System]System.Uri uri)
0x301a  ldloca.s 0
0x301c  call     bool System.Net.Http.Formatting.FormUrlEncodedJson::TryParse(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> nameValuePairs, [out] class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject& value)
0x3021  brfalse.s loc_3031
0x3023  ldarg.1
0x3024  ldloc.0
0x3025  callvirt T0x2B000037
0x302a  stobj    mvar<u1>
0x302f  ldc.i4.1
0x3030  ret
0x3031  ldarg.1
0x3032  initobj  mvar<u1>
0x3038  ldc.i4.0
0x3039  ret
```
