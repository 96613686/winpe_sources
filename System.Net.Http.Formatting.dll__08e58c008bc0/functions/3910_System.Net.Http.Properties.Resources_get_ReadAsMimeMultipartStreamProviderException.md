# System.Net.Http.Properties.Resources::get_ReadAsMimeMultipartStreamProviderException

- ea: `0x3910`
- end: `0x3925`
- name: `System.Net.Http.Properties.Resources::get_ReadAsMimeMultipartStreamProviderException`
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

- `0x3915`: `ReadAsMimeMultipartStreamProviderException`

## pseudocode

```c

```

## disassembly

```asm
0x3910  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x3915  ldstr    aReadasmimemult_6// "ReadAsMimeMultipartStreamProviderExcept"...
0x391a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x391f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3924  ret
```
