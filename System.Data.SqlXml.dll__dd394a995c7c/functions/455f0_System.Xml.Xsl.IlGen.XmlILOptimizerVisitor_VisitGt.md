# System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::VisitGt

- ea: `0x455f0`
- end: `0x45887`
- name: `System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::VisitGt`
- size: `663`
- prototype: ``
- caller_count: `0`
- callee_count: `27`
- tags: `registry_config`

## callees

- `0x36190`
- `0x36430`
- `0x36710`
- `0x36750`
- `0x36c80`
- `0x37390`
- `0x376a0`
- `0x376c0`
- `0x37750`
- `0x38590`
- `0x3aef0`
- `0x3b050`
- `0x3b1c0`
- `0x3b1e0`
- `0x3b480`
- `0x40a90`
- `0x40bd0`
- `0x40c40`
- `0x42c20`
- `0x42c30`
- `0x455f0`
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
0x455f0  ldarg.1
0x455f1  ldc.i4.0
0x455f2  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x455f7  stloc.0
0x455f8  ldarg.1
0x455f9  ldc.i4.1
0x455fa  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x455ff  stloc.1
0x45600  ldarg.0
0x45601  ldc.i4.s 0x68
0x45603  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x45608  brfalse.s loc_4563E
0x4560a  ldloc.0
0x4560b  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x45610  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::None
0x45615  bne.un.s loc_4563E
0x45617  ldarg.0
0x45618  ldc.i4.s 0x68
0x4561a  ldarg.1
0x4561b  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x45620  brfalse.s loc_4563E
0x45622  ldarg.0
0x45623  ldc.i4.s 0x68
0x45625  ldarg.1
0x45626  ldarg.0
0x45627  ldarg.0
0x45628  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x4562d  ldloc.0
0x4562e  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::Nop(class System.Xml.Xsl.Qil.QilNode child)
0x45633  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNop(class System.Xml.Xsl.Qil.QilUnary n)
0x45638  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x4563d  ret
0x4563e  ldarg.0
0x4563f  ldc.i4.s 0x68
0x45641  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x45646  brfalse.s loc_4567C
0x45648  ldloc.1
0x45649  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4564e  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::None
0x45653  bne.un.s loc_4567C
0x45655  ldarg.0
0x45656  ldc.i4.s 0x68
0x45658  ldarg.1
0x45659  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x4565e  brfalse.s loc_4567C
0x45660  ldarg.0
0x45661  ldc.i4.s 0x68
0x45663  ldarg.1
0x45664  ldarg.0
0x45665  ldarg.0
0x45666  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x4566b  ldloc.1
0x4566c  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::Nop(class System.Xml.Xsl.Qil.QilNode child)
0x45671  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNop(class System.Xml.Xsl.Qil.QilUnary n)
0x45676  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x4567b  ret
0x4567c  ldarg.0
0x4567d  ldc.i4.s 0x43
0x4567f  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x45684  brfalse.s loc_456B7
0x45686  ldarg.0
0x45687  ldloc.0
0x45688  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x4568d  brfalse.s loc_456B7
0x4568f  ldarg.0
0x45690  ldloc.1
0x45691  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x45696  brfalse.s loc_456B7
0x45698  ldarg.0
0x45699  ldc.i4.s 0x43
0x4569b  ldarg.1
0x4569c  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x456a1  brfalse.s loc_456B7
0x456a3  ldarg.0
0x456a4  ldc.i4.s 0x43
0x456a6  ldarg.1
0x456a7  ldarg.0
0x456a8  ldc.i4.s 0x35
0x456aa  ldloc.0
0x456ab  ldloc.1
0x456ac  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::FoldComparison(valuetype System.Xml.Xsl.Qil.QilNodeType opType, class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x456b1  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x456b6  ret
0x456b7  ldarg.0
0x456b8  ldc.i4.s 0x73
0x456ba  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x456bf  brfalse.s loc_456FB
0x456c1  ldarg.0
0x456c2  ldloc.0
0x456c3  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x456c8  brfalse.s loc_456FB
0x456ca  ldarg.0
0x456cb  ldloc.1
0x456cc  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x456d1  brtrue.s loc_456FB
0x456d3  ldarg.0
0x456d4  ldc.i4.s 0x73
0x456d6  ldarg.1
0x456d7  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x456dc  brfalse.s loc_456FB
0x456de  ldarg.0
0x456df  ldc.i4.s 0x73
0x456e1  ldarg.1
0x456e2  ldarg.0
0x456e3  ldarg.0
0x456e4  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x456e9  ldloc.1
0x456ea  ldloc.0
0x456eb  callvirt instance class System.Xml.Xsl.Qil.QilBinary System.Xml.Xsl.Qil.QilFactory::Lt(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x456f0  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitLt(class System.Xml.Xsl.Qil.QilBinary n)
0x456f5  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x456fa  ret
0x456fb  ldarg.0
0x456fc  ldc.i4   0x89
0x45701  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x45706  brfalse  loc_457AE
0x4570b  ldloc.0
0x4570c  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x45711  ldc.i4.s 0x6A
0x45713  bne.un   loc_457AE
0x45718  ldloc.0
0x45719  ldc.i4.0
0x4571a  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x4571f  stloc.2
0x45720  ldloc.0
0x45721  ldc.i4.1
0x45722  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x45727  stloc.3
0x45728  ldloc.3
0x45729  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x4572e  ldc.i4.s 0x1A
0x45730  bne.un.s loc_457AE
0x45732  ldloc.3
0x45733  castclass System.Xml.Xsl.Qil.QilLiteral
0x45738  callvirt instance object System.Xml.Xsl.Qil.QilLiteral::get_Value()
0x4573d  castclass System.Xml.Xsl.XmlQueryType
0x45742  stloc.s  4
0x45744  ldarg.0
0x45745  ldloc.2
0x45746  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4574b  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsPrimitiveNumeric(class System.Xml.Xsl.XmlQueryType typ)
0x45750  brfalse.s loc_457AE
0x45752  ldarg.0
0x45753  ldloc.s  4
0x45755  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsPrimitiveNumeric(class System.Xml.Xsl.XmlQueryType typ)
0x4575a  brfalse.s loc_457AE
0x4575c  ldarg.0
0x4575d  ldloc.1
0x4575e  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::IsLiteral(class System.Xml.Xsl.Qil.QilNode nd)
0x45763  brfalse.s loc_457AE
0x45765  ldarg.0
0x45766  ldloc.1
0x45767  ldloc.2
0x45768  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4576d  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::CanFoldXsltConvertNonLossy(class System.Xml.Xsl.Qil.QilNode ndLiteral, class System.Xml.Xsl.XmlQueryType typTarget)
0x45772  brfalse.s loc_457AE
0x45774  ldarg.0
0x45775  ldc.i4   0x89
0x4577a  ldarg.1
0x4577b  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x45780  brfalse.s loc_457AE
0x45782  ldarg.0
0x45783  ldc.i4   0x89
0x45788  ldarg.1
0x45789  ldarg.0
0x4578a  ldarg.0
0x4578b  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x45790  ldloc.2
0x45791  ldarg.0
0x45792  ldloc.1
0x45793  ldloc.2
0x45794  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x45799  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::FoldXsltConvert(class System.Xml.Xsl.Qil.QilNode ndLiteral, class System.Xml.Xsl.XmlQueryType typTarget)
0x4579e  callvirt instance class System.Xml.Xsl.Qil.QilBinary System.Xml.Xsl.Qil.QilFactory::Gt(class System.Xml.Xsl.Qil.QilNode left, class System.Xml.Xsl.Qil.QilNode right)
0x457a3  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitGt(class System.Xml.Xsl.Qil.QilBinary n)
0x457a8  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x457ad  ret
0x457ae  ldarg.0
0x457af  ldc.i4.s 0x79
0x457b1  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x457b6  brfalse.s loc_45824
0x457b8  ldloc.0
0x457b9  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x457be  ldc.i4.s 0x21
0x457c0  bne.un.s loc_45824
0x457c2  ldloc.0
0x457c3  ldc.i4.0
0x457c4  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x457c9  stloc.s  5
0x457cb  ldloc.1
0x457cc  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x457d1  ldc.i4.s 0x15
0x457d3  bne.un.s loc_45824
0x457d5  ldloc.1
0x457d6  castclass System.Xml.Xsl.Qil.QilLiteral
0x457db  callvirt instance object System.Xml.Xsl.Qil.QilLiteral::get_Value()
0x457e0  unbox.any [mscorlib]System.Int32
0x457e5  stloc.s  6
0x457e7  ldloc.s  6
0x457e9  brtrue.s loc_45824
0x457eb  ldarg.0
0x457ec  ldc.i4.s 0x79
0x457ee  ldarg.1
0x457ef  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x457f4  brfalse.s loc_45824
0x457f6  ldarg.0
0x457f7  ldc.i4.s 0x79
0x457f9  ldarg.1
0x457fa  ldarg.0
0x457fb  ldarg.0
0x457fc  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x45801  ldarg.0
0x45802  ldarg.0
0x45803  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilReplaceVisitor::f
0x45808  ldloc.s  5
0x4580a  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::IsEmpty(class System.Xml.Xsl.Qil.QilNode child)
0x4580f  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitIsEmpty(class System.Xml.Xsl.Qil.QilUnary n)
0x45814  callvirt instance class System.Xml.Xsl.Qil.QilUnary System.Xml.Xsl.Qil.QilFactory::Not(class System.Xml.Xsl.Qil.QilNode child)
0x45819  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::VisitNot(class System.Xml.Xsl.Qil.QilUnary n)
0x4581e  call     instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::Replace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original, class System.Xml.Xsl.Qil.QilNode replacement)
0x45823  ret
0x45824  ldarg.0
0x45825  ldc.i4.s 0x1F
0x45827  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::get_Item(valuetype System.Xml.Xsl.IlGen.XmlILOptimization ann)
0x4582c  brfalse.s loc_4587F
0x4582e  ldloc.0
0x4582f  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x45834  ldc.i4.s 0x21
0x45836  bne.un.s loc_4587F
0x45838  ldloc.1
0x45839  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x4583e  ldc.i4.s 0x15
0x45840  bne.un.s loc_4587F
0x45842  ldloc.1
0x45843  castclass System.Xml.Xsl.Qil.QilLiteral
0x45848  callvirt instance object System.Xml.Xsl.Qil.QilLiteral::get_Value()
0x4584d  unbox.any [mscorlib]System.Int32
0x45852  stloc.s  7
0x45854  ldarg.0
0x45855  ldc.i4.s 0x1F
0x45857  ldarg.1
0x45858  call     instance bool System.Xml.Xsl.IlGen.XmlILOptimizerVisitor::AllowReplace(valuetype System.Xml.Xsl.IlGen.XmlILOptimization pattern, class System.Xml.Xsl.Qil.QilNode original)
0x4585d  brfalse.s loc_4587F
0x4585f  ldloc.0
0x45860  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Write(class System.Xml.Xsl.Qil.QilNode nd)
0x45865  ldc.i4.s 9
0x45867  callvirt instance void System.Xml.Xsl.IlGen.OptimizerPatterns::AddPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x4586c  ldloc.0
0x4586d  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Write(class System.Xml.Xsl.Qil.QilNode nd)
0x45872  ldc.i4.2
0x45873  ldloc.s  7
0x45875  box      [mscorlib]System.Int32
0x4587a  callvirt instance void System.Xml.Xsl.IlGen.OptimizerPatterns::AddArgument(valuetype System.Xml.Xsl.IlGen.OptimizerPatternArgument argId, object arg)
0x4587f  ldarg.0
0x45880  ldarg.1
0x45881  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilPatternVisitor::NoReplace(class System.Xml.Xsl.Qil.QilNode node)
0x45886  ret
```
