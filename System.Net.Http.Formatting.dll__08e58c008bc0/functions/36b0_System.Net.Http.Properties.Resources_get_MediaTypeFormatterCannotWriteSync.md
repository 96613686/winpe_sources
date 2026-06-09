# System.Net.Http.Properties.Resources::get_MediaTypeFormatterCannotWriteSync

- ea: `0x36b0`
- end: `0x36c5`
- name: `System.Net.Http.Properties.Resources::get_MediaTypeFormatterCannotWriteSync`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x6a90`

## callees

- `0x30a0`

## string_xrefs

- `0x36b5`: `MediaTypeFormatterCannotWriteSync`

## pseudocode

```c

```

## disassembly

```asm
0x36b0  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x36b5  ldstr    aMediatypeforma_6// "MediaTypeFormatterCannotWriteSync"
0x36ba  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x36bf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x36c4  ret
```
