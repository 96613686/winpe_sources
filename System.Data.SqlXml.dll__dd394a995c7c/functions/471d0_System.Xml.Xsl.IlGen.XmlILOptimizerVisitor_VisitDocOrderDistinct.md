# System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::VisitDocOrderDistinct

- ea: `0x471d0`
- end: `0x479cf`
- name: `System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::VisitDocOrderDistinct`
- size: `2047`
- prototype: ``
- caller_count: `0`
- callee_count: `34`
- tags: `registry_config`

## callees

- `0x2030`
- `0x36190`
- `0x361f0`
- `0x367f0`
- `0x36810`
- `0x36870`
- `0x36980`
- `0x376a0`
- `0x376c0`
- `0x37750`
- `0x38590`
- `0x3aef0`
- `0x3af20`
- `0x3b230`
- `0x3b240`
- `0x3b270`
- `0x3b300`
- `0x409c0`
- `0x40a90`
- `0x40af0`
- `0x40bd0`
- `0x40c00`
- `0x40c40`
- `0x40c60`
- `0x42c20`
- `0x42c30`
- `0x471d0`
- `0x49720`
- `0x49730`
- `0x49750`
- `0x49a70`
- `0x49ad0`
- `0x4a190`
- `0x4a1a0`

## pseudocode

```c

```

## disassembly

```asm
0x471d0  ldarg.1
0x471d1  ldc.i4.0
0x471d2  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x471d7  stloc.0
0x471d8  ldarg.0
0x471d9  ldc.i4.s 0x68
0x471db  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x471e0  brfalse.s loc_47216
0x471e2  ldloc.0
0x471e3  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x471e8  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::None
0x471ed  bne.un.s loc_47216
0x471ef  ldarg.0
0x471f0  ldc.i4.s 0x68
0x471f2  ldarg.1
0x471f3  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x471f8  brfalse.s loc_47216
0x471fa  ldarg.0
0x471fb  ldc.i4.s 0x68
0x471fd  ldarg.1
0x471fe  ldarg.0
0x471ff  ldarg.0
0x47200  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x47205  ldloc.0
0x47206  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::Nop(class System.Xml.Xsl.Qil.QilNode child)
0x4720b  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNop(class System.Xml.Xsl.Qil.QilUnary n)
0x47210  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x47215  ret
0x47216  ldarg.0
0x47217  ldc.i4.s 0x3F
0x47219  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x4721e  brfalse.s loc_4723F
0x47220  ldarg.0
0x47221  ldloc.0
0x47222  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsDocOrderDistinct(class System.Xml.Xsl.Qil.QilNode nd)
0x47227  brfalse.s loc_4723F
0x47229  ldarg.0
0x4722a  ldc.i4.s 0x3F
0x4722c  ldarg.1
0x4722d  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x47232  brfalse.s loc_4723F
0x47234  ldarg.0
0x47235  ldc.i4.s 0x3F
0x47237  ldarg.1
0x47238  ldloc.0
0x47239  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x4723e  ret
0x4723f  ldarg.0
0x47240  ldc.i4.s 0x67
0x47242  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x47247  brfalse  loc_4737C
0x4724c  ldloc.0
0x4724d  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x47252  ldc.i4.s 0x3C
0x47254  bne.un   loc_4737C
0x47259  ldloc.0
0x4725a  ldc.i4.0
0x4725b  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x47260  stloc.1
0x47261  ldloc.0
0x47262  ldc.i4.1
0x47263  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x47268  stloc.2
0x47269  ldloc.1
0x4726a  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x4726f  ldc.i4.s 0xE
0x47271  bne.un   loc_4737C
0x47276  ldloc.1
0x47277  ldc.i4.0
0x47278  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x4727d  stloc.3
0x4727e  ldloc.3
0x4727f  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x47284  ldc.i4.s 0x3C
0x47286  bne.un   loc_4737C
0x4728b  ldloc.3
0x4728c  ldc.i4.0
0x4728d  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x47292  stloc.s  4
0x47294  ldloc.3
0x47295  ldc.i4.1
0x47296  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x4729b  stloc.s  5
0x4729d  ldloc.s  5
0x4729f  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x472a4  ldc.i4.s 0x49
0x472a6  bne.un   loc_4737C
0x472ab  ldloc.s  5
0x472ad  ldc.i4.0
0x472ae  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x472b3  stloc.s  6
0x472b5  ldloc.2
0x472b6  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x472bb  ldc.i4.s 0x3D
0x472bd  bne.un   loc_4737C
0x472c2  ldloc.2
0x472c3  ldc.i4.0
0x472c4  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x472c9  stloc.s  7
0x472cb  ldloc.2
0x472cc  ldc.i4.1
0x472cd  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x472d2  stloc.s  8
0x472d4  ldloc.2
0x472d5  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Read(class System.Xml.Xsl.Qil.QilNode nd)
0x472da  ldc.i4.5
0x472db  callvirt instance bool System.Xml.Xsl.IlGen.OptimizerPatterns::MatchesPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x472e0  brtrue.s loc_472F3
0x472e2  ldloc.2
0x472e3  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Read(class System.Xml.Xsl.Qil.QilNode nd)
0x472e8  ldc.i4.4
0x472e9  callvirt instance bool System.Xml.Xsl.IlGen.OptimizerPatterns::MatchesPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x472ee  brfalse  loc_4737C
0x472f3  ldarg.0
0x472f4  ldloc.2
0x472f5  ldc.i4.s 0x43
0x472f7  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsStepPattern(class System.Xml.Xsl.Qil.QilNode nd, valuetype System.Xml.Xsl.Qil.QilNodeType stepType)
0x472fc  brfalse.s loc_4737C
0x472fe  ldarg.0
0x472ff  ldc.i4.s 0x67
0x47301  ldarg.1
0x47302  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x47307  brfalse.s loc_4737C
0x47309  ldarg.0
0x4730a  ldarg.0
0x4730b  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x47310  ldarg.0
0x47311  ldarg.0
0x47312  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x47317  ldloc.s  6
0x47319  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::Descendant(class System.Xml.Xsl.Qil.QilNode child)
0x4731e  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitDescendant(class System.Xml.Xsl.Qil.QilUnary n)
0x47323  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilFactory::For(class System.Xml.Xsl.Qil.QilNode binding)
0x47328  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitFor(class System.Xml.Xsl.Qil.QilIterator n)
0x4732d  stloc.s  9
0x4732f  ldarg.0
0x47330  ldc.i4.s 0x67
0x47332  ldarg.1
0x47333  ldarg.0
0x47334  ldarg.0
0x47335  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x4733a  ldarg.0
0x4733b  ldarg.0
0x4733c  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x47341  ldloc.s  4
0x47343  ldarg.0
0x47344  ldarg.0
0x47345  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x4734a  ldloc.s  9
0x4734c  ldarg.0
0x4734d  ldloc.s  8
0x4734f  ldloc.s  7
0x47351  ldloc.s  9
0x47353  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Subs(class System.Xml.Xsl.Qil.QilNode expr, class System.Xml.Xsl.Qil.QilNode refOld, class System.Xml.Xsl.Qil.QilNode refNew)
0x47358  callvirt instance class System.Xml.Xsl.Qil.QilLoop System.Xml.Xsl.Qil.QilFactory::Filter(class System.Xml.Xsl.Qil.QilNode variable, class System.Xml.Xsl.Qil.QilNode body)
0x4735d  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitFilter(class System.Xml.Xsl.Qil.QilLoop n)
0x47362  callvirt instance class System.Xml.Xsl.Qil.QilLoop System.Xml.Xsl.Qil.QilFactory::Loop(class System.Xml.Xsl.Qil.QilNode variable, class System.Xml.Xsl.Qil.QilNode body)
0x47367  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitLoop(class System.Xml.Xsl.Qil.QilLoop n)
0x4736c  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::DocOrderDistinct(class System.Xml.Xsl.Qil.QilNode child)
0x47371  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitDocOrderDistinct(class System.Xml.Xsl.Qil.QilUnary n)
0x47376  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x4737b  ret
0x4737c  ldarg.0
0x4737d  ldc.i4.s 0x67
0x4737f  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x47384  brfalse  loc_4747E
0x47389  ldloc.0
0x4738a  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x4738f  ldc.i4.s 0x3C
0x47391  bne.un   loc_4747E
0x47396  ldloc.0
0x47397  ldc.i4.0
0x47398  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x4739d  stloc.s  0xA
0x4739f  ldloc.0
0x473a0  ldc.i4.1
0x473a1  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x473a6  stloc.s  0xB
0x473a8  ldloc.s  0xA
0x473aa  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x473af  ldc.i4.s 0xE
0x473b1  bne.un   loc_4747E
0x473b6  ldloc.s  0xA
0x473b8  ldc.i4.0
0x473b9  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x473be  stloc.s  0xC
0x473c0  ldloc.s  0xC
0x473c2  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x473c7  ldc.i4.s 0x49
0x473c9  bne.un   loc_4747E
0x473ce  ldloc.s  0xC
0x473d0  ldc.i4.0
0x473d1  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x473d6  stloc.s  0xD
0x473d8  ldloc.s  0xB
0x473da  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x473df  ldc.i4.s 0x3D
0x473e1  bne.un   loc_4747E
0x473e6  ldloc.s  0xB
0x473e8  ldc.i4.0
0x473e9  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x473ee  stloc.s  0xE
0x473f0  ldloc.s  0xB
0x473f2  ldc.i4.1
0x473f3  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x473f8  stloc.s  0xF
0x473fa  ldloc.s  0xB
0x473fc  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Read(class System.Xml.Xsl.Qil.QilNode nd)
0x47401  ldc.i4.5
0x47402  callvirt instance bool System.Xml.Xsl.IlGen.OptimizerPatterns::MatchesPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x47407  brtrue.s loc_47418
0x47409  ldloc.s  0xB
0x4740b  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Read(class System.Xml.Xsl.Qil.QilNode nd)
0x47410  ldc.i4.4
0x47411  callvirt instance bool System.Xml.Xsl.IlGen.OptimizerPatterns::MatchesPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x47416  brfalse.s loc_4747E
0x47418  ldarg.0
0x47419  ldloc.s  0xB
0x4741b  ldc.i4.s 0x43
0x4741d  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsStepPattern(class System.Xml.Xsl.Qil.QilNode nd, valuetype System.Xml.Xsl.Qil.QilNodeType stepType)
0x47422  brfalse.s loc_4747E
0x47424  ldarg.0
0x47425  ldc.i4.s 0x67
0x47427  ldarg.1
0x47428  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x4742d  brfalse.s loc_4747E
0x4742f  ldarg.0
0x47430  ldarg.0
0x47431  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x47436  ldarg.0
0x47437  ldarg.0
0x47438  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x4743d  ldloc.s  0xD
0x4743f  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::Descendant(class System.Xml.Xsl.Qil.QilNode child)
0x47444  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitDescendant(class System.Xml.Xsl.Qil.QilUnary n)
0x47449  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilFactory::For(class System.Xml.Xsl.Qil.QilNode binding)
0x4744e  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitFor(class System.Xml.Xsl.Qil.QilIterator n)
0x47453  stloc.s  0x10
0x47455  ldarg.0
0x47456  ldc.i4.s 0x67
0x47458  ldarg.1
0x47459  ldarg.0
0x4745a  ldarg.0
0x4745b  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x47460  ldloc.s  0x10
0x47462  ldarg.0
0x47463  ldloc.s  0xF
0x47465  ldloc.s  0xE
0x47467  ldloc.s  0x10
0x47469  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Subs(class System.Xml.Xsl.Qil.QilNode expr, class System.Xml.Xsl.Qil.QilNode refOld, class System.Xml.Xsl.Qil.QilNode refNew)
0x4746e  callvirt instance class System.Xml.Xsl.Qil.QilLoop System.Xml.Xsl.Qil.QilFactory::Filter(class System.Xml.Xsl.Qil.QilNode variable, class System.Xml.Xsl.Qil.QilNode body)
0x47473  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitFilter(class System.Xml.Xsl.Qil.QilLoop n)
0x47478  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x4747d  ret
0x4747e  ldarg.0
0x4747f  ldc.i4.s 0x35
0x47481  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x47486  brfalse  loc_47558
0x4748b  ldloc.0
0x4748c  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x47491  ldc.i4.s 0x3D
0x47493  bne.un   loc_47558
0x47498  ldloc.0
0x47499  ldc.i4.0
0x4749a  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x4749f  stloc.s  0x11
0x474a1  ldloc.0
0x474a2  ldc.i4.1
0x474a3  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x474a8  stloc.s  0x12
0x474aa  ldloc.s  0x11
0x474ac  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x474b1  ldc.i4.s 0xE
0x474b3  bne.un   loc_47558
0x474b8  ldloc.s  0x11
0x474ba  ldc.i4.0
0x474bb  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x474c0  stloc.s  0x13
0x474c2  ldloc.s  0x11
0x474c4  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Read(class System.Xml.Xsl.Qil.QilNode nd)
0x474c9  ldc.i4.7
0x474ca  callvirt instance bool System.Xml.Xsl.IlGen.OptimizerPatterns::MatchesPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x474cf  brtrue   loc_47558
0x474d4  ldloc.0
0x474d5  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Read(class System.Xml.Xsl.Qil.QilNode nd)
0x474da  ldc.i4.5
0x474db  callvirt instance bool System.Xml.Xsl.IlGen.OptimizerPatterns::MatchesPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x474e0  brtrue.s loc_47558
0x474e2  ldloc.0
0x474e3  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Read(class System.Xml.Xsl.Qil.QilNode nd)
0x474e8  ldc.i4.4
0x474e9  callvirt instance bool System.Xml.Xsl.IlGen.OptimizerPatterns::MatchesPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x474ee  brtrue.s loc_47558
0x474f0  ldloc.0
0x474f1  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Read(class System.Xml.Xsl.Qil.QilNode nd)
0x474f6  ldc.i4.3
0x474f7  callvirt instance bool System.Xml.Xsl.IlGen.OptimizerPatterns::MatchesPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x474fc  brtrue.s loc_47558
0x474fe  ldarg.0
0x474ff  ldc.i4.s 0x35
  ... truncated ...
```
