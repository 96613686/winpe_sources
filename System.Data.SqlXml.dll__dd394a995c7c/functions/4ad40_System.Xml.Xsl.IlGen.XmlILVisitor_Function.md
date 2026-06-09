# System.Xml.Xsl.IlGen.XmlILVisitor::Function

- ea: `0x4ad40`
- end: `0x4af60`
- name: `System.Xml.Xsl.IlGen.XmlILVisitor::Function`
- size: `544`
- prototype: ``
- caller_count: `1`
- callee_count: `35`
- tags: `registry_config`

## callers

- `0x4a930`

## callees

- `0x2370`
- `0x35d30`
- `0x36ec0`
- `0x36ee0`
- `0x37100`
- `0x376c0`
- `0x376e0`
- `0x37700`
- `0x37790`
- `0x3ef70`
- `0x3f000`
- `0x3f070`
- `0x3f180`
- `0x3f1f0`
- `0x3f270`
- `0x3f3e0`
- `0x3fe20`
- `0x3ff00`
- `0x3ff10`
- `0x3ffd0`
- `0x40120`
- `0x402c0`
- `0x405b0`
- `0x411d0`
- `0x41210`
- `0x41230`
- `0x41260`
- `0x41350`
- `0x41490`
- `0x4ad40`
- `0x50490`
- `0x504f0`
- `0x50650`
- `0x50700`
- `0x50a90`

## pseudocode

```c

```

## disassembly

```asm
0x4ad40  ldarg.1
0x4ad41  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilFunction::get_Arguments()
0x4ad46  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xml.Xsl.Qil.QilNode> System.Xml.Xsl.Qil.QilNode::GetEnumerator()
0x4ad4b  stloc.s  4
0x4ad4d  br.s     loc_4ADA8
0x4ad4f  ldloc.s  4
0x4ad51  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xml.Xsl.Qil.QilNode>::get_Current()
0x4ad56  castclass System.Xml.Xsl.Qil.QilIterator
0x4ad5b  stloc.s  5
0x4ad5d  ldarg.0
0x4ad5e  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ad63  newobj   instance void System.Xml.Xsl.IlGen.IteratorDescriptor::.ctor(class System.Xml.Xsl.IlGen.GenerateHelper helper)
0x4ad68  stloc.2
0x4ad69  ldloc.s  5
0x4ad6b  call     class System.Xml.Xsl.IlGen.XmlILAnnotation System.Xml.Xsl.IlGen.XmlILAnnotation::Write(class System.Xml.Xsl.Qil.QilNode nd)
0x4ad70  callvirt instance int32 System.Xml.Xsl.IlGen.XmlILAnnotation::get_ArgumentPosition()
0x4ad75  ldc.i4.1
0x4ad76  add
0x4ad77  stloc.1
0x4ad78  ldloc.2
0x4ad79  ldloc.1
0x4ad7a  ldarg.0
0x4ad7b  ldloc.s  5
0x4ad7d  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILVisitor::GetItemStorageType(class System.Xml.Xsl.Qil.QilNode nd)
0x4ad82  ldloc.s  5
0x4ad84  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4ad89  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsSingleton()
0x4ad8e  ldc.i4.0
0x4ad8f  ceq
0x4ad91  call     valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.StorageDescriptor::Parameter(int32 paramIndex, class [mscorlib]System.Type itemStorageType, bool isCached)
0x4ad96  callvirt instance void System.Xml.Xsl.IlGen.IteratorDescriptor::set_Storage(valuetype System.Xml.Xsl.IlGen.StorageDescriptor value)
0x4ad9b  ldloc.s  5
0x4ad9d  call     class System.Xml.Xsl.IlGen.XmlILAnnotation System.Xml.Xsl.IlGen.XmlILAnnotation::Write(class System.Xml.Xsl.Qil.QilNode nd)
0x4ada2  ldloc.2
0x4ada3  callvirt instance void System.Xml.Xsl.IlGen.XmlILAnnotation::set_CachedIteratorDescriptor(class System.Xml.Xsl.IlGen.IteratorDescriptor value)
0x4ada8  ldloc.s  4
0x4adaa  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4adaf  brtrue.s loc_4AD4F
0x4adb1  leave.s  loc_4ADBF
0x4adb3  ldloc.s  4
0x4adb5  brfalse.s loc_4ADBE
0x4adb7  ldloc.s  4
0x4adb9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4adbe  endfinally
0x4adbf  ldarg.1
0x4adc0  call     class System.Xml.Xsl.IlGen.XmlILAnnotation System.Xml.Xsl.IlGen.XmlILAnnotation::Write(class System.Xml.Xsl.Qil.QilNode nd)
0x4adc5  callvirt instance class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILAnnotation::get_FunctionBinding()
0x4adca  stloc.0
0x4adcb  ldarg.1
0x4adcc  call     class System.Xml.Xsl.IlGen.XmlILConstructInfo System.Xml.Xsl.IlGen.XmlILConstructInfo::Read(class System.Xml.Xsl.Qil.QilNode nd)
0x4add1  callvirt instance valuetype System.Xml.Xsl.IlGen.XmlILConstructMethod System.Xml.Xsl.IlGen.XmlILConstructInfo::get_ConstructMethod()
0x4add6  ldc.i4.1
0x4add7  ceq
0x4add9  stloc.3
0x4adda  ldarg.0
0x4addb  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ade0  ldloc.0
0x4ade1  ldarg.1
0x4ade2  callvirt instance class System.Xml.Xsl.ISourceLineInfo System.Xml.Xsl.Qil.QilNode::get_SourceLine()
0x4ade7  ldloc.3
0x4ade8  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::MethodBegin(class [mscorlib]System.Reflection.MethodBase methInfo, class System.Xml.Xsl.ISourceLineInfo sourceInfo, bool initWriters)
0x4aded  ldarg.1
0x4adee  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilFunction::get_Arguments()
0x4adf3  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xml.Xsl.Qil.QilNode> System.Xml.Xsl.Qil.QilNode::GetEnumerator()
0x4adf8  stloc.s  6
0x4adfa  br       loc_4AEFA
0x4adff  ldloc.s  6
0x4ae01  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xml.Xsl.Qil.QilNode>::get_Current()
0x4ae06  castclass System.Xml.Xsl.Qil.QilIterator
0x4ae0b  stloc.s  7
0x4ae0d  ldarg.0
0x4ae0e  ldfld    class System.Xml.Xsl.Qil.QilExpression System.Xml.Xsl.IlGen.XmlILVisitor::qil
0x4ae13  callvirt instance bool System.Xml.Xsl.Qil.QilExpression::get_IsDebug()
0x4ae18  brfalse.s loc_4AE35
0x4ae1a  ldloc.s  7
0x4ae1c  callvirt instance class System.Xml.Xsl.ISourceLineInfo System.Xml.Xsl.Qil.QilNode::get_SourceLine()
0x4ae21  brfalse.s loc_4AE35
0x4ae23  ldarg.0
0x4ae24  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ae29  ldloc.s  7
0x4ae2b  callvirt instance class System.Xml.Xsl.ISourceLineInfo System.Xml.Xsl.Qil.QilNode::get_SourceLine()
0x4ae30  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::DebugSequencePoint(class System.Xml.Xsl.ISourceLineInfo sourceInfo)
0x4ae35  ldloc.s  7
0x4ae37  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilIterator::get_Binding()
0x4ae3c  brfalse  loc_4AEFA
0x4ae41  ldloc.s  7
0x4ae43  callvirt instance object System.Xml.Xsl.Qil.QilNode::get_Annotation()
0x4ae48  isinst   System.Xml.Xsl.IlGen.XmlILAnnotation
0x4ae4d  callvirt instance int32 System.Xml.Xsl.IlGen.XmlILAnnotation::get_ArgumentPosition()
0x4ae52  ldc.i4.1
0x4ae53  add
0x4ae54  stloc.1
0x4ae55  ldarg.0
0x4ae56  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ae5b  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.GenerateHelper::DefineLabel()
0x4ae60  stloc.s  8
0x4ae62  ldarg.0
0x4ae63  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ae68  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadQueryRuntime()
0x4ae6d  ldarg.0
0x4ae6e  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ae73  ldloc.1
0x4ae74  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadParameter(int32 paramPos)
0x4ae79  ldarg.0
0x4ae7a  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ae7f  ldc.i4.s 0x1D
0x4ae81  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadInteger(int32 intVal)
0x4ae86  ldarg.0
0x4ae87  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ae8c  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::SeqMatchesCode
0x4ae91  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x4ae96  ldarg.0
0x4ae97  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4ae9c  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Brfalse
0x4aea1  ldloc.s  8
0x4aea3  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, valuetype [mscorlib]System.Reflection.Emit.Label lblVal)
0x4aea8  ldarg.0
0x4aea9  ldloc.s  7
0x4aeab  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::StartNestedIterator(class System.Xml.Xsl.Qil.QilNode nd)
0x4aeb0  ldarg.0
0x4aeb1  ldloc.s  7
0x4aeb3  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilIterator::get_Binding()
0x4aeb8  ldarg.0
0x4aeb9  ldloc.s  7
0x4aebb  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILVisitor::GetItemStorageType(class System.Xml.Xsl.Qil.QilNode nd)
0x4aec0  ldloc.s  7
0x4aec2  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4aec7  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsSingleton()
0x4aecc  ldc.i4.0
0x4aecd  ceq
0x4aecf  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisitEnsureStack(class System.Xml.Xsl.Qil.QilNode nd, class [mscorlib]System.Type itemStorageType, bool isCached)
0x4aed4  ldarg.0
0x4aed5  ldloc.s  7
0x4aed7  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::EndNestedIterator(class System.Xml.Xsl.Qil.QilNode nd)
0x4aedc  ldarg.0
0x4aedd  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4aee2  ldloc.1
0x4aee3  box      [mscorlib]System.Int32
0x4aee8  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::SetParameter(object paramId)
0x4aeed  ldarg.0
0x4aeee  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4aef3  ldloc.s  8
0x4aef5  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label lbl)
0x4aefa  ldloc.s  6
0x4aefc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4af01  brtrue   loc_4ADFF
0x4af06  leave.s  loc_4AF14
0x4af08  ldloc.s  6
0x4af0a  brfalse.s loc_4AF13
0x4af0c  ldloc.s  6
0x4af0e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4af13  endfinally
0x4af14  ldarg.0
0x4af15  ldarg.1
0x4af16  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::StartNestedIterator(class System.Xml.Xsl.Qil.QilNode nd)
0x4af1b  ldloc.3
0x4af1c  brfalse.s loc_4AF2C
0x4af1e  ldarg.0
0x4af1f  ldarg.1
0x4af20  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilFunction::get_Definition()
0x4af25  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisit(class System.Xml.Xsl.Qil.QilNode nd)
0x4af2a  br.s     loc_4AF4D
0x4af2c  ldarg.0
0x4af2d  ldarg.1
0x4af2e  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilFunction::get_Definition()
0x4af33  ldarg.0
0x4af34  ldarg.1
0x4af35  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILVisitor::GetItemStorageType(class System.Xml.Xsl.Qil.QilNode nd)
0x4af3a  ldarg.1
0x4af3b  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4af40  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsSingleton()
0x4af45  ldc.i4.0
0x4af46  ceq
0x4af48  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisitEnsureStack(class System.Xml.Xsl.Qil.QilNode nd, class [mscorlib]System.Type itemStorageType, bool isCached)
0x4af4d  ldarg.0
0x4af4e  ldarg.1
0x4af4f  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::EndNestedIterator(class System.Xml.Xsl.Qil.QilNode nd)
0x4af54  ldarg.0
0x4af55  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4af5a  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::MethodEnd()
0x4af5f  ret
```
