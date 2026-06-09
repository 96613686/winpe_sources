# System.Xml.Xsl.IlGen.XmlILVisitor::HandleFilterPatterns

- ea: `0x4cc30`
- end: `0x4d1fe`
- name: `System.Xml.Xsl.IlGen.XmlILVisitor::HandleFilterPatterns`
- size: `1486`
- prototype: ``
- caller_count: `1`
- callee_count: `38`
- tags: `registry_config`

## callers

- `0x4cbb0`

## callees

- `0x1fc0`
- `0x35940`
- `0x374b0`
- `0x374d0`
- `0x376a0`
- `0x376c0`
- `0x3a690`
- `0x3af20`
- `0x3f060`
- `0x3f070`
- `0x3f170`
- `0x3f180`
- `0x3f3e0`
- `0x3f880`
- `0x3ff00`
- `0x3ff10`
- `0x3ff40`
- `0x3ffd0`
- `0x3fff0`
- `0x400f0`
- `0x40380`
- `0x405b0`
- `0x407e0`
- `0x40820`
- `0x409c0`
- `0x40c00`
- `0x40c60`
- `0x40db0`
- `0x4cc30`
- `0x4d200`
- `0x4d4b0`
- `0x4f8f0`
- `0x4f940`
- `0x4fa80`
- `0x503a0`
- `0x504d0`
- `0x504f0`
- `0x506d0`

## pseudocode

```c

```

## disassembly

```asm
0x4cc30  ldarg.1
0x4cc31  call     class System.Xml.Xsl.IlGen.OptimizerPatterns System.Xml.Xsl.IlGen.OptimizerPatterns::Read(class System.Xml.Xsl.Qil.QilNode nd)
0x4cc36  stloc.0
0x4cc37  ldloc.0
0x4cc38  ldc.i4.5
0x4cc39  callvirt instance bool System.Xml.Xsl.IlGen.OptimizerPatterns::MatchesPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x4cc3e  stloc.s  6
0x4cc40  ldloc.s  6
0x4cc42  brtrue.s loc_4CC50
0x4cc44  ldloc.0
0x4cc45  ldc.i4.4
0x4cc46  callvirt instance bool System.Xml.Xsl.IlGen.OptimizerPatterns::MatchesPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x4cc4b  brfalse  loc_4CFB7
0x4cc50  ldloc.s  6
0x4cc52  brfalse.s loc_4CC65
0x4cc54  ldc.i4.2
0x4cc55  stloc.2
0x4cc56  ldloc.0
0x4cc57  ldc.i4.2
0x4cc58  callvirt instance object System.Xml.Xsl.IlGen.OptimizerPatterns::GetArgument(valuetype System.Xml.Xsl.IlGen.OptimizerPatternArgument argNum)
0x4cc5d  castclass System.Xml.Xsl.Qil.QilName
0x4cc62  stloc.3
0x4cc63  br.s     loc_4CC79
0x4cc65  ldloc.0
0x4cc66  ldc.i4.2
0x4cc67  callvirt instance object System.Xml.Xsl.IlGen.OptimizerPatterns::GetArgument(valuetype System.Xml.Xsl.IlGen.OptimizerPatternArgument argNum)
0x4cc6c  castclass System.Xml.Xsl.XmlQueryType
0x4cc71  callvirt instance valuetype System.Xml.Xsl.XmlNodeKindFlags System.Xml.Xsl.XmlQueryType::get_NodeKinds()
0x4cc76  stloc.2
0x4cc77  ldnull
0x4cc78  stloc.3
0x4cc79  ldloc.0
0x4cc7a  ldc.i4.0
0x4cc7b  callvirt instance object System.Xml.Xsl.IlGen.OptimizerPatterns::GetArgument(valuetype System.Xml.Xsl.IlGen.OptimizerPatternArgument argNum)
0x4cc80  castclass System.Xml.Xsl.Qil.QilNode
0x4cc85  stloc.s  5
0x4cc87  ldloc.0
0x4cc88  ldc.i4.1
0x4cc89  callvirt instance object System.Xml.Xsl.IlGen.OptimizerPatterns::GetArgument(valuetype System.Xml.Xsl.IlGen.OptimizerPatternArgument argNum)
0x4cc8e  castclass System.Xml.Xsl.Qil.QilNode
0x4cc93  stloc.s  4
0x4cc95  ldloc.s  5
0x4cc97  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x4cc9c  stloc.s  7
0x4cc9e  ldloc.s  7
0x4cca0  ldc.i4.s 0x43
0x4cca2  sub
0x4cca3  switch   loc_4CCF3, loc_4D1FC, loc_4CE31, loc_4D1FC, loc_4D1FC, loc_4CE8D, loc_4CE8D, loc_4CE58, loc_4CE58, loc_4CEC2, loc_4CEE9, loc_4CF10, loc_4CF37
0x4ccdc  ldloc.s  7
0x4ccde  ldc.i4.s 0x62
0x4cce0  beq      loc_4CF69
0x4cce5  ldloc.s  7
0x4cce7  ldc.i4.s 0x63
0x4cce9  beq      loc_4CF90
0x4ccee  br       loc_4D1FC
0x4ccf3  ldloc.s  6
0x4ccf5  brfalse  loc_4CD9B
0x4ccfa  ldarg.0
0x4ccfb  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4cd00  ldstr    aIterelemconten// "$$$iterElemContent"
0x4cd05  ldtoken  System.Xml.Xsl.Runtime.ElementContentIterator
0x4cd0a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4cd0f  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Xsl.IlGen.GenerateHelper::DeclareLocal(string name, class [mscorlib]System.Type type)
0x4cd14  stloc.1
0x4cd15  ldarg.0
0x4cd16  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4cd1b  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloca
0x4cd20  ldloc.1
0x4cd21  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4cd26  ldarg.0
0x4cd27  ldloc.s  4
0x4cd29  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisitEnsureStack(class System.Xml.Xsl.Qil.QilNode nd)
0x4cd2e  ldarg.0
0x4cd2f  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4cd34  ldarg.0
0x4cd35  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4cd3a  callvirt instance class System.Xml.Xsl.IlGen.StaticDataManager System.Xml.Xsl.IlGen.GenerateHelper::get_StaticData()
0x4cd3f  ldloc.3
0x4cd40  callvirt instance string System.Xml.Xsl.Qil.QilName::get_LocalName()
0x4cd45  callvirt instance int32 System.Xml.Xsl.IlGen.StaticDataManager::DeclareName(string name)
0x4cd4a  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::CallGetAtomizedName(int32 idxName)
0x4cd4f  ldarg.0
0x4cd50  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4cd55  ldarg.0
0x4cd56  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4cd5b  callvirt instance class System.Xml.Xsl.IlGen.StaticDataManager System.Xml.Xsl.IlGen.GenerateHelper::get_StaticData()
0x4cd60  ldloc.3
0x4cd61  callvirt instance string System.Xml.Xsl.Qil.QilName::get_NamespaceUri()
0x4cd66  callvirt instance int32 System.Xml.Xsl.IlGen.StaticDataManager::DeclareName(string name)
0x4cd6b  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::CallGetAtomizedName(int32 idxName)
0x4cd70  ldarg.0
0x4cd71  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4cd76  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::ElemContentCreate
0x4cd7b  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x4cd80  ldarg.0
0x4cd81  ldtoken  [System.Xml]System.Xml.XPath.XPathNavigator
0x4cd86  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4cd8b  ldloc.1
0x4cd8c  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::ElemContentNext
0x4cd91  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::GenerateSimpleIterator(class [mscorlib]System.Type itemStorageType, class [mscorlib]System.Reflection.Emit.LocalBuilder locIter, class [mscorlib]System.Reflection.MethodInfo methNext)
0x4cd96  br       loc_4CE2F
0x4cd9b  ldloc.2
0x4cd9c  ldc.i4.s 0x3A
0x4cd9e  bne.un.s loc_4CDC3
0x4cda0  ldarg.0
0x4cda1  ldloc.s  4
0x4cda3  ldstr    aItercontent// "$$$iterContent"
0x4cda8  ldtoken  System.Xml.Xsl.Runtime.ContentIterator
0x4cdad  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4cdb2  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::ContentCreate
0x4cdb7  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::ContentNext
0x4cdbc  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::CreateSimpleIterator(class System.Xml.Xsl.Qil.QilNode ndCtxt, string iterName, class [mscorlib]System.Type iterType, class [mscorlib]System.Reflection.MethodInfo methCreate, class [mscorlib]System.Reflection.MethodInfo methNext)
0x4cdc1  br.s     loc_4CE2F
0x4cdc3  ldarg.0
0x4cdc4  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4cdc9  ldstr    aItercontent// "$$$iterContent"
0x4cdce  ldtoken  System.Xml.Xsl.Runtime.NodeKindContentIterator
0x4cdd3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4cdd8  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Xsl.IlGen.GenerateHelper::DeclareLocal(string name, class [mscorlib]System.Type type)
0x4cddd  stloc.1
0x4cdde  ldarg.0
0x4cddf  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4cde4  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloca
0x4cde9  ldloc.1
0x4cdea  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4cdef  ldarg.0
0x4cdf0  ldloc.s  4
0x4cdf2  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisitEnsureStack(class System.Xml.Xsl.Qil.QilNode nd)
0x4cdf7  ldarg.0
0x4cdf8  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4cdfd  ldarg.0
0x4cdfe  ldloc.2
0x4cdff  call     instance valuetype [System.Xml]System.Xml.XPath.XPathNodeType System.Xml.Xsl.IlGen.XmlILVisitor::QilXmlToXPathNodeType(valuetype System.Xml.Xsl.XmlNodeKindFlags xmlTypes)
0x4ce04  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadInteger(int32 intVal)
0x4ce09  ldarg.0
0x4ce0a  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ce0f  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::KindContentCreate
0x4ce14  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x4ce19  ldarg.0
0x4ce1a  ldtoken  [System.Xml]System.Xml.XPath.XPathNavigator
0x4ce1f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4ce24  ldloc.1
0x4ce25  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::KindContentNext
0x4ce2a  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::GenerateSimpleIterator(class [mscorlib]System.Type itemStorageType, class [mscorlib]System.Reflection.Emit.LocalBuilder locIter, class [mscorlib]System.Reflection.MethodInfo methNext)
0x4ce2f  ldc.i4.1
0x4ce30  ret
0x4ce31  ldarg.0
0x4ce32  ldloc.s  4
0x4ce34  ldstr    aIterpar// "$$$iterPar"
0x4ce39  ldtoken  System.Xml.Xsl.Runtime.ParentIterator
0x4ce3e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4ce43  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::ParentCreate
0x4ce48  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::ParentNext
0x4ce4d  ldloc.2
0x4ce4e  ldloc.3
0x4ce4f  ldc.i4.m1
0x4ce50  ldnull
0x4ce51  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::CreateFilteredIterator(class System.Xml.Xsl.Qil.QilNode ndCtxt, string iterName, class [mscorlib]System.Type iterType, class [mscorlib]System.Reflection.MethodInfo methCreate, class [mscorlib]System.Reflection.MethodInfo methNext, valuetype System.Xml.Xsl.XmlNodeKindFlags kinds, class System.Xml.Xsl.Qil.QilName ndName, valuetype [System.Xml]System.Xml.TriState orSelf, class System.Xml.Xsl.Qil.QilNode ndEnd)
0x4ce56  ldc.i4.1
0x4ce57  ret
0x4ce58  ldarg.0
0x4ce59  ldloc.s  4
0x4ce5b  ldstr    aIteranc// "$$$iterAnc"
0x4ce60  ldtoken  System.Xml.Xsl.Runtime.AncestorIterator
0x4ce65  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4ce6a  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::AncCreate
0x4ce6f  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::AncNext
0x4ce74  ldloc.2
0x4ce75  ldloc.3
0x4ce76  ldloc.s  5
0x4ce78  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x4ce7d  ldc.i4.s 0x4A
0x4ce7f  beq.s    loc_4CE84
0x4ce81  ldc.i4.1
0x4ce82  br.s     loc_4CE85
0x4ce84  ldc.i4.0
0x4ce85  ldnull
0x4ce86  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::CreateFilteredIterator(class System.Xml.Xsl.Qil.QilNode ndCtxt, string iterName, class [mscorlib]System.Type iterType, class [mscorlib]System.Reflection.MethodInfo methCreate, class [mscorlib]System.Reflection.MethodInfo methNext, valuetype System.Xml.Xsl.XmlNodeKindFlags kinds, class System.Xml.Xsl.Qil.QilName ndName, valuetype [System.Xml]System.Xml.TriState orSelf, class System.Xml.Xsl.Qil.QilNode ndEnd)
0x4ce8b  ldc.i4.1
0x4ce8c  ret
0x4ce8d  ldarg.0
0x4ce8e  ldloc.s  4
0x4ce90  ldstr    aIterdesc// "$$$iterDesc"
0x4ce95  ldtoken  System.Xml.Xsl.Runtime.DescendantIterator
0x4ce9a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4ce9f  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::DescCreate
0x4cea4  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::DescNext
0x4cea9  ldloc.2
0x4ceaa  ldloc.3
0x4ceab  ldloc.s  5
0x4cead  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x4ceb2  ldc.i4.s 0x48
0x4ceb4  beq.s    loc_4CEB9
0x4ceb6  ldc.i4.1
0x4ceb7  br.s     loc_4CEBA
0x4ceb9  ldc.i4.0
0x4ceba  ldnull
0x4cebb  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::CreateFilteredIterator(class System.Xml.Xsl.Qil.QilNode ndCtxt, string iterName, class [mscorlib]System.Type iterType, class [mscorlib]System.Reflection.MethodInfo methCreate, class [mscorlib]System.Reflection.MethodInfo methNext, valuetype System.Xml.Xsl.XmlNodeKindFlags kinds, class System.Xml.Xsl.Qil.QilName ndName, valuetype [System.Xml]System.Xml.TriState orSelf, class System.Xml.Xsl.Qil.QilNode ndEnd)
0x4cec0  ldc.i4.1
0x4cec1  ret
0x4cec2  ldarg.0
0x4cec3  ldloc.s  4
0x4cec5  ldstr    aIterprec// "$$$iterPrec"
0x4ceca  ldtoken  System.Xml.Xsl.Runtime.PrecedingIterator
0x4cecf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4ced4  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::PrecCreate
0x4ced9  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::PrecNext
0x4cede  ldloc.2
0x4cedf  ldloc.3
0x4cee0  ldc.i4.m1
0x4cee1  ldnull
0x4cee2  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::CreateFilteredIterator(class System.Xml.Xsl.Qil.QilNode ndCtxt, string iterName, class [mscorlib]System.Type iterType, class [mscorlib]System.Reflection.MethodInfo methCreate, class [mscorlib]System.Reflection.MethodInfo methNext, valuetype System.Xml.Xsl.XmlNodeKindFlags kinds, class System.Xml.Xsl.Qil.QilName ndName, valuetype [System.Xml]System.Xml.TriState orSelf, class System.Xml.Xsl.Qil.QilNode ndEnd)
0x4cee7  ldc.i4.1
0x4cee8  ret
0x4cee9  ldarg.0
0x4ceea  ldloc.s  4
0x4ceec  ldstr    aIterfollsib// "$$$iterFollSib"
0x4cef1  ldtoken  System.Xml.Xsl.Runtime.FollowingSiblingIterator
0x4cef6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4cefb  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::FollSibCreate
0x4cf00  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::FollSibNext
0x4cf05  ldloc.2
0x4cf06  ldloc.3
0x4cf07  ldc.i4.m1
0x4cf08  ldnull
0x4cf09  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::CreateFilteredIterator(class System.Xml.Xsl.Qil.QilNode ndCtxt, string iterName, class [mscorlib]System.Type iterType, class [mscorlib]System.Reflection.MethodInfo methCreate, class [mscorlib]System.Reflection.MethodInfo methNext, valuetype System.Xml.Xsl.XmlNodeKindFlags kinds, class System.Xml.Xsl.Qil.QilName ndName, valuetype [System.Xml]System.Xml.TriState orSelf, class System.Xml.Xsl.Qil.QilNode ndEnd)
0x4cf0e  ldc.i4.1
0x4cf0f  ret
0x4cf10  ldarg.0
0x4cf11  ldloc.s  4
0x4cf13  ldstr    aIterpresib// "$$$iterPreSib"
0x4cf18  ldtoken  System.Xml.Xsl.Runtime.PrecedingSiblingIterator
0x4cf1d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4cf22  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::PreSibCreate
0x4cf27  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::PreSibNext
0x4cf2c  ldloc.2
0x4cf2d  ldloc.3
0x4cf2e  ldc.i4.m1
0x4cf2f  ldnull
0x4cf30  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::CreateFilteredIterator(class System.Xml.Xsl.Qil.QilNode ndCtxt, string iterName, class [mscorlib]System.Type iterType, class [mscorlib]System.Reflection.MethodInfo methCreate, class [mscorlib]System.Reflection.MethodInfo methNext, valuetype System.Xml.Xsl.XmlNodeKindFlags kinds, class System.Xml.Xsl.Qil.QilName ndName, valuetype [System.Xml]System.Xml.TriState orSelf, class System.Xml.Xsl.Qil.QilNode ndEnd)
0x4cf35  ldc.i4.1
0x4cf36  ret
0x4cf37  ldarg.0
0x4cf38  ldloc.s  4
0x4cf3a  ldstr    aIterrange// "$$$iterRange"
0x4cf3f  ldtoken  System.Xml.Xsl.Runtime.NodeRangeIterator
0x4cf44  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4cf49  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::NodeRangeCreate
0x4cf4e  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::NodeRangeNext
0x4cf53  ldloc.2
0x4cf54  ldloc.3
0x4cf55  ldc.i4.m1
0x4cf56  ldloc.s  5
0x4cf58  castclass System.Xml.Xsl.Qil.QilBinary
0x4cf5d  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilBinary::get_Right()
0x4cf62  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::CreateFilteredIterator(class System.Xml.Xsl.Qil.QilNode ndCtxt, string iterName, class [mscorlib]System.Type iterType, class [mscorlib]System.Reflection.MethodInfo methCreate, class [mscorlib]System.Reflection.MethodInfo methNext, valuetype System.Xml.Xsl.XmlNodeKindFlags kinds, class System.Xml.Xsl.Qil.QilName ndName, valuetype [System.Xml]System.Xml.TriState orSelf, class System.Xml.Xsl.Qil.QilNode ndEnd)
0x4cf67  ldc.i4.1
0x4cf68  ret
0x4cf69  ldarg.0
0x4cf6a  ldloc.s  4
0x4cf6c  ldstr    aIterfoll// "$$$iterFoll"
0x4cf71  ldtoken  System.Xml.Xsl.Runtime.XPathFollowingIterator
0x4cf76  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4cf7b  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::XPFollCreate
0x4cf80  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::XPFollNext
0x4cf85  ldloc.2
0x4cf86  ldloc.3
0x4cf87  ldc.i4.m1
0x4cf88  ldnull
0x4cf89  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::CreateFilteredIterator(class System.Xml.Xsl.Qil.QilNode ndCtxt, string iterName, class [mscorlib]System.Type iterType, class [mscorlib]System.Reflection.MethodInfo methCreate, class [mscorlib]System.Reflection.MethodInfo methNext, valuetype System.Xml.Xsl.XmlNodeKindFlags kinds, class System.Xml.Xsl.Qil.QilName ndName, valuetype [System.Xml]System.Xml.TriState orSelf, class System.Xml.Xsl.Qil.QilNode ndEnd)
0x4cf8e  ldc.i4.1
0x4cf8f  ret
0x4cf90  ldarg.0
0x4cf91  ldloc.s  4
0x4cf93  ldstr    aIterprec// "$$$iterPrec"
0x4cf98  ldtoken  System.Xml.Xsl.Runtime.XPathPrecedingIterator
0x4cf9d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4cfa2  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::XPPrecCreate
0x4cfa7  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::XPPrecNext
0x4cfac  ldloc.2
0x4cfad  ldloc.3
0x4cfae  ldc.i4.m1
0x4cfaf  ldnull
0x4cfb0  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::CreateFilteredIterator(class System.Xml.Xsl.Qil.QilNode ndCtxt, string iterName, class [mscorlib]System.Type iterType, class [mscorlib]System.Reflection.MethodInfo methCreate, class [mscorlib]System.Reflection.MethodInfo methNext, valuetype System.Xml.Xsl.XmlNodeKindFlags kinds, class System.Xml.Xsl.Qil.QilName ndName, valuetype [System.Xml]System.Xml.TriState orSelf, class System.Xml.Xsl.Qil.QilNode ndEnd)
0x4cfb5  ldc.i4.1
0x4cfb6  ret
0x4cfb7  ldloc.0
0x4cfb8  ldc.i4.3
0x4cfb9  callvirt instance bool System.Xml.Xsl.IlGen.OptimizerPatterns::MatchesPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x4cfbe  brfalse.s loc_4CFF1
0x4cfc0  ldloc.0
0x4cfc1  ldc.i4.1
0x4cfc2  callvirt instance object System.Xml.Xsl.IlGen.OptimizerPatterns::GetArgument(valuetype System.Xml.Xsl.IlGen.OptimizerPatternArgument argNum)
0x4cfc7  castclass System.Xml.Xsl.Qil.QilNode
0x4cfcc  stloc.s  4
0x4cfce  ldarg.0
0x4cfcf  ldloc.s  4
0x4cfd1  ldstr    aIterattr// "$$$iterAttr"
0x4cfd6  ldtoken  System.Xml.Xsl.Runtime.AttributeIterator
0x4cfdb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
  ... truncated ...
```
