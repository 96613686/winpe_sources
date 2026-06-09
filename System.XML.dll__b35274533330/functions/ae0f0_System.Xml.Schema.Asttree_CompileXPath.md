# System.Xml.Schema.Asttree::CompileXPath

- ea: `0xae0f0`
- end: `0xae343`
- name: `System.Xml.Schema.Asttree::CompileXPath`
- size: `595`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0xae040`

## callees

- `0x3d0`
- `0x3e0`
- `0x7200`
- `0xadf40`
- `0xadfc0`
- `0xae070`
- `0xae090`
- `0xae0b0`
- `0xae0d0`
- `0xae0f0`
- `0xae350`
- `0xd2fb0`

## string_xrefs

- `0xae0fb`: `Sch_EmptyXPath`
- `0xae15d`: `Sch_ICXpathError`
- `0xae186`: `Sch_ICXpathError`
- `0xae1c3`: `Sch_ICXpathError`
- `0xae20e`: `Sch_ICXpathError`
- `0xae298`: `Sch_ICXpathError`
- `0xae2b4`: `Sch_ICXpathError`
- `0xae2d3`: `Sch_ICXpathError`

## pseudocode

```c

```

## disassembly

```asm
0xae0f0  ldarg.1
0xae0f1  brfalse.s loc_AE0FB
0xae0f3  ldarg.1
0xae0f4  callvirt instance int32 [mscorlib]System.String::get_Length()
0xae0f9  brtrue.s loc_AE10B
0xae0fb  ldstr    aSchEmptyxpath// "Sch_EmptyXPath"
0xae100  ldsfld   string [mscorlib]System.String::Empty
0xae105  newobj   instance void System.Xml.Schema.XmlSchemaException::.ctor(string res, string arg)
0xae10a  throw
0xae10b  ldarg.1
0xae10c  ldc.i4.1
0xae10d  newarr   [mscorlib]System.Char
0xae112  dup
0xae113  ldc.i4.0
0xae114  ldc.i4.s 0x7C
0xae116  stelem.i2
0xae117  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xae11c  stloc.0
0xae11d  ldloc.0
0xae11e  ldlen
0xae11f  conv.i4
0xae120  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor(int32)
0xae125  stloc.1
0xae126  ldarg.0
0xae127  ldloc.0
0xae128  ldlen
0xae129  conv.i4
0xae12a  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor(int32)
0xae12f  stfld    class [mscorlib]System.Collections.ArrayList System.Xml.Schema.Asttree::fAxisArray
0xae134  ldc.i4.0
0xae135  stloc.3
0xae136  br.s     loc_AE154
0xae138  ldloc.0
0xae139  ldloc.3
0xae13a  ldelem.ref
0xae13b  call     class MS.Internal.Xml.XPath.AstNode MS.Internal.Xml.XPath.XPathParser::ParseXPathExpresion(string xpathExpresion)
0xae140  castclass MS.Internal.Xml.XPath.Axis
0xae145  stloc.s  4
0xae147  ldloc.1
0xae148  ldloc.s  4
0xae14a  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xae14f  pop
0xae150  ldloc.3
0xae151  ldc.i4.1
0xae152  add
0xae153  stloc.3
0xae154  ldloc.3
0xae155  ldloc.0
0xae156  ldlen
0xae157  conv.i4
0xae158  blt.s    loc_AE138
0xae15a  leave.s  loc_AE169
0xae15c  pop
0xae15d  ldstr    aSchIcxpatherro// "Sch_ICXpathError"
0xae162  ldarg.1
0xae163  newobj   instance void System.Xml.Schema.XmlSchemaException::.ctor(string res, string arg)
0xae168  throw
0xae169  ldc.i4.0
0xae16a  stloc.s  5
0xae16c  br       loc_AE335
0xae171  ldloc.1
0xae172  ldloc.s  5
0xae174  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xae179  castclass MS.Internal.Xml.XPath.Axis
0xae17e  stloc.s  6
0xae180  ldloc.s  6
0xae182  dup
0xae183  stloc.2
0xae184  brtrue.s loc_AE192
0xae186  ldstr    aSchIcxpatherro// "Sch_ICXpathError"
0xae18b  ldarg.1
0xae18c  newobj   instance void System.Xml.Schema.XmlSchemaException::.ctor(string res, string arg)
0xae191  throw
0xae192  ldloc.2
0xae193  stloc.s  7
0xae195  ldloc.2
0xae196  call     bool System.Xml.Schema.Asttree::IsAttribute(class MS.Internal.Xml.XPath.Axis ast)
0xae19b  brfalse.s loc_AE21A
0xae19d  ldarg.2
0xae19e  brtrue.s loc_AE1AC
0xae1a0  ldstr    aSchSelectoratt// "Sch_SelectorAttr"
0xae1a5  ldarg.1
0xae1a6  newobj   instance void System.Xml.Schema.XmlSchemaException::.ctor(string res, string arg)
0xae1ab  throw
0xae1ac  ldarg.0
0xae1ad  ldloc.2
0xae1ae  ldarg.3
0xae1af  call     instance void System.Xml.Schema.Asttree::SetURN(class MS.Internal.Xml.XPath.Axis axis, class System.Xml.XmlNamespaceManager nsmgr)
0xae1b4  ldloc.2
0xae1b5  callvirt instance class MS.Internal.Xml.XPath.AstNode MS.Internal.Xml.XPath.Axis::get_Input()
0xae1ba  castclass MS.Internal.Xml.XPath.Axis
0xae1bf  stloc.2
0xae1c0  leave.s  loc_AE21A
0xae1c2  pop
0xae1c3  ldstr    aSchIcxpatherro// "Sch_ICXpathError"
0xae1c8  ldarg.1
0xae1c9  newobj   instance void System.Xml.Schema.XmlSchemaException::.ctor(string res, string arg)
0xae1ce  throw
0xae1cf  ldloc.2
0xae1d0  call     bool System.Xml.Schema.Asttree::IsSelf(class MS.Internal.Xml.XPath.Axis ast)
0xae1d5  brfalse.s loc_AE1EB
0xae1d7  ldloc.s  6
0xae1d9  ldloc.2
0xae1da  beq.s    loc_AE1EB
0xae1dc  ldloc.s  7
0xae1de  ldloc.2
0xae1df  callvirt instance class MS.Internal.Xml.XPath.AstNode MS.Internal.Xml.XPath.Axis::get_Input()
0xae1e4  callvirt instance void MS.Internal.Xml.XPath.Axis::set_Input(class MS.Internal.Xml.XPath.AstNode value)
0xae1e9  br.s     loc_AE1FE
0xae1eb  ldloc.2
0xae1ec  stloc.s  7
0xae1ee  ldloc.2
0xae1ef  call     bool System.Xml.Schema.Asttree::IsNameTest(class MS.Internal.Xml.XPath.Axis ast)
0xae1f4  brfalse.s loc_AE1FE
0xae1f6  ldarg.0
0xae1f7  ldloc.2
0xae1f8  ldarg.3
0xae1f9  call     instance void System.Xml.Schema.Asttree::SetURN(class MS.Internal.Xml.XPath.Axis axis, class System.Xml.XmlNamespaceManager nsmgr)
0xae1fe  nop
0xae1ff  ldloc.2
0xae200  callvirt instance class MS.Internal.Xml.XPath.AstNode MS.Internal.Xml.XPath.Axis::get_Input()
0xae205  castclass MS.Internal.Xml.XPath.Axis
0xae20a  stloc.2
0xae20b  leave.s  loc_AE21A
0xae20d  pop
0xae20e  ldstr    aSchIcxpatherro// "Sch_ICXpathError"
0xae213  ldarg.1
0xae214  newobj   instance void System.Xml.Schema.XmlSchemaException::.ctor(string res, string arg)
0xae219  throw
0xae21a  ldloc.2
0xae21b  brfalse.s loc_AE22D
0xae21d  ldloc.2
0xae21e  call     bool System.Xml.Schema.Asttree::IsNameTest(class MS.Internal.Xml.XPath.Axis ast)
0xae223  brtrue.s loc_AE1CF
0xae225  ldloc.2
0xae226  call     bool System.Xml.Schema.Asttree::IsSelf(class MS.Internal.Xml.XPath.Axis ast)
0xae22b  brtrue.s loc_AE1CF
0xae22d  ldloc.s  7
0xae22f  ldnull
0xae230  callvirt instance void MS.Internal.Xml.XPath.Axis::set_Input(class MS.Internal.Xml.XPath.AstNode value)
0xae235  ldloc.2
0xae236  brtrue.s loc_AE290
0xae238  ldloc.s  6
0xae23a  call     bool System.Xml.Schema.Asttree::IsSelf(class MS.Internal.Xml.XPath.Axis ast)
0xae23f  brfalse.s loc_AE272
0xae241  ldloc.s  6
0xae243  callvirt instance class MS.Internal.Xml.XPath.AstNode MS.Internal.Xml.XPath.Axis::get_Input()
0xae248  brfalse.s loc_AE272
0xae24a  ldarg.0
0xae24b  ldfld    class [mscorlib]System.Collections.ArrayList System.Xml.Schema.Asttree::fAxisArray
0xae250  ldloc.s  6
0xae252  callvirt instance class MS.Internal.Xml.XPath.AstNode MS.Internal.Xml.XPath.Axis::get_Input()
0xae257  castclass MS.Internal.Xml.XPath.Axis
0xae25c  call     class System.Xml.Schema.DoubleLinkAxis System.Xml.Schema.DoubleLinkAxis::ConvertTree(class MS.Internal.Xml.XPath.Axis axis)
0xae261  ldc.i4.0
0xae262  newobj   instance void System.Xml.Schema.ForwardAxis::.ctor(class System.Xml.Schema.DoubleLinkAxis axis, bool isdesorself)
0xae267  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xae26c  pop
0xae26d  br       loc_AE32F
0xae272  ldarg.0
0xae273  ldfld    class [mscorlib]System.Collections.ArrayList System.Xml.Schema.Asttree::fAxisArray
0xae278  ldloc.s  6
0xae27a  call     class System.Xml.Schema.DoubleLinkAxis System.Xml.Schema.DoubleLinkAxis::ConvertTree(class MS.Internal.Xml.XPath.Axis axis)
0xae27f  ldc.i4.0
0xae280  newobj   instance void System.Xml.Schema.ForwardAxis::.ctor(class System.Xml.Schema.DoubleLinkAxis axis, bool isdesorself)
0xae285  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xae28a  pop
0xae28b  br       loc_AE32F
0xae290  ldloc.2
0xae291  call     bool System.Xml.Schema.Asttree::IsDescendantOrSelf(class MS.Internal.Xml.XPath.Axis ast)
0xae296  brtrue.s loc_AE2A4
0xae298  ldstr    aSchIcxpatherro// "Sch_ICXpathError"
0xae29d  ldarg.1
0xae29e  newobj   instance void System.Xml.Schema.XmlSchemaException::.ctor(string res, string arg)
0xae2a3  throw
0xae2a4  nop
0xae2a5  ldloc.2
0xae2a6  callvirt instance class MS.Internal.Xml.XPath.AstNode MS.Internal.Xml.XPath.Axis::get_Input()
0xae2ab  castclass MS.Internal.Xml.XPath.Axis
0xae2b0  stloc.2
0xae2b1  leave.s  loc_AE2C0
0xae2b3  pop
0xae2b4  ldstr    aSchIcxpatherro// "Sch_ICXpathError"
0xae2b9  ldarg.1
0xae2ba  newobj   instance void System.Xml.Schema.XmlSchemaException::.ctor(string res, string arg)
0xae2bf  throw
0xae2c0  ldloc.2
0xae2c1  brfalse.s loc_AE2D3
0xae2c3  ldloc.2
0xae2c4  call     bool System.Xml.Schema.Asttree::IsSelf(class MS.Internal.Xml.XPath.Axis ast)
0xae2c9  brfalse.s loc_AE2D3
0xae2cb  ldloc.2
0xae2cc  callvirt instance class MS.Internal.Xml.XPath.AstNode MS.Internal.Xml.XPath.Axis::get_Input()
0xae2d1  brfalse.s loc_AE2DF
0xae2d3  ldstr    aSchIcxpatherro// "Sch_ICXpathError"
0xae2d8  ldarg.1
0xae2d9  newobj   instance void System.Xml.Schema.XmlSchemaException::.ctor(string res, string arg)
0xae2de  throw
0xae2df  ldloc.s  6
0xae2e1  call     bool System.Xml.Schema.Asttree::IsSelf(class MS.Internal.Xml.XPath.Axis ast)
0xae2e6  brfalse.s loc_AE316
0xae2e8  ldloc.s  6
0xae2ea  callvirt instance class MS.Internal.Xml.XPath.AstNode MS.Internal.Xml.XPath.Axis::get_Input()
0xae2ef  brfalse.s loc_AE316
0xae2f1  ldarg.0
0xae2f2  ldfld    class [mscorlib]System.Collections.ArrayList System.Xml.Schema.Asttree::fAxisArray
0xae2f7  ldloc.s  6
0xae2f9  callvirt instance class MS.Internal.Xml.XPath.AstNode MS.Internal.Xml.XPath.Axis::get_Input()
0xae2fe  castclass MS.Internal.Xml.XPath.Axis
0xae303  call     class System.Xml.Schema.DoubleLinkAxis System.Xml.Schema.DoubleLinkAxis::ConvertTree(class MS.Internal.Xml.XPath.Axis axis)
0xae308  ldc.i4.1
0xae309  newobj   instance void System.Xml.Schema.ForwardAxis::.ctor(class System.Xml.Schema.DoubleLinkAxis axis, bool isdesorself)
0xae30e  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xae313  pop
0xae314  br.s     loc_AE32F
0xae316  ldarg.0
0xae317  ldfld    class [mscorlib]System.Collections.ArrayList System.Xml.Schema.Asttree::fAxisArray
0xae31c  ldloc.s  6
0xae31e  call     class System.Xml.Schema.DoubleLinkAxis System.Xml.Schema.DoubleLinkAxis::ConvertTree(class MS.Internal.Xml.XPath.Axis axis)
0xae323  ldc.i4.1
0xae324  newobj   instance void System.Xml.Schema.ForwardAxis::.ctor(class System.Xml.Schema.DoubleLinkAxis axis, bool isdesorself)
0xae329  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xae32e  pop
0xae32f  ldloc.s  5
0xae331  ldc.i4.1
0xae332  add
0xae333  stloc.s  5
0xae335  ldloc.s  5
0xae337  ldloc.1
0xae338  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xae33d  blt      loc_AE171
0xae342  ret
```
