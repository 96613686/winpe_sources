# System.Net.Http.Formatting.FormDataCollection::ReadAsNameValueCollection

- ea: `0x5fd0`
- end: `0x5ff3`
- name: `System.Net.Http.Formatting.FormDataCollection::ReadAsNameValueCollection`
- size: `35`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x2f50`
- `0x3e60`
- `0x6000`
- `0x6010`
- `0x8b50`
- `0xbcd0`

## callees

- `0x5fd0`
- `0xafc0`

## pseudocode

```c

```

## disassembly

```asm
0x5fd0  ldarg.0
0x5fd1  ldfld    class [System]System.Collections.Specialized.NameValueCollection System.Net.Http.Formatting.FormDataCollection::_nameValueCollection
0x5fd6  brtrue.s loc_5FEC
0x5fd8  ldarg.0
0x5fd9  call     class System.Net.Http.Formatting.Internal.HttpValueCollection System.Net.Http.Formatting.Internal.HttpValueCollection::Create(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> pairs)
0x5fde  stloc.0
0x5fdf  ldarg.0
0x5fe0  ldflda   class [System]System.Collections.Specialized.NameValueCollection System.Net.Http.Formatting.FormDataCollection::_nameValueCollection
0x5fe5  ldloc.0
0x5fe6  call     T0x2B000044
0x5feb  pop
0x5fec  ldarg.0
0x5fed  ldfld    class [System]System.Collections.Specialized.NameValueCollection System.Net.Http.Formatting.FormDataCollection::_nameValueCollection
0x5ff2  ret
```
