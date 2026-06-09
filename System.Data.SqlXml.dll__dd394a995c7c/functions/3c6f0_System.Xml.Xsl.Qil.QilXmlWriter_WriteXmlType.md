# System.Xml.Xsl.Qil.QilXmlWriter::WriteXmlType

- ea: `0x3c6f0`
- end: `0x3c722`
- name: `System.Xml.Xsl.Qil.QilXmlWriter::WriteXmlType`
- size: `50`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x3c850`
- `0x3c9b0`

## callees

- `0x24f0`
- `0x376c0`
- `0x3c6f0`

## string_xrefs

- `0x3c6f6`: `xmlType`

## pseudocode

```c

```

## disassembly

```asm
0x3c6f0  ldarg.0
0x3c6f1  ldfld    class [System.Xml]System.Xml.XmlWriter System.Xml.Xsl.Qil.QilXmlWriter::writer
0x3c6f6  ldstr    aXmltype// "xmlType"
0x3c6fb  ldarg.1
0x3c6fc  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x3c701  ldarg.0
0x3c702  ldfld    valuetype Options System.Xml.Xsl.Qil.QilXmlWriter::options
0x3c707  ldc.i4.4
0x3c708  and
0x3c709  brtrue.s loc_3C712
0x3c70b  ldstr    aG// "G"
0x3c710  br.s     loc_3C717
0x3c712  ldstr    aS// "S"
0x3c717  callvirt instance string System.Xml.Xsl.XmlQueryType::ToString(string format)
0x3c71c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x3c721  ret
```
