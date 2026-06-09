# System.Xml.Xsl.IlGen.XmlILVisitor::CreateAggregator

- ea: `0x4c350`
- end: `0x4c489`
- name: `System.Xml.Xsl.IlGen.XmlILVisitor::CreateAggregator`
- size: `313`
- prototype: ``
- caller_count: `4`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x4c290`
- `0x4c2c0`
- `0x4c2f0`
- `0x4c320`

## callees

- `0x2390`
- `0x376c0`
- `0x3a530`
- `0x3a690`
- `0x3f170`
- `0x3f3e0`
- `0x3ff00`
- `0x3ffd0`
- `0x3fff0`
- `0x400f0`
- `0x40320`
- `0x40380`
- `0x405b0`
- `0x407e0`
- `0x40820`
- `0x4c350`
- `0x504d0`
- `0x504f0`
- `0x50a90`

## pseudocode

```c

```

## disassembly

```asm
0x4c350  ldarg.0
0x4c351  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c356  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.GenerateHelper::DefineLabel()
0x4c35b  stloc.0
0x4c35c  ldarg.s  4
0x4c35e  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.MemberInfo::get_DeclaringType()
0x4c363  stloc.1
0x4c364  ldarg.0
0x4c365  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c36a  ldarg.2
0x4c36b  ldloc.1
0x4c36c  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Xsl.IlGen.GenerateHelper::DeclareLocal(string name, class [mscorlib]System.Type type)
0x4c371  stloc.2
0x4c372  ldarg.0
0x4c373  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c378  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloca
0x4c37d  ldloc.2
0x4c37e  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4c383  ldarg.0
0x4c384  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c389  ldarg.3
0x4c38a  ldfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::AggCreate
0x4c38f  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x4c394  ldarg.0
0x4c395  ldarg.1
0x4c396  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilUnary::get_Child()
0x4c39b  ldloc.0
0x4c39c  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::StartNestedIterator(class System.Xml.Xsl.Qil.QilNode nd, valuetype [mscorlib]System.Reflection.Emit.Label lblOnEnd)
0x4c3a1  ldarg.0
0x4c3a2  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c3a7  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloca
0x4c3ac  ldloc.2
0x4c3ad  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4c3b2  ldarg.0
0x4c3b3  ldarg.1
0x4c3b4  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilUnary::get_Child()
0x4c3b9  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::Visit(class System.Xml.Xsl.Qil.QilNode n)
0x4c3be  pop
0x4c3bf  ldarg.0
0x4c3c0  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4c3c5  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureStackNoCache()
0x4c3ca  ldarg.0
0x4c3cb  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4c3d0  ldarg.1
0x4c3d1  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4c3d6  ldarg.0
0x4c3d7  ldarg.1
0x4c3d8  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILVisitor::GetItemStorageType(class System.Xml.Xsl.Qil.QilNode nd)
0x4c3dd  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureItemStorageType(class System.Xml.Xsl.XmlQueryType xmlType, class [mscorlib]System.Type storageTypeDest)
0x4c3e2  ldarg.0
0x4c3e3  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c3e8  ldarg.s  4
0x4c3ea  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x4c3ef  ldarg.0
0x4c3f0  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c3f5  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloca
0x4c3fa  ldloc.2
0x4c3fb  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4c400  ldarg.0
0x4c401  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4c406  ldloc.0
0x4c407  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::LoopToEnd(valuetype [mscorlib]System.Reflection.Emit.Label lblOnEnd)
0x4c40c  ldarg.0
0x4c40d  ldarg.1
0x4c40e  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilUnary::get_Child()
0x4c413  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::EndNestedIterator(class System.Xml.Xsl.Qil.QilNode nd)
0x4c418  ldarg.1
0x4c419  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4c41e  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_MaybeEmpty()
0x4c423  brfalse.s loc_4C462
0x4c425  ldarg.0
0x4c426  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c42b  ldarg.3
0x4c42c  ldfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::AggIsEmpty
0x4c431  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x4c436  ldarg.0
0x4c437  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c43c  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Brtrue
0x4c441  ldarg.0
0x4c442  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4c447  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.IteratorDescriptor::GetLabelNext()
0x4c44c  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, valuetype [mscorlib]System.Reflection.Emit.Label lblVal)
0x4c451  ldarg.0
0x4c452  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c457  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloca
0x4c45c  ldloc.2
0x4c45d  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4c462  ldarg.0
0x4c463  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c468  ldarg.s  5
0x4c46a  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x4c46f  ldarg.0
0x4c470  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4c475  ldarg.0
0x4c476  ldarg.1
0x4c477  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILVisitor::GetItemStorageType(class System.Xml.Xsl.Qil.QilNode nd)
0x4c47c  ldc.i4.0
0x4c47d  call     valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.StorageDescriptor::Stack(class [mscorlib]System.Type itemStorageType, bool isCached)
0x4c482  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::set_Storage(valuetype System.Xml.Xsl.IlGen.StorageDescriptor value)
0x4c487  ldarg.1
0x4c488  ret
```
