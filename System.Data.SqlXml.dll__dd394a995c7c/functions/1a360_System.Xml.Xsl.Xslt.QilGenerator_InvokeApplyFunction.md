# System.Xml.Xsl.Xslt.QilGenerator::InvokeApplyFunction

- ea: `0x1a360`
- end: `0x1a673`
- name: `System.Xml.Xsl.Xslt.QilGenerator::InvokeApplyFunction`
- size: `787`
- prototype: ``
- caller_count: `2`
- callee_count: `38`
- tags: `registry_config`

## callers

- `0x1a160`
- `0x1a360`

## callees

- `0x146d0`
- `0x147f0`
- `0x15980`
- `0x15c80`
- `0x162d0`
- `0x165a0`
- `0x1a1f0`
- `0x1a290`
- `0x1a360`
- `0x1a870`
- `0x36450`
- `0x36ec0`
- `0x36ef0`
- `0x374b0`
- `0x37510`
- `0x376c0`
- `0x376d0`
- `0x37750`
- `0x377c0`
- `0x37800`
- `0x379c0`
- `0x37a00`
- `0x37af0`
- `0x37b50`
- `0x37c40`
- `0x37c60`
- `0x37cb0`
- `0x37de0`
- `0x37ec0`
- `0x37ef0`
- `0x38150`
- `0x381c0`
- `0x381f0`
- `0x38200`
- `0x38310`
- `0x383b0`
- `0x383d0`
- `0x38ce0`

## string_xrefs

- `0x1a4f2`: `<xsl:apply-templates`

## pseudocode

```c

```

## disassembly

```asm
0x1a360  ldarg.1
0x1a361  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class System.Xml.Xsl.Qil.QilName, valuetype System.Xml.Xsl.XslFlags> System.Xml.Xsl.Xslt.StylesheetLevel::ModeFlags
0x1a366  ldarg.2
0x1a367  ldloca.s 0
0x1a369  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class System.Xml.Xsl.Qil.QilName, valuetype System.Xml.Xsl.XslFlags>::TryGetValue(var<u1>, !!T0)
0x1a36e  brtrue.s loc_1A372
0x1a370  ldc.i4.0
0x1a371  stloc.0
0x1a372  ldloc.0
0x1a373  ldc.i4   0x100
0x1a378  or
0x1a379  stloc.0
0x1a37a  ldarg.0
0x1a37b  ldarg.3
0x1a37c  ldloc.0
0x1a37d  call     instance class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Xslt.XslNode> System.Xml.Xsl.Xslt.QilGenerator::AddRemoveImplicitArgs(class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Xslt.XslNode> args, valuetype System.Xml.Xsl.XslFlags flags)
0x1a382  starg.s  3
0x1a384  ldarg.0
0x1a385  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1a38a  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilPatternFactory::ActualParameterList()
0x1a38f  stloc.1
0x1a390  ldnull
0x1a391  stloc.2
0x1a392  ldarg.1
0x1a393  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class System.Xml.Xsl.Qil.QilName, class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Qil.QilFunction>> System.Xml.Xsl.Xslt.StylesheetLevel::ApplyFunctions
0x1a398  ldarg.2
0x1a399  ldloca.s 3
0x1a39b  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class System.Xml.Xsl.Qil.QilName, class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Qil.QilFunction>>::TryGetValue(var<u1>, !!T0)
0x1a3a0  brtrue.s loc_1A3B9
0x1a3a2  ldarg.1
0x1a3a3  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class System.Xml.Xsl.Qil.QilName, class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Qil.QilFunction>> System.Xml.Xsl.Xslt.StylesheetLevel::ApplyFunctions
0x1a3a8  ldarg.2
0x1a3a9  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Qil.QilFunction>::.ctor()
0x1a3ae  dup
0x1a3af  stloc.s  4
0x1a3b1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class System.Xml.Xsl.Qil.QilName, class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Qil.QilFunction>>::set_Item(var<u1>, !!T0)
0x1a3b6  ldloc.s  4
0x1a3b8  stloc.3
0x1a3b9  ldloc.3
0x1a3ba  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Qil.QilFunction>::GetEnumerator()
0x1a3bf  stloc.s  5
0x1a3c1  br.s     loc_1A3E2
0x1a3c3  ldloca.s 5
0x1a3c5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xml.Xsl.Qil.QilFunction>::get_Current()
0x1a3ca  stloc.s  6
0x1a3cc  ldarg.0
0x1a3cd  ldloc.s  6
0x1a3cf  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilFunction::get_Arguments()
0x1a3d4  ldarg.3
0x1a3d5  ldloc.1
0x1a3d6  call     instance bool System.Xml.Xsl.Xslt.QilGenerator::FillupInvokeArgs(class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Qil.QilNode> formalArgs, class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Xslt.XslNode> actualArgs, class System.Xml.Xsl.Qil.QilList invokeArgs)
0x1a3db  brfalse.s loc_1A3E2
0x1a3dd  ldloc.s  6
0x1a3df  stloc.2
0x1a3e0  leave.s  loc_1A3FB
0x1a3e2  ldloca.s 5
0x1a3e4  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xml.Xsl.Qil.QilFunction>::MoveNext()
0x1a3e9  brtrue.s loc_1A3C3
0x1a3eb  leave.s  loc_1A3FB
0x1a3ed  ldloca.s 5
0x1a3ef  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xml.Xsl.Qil.QilFunction>
0x1a3f5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a3fa  endfinally
0x1a3fb  ldloc.2
0x1a3fc  brtrue   loc_1A665
0x1a401  ldloc.1
0x1a402  callvirt instance void System.Xml.Xsl.Qil.QilNode::Clear()
0x1a407  ldarg.0
0x1a408  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1a40d  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilPatternFactory::FormalParameterList()
0x1a412  stloc.s  7
0x1a414  ldc.i4.0
0x1a415  stloc.s  0xC
0x1a417  br.s     loc_1A485
0x1a419  ldarg.3
0x1a41a  ldloc.s  0xC
0x1a41c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Xslt.XslNode>::get_Item(!!T0)
0x1a421  castclass System.Xml.Xsl.Xslt.VarPar
0x1a426  stloc.s  0xD
0x1a428  ldloc.1
0x1a429  ldloc.s  0xD
0x1a42b  ldfld    class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.VarPar::Value
0x1a430  callvirt instance void System.Xml.Xsl.Qil.QilNode::Add(class System.Xml.Xsl.Qil.QilNode node)
0x1a435  ldarg.0
0x1a436  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1a43b  ldloc.s  0xC
0x1a43d  brfalse.s loc_1A44D
0x1a43f  ldloc.s  0xD
0x1a441  ldfld    class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.VarPar::Value
0x1a446  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x1a44b  br.s     loc_1A452
0x1a44d  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::NodeNotRtf
0x1a452  callvirt instance class System.Xml.Xsl.Qil.QilParameter System.Xml.Xsl.Qil.QilPatternFactory::Parameter(class System.Xml.Xsl.XmlQueryType t)
0x1a457  stloc.s  0xE
0x1a459  ldloc.s  0xE
0x1a45b  ldarg.0
0x1a45c  ldloc.s  0xD
0x1a45e  ldfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XslNode::Name
0x1a463  call     instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.QilGenerator::CloneName(class System.Xml.Xsl.Qil.QilName name)
0x1a468  callvirt instance void System.Xml.Xsl.Qil.QilParameter::set_Name(class System.Xml.Xsl.Qil.QilName value)
0x1a46d  ldloc.s  7
0x1a46f  ldloc.s  0xE
0x1a471  callvirt instance void System.Xml.Xsl.Qil.QilNode::Add(class System.Xml.Xsl.Qil.QilNode node)
0x1a476  ldloc.s  0xD
0x1a478  ldloc.s  0xE
0x1a47a  stfld    class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.VarPar::Value
0x1a47f  ldloc.s  0xC
0x1a481  ldc.i4.1
0x1a482  add
0x1a483  stloc.s  0xC
0x1a485  ldloc.s  0xC
0x1a487  ldarg.3
0x1a488  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class System.Xml.Xsl.Xslt.XslNode>::get_Count()
0x1a48d  blt.s    loc_1A419
0x1a48f  ldarg.0
0x1a490  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1a495  ldloc.s  7
0x1a497  ldarg.0
0x1a498  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1a49d  ldloc.0
0x1a49e  ldc.i4   0x4000
0x1a4a3  and
0x1a4a4  ldc.i4.0
0x1a4a5  cgt.un
0x1a4a7  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Boolean(bool b)
0x1a4ac  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::NodeNotRtfS
0x1a4b1  callvirt instance class System.Xml.Xsl.Qil.QilFunction System.Xml.Xsl.Qil.QilPatternFactory::Function(class System.Xml.Xsl.Qil.QilList args, class System.Xml.Xsl.Qil.QilNode sideEffects, class System.Xml.Xsl.XmlQueryType resultType)
0x1a4b6  stloc.2
0x1a4b7  ldarg.2
0x1a4b8  callvirt instance string System.Xml.Xsl.Qil.QilName::get_LocalName()
0x1a4bd  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1a4c2  brfalse.s loc_1A4DB
0x1a4c4  ldstr    aMode_0// " mode=\""
0x1a4c9  ldarg.2
0x1a4ca  callvirt instance string System.Xml.Xsl.Qil.QilName::get_QualifiedName()
0x1a4cf  ldstr    asc_5AD22// "\""
0x1a4d4  call     string [mscorlib]System.String::Concat(string, string, string)
0x1a4d9  br.s     loc_1A4E0
0x1a4db  ldsfld   string [mscorlib]System.String::Empty
0x1a4e0  stloc.s  8
0x1a4e2  ldloc.2
0x1a4e3  ldarg.1
0x1a4e4  isinst   System.Xml.Xsl.Xslt.RootLevel
0x1a4e9  brtrue.s loc_1A4F2
0x1a4eb  ldstr    aXslApplyImport// "<xsl:apply-imports"
0x1a4f0  br.s     loc_1A4F7
0x1a4f2  ldstr    aXslApplyTempla// "<xsl:apply-templates"
0x1a4f7  ldloc.s  8
0x1a4f9  ldstr    asc_5AD76// ">"
0x1a4fe  call     string [mscorlib]System.String::Concat(string, string, string)
0x1a503  callvirt instance void System.Xml.Xsl.Qil.QilReference::set_DebugName(string value)
0x1a508  ldloc.3
0x1a509  ldloc.2
0x1a50a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xml.Xsl.Qil.QilFunction>::Add(var<u1>)
0x1a50f  ldarg.0
0x1a510  ldfld    class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Xslt.QilGenerator::functions
0x1a515  ldloc.2
0x1a516  callvirt instance void System.Xml.Xsl.Qil.QilNode::Add(class System.Xml.Xsl.Qil.QilNode node)
0x1a51b  ldloc.s  7
0x1a51d  ldc.i4.0
0x1a51e  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x1a523  castclass System.Xml.Xsl.Qil.QilIterator
0x1a528  stloc.s  9
0x1a52a  ldarg.0
0x1a52b  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1a530  ldarg.0
0x1a531  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1a536  ldloc.s  9
0x1a538  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Content(class System.Xml.Xsl.Qil.QilNode context)
0x1a53d  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilPatternFactory::For(class System.Xml.Xsl.Qil.QilNode binding)
0x1a542  stloc.s  0xF
0x1a544  ldarg.0
0x1a545  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1a54a  ldloc.s  0xF
0x1a54c  ldarg.0
0x1a54d  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1a552  ldloc.s  0xF
0x1a554  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::Content
0x1a559  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::IsType(class System.Xml.Xsl.Qil.QilNode expr, class System.Xml.Xsl.XmlQueryType t)
0x1a55e  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Filter(class System.Xml.Xsl.Qil.QilIterator variable, class System.Xml.Xsl.Qil.QilNode expr)
0x1a563  stloc.s  0x10
0x1a565  ldloc.s  0x10
0x1a567  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::ContentS
0x1a56c  callvirt instance void System.Xml.Xsl.Qil.QilNode::set_XmlType(class System.Xml.Xsl.XmlQueryType value)
0x1a571  ldarg.0
0x1a572  ldfld    valuetype System.Xml.Xsl.Xslt.LoopFocus System.Xml.Xsl.Xslt.QilGenerator::curLoop
0x1a577  stloc.s  0x11
0x1a579  ldarg.0
0x1a57a  ldflda   valuetype System.Xml.Xsl.Xslt.LoopFocus System.Xml.Xsl.Xslt.QilGenerator::curLoop
0x1a57f  ldarg.0
0x1a580  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1a585  ldloc.s  0x10
0x1a587  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilPatternFactory::For(class System.Xml.Xsl.Qil.QilNode binding)
0x1a58c  call     instance void System.Xml.Xsl.Xslt.LoopFocus::SetFocus(class System.Xml.Xsl.Qil.QilIterator current)
0x1a591  ldarg.0
0x1a592  ldarg.0
0x1a593  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.QilGenerator::compiler
0x1a598  ldfld    class System.Xml.Xsl.Xslt.RootLevel System.Xml.Xsl.Xslt.Compiler::Root
0x1a59d  ldarg.2
0x1a59e  ldnull
0x1a59f  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::InvokeApplyFunction(class System.Xml.Xsl.Xslt.StylesheetLevel sheet, class System.Xml.Xsl.Qil.QilName mode, class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Xslt.XslNode> actualArgs)
0x1a5a4  stloc.s  0x12
0x1a5a6  ldarg.0
0x1a5a7  call     instance bool System.Xml.Xsl.Xslt.QilGenerator::get_IsDebug()
0x1a5ac  brfalse.s loc_1A5C3
0x1a5ae  ldarg.0
0x1a5af  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1a5b4  ldarg.0
0x1a5b5  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::InvokeOnCurrentNodeChanged()
0x1a5ba  ldloc.s  0x12
0x1a5bc  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Sequence(class System.Xml.Xsl.Qil.QilNode child1, class System.Xml.Xsl.Qil.QilNode child2)
0x1a5c1  stloc.s  0x12
0x1a5c3  ldarg.0
0x1a5c4  ldflda   valuetype System.Xml.Xsl.Xslt.LoopFocus System.Xml.Xsl.Xslt.QilGenerator::curLoop
0x1a5c9  ldloc.s  0x12
0x1a5cb  call     instance class System.Xml.Xsl.Qil.QilLoop System.Xml.Xsl.Xslt.LoopFocus::ConstructLoop(class System.Xml.Xsl.Qil.QilNode body)
0x1a5d0  stloc.s  0xA
0x1a5d2  ldarg.0
0x1a5d3  ldloc.s  0x11
0x1a5d5  stfld    valuetype System.Xml.Xsl.Xslt.LoopFocus System.Xml.Xsl.Xslt.QilGenerator::curLoop
0x1a5da  ldarg.0
0x1a5db  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1a5e0  callvirt instance class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilPatternFactory::get_BaseFactory()
0x1a5e5  ldarg.0
0x1a5e6  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1a5eb  ldloc.s  9
0x1a5ed  ldarg.0
0x1a5ee  ldfld    class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Xslt.QilGenerator::elementOrDocumentType
0x1a5f3  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::IsType(class System.Xml.Xsl.Qil.QilNode expr, class System.Xml.Xsl.XmlQueryType t)
0x1a5f8  ldloc.s  0xA
0x1a5fa  ldarg.0
0x1a5fb  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1a600  ldarg.0
0x1a601  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1a606  ldloc.s  9
0x1a608  ldarg.0
0x1a609  ldfld    class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Xslt.QilGenerator::textOrAttributeType
0x1a60e  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::IsType(class System.Xml.Xsl.Qil.QilNode expr, class System.Xml.Xsl.XmlQueryType t)
0x1a613  ldarg.0
0x1a614  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1a619  ldarg.0
0x1a61a  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1a61f  ldloc.s  9
0x1a621  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::XPathNodeValue(class System.Xml.Xsl.Qil.QilNode expr)
0x1a626  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::TextCtor(class System.Xml.Xsl.Qil.QilNode content)
0x1a62b  ldarg.0
0x1a62c  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1a631  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Sequence()
0x1a636  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Conditional(class System.Xml.Xsl.Qil.QilNode condition, class System.Xml.Xsl.Qil.QilNode trueBranch, class System.Xml.Xsl.Qil.QilNode falseBranch)
0x1a63b  callvirt instance class System.Xml.Xsl.Qil.QilTernary System.Xml.Xsl.Qil.QilFactory::Conditional(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode center, class System.Xml.Xsl.Qil.QilNode right)
0x1a640  stloc.s  0xB
0x1a642  ldarg.0
0x1a643  ldfld    class System.Xml.Xsl.Xslt.MatcherBuilder System.Xml.Xsl.Xslt.QilGenerator::matcherBuilder
0x1a648  ldarg.1
0x1a649  ldarg.2
0x1a64a  callvirt instance void System.Xml.Xsl.Xslt.MatcherBuilder::CollectPatterns(class System.Xml.Xsl.Xslt.StylesheetLevel sheet, class System.Xml.Xsl.Qil.QilName mode)
0x1a64f  ldloc.2
0x1a650  ldarg.0
0x1a651  ldfld    class System.Xml.Xsl.Xslt.MatcherBuilder System.Xml.Xsl.Xslt.QilGenerator::matcherBuilder
0x1a656  ldloc.s  9
0x1a658  ldarg.3
0x1a659  ldloc.s  0xB
0x1a65b  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.MatcherBuilder::BuildMatcher(class System.Xml.Xsl.Qil.QilIterator it, class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Xslt.XslNode> actualArgs, class System.Xml.Xsl.Qil.QilNode otherwise)
0x1a660  callvirt instance void System.Xml.Xsl.Qil.QilFunction::set_Definition(class System.Xml.Xsl.Qil.QilNode value)
0x1a665  ldarg.0
0x1a666  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x1a66b  ldloc.2
0x1a66c  ldloc.1
0x1a66d  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Invoke(class System.Xml.Xsl.Qil.QilFunction func, class System.Xml.Xsl.Qil.QilList args)
0x1a672  ret
```
