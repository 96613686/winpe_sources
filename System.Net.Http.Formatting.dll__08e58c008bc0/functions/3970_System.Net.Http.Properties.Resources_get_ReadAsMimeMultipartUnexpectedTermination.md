# System.Net.Http.Properties.Resources::get_ReadAsMimeMultipartUnexpectedTermination

- ea: `0x3970`
- end: `0x3985`
- name: `System.Net.Http.Properties.Resources::get_ReadAsMimeMultipartUnexpectedTermination`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0xdac0`

## callees

- `0x30a0`

## string_xrefs

- `0x3975`: `ReadAsMimeMultipartUnexpectedTermination`

## pseudocode

```c

```

## disassembly

```asm
0x3970  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x3975  ldstr    aReadasmimemult_9// "ReadAsMimeMultipartUnexpectedTerminatio"...
0x397a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x397f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3984  ret
```
