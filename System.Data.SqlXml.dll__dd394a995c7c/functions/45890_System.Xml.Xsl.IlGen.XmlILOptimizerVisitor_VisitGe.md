# System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::VisitGe

- ea: `0x45890`
- end: `0x45ab1`
- name: `System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::VisitGe`
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
- `0x45890`
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
0x45890  ldarg.1
0x45891  ldc.i4.0
0x45892  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x45897  stloc.0
0x45898  ldarg.1
0x45899  ldc.i4.1
0x4589a  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x4589f  stloc.1
0x458a0  ldarg.0
0x458a1  ldc.i4.s 0x68
0x458a3  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x458a8  brfalse.s loc_458DE
0x458aa  ldloc.0
0x458ab  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x458b0  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::None
0x458b5  bne.un.s loc_458DE
0x458b7  ldarg.0
0x458b8  ldc.i4.s 0x68
0x458ba  ldarg.1
0x458bb  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x458c0  brfalse.s loc_458DE
0x458c2  ldarg.0
0x458c3  ldc.i4.s 0x68
0x458c5  ldarg.1
0x458c6  ldarg.0
0x458c7  ldarg.0
0x458c8  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x458cd  ldloc.0
0x458ce  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::Nop(class System.Xml.Xsl.Qil.QilNode child)
0x458d3  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNop(class System.Xml.Xsl.Qil.QilUnary n)
0x458d8  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x458dd  ret
0x458de  ldarg.0
0x458df  ldc.i4.s 0x68
0x458e1  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x458e6  brfalse.s loc_4591C
0x458e8  ldloc.1
0x458e9  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x458ee  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::None
0x458f3  bne.un.s loc_4591C
0x458f5  ldarg.0
0x458f6  ldc.i4.s 0x68
0x458f8  ldarg.1
0x458f9  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x458fe  brfalse.s loc_4591C
0x45900  ldarg.0
0x45901  ldc.i4.s 0x68
0x45903  ldarg.1
0x45904  ldarg.0
0x45905  ldarg.0
0x45906  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x4590b  ldloc.1
0x4590c  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::Nop(class System.Xml.Xsl.Qil.QilNode child)
0x45911  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNop(class System.Xml.Xsl.Qil.QilUnary n)
0x45916  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x4591b  ret
0x4591c  ldarg.0
0x4591d  ldc.i4.s 0x42
0x4591f  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x45924  brfalse.s loc_45957
0x45926  ldarg.0
0x45927  ldloc.0
0x45928  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x4592d  brfalse.s loc_45957
0x4592f  ldarg.0
0x45930  ldloc.1
0x45931  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x45936  brfalse.s loc_45957
0x45938  ldarg.0
0x45939  ldc.i4.s 0x42
0x4593b  ldarg.1
0x4593c  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x45941  brfalse.s loc_45957
0x45943  ldarg.0
0x45944  ldc.i4.s 0x42
0x45946  ldarg.1
0x45947  ldarg.0
0x45948  ldc.i4.s 0x36
0x4594a  ldloc.0
0x4594b  ldloc.1
0x4594c  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::FoldComparison(valuetype System.Xml.Xsl.Qil.QilNodeType opType, class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x45951  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x45956  ret
0x45957  ldarg.0
0x45958  ldc.i4.s 0x72
0x4595a  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x4595f  brfalse.s loc_4599B
0x45961  ldarg.0
0x45962  ldloc.0
0x45963  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x45968  brfalse.s loc_4599B
0x4596a  ldarg.0
0x4596b  ldloc.1
0x4596c  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x45971  brtrue.s loc_4599B
0x45973  ldarg.0
0x45974  ldc.i4.s 0x72
0x45976  ldarg.1
0x45977  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x4597c  brfalse.s loc_4599B
0x4597e  ldarg.0
0x4597f  ldc.i4.s 0x72
0x45981  ldarg.1
0x45982  ldarg.0
0x45983  ldarg.0
0x45984  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x45989  ldloc.1
0x4598a  ldloc.0
0x4598b  callvirt instance class System.Xml.Xsl.Qil.QilBinary System.Xml.Xsl.Qil.QilFactory::Le(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x45990  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitLe(class System.Xml.Xsl.Qil.QilBinary n)
0x45995  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x4599a  ret
0x4599b  ldarg.0
0x4599c  ldc.i4   0x88
0x459a1  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x459a6  brfalse  loc_45A4E
0x459ab  ldloc.0
0x459ac  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x459b1  ldc.i4.s 0x6A
0x459b3  bne.un   loc_45A4E
0x459b8  ldloc.0
0x459b9  ldc.i4.0
0x459ba  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x459bf  stloc.2
0x459c0  ldloc.0
0x459c1  ldc.i4.1
0x459c2  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x459c7  stloc.3
0x459c8  ldloc.3
0x459c9  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x459ce  ldc.i4.s 0x1A
0x459d0  bne.un.s loc_45A4E
0x459d2  ldloc.3
0x459d3  castclass System.Xml.Xsl.Qil.QilLiteral
0x459d8  callvirt instance object System.Xml.Xsl.Qil.QilLiteral::get_Value()
0x459dd  castclass System.Xml.Xsl.XmlQueryType
0x459e2  stloc.s  4
0x459e4  ldarg.0
0x459e5  ldloc.2
0x459e6  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x459eb  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsPrimitiveNumeric(class System.Xml.Xsl.XmlQueryType typ)
0x459f0  brfalse.s loc_45A4E
0x459f2  ldarg.0
0x459f3  ldloc.s  4
0x459f5  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsPrimitiveNumeric(class System.Xml.Xsl.XmlQueryType typ)
0x459fa  brfalse.s loc_45A4E
0x459fc  ldarg.0
0x459fd  ldloc.1
0x459fe  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x45a03  brfalse.s loc_45A4E
0x45a05  ldarg.0
0x45a06  ldloc.1
0x45a07  ldloc.2
0x45a08  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x45a0d  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::CanFoldXsltConvertNonLossy(class System.Xml.Xsl.Qil.QilNode ndLiteral, class System.Xml.Xsl.XmlQueryType typTarget)
0x45a12  brfalse.s loc_45A4E
0x45a14  ldarg.0
0x45a15  ldc.i4   0x88
0x45a1a  ldarg.1
0x45a1b  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x45a20  brfalse.s loc_45A4E
0x45a22  ldarg.0
0x45a23  ldc.i4   0x88
0x45a28  ldarg.1
0x45a29  ldarg.0
0x45a2a  ldarg.0
0x45a2b  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x45a30  ldloc.2
0x45a31  ldarg.0
0x45a32  ldloc.1
0x45a33  ldloc.2
0x45a34  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x45a39  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::FoldXsltConvert(class System.Xml.Xsl.Qil.QilNode ndLiteral, class System.Xml.Xsl.XmlQueryType typTarget)
0x45a3e  callvirt instance class System.Xml.Xsl.Qil.QilBinary System.Xml.Xsl.Qil.QilFactory::Ge(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x45a43  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitGe(class System.Xml.Xsl.Qil.QilBinary n)
0x45a48  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x45a4d  ret
0x45a4e  ldarg.0
0x45a4f  ldc.i4.s 0x1E
0x45a51  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x45a56  brfalse.s loc_45AA9
0x45a58  ldloc.0
0x45a59  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x45a5e  ldc.i4.s 0x21
0x45a60  bne.un.s loc_45AA9
0x45a62  ldloc.1
0x45a63  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x45a68  ldc.i4.s 0x15
0x45a6a  bne.un.s loc_45AA9
0x45a6c  ldloc.1
0x45a6d  castclass System.Xml.Xsl.Qil.QilLiteral
0x45a72  callvirt instance object System.Xml.Xsl.Qil.QilLiteral::get_Value()
0x45a77  unbox.any [mscorlib]System.Int32
0x45a7c  stloc.s  5
0x45a7e  ldarg.0
0x45a7f  ldc.i4.s 0x1E
0x45a81  ldarg.1
0x45a82  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x45a87  brfalse.s loc_45AA9
0x45a89  ldloc.0
0x45a8a  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Write(class System.Xml.Xsl.Qil.QilNode nd)
0x45a8f  ldc.i4.s 9
0x45a91  callvirt instance void System.Xml.Xsl.IlGen.OptimizerPatterns::AddPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x45a96  ldloc.0
0x45a97  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Write(class System.Xml.Xsl.Qil.QilNode nd)
0x45a9c  ldc.i4.2
0x45a9d  ldloc.s  5
0x45a9f  box      [mscorlib]System.Int32
0x45aa4  callvirt instance void System.Xml.Xsl.IlGen.OptimizerPatterns::AddArgument(valuetype System.Xml.Xsl.IlGen.OptimizerPatternArgument argId, object arg)
0x45aa9  ldarg.0
0x45aaa  ldarg.1
0x45aab  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternVisitor::NoReplace(class System.Xml.Xsl.Qil.QilNode node)
0x45ab0  ret
```
