# System.Xml.Xsl.IlGen.XmlILVisitor::CreateSetIterator

- ea: `0x4c070`
- end: `0x4c286`
- name: `System.Xml.Xsl.IlGen.XmlILVisitor::CreateSetIterator`
- size: `534`
- prototype: ``
- caller_count: `3`
- callee_count: `20`
- tags: `registry_config`

## callers

- `0x4bfe0`
- `0x4c010`
- `0x4c040`

## callees

- `0x2370`
- `0x35920`
- `0x35940`
- `0x376c0`
- `0x3f170`
- `0x3f180`
- `0x3f3e0`
- `0x3ff00`
- `0x3ff10`
- `0x3ff40`
- `0x3ffe0`
- `0x3fff0`
- `0x40040`
- `0x40180`
- `0x40320`
- `0x40330`
- `0x405b0`
- `0x40770`
- `0x4c070`
- `0x50670`

## pseudocode

```c

```

## disassembly

```asm
0x4c070  ldarg.0
0x4c071  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c076  ldarg.2
0x4c077  ldarg.3
0x4c078  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Xsl.IlGen.GenerateHelper::DeclareLocal(string name, class [mscorlib]System.Type type)
0x4c07d  stloc.0
0x4c07e  ldarg.0
0x4c07f  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c084  ldstr    aNavset// "$$$navSet"
0x4c089  ldtoken  [System.Xml]System.Xml.XPath.XPathNavigator
0x4c08e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4c093  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Xsl.IlGen.GenerateHelper::DeclareLocal(string name, class [mscorlib]System.Type type)
0x4c098  stloc.1
0x4c099  ldarg.0
0x4c09a  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c09f  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloca
0x4c0a4  ldloc.0
0x4c0a5  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4c0aa  ldarg.0
0x4c0ab  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c0b0  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadQueryRuntime()
0x4c0b5  ldarg.0
0x4c0b6  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c0bb  ldarg.s  4
0x4c0bd  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x4c0c2  ldarg.0
0x4c0c3  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c0c8  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.GenerateHelper::DefineLabel()
0x4c0cd  stloc.2
0x4c0ce  ldarg.0
0x4c0cf  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c0d4  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.GenerateHelper::DefineLabel()
0x4c0d9  stloc.3
0x4c0da  ldarg.0
0x4c0db  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c0e0  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.GenerateHelper::DefineLabel()
0x4c0e5  stloc.s  6
0x4c0e7  ldarg.0
0x4c0e8  ldarg.1
0x4c0e9  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilBinary::get_Left()
0x4c0ee  ldloc.2
0x4c0ef  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisit(class System.Xml.Xsl.Qil.QilNode nd, valuetype [mscorlib]System.Reflection.Emit.Label lblOnEnd)
0x4c0f4  ldarg.0
0x4c0f5  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterNested
0x4c0fa  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.IteratorDescriptor::GetLabelNext()
0x4c0ff  stloc.s  4
0x4c101  ldarg.0
0x4c102  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4c107  ldloc.1
0x4c108  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureLocal(class [mscorlib]System.Reflection.Emit.LocalBuilder bldr)
0x4c10d  ldarg.0
0x4c10e  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c113  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Brtrue
0x4c118  ldloc.3
0x4c119  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::EmitUnconditionalBranch(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, valuetype [mscorlib]System.Reflection.Emit.Label lblTarget)
0x4c11e  ldarg.0
0x4c11f  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c124  ldloc.s  6
0x4c126  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label lbl)
0x4c12b  ldarg.0
0x4c12c  ldarg.1
0x4c12d  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilBinary::get_Right()
0x4c132  ldloc.2
0x4c133  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisit(class System.Xml.Xsl.Qil.QilNode nd, valuetype [mscorlib]System.Reflection.Emit.Label lblOnEnd)
0x4c138  ldarg.0
0x4c139  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterNested
0x4c13e  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.IteratorDescriptor::GetLabelNext()
0x4c143  stloc.s  5
0x4c145  ldarg.0
0x4c146  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4c14b  ldloc.1
0x4c14c  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureLocal(class [mscorlib]System.Reflection.Emit.LocalBuilder bldr)
0x4c151  ldarg.0
0x4c152  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c157  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Brtrue
0x4c15c  ldloc.3
0x4c15d  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::EmitUnconditionalBranch(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, valuetype [mscorlib]System.Reflection.Emit.Label lblTarget)
0x4c162  ldarg.0
0x4c163  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c168  ldloc.2
0x4c169  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label lbl)
0x4c16e  ldarg.0
0x4c16f  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c174  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldnull
0x4c179  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode)
0x4c17e  ldarg.0
0x4c17f  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c184  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Stloc
0x4c189  ldloc.1
0x4c18a  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4c18f  ldarg.0
0x4c190  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c195  ldloc.3
0x4c196  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label lbl)
0x4c19b  ldarg.0
0x4c19c  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c1a1  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloca
0x4c1a6  ldloc.0
0x4c1a7  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4c1ac  ldarg.0
0x4c1ad  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c1b2  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloc
0x4c1b7  ldloc.1
0x4c1b8  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4c1bd  ldarg.0
0x4c1be  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c1c3  ldarg.s  5
0x4c1c5  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x4c1ca  ldarg.1
0x4c1cb  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4c1d0  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsSingleton()
0x4c1d5  brfalse.s loc_4C225
0x4c1d7  ldarg.0
0x4c1d8  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c1dd  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Switch
0x4c1e2  ldc.i4.3
0x4c1e3  newarr   [mscorlib]System.Reflection.Emit.Label
0x4c1e8  dup
0x4c1e9  ldc.i4.0
0x4c1ea  ldloc.s  6
0x4c1ec  stelem   [mscorlib]System.Reflection.Emit.Label
0x4c1f1  dup
0x4c1f2  ldc.i4.1
0x4c1f3  ldloc.s  4
0x4c1f5  stelem   [mscorlib]System.Reflection.Emit.Label
0x4c1fa  dup
0x4c1fb  ldc.i4.2
0x4c1fc  ldloc.s  5
0x4c1fe  stelem   [mscorlib]System.Reflection.Emit.Label
0x4c203  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, valuetype [mscorlib]System.Reflection.Emit.Label[] arrLabels)
0x4c208  ldarg.0
0x4c209  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4c20e  ldloc.0
0x4c20f  ldtoken  [System.Xml]System.Xml.XPath.XPathNavigator
0x4c214  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4c219  call     valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.StorageDescriptor::Current(class [mscorlib]System.Reflection.Emit.LocalBuilder locIter, class [mscorlib]System.Type itemStorageType)
0x4c21e  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::set_Storage(valuetype System.Xml.Xsl.IlGen.StorageDescriptor value)
0x4c223  br.s     loc_4C284
0x4c225  ldarg.0
0x4c226  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4c22b  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Switch
0x4c230  ldc.i4.4
0x4c231  newarr   [mscorlib]System.Reflection.Emit.Label
0x4c236  dup
0x4c237  ldc.i4.0
0x4c238  ldarg.0
0x4c239  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4c23e  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.IteratorDescriptor::GetLabelNext()
0x4c243  stelem   [mscorlib]System.Reflection.Emit.Label
0x4c248  dup
0x4c249  ldc.i4.1
0x4c24a  ldloc.s  6
0x4c24c  stelem   [mscorlib]System.Reflection.Emit.Label
0x4c251  dup
0x4c252  ldc.i4.2
0x4c253  ldloc.s  4
0x4c255  stelem   [mscorlib]System.Reflection.Emit.Label
0x4c25a  dup
0x4c25b  ldc.i4.3
0x4c25c  ldloc.s  5
0x4c25e  stelem   [mscorlib]System.Reflection.Emit.Label
0x4c263  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, valuetype [mscorlib]System.Reflection.Emit.Label[] arrLabels)
0x4c268  ldarg.0
0x4c269  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4c26e  ldloc.2
0x4c26f  ldloc.0
0x4c270  ldtoken  [System.Xml]System.Xml.XPath.XPathNavigator
0x4c275  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4c27a  call     valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.StorageDescriptor::Current(class [mscorlib]System.Reflection.Emit.LocalBuilder locIter, class [mscorlib]System.Type itemStorageType)
0x4c27f  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::SetIterator(valuetype [mscorlib]System.Reflection.Emit.Label lblNext, valuetype System.Xml.Xsl.IlGen.StorageDescriptor storage)
0x4c284  ldarg.1
0x4c285  ret
```
