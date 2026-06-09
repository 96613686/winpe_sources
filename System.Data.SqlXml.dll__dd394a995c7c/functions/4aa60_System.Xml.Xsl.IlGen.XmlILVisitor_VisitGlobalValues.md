# System.Xml.Xsl.IlGen.XmlILVisitor::VisitGlobalValues

- ea: `0x4aa60`
- end: `0x4ad3f`
- name: `System.Xml.Xsl.IlGen.XmlILVisitor::VisitGlobalValues`
- size: `735`
- prototype: ``
- caller_count: `1`
- callee_count: `38`
- tags: `registry_config`

## callers

- `0x4a930`

## callees

- `0x1b0`
- `0x2370`
- `0x37100`
- `0x374b0`
- `0x374d0`
- `0x376c0`
- `0x376e0`
- `0x37790`
- `0x379b0`
- `0x38cd0`
- `0x3ef70`
- `0x3f000`
- `0x3f060`
- `0x3f070`
- `0x3f170`
- `0x3f180`
- `0x3f3e0`
- `0x3f900`
- `0x3f930`
- `0x3f9a0`
- `0x3ff00`
- `0x3ff10`
- `0x3ffd0`
- `0x3fff0`
- `0x40020`
- `0x40040`
- `0x40280`
- `0x405a0`
- `0x40f00`
- `0x40fa0`
- `0x411d0`
- `0x41250`
- `0x4aa60`
- `0x50490`
- `0x504f0`
- `0x50700`
- `0x50a70`
- `0x50a90`

## string_xrefs

- `0x4aca9`: `XmlIl_UnknownParam`

## pseudocode

```c

```

## disassembly

```asm
0x4aa60  ldarg.1
0x4aa61  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xml.Xsl.Qil.QilNode> System.Xml.Xsl.Qil.QilNode::GetEnumerator()
0x4aa66  stloc.s  5
0x4aa68  br       loc_4AD24
0x4aa6d  ldloc.s  5
0x4aa6f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xml.Xsl.Qil.QilNode>::get_Current()
0x4aa74  castclass System.Xml.Xsl.Qil.QilIterator
0x4aa79  stloc.s  6
0x4aa7b  ldloc.s  6
0x4aa7d  isinst   System.Xml.Xsl.Qil.QilParameter
0x4aa82  stloc.s  7
0x4aa84  ldloc.s  6
0x4aa86  call     class System.Xml.Xsl.IlGen.XmlILAnnotation System.Xml.Xsl.IlGen.XmlILAnnotation::Write(class System.Xml.Xsl.Qil.QilNode nd)
0x4aa8b  callvirt instance class System.Xml.Xsl.IlGen.IteratorDescriptor System.Xml.Xsl.IlGen.XmlILAnnotation::get_CachedIteratorDescriptor()
0x4aa90  callvirt instance valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.IteratorDescriptor::get_Storage()
0x4aa95  stloc.s  8
0x4aa97  ldloca.s 8
0x4aa99  call     instance class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.StorageDescriptor::get_GlobalLocation()
0x4aa9e  stloc.0
0x4aa9f  ldloc.s  6
0x4aaa1  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4aaa6  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsSingleton()
0x4aaab  ldc.i4.0
0x4aaac  ceq
0x4aaae  stloc.3
0x4aaaf  ldarg.0
0x4aab0  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4aab5  callvirt instance class System.Xml.Xsl.IlGen.StaticDataManager System.Xml.Xsl.IlGen.GenerateHelper::get_StaticData()
0x4aaba  ldloc.s  6
0x4aabc  callvirt instance string System.Xml.Xsl.Qil.QilReference::get_DebugName()
0x4aac1  callvirt instance int32 System.Xml.Xsl.IlGen.StaticDataManager::DeclareGlobalValue(string name)
0x4aac6  stloc.s  4
0x4aac8  ldarg.0
0x4aac9  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4aace  ldloc.0
0x4aacf  ldloc.s  6
0x4aad1  callvirt instance class System.Xml.Xsl.ISourceLineInfo System.Xml.Xsl.Qil.QilNode::get_SourceLine()
0x4aad6  ldc.i4.0
0x4aad7  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::MethodBegin(class [mscorlib]System.Reflection.MethodBase methInfo, class System.Xml.Xsl.ISourceLineInfo sourceInfo, bool initWriters)
0x4aadc  ldarg.0
0x4aadd  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4aae2  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.GenerateHelper::DefineLabel()
0x4aae7  stloc.1
0x4aae8  ldarg.0
0x4aae9  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4aaee  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.GenerateHelper::DefineLabel()
0x4aaf3  stloc.2
0x4aaf4  ldarg.0
0x4aaf5  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4aafa  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadQueryRuntime()
0x4aaff  ldarg.0
0x4ab00  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ab05  ldloc.s  4
0x4ab07  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadInteger(int32 intVal)
0x4ab0c  ldarg.0
0x4ab0d  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ab12  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GlobalComputed
0x4ab17  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x4ab1c  ldarg.0
0x4ab1d  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ab22  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Brtrue
0x4ab27  ldloc.1
0x4ab28  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, valuetype [mscorlib]System.Reflection.Emit.Label lblVal)
0x4ab2d  ldarg.0
0x4ab2e  ldloc.s  6
0x4ab30  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::StartNestedIterator(class System.Xml.Xsl.Qil.QilNode nd)
0x4ab35  ldloc.s  7
0x4ab37  brfalse  loc_4AC3B
0x4ab3c  ldarg.0
0x4ab3d  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ab42  ldstr    aParam_0// "$$$param"
0x4ab47  ldtoken  [mscorlib]System.Object
0x4ab4c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4ab51  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Xsl.IlGen.GenerateHelper::DeclareLocal(string name, class [mscorlib]System.Type type)
0x4ab56  stloc.s  9
0x4ab58  ldarg.0
0x4ab59  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ab5e  ldloc.s  7
0x4ab60  callvirt instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilParameter::get_Name()
0x4ab65  callvirt instance string System.Xml.Xsl.Qil.QilName::get_LocalName()
0x4ab6a  ldloc.s  7
0x4ab6c  callvirt instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilParameter::get_Name()
0x4ab71  callvirt instance string System.Xml.Xsl.Qil.QilName::get_NamespaceUri()
0x4ab76  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::CallGetParameter(string localName, string namespaceUri)
0x4ab7b  ldarg.0
0x4ab7c  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ab81  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Stloc
0x4ab86  ldloc.s  9
0x4ab88  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4ab8d  ldarg.0
0x4ab8e  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ab93  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloc
0x4ab98  ldloc.s  9
0x4ab9a  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4ab9f  ldarg.0
0x4aba0  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4aba5  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Brfalse
0x4abaa  ldloc.2
0x4abab  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, valuetype [mscorlib]System.Reflection.Emit.Label lblVal)
0x4abb0  ldarg.0
0x4abb1  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4abb6  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadQueryRuntime()
0x4abbb  ldarg.0
0x4abbc  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4abc1  ldloc.s  4
0x4abc3  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadInteger(int32 intVal)
0x4abc8  ldarg.0
0x4abc9  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4abce  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadQueryRuntime()
0x4abd3  ldarg.0
0x4abd4  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4abd9  ldarg.0
0x4abda  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4abdf  callvirt instance class System.Xml.Xsl.IlGen.StaticDataManager System.Xml.Xsl.IlGen.GenerateHelper::get_StaticData()
0x4abe4  ldsfld   class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.XmlQueryTypeFactory::ItemS
0x4abe9  callvirt instance int32 System.Xml.Xsl.IlGen.StaticDataManager::DeclareXmlType(class System.Xml.Xsl.XmlQueryType type)
0x4abee  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadInteger(int32 intVal)
0x4abf3  ldarg.0
0x4abf4  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4abf9  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloc
0x4abfe  ldloc.s  9
0x4ac00  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4ac05  ldarg.0
0x4ac06  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ac0b  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::ChangeTypeXsltResult
0x4ac10  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x4ac15  ldarg.0
0x4ac16  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ac1b  ldtoken  [mscorlib]System.Object
0x4ac20  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4ac25  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::CallSetGlobalValue(class [mscorlib]System.Type clrType)
0x4ac2a  ldarg.0
0x4ac2b  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ac30  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Br
0x4ac35  ldloc.1
0x4ac36  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::EmitUnconditionalBranch(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, valuetype [mscorlib]System.Reflection.Emit.Label lblTarget)
0x4ac3b  ldarg.0
0x4ac3c  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ac41  ldloc.2
0x4ac42  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label lbl)
0x4ac47  ldloc.s  6
0x4ac49  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilIterator::get_Binding()
0x4ac4e  brfalse.s loc_4AC93
0x4ac50  ldarg.0
0x4ac51  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ac56  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadQueryRuntime()
0x4ac5b  ldarg.0
0x4ac5c  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ac61  ldloc.s  4
0x4ac63  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadInteger(int32 intVal)
0x4ac68  ldarg.0
0x4ac69  ldloc.s  6
0x4ac6b  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilIterator::get_Binding()
0x4ac70  ldarg.0
0x4ac71  ldloc.s  6
0x4ac73  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILVisitor::GetItemStorageType(class System.Xml.Xsl.Qil.QilNode nd)
0x4ac78  ldloc.3
0x4ac79  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisitEnsureStack(class System.Xml.Xsl.Qil.QilNode nd, class [mscorlib]System.Type itemStorageType, bool isCached)
0x4ac7e  ldarg.0
0x4ac7f  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ac84  ldarg.0
0x4ac85  ldloc.s  6
0x4ac87  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILVisitor::GetStorageType(class System.Xml.Xsl.Qil.QilNode nd)
0x4ac8c  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::CallSetGlobalValue(class [mscorlib]System.Type clrType)
0x4ac91  br.s     loc_4ACF0
0x4ac93  ldarg.0
0x4ac94  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ac99  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadQueryRuntime()
0x4ac9e  ldarg.0
0x4ac9f  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4aca4  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldstr
0x4aca9  ldstr    aXmlilUnknownpa// "XmlIl_UnknownParam"
0x4acae  ldc.i4.2
0x4acaf  newarr   [mscorlib]System.String
0x4acb4  dup
0x4acb5  ldc.i4.0
0x4acb6  ldloc.s  7
0x4acb8  callvirt instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilParameter::get_Name()
0x4acbd  callvirt instance string System.Xml.Xsl.Qil.QilName::get_LocalName()
0x4acc2  stelem.ref
0x4acc3  dup
0x4acc4  ldc.i4.1
0x4acc5  ldloc.s  7
0x4acc7  callvirt instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilParameter::get_Name()
0x4accc  callvirt instance string System.Xml.Xsl.Qil.QilName::get_NamespaceUri()
0x4acd1  stelem.ref
0x4acd2  stloc.s  0xA
0x4acd4  ldloc.s  0xA
0x4acd6  call     string System.Xml.Utils.Res::GetString(string name, object[] args)
0x4acdb  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, string strVal)
0x4ace0  ldarg.0
0x4ace1  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ace6  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::ThrowException
0x4aceb  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x4acf0  ldarg.0
0x4acf1  ldloc.s  6
0x4acf3  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::EndNestedIterator(class System.Xml.Xsl.Qil.QilNode nd)
0x4acf8  ldarg.0
0x4acf9  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4acfe  ldloc.1
0x4acff  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label lbl)
0x4ad04  ldarg.0
0x4ad05  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ad0a  ldloc.s  4
0x4ad0c  ldarg.0
0x4ad0d  ldloc.s  6
0x4ad0f  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILVisitor::GetStorageType(class System.Xml.Xsl.Qil.QilNode nd)
0x4ad14  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::CallGetGlobalValue(int32 idxValue, class [mscorlib]System.Type clrType)
0x4ad19  ldarg.0
0x4ad1a  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ad1f  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::MethodEnd()
0x4ad24  ldloc.s  5
0x4ad26  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4ad2b  brtrue   loc_4AA6D
0x4ad30  leave.s  loc_4AD3E
0x4ad32  ldloc.s  5
0x4ad34  brfalse.s loc_4AD3D
0x4ad36  ldloc.s  5
0x4ad38  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4ad3d  endfinally
0x4ad3e  ret
```
