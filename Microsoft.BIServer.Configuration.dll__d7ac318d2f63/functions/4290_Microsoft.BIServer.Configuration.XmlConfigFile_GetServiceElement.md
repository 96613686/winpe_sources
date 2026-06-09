# Microsoft.BIServer.Configuration.XmlConfigFile::GetServiceElement

- ea: `0x4290`
- end: `0x42a1`
- name: `Microsoft.BIServer.Configuration.XmlConfigFile::GetServiceElement`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x4230`

## string_xrefs

- `0x4296`: `/Service`

## pseudocode

```c

```

## disassembly

```asm
0x4290  ldarg.0
0x4291  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.XmlConfigFile::_rootElement
0x4296  ldstr    aService// "/Service"
0x429b  call     class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.XPath.Extensions::XPathSelectElement(class [System.Xml.Linq]System.Xml.Linq.XNode, string)
0x42a0  ret
```
