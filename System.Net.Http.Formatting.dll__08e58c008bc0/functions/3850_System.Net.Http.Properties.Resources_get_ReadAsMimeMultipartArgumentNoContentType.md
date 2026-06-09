# System.Net.Http.Properties.Resources::get_ReadAsMimeMultipartArgumentNoContentType

- ea: `0x3850`
- end: `0x3865`
- name: `System.Net.Http.Properties.Resources::get_ReadAsMimeMultipartArgumentNoContentType`
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

- `0x3855`: `ReadAsMimeMultipartArgumentNoContentType`

## pseudocode

```c

```

## disassembly

```asm
0x3850  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x3855  ldstr    aReadasmimemult_0// "ReadAsMimeMultipartArgumentNoContentTyp"...
0x385a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x385f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3864  ret
```
