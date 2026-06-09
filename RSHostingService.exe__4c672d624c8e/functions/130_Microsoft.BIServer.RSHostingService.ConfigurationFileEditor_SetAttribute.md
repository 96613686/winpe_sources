# Microsoft.BIServer.RSHostingService.ConfigurationFileEditor::SetAttribute

- ea: `0x130`
- end: `0x165`
- name: `Microsoft.BIServer.RSHostingService.ConfigurationFileEditor::SetAttribute`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x40`

## callees

- `0x130`

## pseudocode

```c

```

## disassembly

```asm
0x130  ldarg.2
0x131  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x136  ldarg.3
0x137  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x13c  brtrue.s loc_151
0x13e  ldarg.2
0x13f  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x144  ldarg.1
0x145  ldarg.3
0x146  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x14b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x150  pop
0x151  ldarg.2
0x152  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x157  ldarg.3
0x158  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x15d  ldarg.s  4
0x15f  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x164  ret
```
