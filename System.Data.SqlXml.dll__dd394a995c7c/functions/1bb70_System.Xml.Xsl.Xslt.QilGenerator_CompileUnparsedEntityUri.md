# System.Xml.Xsl.Xslt.QilGenerator::CompileUnparsedEntityUri

- ea: `0x1bb70`
- end: `0x1bb9a`
- name: `System.Xml.Xsl.Xslt.QilGenerator::CompileUnparsedEntityUri`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1a9a0`

## callees

- `0x294a0`

## string_xrefs

- `0x1bb8e`: `unparsed-entity-uri`

## pseudocode

```c

```

## disassembly

```asm
0x1bb70  ldarg.0
0x1bb71  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1bb76  ldarg.0
0x1bb77  ldfld    class System.Xml.Xsl.Xslt.XslNode System.Xml.Xsl.Xslt.QilGenerator::lastScope
0x1bb7c  ldfld    class System.Xml.Xsl.ISourceLineInfo System.Xml.Xsl.Xslt.XslNode::SourceLine
0x1bb81  ldstr    aXsltUnsupporte// "Xslt_UnsupportedXsltFunction"
0x1bb86  ldc.i4.1
0x1bb87  newarr   [mscorlib]System.String
0x1bb8c  dup
0x1bb8d  ldc.i4.0
0x1bb8e  ldstr    aUnparsedEntity// "unparsed-entity-uri"
0x1bb93  stelem.ref
0x1bb94  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::Error(class System.Xml.Xsl.ISourceLineInfo lineInfo, string res, string[] args)
0x1bb99  ret
```
