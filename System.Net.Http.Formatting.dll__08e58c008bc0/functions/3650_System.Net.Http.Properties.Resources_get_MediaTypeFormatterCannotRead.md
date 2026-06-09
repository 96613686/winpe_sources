# System.Net.Http.Properties.Resources::get_MediaTypeFormatterCannotRead

- ea: `0x3650`
- end: `0x3665`
- name: `System.Net.Http.Properties.Resources::get_MediaTypeFormatterCannotRead`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x7f20`

## callees

- `0x30a0`

## string_xrefs

- `0x3655`: `MediaTypeFormatterCannotRead`

## pseudocode

```c

```

## disassembly

```asm
0x3650  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x3655  ldstr    aMediatypeforma_3// "MediaTypeFormatterCannotRead"
0x365a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x365f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3664  ret
```
