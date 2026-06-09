# System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisitEnsureCache

- ea: `0x50780`
- end: `0x509b2`
- name: `System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisitEnsureCache`
- size: `562`
- prototype: ``
- caller_count: `3`
- callee_count: `25`
- tags: `registry_config`

## callers

- `0x4d8a0`
- `0x4efa0`
- `0x505b0`

## callees

- `0x2370`
- `0x376c0`
- `0x3a690`
- `0x3f170`
- `0x3f3e0`
- `0x3f420`
- `0x3ff00`
- `0x3ff40`
- `0x3fff0`
- `0x40150`
- `0x402a0`
- `0x40300`
- `0x40380`
- `0x405a0`
- `0x405b0`
- `0x406e0`
- `0x407e0`
- `0x40820`
- `0x50490`
- `0x504d0`
- `0x504f0`
- `0x50700`
- `0x50780`
- `0x509c0`
- `0x50a90`

## string_xrefs

- `0x50876`: `$$$cache`
- `0x50833`: `$$$cacheResult`

## pseudocode

```c

```

## disassembly

```asm
0x50780  ldarg.0
0x50781  ldarg.1
0x50782  call     instance bool System.Xml.Xsl.IlGen.XmlILVisitor::CachesResult(class System.Xml.Xsl.Qil.QilNode nd)
0x50787  stloc.0
0x50788  ldarg.0
0x50789  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x5078e  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.GenerateHelper::DefineLabel()
0x50793  stloc.2
0x50794  ldloc.0
0x50795  brfalse  loc_5083D
0x5079a  ldarg.0
0x5079b  ldarg.1
0x5079c  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::StartNestedIterator(class System.Xml.Xsl.Qil.QilNode nd)
0x507a1  ldarg.0
0x507a2  ldarg.1
0x507a3  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::Visit(class System.Xml.Xsl.Qil.QilNode n)
0x507a8  pop
0x507a9  ldarg.0
0x507aa  ldarg.1
0x507ab  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::EndNestedIterator(class System.Xml.Xsl.Qil.QilNode nd)
0x507b0  ldarg.0
0x507b1  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x507b6  ldarg.0
0x507b7  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterNested
0x507bc  callvirt instance valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.IteratorDescriptor::get_Storage()
0x507c1  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::set_Storage(valuetype System.Xml.Xsl.IlGen.StorageDescriptor value)
0x507c6  ldarg.0
0x507c7  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x507cc  callvirt instance valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.IteratorDescriptor::get_Storage()
0x507d1  stloc.s  5
0x507d3  ldloca.s 5
0x507d5  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.StorageDescriptor::get_ItemStorageType()
0x507da  ldarg.2
0x507db  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x507e0  brfalse.s loc_507E3
0x507e2  ret
0x507e3  ldarg.0
0x507e4  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x507e9  callvirt instance valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.IteratorDescriptor::get_Storage()
0x507ee  stloc.s  5
0x507f0  ldloca.s 5
0x507f2  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.StorageDescriptor::get_ItemStorageType()
0x507f7  ldtoken  [System.Xml]System.Xml.XPath.XPathNavigator
0x507fc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x50801  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x50806  brtrue.s loc_5081A
0x50808  ldarg.2
0x50809  ldtoken  [System.Xml]System.Xml.XPath.XPathNavigator
0x5080e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x50813  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x50818  brfalse.s loc_5082D
0x5081a  ldarg.0
0x5081b  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x50820  ldarg.1
0x50821  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x50826  ldarg.2
0x50827  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureItemStorageType(class System.Xml.Xsl.XmlQueryType xmlType, class [mscorlib]System.Type storageTypeDest)
0x5082c  ret
0x5082d  ldarg.0
0x5082e  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x50833  ldstr    aCacheresult// "$$$cacheResult"
0x50838  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureNoStack(string locName)
0x5083d  ldarg.0
0x5083e  ldarg.1
0x5083f  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILVisitor::GetItemStorageType(class System.Xml.Xsl.Qil.QilNode nd)
0x50844  ldtoken  [System.Xml]System.Xml.XPath.XPathNavigator
0x50849  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5084e  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x50853  brtrue.s loc_50858
0x50855  ldarg.2
0x50856  br.s     loc_50862
0x50858  ldtoken  [System.Xml]System.Xml.XPath.XPathNavigator
0x5085d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x50862  stloc.3
0x50863  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class System.Xml.Xsl.IlGen.XmlILStorageMethods> System.Xml.Xsl.IlGen.XmlILMethods::StorageMethods
0x50868  ldloc.3
0x50869  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class System.Xml.Xsl.IlGen.XmlILStorageMethods>::get_Item(void)
0x5086e  stloc.s  4
0x50870  ldarg.0
0x50871  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x50876  ldstr    aCache// "$$$cache"
0x5087b  ldloc.s  4
0x5087d  ldfld    class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILStorageMethods::SeqType
0x50882  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Xsl.IlGen.GenerateHelper::DeclareLocal(string name, class [mscorlib]System.Type type)
0x50887  stloc.1
0x50888  ldarg.0
0x50889  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x5088e  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloc
0x50893  ldloc.1
0x50894  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x50899  ldarg.1
0x5089a  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x5089f  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsSingleton()
0x508a4  brfalse.s loc_508D7
0x508a6  ldarg.0
0x508a7  ldarg.1
0x508a8  ldloc.3
0x508a9  ldc.i4.0
0x508aa  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisitEnsureStack(class System.Xml.Xsl.Qil.QilNode nd, class [mscorlib]System.Type itemStorageType, bool isCached)
0x508af  ldarg.0
0x508b0  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x508b5  ldloc.s  4
0x508b7  ldfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::SeqReuseSgl
0x508bc  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::CallToken(class [mscorlib]System.Reflection.MethodInfo meth)
0x508c1  ldarg.0
0x508c2  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x508c7  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Stloc
0x508cc  ldloc.1
0x508cd  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x508d2  br       loc_5099E
0x508d7  ldarg.0
0x508d8  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x508dd  ldloc.s  4
0x508df  ldfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::SeqReuse
0x508e4  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::CallToken(class [mscorlib]System.Reflection.MethodInfo meth)
0x508e9  ldarg.0
0x508ea  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x508ef  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Stloc
0x508f4  ldloc.1
0x508f5  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x508fa  ldarg.0
0x508fb  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x50900  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloc
0x50905  ldloc.1
0x50906  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x5090b  ldarg.0
0x5090c  ldarg.1
0x5090d  ldloc.2
0x5090e  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::StartNestedIterator(class System.Xml.Xsl.Qil.QilNode nd, valuetype [mscorlib]System.Reflection.Emit.Label lblOnEnd)
0x50913  ldloc.0
0x50914  brfalse.s loc_50933
0x50916  ldarg.0
0x50917  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x5091c  ldarg.0
0x5091d  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x50922  callvirt instance class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.IteratorDescriptor::get_ParentIterator()
0x50927  callvirt instance valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.IteratorDescriptor::get_Storage()
0x5092c  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::set_Storage(valuetype System.Xml.Xsl.IlGen.StorageDescriptor value)
0x50931  br.s     loc_5093B
0x50933  ldarg.0
0x50934  ldarg.1
0x50935  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::Visit(class System.Xml.Xsl.Qil.QilNode n)
0x5093a  pop
0x5093b  ldarg.0
0x5093c  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x50941  ldarg.1
0x50942  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x50947  ldloc.3
0x50948  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureItemStorageType(class System.Xml.Xsl.XmlQueryType xmlType, class [mscorlib]System.Type storageTypeDest)
0x5094d  ldarg.0
0x5094e  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x50953  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureStackNoCache()
0x50958  ldarg.0
0x50959  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x5095e  ldloc.s  4
0x50960  ldfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::SeqAdd
0x50965  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x5096a  ldarg.0
0x5096b  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x50970  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloc
0x50975  ldloc.1
0x50976  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x5097b  ldarg.0
0x5097c  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x50981  ldloc.2
0x50982  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::LoopToEnd(valuetype [mscorlib]System.Reflection.Emit.Label lblOnEnd)
0x50987  ldarg.0
0x50988  ldarg.1
0x50989  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::EndNestedIterator(class System.Xml.Xsl.Qil.QilNode nd)
0x5098e  ldarg.0
0x5098f  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x50994  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Pop
0x50999  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode)
0x5099e  ldarg.0
0x5099f  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x509a4  ldloc.1
0x509a5  ldarg.2
0x509a6  ldc.i4.1
0x509a7  call     valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.StorageDescriptor::Local(class [mscorlib]System.Reflection.Emit.LocalBuilder loc, class [mscorlib]System.Type itemStorageType, bool isCached)
0x509ac  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::set_Storage(valuetype System.Xml.Xsl.IlGen.StorageDescriptor value)
0x509b1  ret
```
