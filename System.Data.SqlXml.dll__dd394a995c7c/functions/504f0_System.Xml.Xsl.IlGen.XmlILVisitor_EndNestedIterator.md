# System.Xml.Xsl.IlGen.XmlILVisitor::EndNestedIterator

- ea: `0x504f0`
- end: `0x505af`
- name: `System.Xml.Xsl.IlGen.XmlILVisitor::EndNestedIterator`
- size: `191`
- prototype: ``
- caller_count: `22`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x4a930`
- `0x4aa60`
- `0x4ad40`
- `0x4b4e0`
- `0x4bbe0`
- `0x4c350`
- `0x4c770`
- `0x4cbb0`
- `0x4cc30`
- `0x4d270`
- `0x4d420`
- `0x4d520`
- `0x4d740`
- `0x4d910`
- `0x4eb20`
- `0x4ece0`
- `0x4ee70`
- `0x4f9c0`
- `0x505b0`
- `0x50670`
- `0x50740`
- `0x50780`

## callees

- `0x376c0`
- `0x3ffd0`
- `0x400e0`
- `0x40240`
- `0x40300`
- `0x40570`
- `0x40580`
- `0x40590`
- `0x405a0`
- `0x405b0`
- `0x407e0`
- `0x40820`
- `0x504f0`

## pseudocode

```c

```

## disassembly

```asm
0x504f0  ldarg.0
0x504f1  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x504f6  callvirt instance bool System.Xml.Xsl.IlGen.IteratorDescriptor::get_IsBranching()
0x504fb  brfalse  loc_50591
0x50500  ldarg.0
0x50501  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x50506  callvirt instance valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.IteratorDescriptor::get_Storage()
0x5050b  stloc.0
0x5050c  ldloca.s 0
0x5050e  call     instance valuetype System.Xml.Xsl.IlGen.ItemLocation System.Xml.Xsl.IlGen.StorageDescriptor::get_Location()
0x50513  brfalse.s loc_50591
0x50515  ldarg.0
0x50516  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x5051b  ldarg.1
0x5051c  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x50521  ldtoken  [mscorlib]System.Boolean
0x50526  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5052b  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureItemStorageType(class System.Xml.Xsl.XmlQueryType xmlType, class [mscorlib]System.Type storageTypeDest)
0x50530  ldarg.0
0x50531  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x50536  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureStackNoCache()
0x5053b  ldarg.0
0x5053c  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x50541  callvirt instance valuetype System.Xml.Xsl.IlGen.BranchingContext System.Xml.Xsl.IlGen.IteratorDescriptor::get_CurrentBranchingContext()
0x50546  ldc.i4.1
0x50547  bne.un.s loc_50566
0x50549  ldarg.0
0x5054a  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x5054f  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Brtrue
0x50554  ldarg.0
0x50555  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x5055a  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.IteratorDescriptor::get_LabelBranch()
0x5055f  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, valuetype [mscorlib]System.Reflection.Emit.Label lblVal)
0x50564  br.s     loc_50581
0x50566  ldarg.0
0x50567  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x5056c  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Brfalse
0x50571  ldarg.0
0x50572  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x50577  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.IteratorDescriptor::get_LabelBranch()
0x5057c  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, valuetype [mscorlib]System.Reflection.Emit.Label lblVal)
0x50581  ldarg.0
0x50582  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x50587  call     valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.StorageDescriptor::None()
0x5058c  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::set_Storage(valuetype System.Xml.Xsl.IlGen.StorageDescriptor value)
0x50591  ldarg.0
0x50592  ldarg.0
0x50593  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x50598  stfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterNested
0x5059d  ldarg.0
0x5059e  ldarg.0
0x5059f  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x505a4  callvirt instance class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.IteratorDescriptor::get_ParentIterator()
0x505a9  stfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x505ae  ret
```
