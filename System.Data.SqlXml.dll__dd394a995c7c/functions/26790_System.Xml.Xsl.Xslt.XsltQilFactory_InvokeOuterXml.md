# System.Xml.Xsl.Xslt.XsltQilFactory::InvokeOuterXml

- ea: `0x26790`
- end: `0x267b6`
- name: `System.Xml.Xsl.Xslt.XsltQilFactory::InvokeOuterXml`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18510`

## callees

- `0x37a80`
- `0x38420`

## string_xrefs

- `0x26792`: `outer-xml`

## pseudocode

```c

```

## disassembly

```asm
0x26790  ldarg.0
0x26791  ldarg.0
0x26792  ldstr    aOuterXml// "outer-xml"
0x26797  call     instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilPatternFactory::QName(string local)
0x2679c  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XsltMethods::OuterXml
0x267a1  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::StringX
0x267a6  ldc.i4.1
0x267a7  newarr   System.Xml.Xsl.Qil.QilNode
0x267ac  dup
0x267ad  ldc.i4.0
0x267ae  ldarg.1
0x267af  stelem.ref
0x267b0  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::XsltInvokeEarlyBound(class System.Xml.Xsl.Qil.QilNode name, class [mscorlib]System.Reflection.MethodInfo d, class System.Xml.Xsl.XmlQueryType t, class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode> args)
0x267b5  ret
```
