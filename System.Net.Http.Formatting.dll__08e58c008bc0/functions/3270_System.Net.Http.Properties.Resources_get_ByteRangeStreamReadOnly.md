# System.Net.Http.Properties.Resources::get_ByteRangeStreamReadOnly

- ea: `0x3270`
- end: `0x3285`
- name: `System.Net.Http.Properties.Resources::get_ByteRangeStreamReadOnly`
- size: `21`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x4d10`
- `0x4d30`
- `0x4d50`
- `0x4d70`
- `0x4d90`
- `0x4db0`

## callees

- `0x30a0`

## string_xrefs

- `0x3275`: `ByteRangeStreamReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0x3270  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x3275  ldstr    aByterangestrea_7// "ByteRangeStreamReadOnly"
0x327a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x327f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3284  ret
```
