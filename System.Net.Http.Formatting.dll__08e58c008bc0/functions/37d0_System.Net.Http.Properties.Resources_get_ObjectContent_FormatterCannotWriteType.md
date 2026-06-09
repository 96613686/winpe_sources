# System.Net.Http.Properties.Resources::get_ObjectContent_FormatterCannotWriteType

- ea: `0x37d0`
- end: `0x37e5`
- name: `System.Net.Http.Properties.Resources::get_ObjectContent_FormatterCannotWriteType`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x2d60`

## callees

- `0x30a0`

## string_xrefs

- `0x37d5`: `ObjectContent_FormatterCannotWriteType`

## pseudocode

```c

```

## disassembly

```asm
0x37d0  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x37d5  ldstr    aObjectcontentF// "ObjectContent_FormatterCannotWriteType"
0x37da  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x37df  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x37e4  ret
```
