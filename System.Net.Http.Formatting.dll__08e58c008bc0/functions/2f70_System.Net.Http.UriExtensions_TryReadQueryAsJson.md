# System.Net.Http.UriExtensions::TryReadQueryAsJson

- ea: `0x2f70`
- end: `0x2f91`
- name: `System.Net.Http.UriExtensions::TryReadQueryAsJson`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x2f70`
- `0x5ef0`
- `0x6100`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x2f70  ldarg.0
0x2f71  ldnull
0x2f72  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x2f77  brfalse.s loc_2F84
0x2f79  ldstr    aAddress// "address"
0x2f7e  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x2f83  throw
0x2f84  ldarg.0
0x2f85  newobj   instance void System.Net.Http.Formatting.FormDataCollection::.ctor(class [System]System.Uri uri)
0x2f8a  ldarg.1
0x2f8b  call     bool System.Net.Http.Formatting.FormUrlEncodedJson::TryParse(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> nameValuePairs, [out] class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject& value)
0x2f90  ret
```
