# System.Net.Http.Properties.Resources::get_ReadAsMimeMultipartStreamProviderReadOnly

- ea: `0x3950`
- end: `0x3965`
- name: `System.Net.Http.Properties.Resources::get_ReadAsMimeMultipartStreamProviderReadOnly`
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

- `0x3955`: `ReadAsMimeMultipartStreamProviderReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0x3950  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x3955  ldstr    aReadasmimemult_8// "ReadAsMimeMultipartStreamProviderReadOn"...
0x395a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x395f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3964  ret
```
