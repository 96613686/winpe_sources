# System.Xml.Xsl.Xslt.XsltQilFactory::InvokeMsNamespaceUri

- ea: `0x268d0`
- end: `0x268fa`
- name: `System.Xml.Xsl.Xslt.XsltQilFactory::InvokeMsNamespaceUri`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1a9a0`

## callees

- `0x37a80`
- `0x38420`

## string_xrefs

- `0x268d2`: `ms:namespace-uri`

## pseudocode

```c

```

## disassembly

```asm
0x268d0  ldarg.0
0x268d1  ldarg.0
0x268d2  ldstr    aMsNamespaceUri// "ms:namespace-uri"
0x268d7  call     instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilPatternFactory::QName(string local)
0x268dc  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::MSNamespaceUri
0x268e1  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::StringX
0x268e6  ldc.i4.2
0x268e7  newarr   System.Xml.Xsl.Qil.QilNode
0x268ec  dup
0x268ed  ldc.i4.0
0x268ee  ldarg.1
0x268ef  stelem.ref
0x268f0  dup
0x268f1  ldc.i4.1
0x268f2  ldarg.2
0x268f3  stelem.ref
0x268f4  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::XsltInvokeEarlyBound(class System.Xml.Xsl.Qil.QilNode name, class [mscorlib]System.Reflection.MethodInfo d, class System.Xml.Xsl.XmlQueryType t, class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode> args)
0x268f9  ret
```
