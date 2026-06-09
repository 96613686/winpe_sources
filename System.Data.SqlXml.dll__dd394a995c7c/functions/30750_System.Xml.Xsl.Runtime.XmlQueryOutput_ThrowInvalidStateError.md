# System.Xml.Xsl.Runtime.XmlQueryOutput::ThrowInvalidStateError

- ea: `0x30750`
- end: `0x30856`
- name: `System.Xml.Xsl.Runtime.XmlQueryOutput::ThrowInvalidStateError`
- size: `262`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x2fbe0`
- `0x30150`
- `0x30380`
- `0x303c0`

## callees

- `0x3780`
- `0x30430`
- `0x30750`

## string_xrefs

- `0x3077f`: `XmlIl_BadXmlState`
- `0x307c6`: `XmlIl_BadXmlState`
- `0x30820`: `XmlIl_BadXmlState`
- `0x30807`: `XmlIl_BadXmlStateAttr`

## pseudocode

```c

```

## disassembly

```asm
0x30750  ldarg.1
0x30751  switch   loc_3077F, loc_3077F, loc_307BD, loc_307BD, loc_3077F, loc_30820, loc_30820, loc_3077F, loc_3077F
0x3077a  br       loc_30820
0x3077f  ldstr    aXmlilBadxmlsta// "XmlIl_BadXmlState"
0x30784  ldc.i4.2
0x30785  newarr   [mscorlib]System.String
0x3078a  dup
0x3078b  ldc.i4.0
0x3078c  ldarga.s 1
0x3078e  constrained. [System.Xml]System.Xml.XPath.XPathNodeType
0x30794  callvirt instance string [mscorlib]System.Object::ToString()
0x30799  stelem.ref
0x3079a  dup
0x3079b  ldc.i4.1
0x3079c  ldarg.0
0x3079d  ldarg.0
0x3079e  ldfld    valuetype System.Xml.Xsl.Runtime.XmlState System.Xml.Xsl.Runtime.XmlQueryOutput::xstate
0x307a3  call     instance valuetype [System.Xml]System.Xml.XPath.XPathNodeType System.Xml.Xsl.Runtime.XmlQueryOutput::XmlStateToNodeType(valuetype System.Xml.Xsl.Runtime.XmlState xstate)
0x307a8  stloc.0
0x307a9  ldloca.s 0
0x307ab  constrained. [System.Xml]System.Xml.XPath.XPathNodeType
0x307b1  callvirt instance string [mscorlib]System.Object::ToString()
0x307b6  stelem.ref
0x307b7  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string res, string[] args)
0x307bc  throw
0x307bd  ldarg.0
0x307be  ldfld    int32 System.Xml.Xsl.Runtime.XmlQueryOutput::depth
0x307c3  ldc.i4.1
0x307c4  bne.un.s loc_307FB
0x307c6  ldstr    aXmlilBadxmlsta// "XmlIl_BadXmlState"
0x307cb  ldc.i4.2
0x307cc  newarr   [mscorlib]System.String
0x307d1  dup
0x307d2  ldc.i4.0
0x307d3  ldarga.s 1
0x307d5  constrained. [System.Xml]System.Xml.XPath.XPathNodeType
0x307db  callvirt instance string [mscorlib]System.Object::ToString()
0x307e0  stelem.ref
0x307e1  dup
0x307e2  ldc.i4.1
0x307e3  ldarg.0
0x307e4  ldflda   valuetype [System.Xml]System.Xml.XPath.XPathNodeType System.Xml.Xsl.Runtime.XmlQueryOutput::rootType
0x307e9  constrained. [System.Xml]System.Xml.XPath.XPathNodeType
0x307ef  callvirt instance string [mscorlib]System.Object::ToString()
0x307f4  stelem.ref
0x307f5  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string res, string[] args)
0x307fa  throw
0x307fb  ldarg.0
0x307fc  ldfld    valuetype System.Xml.Xsl.Runtime.XmlState System.Xml.Xsl.Runtime.XmlQueryOutput::xstate
0x30801  ldc.i4.2
0x30802  bne.un   loc_3077F
0x30807  ldstr    aXmlilBadxmlsta_0// "XmlIl_BadXmlStateAttr"
0x3080c  ldc.i4.1
0x3080d  newarr   [mscorlib]System.String
0x30812  dup
0x30813  ldc.i4.0
0x30814  ldsfld   string [mscorlib]System.String::Empty
0x30819  stelem.ref
0x3081a  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string res, string[] args)
0x3081f  throw
0x30820  ldstr    aXmlilBadxmlsta// "XmlIl_BadXmlState"
0x30825  ldc.i4.2
0x30826  newarr   [mscorlib]System.String
0x3082b  dup
0x3082c  ldc.i4.0
0x3082d  ldstr    aUnknown// "Unknown"
0x30832  stelem.ref
0x30833  dup
0x30834  ldc.i4.1
0x30835  ldarg.0
0x30836  ldarg.0
0x30837  ldfld    valuetype System.Xml.Xsl.Runtime.XmlState System.Xml.Xsl.Runtime.XmlQueryOutput::xstate
0x3083c  call     instance valuetype [System.Xml]System.Xml.XPath.XPathNodeType System.Xml.Xsl.Runtime.XmlQueryOutput::XmlStateToNodeType(valuetype System.Xml.Xsl.Runtime.XmlState xstate)
0x30841  stloc.0
0x30842  ldloca.s 0
0x30844  constrained. [System.Xml]System.Xml.XPath.XPathNodeType
0x3084a  callvirt instance string [mscorlib]System.Object::ToString()
0x3084f  stelem.ref
0x30850  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string res, string[] args)
0x30855  throw
```
