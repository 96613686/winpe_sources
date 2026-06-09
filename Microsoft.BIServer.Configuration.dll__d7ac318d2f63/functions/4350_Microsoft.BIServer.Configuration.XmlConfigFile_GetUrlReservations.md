# Microsoft.BIServer.Configuration.XmlConfigFile::GetUrlReservations

- ea: `0x4350`
- end: `0x4387`
- name: `Microsoft.BIServer.Configuration.XmlConfigFile::GetUrlReservations`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3fa0`
- `0x3fc0`
- `0x4030`

## callees

- `0x4350`

## pseudocode

```c

```

## disassembly

```asm
0x4350  ldarg.0
0x4351  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.XmlConfigFile::_rootElement
0x4356  ldstr    aUrlreservation_1// "//URLReservations"
0x435b  call     class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.XPath.Extensions::XPathSelectElement(class [System.Xml.Linq]System.Xml.Linq.XNode, string)
0x4360  stloc.0
0x4361  ldloc.0
0x4362  brtrue.s loc_4385
0x4364  ldarg.0
0x4365  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.XmlConfigFile::_rootElement
0x436a  ldstr    aUrlreservation_2// "URLReservations"
0x436f  callvirt instance void [System.Xml.Linq]System.Xml.Linq.XContainer::Add(object)
0x4374  ldarg.0
0x4375  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.XmlConfigFile::_rootElement
0x437a  ldstr    aUrlreservation_1// "//URLReservations"
0x437f  call     class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.XPath.Extensions::XPathSelectElement(class [System.Xml.Linq]System.Xml.Linq.XNode, string)
0x4384  stloc.0
0x4385  ldloc.0
0x4386  ret
```
