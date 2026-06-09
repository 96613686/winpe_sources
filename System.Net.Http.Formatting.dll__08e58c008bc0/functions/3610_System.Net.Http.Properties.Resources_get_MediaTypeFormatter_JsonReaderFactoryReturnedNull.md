# System.Net.Http.Properties.Resources::get_MediaTypeFormatter_JsonReaderFactoryReturnedNull

- ea: `0x3610`
- end: `0x3625`
- name: `System.Net.Http.Properties.Resources::get_MediaTypeFormatter_JsonReaderFactoryReturnedNull`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x5730`

## callees

- `0x30a0`

## string_xrefs

- `0x3615`: `MediaTypeFormatter_JsonReaderFactoryReturnedNull`

## pseudocode

```c

```

## disassembly

```asm
0x3610  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x3615  ldstr    aMediatypeforma_1// "MediaTypeFormatter_JsonReaderFactoryRet"...
0x361a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x361f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3624  ret
```
