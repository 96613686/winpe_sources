# System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::VisitLt

- ea: `0x45ac0`
- end: `0x45ce1`
- name: `System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::VisitLt`
- size: `545`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config`

## callees

- `0x36190`
- `0x36710`
- `0x36750`
- `0x37390`
- `0x376a0`
- `0x376c0`
- `0x37750`
- `0x38590`
- `0x3aef0`
- `0x3b1c0`
- `0x3b1e0`
- `0x40a90`
- `0x40bd0`
- `0x40c40`
- `0x42c20`
- `0x42c30`
- `0x45ac0`
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
0x45ac0  ldarg.1
0x45ac1  ldc.i4.0
0x45ac2  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x45ac7  stloc.0
0x45ac8  ldarg.1
0x45ac9  ldc.i4.1
0x45aca  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x45acf  stloc.1
0x45ad0  ldarg.0
0x45ad1  ldc.i4.s 0x68
0x45ad3  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x45ad8  brfalse.s loc_45B0E
0x45ada  ldloc.0
0x45adb  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x45ae0  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::None
0x45ae5  bne.un.s loc_45B0E
0x45ae7  ldarg.0
0x45ae8  ldc.i4.s 0x68
0x45aea  ldarg.1
0x45aeb  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x45af0  brfalse.s loc_45B0E
0x45af2  ldarg.0
0x45af3  ldc.i4.s 0x68
0x45af5  ldarg.1
0x45af6  ldarg.0
0x45af7  ldarg.0
0x45af8  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x45afd  ldloc.0
0x45afe  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::Nop(class System.Xml.Xsl.Qil.QilNode child)
0x45b03  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNop(class System.Xml.Xsl.Qil.QilUnary n)
0x45b08  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x45b0d  ret
0x45b0e  ldarg.0
0x45b0f  ldc.i4.s 0x68
0x45b11  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x45b16  brfalse.s loc_45B4C
0x45b18  ldloc.1
0x45b19  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x45b1e  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::None
0x45b23  bne.un.s loc_45B4C
0x45b25  ldarg.0
0x45b26  ldc.i4.s 0x68
0x45b28  ldarg.1
0x45b29  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x45b2e  brfalse.s loc_45B4C
0x45b30  ldarg.0
0x45b31  ldc.i4.s 0x68
0x45b33  ldarg.1
0x45b34  ldarg.0
0x45b35  ldarg.0
0x45b36  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x45b3b  ldloc.1
0x45b3c  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::Nop(class System.Xml.Xsl.Qil.QilNode child)
0x45b41  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNop(class System.Xml.Xsl.Qil.QilUnary n)
0x45b46  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x45b4b  ret
0x45b4c  ldarg.0
0x45b4d  ldc.i4.s 0x4D
0x45b4f  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x45b54  brfalse.s loc_45B87
0x45b56  ldarg.0
0x45b57  ldloc.0
0x45b58  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x45b5d  brfalse.s loc_45B87
0x45b5f  ldarg.0
0x45b60  ldloc.1
0x45b61  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x45b66  brfalse.s loc_45B87
0x45b68  ldarg.0
0x45b69  ldc.i4.s 0x4D
0x45b6b  ldarg.1
0x45b6c  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x45b71  brfalse.s loc_45B87
0x45b73  ldarg.0
0x45b74  ldc.i4.s 0x4D
0x45b76  ldarg.1
0x45b77  ldarg.0
0x45b78  ldc.i4.s 0x37
0x45b7a  ldloc.0
0x45b7b  ldloc.1
0x45b7c  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::FoldComparison(valuetype System.Xml.Xsl.Qil.QilNodeType opType, class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x45b81  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x45b86  ret
0x45b87  ldarg.0
0x45b88  ldc.i4.s 0x7F
0x45b8a  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x45b8f  brfalse.s loc_45BCB
0x45b91  ldarg.0
0x45b92  ldloc.0
0x45b93  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x45b98  brfalse.s loc_45BCB
0x45b9a  ldarg.0
0x45b9b  ldloc.1
0x45b9c  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x45ba1  brtrue.s loc_45BCB
0x45ba3  ldarg.0
0x45ba4  ldc.i4.s 0x7F
0x45ba6  ldarg.1
0x45ba7  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x45bac  brfalse.s loc_45BCB
0x45bae  ldarg.0
0x45baf  ldc.i4.s 0x7F
0x45bb1  ldarg.1
0x45bb2  ldarg.0
0x45bb3  ldarg.0
0x45bb4  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x45bb9  ldloc.1
0x45bba  ldloc.0
0x45bbb  callvirt instance class System.Xml.Xsl.Qil.QilBinary System.Xml.Xsl.Qil.QilFactory::Gt(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x45bc0  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitGt(class System.Xml.Xsl.Qil.QilBinary n)
0x45bc5  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x45bca  ret
0x45bcb  ldarg.0
0x45bcc  ldc.i4   0x8B
0x45bd1  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x45bd6  brfalse  loc_45C7E
0x45bdb  ldloc.0
0x45bdc  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x45be1  ldc.i4.s 0x6A
0x45be3  bne.un   loc_45C7E
0x45be8  ldloc.0
0x45be9  ldc.i4.0
0x45bea  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x45bef  stloc.2
0x45bf0  ldloc.0
0x45bf1  ldc.i4.1
0x45bf2  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x45bf7  stloc.3
0x45bf8  ldloc.3
0x45bf9  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x45bfe  ldc.i4.s 0x1A
0x45c00  bne.un.s loc_45C7E
0x45c02  ldloc.3
0x45c03  castclass System.Xml.Xsl.Qil.QilLiteral
0x45c08  callvirt instance object System.Xml.Xsl.Qil.QilLiteral::get_Value()
0x45c0d  castclass System.Xml.Xsl.XmlQueryType
0x45c12  stloc.s  4
0x45c14  ldarg.0
0x45c15  ldloc.2
0x45c16  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x45c1b  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsPrimitiveNumeric(class System.Xml.Xsl.XmlQueryType typ)
0x45c20  brfalse.s loc_45C7E
0x45c22  ldarg.0
0x45c23  ldloc.s  4
0x45c25  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsPrimitiveNumeric(class System.Xml.Xsl.XmlQueryType typ)
0x45c2a  brfalse.s loc_45C7E
0x45c2c  ldarg.0
0x45c2d  ldloc.1
0x45c2e  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x45c33  brfalse.s loc_45C7E
0x45c35  ldarg.0
0x45c36  ldloc.1
0x45c37  ldloc.2
0x45c38  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x45c3d  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::CanFoldXsltConvertNonLossy(class System.Xml.Xsl.Qil.QilNode ndLiteral, class System.Xml.Xsl.XmlQueryType typTarget)
0x45c42  brfalse.s loc_45C7E
0x45c44  ldarg.0
0x45c45  ldc.i4   0x8B
0x45c4a  ldarg.1
0x45c4b  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x45c50  brfalse.s loc_45C7E
0x45c52  ldarg.0
0x45c53  ldc.i4   0x8B
0x45c58  ldarg.1
0x45c59  ldarg.0
0x45c5a  ldarg.0
0x45c5b  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x45c60  ldloc.2
0x45c61  ldarg.0
0x45c62  ldloc.1
0x45c63  ldloc.2
0x45c64  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x45c69  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::FoldXsltConvert(class System.Xml.Xsl.Qil.QilNode ndLiteral, class System.Xml.Xsl.XmlQueryType typTarget)
0x45c6e  callvirt instance class System.Xml.Xsl.Qil.QilBinary System.Xml.Xsl.Qil.QilFactory::Lt(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x45c73  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitLt(class System.Xml.Xsl.Qil.QilBinary n)
0x45c78  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x45c7d  ret
0x45c7e  ldarg.0
0x45c7f  ldc.i4.s 0x21
0x45c81  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x45c86  brfalse.s loc_45CD9
0x45c88  ldloc.0
0x45c89  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x45c8e  ldc.i4.s 0x21
0x45c90  bne.un.s loc_45CD9
0x45c92  ldloc.1
0x45c93  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x45c98  ldc.i4.s 0x15
0x45c9a  bne.un.s loc_45CD9
0x45c9c  ldloc.1
0x45c9d  castclass System.Xml.Xsl.Qil.QilLiteral
0x45ca2  callvirt instance object System.Xml.Xsl.Qil.QilLiteral::get_Value()
0x45ca7  unbox.any [mscorlib]System.Int32
0x45cac  stloc.s  5
0x45cae  ldarg.0
0x45caf  ldc.i4.s 0x21
0x45cb1  ldarg.1
0x45cb2  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x45cb7  brfalse.s loc_45CD9
0x45cb9  ldloc.0
0x45cba  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Write(class System.Xml.Xsl.Qil.QilNode nd)
0x45cbf  ldc.i4.s 9
0x45cc1  callvirt instance void System.Xml.Xsl.IlGen.OptimizerPatterns::AddPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x45cc6  ldloc.0
0x45cc7  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Write(class System.Xml.Xsl.Qil.QilNode nd)
0x45ccc  ldc.i4.2
0x45ccd  ldloc.s  5
0x45ccf  box      [mscorlib]System.Int32
0x45cd4  callvirt instance void System.Xml.Xsl.IlGen.OptimizerPatterns::AddArgument(valuetype System.Xml.Xsl.IlGen.OptimizerPatternArgument argId, object arg)
0x45cd9  ldarg.0
0x45cda  ldarg.1
0x45cdb  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternVisitor::NoReplace(class System.Xml.Xsl.Qil.QilNode node)
0x45ce0  ret
```
