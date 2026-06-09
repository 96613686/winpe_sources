# Microsoft.ReportingServices.Modeling.AttributeRefNode::Compile

- ea: `0x1b600`
- end: `0x1b773`
- name: `Microsoft.ReportingServices.Modeling.AttributeRefNode::Compile`
- size: `371`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callees

- `0x84f0`
- `0x8500`
- `0x8530`
- `0x86b0`
- `0x97d0`
- `0x9d20`
- `0x139d0`
- `0x187f0`
- `0x18fe0`
- `0x1b600`
- `0x1b7c0`
- `0x231d0`
- `0x231f0`
- `0x24200`
- `0x24210`
- `0x24230`
- `0x24250`
- `0x255f0`
- `0x25600`
- `0x25a90`
- `0x25b70`

## pseudocode

```c

```

## disassembly

```asm
0x1b600  ldarg.0
0x1b601  ldarg.1
0x1b602  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldPersist()
0x1b607  call     instance void Microsoft.ReportingServices.Modeling.ModelingObject::Compile(bool shouldPersist)
0x1b60c  ldarg.3
0x1b60d  ldnull
0x1b60e  stind.ref
0x1b60f  ldarg.1
0x1b610  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldCheckInvalidRefsDuringCompilation()
0x1b615  brfalse  loc_1B6F9
0x1b61a  ldarg.0
0x1b61b  ldfld    class Microsoft.ReportingServices.Modeling.IQueryAttributeInternal Microsoft.ReportingServices.Modeling.AttributeRefNode::m_attribute
0x1b620  callvirt instance bool Microsoft.ReportingServices.Modeling.IQueryAttribute::get_IsInvalidRefTarget()
0x1b625  brfalse  loc_1B6F9
0x1b62a  ldarg.0
0x1b62b  ldfld    class Microsoft.ReportingServices.Modeling.IQueryAttributeInternal Microsoft.ReportingServices.Modeling.AttributeRefNode::m_attribute
0x1b630  callvirt instance class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.IQueryAttribute::get_ModelAttribute()
0x1b635  brfalse.s loc_1B68E
0x1b637  ldarg.2
0x1b638  brtrue.s loc_1B648
0x1b63a  ldnull
0x1b63b  ldftn    string Microsoft.ReportingServices.Modeling.SRErrors::ItemNotFound_MultipleProperties(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string reference)
0x1b641  newobj   instance void Microsoft.ReportingServices.Modeling.SRInvalidReferenceMethod::.ctor(object object, native int method)
0x1b646  br.s     loc_1B654
0x1b648  ldnull
0x1b649  ldftn    string Microsoft.ReportingServices.Modeling.SRErrors::ItemNotFound(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string reference)
0x1b64f  newobj   instance void Microsoft.ReportingServices.Modeling.SRInvalidReferenceMethod::.ctor(object object, native int method)
0x1b654  stloc.0
0x1b655  ldarg.1
0x1b656  ldc.i4.s 0x11
0x1b658  ldloc.0
0x1b659  ldstr    aAttributerefAt// "AttributeRef.AttributeID"
0x1b65e  ldarg.1
0x1b65f  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x1b664  ldarg.0
0x1b665  ldfld    class Microsoft.ReportingServices.Modeling.IQueryAttributeInternal Microsoft.ReportingServices.Modeling.AttributeRefNode::m_attribute
0x1b66a  callvirt instance class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.IQueryAttribute::get_ModelAttribute()
0x1b66f  callvirt instance valuetype Microsoft.ReportingServices.Modeling.QName Microsoft.ReportingServices.Modeling.ModelItem::get_ID()
0x1b674  stloc.1
0x1b675  ldloca.s 1
0x1b677  constrained. Microsoft.ReportingServices.Modeling.QName
0x1b67d  callvirt instance string [mscorlib]System.Object::ToString()
0x1b682  callvirt instance string Microsoft.ReportingServices.Modeling.SRInvalidReferenceMethod::Invoke(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string reference)
0x1b687  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x1b68c  br.s     loc_1B6EF
0x1b68e  ldarg.0
0x1b68f  ldfld    class Microsoft.ReportingServices.Modeling.IQueryAttributeInternal Microsoft.ReportingServices.Modeling.AttributeRefNode::m_attribute
0x1b694  callvirt instance class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.IQueryAttribute::get_CalculatedAttribute()
0x1b699  brfalse.s loc_1B6E4
0x1b69b  ldarg.2
0x1b69c  brtrue.s loc_1B6AC
0x1b69e  ldnull
0x1b69f  ldftn    string Microsoft.ReportingServices.Modeling.SRErrors::CalculatedAttributeNotFound_MultipleProperties(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string reference)
0x1b6a5  newobj   instance void Microsoft.ReportingServices.Modeling.SRInvalidReferenceMethod::.ctor(object object, native int method)
0x1b6aa  br.s     loc_1B6B8
0x1b6ac  ldnull
0x1b6ad  ldftn    string Microsoft.ReportingServices.Modeling.SRErrors::CalculatedAttributeNotFound(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string reference)
0x1b6b3  newobj   instance void Microsoft.ReportingServices.Modeling.SRInvalidReferenceMethod::.ctor(object object, native int method)
0x1b6b8  stloc.2
0x1b6b9  ldarg.1
0x1b6ba  ldc.i4.s 0x17
0x1b6bc  ldloc.2
0x1b6bd  ldstr    aAttributerefAt_0// "AttributeRef.AttributeName"
0x1b6c2  ldarg.1
0x1b6c3  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x1b6c8  ldarg.0
0x1b6c9  ldfld    class Microsoft.ReportingServices.Modeling.IQueryAttributeInternal Microsoft.ReportingServices.Modeling.AttributeRefNode::m_attribute
0x1b6ce  callvirt instance class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.IQueryAttribute::get_CalculatedAttribute()
0x1b6d3  callvirt instance string Microsoft.ReportingServices.Modeling.Expression::get_Name()
0x1b6d8  callvirt instance string Microsoft.ReportingServices.Modeling.SRInvalidReferenceMethod::Invoke(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string reference)
0x1b6dd  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x1b6e2  br.s     loc_1B6EF
0x1b6e4  ldstr    aNullOrUnrecogn// "Null or unrecognized IQueryAttribute"
0x1b6e9  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1b6ee  throw
0x1b6ef  ldloca.s 3
0x1b6f1  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>
0x1b6f7  ldloc.3
0x1b6f8  ret
0x1b6f9  ldarg.0
0x1b6fa  ldfld    class Microsoft.ReportingServices.Modeling.IQueryAttributeInternal Microsoft.ReportingServices.Modeling.AttributeRefNode::m_attribute
0x1b6ff  ldarg.1
0x1b700  ldstr    aAttributeref// "AttributeRef"
0x1b705  ldarg.2
0x1b706  ldc.i4.0
0x1b707  ceq
0x1b709  callvirt instance bool Microsoft.ReportingServices.Modeling.IQueryAttributeInternal::CheckReference(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, string propertyName, bool multipleInScope)
0x1b70e  brtrue.s loc_1B71A
0x1b710  ldloca.s 3
0x1b712  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>
0x1b718  ldloc.3
0x1b719  ret
0x1b71a  ldarg.0
0x1b71b  ldfld    class Microsoft.ReportingServices.Modeling.IQueryAttributeInternal Microsoft.ReportingServices.Modeling.AttributeRefNode::m_attribute
0x1b720  callvirt instance bool Microsoft.ReportingServices.Modeling.IQueryAttributeInternal::get_ReplaceWithExpression()
0x1b725  brfalse.s loc_1B762
0x1b727  ldarg.0
0x1b728  ldarg.1
0x1b729  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::IsInSetArgumentContext()
0x1b72e  call     instance class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.AttributeRefNode::CreateReplacementExpression(bool inSetArgumentContext)
0x1b733  stloc.s  4
0x1b735  ldarg.1
0x1b736  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldNormalize()
0x1b73b  brfalse.s loc_1B754
0x1b73d  ldarg.1
0x1b73e  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldPersist()
0x1b743  brtrue.s loc_1B750
0x1b745  ldstr    aNormalizeWitho_0// "Normalize without persist"
0x1b74a  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1b74f  throw
0x1b750  ldarg.3
0x1b751  ldloc.s  4
0x1b753  stind.ref
0x1b754  ldloc.s  4
0x1b756  ldarg.1
0x1b757  ldsfld   valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags::None
0x1b75c  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType> Microsoft.ReportingServices.Modeling.Expression::Compile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags flags)
0x1b761  ret
0x1b762  ldarg.0
0x1b763  ldfld    class Microsoft.ReportingServices.Modeling.IQueryAttributeInternal Microsoft.ReportingServices.Modeling.AttributeRefNode::m_attribute
0x1b768  callvirt instance valuetype Microsoft.ReportingServices.Modeling.ResultType Microsoft.ReportingServices.Modeling.IQueryAttribute::GetResultType()
0x1b76d  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::.ctor(var<u1>)
0x1b772  ret
```
