# Microsoft.BIServer.Configuration.ConfigReader::ReadIntSettingWithValidation_0

- ea: `0x1760`
- end: `0x177c`
- name: `Microsoft.BIServer.Configuration.ConfigReader::ReadIntSettingWithValidation_0`
- size: `28`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1430`
- `0x14c0`
- `0x1740`

## callees

- `0x17e0`

## pseudocode

```c

```

## disassembly

```asm
0x1760  ldarg.0
0x1761  ldarg.1
0x1762  ldarg.3
0x1763  ldarg.s  4
0x1765  ldarg.2
0x1766  ldarg.1
0x1767  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x176c  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x1771  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x1776  call     instance int32 Microsoft.BIServer.Configuration.ConfigReader::TryGetInt(string key, int32 minValue, int32 maxValue, string settingValue)
0x177b  ret
```
