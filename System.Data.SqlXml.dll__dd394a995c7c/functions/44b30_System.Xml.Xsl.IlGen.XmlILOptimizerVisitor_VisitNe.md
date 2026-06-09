# System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::VisitNe

- ea: `0x44b30`
- end: `0x44e57`
- name: `System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::VisitNe`
- size: `807`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: `registry_config`

## callees

- `0x2370`
- `0x36190`
- `0x36430`
- `0x366d0`
- `0x36790`
- `0x36c80`
- `0x37390`
- `0x376a0`
- `0x376c0`
- `0x37750`
- `0x38590`
- `0x3aef0`
- `0x3b050`
- `0x3b1a0`
- `0x3b200`
- `0x3b480`
- `0x40a90`
- `0x40bd0`
- `0x40c40`
- `0x42c20`
- `0x42c30`
- `0x44b30`
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
0x44b30  ldarg.1
0x44b31  ldc.i4.0
0x44b32  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x44b37  stloc.0
0x44b38  ldarg.1
0x44b39  ldc.i4.1
0x44b3a  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x44b3f  stloc.1
0x44b40  ldarg.0
0x44b41  ldc.i4.s 0x68
0x44b43  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x44b48  brfalse.s loc_44B7E
0x44b4a  ldloc.0
0x44b4b  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x44b50  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::None
0x44b55  bne.un.s loc_44B7E
0x44b57  ldarg.0
0x44b58  ldc.i4.s 0x68
0x44b5a  ldarg.1
0x44b5b  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x44b60  brfalse.s loc_44B7E
0x44b62  ldarg.0
0x44b63  ldc.i4.s 0x68
0x44b65  ldarg.1
0x44b66  ldarg.0
0x44b67  ldarg.0
0x44b68  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x44b6d  ldloc.0
0x44b6e  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::Nop(class System.Xml.Xsl.Qil.QilNode child)
0x44b73  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNop(class System.Xml.Xsl.Qil.QilUnary n)
0x44b78  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x44b7d  ret
0x44b7e  ldarg.0
0x44b7f  ldc.i4.s 0x68
0x44b81  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x44b86  brfalse.s loc_44BBC
0x44b88  ldloc.1
0x44b89  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x44b8e  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::None
0x44b93  bne.un.s loc_44BBC
0x44b95  ldarg.0
0x44b96  ldc.i4.s 0x68
0x44b98  ldarg.1
0x44b99  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x44b9e  brfalse.s loc_44BBC
0x44ba0  ldarg.0
0x44ba1  ldc.i4.s 0x68
0x44ba3  ldarg.1
0x44ba4  ldarg.0
0x44ba5  ldarg.0
0x44ba6  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x44bab  ldloc.1
0x44bac  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::Nop(class System.Xml.Xsl.Qil.QilNode child)
0x44bb1  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNop(class System.Xml.Xsl.Qil.QilUnary n)
0x44bb6  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x44bbb  ret
0x44bbc  ldarg.0
0x44bbd  ldc.i4.s 0x53
0x44bbf  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x44bc4  brfalse.s loc_44BF7
0x44bc6  ldarg.0
0x44bc7  ldloc.0
0x44bc8  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x44bcd  brfalse.s loc_44BF7
0x44bcf  ldarg.0
0x44bd0  ldloc.1
0x44bd1  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x44bd6  brfalse.s loc_44BF7
0x44bd8  ldarg.0
0x44bd9  ldc.i4.s 0x53
0x44bdb  ldarg.1
0x44bdc  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x44be1  brfalse.s loc_44BF7
0x44be3  ldarg.0
0x44be4  ldc.i4.s 0x53
0x44be6  ldarg.1
0x44be7  ldarg.0
0x44be8  ldc.i4.s 0x33
0x44bea  ldloc.0
0x44beb  ldloc.1
0x44bec  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::FoldComparison(valuetype System.Xml.Xsl.Qil.QilNodeType opType, class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x44bf1  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x44bf6  ret
0x44bf7  ldarg.0
0x44bf8  ldc.i4   0x82
0x44bfd  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x44c02  brfalse.s loc_44C44
0x44c04  ldarg.0
0x44c05  ldloc.0
0x44c06  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x44c0b  brfalse.s loc_44C44
0x44c0d  ldarg.0
0x44c0e  ldloc.1
0x44c0f  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x44c14  brtrue.s loc_44C44
0x44c16  ldarg.0
0x44c17  ldc.i4   0x82
0x44c1c  ldarg.1
0x44c1d  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x44c22  brfalse.s loc_44C44
0x44c24  ldarg.0
0x44c25  ldc.i4   0x82
0x44c2a  ldarg.1
0x44c2b  ldarg.0
0x44c2c  ldarg.0
0x44c2d  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x44c32  ldloc.1
0x44c33  ldloc.0
0x44c34  callvirt instance class System.Xml.Xsl.Qil.QilBinary System.Xml.Xsl.Qil.QilFactory::Ne(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x44c39  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNe(class System.Xml.Xsl.Qil.QilBinary n)
0x44c3e  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x44c43  ret
0x44c44  ldarg.0
0x44c45  ldc.i4   0x8C
0x44c4a  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x44c4f  brfalse  loc_44CF7
0x44c54  ldloc.0
0x44c55  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x44c5a  ldc.i4.s 0x6A
0x44c5c  bne.un   loc_44CF7
0x44c61  ldloc.0
0x44c62  ldc.i4.0
0x44c63  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x44c68  stloc.2
0x44c69  ldloc.0
0x44c6a  ldc.i4.1
0x44c6b  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x44c70  stloc.3
0x44c71  ldloc.3
0x44c72  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x44c77  ldc.i4.s 0x1A
0x44c79  bne.un.s loc_44CF7
0x44c7b  ldloc.3
0x44c7c  castclass System.Xml.Xsl.Qil.QilLiteral
0x44c81  callvirt instance object System.Xml.Xsl.Qil.QilLiteral::get_Value()
0x44c86  castclass System.Xml.Xsl.XmlQueryType
0x44c8b  stloc.s  4
0x44c8d  ldarg.0
0x44c8e  ldloc.2
0x44c8f  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x44c94  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsPrimitiveNumeric(class System.Xml.Xsl.XmlQueryType typ)
0x44c99  brfalse.s loc_44CF7
0x44c9b  ldarg.0
0x44c9c  ldloc.s  4
0x44c9e  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsPrimitiveNumeric(class System.Xml.Xsl.XmlQueryType typ)
0x44ca3  brfalse.s loc_44CF7
0x44ca5  ldarg.0
0x44ca6  ldloc.1
0x44ca7  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x44cac  brfalse.s loc_44CF7
0x44cae  ldarg.0
0x44caf  ldloc.1
0x44cb0  ldloc.2
0x44cb1  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x44cb6  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::CanFoldXsltConvertNonLossy(class System.Xml.Xsl.Qil.QilNode ndLiteral, class System.Xml.Xsl.XmlQueryType typTarget)
0x44cbb  brfalse.s loc_44CF7
0x44cbd  ldarg.0
0x44cbe  ldc.i4   0x8C
0x44cc3  ldarg.1
0x44cc4  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x44cc9  brfalse.s loc_44CF7
0x44ccb  ldarg.0
0x44ccc  ldc.i4   0x8C
0x44cd1  ldarg.1
0x44cd2  ldarg.0
0x44cd3  ldarg.0
0x44cd4  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x44cd9  ldloc.2
0x44cda  ldarg.0
0x44cdb  ldloc.1
0x44cdc  ldloc.2
0x44cdd  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x44ce2  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::FoldXsltConvert(class System.Xml.Xsl.Qil.QilNode ndLiteral, class System.Xml.Xsl.XmlQueryType typTarget)
0x44ce7  callvirt instance class System.Xml.Xsl.Qil.QilBinary System.Xml.Xsl.Qil.QilFactory::Ne(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x44cec  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNe(class System.Xml.Xsl.Qil.QilBinary n)
0x44cf1  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x44cf6  ret
0x44cf7  ldarg.0
0x44cf8  ldc.i4.s 0x75
0x44cfa  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x44cff  brfalse.s loc_44D7E
0x44d01  ldloc.0
0x44d02  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x44d07  ldc.i4.s 0x65
0x44d09  bne.un.s loc_44D7E
0x44d0b  ldloc.0
0x44d0c  ldc.i4.0
0x44d0d  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x44d12  stloc.s  5
0x44d14  ldloc.s  5
0x44d16  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x44d1b  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsSingleton()
0x44d20  brfalse.s loc_44D7E
0x44d22  ldloc.1
0x44d23  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x44d28  ldc.i4.s 0x65
0x44d2a  bne.un.s loc_44D7E
0x44d2c  ldloc.1
0x44d2d  ldc.i4.0
0x44d2e  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x44d33  stloc.s  6
0x44d35  ldloc.s  6
0x44d37  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x44d3c  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsSingleton()
0x44d41  brfalse.s loc_44D7E
0x44d43  ldarg.0
0x44d44  ldc.i4.s 0x75
0x44d46  ldarg.1
0x44d47  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x44d4c  brfalse.s loc_44D7E
0x44d4e  ldarg.0
0x44d4f  ldc.i4.s 0x75
0x44d51  ldarg.1
0x44d52  ldarg.0
0x44d53  ldarg.0
0x44d54  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x44d59  ldarg.0
0x44d5a  ldarg.0
0x44d5b  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x44d60  ldloc.s  5
0x44d62  ldloc.s  6
0x44d64  callvirt instance class System.Xml.Xsl.Qil.QilBinary System.Xml.Xsl.Qil.QilFactory::Is(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x44d69  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitIs(class System.Xml.Xsl.Qil.QilBinary n)
0x44d6e  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::Not(class System.Xml.Xsl.Qil.QilNode child)
0x44d73  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNot(class System.Xml.Xsl.Qil.QilUnary n)
0x44d78  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x44d7d  ret
0x44d7e  ldarg.0
0x44d7f  ldc.i4.s 0x7A
0x44d81  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x44d86  brfalse.s loc_44DF4
0x44d88  ldloc.0
0x44d89  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x44d8e  ldc.i4.s 0x21
0x44d90  bne.un.s loc_44DF4
0x44d92  ldloc.0
0x44d93  ldc.i4.0
0x44d94  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x44d99  stloc.s  7
0x44d9b  ldloc.1
0x44d9c  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x44da1  ldc.i4.s 0x15
0x44da3  bne.un.s loc_44DF4
0x44da5  ldloc.1
0x44da6  castclass System.Xml.Xsl.Qil.QilLiteral
0x44dab  callvirt instance object System.Xml.Xsl.Qil.QilLiteral::get_Value()
0x44db0  unbox.any [mscorlib]System.Int32
0x44db5  stloc.s  8
0x44db7  ldloc.s  8
0x44db9  brtrue.s loc_44DF4
0x44dbb  ldarg.0
0x44dbc  ldc.i4.s 0x7A
0x44dbe  ldarg.1
0x44dbf  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x44dc4  brfalse.s loc_44DF4
0x44dc6  ldarg.0
0x44dc7  ldc.i4.s 0x7A
0x44dc9  ldarg.1
0x44dca  ldarg.0
0x44dcb  ldarg.0
0x44dcc  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x44dd1  ldarg.0
0x44dd2  ldarg.0
0x44dd3  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x44dd8  ldloc.s  7
0x44dda  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::IsEmpty(class System.Xml.Xsl.Qil.QilNode child)
0x44ddf  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitIsEmpty(class System.Xml.Xsl.Qil.QilUnary n)
0x44de4  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::Not(class System.Xml.Xsl.Qil.QilNode child)
0x44de9  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNot(class System.Xml.Xsl.Qil.QilUnary n)
0x44dee  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x44df3  ret
0x44df4  ldarg.0
0x44df5  ldc.i4.s 0x22
0x44df7  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x44dfc  brfalse.s loc_44E4F
0x44dfe  ldloc.0
0x44dff  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x44e04  ldc.i4.s 0x21
0x44e06  bne.un.s loc_44E4F
0x44e08  ldloc.1
0x44e09  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x44e0e  ldc.i4.s 0x15
0x44e10  bne.un.s loc_44E4F
0x44e12  ldloc.1
0x44e13  castclass System.Xml.Xsl.Qil.QilLiteral
0x44e18  callvirt instance object System.Xml.Xsl.Qil.QilLiteral::get_Value()
0x44e1d  unbox.any [mscorlib]System.Int32
0x44e22  stloc.s  9
0x44e24  ldarg.0
0x44e25  ldc.i4.s 0x22
0x44e27  ldarg.1
0x44e28  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x44e2d  brfalse.s loc_44E4F
0x44e2f  ldloc.0
0x44e30  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Write(class System.Xml.Xsl.Qil.QilNode nd)
0x44e35  ldc.i4.s 9
0x44e37  callvirt instance void System.Xml.Xsl.IlGen.OptimizerPatterns::AddPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x44e3c  ldloc.0
0x44e3d  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Write(class System.Xml.Xsl.Qil.QilNode nd)
0x44e42  ldc.i4.2
  ... truncated ...
```
