# System.Xml.Xsl.IlGen.XmlILVisitor::HandleDodPatterns

- ea: `0x4d910`
- end: `0x4dc69`
- name: `System.Xml.Xsl.IlGen.XmlILVisitor::HandleDodPatterns`
- size: `857`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config`

## callers

- `0x4d8a0`

## callees

- `0x1fc0`
- `0x376a0`
- `0x376c0`
- `0x3a530`
- `0x3a690`
- `0x3f170`
- `0x3f180`
- `0x3f3e0`
- `0x3ff00`
- `0x3fff0`
- `0x400f0`
- `0x40380`
- `0x405b0`
- `0x40670`
- `0x409c0`
- `0x40c00`
- `0x40c60`
- `0x4d910`
- `0x4f940`
- `0x4f9c0`
- `0x504d0`
- `0x504f0`

## pseudocode

```c

```

## disassembly

```asm
0x4d910  ldarg.1
0x4d911  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Read(class System.Xml.Xsl.Qil.QilNode nd)
0x4d916  stloc.0
0x4d917  ldloc.0
0x4d918  ldc.i4.8
0x4d919  callvirt instance bool System.Xml.Xsl.IlGen.OptimizerPatterns::MatchesPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x4d91e  stloc.s  5
0x4d920  ldloc.s  5
0x4d922  brtrue.s loc_4D930
0x4d924  ldloc.0
0x4d925  ldc.i4.1
0x4d926  callvirt instance bool System.Xml.Xsl.IlGen.OptimizerPatterns::MatchesPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x4d92b  brfalse  loc_4DB64
0x4d930  ldloc.0
0x4d931  ldc.i4.2
0x4d932  callvirt instance object System.Xml.Xsl.IlGen.OptimizerPatterns::GetArgument(valuetype System.Xml.Xsl.IlGen.OptimizerPatternArgument argNum)
0x4d937  castclass System.Xml.Xsl.Qil.QilNode
0x4d93c  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Read(class System.Xml.Xsl.Qil.QilNode nd)
0x4d941  stloc.s  6
0x4d943  ldloc.s  6
0x4d945  ldc.i4.5
0x4d946  callvirt instance bool System.Xml.Xsl.IlGen.OptimizerPatterns::MatchesPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x4d94b  brfalse.s loc_4D95F
0x4d94d  ldc.i4.2
0x4d94e  stloc.1
0x4d94f  ldloc.s  6
0x4d951  ldc.i4.2
0x4d952  callvirt instance object System.Xml.Xsl.IlGen.OptimizerPatterns::GetArgument(valuetype System.Xml.Xsl.IlGen.OptimizerPatternArgument argNum)
0x4d957  castclass System.Xml.Xsl.Qil.QilName
0x4d95c  stloc.2
0x4d95d  br.s     loc_4D998
0x4d95f  ldloc.s  6
0x4d961  ldc.i4.4
0x4d962  callvirt instance bool System.Xml.Xsl.IlGen.OptimizerPatterns::MatchesPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x4d967  brfalse.s loc_4D980
0x4d969  ldloc.s  6
0x4d96b  ldc.i4.2
0x4d96c  callvirt instance object System.Xml.Xsl.IlGen.OptimizerPatterns::GetArgument(valuetype System.Xml.Xsl.IlGen.OptimizerPatternArgument argNum)
0x4d971  castclass System.Xml.Xsl.XmlQueryType
0x4d976  callvirt instance valuetype System.Xml.Xsl.XmlNodeKindFlags System.Xml.Xsl.XmlQueryType::get_NodeKinds()
0x4d97b  stloc.1
0x4d97c  ldnull
0x4d97d  stloc.2
0x4d97e  br.s     loc_4D998
0x4d980  ldarg.1
0x4d981  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4d986  callvirt instance valuetype System.Xml.Xsl.XmlNodeKindFlags System.Xml.Xsl.XmlQueryType::get_NodeKinds()
0x4d98b  ldc.i4.4
0x4d98c  and
0x4d98d  brtrue.s loc_4D993
0x4d98f  ldc.i4.s 0x3A
0x4d991  br.s     loc_4D995
0x4d993  ldc.i4.s 0x7F
0x4d995  stloc.1
0x4d996  ldnull
0x4d997  stloc.2
0x4d998  ldloc.s  6
0x4d99a  ldc.i4.0
0x4d99b  callvirt instance object System.Xml.Xsl.IlGen.OptimizerPatterns::GetArgument(valuetype System.Xml.Xsl.IlGen.OptimizerPatternArgument argNum)
0x4d9a0  castclass System.Xml.Xsl.Qil.QilNode
0x4d9a5  stloc.s  4
0x4d9a7  ldloc.s  5
0x4d9a9  brfalse  loc_4DAB4
0x4d9ae  ldloc.s  4
0x4d9b0  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x4d9b5  stloc.s  7
0x4d9b7  ldloc.s  7
0x4d9b9  ldc.i4.s 0x49
0x4d9bb  bgt.s    loc_4D9D0
0x4d9bd  ldloc.s  7
0x4d9bf  ldc.i4.s 0x43
0x4d9c1  beq.s    loc_4D9ED
0x4d9c3  ldloc.s  7
0x4d9c5  ldc.i4.s 0x48
0x4d9c7  sub
0x4d9c8  ldc.i4.1
0x4d9c9  ble.un.s loc_4DA12
0x4d9cb  br       loc_4DC67
0x4d9d0  ldloc.s  7
0x4d9d2  ldc.i4.s 0x4D
0x4d9d4  beq      loc_4DA6A
0x4d9d9  ldloc.s  7
0x4d9db  ldc.i4.s 0x62
0x4d9dd  beq.s    loc_4DA45
0x4d9df  ldloc.s  7
0x4d9e1  ldc.i4.s 0x63
0x4d9e3  beq      loc_4DA8F
0x4d9e8  br       loc_4DC67
0x4d9ed  ldarg.0
0x4d9ee  ldarg.1
0x4d9ef  ldstr    aItercontent// "$$$iterContent"
0x4d9f4  ldtoken  System.Xml.Xsl.Runtime.ContentMergeIterator
0x4d9f9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4d9fe  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::ContentMergeCreate
0x4da03  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::ContentMergeNext
0x4da08  ldloc.1
0x4da09  ldloc.2
0x4da0a  ldc.i4.m1
0x4da0b  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::CreateContainerIterator(class System.Xml.Xsl.Qil.QilUnary ndDod, string iterName, class [mscorlib]System.Type iterType, class [mscorlib]System.Reflection.MethodInfo methCreate, class [mscorlib]System.Reflection.MethodInfo methNext, valuetype System.Xml.Xsl.XmlNodeKindFlags kinds, class System.Xml.Xsl.Qil.QilName ndName, valuetype [System.Xml]System.Xml.TriState orSelf)
0x4da10  ldc.i4.1
0x4da11  ret
0x4da12  ldarg.0
0x4da13  ldarg.1
0x4da14  ldstr    aIterdesc// "$$$iterDesc"
0x4da19  ldtoken  System.Xml.Xsl.Runtime.DescendantMergeIterator
0x4da1e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4da23  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::DescMergeCreate
0x4da28  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::DescMergeNext
0x4da2d  ldloc.1
0x4da2e  ldloc.2
0x4da2f  ldloc.s  4
0x4da31  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x4da36  ldc.i4.s 0x48
0x4da38  beq.s    loc_4DA3D
0x4da3a  ldc.i4.1
0x4da3b  br.s     loc_4DA3E
0x4da3d  ldc.i4.0
0x4da3e  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::CreateContainerIterator(class System.Xml.Xsl.Qil.QilUnary ndDod, string iterName, class [mscorlib]System.Type iterType, class [mscorlib]System.Reflection.MethodInfo methCreate, class [mscorlib]System.Reflection.MethodInfo methNext, valuetype System.Xml.Xsl.XmlNodeKindFlags kinds, class System.Xml.Xsl.Qil.QilName ndName, valuetype [System.Xml]System.Xml.TriState orSelf)
0x4da43  ldc.i4.1
0x4da44  ret
0x4da45  ldarg.0
0x4da46  ldarg.1
0x4da47  ldstr    aIterfoll// "$$$iterFoll"
0x4da4c  ldtoken  System.Xml.Xsl.Runtime.XPathFollowingMergeIterator
0x4da51  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4da56  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::XPFollMergeCreate
0x4da5b  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::XPFollMergeNext
0x4da60  ldloc.1
0x4da61  ldloc.2
0x4da62  ldc.i4.m1
0x4da63  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::CreateContainerIterator(class System.Xml.Xsl.Qil.QilUnary ndDod, string iterName, class [mscorlib]System.Type iterType, class [mscorlib]System.Reflection.MethodInfo methCreate, class [mscorlib]System.Reflection.MethodInfo methNext, valuetype System.Xml.Xsl.XmlNodeKindFlags kinds, class System.Xml.Xsl.Qil.QilName ndName, valuetype [System.Xml]System.Xml.TriState orSelf)
0x4da68  ldc.i4.1
0x4da69  ret
0x4da6a  ldarg.0
0x4da6b  ldarg.1
0x4da6c  ldstr    aIterfollsib// "$$$iterFollSib"
0x4da71  ldtoken  System.Xml.Xsl.Runtime.FollowingSiblingMergeIterator
0x4da76  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4da7b  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::FollSibMergeCreate
0x4da80  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::FollSibMergeNext
0x4da85  ldloc.1
0x4da86  ldloc.2
0x4da87  ldc.i4.m1
0x4da88  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::CreateContainerIterator(class System.Xml.Xsl.Qil.QilUnary ndDod, string iterName, class [mscorlib]System.Type iterType, class [mscorlib]System.Reflection.MethodInfo methCreate, class [mscorlib]System.Reflection.MethodInfo methNext, valuetype System.Xml.Xsl.XmlNodeKindFlags kinds, class System.Xml.Xsl.Qil.QilName ndName, valuetype [System.Xml]System.Xml.TriState orSelf)
0x4da8d  ldc.i4.1
0x4da8e  ret
0x4da8f  ldarg.0
0x4da90  ldarg.1
0x4da91  ldstr    aIterprec// "$$$iterPrec"
0x4da96  ldtoken  System.Xml.Xsl.Runtime.XPathPrecedingMergeIterator
0x4da9b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4daa0  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::XPPrecMergeCreate
0x4daa5  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::XPPrecMergeNext
0x4daaa  ldloc.1
0x4daab  ldloc.2
0x4daac  ldc.i4.m1
0x4daad  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::CreateContainerIterator(class System.Xml.Xsl.Qil.QilUnary ndDod, string iterName, class [mscorlib]System.Type iterType, class [mscorlib]System.Reflection.MethodInfo methCreate, class [mscorlib]System.Reflection.MethodInfo methNext, valuetype System.Xml.Xsl.XmlNodeKindFlags kinds, class System.Xml.Xsl.Qil.QilName ndName, valuetype [System.Xml]System.Xml.TriState orSelf)
0x4dab2  ldc.i4.1
0x4dab3  ret
0x4dab4  ldloc.s  6
0x4dab6  ldc.i4.1
0x4dab7  callvirt instance object System.Xml.Xsl.IlGen.OptimizerPatterns::GetArgument(valuetype System.Xml.Xsl.IlGen.OptimizerPatternArgument argNum)
0x4dabc  castclass System.Xml.Xsl.Qil.QilNode
0x4dac1  stloc.3
0x4dac2  ldloc.s  4
0x4dac4  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x4dac9  stloc.s  8
0x4dacb  ldloc.s  8
0x4dacd  ldc.i4.s 0x4A
0x4dacf  sub
0x4dad0  ldc.i4.1
0x4dad1  ble.un.s loc_4DAE4
0x4dad3  ldloc.s  8
0x4dad5  ldc.i4.s 0x4E
0x4dad7  beq.s    loc_4DB18
0x4dad9  ldloc.s  8
0x4dadb  ldc.i4.s 0x63
0x4dadd  beq.s    loc_4DB3E
0x4dadf  br       loc_4DC67
0x4dae4  ldarg.0
0x4dae5  ldloc.3
0x4dae6  ldstr    aIteranc// "$$$iterAnc"
0x4daeb  ldtoken  System.Xml.Xsl.Runtime.AncestorDocOrderIterator
0x4daf0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4daf5  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::AncDOCreate
0x4dafa  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::AncDONext
0x4daff  ldloc.1
0x4db00  ldloc.2
0x4db01  ldloc.s  4
0x4db03  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x4db08  ldc.i4.s 0x4A
0x4db0a  beq.s    loc_4DB0F
0x4db0c  ldc.i4.1
0x4db0d  br.s     loc_4DB10
0x4db0f  ldc.i4.0
0x4db10  ldnull
0x4db11  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::CreateFilteredIterator(class System.Xml.Xsl.Qil.QilNode ndCtxt, string iterName, class [mscorlib]System.Type iterType, class [mscorlib]System.Reflection.MethodInfo methCreate, class [mscorlib]System.Reflection.MethodInfo methNext, valuetype System.Xml.Xsl.XmlNodeKindFlags kinds, class System.Xml.Xsl.Qil.QilName ndName, valuetype [System.Xml]System.Xml.TriState orSelf, class System.Xml.Xsl.Qil.QilNode ndEnd)
0x4db16  ldc.i4.1
0x4db17  ret
0x4db18  ldarg.0
0x4db19  ldloc.3
0x4db1a  ldstr    aIterpresib// "$$$iterPreSib"
0x4db1f  ldtoken  System.Xml.Xsl.Runtime.PrecedingSiblingDocOrderIterator
0x4db24  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4db29  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::PreSibDOCreate
0x4db2e  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::PreSibDONext
0x4db33  ldloc.1
0x4db34  ldloc.2
0x4db35  ldc.i4.m1
0x4db36  ldnull
0x4db37  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::CreateFilteredIterator(class System.Xml.Xsl.Qil.QilNode ndCtxt, string iterName, class [mscorlib]System.Type iterType, class [mscorlib]System.Reflection.MethodInfo methCreate, class [mscorlib]System.Reflection.MethodInfo methNext, valuetype System.Xml.Xsl.XmlNodeKindFlags kinds, class System.Xml.Xsl.Qil.QilName ndName, valuetype [System.Xml]System.Xml.TriState orSelf, class System.Xml.Xsl.Qil.QilNode ndEnd)
0x4db3c  ldc.i4.1
0x4db3d  ret
0x4db3e  ldarg.0
0x4db3f  ldloc.3
0x4db40  ldstr    aIterprec// "$$$iterPrec"
0x4db45  ldtoken  System.Xml.Xsl.Runtime.XPathPrecedingDocOrderIterator
0x4db4a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4db4f  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::XPPrecDOCreate
0x4db54  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::XPPrecDONext
0x4db59  ldloc.1
0x4db5a  ldloc.2
0x4db5b  ldc.i4.m1
0x4db5c  ldnull
0x4db5d  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::CreateFilteredIterator(class System.Xml.Xsl.Qil.QilNode ndCtxt, string iterName, class [mscorlib]System.Type iterType, class [mscorlib]System.Reflection.MethodInfo methCreate, class [mscorlib]System.Reflection.MethodInfo methNext, valuetype System.Xml.Xsl.XmlNodeKindFlags kinds, class System.Xml.Xsl.Qil.QilName ndName, valuetype [System.Xml]System.Xml.TriState orSelf, class System.Xml.Xsl.Qil.QilNode ndEnd)
0x4db62  ldc.i4.1
0x4db63  ret
0x4db64  ldloc.0
0x4db65  ldc.i4.s 0x10
0x4db67  callvirt instance bool System.Xml.Xsl.IlGen.OptimizerPatterns::MatchesPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x4db6c  brfalse  loc_4DC67
0x4db71  ldarg.0
0x4db72  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4db77  ldstr    aDodmerge// "$$$dodMerge"
0x4db7c  ldtoken  System.Xml.Xsl.Runtime.DodSequenceMerge
0x4db81  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4db86  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Xsl.IlGen.GenerateHelper::DeclareLocal(string name, class [mscorlib]System.Type type)
0x4db8b  stloc.s  9
0x4db8d  ldarg.0
0x4db8e  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4db93  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.GenerateHelper::DefineLabel()
0x4db98  stloc.s  0xA
0x4db9a  ldarg.0
0x4db9b  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4dba0  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloca
0x4dba5  ldloc.s  9
0x4dba7  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4dbac  ldarg.0
0x4dbad  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4dbb2  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadQueryRuntime()
0x4dbb7  ldarg.0
0x4dbb8  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4dbbd  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::DodMergeCreate
0x4dbc2  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x4dbc7  ldarg.0
0x4dbc8  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4dbcd  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloca
0x4dbd2  ldloc.s  9
0x4dbd4  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4dbd9  ldarg.0
0x4dbda  ldarg.1
0x4dbdb  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilUnary::get_Child()
0x4dbe0  ldloc.s  0xA
0x4dbe2  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::StartNestedIterator(class System.Xml.Xsl.Qil.QilNode nd, valuetype [mscorlib]System.Reflection.Emit.Label lblOnEnd)
0x4dbe7  ldarg.0
0x4dbe8  ldarg.1
0x4dbe9  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilUnary::get_Child()
0x4dbee  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::Visit(class System.Xml.Xsl.Qil.QilNode n)
0x4dbf3  pop
0x4dbf4  ldarg.0
0x4dbf5  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4dbfa  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureStack()
0x4dbff  ldarg.0
0x4dc00  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4dc05  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::DodMergeAdd
0x4dc0a  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x4dc0f  ldarg.0
0x4dc10  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4dc15  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloca
0x4dc1a  ldloc.s  9
0x4dc1c  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4dc21  ldarg.0
0x4dc22  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4dc27  ldloc.s  0xA
0x4dc29  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::LoopToEnd(valuetype [mscorlib]System.Reflection.Emit.Label lblOnEnd)
0x4dc2e  ldarg.0
0x4dc2f  ldarg.1
0x4dc30  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilUnary::get_Child()
0x4dc35  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::EndNestedIterator(class System.Xml.Xsl.Qil.QilNode nd)
0x4dc3a  ldarg.0
0x4dc3b  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4dc40  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::DodMergeSeq
0x4dc45  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x4dc4a  ldarg.0
0x4dc4b  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4dc50  ldtoken  [System.Xml]System.Xml.XPath.XPathNavigator
0x4dc55  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4dc5a  ldc.i4.1
0x4dc5b  call     valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.StorageDescriptor::Stack(class [mscorlib]System.Type itemStorageType, bool isCached)
0x4dc60  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::set_Storage(valuetype System.Xml.Xsl.IlGen.StorageDescriptor value)
  ... truncated ...
```
