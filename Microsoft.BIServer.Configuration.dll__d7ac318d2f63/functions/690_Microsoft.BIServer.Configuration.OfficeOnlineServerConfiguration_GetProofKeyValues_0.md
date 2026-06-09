# Microsoft.BIServer.Configuration.OfficeOnlineServerConfiguration::GetProofKeyValues_0

- ea: `0x690`
- end: `0x6cc`
- name: `Microsoft.BIServer.Configuration.OfficeOnlineServerConfiguration::GetProofKeyValues_0`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6c70`

## callees

- `0x500`
- `0x520`
- `0x530`

## pseudocode

```c

```

## disassembly

```asm
0x690  newobj   instance void Microsoft.BIServer.Configuration.OfficeProofKeyValues::.ctor()
0x695  dup
0x696  ldarg.0
0x697  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x69c  ldstr    aValue// "value"
0x6a1  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x6a6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x6ab  callvirt instance void Microsoft.BIServer.Configuration.OfficeProofKeyValues::set_Value(string value)
0x6b0  dup
0x6b1  ldarg.0
0x6b2  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x6b7  ldstr    aOldvalue// "oldvalue"
0x6bc  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x6c1  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x6c6  callvirt instance void Microsoft.BIServer.Configuration.OfficeProofKeyValues::set_OldValue(string value)
0x6cb  ret
```
