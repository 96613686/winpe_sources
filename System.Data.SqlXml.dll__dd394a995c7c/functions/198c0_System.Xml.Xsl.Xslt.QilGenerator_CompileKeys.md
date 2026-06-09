# System.Xml.Xsl.Xslt.QilGenerator::CompileKeys

- ea: `0x198c0`
- end: `0x19a77`
- name: `System.Xml.Xsl.Xslt.QilGenerator::CompileKeys`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x16300`

## callees

- `0x144e0`
- `0x167e0`
- `0x16810`
- `0x198c0`
- `0x19f70`
- `0x19ff0`
- `0x1a750`
- `0x1df00`
- `0x297d0`
- `0x377c0`
- `0x37b80`
- `0x37bf0`
- `0x37c40`
- `0x37c60`
- `0x37ca0`
- `0x37d80`
- `0x380a0`
- `0x38120`
- `0x38150`
- `0x381d0`
- `0x383c0`
- `0x38ce0`

## pseudocode

```c

```

## disassembly

```asm
0x198c0  ldc.i4.0
0x198c1  stloc.0
0x198c2  br       loc_19A54
0x198c7  ldarg.0
0x198c8  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.QilGenerator::compiler
0x198cd  ldfld    class System.Xml.Xsl.Xslt.Keys System.Xml.Xsl.Xslt.Compiler::Keys
0x198d2  ldloc.0
0x198d3  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.Key>>::get_Item(!!T0)
0x198d8  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.Key>::GetEnumerator()
0x198dd  stloc.1
0x198de  br       loc_19A34
0x198e3  ldloca.s 1
0x198e5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xml.Xsl.Xslt.Key>::get_Current()
0x198ea  stloc.2
0x198eb  ldarg.0
0x198ec  ldloc.2
0x198ed  call     instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Xslt.QilGenerator::EnterScope(class System.Xml.Xsl.Xslt.XslNode node)
0x198f2  pop
0x198f3  ldarg.0
0x198f4  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x198f9  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::NodeNotRtf
0x198fe  callvirt instance class System.Xml.Xsl.Qil.QilParameter System.Xml.Xsl.Qil.QilPatternFactory::Parameter(class System.Xml.Xsl.XmlQueryType t)
0x19903  stloc.3
0x19904  ldarg.0
0x19905  ldflda   valuetype System.Xml.Xsl.Xslt.SingletonFocus System.Xml.Xsl.Xslt.QilGenerator::singlFocus
0x1990a  ldloc.3
0x1990b  call     instance void System.Xml.Xsl.Xslt.SingletonFocus::SetFocus(class System.Xml.Xsl.Qil.QilIterator current)
0x19910  ldarg.0
0x19911  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x19916  ldarg.0
0x19917  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1991c  ldarg.0
0x1991d  ldloc.2
0x1991e  ldfld    string System.Xml.Xsl.Xslt.Key::Match
0x19923  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileKeyMatch(string pttrn)
0x19928  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::OptimizeBarrier(class System.Xml.Xsl.Qil.QilNode child)
0x1992d  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilPatternFactory::For(class System.Xml.Xsl.Qil.QilNode binding)
0x19932  stloc.s  4
0x19934  ldarg.0
0x19935  ldflda   valuetype System.Xml.Xsl.Xslt.SingletonFocus System.Xml.Xsl.Xslt.QilGenerator::singlFocus
0x1993a  ldloc.s  4
0x1993c  call     instance void System.Xml.Xsl.Xslt.SingletonFocus::SetFocus(class System.Xml.Xsl.Qil.QilIterator current)
0x19941  ldarg.0
0x19942  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x19947  ldarg.0
0x19948  ldloc.2
0x19949  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileKeyUse(class System.Xml.Xsl.Xslt.Key key)
0x1994e  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilPatternFactory::For(class System.Xml.Xsl.Qil.QilNode binding)
0x19953  stloc.s  5
0x19955  ldarg.0
0x19956  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1995b  ldarg.0
0x1995c  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x19961  ldarg.0
0x19962  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x19967  ldloc.s  5
0x19969  ldarg.0
0x1996a  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1996f  ldloc.s  5
0x19971  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathQilFactory::ConvertToString(class System.Xml.Xsl.Qil.QilNode n)
0x19976  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Loop(class System.Xml.Xsl.Qil.QilIterator variable, class System.Xml.Xsl.Qil.QilNode body)
0x1997b  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::OptimizeBarrier(class System.Xml.Xsl.Qil.QilNode child)
0x19980  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilPatternFactory::For(class System.Xml.Xsl.Qil.QilNode binding)
0x19985  stloc.s  5
0x19987  ldarg.0
0x19988  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1998d  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::StringX
0x19992  callvirt instance class System.Xml.Xsl.Qil.QilParameter System.Xml.Xsl.Qil.QilPatternFactory::Parameter(class System.Xml.Xsl.XmlQueryType t)
0x19997  stloc.s  6
0x19999  ldarg.0
0x1999a  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1999f  ldarg.0
0x199a0  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x199a5  ldloc.3
0x199a6  ldloc.s  6
0x199a8  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilPatternFactory::FormalParameterList(class System.Xml.Xsl.Qil.QilNode arg1, class System.Xml.Xsl.Qil.QilNode arg2)
0x199ad  ldarg.0
0x199ae  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x199b3  ldloc.s  4
0x199b5  ldarg.0
0x199b6  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x199bb  ldarg.0
0x199bc  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x199c1  ldarg.0
0x199c2  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x199c7  ldloc.s  5
0x199c9  ldarg.0
0x199ca  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x199cf  ldloc.s  5
0x199d1  ldloc.s  6
0x199d3  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Eq(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x199d8  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Filter(class System.Xml.Xsl.Qil.QilIterator variable, class System.Xml.Xsl.Qil.QilNode expr)
0x199dd  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::IsEmpty(class System.Xml.Xsl.Qil.QilNode set)
0x199e2  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Not(class System.Xml.Xsl.Qil.QilNode child)
0x199e7  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Filter(class System.Xml.Xsl.Qil.QilIterator variable, class System.Xml.Xsl.Qil.QilNode expr)
0x199ec  ldarg.0
0x199ed  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x199f2  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::False()
0x199f7  callvirt instance class System.Xml.Xsl.Qil.QilFunction System.Xml.Xsl.Qil.QilPatternFactory::Function(class System.Xml.Xsl.Qil.QilList args, class System.Xml.Xsl.Qil.QilNode defn, class System.Xml.Xsl.Qil.QilNode sideEffects)
0x199fc  stloc.s  7
0x199fe  ldloc.s  7
0x19a00  ldloc.2
0x19a01  callvirt instance string System.Xml.Xsl.Xslt.Key::GetDebugName()
0x19a06  callvirt instance void System.Xml.Xsl.Qil.QilReference::set_DebugName(string value)
0x19a0b  ldloc.s  7
0x19a0d  ldloc.2
0x19a0e  ldfld    class System.Xml.Xsl.ISourceLineInfo System.Xml.Xsl.Xslt.XslNode::SourceLine
0x19a13  call     class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::SetLineInfo(class System.Xml.Xsl.Qil.QilNode n, class System.Xml.Xsl.ISourceLineInfo lineInfo)
0x19a18  pop
0x19a19  ldloc.2
0x19a1a  ldloc.s  7
0x19a1c  stfld    class System.Xml.Xsl.Qil.QilFunction System.Xml.Xsl.Xslt.Key::Function
0x19a21  ldarg.0
0x19a22  ldfld    class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Xslt.QilGenerator::functions
0x19a27  ldloc.s  7
0x19a29  callvirt instance void System.Xml.Xsl.Qil.QilNode::Add(class System.Xml.Xsl.Qil.QilNode node)
0x19a2e  ldarg.0
0x19a2f  call     instance void System.Xml.Xsl.Xslt.QilGenerator::ExitScope()
0x19a34  ldloca.s 1
0x19a36  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xml.Xsl.Xslt.Key>::MoveNext()
0x19a3b  brtrue   loc_198E3
0x19a40  leave.s  loc_19A50
0x19a42  ldloca.s 1
0x19a44  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xml.Xsl.Xslt.Key>
0x19a4a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19a4f  endfinally
0x19a50  ldloc.0
0x19a51  ldc.i4.1
0x19a52  add
0x19a53  stloc.0
0x19a54  ldloc.0
0x19a55  ldarg.0
0x19a56  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.QilGenerator::compiler
0x19a5b  ldfld    class System.Xml.Xsl.Xslt.Keys System.Xml.Xsl.Xslt.Compiler::Keys
0x19a60  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Xslt.Key>>::get_Count()
0x19a65  blt      loc_198C7
0x19a6a  ldarg.0
0x19a6b  ldflda   valuetype System.Xml.Xsl.Xslt.SingletonFocus System.Xml.Xsl.Xslt.QilGenerator::singlFocus
0x19a70  ldnull
0x19a71  call     instance void System.Xml.Xsl.Xslt.SingletonFocus::SetFocus(class System.Xml.Xsl.Qil.QilIterator current)
0x19a76  ret
```
