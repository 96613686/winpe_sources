# System.Net.Http.Properties.Resources::get_XmlMediaTypeFormatter_NullReturnedSerializer

- ea: `0x3a30`
- end: `0x3a45`
- name: `System.Net.Http.Properties.Resources::get_XmlMediaTypeFormatter_NullReturnedSerializer`
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

- `0x3a35`: `XmlMediaTypeFormatter_NullReturnedSerializer`

## pseudocode

```c

```

## disassembly

```asm
0x3a30  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x3a35  ldstr    aXmlmediatypefo_0// "XmlMediaTypeFormatter_NullReturnedSeria"...
0x3a3a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x3a3f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3a44  ret
```
