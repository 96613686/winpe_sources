# System.Xml.Xsl.Xslt.XsltQilFactory::InvokeBaseUri

- ea: `0x26570`
- end: `0x26596`
- name: `System.Xml.Xsl.Xslt.XsltQilFactory::InvokeBaseUri`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1b960`

## callees

- `0x37a80`
- `0x38420`

## string_xrefs

- `0x26572`: `base-uri`

## pseudocode

```c

```

## disassembly

```asm
0x26570  ldarg.0
0x26571  ldarg.0
0x26572  ldstr    aBaseUri// "base-uri"
0x26577  call     instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilPatternFactory::QName(string local)
0x2657c  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::BaseUri
0x26581  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::StringX
0x26586  ldc.i4.1
0x26587  newarr   System.Xml.Xsl.Qil.QilNode
0x2658c  dup
0x2658d  ldc.i4.0
0x2658e  ldarg.1
0x2658f  stelem.ref
0x26590  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::XsltInvokeEarlyBound(class System.Xml.Xsl.Qil.QilNode name, class [mscorlib]System.Reflection.MethodInfo d, class System.Xml.Xsl.XmlQueryType t, class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode> args)
0x26595  ret
```
