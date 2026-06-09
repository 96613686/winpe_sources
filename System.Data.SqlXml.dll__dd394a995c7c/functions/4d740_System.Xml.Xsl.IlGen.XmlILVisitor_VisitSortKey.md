# System.Xml.Xsl.IlGen.XmlILVisitor::VisitSortKey

- ea: `0x4d740`
- end: `0x4d89b`
- name: `System.Xml.Xsl.IlGen.XmlILVisitor::VisitSortKey`
- size: `347`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config`

## callers

- `0x4d520`

## callees

- `0x2370`
- `0x373b0`
- `0x376a0`
- `0x376c0`
- `0x39070`
- `0x39090`
- `0x3a690`
- `0x3f060`
- `0x3f180`
- `0x3f3e0`
- `0x3f950`
- `0x3fd40`
- `0x3ff00`
- `0x3ff10`
- `0x3fff0`
- `0x40040`
- `0x407e0`
- `0x40820`
- `0x40fe0`
- `0x4d740`
- `0x504d0`
- `0x504f0`
- `0x506d0`
- `0x50a90`

## pseudocode

```c

```

## disassembly

```asm
0x4d740  ldarg.0
0x4d741  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d746  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloca
0x4d74b  ldarg.2
0x4d74c  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4d751  ldarg.1
0x4d752  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilSortKey::get_Collation()
0x4d757  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x4d75c  ldc.i4.s 0x14
0x4d75e  bne.un.s loc_4D78D
0x4d760  ldarg.0
0x4d761  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d766  ldarg.0
0x4d767  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d76c  callvirt instance class System.Xml.Xsl.IlGen.StaticDataManager System.Xml.Xsl.IlGen.GenerateHelper::get_StaticData()
0x4d771  ldarg.1
0x4d772  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilSortKey::get_Collation()
0x4d777  castclass System.Xml.Xsl.Qil.QilLiteral
0x4d77c  call     string System.Xml.Xsl.Qil.QilLiteral::op_Implicit(class System.Xml.Xsl.Qil.QilLiteral literal)
0x4d781  callvirt instance int32 System.Xml.Xsl.IlGen.StaticDataManager::DeclareCollation(string collation)
0x4d786  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::CallGetCollation(int32 idxName)
0x4d78b  br.s     loc_4D7B4
0x4d78d  ldarg.0
0x4d78e  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d793  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadQueryRuntime()
0x4d798  ldarg.0
0x4d799  ldarg.1
0x4d79a  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilSortKey::get_Collation()
0x4d79f  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisitEnsureStack(class System.Xml.Xsl.Qil.QilNode nd)
0x4d7a4  ldarg.0
0x4d7a5  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d7aa  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::CreateCollation
0x4d7af  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x4d7b4  ldarg.1
0x4d7b5  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4d7ba  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsSingleton()
0x4d7bf  brfalse.s loc_4D7E4
0x4d7c1  ldarg.0
0x4d7c2  ldarg.1
0x4d7c3  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilSortKey::get_Key()
0x4d7c8  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisitEnsureStack(class System.Xml.Xsl.Qil.QilNode nd)
0x4d7cd  ldarg.0
0x4d7ce  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d7d3  ldarg.1
0x4d7d4  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilSortKey::get_Key()
0x4d7d9  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4d7de  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::AddSortKey(class System.Xml.Xsl.XmlQueryType keyType)
0x4d7e3  ret
0x4d7e4  ldarg.0
0x4d7e5  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d7ea  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.GenerateHelper::DefineLabel()
0x4d7ef  stloc.0
0x4d7f0  ldarg.0
0x4d7f1  ldarg.1
0x4d7f2  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilSortKey::get_Key()
0x4d7f7  ldloc.0
0x4d7f8  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::StartNestedIterator(class System.Xml.Xsl.Qil.QilNode nd, valuetype [mscorlib]System.Reflection.Emit.Label lblOnEnd)
0x4d7fd  ldarg.0
0x4d7fe  ldarg.1
0x4d7ff  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilSortKey::get_Key()
0x4d804  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::Visit(class System.Xml.Xsl.Qil.QilNode n)
0x4d809  pop
0x4d80a  ldarg.0
0x4d80b  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4d810  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureStackNoCache()
0x4d815  ldarg.0
0x4d816  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4d81b  ldarg.1
0x4d81c  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilSortKey::get_Key()
0x4d821  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4d826  ldarg.0
0x4d827  ldarg.1
0x4d828  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilSortKey::get_Key()
0x4d82d  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILVisitor::GetItemStorageType(class System.Xml.Xsl.Qil.QilNode nd)
0x4d832  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureItemStorageType(class System.Xml.Xsl.XmlQueryType xmlType, class [mscorlib]System.Type storageTypeDest)
0x4d837  ldarg.0
0x4d838  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d83d  ldarg.1
0x4d83e  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilSortKey::get_Key()
0x4d843  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4d848  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::AddSortKey(class System.Xml.Xsl.XmlQueryType keyType)
0x4d84d  ldarg.0
0x4d84e  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d853  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.GenerateHelper::DefineLabel()
0x4d858  stloc.1
0x4d859  ldarg.0
0x4d85a  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d85f  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Br_S
0x4d864  ldloc.1
0x4d865  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::EmitUnconditionalBranch(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, valuetype [mscorlib]System.Reflection.Emit.Label lblTarget)
0x4d86a  ldarg.0
0x4d86b  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d870  ldloc.0
0x4d871  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label lbl)
0x4d876  ldarg.0
0x4d877  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d87c  ldnull
0x4d87d  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::AddSortKey(class System.Xml.Xsl.XmlQueryType keyType)
0x4d882  ldarg.0
0x4d883  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d888  ldloc.1
0x4d889  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label lbl)
0x4d88e  ldarg.0
0x4d88f  ldarg.1
0x4d890  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilSortKey::get_Key()
0x4d895  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::EndNestedIterator(class System.Xml.Xsl.Qil.QilNode nd)
0x4d89a  ret
```
