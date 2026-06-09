# System.Xml.Xsl.Xslt.XPathPatternBuilder::BuildPredicates

- ea: `0x1d0b0`
- end: `0x1d2e6`
- name: `System.Xml.Xsl.Xslt.XPathPatternBuilder::BuildPredicates`
- size: `566`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config`

## callers

- `0x1d8f0`

## callees

- `0x1d0b0`
- `0x1d400`
- `0x27ac0`
- `0x27b40`
- `0x37110`
- `0x37430`
- `0x37450`
- `0x37460`
- `0x376c0`
- `0x37720`
- `0x37a00`
- `0x37c40`
- `0x37ce0`
- `0x37d80`
- `0x380f0`
- `0x38120`
- `0x38150`
- `0x38200`
- `0x38210`
- `0x383b0`
- `0x383c0`
- `0x56e40`

## pseudocode

```c

```

## disassembly

```asm
0x1d0b0  ldarg.2
0x1d0b1  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Qil.QilNode>::get_Count()
0x1d0b6  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Qil.QilNode>::.ctor(int32)
0x1d0bb  stloc.0
0x1d0bc  ldarg.2
0x1d0bd  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Qil.QilNode>::GetEnumerator()
0x1d0c2  stloc.3
0x1d0c3  br.s     loc_1D0E7
0x1d0c5  ldloca.s 3
0x1d0c7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xml.Xsl.Qil.QilNode>::get_Current()
0x1d0cc  stloc.s  4
0x1d0ce  ldloc.0
0x1d0cf  ldloc.s  4
0x1d0d1  ldarg.0
0x1d0d2  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.Xslt.XPathPatternBuilder::f
0x1d0d7  ldarg.0
0x1d0d8  ldfld    class XPathPredicateEnvironment System.Xml.Xsl.Xslt.XPathPatternBuilder::predicateEnvironment
0x1d0dd  call     class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathBuilder::PredicateToBoolean(class System.Xml.Xsl.Qil.QilNode predicate, class System.Xml.Xsl.XPath.XPathQilFactory f, class System.Xml.Xsl.XPath.IXPathEnvironment env)
0x1d0e2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Qil.QilNode>::Add(var<u1>)
0x1d0e7  ldloca.s 3
0x1d0e9  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xml.Xsl.Qil.QilNode>::MoveNext()
0x1d0ee  brtrue.s loc_1D0C5
0x1d0f0  leave.s  loc_1D100
0x1d0f2  ldloca.s 3
0x1d0f4  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xml.Xsl.Qil.QilNode>
0x1d0fa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d0ff  endfinally
0x1d100  ldarg.1
0x1d101  castclass System.Xml.Xsl.Qil.QilLoop
0x1d106  stloc.1
0x1d107  ldloc.1
0x1d108  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilLoop::get_Variable()
0x1d10d  stloc.2
0x1d10e  ldarg.0
0x1d10f  ldfld    class XPathPredicateEnvironment System.Xml.Xsl.Xslt.XPathPatternBuilder::predicateEnvironment
0x1d114  ldfld    int32 XPathPredicateEnvironment::numFixupLast
0x1d119  brtrue.s loc_1D190
0x1d11b  ldarg.0
0x1d11c  ldfld    class XPathPredicateEnvironment System.Xml.Xsl.Xslt.XPathPatternBuilder::predicateEnvironment
0x1d121  ldfld    int32 XPathPredicateEnvironment::numFixupPosition
0x1d126  brtrue.s loc_1D190
0x1d128  ldloc.0
0x1d129  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Qil.QilNode>::GetEnumerator()
0x1d12e  stloc.s  5
0x1d130  br.s     loc_1D154
0x1d132  ldloca.s 5
0x1d134  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xml.Xsl.Qil.QilNode>::get_Current()
0x1d139  stloc.s  6
0x1d13b  ldloc.1
0x1d13c  ldarg.0
0x1d13d  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.Xslt.XPathPatternBuilder::f
0x1d142  ldloc.1
0x1d143  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilLoop::get_Body()
0x1d148  ldloc.s  6
0x1d14a  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::And(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x1d14f  callvirt instance void System.Xml.Xsl.Qil.QilLoop::set_Body(class System.Xml.Xsl.Qil.QilNode value)
0x1d154  ldloca.s 5
0x1d156  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xml.Xsl.Qil.QilNode>::MoveNext()
0x1d15b  brtrue.s loc_1D132
0x1d15d  leave.s  loc_1D16D
0x1d15f  ldloca.s 5
0x1d161  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xml.Xsl.Qil.QilNode>
0x1d167  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d16c  endfinally
0x1d16d  ldloc.1
0x1d16e  ldarg.0
0x1d16f  ldfld    class XPathPredicateEnvironment System.Xml.Xsl.Xslt.XPathPatternBuilder::predicateEnvironment
0x1d174  ldfld    class FixupVisitor XPathPredicateEnvironment::fixupVisitor
0x1d179  ldloc.1
0x1d17a  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilLoop::get_Body()
0x1d17f  ldloc.2
0x1d180  ldnull
0x1d181  callvirt instance class System.Xml.Xsl.Qil.QilNode FixupVisitor::Fixup(class System.Xml.Xsl.Qil.QilNode inExpr, class System.Xml.Xsl.Qil.QilIterator current, class System.Xml.Xsl.Qil.QilNode last)
0x1d186  callvirt instance void System.Xml.Xsl.Qil.QilLoop::set_Body(class System.Xml.Xsl.Qil.QilNode value)
0x1d18b  br       loc_1D2D5
0x1d190  ldarg.0
0x1d191  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.Xslt.XPathPatternBuilder::f
0x1d196  ldarg.0
0x1d197  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.Xslt.XPathPatternBuilder::f
0x1d19c  ldloc.2
0x1d19d  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Parent(class System.Xml.Xsl.Qil.QilNode context)
0x1d1a2  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilPatternFactory::For(class System.Xml.Xsl.Qil.QilNode binding)
0x1d1a7  stloc.s  7
0x1d1a9  ldarg.0
0x1d1aa  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.Xslt.XPathPatternBuilder::f
0x1d1af  ldloc.s  7
0x1d1b1  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Content(class System.Xml.Xsl.Qil.QilNode context)
0x1d1b6  stloc.s  8
0x1d1b8  ldarg.1
0x1d1b9  ldarg.0
0x1d1ba  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.Xslt.XPathPatternBuilder::f
0x1d1bf  callvirt instance class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilPatternFactory::get_BaseFactory()
0x1d1c4  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::DeepClone(class System.Xml.Xsl.Qil.QilFactory f)
0x1d1c9  castclass System.Xml.Xsl.Qil.QilLoop
0x1d1ce  stloc.s  9
0x1d1d0  ldloc.s  9
0x1d1d2  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilLoop::get_Variable()
0x1d1d7  ldloc.s  8
0x1d1d9  callvirt instance void System.Xml.Xsl.Qil.QilIterator::set_Binding(class System.Xml.Xsl.Qil.QilNode value)
0x1d1de  ldarg.0
0x1d1df  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.Xslt.XPathPatternBuilder::f
0x1d1e4  ldloc.s  7
0x1d1e6  ldloc.s  9
0x1d1e8  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Loop(class System.Xml.Xsl.Qil.QilIterator variable, class System.Xml.Xsl.Qil.QilNode body)
0x1d1ed  castclass System.Xml.Xsl.Qil.QilLoop
0x1d1f2  stloc.s  9
0x1d1f4  ldloc.s  9
0x1d1f6  stloc.s  0xA
0x1d1f8  ldloc.0
0x1d1f9  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Qil.QilNode>::GetEnumerator()
0x1d1fe  stloc.s  0xD
0x1d200  br.s     loc_1D249
0x1d202  ldloca.s 0xD
0x1d204  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xml.Xsl.Qil.QilNode>::get_Current()
0x1d209  stloc.s  0xE
0x1d20b  ldloc.s  0xA
0x1d20d  ldloc.s  0xE
0x1d20f  ldc.i4.0
0x1d210  ldarg.0
0x1d211  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.Xslt.XPathPatternBuilder::f
0x1d216  ldarg.0
0x1d217  ldfld    class XPathPredicateEnvironment System.Xml.Xsl.Xslt.XPathPatternBuilder::predicateEnvironment
0x1d21c  ldfld    class FixupVisitor XPathPredicateEnvironment::fixupVisitor
0x1d221  ldarg.0
0x1d222  ldfld    class XPathPredicateEnvironment System.Xml.Xsl.Xslt.XPathPatternBuilder::predicateEnvironment
0x1d227  ldflda   int32 XPathPredicateEnvironment::numFixupCurrent
0x1d22c  ldarg.0
0x1d22d  ldfld    class XPathPredicateEnvironment System.Xml.Xsl.Xslt.XPathPatternBuilder::predicateEnvironment
0x1d232  ldflda   int32 XPathPredicateEnvironment::numFixupPosition
0x1d237  ldarg.0
0x1d238  ldfld    class XPathPredicateEnvironment System.Xml.Xsl.Xslt.XPathPatternBuilder::predicateEnvironment
0x1d23d  ldflda   int32 XPathPredicateEnvironment::numFixupLast
0x1d242  call     class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.XPath.XPathBuilder::BuildOnePredicate(class System.Xml.Xsl.Qil.QilNode nodeset, class System.Xml.Xsl.Qil.QilNode predicate, bool isReverseStep, class System.Xml.Xsl.XPath.XPathQilFactory f, class FixupVisitor fixupVisitor, int32& numFixupCurrent, int32& numFixupPosition, int32& numFixupLast)
0x1d247  stloc.s  0xA
0x1d249  ldloca.s 0xD
0x1d24b  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xml.Xsl.Qil.QilNode>::MoveNext()
0x1d250  brtrue.s loc_1D202
0x1d252  leave.s  loc_1D262
0x1d254  ldloca.s 0xD
0x1d256  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xml.Xsl.Qil.QilNode>
0x1d25c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d261  endfinally
0x1d262  ldarg.0
0x1d263  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.Xslt.XPathPatternBuilder::f
0x1d268  ldloc.s  0xA
0x1d26a  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilPatternFactory::For(class System.Xml.Xsl.Qil.QilNode binding)
0x1d26f  stloc.s  0xB
0x1d271  ldarg.0
0x1d272  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.Xslt.XPathPatternBuilder::f
0x1d277  ldloc.s  0xB
0x1d279  ldarg.0
0x1d27a  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.Xslt.XPathPatternBuilder::f
0x1d27f  ldloc.s  0xB
0x1d281  ldloc.2
0x1d282  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Is(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x1d287  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Filter(class System.Xml.Xsl.Qil.QilIterator variable, class System.Xml.Xsl.Qil.QilNode expr)
0x1d28c  stloc.s  0xC
0x1d28e  ldloc.1
0x1d28f  ldarg.0
0x1d290  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.Xslt.XPathPatternBuilder::f
0x1d295  ldarg.0
0x1d296  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.Xslt.XPathPatternBuilder::f
0x1d29b  ldloc.s  0xC
0x1d29d  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::IsEmpty(class System.Xml.Xsl.Qil.QilNode set)
0x1d2a2  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Not(class System.Xml.Xsl.Qil.QilNode child)
0x1d2a7  callvirt instance void System.Xml.Xsl.Qil.QilLoop::set_Body(class System.Xml.Xsl.Qil.QilNode value)
0x1d2ac  ldloc.1
0x1d2ad  ldarg.0
0x1d2ae  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.Xslt.XPathPatternBuilder::f
0x1d2b3  ldarg.0
0x1d2b4  ldfld    class System.Xml.Xsl.XPath.XPathQilFactory System.Xml.Xsl.Xslt.XPathPatternBuilder::f
0x1d2b9  ldloc.2
0x1d2ba  ldloc.1
0x1d2bb  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x1d2c0  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::IsType(class System.Xml.Xsl.Qil.QilNode expr, class System.Xml.Xsl.XmlQueryType t)
0x1d2c5  ldloc.1
0x1d2c6  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilLoop::get_Body()
0x1d2cb  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::And(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x1d2d0  callvirt instance void System.Xml.Xsl.Qil.QilLoop::set_Body(class System.Xml.Xsl.Qil.QilNode value)
0x1d2d5  ldarg.1
0x1d2d6  ldc.r8   0.5
0x1d2df  call     void System.Xml.Xsl.Xslt.XPathPatternBuilder::SetPriority(class System.Xml.Xsl.Qil.QilNode node, float64 priority)
0x1d2e4  ldarg.1
0x1d2e5  ret
```
