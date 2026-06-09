# System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::VisitIsType

- ea: `0x48eb0`
- end: `0x4915c`
- name: `System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::VisitIsType`
- size: `684`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: `registry_config`

## callees

- `0x1ff0`
- `0x2030`
- `0x2110`
- `0x36190`
- `0x36210`
- `0x36270`
- `0x36290`
- `0x367f0`
- `0x36c80`
- `0x37390`
- `0x376a0`
- `0x376c0`
- `0x37750`
- `0x38590`
- `0x3aef0`
- `0x3af40`
- `0x3af90`
- `0x3afa0`
- `0x3b230`
- `0x3b480`
- `0x409c0`
- `0x40c60`
- `0x42c20`
- `0x42c30`
- `0x48eb0`
- `0x49720`

## pseudocode

```c

```

## disassembly

```asm
0x48eb0  ldarg.1
0x48eb1  ldc.i4.0
0x48eb2  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x48eb7  stloc.0
0x48eb8  ldarg.1
0x48eb9  ldc.i4.1
0x48eba  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x48ebf  stloc.1
0x48ec0  ldarg.0
0x48ec1  ldc.i4.s 0x68
0x48ec3  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x48ec8  brfalse.s loc_48EFE
0x48eca  ldloc.0
0x48ecb  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x48ed0  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::None
0x48ed5  bne.un.s loc_48EFE
0x48ed7  ldarg.0
0x48ed8  ldc.i4.s 0x68
0x48eda  ldarg.1
0x48edb  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x48ee0  brfalse.s loc_48EFE
0x48ee2  ldarg.0
0x48ee3  ldc.i4.s 0x68
0x48ee5  ldarg.1
0x48ee6  ldarg.0
0x48ee7  ldarg.0
0x48ee8  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x48eed  ldloc.0
0x48eee  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::Nop(class System.Xml.Xsl.Qil.QilNode child)
0x48ef3  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNop(class System.Xml.Xsl.Qil.QilUnary n)
0x48ef8  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x48efd  ret
0x48efe  ldarg.0
0x48eff  ldc.i4.s 0x47
0x48f01  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x48f06  brfalse.s loc_48F66
0x48f08  ldloc.0
0x48f09  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Read(class System.Xml.Xsl.Qil.QilNode nd)
0x48f0e  ldc.i4.s 0xE
0x48f10  callvirt instance bool System.Xml.Xsl.IlGen.OptimizerPatterns::MatchesPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x48f15  brtrue.s loc_48F66
0x48f17  ldloc.1
0x48f18  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x48f1d  ldc.i4.s 0x1A
0x48f1f  bne.un.s loc_48F66
0x48f21  ldloc.1
0x48f22  castclass System.Xml.Xsl.Qil.QilLiteral
0x48f27  callvirt instance object System.Xml.Xsl.Qil.QilLiteral::get_Value()
0x48f2c  castclass System.Xml.Xsl.XmlQueryType
0x48f31  stloc.2
0x48f32  ldloc.0
0x48f33  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x48f38  ldloc.2
0x48f39  callvirt instance bool System.Xml.Xsl.XmlQueryType::IsSubtypeOf(class System.Xml.Xsl.XmlQueryType baseType)
0x48f3e  brfalse.s loc_48F66
0x48f40  ldarg.0
0x48f41  ldc.i4.s 0x47
0x48f43  ldarg.1
0x48f44  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x48f49  brfalse.s loc_48F66
0x48f4b  ldarg.0
0x48f4c  ldc.i4.s 0x47
0x48f4e  ldarg.1
0x48f4f  ldarg.0
0x48f50  ldarg.0
0x48f51  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x48f56  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilFactory::True()
0x48f5b  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitTrue(class System.Xml.Xsl.Qil.QilNode n)
0x48f60  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x48f65  ret
0x48f66  ldarg.0
0x48f67  ldc.i4.s 0x47
0x48f69  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x48f6e  brfalse.s loc_48FCE
0x48f70  ldloc.0
0x48f71  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Read(class System.Xml.Xsl.Qil.QilNode nd)
0x48f76  ldc.i4.s 0xE
0x48f78  callvirt instance bool System.Xml.Xsl.IlGen.OptimizerPatterns::MatchesPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x48f7d  brtrue.s loc_48FCE
0x48f7f  ldloc.1
0x48f80  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x48f85  ldc.i4.s 0x1A
0x48f87  bne.un.s loc_48FCE
0x48f89  ldloc.1
0x48f8a  castclass System.Xml.Xsl.Qil.QilLiteral
0x48f8f  callvirt instance object System.Xml.Xsl.Qil.QilLiteral::get_Value()
0x48f94  castclass System.Xml.Xsl.XmlQueryType
0x48f99  stloc.3
0x48f9a  ldloc.0
0x48f9b  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x48fa0  ldloc.3
0x48fa1  callvirt instance bool System.Xml.Xsl.XmlQueryType::NeverSubtypeOf(class System.Xml.Xsl.XmlQueryType baseType)
0x48fa6  brfalse.s loc_48FCE
0x48fa8  ldarg.0
0x48fa9  ldc.i4.s 0x47
0x48fab  ldarg.1
0x48fac  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x48fb1  brfalse.s loc_48FCE
0x48fb3  ldarg.0
0x48fb4  ldc.i4.s 0x47
0x48fb6  ldarg.1
0x48fb7  ldarg.0
0x48fb8  ldarg.0
0x48fb9  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x48fbe  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilFactory::False()
0x48fc3  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitFalse(class System.Xml.Xsl.Qil.QilNode n)
0x48fc8  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x48fcd  ret
0x48fce  ldarg.0
0x48fcf  ldc.i4.s 0x47
0x48fd1  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x48fd6  brfalse.s loc_49034
0x48fd8  ldloc.1
0x48fd9  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x48fde  ldc.i4.s 0x1A
0x48fe0  bne.un.s loc_49034
0x48fe2  ldloc.1
0x48fe3  castclass System.Xml.Xsl.Qil.QilLiteral
0x48fe8  callvirt instance object System.Xml.Xsl.Qil.QilLiteral::get_Value()
0x48fed  castclass System.Xml.Xsl.XmlQueryType
0x48ff2  stloc.s  4
0x48ff4  ldloc.0
0x48ff5  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x48ffa  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryType::get_Prime()
0x48fff  ldloc.s  4
0x49001  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryType::get_Prime()
0x49006  callvirt instance bool System.Xml.Xsl.XmlQueryType::NeverSubtypeOf(class System.Xml.Xsl.XmlQueryType baseType)
0x4900b  brfalse.s loc_49034
0x4900d  ldarg.0
0x4900e  ldc.i4.s 0x47
0x49010  ldarg.1
0x49011  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x49016  brfalse.s loc_49034
0x49018  ldarg.0
0x49019  ldc.i4.s 0x47
0x4901b  ldarg.1
0x4901c  ldarg.0
0x4901d  ldarg.0
0x4901e  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x49023  ldloc.0
0x49024  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::IsEmpty(class System.Xml.Xsl.Qil.QilNode child)
0x49029  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitIsEmpty(class System.Xml.Xsl.Qil.QilUnary n)
0x4902e  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x49033  ret
0x49034  ldarg.0
0x49035  ldc.i4.s 0x47
0x49037  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x4903c  brfalse  loc_490C4
0x49041  ldloc.0
0x49042  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Read(class System.Xml.Xsl.Qil.QilNode nd)
0x49047  ldc.i4.s 0xE
0x49049  callvirt instance bool System.Xml.Xsl.IlGen.OptimizerPatterns::MatchesPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x4904e  brfalse.s loc_490C4
0x49050  ldloc.1
0x49051  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x49056  ldc.i4.s 0x1A
0x49058  bne.un.s loc_490C4
0x4905a  ldloc.1
0x4905b  castclass System.Xml.Xsl.Qil.QilLiteral
0x49060  callvirt instance object System.Xml.Xsl.Qil.QilLiteral::get_Value()
0x49065  castclass System.Xml.Xsl.XmlQueryType
0x4906a  stloc.s  5
0x4906c  ldloc.0
0x4906d  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x49072  ldloc.s  5
0x49074  callvirt instance bool System.Xml.Xsl.XmlQueryType::IsSubtypeOf(class System.Xml.Xsl.XmlQueryType baseType)
0x49079  brfalse.s loc_490C4
0x4907b  ldarg.0
0x4907c  ldc.i4.s 0x47
0x4907e  ldarg.1
0x4907f  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x49084  brfalse.s loc_490C4
0x49086  ldarg.0
0x49087  ldc.i4.s 0x47
0x49089  ldarg.1
0x4908a  ldarg.0
0x4908b  ldarg.0
0x4908c  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x49091  ldarg.0
0x49092  ldarg.0
0x49093  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x49098  ldloc.0
0x49099  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilFactory::Let(class System.Xml.Xsl.Qil.QilNode binding)
0x4909e  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitLet(class System.Xml.Xsl.Qil.QilIterator n)
0x490a3  ldarg.0
0x490a4  ldarg.0
0x490a5  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x490aa  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilFactory::True()
0x490af  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitTrue(class System.Xml.Xsl.Qil.QilNode n)
0x490b4  callvirt instance class System.Xml.Xsl.Qil.QilLoop System.Xml.Xsl.Qil.QilFactory::Loop(class System.Xml.Xsl.Qil.QilNode variable, class System.Xml.Xsl.Qil.QilNode body)
0x490b9  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitLoop(class System.Xml.Xsl.Qil.QilLoop n)
0x490be  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x490c3  ret
0x490c4  ldarg.0
0x490c5  ldc.i4.s 0x47
0x490c7  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x490cc  brfalse  loc_49154
0x490d1  ldloc.0
0x490d2  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Read(class System.Xml.Xsl.Qil.QilNode nd)
0x490d7  ldc.i4.s 0xE
0x490d9  callvirt instance bool System.Xml.Xsl.IlGen.OptimizerPatterns::MatchesPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x490de  brfalse.s loc_49154
0x490e0  ldloc.1
0x490e1  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x490e6  ldc.i4.s 0x1A
0x490e8  bne.un.s loc_49154
0x490ea  ldloc.1
0x490eb  castclass System.Xml.Xsl.Qil.QilLiteral
0x490f0  callvirt instance object System.Xml.Xsl.Qil.QilLiteral::get_Value()
0x490f5  castclass System.Xml.Xsl.XmlQueryType
0x490fa  stloc.s  6
0x490fc  ldloc.0
0x490fd  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x49102  ldloc.s  6
0x49104  callvirt instance bool System.Xml.Xsl.XmlQueryType::NeverSubtypeOf(class System.Xml.Xsl.XmlQueryType baseType)
0x49109  brfalse.s loc_49154
0x4910b  ldarg.0
0x4910c  ldc.i4.s 0x47
0x4910e  ldarg.1
0x4910f  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x49114  brfalse.s loc_49154
0x49116  ldarg.0
0x49117  ldc.i4.s 0x47
0x49119  ldarg.1
0x4911a  ldarg.0
0x4911b  ldarg.0
0x4911c  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x49121  ldarg.0
0x49122  ldarg.0
0x49123  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x49128  ldloc.0
0x49129  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilFactory::Let(class System.Xml.Xsl.Qil.QilNode binding)
0x4912e  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitLet(class System.Xml.Xsl.Qil.QilIterator n)
0x49133  ldarg.0
0x49134  ldarg.0
0x49135  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x4913a  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilFactory::False()
0x4913f  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitFalse(class System.Xml.Xsl.Qil.QilNode n)
0x49144  callvirt instance class System.Xml.Xsl.Qil.QilLoop System.Xml.Xsl.Qil.QilFactory::Loop(class System.Xml.Xsl.Qil.QilNode variable, class System.Xml.Xsl.Qil.QilNode body)
0x49149  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitLoop(class System.Xml.Xsl.Qil.QilLoop n)
0x4914e  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x49153  ret
0x49154  ldarg.0
0x49155  ldarg.1
0x49156  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternVisitor::NoReplace(class System.Xml.Xsl.Qil.QilNode node)
0x4915b  ret
```
