# System.Xml.Xsl.Runtime.XsltConvert::EnsureNodeSet

- ea: `0x33ee0`
- end: `0x33f3a`
- name: `System.Xml.Xsl.Runtime.XsltConvert::EnsureNodeSet`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x3780`
- `0x2eaa0`
- `0x33ee0`

## string_xrefs

- `0x33ef9`: `XPath_NodeSetExpected`
- `0x33f1a`: `XPath_RtfInPathExpr`

## pseudocode

```c

```

## disassembly

```asm
0x33ee0  ldarg.0
0x33ee1  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [System.Xml]System.Xml.XPath.XPathItem>::get_Count()
0x33ee6  ldc.i4.1
0x33ee7  bne.un.s loc_33F33
0x33ee9  ldarg.0
0x33eea  ldc.i4.0
0x33eeb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class [System.Xml]System.Xml.XPath.XPathItem>::get_Item(!!T0)
0x33ef0  stloc.0
0x33ef1  ldloc.0
0x33ef2  callvirt instance bool [System.Xml]System.Xml.XPath.XPathItem::get_IsNode()
0x33ef7  brtrue.s loc_33F12
0x33ef9  ldstr    aXpathNodesetex// "XPath_NodeSetExpected"
0x33efe  ldc.i4.1
0x33eff  newarr   [mscorlib]System.String
0x33f04  dup
0x33f05  ldc.i4.0
0x33f06  ldsfld   string [mscorlib]System.String::Empty
0x33f0b  stelem.ref
0x33f0c  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string res, string[] args)
0x33f11  throw
0x33f12  ldloc.0
0x33f13  isinst   System.Xml.Xsl.Runtime.RtfNavigator
0x33f18  brfalse.s loc_33F33
0x33f1a  ldstr    aXpathRtfinpath// "XPath_RtfInPathExpr"
0x33f1f  ldc.i4.1
0x33f20  newarr   [mscorlib]System.String
0x33f25  dup
0x33f26  ldc.i4.0
0x33f27  ldsfld   string [mscorlib]System.String::Empty
0x33f2c  stelem.ref
0x33f2d  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string res, string[] args)
0x33f32  throw
0x33f33  ldarg.0
0x33f34  call     class [mscorlib]System.Collections.Generic.IList`1<class [System.Xml]System.Xml.XPath.XPathNavigator> System.Xml.Xsl.Runtime.XmlILStorageConverter::ItemsToNavigators(class [mscorlib]System.Collections.Generic.IList`1<class [System.Xml]System.Xml.XPath.XPathItem> listItems)
0x33f39  ret
```
