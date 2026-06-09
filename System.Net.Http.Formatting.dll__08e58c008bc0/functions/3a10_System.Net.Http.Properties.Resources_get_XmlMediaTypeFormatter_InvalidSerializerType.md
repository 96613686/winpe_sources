# System.Net.Http.Properties.Resources::get_XmlMediaTypeFormatter_InvalidSerializerType

- ea: `0x3a10`
- end: `0x3a25`
- name: `System.Net.Http.Properties.Resources::get_XmlMediaTypeFormatter_InvalidSerializerType`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x96f0`

## callees

- `0x30a0`

## string_xrefs

- `0x3a15`: `XmlMediaTypeFormatter_InvalidSerializerType`

## pseudocode

```c

```

## disassembly

```asm
0x3a10  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x3a15  ldstr    aXmlmediatypefo// "XmlMediaTypeFormatter_InvalidSerializer"...
0x3a1a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x3a1f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3a24  ret
```
