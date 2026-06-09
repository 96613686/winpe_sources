# System.Net.Http.Properties.Resources::get_AsyncResult_MultipleCompletes

- ea: `0x3110`
- end: `0x3125`
- name: `System.Net.Http.Properties.Resources::get_AsyncResult_MultipleCompletes`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x5100`

## callees

- `0x30a0`

## string_xrefs

- `0x3115`: `AsyncResult_MultipleCompletes`

## pseudocode

```c

```

## disassembly

```asm
0x3110  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x3115  ldstr    aAsyncresultMul// "AsyncResult_MultipleCompletes"
0x311a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x311f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3124  ret
```
