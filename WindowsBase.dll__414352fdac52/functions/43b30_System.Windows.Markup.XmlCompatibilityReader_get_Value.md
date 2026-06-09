# System.Windows.Markup.XmlCompatibilityReader::get_Value

- ea: `0x43b30`
- end: `0x43b8a`
- name: `System.Windows.Markup.XmlCompatibilityReader::get_Value`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x43b30`
- `0x44b80`

## string_xrefs

- `0x43b30`: `xmlns`
- `0x43b54`: `xmlns`

## pseudocode

```c

```

## disassembly

```asm
0x43b30  ldstr    aXmlns// "xmlns"
0x43b35  ldarg.0
0x43b36  call     instance class [System.Xml]System.Xml.XmlReader System.Windows.Markup.XmlWrappingReader::get_Reader()
0x43b3b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x43b40  ldc.i4.4
0x43b41  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x43b46  brfalse.s loc_43B54
0x43b48  ldarg.0
0x43b49  ldsfld   string [mscorlib]System.String::Empty
0x43b4e  callvirt instance string [System.Xml]System.Xml.XmlReader::LookupNamespace(string)
0x43b53  ret
0x43b54  ldstr    aXmlns// "xmlns"
0x43b59  ldarg.0
0x43b5a  call     instance class [System.Xml]System.Xml.XmlReader System.Windows.Markup.XmlWrappingReader::get_Reader()
0x43b5f  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Prefix()
0x43b64  ldc.i4.4
0x43b65  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x43b6a  brfalse.s loc_43B7E
0x43b6c  ldarg.0
0x43b6d  ldarg.0
0x43b6e  call     instance class [System.Xml]System.Xml.XmlReader System.Windows.Markup.XmlWrappingReader::get_Reader()
0x43b73  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x43b78  callvirt instance string [System.Xml]System.Xml.XmlReader::LookupNamespace(string)
0x43b7d  ret
0x43b7e  ldarg.0
0x43b7f  call     instance class [System.Xml]System.Xml.XmlReader System.Windows.Markup.XmlWrappingReader::get_Reader()
0x43b84  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x43b89  ret
```
