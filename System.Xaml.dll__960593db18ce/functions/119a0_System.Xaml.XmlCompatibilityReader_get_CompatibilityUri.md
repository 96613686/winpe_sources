# System.Xaml.XmlCompatibilityReader::get_CompatibilityUri

- ea: `0x119a0`
- end: `0x119ca`
- name: `System.Xaml.XmlCompatibilityReader::get_CompatibilityUri`
- size: `42`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10900`
- `0x10a40`
- `0x11010`
- `0x110b0`

## callees

- `0x119a0`
- `0x11d80`

## string_xrefs

- `0x119b4`: `http://schemas.openxmlformats.org/markup-compatibility/2006`

## pseudocode

```c

```

## disassembly

```asm
0x119a0  ldarg.0
0x119a1  ldfld    string System.Xaml.XmlCompatibilityReader::_compatibilityUri
0x119a6  brtrue.s loc_119C3
0x119a8  ldarg.0
0x119a9  ldarg.0
0x119aa  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x119af  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x119b4  ldstr    aHttpSchemasOpe// "http://schemas.openxmlformats.org/marku"...
0x119b9  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x119be  stfld    string System.Xaml.XmlCompatibilityReader::_compatibilityUri
0x119c3  ldarg.0
0x119c4  ldfld    string System.Xaml.XmlCompatibilityReader::_compatibilityUri
0x119c9  ret
```
