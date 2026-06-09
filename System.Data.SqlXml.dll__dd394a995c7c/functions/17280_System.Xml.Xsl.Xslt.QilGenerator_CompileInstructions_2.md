# System.Xml.Xsl.Xslt.QilGenerator::CompileInstructions_2

- ea: `0x17280`
- end: `0x1754c`
- name: `System.Xml.Xsl.Xslt.QilGenerator::CompileInstructions_2`
- size: `716`
- prototype: ``
- caller_count: `3`
- callee_count: `38`
- tags: `registry_config, broker_com_uri`

## callers

- `0x17250`
- `0x17260`
- `0x17270`

## callees

- `0x162d0`
- `0x167e0`
- `0x16810`
- `0x17260`
- `0x17280`
- `0x17550`
- `0x17560`
- `0x175d0`
- `0x17740`
- `0x17830`
- `0x17890`
- `0x17c20`
- `0x17c70`
- `0x17cc0`
- `0x17ce0`
- `0x17d50`
- `0x17df0`
- `0x17f70`
- `0x17f90`
- `0x18110`
- `0x181b0`
- `0x18290`
- `0x183d0`
- `0x18400`
- `0x18460`
- `0x18470`
- `0x18510`
- `0x185b0`
- `0x19700`
- `0x1a730`
- `0x1a7c0`
- `0x376a0`
- `0x37740`
- `0x37750`
- `0x377c0`
- `0x37c50`
- `0x38120`
- `0x38ce0`

## pseudocode

```c

```

## disassembly

```asm
0x17280  ldarg.2
0x17281  stloc.0
0x17282  br       loc_17525
0x17287  ldarg.1
0x17288  ldloc.0
0x17289  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Xslt.XslNode>::get_Item(!!T0)
0x1728e  stloc.1
0x1728f  ldloc.1
0x17290  ldfld    valuetype System.Xml.Xsl.Xslt.XslNodeType System.Xml.Xsl.Xslt.XslNode::NodeType
0x17295  stloc.2
0x17296  ldloc.2
0x17297  ldc.i4.s 0x16
0x17299  beq      loc_17521
0x1729e  ldarg.0
0x1729f  ldloc.1
0x172a0  call     instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Xslt.QilGenerator::EnterScope(class System.Xml.Xsl.Xslt.XslNode node)
0x172a5  stloc.3
0x172a6  ldloc.2
0x172a7  ldc.i4.1
0x172a8  sub
0x172a9  switch   loc_1732B, loc_17339, loc_1734C, loc_1747D, loc_1735F, loc_17372, loc_17380, loc_1738E, loc_1739C, loc_173AA, loc_173BD, loc_173CB, loc_173DE, loc_1747D, loc_173EC, loc_173FA, loc_17405, loc_17410, loc_1741B, loc_17426, loc_1747D, loc_1747D, loc_17436, loc_1747D, loc_1747D, loc_17441, loc_17451, loc_1745C, loc_17467, loc_17472
0x17326  br       loc_1747D
0x1732b  ldarg.0
0x1732c  ldloc.1
0x1732d  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileApplyImports(class System.Xml.Xsl.Xslt.XslNode node)
0x17332  stloc.s  4
0x17334  br       loc_17480
0x17339  ldarg.0
0x1733a  ldloc.1
0x1733b  castclass System.Xml.Xsl.Xslt.XslNodeEx
0x17340  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileApplyTemplates(class System.Xml.Xsl.Xslt.XslNodeEx node)
0x17345  stloc.s  4
0x17347  br       loc_17480
0x1734c  ldarg.0
0x1734d  ldloc.1
0x1734e  castclass System.Xml.Xsl.Xslt.NodeCtor
0x17353  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileAttribute(class System.Xml.Xsl.Xslt.NodeCtor node)
0x17358  stloc.s  4
0x1735a  br       loc_17480
0x1735f  ldarg.0
0x17360  ldloc.1
0x17361  castclass System.Xml.Xsl.Xslt.XslNodeEx
0x17366  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileCallTemplate(class System.Xml.Xsl.Xslt.XslNodeEx node)
0x1736b  stloc.s  4
0x1736d  br       loc_17480
0x17372  ldarg.0
0x17373  ldloc.1
0x17374  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileChoose(class System.Xml.Xsl.Xslt.XslNode node)
0x17379  stloc.s  4
0x1737b  br       loc_17480
0x17380  ldarg.0
0x17381  ldloc.1
0x17382  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileComment(class System.Xml.Xsl.Xslt.XslNode node)
0x17387  stloc.s  4
0x17389  br       loc_17480
0x1738e  ldarg.0
0x1738f  ldloc.1
0x17390  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileCopy(class System.Xml.Xsl.Xslt.XslNode copy)
0x17395  stloc.s  4
0x17397  br       loc_17480
0x1739c  ldarg.0
0x1739d  ldloc.1
0x1739e  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileCopyOf(class System.Xml.Xsl.Xslt.XslNode node)
0x173a3  stloc.s  4
0x173a5  br       loc_17480
0x173aa  ldarg.0
0x173ab  ldloc.1
0x173ac  castclass System.Xml.Xsl.Xslt.NodeCtor
0x173b1  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileElement(class System.Xml.Xsl.Xslt.NodeCtor node)
0x173b6  stloc.s  4
0x173b8  br       loc_17480
0x173bd  ldarg.0
0x173be  ldloc.1
0x173bf  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileError(class System.Xml.Xsl.Xslt.XslNode node)
0x173c4  stloc.s  4
0x173c6  br       loc_17480
0x173cb  ldarg.0
0x173cc  ldloc.1
0x173cd  castclass System.Xml.Xsl.Xslt.XslNodeEx
0x173d2  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileForEach(class System.Xml.Xsl.Xslt.XslNodeEx node)
0x173d7  stloc.s  4
0x173d9  br       loc_17480
0x173de  ldarg.0
0x173df  ldloc.1
0x173e0  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileIf(class System.Xml.Xsl.Xslt.XslNode ifNode)
0x173e5  stloc.s  4
0x173e7  br       loc_17480
0x173ec  ldarg.0
0x173ed  ldloc.1
0x173ee  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileList(class System.Xml.Xsl.Xslt.XslNode node)
0x173f3  stloc.s  4
0x173f5  br       loc_17480
0x173fa  ldarg.0
0x173fb  ldloc.1
0x173fc  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileLiteralAttribute(class System.Xml.Xsl.Xslt.XslNode node)
0x17401  stloc.s  4
0x17403  br.s     loc_17480
0x17405  ldarg.0
0x17406  ldloc.1
0x17407  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileLiteralElement(class System.Xml.Xsl.Xslt.XslNode node)
0x1740c  stloc.s  4
0x1740e  br.s     loc_17480
0x17410  ldarg.0
0x17411  ldloc.1
0x17412  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileMessage(class System.Xml.Xsl.Xslt.XslNode node)
0x17417  stloc.s  4
0x17419  br.s     loc_17480
0x1741b  ldarg.0
0x1741c  ldloc.1
0x1741d  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileNop(class System.Xml.Xsl.Xslt.XslNode node)
0x17422  stloc.s  4
0x17424  br.s     loc_17480
0x17426  ldarg.0
0x17427  ldloc.1
0x17428  castclass System.Xml.Xsl.Xslt.Number
0x1742d  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileNumber(class System.Xml.Xsl.Xslt.Number num)
0x17432  stloc.s  4
0x17434  br.s     loc_17480
0x17436  ldarg.0
0x17437  ldloc.1
0x17438  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompilePI(class System.Xml.Xsl.Xslt.XslNode node)
0x1743d  stloc.s  4
0x1743f  br.s     loc_17480
0x17441  ldarg.0
0x17442  ldloc.1
0x17443  castclass System.Xml.Xsl.Xslt.Text
0x17448  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileText(class System.Xml.Xsl.Xslt.Text node)
0x1744d  stloc.s  4
0x1744f  br.s     loc_17480
0x17451  ldarg.0
0x17452  ldloc.1
0x17453  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileUseAttributeSet(class System.Xml.Xsl.Xslt.XslNode node)
0x17458  stloc.s  4
0x1745a  br.s     loc_17480
0x1745c  ldarg.0
0x1745d  ldloc.1
0x1745e  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileValueOf(class System.Xml.Xsl.Xslt.XslNode valueOf)
0x17463  stloc.s  4
0x17465  br.s     loc_17480
0x17467  ldarg.0
0x17468  ldloc.1
0x17469  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileValueOfDoe(class System.Xml.Xsl.Xslt.XslNode valueOf)
0x1746e  stloc.s  4
0x17470  br.s     loc_17480
0x17472  ldarg.0
0x17473  ldloc.1
0x17474  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileVariable(class System.Xml.Xsl.Xslt.XslNode node)
0x17479  stloc.s  4
0x1747b  br.s     loc_17480
0x1747d  ldnull
0x1747e  stloc.s  4
0x17480  ldarg.0
0x17481  call     instance void System.Xml.Xsl.Xslt.QilGenerator::ExitScope()
0x17486  ldloc.s  4
0x17488  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x1748d  ldc.i4.s 0x22
0x1748f  bne.un.s loc_1749D
0x17491  ldloc.s  4
0x17493  callvirt instance int32 System.Xml.Xsl.Qil.QilNode::get_Count()
0x17498  brfalse  loc_17521
0x1749d  ldloc.2
0x1749e  ldc.i4.s 0x10
0x174a0  beq.s    loc_174B5
0x174a2  ldloc.2
0x174a3  ldc.i4.s 0x1B
0x174a5  beq.s    loc_174B5
0x174a7  ldarg.0
0x174a8  ldloc.s  4
0x174aa  ldloc.1
0x174ab  ldfld    class System.Xml.Xsl.ISourceLineInfo System.Xml.Xsl.Xslt.XslNode::SourceLine
0x174b0  call     instance void System.Xml.Xsl.Xslt.QilGenerator::SetLineInfoCheck(class System.Xml.Xsl.Qil.QilNode n, class System.Xml.Xsl.ISourceLineInfo lineInfo)
0x174b5  ldarg.0
0x174b6  ldloc.s  4
0x174b8  ldloc.3
0x174b9  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::SetDebugNs(class System.Xml.Xsl.Qil.QilNode n, class System.Xml.Xsl.Qil.QilList nsList)
0x174be  stloc.s  4
0x174c0  ldloc.2
0x174c1  ldc.i4.s 0x1E
0x174c3  bne.un.s loc_17519
0x174c5  ldarg.0
0x174c6  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x174cb  ldloc.s  4
0x174cd  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilPatternFactory::Let(class System.Xml.Xsl.Qil.QilNode binding)
0x174d2  stloc.s  5
0x174d4  ldloc.s  5
0x174d6  ldloc.1
0x174d7  ldfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XslNode::Name
0x174dc  callvirt instance string [mscorlib]System.Object::ToString()
0x174e1  callvirt instance void System.Xml.Xsl.Qil.QilReference::set_DebugName(string value)
0x174e6  ldarg.0
0x174e7  ldfld    class System.Xml.Xsl.Xslt.CompilerScopeManager`1<class System.Xml.Xsl.Qil.QilIterator> System.Xml.Xsl.Xslt.QilGenerator::scope
0x174ec  ldloc.1
0x174ed  ldfld    class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Xslt.XslNode::Name
0x174f2  ldloc.s  5
0x174f4  callvirt instance void class System.Xml.Xsl.Xslt.CompilerScopeManager`1<class System.Xml.Xsl.Qil.QilIterator>::AddVariable(class System.Xml.Xsl.Qil.QilName, var<u1>)
0x174f9  ldarg.0
0x174fa  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x174ff  ldloc.s  5
0x17501  ldarg.0
0x17502  ldarg.1
0x17503  ldloc.0
0x17504  ldc.i4.1
0x17505  add
0x17506  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Xslt.QilGenerator::CompileInstructions(class [mscorlib]System.Collections.Generic.IList`1<class System.Xml.Xsl.Xslt.XslNode> instructions, int32 from)
0x1750b  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternFactory::Loop(class System.Xml.Xsl.Qil.QilIterator variable, class System.Xml.Xsl.Qil.QilNode body)
0x17510  stloc.s  4
0x17512  ldarg.1
0x17513  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class System.Xml.Xsl.Xslt.XslNode>::get_Count()
0x17518  stloc.0
0x17519  ldarg.3
0x1751a  ldloc.s  4
0x1751c  callvirt instance void System.Xml.Xsl.Qil.QilNode::Add(class System.Xml.Xsl.Qil.QilNode node)
0x17521  ldloc.0
0x17522  ldc.i4.1
0x17523  add
0x17524  stloc.0
0x17525  ldloc.0
0x17526  ldarg.1
0x17527  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class System.Xml.Xsl.Xslt.XslNode>::get_Count()
0x1752c  blt      loc_17287
0x17531  ldarg.0
0x17532  call     instance bool System.Xml.Xsl.Xslt.QilGenerator::get_IsDebug()
0x17537  brtrue.s loc_1754A
0x17539  ldarg.3
0x1753a  callvirt instance int32 System.Xml.Xsl.Qil.QilNode::get_Count()
0x1753f  ldc.i4.1
0x17540  bne.un.s loc_1754A
0x17542  ldarg.3
0x17543  ldc.i4.0
0x17544  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x17549  ret
0x1754a  ldarg.3
0x1754b  ret
```
