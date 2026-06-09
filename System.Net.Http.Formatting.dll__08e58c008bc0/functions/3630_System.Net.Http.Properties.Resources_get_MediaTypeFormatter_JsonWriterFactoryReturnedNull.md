# System.Net.Http.Properties.Resources::get_MediaTypeFormatter_JsonWriterFactoryReturnedNull

- ea: `0x3630`
- end: `0x3645`
- name: `System.Net.Http.Properties.Resources::get_MediaTypeFormatter_JsonWriterFactoryReturnedNull`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x58b0`

## callees

- `0x30a0`

## string_xrefs

- `0x3635`: `MediaTypeFormatter_JsonWriterFactoryReturnedNull`

## pseudocode

```c

```

## disassembly

```asm
0x3630  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x3635  ldstr    aMediatypeforma_2// "MediaTypeFormatter_JsonWriterFactoryRet"...
0x363a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x363f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3644  ret
```
