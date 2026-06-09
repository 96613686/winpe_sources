# Microsoft.BIServer.Configuration.ConfigReader::ReadIntSettingWithValidation

- ea: `0x1740`
- end: `0x175d`
- name: `Microsoft.BIServer.Configuration.ConfigReader::ReadIntSettingWithValidation`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1740`
- `0x1760`

## pseudocode

```c

```

## disassembly

```asm
0x1740  ldarg.2
0x1741  ldarg.1
0x1742  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x1747  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x174c  brtrue.s loc_1750
0x174e  ldarg.3
0x174f  ret
0x1750  ldarg.0
0x1751  ldarg.1
0x1752  ldarg.2
0x1753  ldarg.s  4
0x1755  ldarg.s  5
0x1757  call     instance int32 Microsoft.BIServer.Configuration.ConfigReader::ReadIntSettingWithValidation(string element, class [System.Xml.Linq]System.Xml.Linq.XElement configSection, int32 minValue, [opt] int32 maxValue)
0x175c  ret
```
