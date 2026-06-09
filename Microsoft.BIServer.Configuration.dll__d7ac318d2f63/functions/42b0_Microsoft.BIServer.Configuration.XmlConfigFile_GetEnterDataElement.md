# Microsoft.BIServer.Configuration.XmlConfigFile::GetEnterDataElement

- ea: `0x42b0`
- end: `0x42c1`
- name: `Microsoft.BIServer.Configuration.XmlConfigFile::GetEnterDataElement`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x4180`

## string_xrefs

- `0x42b6`: `//Extension[@Name = 'ENTERDATA']`

## pseudocode

```c

```

## disassembly

```asm
0x42b0  ldarg.0
0x42b1  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.XmlConfigFile::_rootElement
0x42b6  ldstr    aExtensionNameE// "//Extension[@Name = 'ENTERDATA']"
0x42bb  call     class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.XPath.Extensions::XPathSelectElement(class [System.Xml.Linq]System.Xml.Linq.XNode, string)
0x42c0  ret
```
