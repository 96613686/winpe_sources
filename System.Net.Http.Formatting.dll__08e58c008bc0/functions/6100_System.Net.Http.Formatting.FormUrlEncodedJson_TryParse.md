# System.Net.Http.Formatting.FormUrlEncodedJson::TryParse

- ea: `0x6100`
- end: `0x6115`
- name: `System.Net.Http.Formatting.FormUrlEncodedJson::TryParse`
- size: `21`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2f70`
- `0x2fa0`
- `0x3000`

## callees

- `0x6140`

## pseudocode

```c

```

## disassembly

```asm
0x6100  ldarg.1
0x6101  ldarg.0
0x6102  ldc.i4   0x7FFFFFFF
0x6107  ldc.i4.0
0x6108  call     class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject System.Net.Http.Formatting.FormUrlEncodedJson::ParseInternal(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> nameValuePairs, int32 maxDepth, bool throwOnError)
0x610d  dup
0x610e  stloc.0
0x610f  stind.ref
0x6110  ldloc.0
0x6111  ldnull
0x6112  cgt.un
0x6114  ret
```
