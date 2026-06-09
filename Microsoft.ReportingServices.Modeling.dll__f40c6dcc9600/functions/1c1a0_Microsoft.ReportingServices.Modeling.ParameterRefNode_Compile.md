# Microsoft.ReportingServices.Modeling.ParameterRefNode::Compile

- ea: `0x1c1a0`
- end: `0x1c2cd`
- name: `Microsoft.ReportingServices.Modeling.ParameterRefNode::Compile`
- size: `301`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callees

- `0x84f0`
- `0x8500`
- `0x8570`
- `0x85a0`
- `0x97d0`
- `0x9d20`
- `0xafc0`
- `0x18fe0`
- `0x19c50`
- `0x1c1a0`
- `0x22ab0`
- `0x22ae0`
- `0x22b20`
- `0x22b40`
- `0x22bc0`
- `0x22f40`
- `0x237c0`
- `0x240e0`
- `0x255f0`
- `0x25600`
- `0x25a90`
- `0x25b70`

## string_xrefs

- `0x1c263`: `ReplaceParameterRefs without persist.`
- `0x1c276`: `ReplaceParameterRefs with null ParameterValues.`

## pseudocode

```c

```

## disassembly

```asm
0x1c1a0  ldarg.0
0x1c1a1  ldarg.1
0x1c1a2  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldPersist()
0x1c1a7  call     instance void Microsoft.ReportingServices.Modeling.ModelingObject::Compile(bool shouldPersist)
0x1c1ac  ldarg.3
0x1c1ad  ldnull
0x1c1ae  stind.ref
0x1c1af  ldarg.0
0x1c1b0  ldfld    class Microsoft.ReportingServices.Modeling.Parameter Microsoft.ReportingServices.Modeling.ParameterRefNode::m_parameter
0x1c1b5  callvirt instance string Microsoft.ReportingServices.Modeling.Parameter::get_Name()
0x1c1ba  ldstr    aParameterrefPa// "ParameterRef.ParameterName"
0x1c1bf  ldc.i4.1
0x1c1c0  newobj   instance void Microsoft.ReportingServices.Modeling.ModelingReference::.ctor(string referenceByName, string propertyName, bool multipleInScope)
0x1c1c5  ldarg.1
0x1c1c6  call     class Microsoft.ReportingServices.Modeling.Parameter Microsoft.ReportingServices.Modeling.SemanticQuery::TryGetParameter(valuetype Microsoft.ReportingServices.Modeling.ModelingReference itemRef, class Microsoft.ReportingServices.Modeling.ValidationContext ctx)
0x1c1cb  stloc.0
0x1c1cc  ldloc.0
0x1c1cd  callvirt instance bool Microsoft.ReportingServices.Modeling.Parameter::get_IsInvalidRefTarget()
0x1c1d2  brtrue.s loc_1C1F2
0x1c1d4  ldloc.0
0x1c1d5  ldarg.0
0x1c1d6  ldfld    class Microsoft.ReportingServices.Modeling.Parameter Microsoft.ReportingServices.Modeling.ParameterRefNode::m_parameter
0x1c1db  beq.s    loc_1C1F2
0x1c1dd  ldarg.1
0x1c1de  ldarg.0
0x1c1df  ldfld    class Microsoft.ReportingServices.Modeling.Parameter Microsoft.ReportingServices.Modeling.ParameterRefNode::m_parameter
0x1c1e4  ldstr    aParameterrefPa// "ParameterRef.ParameterName"
0x1c1e9  ldarg.2
0x1c1ea  ldc.i4.0
0x1c1eb  ceq
0x1c1ed  call     void Microsoft.ReportingServices.Modeling.SemanticQuery::AddWrongSemanticQueryError(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, class Microsoft.ReportingServices.Modeling.IValidationScope referencedItem, string propertyName, bool multipleInScope)
0x1c1f2  ldarg.1
0x1c1f3  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldCheckInvalidRefsDuringCompilation()
0x1c1f8  brfalse.s loc_1C253
0x1c1fa  ldarg.0
0x1c1fb  ldfld    class Microsoft.ReportingServices.Modeling.Parameter Microsoft.ReportingServices.Modeling.ParameterRefNode::m_parameter
0x1c200  callvirt instance bool Microsoft.ReportingServices.Modeling.Parameter::get_IsInvalidRefTarget()
0x1c205  brfalse.s loc_1C253
0x1c207  ldarg.2
0x1c208  brtrue.s loc_1C218
0x1c20a  ldnull
0x1c20b  ldftn    string Microsoft.ReportingServices.Modeling.SRErrors::ParameterNotFound_MultipleProperties(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string reference)
0x1c211  newobj   instance void Microsoft.ReportingServices.Modeling.SRInvalidReferenceMethod::.ctor(object object, native int method)
0x1c216  br.s     loc_1C224
0x1c218  ldnull
0x1c219  ldftn    string Microsoft.ReportingServices.Modeling.SRErrors::ParameterNotFound(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string reference)
0x1c21f  newobj   instance void Microsoft.ReportingServices.Modeling.SRInvalidReferenceMethod::.ctor(object object, native int method)
0x1c224  stloc.1
0x1c225  ldarg.1
0x1c226  ldc.i4.s 0x18
0x1c228  ldloc.1
0x1c229  ldstr    aParametername// "ParameterName"
0x1c22e  ldarg.1
0x1c22f  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x1c234  ldarg.0
0x1c235  ldfld    class Microsoft.ReportingServices.Modeling.Parameter Microsoft.ReportingServices.Modeling.ParameterRefNode::m_parameter
0x1c23a  callvirt instance string Microsoft.ReportingServices.Modeling.Parameter::get_Name()
0x1c23f  callvirt instance string Microsoft.ReportingServices.Modeling.SRInvalidReferenceMethod::Invoke(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string reference)
0x1c244  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x1c249  ldloca.s 2
0x1c24b  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>
0x1c251  ldloc.2
0x1c252  ret
0x1c253  ldarg.1
0x1c254  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldReplaceParameterRefs()
0x1c259  brfalse.s loc_1C2A1
0x1c25b  ldarg.1
0x1c25c  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldPersist()
0x1c261  brtrue.s loc_1C26E
0x1c263  ldstr    aReplaceparamet// "ReplaceParameterRefs without persist."
0x1c268  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1c26d  throw
0x1c26e  ldarg.1
0x1c26f  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> Microsoft.ReportingServices.Modeling.CompilationContext::get_ParameterValues()
0x1c274  brtrue.s loc_1C281
0x1c276  ldstr    aReplaceparamet_0// "ReplaceParameterRefs with null Paramete"...
0x1c27b  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1c280  throw
0x1c281  ldarg.3
0x1c282  ldarg.0
0x1c283  ldfld    class Microsoft.ReportingServices.Modeling.Parameter Microsoft.ReportingServices.Modeling.ParameterRefNode::m_parameter
0x1c288  ldarg.1
0x1c289  callvirt instance class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Parameter::CreateReplacementExpression(class Microsoft.ReportingServices.Modeling.CompilationContext ctx)
0x1c28e  stind.ref
0x1c28f  ldarg.3
0x1c290  ldind.ref
0x1c291  brfalse.s loc_1C2A1
0x1c293  ldarg.3
0x1c294  ldind.ref
0x1c295  ldarg.1
0x1c296  ldsfld   valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags::None
0x1c29b  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType> Microsoft.ReportingServices.Modeling.Expression::Compile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags flags)
0x1c2a0  ret
0x1c2a1  ldarg.0
0x1c2a2  ldfld    class Microsoft.ReportingServices.Modeling.Parameter Microsoft.ReportingServices.Modeling.ParameterRefNode::m_parameter
0x1c2a7  callvirt instance valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.Parameter::get_DataType()
0x1c2ac  ldarg.0
0x1c2ad  ldfld    class Microsoft.ReportingServices.Modeling.Parameter Microsoft.ReportingServices.Modeling.ParameterRefNode::m_parameter
0x1c2b2  callvirt instance valuetype Microsoft.ReportingServices.Modeling.Cardinality Microsoft.ReportingServices.Modeling.Parameter::get_Cardinality()
0x1c2b7  ldarg.0
0x1c2b8  ldfld    class Microsoft.ReportingServices.Modeling.Parameter Microsoft.ReportingServices.Modeling.ParameterRefNode::m_parameter
0x1c2bd  callvirt instance bool Microsoft.ReportingServices.Modeling.Parameter::get_Nullable()
0x1c2c2  newobj   instance void Microsoft.ReportingServices.Modeling.ResultType::.ctor(valuetype Microsoft.ReportingServices.Modeling.DataType dataType, valuetype Microsoft.ReportingServices.Modeling.Cardinality cardinality, bool nullable)
0x1c2c7  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::.ctor(var<u1>)
0x1c2cc  ret
```
