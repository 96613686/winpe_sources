# System.Net.Http.Properties.Resources::get_ReadAsMimeMultipartHeaderParseError

- ea: `0x38d0`
- end: `0x38e5`
- name: `System.Net.Http.Properties.Resources::get_ReadAsMimeMultipartHeaderParseError`
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

- `0x38d5`: `ReadAsMimeMultipartHeaderParseError`

## pseudocode

```c

```

## disassembly

```asm
0x38d0  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x38d5  ldstr    aReadasmimemult_4// "ReadAsMimeMultipartHeaderParseError"
0x38da  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x38df  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x38e4  ret
```
