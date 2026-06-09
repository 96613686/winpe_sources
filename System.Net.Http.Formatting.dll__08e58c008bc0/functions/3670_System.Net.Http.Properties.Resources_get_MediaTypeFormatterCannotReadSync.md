# System.Net.Http.Properties.Resources::get_MediaTypeFormatterCannotReadSync

- ea: `0x3670`
- end: `0x3685`
- name: `System.Net.Http.Properties.Resources::get_MediaTypeFormatterCannotReadSync`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x6ac0`

## callees

- `0x30a0`

## string_xrefs

- `0x3675`: `MediaTypeFormatterCannotReadSync`

## pseudocode

```c

```

## disassembly

```asm
0x3670  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x3675  ldstr    aMediatypeforma_4// "MediaTypeFormatterCannotReadSync"
0x367a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x367f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3684  ret
```
