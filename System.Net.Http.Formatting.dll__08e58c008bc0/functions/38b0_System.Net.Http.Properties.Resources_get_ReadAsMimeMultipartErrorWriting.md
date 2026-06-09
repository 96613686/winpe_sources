# System.Net.Http.Properties.Resources::get_ReadAsMimeMultipartErrorWriting

- ea: `0x38b0`
- end: `0x38c5`
- name: `System.Net.Http.Properties.Resources::get_ReadAsMimeMultipartErrorWriting`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0xcb10`

## callees

- `0x30a0`

## string_xrefs

- `0x38b5`: `ReadAsMimeMultipartErrorWriting`

## pseudocode

```c

```

## disassembly

```asm
0x38b0  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x38b5  ldstr    aReadasmimemult_3// "ReadAsMimeMultipartErrorWriting"
0x38ba  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x38bf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x38c4  ret
```
