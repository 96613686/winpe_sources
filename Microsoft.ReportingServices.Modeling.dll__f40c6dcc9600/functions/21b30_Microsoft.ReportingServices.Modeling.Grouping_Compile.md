# Microsoft.ReportingServices.Modeling.Grouping::Compile

- ea: `0x21b30`
- end: `0x21c4f`
- name: `Microsoft.ReportingServices.Modeling.Grouping::Compile`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x21c50`

## callees

- `0x84f0`
- `0x8720`
- `0x8740`
- `0x9d20`
- `0x18870`
- `0x18fe0`
- `0x19a00`
- `0x19cd0`
- `0x1bb50`
- `0x21970`
- `0x21b30`
- `0x25150`
- `0x25170`
- `0x25190`
- `0x251b0`
- `0x25590`
- `0x25a90`
- `0x25b70`
- `0x25bb0`
- `0x25be0`

## pseudocode

```c

```

## disassembly

```asm
0x21b30  ldarg.0
0x21b31  ldfld    string Microsoft.ReportingServices.Modeling.Grouping::m_name
0x21b36  callvirt instance int32 [mscorlib]System.String::get_Length()
0x21b3b  brtrue.s loc_21B50
0x21b3d  ldarg.1
0x21b3e  ldc.i4.s 0x5E
0x21b40  ldarg.1
0x21b41  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x21b46  call     string Microsoft.ReportingServices.Modeling.SRErrors::MissingGroupingName(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0x21b4b  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x21b50  ldarg.1
0x21b51  ldarg.0
0x21b52  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::PushScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x21b57  ldarg.0
0x21b58  ldarg.1
0x21b59  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldPersist()
0x21b5e  call     instance void Microsoft.ReportingServices.Modeling.ModelingObject::Compile(bool shouldPersist)
0x21b63  ldarg.0
0x21b64  ldfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Grouping::m_expression
0x21b69  brtrue.s loc_21B83
0x21b6b  ldarg.1
0x21b6c  ldc.i4.s 0x5F
0x21b6e  ldarg.1
0x21b6f  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x21b74  call     string Microsoft.ReportingServices.Modeling.SRErrors::MissingGroupingExpression(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0x21b79  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x21b7e  leave    loc_21C4E
0x21b83  ldarg.0
0x21b84  ldfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Grouping::m_expression
0x21b89  ldarg.1
0x21b8a  ldsfld   valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags::GroupingExpression
0x21b8f  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType> Microsoft.ReportingServices.Modeling.Expression::Compile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags flags)
0x21b94  stloc.0
0x21b95  ldloca.s 0
0x21b97  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::get_HasValue()
0x21b9c  brtrue.s loc_21BA3
0x21b9e  leave    loc_21C4E
0x21ba3  ldloca.s 0
0x21ba5  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::get_Value()
0x21baa  stloc.1
0x21bab  ldloca.s 1
0x21bad  call     instance valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.ResultType::get_DataType()
0x21bb2  ldc.i4.6
0x21bb3  bne.un.s loc_21BCD
0x21bb5  ldarg.1
0x21bb6  ldc.i4.s 0x60
0x21bb8  ldarg.0
0x21bb9  ldfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Grouping::m_expression
0x21bbe  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x21bc3  call     string Microsoft.ReportingServices.Modeling.SRErrors::BinaryGroupingExpression(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0x21bc8  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x21bcd  ldarg.0
0x21bce  call     instance bool Microsoft.ReportingServices.Modeling.Grouping::get_IsEntityGrouping()
0x21bd3  brfalse.s loc_21C06
0x21bd5  ldarg.1
0x21bd6  ldarg.0
0x21bd7  ldfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Grouping::m_expression
0x21bdc  callvirt instance class Microsoft.ReportingServices.Modeling.EntityRefNode Microsoft.ReportingServices.Modeling.Expression::get_NodeAsEntityRef()
0x21be1  callvirt instance class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.EntityRefNode::get_Entity()
0x21be6  callvirt instance void Microsoft.ReportingServices.Modeling.CompilationContext::PushContextEntity(class Microsoft.ReportingServices.Modeling.IQueryEntity entity)
0x21beb  ldarg.0
0x21bec  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionCollection Microsoft.ReportingServices.Modeling.Grouping::m_details
0x21bf1  ldarg.1
0x21bf2  ldsfld   valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags::GroupingDetail
0x21bf7  callvirt instance valuetype Microsoft.ReportingServices.Modeling.ResultType[] Microsoft.ReportingServices.Modeling.ExpressionCollection::Compile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags flags)
0x21bfc  pop
0x21bfd  leave.s  loc_21C4E
0x21bff  ldarg.1
0x21c00  callvirt instance void Microsoft.ReportingServices.Modeling.CompilationContext::PopContextEntity()
0x21c05  endfinally
0x21c06  ldarg.0
0x21c07  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionCollection Microsoft.ReportingServices.Modeling.Grouping::m_details
0x21c0c  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.Expression>::get_Count()
0x21c11  brtrue.s loc_21C27
0x21c13  ldarg.0
0x21c14  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionCollection Microsoft.ReportingServices.Modeling.Grouping::m_details
0x21c19  ldarg.1
0x21c1a  ldsfld   valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags::GroupingDetail
0x21c1f  callvirt instance valuetype Microsoft.ReportingServices.Modeling.ResultType[] Microsoft.ReportingServices.Modeling.ExpressionCollection::Compile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags flags)
0x21c24  pop
0x21c25  leave.s  loc_21C4E
0x21c27  ldarg.1
0x21c28  ldc.i4.s 0x61
0x21c2a  ldarg.1
0x21c2b  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x21c30  ldarg.0
0x21c31  ldfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Grouping::m_expression
0x21c36  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x21c3b  call     string Microsoft.ReportingServices.Modeling.SRErrors::NonEntityGroupingWithDetails(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor expressionTypeAndName)
0x21c40  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x21c45  leave.s  loc_21C4E
0x21c47  ldarg.1
0x21c48  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::PopScope()
0x21c4d  endfinally
0x21c4e  ret
```
