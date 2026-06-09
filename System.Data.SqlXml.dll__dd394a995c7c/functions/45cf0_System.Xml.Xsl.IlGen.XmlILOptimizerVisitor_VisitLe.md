# System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::VisitLe

- ea: `0x45cf0`
- end: `0x45f11`
- name: `System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::VisitLe`
- size: `545`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config`

## callees

- `0x36190`
- `0x36730`
- `0x36770`
- `0x37390`
- `0x376a0`
- `0x376c0`
- `0x37750`
- `0x38590`
- `0x3aef0`
- `0x3b1d0`
- `0x3b1f0`
- `0x40a90`
- `0x40bd0`
- `0x40c40`
- `0x42c20`
- `0x42c30`
- `0x45cf0`
- `0x49720`
- `0x497f0`
- `0x49990`
- `0x49b50`
- `0x49ba0`
- `0x49cd0`

## pseudocode

```c

```

## disassembly

```asm
0x45cf0  ldarg.1
0x45cf1  ldc.i4.0
0x45cf2  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x45cf7  stloc.0
0x45cf8  ldarg.1
0x45cf9  ldc.i4.1
0x45cfa  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x45cff  stloc.1
0x45d00  ldarg.0
0x45d01  ldc.i4.s 0x68
0x45d03  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x45d08  brfalse.s loc_45D3E
0x45d0a  ldloc.0
0x45d0b  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x45d10  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::None
0x45d15  bne.un.s loc_45D3E
0x45d17  ldarg.0
0x45d18  ldc.i4.s 0x68
0x45d1a  ldarg.1
0x45d1b  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x45d20  brfalse.s loc_45D3E
0x45d22  ldarg.0
0x45d23  ldc.i4.s 0x68
0x45d25  ldarg.1
0x45d26  ldarg.0
0x45d27  ldarg.0
0x45d28  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x45d2d  ldloc.0
0x45d2e  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::Nop(class System.Xml.Xsl.Qil.QilNode child)
0x45d33  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNop(class System.Xml.Xsl.Qil.QilUnary n)
0x45d38  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x45d3d  ret
0x45d3e  ldarg.0
0x45d3f  ldc.i4.s 0x68
0x45d41  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x45d46  brfalse.s loc_45D7C
0x45d48  ldloc.1
0x45d49  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x45d4e  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::None
0x45d53  bne.un.s loc_45D7C
0x45d55  ldarg.0
0x45d56  ldc.i4.s 0x68
0x45d58  ldarg.1
0x45d59  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x45d5e  brfalse.s loc_45D7C
0x45d60  ldarg.0
0x45d61  ldc.i4.s 0x68
0x45d63  ldarg.1
0x45d64  ldarg.0
0x45d65  ldarg.0
0x45d66  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x45d6b  ldloc.1
0x45d6c  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::Nop(class System.Xml.Xsl.Qil.QilNode child)
0x45d71  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNop(class System.Xml.Xsl.Qil.QilUnary n)
0x45d76  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x45d7b  ret
0x45d7c  ldarg.0
0x45d7d  ldc.i4.s 0x4A
0x45d7f  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x45d84  brfalse.s loc_45DB7
0x45d86  ldarg.0
0x45d87  ldloc.0
0x45d88  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x45d8d  brfalse.s loc_45DB7
0x45d8f  ldarg.0
0x45d90  ldloc.1
0x45d91  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x45d96  brfalse.s loc_45DB7
0x45d98  ldarg.0
0x45d99  ldc.i4.s 0x4A
0x45d9b  ldarg.1
0x45d9c  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x45da1  brfalse.s loc_45DB7
0x45da3  ldarg.0
0x45da4  ldc.i4.s 0x4A
0x45da6  ldarg.1
0x45da7  ldarg.0
0x45da8  ldc.i4.s 0x38
0x45daa  ldloc.0
0x45dab  ldloc.1
0x45dac  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::FoldComparison(valuetype System.Xml.Xsl.Qil.QilNodeType opType, class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x45db1  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x45db6  ret
0x45db7  ldarg.0
0x45db8  ldc.i4.s 0x78
0x45dba  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x45dbf  brfalse.s loc_45DFB
0x45dc1  ldarg.0
0x45dc2  ldloc.0
0x45dc3  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x45dc8  brfalse.s loc_45DFB
0x45dca  ldarg.0
0x45dcb  ldloc.1
0x45dcc  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x45dd1  brtrue.s loc_45DFB
0x45dd3  ldarg.0
0x45dd4  ldc.i4.s 0x78
0x45dd6  ldarg.1
0x45dd7  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x45ddc  brfalse.s loc_45DFB
0x45dde  ldarg.0
0x45ddf  ldc.i4.s 0x78
0x45de1  ldarg.1
0x45de2  ldarg.0
0x45de3  ldarg.0
0x45de4  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x45de9  ldloc.1
0x45dea  ldloc.0
0x45deb  callvirt instance class System.Xml.Xsl.Qil.QilBinary System.Xml.Xsl.Qil.QilFactory::Ge(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x45df0  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitGe(class System.Xml.Xsl.Qil.QilBinary n)
0x45df5  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x45dfa  ret
0x45dfb  ldarg.0
0x45dfc  ldc.i4   0x8A
0x45e01  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x45e06  brfalse  loc_45EAE
0x45e0b  ldloc.0
0x45e0c  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x45e11  ldc.i4.s 0x6A
0x45e13  bne.un   loc_45EAE
0x45e18  ldloc.0
0x45e19  ldc.i4.0
0x45e1a  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x45e1f  stloc.2
0x45e20  ldloc.0
0x45e21  ldc.i4.1
0x45e22  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x45e27  stloc.3
0x45e28  ldloc.3
0x45e29  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x45e2e  ldc.i4.s 0x1A
0x45e30  bne.un.s loc_45EAE
0x45e32  ldloc.3
0x45e33  castclass System.Xml.Xsl.Qil.QilLiteral
0x45e38  callvirt instance object System.Xml.Xsl.Qil.QilLiteral::get_Value()
0x45e3d  castclass System.Xml.Xsl.XmlQueryType
0x45e42  stloc.s  4
0x45e44  ldarg.0
0x45e45  ldloc.2
0x45e46  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x45e4b  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsPrimitiveNumeric(class System.Xml.Xsl.XmlQueryType typ)
0x45e50  brfalse.s loc_45EAE
0x45e52  ldarg.0
0x45e53  ldloc.s  4
0x45e55  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsPrimitiveNumeric(class System.Xml.Xsl.XmlQueryType typ)
0x45e5a  brfalse.s loc_45EAE
0x45e5c  ldarg.0
0x45e5d  ldloc.1
0x45e5e  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x45e63  brfalse.s loc_45EAE
0x45e65  ldarg.0
0x45e66  ldloc.1
0x45e67  ldloc.2
0x45e68  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x45e6d  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::CanFoldXsltConvertNonLossy(class System.Xml.Xsl.Qil.QilNode ndLiteral, class System.Xml.Xsl.XmlQueryType typTarget)
0x45e72  brfalse.s loc_45EAE
0x45e74  ldarg.0
0x45e75  ldc.i4   0x8A
0x45e7a  ldarg.1
0x45e7b  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x45e80  brfalse.s loc_45EAE
0x45e82  ldarg.0
0x45e83  ldc.i4   0x8A
0x45e88  ldarg.1
0x45e89  ldarg.0
0x45e8a  ldarg.0
0x45e8b  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x45e90  ldloc.2
0x45e91  ldarg.0
0x45e92  ldloc.1
0x45e93  ldloc.2
0x45e94  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x45e99  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::FoldXsltConvert(class System.Xml.Xsl.Qil.QilNode ndLiteral, class System.Xml.Xsl.XmlQueryType typTarget)
0x45e9e  callvirt instance class System.Xml.Xsl.Qil.QilBinary System.Xml.Xsl.Qil.QilFactory::Le(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x45ea3  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitLe(class System.Xml.Xsl.Qil.QilBinary n)
0x45ea8  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x45ead  ret
0x45eae  ldarg.0
0x45eaf  ldc.i4.s 0x20
0x45eb1  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x45eb6  brfalse.s loc_45F09
0x45eb8  ldloc.0
0x45eb9  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x45ebe  ldc.i4.s 0x21
0x45ec0  bne.un.s loc_45F09
0x45ec2  ldloc.1
0x45ec3  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x45ec8  ldc.i4.s 0x15
0x45eca  bne.un.s loc_45F09
0x45ecc  ldloc.1
0x45ecd  castclass System.Xml.Xsl.Qil.QilLiteral
0x45ed2  callvirt instance object System.Xml.Xsl.Qil.QilLiteral::get_Value()
0x45ed7  unbox.any [mscorlib]System.Int32
0x45edc  stloc.s  5
0x45ede  ldarg.0
0x45edf  ldc.i4.s 0x20
0x45ee1  ldarg.1
0x45ee2  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x45ee7  brfalse.s loc_45F09
0x45ee9  ldloc.0
0x45eea  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Write(class System.Xml.Xsl.Qil.QilNode nd)
0x45eef  ldc.i4.s 9
0x45ef1  callvirt instance void System.Xml.Xsl.IlGen.OptimizerPatterns::AddPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x45ef6  ldloc.0
0x45ef7  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Write(class System.Xml.Xsl.Qil.QilNode nd)
0x45efc  ldc.i4.2
0x45efd  ldloc.s  5
0x45eff  box      [mscorlib]System.Int32
0x45f04  callvirt instance void System.Xml.Xsl.IlGen.OptimizerPatterns::AddArgument(valuetype System.Xml.Xsl.IlGen.OptimizerPatternArgument argId, object arg)
0x45f09  ldarg.0
0x45f0a  ldarg.1
0x45f0b  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternVisitor::NoReplace(class System.Xml.Xsl.Qil.QilNode node)
0x45f10  ret
```
