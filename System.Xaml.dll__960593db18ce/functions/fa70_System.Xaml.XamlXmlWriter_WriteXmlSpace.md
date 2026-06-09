# System.Xaml.XamlXmlWriter::WriteXmlSpace

- ea: `0xfa70`
- end: `0xfa90`
- name: `System.Xaml.XamlXmlWriter::WriteXmlSpace`
- size: `32`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x2d8d0`
- `0x2dba0`

## string_xrefs

- `0xfa80`: `http://www.w3.org/XML/1998/namespace`

## pseudocode

```c

```

## disassembly

```asm
0xfa70  ldarg.0
0xfa71  ldfld    class [System.Xml]System.Xml.XmlWriter System.Xaml.XamlXmlWriter::output
0xfa76  ldstr    aXml// "xml"
0xfa7b  ldstr    aSpace// "space"
0xfa80  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0xfa85  ldstr    aPreserve// "preserve"
0xfa8a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0xfa8f  ret
```
