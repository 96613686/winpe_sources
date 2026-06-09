# System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::VisitEq

- ea: `0x44e60`
- end: `0x455e5`
- name: `System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::VisitEq`
- size: `1925`
- prototype: ``
- caller_count: `0`
- callee_count: `35`
- tags: `registry_config`

## callees

- `0x2370`
- `0x23b0`
- `0x36190`
- `0x361f0`
- `0x36430`
- `0x366f0`
- `0x36790`
- `0x36810`
- `0x36c80`
- `0x37390`
- `0x376a0`
- `0x376c0`
- `0x37750`
- `0x38590`
- `0x3aef0`
- `0x3af20`
- `0x3b050`
- `0x3b1b0`
- `0x3b200`
- `0x3b240`
- `0x3b480`
- `0x40a90`
- `0x40bd0`
- `0x40c40`
- `0x42c20`
- `0x42c30`
- `0x44e60`
- `0x49720`
- `0x497f0`
- `0x49990`
- `0x49b50`
- `0x49ba0`
- `0x49cd0`
- `0x49e30`
- `0x49e50`

## pseudocode

```c

```

## disassembly

```asm
0x44e60  ldarg.1
0x44e61  ldc.i4.0
0x44e62  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x44e67  stloc.0
0x44e68  ldarg.1
0x44e69  ldc.i4.1
0x44e6a  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x44e6f  stloc.1
0x44e70  ldarg.0
0x44e71  ldc.i4.s 0x68
0x44e73  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x44e78  brfalse.s loc_44EAE
0x44e7a  ldloc.0
0x44e7b  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x44e80  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::None
0x44e85  bne.un.s loc_44EAE
0x44e87  ldarg.0
0x44e88  ldc.i4.s 0x68
0x44e8a  ldarg.1
0x44e8b  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x44e90  brfalse.s loc_44EAE
0x44e92  ldarg.0
0x44e93  ldc.i4.s 0x68
0x44e95  ldarg.1
0x44e96  ldarg.0
0x44e97  ldarg.0
0x44e98  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x44e9d  ldloc.0
0x44e9e  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::Nop(class System.Xml.Xsl.Qil.QilNode child)
0x44ea3  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNop(class System.Xml.Xsl.Qil.QilUnary n)
0x44ea8  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x44ead  ret
0x44eae  ldarg.0
0x44eaf  ldc.i4.s 0x68
0x44eb1  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x44eb6  brfalse.s loc_44EEC
0x44eb8  ldloc.1
0x44eb9  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x44ebe  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::None
0x44ec3  bne.un.s loc_44EEC
0x44ec5  ldarg.0
0x44ec6  ldc.i4.s 0x68
0x44ec8  ldarg.1
0x44ec9  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x44ece  brfalse.s loc_44EEC
0x44ed0  ldarg.0
0x44ed1  ldc.i4.s 0x68
0x44ed3  ldarg.1
0x44ed4  ldarg.0
0x44ed5  ldarg.0
0x44ed6  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x44edb  ldloc.1
0x44edc  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::Nop(class System.Xml.Xsl.Qil.QilNode child)
0x44ee1  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNop(class System.Xml.Xsl.Qil.QilUnary n)
0x44ee6  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x44eeb  ret
0x44eec  ldarg.0
0x44eed  ldc.i4.s 0x40
0x44eef  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x44ef4  brfalse.s loc_44F27
0x44ef6  ldarg.0
0x44ef7  ldloc.0
0x44ef8  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x44efd  brfalse.s loc_44F27
0x44eff  ldarg.0
0x44f00  ldloc.1
0x44f01  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x44f06  brfalse.s loc_44F27
0x44f08  ldarg.0
0x44f09  ldc.i4.s 0x40
0x44f0b  ldarg.1
0x44f0c  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x44f11  brfalse.s loc_44F27
0x44f13  ldarg.0
0x44f14  ldc.i4.s 0x40
0x44f16  ldarg.1
0x44f17  ldarg.0
0x44f18  ldc.i4.s 0x34
0x44f1a  ldloc.0
0x44f1b  ldloc.1
0x44f1c  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::FoldComparison(valuetype System.Xml.Xsl.Qil.QilNodeType opType, class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x44f21  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x44f26  ret
0x44f27  ldarg.0
0x44f28  ldc.i4.s 0x71
0x44f2a  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x44f2f  brfalse.s loc_44F6B
0x44f31  ldarg.0
0x44f32  ldloc.0
0x44f33  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x44f38  brfalse.s loc_44F6B
0x44f3a  ldarg.0
0x44f3b  ldloc.1
0x44f3c  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x44f41  brtrue.s loc_44F6B
0x44f43  ldarg.0
0x44f44  ldc.i4.s 0x71
0x44f46  ldarg.1
0x44f47  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x44f4c  brfalse.s loc_44F6B
0x44f4e  ldarg.0
0x44f4f  ldc.i4.s 0x71
0x44f51  ldarg.1
0x44f52  ldarg.0
0x44f53  ldarg.0
0x44f54  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x44f59  ldloc.1
0x44f5a  ldloc.0
0x44f5b  callvirt instance class System.Xml.Xsl.Qil.QilBinary System.Xml.Xsl.Qil.QilFactory::Eq(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x44f60  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitEq(class System.Xml.Xsl.Qil.QilBinary n)
0x44f65  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x44f6a  ret
0x44f6b  ldarg.0
0x44f6c  ldc.i4   0x87
0x44f71  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x44f76  brfalse  loc_4501E
0x44f7b  ldloc.0
0x44f7c  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x44f81  ldc.i4.s 0x6A
0x44f83  bne.un   loc_4501E
0x44f88  ldloc.0
0x44f89  ldc.i4.0
0x44f8a  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x44f8f  stloc.2
0x44f90  ldloc.0
0x44f91  ldc.i4.1
0x44f92  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x44f97  stloc.3
0x44f98  ldloc.3
0x44f99  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x44f9e  ldc.i4.s 0x1A
0x44fa0  bne.un.s loc_4501E
0x44fa2  ldloc.3
0x44fa3  castclass System.Xml.Xsl.Qil.QilLiteral
0x44fa8  callvirt instance object System.Xml.Xsl.Qil.QilLiteral::get_Value()
0x44fad  castclass System.Xml.Xsl.XmlQueryType
0x44fb2  stloc.s  4
0x44fb4  ldarg.0
0x44fb5  ldloc.2
0x44fb6  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x44fbb  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsPrimitiveNumeric(class System.Xml.Xsl.XmlQueryType typ)
0x44fc0  brfalse.s loc_4501E
0x44fc2  ldarg.0
0x44fc3  ldloc.s  4
0x44fc5  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsPrimitiveNumeric(class System.Xml.Xsl.XmlQueryType typ)
0x44fca  brfalse.s loc_4501E
0x44fcc  ldarg.0
0x44fcd  ldloc.1
0x44fce  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x44fd3  brfalse.s loc_4501E
0x44fd5  ldarg.0
0x44fd6  ldloc.1
0x44fd7  ldloc.2
0x44fd8  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x44fdd  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::CanFoldXsltConvertNonLossy(class System.Xml.Xsl.Qil.QilNode ndLiteral, class System.Xml.Xsl.XmlQueryType typTarget)
0x44fe2  brfalse.s loc_4501E
0x44fe4  ldarg.0
0x44fe5  ldc.i4   0x87
0x44fea  ldarg.1
0x44feb  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x44ff0  brfalse.s loc_4501E
0x44ff2  ldarg.0
0x44ff3  ldc.i4   0x87
0x44ff8  ldarg.1
0x44ff9  ldarg.0
0x44ffa  ldarg.0
0x44ffb  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x45000  ldloc.2
0x45001  ldarg.0
0x45002  ldloc.1
0x45003  ldloc.2
0x45004  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x45009  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::FoldXsltConvert(class System.Xml.Xsl.Qil.QilNode ndLiteral, class System.Xml.Xsl.XmlQueryType typTarget)
0x4500e  callvirt instance class System.Xml.Xsl.Qil.QilBinary System.Xml.Xsl.Qil.QilFactory::Eq(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x45013  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitEq(class System.Xml.Xsl.Qil.QilBinary n)
0x45018  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x4501d  ret
0x4501e  ldarg.0
0x4501f  ldc.i4.s 0x6C
0x45021  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x45026  brfalse  loc_450AE
0x4502b  ldloc.0
0x4502c  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x45031  ldc.i4.s 0x2B
0x45033  bne.un.s loc_450AE
0x45035  ldloc.0
0x45036  ldc.i4.0
0x45037  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x4503c  stloc.s  5
0x4503e  ldloc.0
0x4503f  ldc.i4.1
0x45040  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x45045  stloc.s  6
0x45047  ldarg.0
0x45048  ldloc.s  6
0x4504a  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x4504f  brfalse.s loc_450AE
0x45051  ldarg.0
0x45052  ldloc.1
0x45053  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x45058  brfalse.s loc_450AE
0x4505a  ldarg.0
0x4505b  ldc.i4.s 0x2C
0x4505d  ldloc.1
0x4505e  castclass System.Xml.Xsl.Qil.QilLiteral
0x45063  ldloc.s  6
0x45065  castclass System.Xml.Xsl.Qil.QilLiteral
0x4506a  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::CanFoldArithmetic(valuetype System.Xml.Xsl.Qil.QilNodeType opType, class System.Xml.Xsl.Qil.QilLiteral left, class System.Xml.Xsl.Qil.QilLiteral right)
0x4506f  brfalse.s loc_450AE
0x45071  ldarg.0
0x45072  ldc.i4.s 0x6C
0x45074  ldarg.1
0x45075  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x4507a  brfalse.s loc_450AE
0x4507c  ldarg.0
0x4507d  ldc.i4.s 0x6C
0x4507f  ldarg.1
0x45080  ldarg.0
0x45081  ldarg.0
0x45082  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x45087  ldloc.s  5
0x45089  ldarg.0
0x4508a  ldc.i4.s 0x2C
0x4508c  ldloc.1
0x4508d  castclass System.Xml.Xsl.Qil.QilLiteral
0x45092  ldloc.s  6
0x45094  castclass System.Xml.Xsl.Qil.QilLiteral
0x45099  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::FoldArithmetic(valuetype System.Xml.Xsl.Qil.QilNodeType opType, class System.Xml.Xsl.Qil.QilLiteral left, class System.Xml.Xsl.Qil.QilLiteral right)
0x4509e  callvirt instance class System.Xml.Xsl.Qil.QilBinary System.Xml.Xsl.Qil.QilFactory::Eq(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x450a3  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitEq(class System.Xml.Xsl.Qil.QilBinary n)
0x450a8  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x450ad  ret
0x450ae  ldarg.0
0x450af  ldc.i4.s 0x74
0x450b1  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x450b6  brfalse.s loc_45124
0x450b8  ldloc.0
0x450b9  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x450be  ldc.i4.s 0x65
0x450c0  bne.un.s loc_45124
0x450c2  ldloc.0
0x450c3  ldc.i4.0
0x450c4  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x450c9  stloc.s  7
0x450cb  ldloc.s  7
0x450cd  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x450d2  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsSingleton()
0x450d7  brfalse.s loc_45124
0x450d9  ldloc.1
0x450da  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x450df  ldc.i4.s 0x65
0x450e1  bne.un.s loc_45124
0x450e3  ldloc.1
0x450e4  ldc.i4.0
0x450e5  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x450ea  stloc.s  8
0x450ec  ldloc.s  8
0x450ee  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x450f3  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsSingleton()
0x450f8  brfalse.s loc_45124
0x450fa  ldarg.0
0x450fb  ldc.i4.s 0x74
0x450fd  ldarg.1
0x450fe  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x45103  brfalse.s loc_45124
0x45105  ldarg.0
0x45106  ldc.i4.s 0x74
0x45108  ldarg.1
0x45109  ldarg.0
0x4510a  ldarg.0
0x4510b  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x45110  ldloc.s  7
0x45112  ldloc.s  8
0x45114  callvirt instance class System.Xml.Xsl.Qil.QilBinary System.Xml.Xsl.Qil.QilFactory::Is(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x45119  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitIs(class System.Xml.Xsl.Qil.QilBinary n)
0x4511e  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x45123  ret
0x45124  ldarg.0
0x45125  ldc.i4.s 0x74
0x45127  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x4512c  brfalse  loc_4524B
0x45131  ldloc.0
0x45132  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x45137  ldc.i4.s 0x65
0x45139  bne.un   loc_4524B
0x4513e  ldloc.0
0x4513f  ldc.i4.0
0x45140  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x45145  stloc.s  9
0x45147  ldloc.s  9
0x45149  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4514e  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsSingleton()
0x45153  brfalse  loc_4524B
0x45158  ldloc.1
0x45159  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x4515e  ldc.i4.s 0x31
0x45160  bne.un   loc_4524B
0x45165  ldloc.1
0x45166  ldc.i4.1
0x45167  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
  ... truncated ...
```
