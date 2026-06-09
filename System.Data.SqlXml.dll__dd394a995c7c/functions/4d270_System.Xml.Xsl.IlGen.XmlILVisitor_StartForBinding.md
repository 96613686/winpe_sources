# System.Xml.Xsl.IlGen.XmlILVisitor::StartForBinding

- ea: `0x4d270`
- end: `0x4d420`
- name: `System.Xml.Xsl.IlGen.XmlILVisitor::StartForBinding`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config`

## callers

- `0x4d200`

## callees

- `0x35d30`
- `0x37100`
- `0x38cd0`
- `0x3a690`
- `0x3f070`
- `0x3f170`
- `0x3fe00`
- `0x3ff40`
- `0x3ffd0`
- `0x3fff0`
- `0x40260`
- `0x40300`
- `0x40310`
- `0x40320`
- `0x40350`
- `0x403c0`
- `0x405a0`
- `0x407f0`
- `0x40800`
- `0x40c00`
- `0x40c60`
- `0x4d270`
- `0x50490`
- `0x504d0`
- `0x504f0`

## pseudocode

```c

```

## disassembly

```asm
0x4d270  ldnull
0x4d271  stloc.0
0x4d272  ldarg.0
0x4d273  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4d278  callvirt instance bool System.Xml.Xsl.IlGen.IteratorDescriptor::get_HasLabelNext()
0x4d27d  brfalse.s loc_4D298
0x4d27f  ldarg.0
0x4d280  ldarg.1
0x4d281  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilIterator::get_Binding()
0x4d286  ldarg.0
0x4d287  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4d28c  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.IteratorDescriptor::GetLabelNext()
0x4d291  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::StartNestedIterator(class System.Xml.Xsl.Qil.QilNode nd, valuetype [mscorlib]System.Reflection.Emit.Label lblOnEnd)
0x4d296  br.s     loc_4D2A4
0x4d298  ldarg.0
0x4d299  ldarg.1
0x4d29a  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilIterator::get_Binding()
0x4d29f  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::StartNestedIterator(class System.Xml.Xsl.Qil.QilNode nd)
0x4d2a4  ldarg.2
0x4d2a5  ldc.i4.7
0x4d2a6  callvirt instance bool System.Xml.Xsl.IlGen.OptimizerPatterns::MatchesPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x4d2ab  brfalse.s loc_4D2E9
0x4d2ad  ldarg.0
0x4d2ae  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d2b3  ldstr    aPos// "$$$pos"
0x4d2b8  ldtoken  [mscorlib]System.Int32
0x4d2bd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4d2c2  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Xsl.IlGen.GenerateHelper::DeclareLocal(string name, class [mscorlib]System.Type type)
0x4d2c7  stloc.0
0x4d2c8  ldarg.0
0x4d2c9  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d2ce  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldc_I4_0
0x4d2d3  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode)
0x4d2d8  ldarg.0
0x4d2d9  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d2de  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Stloc
0x4d2e3  ldloc.0
0x4d2e4  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4d2e9  ldarg.0
0x4d2ea  ldarg.1
0x4d2eb  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilIterator::get_Binding()
0x4d2f0  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilVisitor::Visit(class System.Xml.Xsl.Qil.QilNode n)
0x4d2f5  pop
0x4d2f6  ldarg.0
0x4d2f7  ldfld    class System.Xml.Xsl.Qil.QilExpression System.Xml.Xsl.IlGen.XmlILVisitor::qil
0x4d2fc  callvirt instance bool System.Xml.Xsl.Qil.QilExpression::get_IsDebug()
0x4d301  brfalse.s loc_4D346
0x4d303  ldarg.1
0x4d304  callvirt instance string System.Xml.Xsl.Qil.QilReference::get_DebugName()
0x4d309  brfalse.s loc_4D346
0x4d30b  ldarg.0
0x4d30c  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d311  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::DebugStartScope()
0x4d316  ldarg.0
0x4d317  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4d31c  ldstr    aFor_1// "$$$for"
0x4d321  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureLocalNoCache(string locName)
0x4d326  ldarg.0
0x4d327  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4d32c  callvirt instance valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.IteratorDescriptor::get_Storage()
0x4d331  stloc.1
0x4d332  ldloca.s 1
0x4d334  call     instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Xsl.IlGen.StorageDescriptor::get_LocalLocation()
0x4d339  ldarg.1
0x4d33a  callvirt instance string System.Xml.Xsl.Qil.QilReference::get_DebugName()
0x4d33f  callvirt instance void [mscorlib]System.Reflection.Emit.LocalBuilder::SetLocalSymInfo(string)
0x4d344  br.s     loc_4D356
0x4d346  ldarg.0
0x4d347  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4d34c  ldstr    aFor_1// "$$$for"
0x4d351  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureNoStackNoCache(string locName)
0x4d356  ldarg.2
0x4d357  ldc.i4.7
0x4d358  callvirt instance bool System.Xml.Xsl.IlGen.OptimizerPatterns::MatchesPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x4d35d  brfalse  loc_4D402
0x4d362  ldarg.0
0x4d363  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d368  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloc
0x4d36d  ldloc.0
0x4d36e  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4d373  ldarg.0
0x4d374  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d379  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldc_I4_1
0x4d37e  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode)
0x4d383  ldarg.0
0x4d384  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d389  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Add
0x4d38e  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode)
0x4d393  ldarg.0
0x4d394  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d399  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Stloc
0x4d39e  ldloc.0
0x4d39f  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4d3a4  ldarg.2
0x4d3a5  ldc.i4.s 9
0x4d3a7  callvirt instance bool System.Xml.Xsl.IlGen.OptimizerPatterns::MatchesPattern(valuetype System.Xml.Xsl.IlGen.OptimizerPatternName pattern)
0x4d3ac  brfalse.s loc_4D3F6
0x4d3ae  ldarg.0
0x4d3af  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d3b4  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloc
0x4d3b9  ldloc.0
0x4d3ba  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4d3bf  ldarg.0
0x4d3c0  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d3c5  ldarg.2
0x4d3c6  ldc.i4.2
0x4d3c7  callvirt instance object System.Xml.Xsl.IlGen.OptimizerPatterns::GetArgument(valuetype System.Xml.Xsl.IlGen.OptimizerPatternArgument argNum)
0x4d3cc  unbox.any [mscorlib]System.Int32
0x4d3d1  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadInteger(int32 intVal)
0x4d3d6  ldarg.0
0x4d3d7  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4d3dc  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Bgt
0x4d3e1  ldarg.0
0x4d3e2  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4d3e7  callvirt instance class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.IteratorDescriptor::get_ParentIterator()
0x4d3ec  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.IteratorDescriptor::GetLabelNext()
0x4d3f1  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, valuetype [mscorlib]System.Reflection.Emit.Label lblVal)
0x4d3f6  ldarg.0
0x4d3f7  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4d3fc  ldloc.0
0x4d3fd  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::set_LocalPosition(class [mscorlib]System.Reflection.Emit.LocalBuilder value)
0x4d402  ldarg.0
0x4d403  ldarg.1
0x4d404  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilIterator::get_Binding()
0x4d409  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::EndNestedIterator(class System.Xml.Xsl.Qil.QilNode nd)
0x4d40e  ldarg.0
0x4d40f  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterCurr
0x4d414  ldarg.0
0x4d415  ldfld    class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILVisitor::iterNested
0x4d41a  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::SetIterator(class System.Xml.Xsl.IlGen.IteratorDescriptor iterInfo)
0x4d41f  ret
```
