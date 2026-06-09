# System.Net.Http.Formatting.FormUrlEncodedJson::Parse_0

- ea: `0x60f0`
- end: `0x60f9`
- name: `System.Net.Http.Formatting.FormUrlEncodedJson::Parse_0`
- size: `9`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7620`

## callees

- `0x6140`

## pseudocode

```c

```

## disassembly

```asm
0x60f0  ldarg.0
0x60f1  ldarg.1
0x60f2  ldc.i4.1
0x60f3  call     class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject System.Net.Http.Formatting.FormUrlEncodedJson::ParseInternal(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> nameValuePairs, int32 maxDepth, bool throwOnError)
0x60f8  ret
```
