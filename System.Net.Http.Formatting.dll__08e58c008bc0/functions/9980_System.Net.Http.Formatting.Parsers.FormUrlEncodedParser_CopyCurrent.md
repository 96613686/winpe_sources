# System.Net.Http.Formatting.Parsers.FormUrlEncodedParser::CopyCurrent

- ea: `0x9980`
- end: `0x99bd`
- name: `System.Net.Http.Formatting.Parsers.FormUrlEncodedParser::CopyCurrent`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x9790`

## callees

- `0x9980`
- `0xd870`
- `0xd8b0`

## pseudocode

```c

```

## disassembly

```asm
0x9980  ldarg.0
0x9981  ldfld    valuetype NameValueState System.Net.Http.Formatting.Parsers.FormUrlEncodedParser::_nameValueState
0x9986  brtrue.s loc_99A5
0x9988  ldarg.0
0x9989  ldfld    int64 System.Net.Http.Formatting.Parsers.FormUrlEncodedParser::_totalBytesConsumed
0x998e  ldc.i4.0
0x998f  conv.i8
0x9990  ble.s    loc_99B6
0x9992  ldarg.0
0x9993  ldfld    class CurrentNameValuePair System.Net.Http.Formatting.Parsers.FormUrlEncodedParser::_currentNameValuePair
0x9998  ldarg.0
0x9999  ldfld    class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> System.Net.Http.Formatting.Parsers.FormUrlEncodedParser::_nameValuePairs
0x999e  callvirt instance void CurrentNameValuePair::CopyNameOnlyTo(class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> nameValuePairs)
0x99a3  br.s     loc_99B6
0x99a5  ldarg.0
0x99a6  ldfld    class CurrentNameValuePair System.Net.Http.Formatting.Parsers.FormUrlEncodedParser::_currentNameValuePair
0x99ab  ldarg.0
0x99ac  ldfld    class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> System.Net.Http.Formatting.Parsers.FormUrlEncodedParser::_nameValuePairs
0x99b1  callvirt instance void CurrentNameValuePair::CopyTo(class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> nameValuePairs)
0x99b6  ldarg.1
0x99b7  brfalse.s loc_99BB
0x99b9  ldarg.1
0x99ba  ret
0x99bb  ldc.i4.1
0x99bc  ret
```
