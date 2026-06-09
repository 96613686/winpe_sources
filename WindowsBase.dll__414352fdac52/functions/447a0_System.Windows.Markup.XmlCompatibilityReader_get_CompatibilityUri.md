# System.Windows.Markup.XmlCompatibilityReader::get_CompatibilityUri

- ea: `0x447a0`
- end: `0x447ca`
- name: `System.Windows.Markup.XmlCompatibilityReader::get_CompatibilityUri`
- size: `42`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x43700`
- `0x43840`
- `0x43e10`
- `0x43eb0`

## callees

- `0x447a0`
- `0x44b80`

## string_xrefs

- `0x447b4`: `http://schemas.openxmlformats.org/markup-compatibility/2006`

## pseudocode

```c

```

## disassembly

```asm
0x447a0  ldarg.0
0x447a1  ldfld    string System.Windows.Markup.XmlCompatibilityReader::_compatibilityUri
0x447a6  brtrue.s loc_447C3
0x447a8  ldarg.0
0x447a9  ldarg.0
0x447aa  call     instance class [System.Xml]System.Xml.XmlReader System.Windows.Markup.XmlWrappingReader::get_Reader()
0x447af  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x447b4  ldstr    aHttpSchemasOpe_5// "http://schemas.openxmlformats.org/marku"...
0x447b9  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x447be  stfld    string System.Windows.Markup.XmlCompatibilityReader::_compatibilityUri
0x447c3  ldarg.0
0x447c4  ldfld    string System.Windows.Markup.XmlCompatibilityReader::_compatibilityUri
0x447c9  ret
```
