# System.Net.Http.Properties.Resources::get_ReadAsMimeMultipartStreamProviderNull

- ea: `0x3930`
- end: `0x3945`
- name: `System.Net.Http.Properties.Resources::get_ReadAsMimeMultipartStreamProviderNull`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x2910`

## callees

- `0x30a0`

## string_xrefs

- `0x3935`: `ReadAsMimeMultipartStreamProviderNull`

## pseudocode

```c

```

## disassembly

```asm
0x3930  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x3935  ldstr    aReadasmimemult_7// "ReadAsMimeMultipartStreamProviderNull"
0x393a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x393f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3944  ret
```
