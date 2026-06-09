# Microsoft.BIServer.Configuration.XmlConfigFile::GetDataElement

- ea: `0x42d0`
- end: `0x42e1`
- name: `Microsoft.BIServer.Configuration.XmlConfigFile::GetDataElement`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x4180`

## string_xrefs

- `0x42d6`: `/Extensions/Data`

## pseudocode

```c

```

## disassembly

```asm
0x42d0  ldarg.0
0x42d1  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.XmlConfigFile::_rootElement
0x42d6  ldstr    aExtensionsData// "/Extensions/Data"
0x42db  call     class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.XPath.Extensions::XPathSelectElement(class [System.Xml.Linq]System.Xml.Linq.XNode, string)
0x42e0  ret
```
