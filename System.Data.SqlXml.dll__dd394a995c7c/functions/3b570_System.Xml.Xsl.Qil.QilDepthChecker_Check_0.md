# System.Xml.Xsl.Qil.QilDepthChecker::Check_0

- ea: `0x3b570`
- end: `0x3b5d6`
- name: `System.Xml.Xsl.Qil.QilDepthChecker::Check_0`
- size: `102`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3b550`
- `0x3b570`

## callees

- `0x37740`
- `0x37750`
- `0x3b570`

## string_xrefs

- `0x3b578`: `Xslt_InputTooComplex`

## pseudocode

```c

```

## disassembly

```asm
0x3b570  ldarg.2
0x3b571  ldc.i4   0x320
0x3b576  ble.s    loc_3B589
0x3b578  ldstr    aXsltInputtooco// "Xslt_InputTooComplex"
0x3b57d  ldc.i4.0
0x3b57e  newarr   [mscorlib]System.String
0x3b583  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x3b588  throw
0x3b589  ldarg.1
0x3b58a  isinst   System.Xml.Xsl.Qil.QilReference
0x3b58f  brfalse.s loc_3B5AD
0x3b591  ldarg.0
0x3b592  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class System.Xml.Xsl.Qil.QilNode, bool> System.Xml.Xsl.Qil.QilDepthChecker::visitedRef
0x3b597  ldarg.1
0x3b598  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class System.Xml.Xsl.Qil.QilNode, bool>::ContainsKey(var<u1>)
0x3b59d  brfalse.s loc_3B5A0
0x3b59f  ret
0x3b5a0  ldarg.0
0x3b5a1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class System.Xml.Xsl.Qil.QilNode, bool> System.Xml.Xsl.Qil.QilDepthChecker::visitedRef
0x3b5a6  ldarg.1
0x3b5a7  ldc.i4.1
0x3b5a8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class System.Xml.Xsl.Qil.QilNode, bool>::set_Item(var<u1>, !!T0)
0x3b5ad  ldarg.2
0x3b5ae  ldc.i4.1
0x3b5af  add
0x3b5b0  stloc.0
0x3b5b1  ldc.i4.0
0x3b5b2  stloc.1
0x3b5b3  br.s     loc_3B5CC
0x3b5b5  ldarg.1
0x3b5b6  ldloc.1
0x3b5b7  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x3b5bc  stloc.2
0x3b5bd  ldloc.2
0x3b5be  brfalse.s loc_3B5C8
0x3b5c0  ldarg.0
0x3b5c1  ldloc.2
0x3b5c2  ldloc.0
0x3b5c3  call     instance void System.Xml.Xsl.Qil.QilDepthChecker::Check(class System.Xml.Xsl.Qil.QilNode input, int32 depth)
0x3b5c8  ldloc.1
0x3b5c9  ldc.i4.1
0x3b5ca  add
0x3b5cb  stloc.1
0x3b5cc  ldloc.1
0x3b5cd  ldarg.1
0x3b5ce  callvirt instance int32 System.Xml.Xsl.Qil.QilNode::get_Count()
0x3b5d3  blt.s    loc_3B5B5
0x3b5d5  ret
```
