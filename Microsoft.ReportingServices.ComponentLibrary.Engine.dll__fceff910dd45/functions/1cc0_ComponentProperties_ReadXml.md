# ComponentProperties::ReadXml

- ea: `0x1cc0`
- end: `0x1d4d`
- name: `ComponentProperties::ReadXml`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1cc0`

## pseudocode

```c

```

## disassembly

```asm
0x1cc0  ldarg.0
0x1cc1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Clear()
0x1cc6  ldarg.1
0x1cc7  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x1ccc  pop
0x1ccd  ldarg.1
0x1cce  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x1cd3  brtrue.s loc_1D45
0x1cd5  ldarg.1
0x1cd6  ldstr    aProperties// "Properties"
0x1cdb  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement(string)
0x1ce0  ldarg.1
0x1ce1  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x1ce6  pop
0x1ce7  br.s     loc_1D36
0x1ce9  ldnull
0x1cea  stloc.0
0x1ceb  ldnull
0x1cec  stloc.1
0x1ced  ldarg.1
0x1cee  ldstr    aName_0// "Name"
0x1cf3  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x1cf8  stloc.0
0x1cf9  ldarg.1
0x1cfa  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x1cff  brtrue.s loc_1D0F
0x1d01  ldarg.1
0x1d02  ldstr    aProperty// "Property"
0x1d07  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString(string)
0x1d0c  stloc.1
0x1d0d  br.s     loc_1D16
0x1d0f  ldarg.1
0x1d10  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1d15  pop
0x1d16  ldloc.0
0x1d17  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1d1c  brtrue.s loc_1D2F
0x1d1e  ldarg.0
0x1d1f  ldloc.0
0x1d20  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x1d25  brtrue.s loc_1D2F
0x1d27  ldarg.0
0x1d28  ldloc.0
0x1d29  ldloc.1
0x1d2a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1d2f  ldarg.1
0x1d30  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x1d35  pop
0x1d36  ldarg.1
0x1d37  callvirt instance bool [System.Xml]System.Xml.XmlReader::IsStartElement()
0x1d3c  brtrue.s loc_1CE9
0x1d3e  ldarg.1
0x1d3f  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadEndElement()
0x1d44  ret
0x1d45  ldarg.1
0x1d46  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1d4b  pop
0x1d4c  ret
```
