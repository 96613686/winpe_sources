# System.Net.Http.Properties.Resources::get_MediaTypeFormatterCannotWrite

- ea: `0x3690`
- end: `0x36a5`
- name: `System.Net.Http.Properties.Resources::get_MediaTypeFormatterCannotWrite`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x7f80`

## callees

- `0x30a0`

## string_xrefs

- `0x3695`: `MediaTypeFormatterCannotWrite`

## pseudocode

```c

```

## disassembly

```asm
0x3690  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x3695  ldstr    aMediatypeforma_5// "MediaTypeFormatterCannotWrite"
0x369a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x369f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x36a4  ret
```
