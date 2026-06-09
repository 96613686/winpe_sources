# System.Net.Http.Properties.Resources::get_ReadAsMimeMultipartErrorReading

- ea: `0x3890`
- end: `0x38a5`
- name: `System.Net.Http.Properties.Resources::get_ReadAsMimeMultipartErrorReading`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0xc890`
- `0xcb10`

## callees

- `0x30a0`

## string_xrefs

- `0x3895`: `ReadAsMimeMultipartErrorReading`

## pseudocode

```c

```

## disassembly

```asm
0x3890  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x3895  ldstr    aReadasmimemult_2// "ReadAsMimeMultipartErrorReading"
0x389a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x389f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x38a4  ret
```
