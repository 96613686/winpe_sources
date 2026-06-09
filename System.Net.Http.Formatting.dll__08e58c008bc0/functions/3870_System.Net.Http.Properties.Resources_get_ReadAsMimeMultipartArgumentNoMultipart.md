# System.Net.Http.Properties.Resources::get_ReadAsMimeMultipartArgumentNoMultipart

- ea: `0x3870`
- end: `0x3885`
- name: `System.Net.Http.Properties.Resources::get_ReadAsMimeMultipartArgumentNoMultipart`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0xa8a0`

## callees

- `0x30a0`

## string_xrefs

- `0x3875`: `ReadAsMimeMultipartArgumentNoMultipart`

## pseudocode

```c

```

## disassembly

```asm
0x3870  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x3875  ldstr    aReadasmimemult_1// "ReadAsMimeMultipartArgumentNoMultipart"
0x387a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x387f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3884  ret
```
