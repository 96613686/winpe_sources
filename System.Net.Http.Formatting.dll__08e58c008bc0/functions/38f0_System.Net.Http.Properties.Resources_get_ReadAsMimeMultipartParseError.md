# System.Net.Http.Properties.Resources::get_ReadAsMimeMultipartParseError

- ea: `0x38f0`
- end: `0x3905`
- name: `System.Net.Http.Properties.Resources::get_ReadAsMimeMultipartParseError`
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

- `0x38f5`: `ReadAsMimeMultipartParseError`

## pseudocode

```c

```

## disassembly

```asm
0x38f0  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x38f5  ldstr    aReadasmimemult_5// "ReadAsMimeMultipartParseError"
0x38fa  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x38ff  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3904  ret
```
