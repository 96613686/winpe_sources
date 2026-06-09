# System.Xml.Xsl.IlGen.XmlILVisitor::VisitSort

- ea: `0x4d520`
- end: `0x4d73f`
- name: `System.Xml.Xsl.IlGen.XmlILVisitor::VisitSort`
- size: `543`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config`

## callees

- `0x37430`
- `0x37450`
- `0x376c0`
- `0x37790`
- `0x3f170`
- `0x3f3e0`
- `0x3f420`
- `0x3ff00`
- `0x3ff40`
- `0x3fff0`
- `0x40150`
- `0x40350`
- `0x40380`
- `0x405b0`
- `0x407e0`
- `0x40820`
- `0x4d200`
- `0x4d4b0`
- `0x4d520`
- `0x4d740`
- `0x504d0`
- `0x504f0`
- `0x50a90`

## string_xrefs

- `0x4d547`: `$$$cache`

## pseudocode

```c

```

## disassembly

```asm
0x4d520  ldarg.0
0x4d521  ldarg.1
0x4d522  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILVisitor::GetItemStorageType(class System.Xml.Xsl.Qil.QilNode nd)
0x4d527  stloc.0
0x4d528  ldarg.0
0x4d529  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d52e  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.GenerateHelper::DefineLabel()
0x4d533  stloc.3
0x4d534  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class System.Xml.Xsl.IlGen.XmlILStorageMethods> System.Xml.Xsl.IlGen.XmlILMethods::StorageMethods
0x4d539  ldloc.0
0x4d53a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class System.Xml.Xsl.IlGen.XmlILStorageMethods>::get_Item(void)
0x4d53f  stloc.s  4
0x4d541  ldarg.0
0x4d542  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d547  ldstr    aCache// "$$$cache"
0x4d54c  ldloc.s  4
0x4d54e  ldfld    class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILStorageMethods::SeqType
0x4d553  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Xsl.IlGen.GenerateHelper::DeclareLocal(string name, class [mscorlib]System.Type type)
0x4d558  stloc.1
0x4d559  ldarg.0
0x4d55a  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d55f  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloc
0x4d564  ldloc.1
0x4d565  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4d56a  ldarg.0
0x4d56b  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d570  ldloc.s  4
0x4d572  ldfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::SeqReuse
0x4d577  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::CallToken(class [mscorlib]System.Reflection.MethodInfo meth)
0x4d57c  ldarg.0
0x4d57d  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d582  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Stloc
0x4d587  ldloc.1
0x4d588  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4d58d  ldarg.0
0x4d58e  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d593  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloc
0x4d598  ldloc.1
0x4d599  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4d59e  ldarg.0
0x4d59f  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d5a4  ldstr    aKeys// "$$$keys"
0x4d5a9  ldtoken  System.Xml.Xsl.Runtime.XmlSortKeyAccumulator
0x4d5ae  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4d5b3  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Xsl.IlGen.GenerateHelper::DeclareLocal(string name, class [mscorlib]System.Type type)
0x4d5b8  stloc.2
0x4d5b9  ldarg.0
0x4d5ba  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d5bf  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloca
0x4d5c4  ldloc.2
0x4d5c5  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4d5ca  ldarg.0
0x4d5cb  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d5d0  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::SortKeyCreate
0x4d5d5  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x4d5da  ldarg.0
0x4d5db  ldarg.1
0x4d5dc  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilLoop::get_Variable()
0x4d5e1  ldloc.3
0x4d5e2  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::StartNestedIterator(class System.Xml.Xsl.Qil.QilNode nd, valuetype [mscorlib]System.Reflection.Emit.Label lblOnEnd)
0x4d5e7  ldarg.0
0x4d5e8  ldarg.1
0x4d5e9  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilLoop::get_Variable()
0x4d5ee  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::StartBinding(class System.Xml.Xsl.Qil.QilIterator ndIter)
0x4d5f3  ldarg.0
0x4d5f4  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4d5f9  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureStackNoCache()
0x4d5fe  ldarg.0
0x4d5ff  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4d604  ldarg.1
0x4d605  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilLoop::get_Variable()
0x4d60a  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4d60f  ldarg.0
0x4d610  ldarg.1
0x4d611  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilLoop::get_Variable()
0x4d616  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILVisitor::GetItemStorageType(class System.Xml.Xsl.Qil.QilNode nd)
0x4d61b  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureItemStorageType(class System.Xml.Xsl.XmlQueryType xmlType, class [mscorlib]System.Type storageTypeDest)
0x4d620  ldarg.0
0x4d621  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d626  ldloc.s  4
0x4d628  ldfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::SeqAdd
0x4d62d  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x4d632  ldarg.0
0x4d633  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d638  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloca
0x4d63d  ldloc.2
0x4d63e  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4d643  ldarg.1
0x4d644  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilLoop::get_Body()
0x4d649  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xml.Xsl.Qil.QilNode> System.Xml.Xsl.Qil.QilNode::GetEnumerator()
0x4d64e  stloc.s  5
0x4d650  br.s     loc_4D669
0x4d652  ldloc.s  5
0x4d654  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xml.Xsl.Qil.QilNode>::get_Current()
0x4d659  castclass System.Xml.Xsl.Qil.QilSortKey
0x4d65e  stloc.s  6
0x4d660  ldarg.0
0x4d661  ldloc.s  6
0x4d663  ldloc.2
0x4d664  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::VisitSortKey(class System.Xml.Xsl.Qil.QilSortKey ndKey, class [mscorlib]System.Reflection.Emit.LocalBuilder locKeys)
0x4d669  ldloc.s  5
0x4d66b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4d670  brtrue.s loc_4D652
0x4d672  leave.s  loc_4D680
0x4d674  ldloc.s  5
0x4d676  brfalse.s loc_4D67F
0x4d678  ldloc.s  5
0x4d67a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4d67f  endfinally
0x4d680  ldarg.0
0x4d681  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d686  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::SortKeyFinish
0x4d68b  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x4d690  ldarg.0
0x4d691  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d696  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloc
0x4d69b  ldloc.1
0x4d69c  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4d6a1  ldarg.0
0x4d6a2  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4d6a7  ldloc.3
0x4d6a8  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::LoopToEnd(valuetype [mscorlib]System.Reflection.Emit.Label lblOnEnd)
0x4d6ad  ldarg.0
0x4d6ae  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d6b3  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Pop
0x4d6b8  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode)
0x4d6bd  ldarg.0
0x4d6be  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d6c3  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloc
0x4d6c8  ldloc.1
0x4d6c9  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4d6ce  ldarg.0
0x4d6cf  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d6d4  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloca
0x4d6d9  ldloc.2
0x4d6da  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4d6df  ldarg.0
0x4d6e0  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d6e5  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::SortKeyKeys
0x4d6ea  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x4d6ef  ldarg.0
0x4d6f0  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d6f5  ldloc.s  4
0x4d6f7  ldfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::SeqSortByKeys
0x4d6fc  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x4d701  ldarg.0
0x4d702  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4d707  ldloc.1
0x4d708  ldloc.0
0x4d709  ldc.i4.1
0x4d70a  call     valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.StorageDescriptor::Local(class [mscorlib]System.Reflection.Emit.LocalBuilder loc, class [mscorlib]System.Type itemStorageType, bool isCached)
0x4d70f  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::set_Storage(valuetype System.Xml.Xsl.IlGen.StorageDescriptor value)
0x4d714  ldarg.0
0x4d715  ldarg.1
0x4d716  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilLoop::get_Variable()
0x4d71b  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::EndBinding(class System.Xml.Xsl.Qil.QilIterator ndIter)
0x4d720  ldarg.0
0x4d721  ldarg.1
0x4d722  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilLoop::get_Variable()
0x4d727  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::EndNestedIterator(class System.Xml.Xsl.Qil.QilNode nd)
0x4d72c  ldarg.0
0x4d72d  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4d732  ldarg.0
0x4d733  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterNested
0x4d738  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::SetIterator(class System.Xml.Xsl.IlGen.IteratorDescriptor iterInfo)
0x4d73d  ldarg.1
0x4d73e  ret
```
