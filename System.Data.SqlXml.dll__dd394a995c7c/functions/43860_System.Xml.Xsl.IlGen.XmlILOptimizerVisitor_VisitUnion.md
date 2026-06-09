# System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::VisitUnion

- ea: `0x43860`
- end: `0x43af3`
- name: `System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::VisitUnion`
- size: `659`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config`

## callees

- `0x36190`
- `0x364d0`
- `0x36870`
- `0x376a0`
- `0x376c0`
- `0x37740`
- `0x37750`
- `0x38590`
- `0x3aef0`
- `0x3b0a0`
- `0x3b270`
- `0x409c0`
- `0x40a90`
- `0x40c00`
- `0x40c40`
- `0x42c20`
- `0x42c30`
- `0x43860`
- `0x49720`
- `0x4a170`
- `0x4a190`
- `0x4a1a0`

## pseudocode

```c

```

## disassembly

```asm
0x43860  ldarg.1
0x43861  ldc.i4.0
0x43862  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x43867  stloc.0
0x43868  ldarg.1
0x43869  ldc.i4.1
0x4386a  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x4386f  stloc.1
0x43870  ldarg.0
0x43871  ldc.i4.s 0x68
0x43873  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x43878  brfalse.s loc_438AE
0x4387a  ldloc.0
0x4387b  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x43880  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::None
0x43885  bne.un.s loc_438AE
0x43887  ldarg.0
0x43888  ldc.i4.s 0x68
0x4388a  ldarg.1
0x4388b  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x43890  brfalse.s loc_438AE
0x43892  ldarg.0
0x43893  ldc.i4.s 0x68
0x43895  ldarg.1
0x43896  ldarg.0
0x43897  ldarg.0
0x43898  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x4389d  ldloc.0
0x4389e  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::Nop(class System.Xml.Xsl.Qil.QilNode child)
0x438a3  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNop(class System.Xml.Xsl.Qil.QilUnary n)
0x438a8  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x438ad  ret
0x438ae  ldarg.0
0x438af  ldc.i4.s 0x68
0x438b1  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x438b6  brfalse.s loc_438EC
0x438b8  ldloc.1
0x438b9  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x438be  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::None
0x438c3  bne.un.s loc_438EC
0x438c5  ldarg.0
0x438c6  ldc.i4.s 0x68
0x438c8  ldarg.1
0x438c9  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x438ce  brfalse.s loc_438EC
0x438d0  ldarg.0
0x438d1  ldc.i4.s 0x68
0x438d3  ldarg.1
0x438d4  ldarg.0
0x438d5  ldarg.0
0x438d6  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x438db  ldloc.1
0x438dc  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::Nop(class System.Xml.Xsl.Qil.QilNode child)
0x438e1  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNop(class System.Xml.Xsl.Qil.QilUnary n)
0x438e6  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x438eb  ret
0x438ec  ldarg.0
0x438ed  ldc.i4.s 0x63
0x438ef  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x438f4  brfalse.s loc_43921
0x438f6  ldloc.1
0x438f7  ldloc.0
0x438f8  bne.un.s loc_43921
0x438fa  ldarg.0
0x438fb  ldc.i4.s 0x63
0x438fd  ldarg.1
0x438fe  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x43903  brfalse.s loc_43921
0x43905  ldarg.0
0x43906  ldc.i4.s 0x63
0x43908  ldarg.1
0x43909  ldarg.0
0x4390a  ldarg.0
0x4390b  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x43910  ldloc.0
0x43911  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::DocOrderDistinct(class System.Xml.Xsl.Qil.QilNode child)
0x43916  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitDocOrderDistinct(class System.Xml.Xsl.Qil.QilUnary n)
0x4391b  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x43920  ret
0x43921  ldarg.0
0x43922  ldc.i4.s 0x63
0x43924  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x43929  brfalse.s loc_43964
0x4392b  ldloc.0
0x4392c  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x43931  ldc.i4.s 0x22
0x43933  bne.un.s loc_43964
0x43935  ldloc.0
0x43936  callvirt instance int32 System.Xml.Xsl.Qil.QilNode::get_Count()
0x4393b  brtrue.s loc_43964
0x4393d  ldarg.0
0x4393e  ldc.i4.s 0x63
0x43940  ldarg.1
0x43941  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x43946  brfalse.s loc_43964
0x43948  ldarg.0
0x43949  ldc.i4.s 0x63
0x4394b  ldarg.1
0x4394c  ldarg.0
0x4394d  ldarg.0
0x4394e  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x43953  ldloc.1
0x43954  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::DocOrderDistinct(class System.Xml.Xsl.Qil.QilNode child)
0x43959  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitDocOrderDistinct(class System.Xml.Xsl.Qil.QilUnary n)
0x4395e  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x43963  ret
0x43964  ldarg.0
0x43965  ldc.i4.s 0x63
0x43967  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x4396c  brfalse.s loc_439A7
0x4396e  ldloc.1
0x4396f  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x43974  ldc.i4.s 0x22
0x43976  bne.un.s loc_439A7
0x43978  ldloc.1
0x43979  callvirt instance int32 System.Xml.Xsl.Qil.QilNode::get_Count()
0x4397e  brtrue.s loc_439A7
0x43980  ldarg.0
0x43981  ldc.i4.s 0x63
0x43983  ldarg.1
0x43984  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x43989  brfalse.s loc_439A7
0x4398b  ldarg.0
0x4398c  ldc.i4.s 0x63
0x4398e  ldarg.1
0x4398f  ldarg.0
0x43990  ldarg.0
0x43991  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x43996  ldloc.0
0x43997  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::DocOrderDistinct(class System.Xml.Xsl.Qil.QilNode child)
0x4399c  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitDocOrderDistinct(class System.Xml.Xsl.Qil.QilUnary n)
0x439a1  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x439a6  ret
0x439a7  ldarg.0
0x439a8  ldc.i4.s 0x63
0x439aa  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x439af  brfalse.s loc_439DB
0x439b1  ldloc.0
0x439b2  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x439b7  ldc.i4.s 0x47
0x439b9  bne.un.s loc_439DB
0x439bb  ldloc.1
0x439bc  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x439c1  ldc.i4.s 0x47
0x439c3  bne.un.s loc_439DB
0x439c5  ldarg.0
0x439c6  ldc.i4.s 0x63
0x439c8  ldarg.1
0x439c9  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x439ce  brfalse.s loc_439DB
0x439d0  ldarg.0
0x439d1  ldc.i4.s 0x63
0x439d3  ldarg.1
0x439d4  ldloc.0
0x439d5  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x439da  ret
0x439db  ldarg.0
0x439dc  ldc.i4   0x86
0x439e1  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x439e6  brfalse.s loc_43A4A
0x439e8  ldarg.0
0x439e9  ldloc.0
0x439ea  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsDocOrderDistinct(class System.Xml.Xsl.Qil.QilNode nd)
0x439ef  brfalse.s loc_439FA
0x439f1  ldarg.0
0x439f2  ldloc.1
0x439f3  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsDocOrderDistinct(class System.Xml.Xsl.Qil.QilNode nd)
0x439f8  brtrue.s loc_43A4A
0x439fa  ldarg.0
0x439fb  ldc.i4   0x86
0x43a00  ldarg.1
0x43a01  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x43a06  brfalse.s loc_43A4A
0x43a08  ldarg.0
0x43a09  ldc.i4   0x86
0x43a0e  ldarg.1
0x43a0f  ldarg.0
0x43a10  ldarg.0
0x43a11  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x43a16  ldarg.0
0x43a17  ldarg.0
0x43a18  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x43a1d  ldloc.0
0x43a1e  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::DocOrderDistinct(class System.Xml.Xsl.Qil.QilNode child)
0x43a23  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitDocOrderDistinct(class System.Xml.Xsl.Qil.QilUnary n)
0x43a28  ldarg.0
0x43a29  ldarg.0
0x43a2a  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x43a2f  ldloc.1
0x43a30  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::DocOrderDistinct(class System.Xml.Xsl.Qil.QilNode child)
0x43a35  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitDocOrderDistinct(class System.Xml.Xsl.Qil.QilUnary n)
0x43a3a  callvirt instance class System.Xml.Xsl.Qil.QilBinary System.Xml.Xsl.Qil.QilFactory::Union(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x43a3f  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitUnion(class System.Xml.Xsl.Qil.QilBinary n)
0x43a44  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x43a49  ret
0x43a4a  ldarg.0
0x43a4b  ldc.i4.s 0x31
0x43a4d  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x43a52  brfalse.s loc_43A6B
0x43a54  ldarg.0
0x43a55  ldc.i4.s 0x31
0x43a57  ldarg.1
0x43a58  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x43a5d  brfalse.s loc_43A6B
0x43a5f  ldarg.1
0x43a60  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Write(class System.Xml.Xsl.Qil.QilNode nd)
0x43a65  ldc.i4.6
0x43a66  callvirt instance void System.Xml.Xsl.IlGen.OptimizerPatterns::AddPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x43a6b  ldarg.0
0x43a6c  ldc.i4.s 0x32
0x43a6e  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x43a73  brfalse.s loc_43AEB
0x43a75  ldarg.0
0x43a76  ldloc.0
0x43a77  ldc.i4.s 0x43
0x43a79  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsStepPattern(class System.Xml.Xsl.Qil.QilNode nd, valuetype System.Xml.Xsl.Qil.QilNodeType stepType)
0x43a7e  brtrue.s loc_43A8B
0x43a80  ldarg.0
0x43a81  ldloc.0
0x43a82  ldc.i4.s 0x23
0x43a84  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsStepPattern(class System.Xml.Xsl.Qil.QilNode nd, valuetype System.Xml.Xsl.Qil.QilNodeType stepType)
0x43a89  brfalse.s loc_43AEB
0x43a8b  ldarg.0
0x43a8c  ldloc.1
0x43a8d  ldc.i4.s 0x43
0x43a8f  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsStepPattern(class System.Xml.Xsl.Qil.QilNode nd, valuetype System.Xml.Xsl.Qil.QilNodeType stepType)
0x43a94  brtrue.s loc_43AA1
0x43a96  ldarg.0
0x43a97  ldloc.1
0x43a98  ldc.i4.s 0x23
0x43a9a  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsStepPattern(class System.Xml.Xsl.Qil.QilNode nd, valuetype System.Xml.Xsl.Qil.QilNodeType stepType)
0x43a9f  brfalse.s loc_43AEB
0x43aa1  ldloc.0
0x43aa2  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Read(class System.Xml.Xsl.Qil.QilNode nd)
0x43aa7  ldc.i4.1
0x43aa8  callvirt instance object System.Xml.Xsl.IlGen.OptimizerPatterns::GetArgument(valuetype System.Xml.Xsl.IlGen.OptimizerPatternArgument argNum)
0x43aad  ldloc.1
0x43aae  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Read(class System.Xml.Xsl.Qil.QilNode nd)
0x43ab3  ldc.i4.1
0x43ab4  callvirt instance object System.Xml.Xsl.IlGen.OptimizerPatterns::GetArgument(valuetype System.Xml.Xsl.IlGen.OptimizerPatternArgument argNum)
0x43ab9  bne.un.s loc_43AEB
0x43abb  ldarg.0
0x43abc  ldc.i4.s 0x32
0x43abe  ldarg.1
0x43abf  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x43ac4  brfalse.s loc_43AEB
0x43ac6  ldarg.0
0x43ac7  ldarg.1
0x43ac8  ldloc.0
0x43ac9  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Read(class System.Xml.Xsl.Qil.QilNode nd)
0x43ace  ldc.i4.1
0x43acf  callvirt instance object System.Xml.Xsl.IlGen.OptimizerPatterns::GetArgument(valuetype System.Xml.Xsl.IlGen.OptimizerPatternArgument argNum)
0x43ad4  castclass System.Xml.Xsl.Qil.QilNode
0x43ad9  call     instance void System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AddStepPattern(class System.Xml.Xsl.Qil.QilNode nd, class System.Xml.Xsl.Qil.QilNode input)
0x43ade  ldarg.1
0x43adf  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Write(class System.Xml.Xsl.Qil.QilNode nd)
0x43ae4  ldc.i4.s 0xA
0x43ae6  callvirt instance void System.Xml.Xsl.IlGen.OptimizerPatterns::AddPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x43aeb  ldarg.0
0x43aec  ldarg.1
0x43aed  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternVisitor::NoReplace(class System.Xml.Xsl.Qil.QilNode node)
0x43af2  ret
```
