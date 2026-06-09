# System.Xaml.XmlCompatibilityReader::get_Value

- ea: `0x10d30`
- end: `0x10d8a`
- name: `System.Xaml.XmlCompatibilityReader::get_Value`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x10d30`
- `0x11d80`

## string_xrefs

- `0x10d30`: `xmlns`
- `0x10d54`: `xmlns`

## pseudocode

```c

```

## disassembly

```asm
0x10d30  ldstr    aXmlns// "xmlns"
0x10d35  ldarg.0
0x10d36  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x10d3b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x10d40  ldc.i4.4
0x10d41  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x10d46  brfalse.s loc_10D54
0x10d48  ldarg.0
0x10d49  ldsfld   string [mscorlib]System.String::Empty
0x10d4e  callvirt instance string [System.Xml]System.Xml.XmlReader::LookupNamespace(string)
0x10d53  ret
0x10d54  ldstr    aXmlns// "xmlns"
0x10d59  ldarg.0
0x10d5a  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x10d5f  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Prefix()
0x10d64  ldc.i4.4
0x10d65  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x10d6a  brfalse.s loc_10D7E
0x10d6c  ldarg.0
0x10d6d  ldarg.0
0x10d6e  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x10d73  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x10d78  callvirt instance string [System.Xml]System.Xml.XmlReader::LookupNamespace(string)
0x10d7d  ret
0x10d7e  ldarg.0
0x10d7f  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x10d84  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x10d89  ret
```
