# System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::VisitLoop

- ea: `0x46190`
- end: `0x468d5`
- name: `System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::VisitLoop`
- size: `1861`
- prototype: ``
- caller_count: `0`
- callee_count: `36`
- tags: `registry_config`

## callees

- `0x2370`
- `0x23b0`
- `0x36190`
- `0x361f0`
- `0x36430`
- `0x364b0`
- `0x367f0`
- `0x36810`
- `0x36b20`
- `0x376a0`
- `0x376c0`
- `0x37740`
- `0x37750`
- `0x38590`
- `0x3aef0`
- `0x3af20`
- `0x3b050`
- `0x3b090`
- `0x3b230`
- `0x3b240`
- `0x3b3d0`
- `0x409c0`
- `0x40a90`
- `0x40af0`
- `0x40c00`
- `0x40c40`
- `0x40c60`
- `0x42c20`
- `0x42c30`
- `0x46190`
- `0x49720`
- `0x49730`
- `0x49740`
- `0x49750`
- `0x4a1a0`
- `0x578f0`

## pseudocode

```c

```

## disassembly

```asm
0x46190  ldarg.1
0x46191  ldc.i4.0
0x46192  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x46197  stloc.0
0x46198  ldarg.1
0x46199  ldc.i4.1
0x4619a  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x4619f  stloc.1
0x461a0  ldarg.0
0x461a1  ldc.i4.s 0x68
0x461a3  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x461a8  brfalse.s loc_461E4
0x461aa  ldloc.0
0x461ab  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x461b0  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::None
0x461b5  bne.un.s loc_461E4
0x461b7  ldarg.0
0x461b8  ldc.i4.s 0x68
0x461ba  ldarg.1
0x461bb  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x461c0  brfalse.s loc_461E4
0x461c2  ldarg.0
0x461c3  ldc.i4.s 0x68
0x461c5  ldarg.1
0x461c6  ldarg.0
0x461c7  ldarg.0
0x461c8  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x461cd  ldloc.0
0x461ce  ldc.i4.0
0x461cf  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x461d4  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::Nop(class System.Xml.Xsl.Qil.QilNode child)
0x461d9  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNop(class System.Xml.Xsl.Qil.QilUnary n)
0x461de  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x461e3  ret
0x461e4  ldarg.0
0x461e5  ldc.i4.s 0x48
0x461e7  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x461ec  brfalse.s loc_46236
0x461ee  ldloc.0
0x461ef  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x461f4  ldc.i4.s 0xE
0x461f6  bne.un.s loc_46236
0x461f8  ldloc.0
0x461f9  ldc.i4.0
0x461fa  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x461ff  stloc.2
0x46200  ldloc.2
0x46201  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x46206  ldc.i4.s 0xE
0x46208  bne.un.s loc_46236
0x4620a  ldloc.0
0x4620b  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Read(class System.Xml.Xsl.Qil.QilNode nd)
0x46210  ldc.i4.7
0x46211  callvirt instance bool System.Xml.Xsl.IlGen.OptimizerPatterns::MatchesPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x46216  brtrue.s loc_46236
0x46218  ldarg.0
0x46219  ldc.i4.s 0x48
0x4621b  ldarg.1
0x4621c  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x46221  brfalse.s loc_46236
0x46223  ldarg.0
0x46224  ldc.i4.s 0x48
0x46226  ldarg.1
0x46227  ldarg.0
0x46228  ldloc.1
0x46229  ldloc.0
0x4622a  ldloc.2
0x4622b  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Subs(class System.Xml.Xsl.Qil.QilNode expr, class System.Xml.Xsl.Qil.QilNode refOld, class System.Xml.Xsl.Qil.QilNode refNew)
0x46230  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x46235  ret
0x46236  ldarg.0
0x46237  ldc.i4.s 0x4C
0x46239  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x4623e  brfalse.s loc_4628A
0x46240  ldloc.0
0x46241  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x46246  ldc.i4.s 0xE
0x46248  bne.un.s loc_4628A
0x4624a  ldloc.0
0x4624b  ldc.i4.0
0x4624c  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x46251  stloc.3
0x46252  ldloc.3
0x46253  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x46258  ldc.i4.s 0x22
0x4625a  bne.un.s loc_4628A
0x4625c  ldloc.3
0x4625d  callvirt instance int32 System.Xml.Xsl.Qil.QilNode::get_Count()
0x46262  brtrue.s loc_4628A
0x46264  ldarg.0
0x46265  ldc.i4.s 0x4C
0x46267  ldarg.1
0x46268  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x4626d  brfalse.s loc_4628A
0x4626f  ldarg.0
0x46270  ldc.i4.s 0x4C
0x46272  ldarg.1
0x46273  ldarg.0
0x46274  ldarg.0
0x46275  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x4627a  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilFactory::Sequence()
0x4627f  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitSequence(class System.Xml.Xsl.Qil.QilList n)
0x46284  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x46289  ret
0x4628a  ldarg.0
0x4628b  ldc.i4.s 0x4C
0x4628d  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x46292  brfalse.s loc_462DB
0x46294  ldloc.0
0x46295  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Read(class System.Xml.Xsl.Qil.QilNode nd)
0x4629a  ldc.i4.s 0xE
0x4629c  callvirt instance bool System.Xml.Xsl.IlGen.OptimizerPatterns::MatchesPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x462a1  brtrue.s loc_462DB
0x462a3  ldloc.1
0x462a4  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x462a9  ldc.i4.s 0x22
0x462ab  bne.un.s loc_462DB
0x462ad  ldloc.1
0x462ae  callvirt instance int32 System.Xml.Xsl.Qil.QilNode::get_Count()
0x462b3  brtrue.s loc_462DB
0x462b5  ldarg.0
0x462b6  ldc.i4.s 0x4C
0x462b8  ldarg.1
0x462b9  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x462be  brfalse.s loc_462DB
0x462c0  ldarg.0
0x462c1  ldc.i4.s 0x4C
0x462c3  ldarg.1
0x462c4  ldarg.0
0x462c5  ldarg.0
0x462c6  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x462cb  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilFactory::Sequence()
0x462d0  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitSequence(class System.Xml.Xsl.Qil.QilList n)
0x462d5  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x462da  ret
0x462db  ldarg.0
0x462dc  ldc.i4.s 0x4C
0x462de  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x462e3  brfalse.s loc_46305
0x462e5  ldloc.1
0x462e6  ldloc.0
0x462e7  bne.un.s loc_46305
0x462e9  ldarg.0
0x462ea  ldc.i4.s 0x4C
0x462ec  ldarg.1
0x462ed  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x462f2  brfalse.s loc_46305
0x462f4  ldarg.0
0x462f5  ldc.i4.s 0x4C
0x462f7  ldarg.1
0x462f8  ldloc.0
0x462f9  ldc.i4.0
0x462fa  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x462ff  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x46304  ret
0x46305  ldarg.0
0x46306  ldc.i4.s 0x7E
0x46308  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x4630d  brfalse.s loc_4637D
0x4630f  ldloc.0
0x46310  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x46315  ldc.i4.s 0xE
0x46317  bne.un.s loc_4637D
0x46319  ldloc.0
0x4631a  ldc.i4.0
0x4631b  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x46320  stloc.s  4
0x46322  ldloc.s  4
0x46324  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x46329  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsSingleton()
0x4632e  brfalse.s loc_4637D
0x46330  ldloc.1
0x46331  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x46336  ldc.i4.s 0x55
0x46338  bne.un.s loc_4637D
0x4633a  ldloc.1
0x4633b  ldc.i4.0
0x4633c  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x46341  stloc.s  5
0x46343  ldarg.0
0x46344  ldc.i4.s 0x7E
0x46346  ldarg.1
0x46347  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x4634c  brfalse.s loc_4637D
0x4634e  ldarg.0
0x4634f  ldc.i4.s 0x7E
0x46351  ldarg.1
0x46352  ldarg.0
0x46353  ldarg.0
0x46354  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x46359  ldarg.0
0x4635a  ldarg.0
0x4635b  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x46360  ldloc.0
0x46361  ldloc.s  5
0x46363  callvirt instance class System.Xml.Xsl.Qil.QilLoop System.Xml.Xsl.Qil.QilFactory::Loop(class System.Xml.Xsl.Qil.QilNode variable, class System.Xml.Xsl.Qil.QilNode body)
0x46368  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitLoop(class System.Xml.Xsl.Qil.QilLoop n)
0x4636d  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::TextCtor(class System.Xml.Xsl.Qil.QilNode child)
0x46372  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitTextCtor(class System.Xml.Xsl.Qil.QilUnary n)
0x46377  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x4637c  ret
0x4637d  ldarg.0
0x4637e  ldc.i4.s 0x49
0x46380  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x46385  brfalse.s loc_463E7
0x46387  ldloc.0
0x46388  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x4638d  ldc.i4.s 0xF
0x4638f  beq.s    loc_463A4
0x46391  ldloc.0
0x46392  ldc.i4.0
0x46393  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x46398  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4639d  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsSingleton()
0x463a2  brfalse.s loc_463E7
0x463a4  ldloc.0
0x463a5  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Read(class System.Xml.Xsl.Qil.QilNode nd)
0x463aa  ldc.i4.s 0xE
0x463ac  callvirt instance bool System.Xml.Xsl.IlGen.OptimizerPatterns::MatchesPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x463b1  brtrue.s loc_463E7
0x463b3  ldarg.0
0x463b4  ldfld    class NodeCounter System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::nodeCounter
0x463b9  ldloc.1
0x463ba  ldloc.0
0x463bb  callvirt instance int32 NodeCounter::Count(class System.Xml.Xsl.Qil.QilNode expr, class System.Xml.Xsl.Qil.QilNode target)
0x463c0  ldc.i4.1
0x463c1  bgt.s    loc_463E7
0x463c3  ldarg.0
0x463c4  ldc.i4.s 0x49
0x463c6  ldarg.1
0x463c7  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x463cc  brfalse.s loc_463E7
0x463ce  ldarg.0
0x463cf  ldc.i4.s 0x49
0x463d1  ldarg.1
0x463d2  ldarg.0
0x463d3  ldloc.1
0x463d4  ldloc.0
0x463d5  ldloc.0
0x463d6  ldc.i4.0
0x463d7  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x463dc  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Subs(class System.Xml.Xsl.Qil.QilNode expr, class System.Xml.Xsl.Qil.QilNode refOld, class System.Xml.Xsl.Qil.QilNode refNew)
0x463e1  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x463e6  ret
0x463e7  ldarg.0
0x463e8  ldc.i4.s 0x7B
0x463ea  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x463ef  brfalse.s loc_46469
0x463f1  ldloc.1
0x463f2  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x463f7  ldc.i4.s 0x1F
0x463f9  bne.un.s loc_46469
0x463fb  ldloc.1
0x463fc  ldc.i4.0
0x463fd  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x46402  stloc.s  6
0x46404  ldloc.1
0x46405  ldc.i4.1
0x46406  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x4640b  stloc.s  7
0x4640d  ldloc.1
0x4640e  ldc.i4.2
0x4640f  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x46414  stloc.s  8
0x46416  ldloc.s  7
0x46418  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x4641d  ldc.i4.s 0x22
0x4641f  bne.un.s loc_46469
0x46421  ldloc.s  7
0x46423  callvirt instance int32 System.Xml.Xsl.Qil.QilNode::get_Count()
0x46428  brtrue.s loc_46469
0x4642a  ldloc.s  8
0x4642c  ldloc.0
0x4642d  bne.un.s loc_46469
0x4642f  ldarg.0
0x46430  ldc.i4.s 0x7B
0x46432  ldarg.1
0x46433  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x46438  brfalse.s loc_46469
0x4643a  ldarg.0
0x4643b  ldc.i4.s 0x7B
0x4643d  ldarg.1
0x4643e  ldarg.0
0x4643f  ldarg.0
0x46440  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x46445  ldloc.0
0x46446  ldarg.0
0x46447  ldarg.0
0x46448  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x4644d  ldloc.s  6
0x4644f  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::Not(class System.Xml.Xsl.Qil.QilNode child)
0x46454  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNot(class System.Xml.Xsl.Qil.QilUnary n)
0x46459  callvirt instance class System.Xml.Xsl.Qil.QilLoop System.Xml.Xsl.Qil.QilFactory::Filter(class System.Xml.Xsl.Qil.QilNode variable, class System.Xml.Xsl.Qil.QilNode body)
0x4645e  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitFilter(class System.Xml.Xsl.Qil.QilLoop n)
0x46463  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x46468  ret
0x46469  ldarg.0
0x4646a  ldc.i4.s 0x7B
0x4646c  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x46471  brfalse.s loc_464DA
  ... truncated ...
```
