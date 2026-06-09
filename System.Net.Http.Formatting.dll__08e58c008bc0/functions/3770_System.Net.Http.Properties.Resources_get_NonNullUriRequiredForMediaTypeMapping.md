# System.Net.Http.Properties.Resources::get_NonNullUriRequiredForMediaTypeMapping

- ea: `0x3770`
- end: `0x3785`
- name: `System.Net.Http.Properties.Resources::get_NonNullUriRequiredForMediaTypeMapping`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x8b50`

## callees

- `0x30a0`

## string_xrefs

- `0x3775`: `NonNullUriRequiredForMediaTypeMapping`

## pseudocode

```c

```

## disassembly

```asm
0x3770  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x3775  ldstr    aNonnullurirequ// "NonNullUriRequiredForMediaTypeMapping"
0x377a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x377f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3784  ret
```
