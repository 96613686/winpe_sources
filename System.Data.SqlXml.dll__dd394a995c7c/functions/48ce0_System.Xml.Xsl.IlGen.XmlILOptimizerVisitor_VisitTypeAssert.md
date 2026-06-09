# System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::VisitTypeAssert

- ea: `0x48ce0`
- end: `0x48ea3`
- name: `System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::VisitTypeAssert`
- size: `451`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config`

## callees

- `0x1ff0`
- `0x2030`
- `0x2110`
- `0x36190`
- `0x361b0`
- `0x362b0`
- `0x36450`
- `0x364b0`
- `0x36c80`
- `0x37390`
- `0x376a0`
- `0x376c0`
- `0x37750`
- `0x38590`
- `0x3aef0`
- `0x3af00`
- `0x3afb0`
- `0x3b060`
- `0x3b090`
- `0x3b480`
- `0x42c20`
- `0x42c30`
- `0x48ce0`
- `0x49720`

## pseudocode

```c

```

## disassembly

```asm
0x48ce0  ldarg.1
0x48ce1  ldc.i4.0
0x48ce2  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x48ce7  stloc.0
0x48ce8  ldarg.1
0x48ce9  ldc.i4.1
0x48cea  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x48cef  stloc.1
0x48cf0  ldarg.0
0x48cf1  ldc.i4.s 0x68
0x48cf3  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x48cf8  brfalse.s loc_48D2E
0x48cfa  ldloc.0
0x48cfb  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x48d00  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::None
0x48d05  bne.un.s loc_48D2E
0x48d07  ldarg.0
0x48d08  ldc.i4.s 0x68
0x48d0a  ldarg.1
0x48d0b  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x48d10  brfalse.s loc_48D2E
0x48d12  ldarg.0
0x48d13  ldc.i4.s 0x68
0x48d15  ldarg.1
0x48d16  ldarg.0
0x48d17  ldarg.0
0x48d18  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x48d1d  ldloc.0
0x48d1e  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::Nop(class System.Xml.Xsl.Qil.QilNode child)
0x48d23  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNop(class System.Xml.Xsl.Qil.QilUnary n)
0x48d28  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x48d2d  ret
0x48d2e  ldarg.0
0x48d2f  ldc.i4.s 0x61
0x48d31  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x48d36  brfalse.s loc_48D9D
0x48d38  ldloc.1
0x48d39  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x48d3e  ldc.i4.s 0x1A
0x48d40  bne.un.s loc_48D9D
0x48d42  ldloc.1
0x48d43  castclass System.Xml.Xsl.Qil.QilLiteral
0x48d48  callvirt instance object System.Xml.Xsl.Qil.QilLiteral::get_Value()
0x48d4d  castclass System.Xml.Xsl.XmlQueryType
0x48d52  stloc.2
0x48d53  ldloc.0
0x48d54  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x48d59  ldloc.2
0x48d5a  callvirt instance bool System.Xml.Xsl.XmlQueryType::NeverSubtypeOf(class System.Xml.Xsl.XmlQueryType baseType)
0x48d5f  brfalse.s loc_48D9D
0x48d61  ldarg.0
0x48d62  ldc.i4.s 0x61
0x48d64  ldarg.1
0x48d65  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x48d6a  brfalse.s loc_48D9D
0x48d6c  ldarg.0
0x48d6d  ldc.i4.s 0x61
0x48d6f  ldarg.1
0x48d70  ldarg.0
0x48d71  ldarg.0
0x48d72  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x48d77  ldarg.0
0x48d78  ldarg.0
0x48d79  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x48d7e  ldsfld   string [mscorlib]System.String::Empty
0x48d83  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralString(string value)
0x48d88  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitLiteralString(class System.Xml.Xsl.Qil.QilLiteral n)
0x48d8d  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::Error(class System.Xml.Xsl.Qil.QilNode child)
0x48d92  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitError(class System.Xml.Xsl.Qil.QilUnary n)
0x48d97  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x48d9c  ret
0x48d9d  ldarg.0
0x48d9e  ldc.i4.s 0x61
0x48da0  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x48da5  brfalse  loc_48E50
0x48daa  ldloc.1
0x48dab  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x48db0  ldc.i4.s 0x1A
0x48db2  bne.un   loc_48E50
0x48db7  ldloc.1
0x48db8  castclass System.Xml.Xsl.Qil.QilLiteral
0x48dbd  callvirt instance object System.Xml.Xsl.Qil.QilLiteral::get_Value()
0x48dc2  castclass System.Xml.Xsl.XmlQueryType
0x48dc7  stloc.3
0x48dc8  ldloc.0
0x48dc9  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x48dce  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryType::get_Prime()
0x48dd3  ldloc.3
0x48dd4  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryType::get_Prime()
0x48dd9  callvirt instance bool System.Xml.Xsl.XmlQueryType::NeverSubtypeOf(class System.Xml.Xsl.XmlQueryType baseType)
0x48dde  brfalse.s loc_48E50
0x48de0  ldarg.0
0x48de1  ldc.i4.s 0x61
0x48de3  ldarg.1
0x48de4  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x48de9  brfalse.s loc_48E50
0x48deb  ldarg.0
0x48dec  ldc.i4.s 0x61
0x48dee  ldarg.1
0x48def  ldarg.0
0x48df0  ldarg.0
0x48df1  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x48df6  ldarg.0
0x48df7  ldarg.0
0x48df8  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x48dfd  ldloc.0
0x48dfe  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::IsEmpty(class System.Xml.Xsl.Qil.QilNode child)
0x48e03  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitIsEmpty(class System.Xml.Xsl.Qil.QilUnary n)
0x48e08  ldarg.0
0x48e09  ldarg.0
0x48e0a  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x48e0f  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilFactory::Sequence()
0x48e14  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitSequence(class System.Xml.Xsl.Qil.QilList n)
0x48e19  ldarg.0
0x48e1a  ldarg.0
0x48e1b  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x48e20  ldarg.0
0x48e21  ldarg.0
0x48e22  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x48e27  ldsfld   string [mscorlib]System.String::Empty
0x48e2c  callvirt instance class System.Xml.Xsl.Qil.QilLiteral System.Xml.Xsl.Qil.QilFactory::LiteralString(string value)
0x48e31  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitLiteralString(class System.Xml.Xsl.Qil.QilLiteral n)
0x48e36  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::Error(class System.Xml.Xsl.Qil.QilNode child)
0x48e3b  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitError(class System.Xml.Xsl.Qil.QilUnary n)
0x48e40  callvirt instance class System.Xml.Xsl.Qil.QilTernary System.Xml.Xsl.Qil.QilFactory::Conditional(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode center, class System.Xml.Xsl.Qil.QilNode right)
0x48e45  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitConditional(class System.Xml.Xsl.Qil.QilTernary n)
0x48e4a  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x48e4f  ret
0x48e50  ldarg.0
0x48e51  ldc.i4.s 0x62
0x48e53  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x48e58  brfalse.s loc_48E9B
0x48e5a  ldloc.1
0x48e5b  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x48e60  ldc.i4.s 0x1A
0x48e62  bne.un.s loc_48E9B
0x48e64  ldloc.1
0x48e65  castclass System.Xml.Xsl.Qil.QilLiteral
0x48e6a  callvirt instance object System.Xml.Xsl.Qil.QilLiteral::get_Value()
0x48e6f  castclass System.Xml.Xsl.XmlQueryType
0x48e74  stloc.s  4
0x48e76  ldloc.0
0x48e77  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x48e7c  ldloc.s  4
0x48e7e  callvirt instance bool System.Xml.Xsl.XmlQueryType::IsSubtypeOf(class System.Xml.Xsl.XmlQueryType baseType)
0x48e83  brfalse.s loc_48E9B
0x48e85  ldarg.0
0x48e86  ldc.i4.s 0x62
0x48e88  ldarg.1
0x48e89  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x48e8e  brfalse.s loc_48E9B
0x48e90  ldarg.0
0x48e91  ldc.i4.s 0x62
0x48e93  ldarg.1
0x48e94  ldloc.0
0x48e95  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x48e9a  ret
0x48e9b  ldarg.0
0x48e9c  ldarg.1
0x48e9d  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternVisitor::NoReplace(class System.Xml.Xsl.Qil.QilNode node)
0x48ea2  ret
```
