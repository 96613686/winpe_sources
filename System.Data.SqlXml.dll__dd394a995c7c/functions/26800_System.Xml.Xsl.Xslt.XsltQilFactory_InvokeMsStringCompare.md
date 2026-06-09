# System.Xml.Xsl.Xslt.XsltQilFactory::InvokeMsStringCompare

- ea: `0x26800`
- end: `0x26833`
- name: `System.Xml.Xsl.Xslt.XsltQilFactory::InvokeMsStringCompare`
- size: `51`
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

- `0x26802`: `ms:string-compare`

## pseudocode

```c

```

## disassembly

```asm
0x26800  ldarg.0
0x26801  ldarg.0
0x26802  ldstr    aMsStringCompar// "ms:string-compare"
0x26807  call     instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilPatternFactory::QName(string local)
0x2680c  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::MSStringCompare
0x26811  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::DoubleX
0x26816  ldc.i4.4
0x26817  newarr   System.Xml.Xsl.Qil.QilNode
0x2681c  dup
0x2681d  ldc.i4.0
0x2681e  ldarg.1
0x2681f  stelem.ref
0x26820  dup
0x26821  ldc.i4.1
0x26822  ldarg.2
0x26823  stelem.ref
0x26824  dup
0x26825  ldc.i4.2
0x26826  ldarg.3
0x26827  stelem.ref
0x26828  dup
0x26829  ldc.i4.3
0x2682a  ldarg.s  4
0x2682c  stelem.ref
0x2682d  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::XsltInvokeEarlyBound(class System.Xml.Xsl.Qil.QilNode name, class [mscorlib]System.Reflection.MethodInfo d, class System.Xml.Xsl.XmlQueryType t, class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode> args)
0x26832  ret
```
