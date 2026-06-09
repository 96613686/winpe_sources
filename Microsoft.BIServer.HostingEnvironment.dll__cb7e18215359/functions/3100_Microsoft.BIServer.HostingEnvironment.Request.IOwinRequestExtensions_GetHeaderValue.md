# Microsoft.BIServer.HostingEnvironment.Request.IOwinRequestExtensions::GetHeaderValue

- ea: `0x3100`
- end: `0x312d`
- name: `Microsoft.BIServer.HostingEnvironment.Request.IOwinRequestExtensions::GetHeaderValue`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x3100`

## pseudocode

```c

```

## disassembly

```asm
0x3100  ldnull
0x3101  stloc.0
0x3102  ldarg.0
0x3103  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Headers()
0x3108  ldarg.1
0x3109  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string[]>::ContainsKey(var<u1>)
0x310e  brfalse.s loc_3122
0x3110  ldarg.0
0x3111  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Headers()
0x3116  ldarg.1
0x3117  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> [Microsoft.Owin]Microsoft.Owin.IReadableStringCollection::GetValues(string)
0x311c  call     T0x2B000010
0x3121  stloc.0
0x3122  ldloc.0
0x3123  dup
0x3124  brtrue.s loc_312C
0x3126  pop
0x3127  ldsfld   string [mscorlib]System.String::Empty
0x312c  ret
```
