# System.Xml.Xsl.IlGen.XmlILVisitor::VisitConditional

- ea: `0x4b810`
- end: `0x4ba69`
- name: `System.Xml.Xsl.IlGen.XmlILVisitor::VisitConditional`
- size: `601`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: `registry_config`

## callees

- `0x2370`
- `0x376a0`
- `0x376c0`
- `0x37740`
- `0x39240`
- `0x39260`
- `0x39280`
- `0x3f170`
- `0x3ff00`
- `0x3ff10`
- `0x3ffd0`
- `0x3fff0`
- `0x40040`
- `0x400e0`
- `0x40150`
- `0x40320`
- `0x40330`
- `0x405b0`
- `0x41350`
- `0x41490`
- `0x4b810`
- `0x4ba70`
- `0x50650`
- `0x50720`
- `0x50740`
- `0x50a90`

## pseudocode

```c

```

## disassembly

```asm
0x4b810  ldarg.1
0x4b811  call     class System.Xml.Xsl.IlGen.XmlILConstructInfo System.Xml.Xsl.IlGen.XmlILConstructInfo::Read(class System.Xml.Xsl.Qil.QilNode nd)
0x4b816  stloc.0
0x4b817  ldloc.0
0x4b818  callvirt instance valuetype System.Xml.Xsl.IlGen.XmlILConstructMethod System.Xml.Xsl.IlGen.XmlILConstructInfo::get_ConstructMethod()
0x4b81d  ldc.i4.1
0x4b81e  bne.un   loc_4B8D5
0x4b823  ldarg.0
0x4b824  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4b829  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.GenerateHelper::DefineLabel()
0x4b82e  stloc.1
0x4b82f  ldarg.0
0x4b830  ldarg.1
0x4b831  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilTernary::get_Left()
0x4b836  ldc.i4.2
0x4b837  ldloc.1
0x4b838  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisitWithBranch(class System.Xml.Xsl.Qil.QilNode nd, valuetype System.Xml.Xsl.IlGen.BranchingContext brctxt, valuetype [mscorlib]System.Reflection.Emit.Label lblBranch)
0x4b83d  ldarg.0
0x4b83e  ldarg.1
0x4b83f  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilTernary::get_Center()
0x4b844  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisit(class System.Xml.Xsl.Qil.QilNode nd)
0x4b849  ldarg.1
0x4b84a  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilTernary::get_Right()
0x4b84f  callvirt instance valuetype System.Xml.Xsl.Qil.QilNodeType System.Xml.Xsl.Qil.QilNode::get_NodeType()
0x4b854  ldc.i4.s 0x22
0x4b856  bne.un.s loc_4B87F
0x4b858  ldarg.1
0x4b859  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilTernary::get_Right()
0x4b85e  callvirt instance int32 System.Xml.Xsl.Qil.QilNode::get_Count()
0x4b863  brtrue.s loc_4B87F
0x4b865  ldarg.0
0x4b866  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4b86b  ldloc.1
0x4b86c  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label lbl)
0x4b871  ldarg.0
0x4b872  ldarg.1
0x4b873  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilTernary::get_Right()
0x4b878  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisit(class System.Xml.Xsl.Qil.QilNode nd)
0x4b87d  br.s     loc_4B8C0
0x4b87f  ldarg.0
0x4b880  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4b885  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.GenerateHelper::DefineLabel()
0x4b88a  stloc.2
0x4b88b  ldarg.0
0x4b88c  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4b891  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Br
0x4b896  ldloc.2
0x4b897  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::EmitUnconditionalBranch(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, valuetype [mscorlib]System.Reflection.Emit.Label lblTarget)
0x4b89c  ldarg.0
0x4b89d  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4b8a2  ldloc.1
0x4b8a3  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label lbl)
0x4b8a8  ldarg.0
0x4b8a9  ldarg.1
0x4b8aa  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilTernary::get_Right()
0x4b8af  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisit(class System.Xml.Xsl.Qil.QilNode nd)
0x4b8b4  ldarg.0
0x4b8b5  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4b8ba  ldloc.2
0x4b8bb  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label lbl)
0x4b8c0  ldarg.0
0x4b8c1  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4b8c6  call     valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.StorageDescriptor::None()
0x4b8cb  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::set_Storage(valuetype System.Xml.Xsl.IlGen.StorageDescriptor value)
0x4b8d0  br       loc_4BA67
0x4b8d5  ldnull
0x4b8d6  stloc.s  4
0x4b8d8  ldnull
0x4b8d9  stloc.s  5
0x4b8db  ldarg.0
0x4b8dc  ldarg.1
0x4b8dd  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILVisitor::GetItemStorageType(class System.Xml.Xsl.Qil.QilNode nd)
0x4b8e2  stloc.s  9
0x4b8e4  ldarg.0
0x4b8e5  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4b8ea  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.GenerateHelper::DefineLabel()
0x4b8ef  stloc.s  6
0x4b8f1  ldarg.1
0x4b8f2  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4b8f7  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsSingleton()
0x4b8fc  brfalse.s loc_4B90F
0x4b8fe  ldarg.0
0x4b8ff  ldarg.1
0x4b900  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilTernary::get_Left()
0x4b905  ldc.i4.2
0x4b906  ldloc.s  6
0x4b908  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisitWithBranch(class System.Xml.Xsl.Qil.QilNode nd, valuetype System.Xml.Xsl.IlGen.BranchingContext brctxt, valuetype [mscorlib]System.Reflection.Emit.Label lblBranch)
0x4b90d  br.s     loc_4B971
0x4b90f  ldarg.0
0x4b910  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4b915  ldstr    aCond// "$$$cond"
0x4b91a  ldloc.s  9
0x4b91c  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Xsl.IlGen.GenerateHelper::DeclareLocal(string name, class [mscorlib]System.Type type)
0x4b921  stloc.s  5
0x4b923  ldarg.0
0x4b924  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4b929  ldstr    aBoolresult// "$$$boolResult"
0x4b92e  ldtoken  [mscorlib]System.Boolean
0x4b933  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4b938  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Xsl.IlGen.GenerateHelper::DeclareLocal(string name, class [mscorlib]System.Type type)
0x4b93d  stloc.s  4
0x4b93f  ldarg.0
0x4b940  ldarg.1
0x4b941  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilTernary::get_Left()
0x4b946  ldloc.s  4
0x4b948  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisitEnsureLocal(class System.Xml.Xsl.Qil.QilNode nd, class [mscorlib]System.Reflection.Emit.LocalBuilder loc)
0x4b94d  ldarg.0
0x4b94e  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4b953  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloc
0x4b958  ldloc.s  4
0x4b95a  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4b95f  ldarg.0
0x4b960  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4b965  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Brfalse
0x4b96a  ldloc.s  6
0x4b96c  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, valuetype [mscorlib]System.Reflection.Emit.Label lblVal)
0x4b971  ldarg.0
0x4b972  ldarg.1
0x4b973  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilTernary::get_Center()
0x4b978  ldloc.s  9
0x4b97a  ldloc.s  5
0x4b97c  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::ConditionalBranch(class System.Xml.Xsl.Qil.QilNode ndBranch, class [mscorlib]System.Type itemStorageType, class [mscorlib]System.Reflection.Emit.LocalBuilder locResult)
0x4b981  ldarg.0
0x4b982  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterNested
0x4b987  stloc.3
0x4b988  ldarg.0
0x4b989  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4b98e  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.GenerateHelper::DefineLabel()
0x4b993  stloc.s  7
0x4b995  ldarg.0
0x4b996  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4b99b  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Br
0x4b9a0  ldloc.s  7
0x4b9a2  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::EmitUnconditionalBranch(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, valuetype [mscorlib]System.Reflection.Emit.Label lblTarget)
0x4b9a7  ldarg.0
0x4b9a8  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4b9ad  ldloc.s  6
0x4b9af  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label lbl)
0x4b9b4  ldarg.0
0x4b9b5  ldarg.1
0x4b9b6  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilTernary::get_Right()
0x4b9bb  ldloc.s  9
0x4b9bd  ldloc.s  5
0x4b9bf  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::ConditionalBranch(class System.Xml.Xsl.Qil.QilNode ndBranch, class [mscorlib]System.Type itemStorageType, class [mscorlib]System.Reflection.Emit.LocalBuilder locResult)
0x4b9c4  ldarg.1
0x4b9c5  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4b9ca  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsSingleton()
0x4b9cf  brtrue   loc_4BA5A
0x4b9d4  ldarg.0
0x4b9d5  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4b9da  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Brtrue
0x4b9df  ldloc.s  7
0x4b9e1  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::EmitUnconditionalBranch(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, valuetype [mscorlib]System.Reflection.Emit.Label lblTarget)
0x4b9e6  ldarg.0
0x4b9e7  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4b9ec  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.GenerateHelper::DefineLabel()
0x4b9f1  stloc.s  8
0x4b9f3  ldarg.0
0x4b9f4  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4b9f9  ldloc.s  8
0x4b9fb  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label lbl)
0x4ba00  ldarg.0
0x4ba01  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ba06  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloc
0x4ba0b  ldloc.s  4
0x4ba0d  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4ba12  ldarg.0
0x4ba13  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ba18  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Brtrue
0x4ba1d  ldloc.3
0x4ba1e  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.IteratorDescriptor::GetLabelNext()
0x4ba23  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, valuetype [mscorlib]System.Reflection.Emit.Label lblVal)
0x4ba28  ldarg.0
0x4ba29  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ba2e  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Br
0x4ba33  ldarg.0
0x4ba34  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterNested
0x4ba39  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.IteratorDescriptor::GetLabelNext()
0x4ba3e  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::EmitUnconditionalBranch(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, valuetype [mscorlib]System.Reflection.Emit.Label lblTarget)
0x4ba43  ldarg.0
0x4ba44  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4ba49  ldloc.s  8
0x4ba4b  ldloc.s  5
0x4ba4d  ldloc.s  9
0x4ba4f  ldc.i4.0
0x4ba50  call     valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.StorageDescriptor::Local(class [mscorlib]System.Reflection.Emit.LocalBuilder loc, class [mscorlib]System.Type itemStorageType, bool isCached)
0x4ba55  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::SetIterator(valuetype [mscorlib]System.Reflection.Emit.Label lblNext, valuetype System.Xml.Xsl.IlGen.StorageDescriptor storage)
0x4ba5a  ldarg.0
0x4ba5b  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ba60  ldloc.s  7
0x4ba62  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label lbl)
0x4ba67  ldarg.1
0x4ba68  ret
```
