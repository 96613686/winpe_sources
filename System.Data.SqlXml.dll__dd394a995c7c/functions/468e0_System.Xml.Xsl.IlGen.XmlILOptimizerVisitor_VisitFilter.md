# System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::VisitFilter

- ea: `0x468e0`
- end: `0x4706f`
- name: `System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::VisitFilter`
- size: `1935`
- prototype: ``
- caller_count: `0`
- callee_count: `35`
- tags: `registry_config`

## callees

- `0x2320`
- `0x36190`
- `0x361f0`
- `0x36450`
- `0x364b0`
- `0x367f0`
- `0x36810`
- `0x36900`
- `0x37390`
- `0x376a0`
- `0x376c0`
- `0x37750`
- `0x38590`
- `0x3aef0`
- `0x3af20`
- `0x3b060`
- `0x3b090`
- `0x3b230`
- `0x3b240`
- `0x3b2c0`
- `0x409c0`
- `0x40a90`
- `0x40af0`
- `0x40bd0`
- `0x40c40`
- `0x40c60`
- `0x42c20`
- `0x42c30`
- `0x468e0`
- `0x49720`
- `0x49730`
- `0x49740`
- `0x49750`
- `0x49840`
- `0x4a190`

## pseudocode

```c

```

## disassembly

```asm
0x468e0  ldarg.1
0x468e1  ldc.i4.0
0x468e2  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x468e7  stloc.0
0x468e8  ldarg.1
0x468e9  ldc.i4.1
0x468ea  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x468ef  stloc.1
0x468f0  ldarg.0
0x468f1  ldc.i4.s 0x68
0x468f3  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x468f8  brfalse.s loc_46934
0x468fa  ldloc.0
0x468fb  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x46900  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::None
0x46905  bne.un.s loc_46934
0x46907  ldarg.0
0x46908  ldc.i4.s 0x68
0x4690a  ldarg.1
0x4690b  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x46910  brfalse.s loc_46934
0x46912  ldarg.0
0x46913  ldc.i4.s 0x68
0x46915  ldarg.1
0x46916  ldarg.0
0x46917  ldarg.0
0x46918  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x4691d  ldloc.0
0x4691e  ldc.i4.0
0x4691f  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x46924  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::Nop(class System.Xml.Xsl.Qil.QilNode child)
0x46929  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNop(class System.Xml.Xsl.Qil.QilUnary n)
0x4692e  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x46933  ret
0x46934  ldarg.0
0x46935  ldc.i4.s 0x68
0x46937  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x4693c  brfalse.s loc_46973
0x4693e  ldloc.1
0x4693f  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x46944  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::None
0x46949  bne.un.s loc_46973
0x4694b  ldarg.0
0x4694c  ldc.i4.s 0x68
0x4694e  ldarg.1
0x4694f  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x46954  brfalse.s loc_46973
0x46956  ldarg.0
0x46957  ldc.i4.s 0x68
0x46959  ldarg.1
0x4695a  ldarg.0
0x4695b  ldarg.0
0x4695c  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x46961  ldloc.0
0x46962  ldloc.1
0x46963  callvirt instance class System.Xml.Xsl.Qil.QilLoop System.Xml.Xsl.Qil.QilFactory::Loop(class System.Xml.Xsl.Qil.QilNode variable, class System.Xml.Xsl.Qil.QilNode body)
0x46968  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitLoop(class System.Xml.Xsl.Qil.QilLoop n)
0x4696d  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x46972  ret
0x46973  ldarg.0
0x46974  ldc.i4.s 0x41
0x46976  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x4697b  brfalse.s loc_469BC
0x4697d  ldloc.0
0x4697e  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Read(class System.Xml.Xsl.Qil.QilNode nd)
0x46983  ldc.i4.s 0xE
0x46985  callvirt instance bool System.Xml.Xsl.IlGen.OptimizerPatterns::MatchesPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x4698a  brtrue.s loc_469BC
0x4698c  ldloc.1
0x4698d  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x46992  ldc.i4.s 0x13
0x46994  bne.un.s loc_469BC
0x46996  ldarg.0
0x46997  ldc.i4.s 0x41
0x46999  ldarg.1
0x4699a  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x4699f  brfalse.s loc_469BC
0x469a1  ldarg.0
0x469a2  ldc.i4.s 0x41
0x469a4  ldarg.1
0x469a5  ldarg.0
0x469a6  ldarg.0
0x469a7  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x469ac  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilFactory::Sequence()
0x469b1  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitSequence(class System.Xml.Xsl.Qil.QilList n)
0x469b6  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x469bb  ret
0x469bc  ldarg.0
0x469bd  ldc.i4.s 0x41
0x469bf  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x469c4  brfalse.s loc_469EC
0x469c6  ldloc.1
0x469c7  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x469cc  ldc.i4.s 0x12
0x469ce  bne.un.s loc_469EC
0x469d0  ldarg.0
0x469d1  ldc.i4.s 0x41
0x469d3  ldarg.1
0x469d4  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x469d9  brfalse.s loc_469EC
0x469db  ldarg.0
0x469dc  ldc.i4.s 0x41
0x469de  ldarg.1
0x469df  ldloc.0
0x469e0  ldc.i4.0
0x469e1  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x469e6  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x469eb  ret
0x469ec  ldarg.0
0x469ed  ldc.i4.s 0x6E
0x469ef  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x469f4  brfalse  loc_46B08
0x469f9  ldloc.0
0x469fa  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x469ff  ldc.i4.s 0xE
0x46a01  bne.un   loc_46B08
0x46a06  ldloc.0
0x46a07  ldc.i4.0
0x46a08  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x46a0d  stloc.2
0x46a0e  ldloc.2
0x46a0f  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x46a14  ldc.i4.s 0x43
0x46a16  bne.un   loc_46B08
0x46a1b  ldloc.2
0x46a1c  ldc.i4.0
0x46a1d  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x46a22  stloc.3
0x46a23  ldloc.1
0x46a24  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x46a29  ldc.i4.s 0x1C
0x46a2b  bne.un   loc_46B08
0x46a30  ldloc.1
0x46a31  ldc.i4.0
0x46a32  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x46a37  stloc.s  4
0x46a39  ldloc.1
0x46a3a  ldc.i4.1
0x46a3b  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x46a40  stloc.s  5
0x46a42  ldloc.s  4
0x46a44  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x46a49  ldc.i4.s 0x5F
0x46a4b  bne.un   loc_46B08
0x46a50  ldloc.s  4
0x46a52  ldc.i4.0
0x46a53  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x46a58  stloc.s  6
0x46a5a  ldloc.s  4
0x46a5c  ldc.i4.1
0x46a5d  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x46a62  stloc.s  7
0x46a64  ldloc.s  6
0x46a66  ldloc.0
0x46a67  bne.un   loc_46B08
0x46a6c  ldloc.s  7
0x46a6e  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x46a73  ldc.i4.s 0x1A
0x46a75  bne.un   loc_46B08
0x46a7a  ldloc.s  7
0x46a7c  castclass System.Xml.Xsl.Qil.QilLiteral
0x46a81  callvirt instance object System.Xml.Xsl.Qil.QilLiteral::get_Value()
0x46a86  castclass System.Xml.Xsl.XmlQueryType
0x46a8b  stloc.s  8
0x46a8d  ldloc.s  8
0x46a8f  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::Attribute
0x46a94  call     bool System.Xml.Xsl.XmlQueryType::op_Equality(class System.Xml.Xsl.XmlQueryType left, class System.Xml.Xsl.XmlQueryType right)
0x46a99  brfalse.s loc_46B08
0x46a9b  ldloc.s  5
0x46a9d  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x46aa2  ldc.i4.s 0x34
0x46aa4  bne.un.s loc_46B08
0x46aa6  ldloc.s  5
0x46aa8  ldc.i4.0
0x46aa9  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x46aae  stloc.s  9
0x46ab0  ldloc.s  5
0x46ab2  ldc.i4.1
0x46ab3  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x46ab8  stloc.s  0xA
0x46aba  ldloc.s  9
0x46abc  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x46ac1  ldc.i4.s 0x5A
0x46ac3  bne.un.s loc_46B08
0x46ac5  ldloc.s  9
0x46ac7  ldc.i4.0
0x46ac8  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x46acd  stloc.s  0xB
0x46acf  ldloc.s  0xB
0x46ad1  ldloc.0
0x46ad2  bne.un.s loc_46B08
0x46ad4  ldloc.s  0xA
0x46ad6  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x46adb  ldc.i4.s 0x19
0x46add  bne.un.s loc_46B08
0x46adf  ldarg.0
0x46ae0  ldc.i4.s 0x6E
0x46ae2  ldarg.1
0x46ae3  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x46ae8  brfalse.s loc_46B08
0x46aea  ldarg.0
0x46aeb  ldc.i4.s 0x6E
0x46aed  ldarg.1
0x46aee  ldarg.0
0x46aef  ldarg.0
0x46af0  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x46af5  ldloc.3
0x46af6  ldloc.s  0xA
0x46af8  callvirt instance class System.Xml.Xsl.Qil.QilBinary System.Xml.Xsl.Qil.QilFactory::Attribute(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x46afd  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitAttribute(class System.Xml.Xsl.Qil.QilBinary n)
0x46b02  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x46b07  ret
0x46b08  ldarg.0
0x46b09  ldc.i4.s 0x36
0x46b0b  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x46b10  brfalse  loc_46BBB
0x46b15  ldloc.0
0x46b16  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x46b1b  ldc.i4.s 0xE
0x46b1d  bne.un   loc_46BBB
0x46b22  ldloc.0
0x46b23  ldc.i4.0
0x46b24  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x46b29  stloc.s  0xC
0x46b2b  ldloc.s  0xC
0x46b2d  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x46b32  ldc.i4.s 0x3C
0x46b34  bne.un   loc_46BBB
0x46b39  ldloc.s  0xC
0x46b3b  ldc.i4.0
0x46b3c  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x46b41  stloc.s  0xD
0x46b43  ldloc.s  0xC
0x46b45  ldc.i4.1
0x46b46  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x46b4b  stloc.s  0xE
0x46b4d  ldarg.0
0x46b4e  ldloc.1
0x46b4f  ldloc.0
0x46b50  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::NonPositional(class System.Xml.Xsl.Qil.QilNode expr, class System.Xml.Xsl.Qil.QilNode iter)
0x46b55  brfalse.s loc_46BBB
0x46b57  ldarg.0
0x46b58  ldloc.s  0xC
0x46b5a  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsDocOrderDistinct(class System.Xml.Xsl.Qil.QilNode nd)
0x46b5f  brtrue.s loc_46BBB
0x46b61  ldarg.0
0x46b62  ldc.i4.s 0x36
0x46b64  ldarg.1
0x46b65  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x46b6a  brfalse.s loc_46BBB
0x46b6c  ldarg.0
0x46b6d  ldarg.0
0x46b6e  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x46b73  ldloc.s  0xE
0x46b75  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilFactory::For(class System.Xml.Xsl.Qil.QilNode binding)
0x46b7a  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitFor(class System.Xml.Xsl.Qil.QilIterator n)
0x46b7f  stloc.s  0xF
0x46b81  ldarg.0
0x46b82  ldc.i4.s 0x36
0x46b84  ldarg.1
0x46b85  ldarg.0
0x46b86  ldarg.0
0x46b87  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x46b8c  ldloc.s  0xD
0x46b8e  ldarg.0
0x46b8f  ldarg.0
0x46b90  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x46b95  ldloc.s  0xF
0x46b97  ldarg.0
0x46b98  ldloc.1
0x46b99  ldloc.0
0x46b9a  ldloc.s  0xF
0x46b9c  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Subs(class System.Xml.Xsl.Qil.QilNode expr, class System.Xml.Xsl.Qil.QilNode refOld, class System.Xml.Xsl.Qil.QilNode refNew)
0x46ba1  callvirt instance class System.Xml.Xsl.Qil.QilLoop System.Xml.Xsl.Qil.QilFactory::Filter(class System.Xml.Xsl.Qil.QilNode variable, class System.Xml.Xsl.Qil.QilNode body)
0x46ba6  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitFilter(class System.Xml.Xsl.Qil.QilLoop n)
0x46bab  callvirt instance class System.Xml.Xsl.Qil.QilLoop System.Xml.Xsl.Qil.QilFactory::Loop(class System.Xml.Xsl.Qil.QilNode variable, class System.Xml.Xsl.Qil.QilNode body)
0x46bb0  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitLoop(class System.Xml.Xsl.Qil.QilLoop n)
0x46bb5  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x46bba  ret
0x46bbb  ldarg.0
0x46bbc  ldc.i4.s 0x7C
0x46bbe  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x46bc3  brfalse.s loc_46C3B
0x46bc5  ldloc.0
0x46bc6  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Read(class System.Xml.Xsl.Qil.QilNode nd)
0x46bcb  ldc.i4.s 0xE
0x46bcd  callvirt instance bool System.Xml.Xsl.IlGen.OptimizerPatterns::MatchesPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x46bd2  brtrue.s loc_46C3B
0x46bd4  ldloc.0
0x46bd5  ldc.i4.0
0x46bd6  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x46bdb  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x46be0  ldc.i4.8
0x46be1  beq.s    loc_46C3B
0x46be3  ldarg.0
0x46be4  ldloc.1
0x46be5  ldloc.0
0x46be6  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::DependsOn(class System.Xml.Xsl.Qil.QilNode expr, class System.Xml.Xsl.Qil.QilNode target)
0x46beb  brtrue.s loc_46C3B
0x46bed  ldloc.1
  ... truncated ...
```
