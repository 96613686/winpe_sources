# System.Net.Http.FormattingUtilities::IsJTokenType

- ea: `0x12c0`
- end: `0x12d1`
- name: `System.Net.Http.FormattingUtilities::IsJTokenType`
- size: `17`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x7590`
- `0x7620`
- `0x8530`

## pseudocode

```c

```

## disassembly

```asm
0x12c0  ldtoken  [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken
0x12c5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12ca  ldarg.0
0x12cb  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x12d0  ret
```
