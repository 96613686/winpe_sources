# System.Xml.Xsl.IlGen.XmlILVisitor::Sequence

- ea: `0x4bdc0`
- end: `0x4bfd7`
- name: `System.Xml.Xsl.IlGen.XmlILVisitor::Sequence`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config`

## callers

- `0x4bd10`

## callees

- `0x2370`
- `0x376c0`
- `0x37740`
- `0x37750`
- `0x37790`
- `0x3f070`
- `0x3f170`
- `0x3ff00`
- `0x3ff10`
- `0x3ffe0`
- `0x3fff0`
- `0x40040`
- `0x400f0`
- `0x40150`
- `0x40320`
- `0x40330`
- `0x405b0`
- `0x407b0`
- `0x40810`
- `0x40820`
- `0x4bdc0`
- `0x50670`
- `0x506d0`
- `0x50a90`

## pseudocode

```c

```

## disassembly

```asm
0x4bdc0  ldloca.s 4
0x4bdc2  initobj  [mscorlib]System.Reflection.Emit.Label
0x4bdc8  ldarg.0
0x4bdc9  ldarg.1
0x4bdca  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILVisitor::GetItemStorageType(class System.Xml.Xsl.Qil.QilNode nd)
0x4bdcf  stloc.s  7
0x4bdd1  ldarg.1
0x4bdd2  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4bdd7  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsSingleton()
0x4bddc  brfalse  loc_4BE66
0x4bde1  ldarg.1
0x4bde2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xml.Xsl.Qil.QilNode> System.Xml.Xsl.Qil.QilNode::GetEnumerator()
0x4bde7  stloc.s  8
0x4bde9  br.s     loc_4BE3B
0x4bdeb  ldloc.s  8
0x4bded  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xml.Xsl.Qil.QilNode>::get_Current()
0x4bdf2  stloc.s  9
0x4bdf4  ldloc.s  9
0x4bdf6  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4bdfb  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsSingleton()
0x4be00  brfalse.s loc_4BE0C
0x4be02  ldarg.0
0x4be03  ldloc.s  9
0x4be05  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisitEnsureStack(class System.Xml.Xsl.Qil.QilNode nd)
0x4be0a  br.s     loc_4BE3B
0x4be0c  ldarg.0
0x4be0d  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4be12  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.GenerateHelper::DefineLabel()
0x4be17  stloc.s  4
0x4be19  ldarg.0
0x4be1a  ldloc.s  9
0x4be1c  ldloc.s  4
0x4be1e  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisit(class System.Xml.Xsl.Qil.QilNode nd, valuetype [mscorlib]System.Reflection.Emit.Label lblOnEnd)
0x4be23  ldarg.0
0x4be24  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4be29  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::DiscardStack()
0x4be2e  ldarg.0
0x4be2f  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4be34  ldloc.s  4
0x4be36  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label lbl)
0x4be3b  ldloc.s  8
0x4be3d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4be42  brtrue.s loc_4BDEB
0x4be44  leave.s  loc_4BE52
0x4be46  ldloc.s  8
0x4be48  brfalse.s loc_4BE51
0x4be4a  ldloc.s  8
0x4be4c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4be51  endfinally
0x4be52  ldarg.0
0x4be53  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4be58  ldloc.s  7
0x4be5a  ldc.i4.0
0x4be5b  call     valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.StorageDescriptor::Stack(class [mscorlib]System.Type itemStorageType, bool isCached)
0x4be60  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::set_Storage(valuetype System.Xml.Xsl.IlGen.StorageDescriptor value)
0x4be65  ret
0x4be66  ldarg.0
0x4be67  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4be6c  ldstr    aItemlist// "$$$itemList"
0x4be71  ldloc.s  7
0x4be73  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Xsl.IlGen.GenerateHelper::DeclareLocal(string name, class [mscorlib]System.Type type)
0x4be78  stloc.1
0x4be79  ldarg.0
0x4be7a  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4be7f  ldstr    aIdxlist// "$$$idxList"
0x4be84  ldtoken  [mscorlib]System.Int32
0x4be89  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4be8e  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Xsl.IlGen.GenerateHelper::DeclareLocal(string name, class [mscorlib]System.Type type)
0x4be93  stloc.0
0x4be94  ldarg.1
0x4be95  callvirt instance int32 System.Xml.Xsl.Qil.QilNode::get_Count()
0x4be9a  newarr   [mscorlib]System.Reflection.Emit.Label
0x4be9f  stloc.s  5
0x4bea1  ldarg.0
0x4bea2  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4bea7  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.GenerateHelper::DefineLabel()
0x4beac  stloc.2
0x4bead  ldc.i4.0
0x4beae  stloc.s  6
0x4beb0  br       loc_4BF6D
0x4beb5  ldloc.s  6
0x4beb7  brfalse.s loc_4BEC6
0x4beb9  ldarg.0
0x4beba  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4bebf  ldloc.s  4
0x4bec1  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label lbl)
0x4bec6  ldloc.s  6
0x4bec8  ldarg.1
0x4bec9  callvirt instance int32 System.Xml.Xsl.Qil.QilNode::get_Count()
0x4bece  ldc.i4.1
0x4becf  sub
0x4bed0  bne.un.s loc_4BEE1
0x4bed2  ldarg.0
0x4bed3  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4bed8  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.IteratorDescriptor::GetLabelNext()
0x4bedd  stloc.s  4
0x4bedf  br.s     loc_4BEEE
0x4bee1  ldarg.0
0x4bee2  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4bee7  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.GenerateHelper::DefineLabel()
0x4beec  stloc.s  4
0x4beee  ldarg.0
0x4beef  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4bef4  ldloc.s  6
0x4bef6  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadInteger(int32 intVal)
0x4befb  ldarg.0
0x4befc  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4bf01  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Stloc
0x4bf06  ldloc.0
0x4bf07  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4bf0c  ldarg.0
0x4bf0d  ldarg.1
0x4bf0e  ldloc.s  6
0x4bf10  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x4bf15  ldloc.s  4
0x4bf17  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisit(class System.Xml.Xsl.Qil.QilNode nd, valuetype [mscorlib]System.Reflection.Emit.Label lblOnEnd)
0x4bf1c  ldarg.0
0x4bf1d  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4bf22  ldarg.1
0x4bf23  ldloc.s  6
0x4bf25  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x4bf2a  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4bf2f  ldloc.s  7
0x4bf31  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureItemStorageType(class System.Xml.Xsl.XmlQueryType xmlType, class [mscorlib]System.Type storageTypeDest)
0x4bf36  ldarg.0
0x4bf37  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4bf3c  ldloc.1
0x4bf3d  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureLocalNoCache(class [mscorlib]System.Reflection.Emit.LocalBuilder bldr)
0x4bf42  ldloc.s  5
0x4bf44  ldloc.s  6
0x4bf46  ldarg.0
0x4bf47  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterNested
0x4bf4c  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.IteratorDescriptor::GetLabelNext()
0x4bf51  stelem   [mscorlib]System.Reflection.Emit.Label
0x4bf56  ldarg.0
0x4bf57  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4bf5c  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Brtrue
0x4bf61  ldloc.2
0x4bf62  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::EmitUnconditionalBranch(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, valuetype [mscorlib]System.Reflection.Emit.Label lblTarget)
0x4bf67  ldloc.s  6
0x4bf69  ldc.i4.1
0x4bf6a  add
0x4bf6b  stloc.s  6
0x4bf6d  ldloc.s  6
0x4bf6f  ldarg.1
0x4bf70  callvirt instance int32 System.Xml.Xsl.Qil.QilNode::get_Count()
0x4bf75  blt      loc_4BEB5
0x4bf7a  ldarg.0
0x4bf7b  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4bf80  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.GenerateHelper::DefineLabel()
0x4bf85  stloc.3
0x4bf86  ldarg.0
0x4bf87  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4bf8c  ldloc.3
0x4bf8d  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label lbl)
0x4bf92  ldarg.0
0x4bf93  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4bf98  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloc
0x4bf9d  ldloc.0
0x4bf9e  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4bfa3  ldarg.0
0x4bfa4  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4bfa9  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Switch
0x4bfae  ldloc.s  5
0x4bfb0  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, valuetype [mscorlib]System.Reflection.Emit.Label[] arrLabels)
0x4bfb5  ldarg.0
0x4bfb6  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4bfbb  ldloc.2
0x4bfbc  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label lbl)
0x4bfc1  ldarg.0
0x4bfc2  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4bfc7  ldloc.3
0x4bfc8  ldloc.1
0x4bfc9  ldloc.s  7
0x4bfcb  ldc.i4.0
0x4bfcc  call     valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.StorageDescriptor::Local(class [mscorlib]System.Reflection.Emit.LocalBuilder loc, class [mscorlib]System.Type itemStorageType, bool isCached)
0x4bfd1  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::SetIterator(valuetype [mscorlib]System.Reflection.Emit.Label lblNext, valuetype System.Xml.Xsl.IlGen.StorageDescriptor storage)
0x4bfd6  ret
```
