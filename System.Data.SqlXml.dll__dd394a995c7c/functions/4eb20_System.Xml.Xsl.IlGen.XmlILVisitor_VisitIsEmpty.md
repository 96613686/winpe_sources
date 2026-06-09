# System.Xml.Xsl.IlGen.XmlILVisitor::VisitIsEmpty

- ea: `0x4eb20`
- end: `0x4ecdf`
- name: `System.Xml.Xsl.IlGen.XmlILVisitor::VisitIsEmpty`
- size: `447`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config`

## callees

- `0x3a530`
- `0x3a690`
- `0x3f2d0`
- `0x3f360`
- `0x3fca0`
- `0x3ff00`
- `0x3ff10`
- `0x3ffd0`
- `0x40040`
- `0x400e0`
- `0x400f0`
- `0x402a0`
- `0x403f0`
- `0x40570`
- `0x40580`
- `0x40590`
- `0x405a0`
- `0x405b0`
- `0x407b0`
- `0x4eb20`
- `0x504d0`
- `0x504f0`
- `0x506d0`
- `0x509c0`

## pseudocode

```c

```

## disassembly

```asm
0x4eb20  ldarg.0
0x4eb21  ldarg.1
0x4eb22  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilUnary::get_Child()
0x4eb27  call     instance bool System.Xml.Xsl.IlGen.XmlILVisitor::CachesResult(class System.Xml.Xsl.Qil.QilNode nd)
0x4eb2c  brfalse  loc_4EBE0
0x4eb31  ldarg.0
0x4eb32  ldarg.1
0x4eb33  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilUnary::get_Child()
0x4eb38  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisitEnsureStack(class System.Xml.Xsl.Qil.QilNode nd)
0x4eb3d  ldarg.0
0x4eb3e  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4eb43  ldarg.0
0x4eb44  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterNested
0x4eb49  callvirt instance valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.IteratorDescriptor::get_Storage()
0x4eb4e  stloc.1
0x4eb4f  ldloca.s 1
0x4eb51  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.StorageDescriptor::get_ItemStorageType()
0x4eb56  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::CallCacheCount(class [mscorlib]System.Type itemStorageType)
0x4eb5b  ldarg.0
0x4eb5c  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4eb61  callvirt instance valuetype System.Xml.Xsl.IlGen.BranchingContext System.Xml.Xsl.IlGen.IteratorDescriptor::get_CurrentBranchingContext()
0x4eb66  stloc.2
0x4eb67  ldloc.2
0x4eb68  ldc.i4.1
0x4eb69  beq.s    loc_4EB90
0x4eb6b  ldloc.2
0x4eb6c  ldc.i4.2
0x4eb6d  bne.un.s loc_4EBB1
0x4eb6f  ldarg.0
0x4eb70  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4eb75  ldc.i4.0
0x4eb76  ldarg.0
0x4eb77  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4eb7c  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.IteratorDescriptor::get_LabelBranch()
0x4eb81  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Bne_Un
0x4eb86  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::TestAndBranch(int32 i4, valuetype [mscorlib]System.Reflection.Emit.Label lblBranch, valuetype [mscorlib]System.Reflection.Emit.OpCode opcodeBranch)
0x4eb8b  br       loc_4ECA3
0x4eb90  ldarg.0
0x4eb91  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4eb96  ldc.i4.0
0x4eb97  ldarg.0
0x4eb98  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4eb9d  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.IteratorDescriptor::get_LabelBranch()
0x4eba2  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Beq
0x4eba7  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::TestAndBranch(int32 i4, valuetype [mscorlib]System.Reflection.Emit.Label lblBranch, valuetype [mscorlib]System.Reflection.Emit.OpCode opcodeBranch)
0x4ebac  br       loc_4ECA3
0x4ebb1  ldarg.0
0x4ebb2  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ebb7  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.GenerateHelper::DefineLabel()
0x4ebbc  stloc.0
0x4ebbd  ldarg.0
0x4ebbe  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ebc3  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Brfalse_S
0x4ebc8  ldloc.0
0x4ebc9  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, valuetype [mscorlib]System.Reflection.Emit.Label lblVal)
0x4ebce  ldarg.0
0x4ebcf  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ebd4  ldloc.0
0x4ebd5  ldc.i4.1
0x4ebd6  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::ConvBranchToBool(valuetype [mscorlib]System.Reflection.Emit.Label lblBranch, bool isTrueBranch)
0x4ebdb  br       loc_4ECA3
0x4ebe0  ldarg.0
0x4ebe1  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ebe6  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.GenerateHelper::DefineLabel()
0x4ebeb  stloc.3
0x4ebec  ldarg.0
0x4ebed  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4ebf2  stloc.s  4
0x4ebf4  ldloc.s  4
0x4ebf6  callvirt instance valuetype System.Xml.Xsl.IlGen.BranchingContext System.Xml.Xsl.IlGen.IteratorDescriptor::get_CurrentBranchingContext()
0x4ebfb  ldc.i4.1
0x4ebfc  bne.un.s loc_4EC17
0x4ebfe  ldarg.0
0x4ebff  ldarg.1
0x4ec00  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilUnary::get_Child()
0x4ec05  ldarg.0
0x4ec06  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4ec0b  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.IteratorDescriptor::get_LabelBranch()
0x4ec10  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::StartNestedIterator(class System.Xml.Xsl.Qil.QilNode nd, valuetype [mscorlib]System.Reflection.Emit.Label lblOnEnd)
0x4ec15  br.s     loc_4EC24
0x4ec17  ldarg.0
0x4ec18  ldarg.1
0x4ec19  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilUnary::get_Child()
0x4ec1e  ldloc.3
0x4ec1f  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::StartNestedIterator(class System.Xml.Xsl.Qil.QilNode nd, valuetype [mscorlib]System.Reflection.Emit.Label lblOnEnd)
0x4ec24  ldarg.0
0x4ec25  ldarg.1
0x4ec26  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilUnary::get_Child()
0x4ec2b  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::Visit(class System.Xml.Xsl.Qil.QilNode n)
0x4ec30  pop
0x4ec31  ldarg.0
0x4ec32  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4ec37  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureNoCache()
0x4ec3c  ldarg.0
0x4ec3d  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4ec42  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::DiscardStack()
0x4ec47  ldloc.s  4
0x4ec49  callvirt instance valuetype System.Xml.Xsl.IlGen.BranchingContext System.Xml.Xsl.IlGen.IteratorDescriptor::get_CurrentBranchingContext()
0x4ec4e  stloc.s  5
0x4ec50  ldloc.s  5
0x4ec52  switch   loc_4EC8A, loc_4EC97, loc_4EC65
0x4ec63  br.s     loc_4EC97
0x4ec65  ldarg.0
0x4ec66  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ec6b  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Br
0x4ec70  ldloc.s  4
0x4ec72  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.IteratorDescriptor::get_LabelBranch()
0x4ec77  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::EmitUnconditionalBranch(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, valuetype [mscorlib]System.Reflection.Emit.Label lblTarget)
0x4ec7c  ldarg.0
0x4ec7d  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ec82  ldloc.3
0x4ec83  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label lbl)
0x4ec88  br.s     loc_4EC97
0x4ec8a  ldarg.0
0x4ec8b  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ec90  ldloc.3
0x4ec91  ldc.i4.1
0x4ec92  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::ConvBranchToBool(valuetype [mscorlib]System.Reflection.Emit.Label lblBranch, bool isTrueBranch)
0x4ec97  ldarg.0
0x4ec98  ldarg.1
0x4ec99  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilUnary::get_Child()
0x4ec9e  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::EndNestedIterator(class System.Xml.Xsl.Qil.QilNode nd)
0x4eca3  ldarg.0
0x4eca4  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4eca9  callvirt instance bool System.Xml.Xsl.IlGen.IteratorDescriptor::get_IsBranching()
0x4ecae  brfalse.s loc_4ECC2
0x4ecb0  ldarg.0
0x4ecb1  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4ecb6  call     valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.StorageDescriptor::None()
0x4ecbb  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::set_Storage(valuetype System.Xml.Xsl.IlGen.StorageDescriptor value)
0x4ecc0  br.s     loc_4ECDD
0x4ecc2  ldarg.0
0x4ecc3  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4ecc8  ldtoken  [mscorlib]System.Boolean
0x4eccd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4ecd2  ldc.i4.0
0x4ecd3  call     valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.StorageDescriptor::Stack(class [mscorlib]System.Type itemStorageType, bool isCached)
0x4ecd8  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::set_Storage(valuetype System.Xml.Xsl.IlGen.StorageDescriptor value)
0x4ecdd  ldarg.1
0x4ecde  ret
```
