# System.Xml.Xsl.Runtime.XmlRawWriterWrapper::WriteNamespaceDeclaration

- ea: `0x329b0`
- end: `0x329ec`
- name: `System.Xml.Xsl.Runtime.XmlRawWriterWrapper::WriteNamespaceDeclaration`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x329b0`

## string_xrefs

- `0x329c3`: `xmlns`
- `0x329da`: `xmlns`
- `0x329c8`: `http://www.w3.org/2000/xmlns/`
- `0x329e0`: `http://www.w3.org/2000/xmlns/`

## pseudocode

```c

```

## disassembly

```asm
0x329b0  ldarg.1
0x329b1  callvirt instance int32 [mscorlib]System.String::get_Length()
0x329b6  brtrue.s loc_329D4
0x329b8  ldarg.0
0x329b9  ldfld    class [System.Xml]System.Xml.XmlWriter System.Xml.Xsl.Runtime.XmlRawWriterWrapper::wrapped
0x329be  ldsfld   string [mscorlib]System.String::Empty
0x329c3  ldstr    aXmlns// "xmlns"
0x329c8  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2000/xmlns/"
0x329cd  ldarg.2
0x329ce  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x329d3  ret
0x329d4  ldarg.0
0x329d5  ldfld    class [System.Xml]System.Xml.XmlWriter System.Xml.Xsl.Runtime.XmlRawWriterWrapper::wrapped
0x329da  ldstr    aXmlns// "xmlns"
0x329df  ldarg.1
0x329e0  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2000/xmlns/"
0x329e5  ldarg.2
0x329e6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x329eb  ret
```
