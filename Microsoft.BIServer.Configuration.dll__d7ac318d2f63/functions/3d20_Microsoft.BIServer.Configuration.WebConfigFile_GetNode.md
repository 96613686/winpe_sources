# Microsoft.BIServer.Configuration.WebConfigFile::GetNode

- ea: `0x3d20`
- end: `0x3d2d`
- name: `Microsoft.BIServer.Configuration.WebConfigFile::GetNode`
- size: `13`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3c40`
- `0x3c60`
- `0x3c80`
- `0x3ca0`
- `0x3cd0`
- `0x3d00`

## pseudocode

```c

```

## disassembly

```asm
0x3d20  ldarg.0
0x3d21  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.WebConfigFile::_rootElement
0x3d26  ldarg.1
0x3d27  call     class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.XPath.Extensions::XPathSelectElement(class [System.Xml.Linq]System.Xml.Linq.XNode, string)
0x3d2c  ret
```
