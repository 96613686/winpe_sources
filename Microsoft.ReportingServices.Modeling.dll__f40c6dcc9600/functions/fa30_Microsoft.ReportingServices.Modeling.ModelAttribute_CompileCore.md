# Microsoft.ReportingServices.Modeling.ModelAttribute::CompileCore

- ea: `0xfa30`
- end: `0xfc3a`
- name: `Microsoft.ReportingServices.Modeling.ModelAttribute::CompileCore`
- size: `522`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: `service_task, broker_com_uri`

## callees

- `0x8500`
- `0x8510`
- `0x8690`
- `0xeed0`
- `0xf1b0`
- `0xfa30`
- `0xfc40`
- `0xfd10`
- `0x13090`
- `0x139d0`
- `0x13ae0`
- `0x14390`
- `0x19cd0`
- `0x19cf0`
- `0x19d10`
- `0x24510`
- `0x248f0`
- `0x24910`
- `0x24930`
- `0x24950`
- `0x24970`
- `0x24990`
- `0x24d60`
- `0x25030`
- `0x25540`
- `0x25590`
- `0x25a90`
- `0x25b70`
- `0x25b80`

## pseudocode

```c

```

## disassembly

```asm
0xfa30  ldarg.0
0xfa31  ldarg.1
0xfa32  call     instance void Microsoft.ReportingServices.Modeling.ModelItem::CompileCore(class Microsoft.ReportingServices.Modeling.CompilationContext ctx)
0xfa37  ldarg.0
0xfa38  ldfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.ModelAttribute::m_expression
0xfa3d  brfalse  loc_FB00
0xfa42  ldarg.0
0xfa43  ldarg.1
0xfa44  ldarg.0
0xfa45  ldfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.ModelAttribute::m_expression
0xfa4a  call     instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType> Microsoft.ReportingServices.Modeling.ModelAttribute::CompileExpression(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, class Microsoft.ReportingServices.Modeling.Expression expression)
0xfa4f  stloc.0
0xfa50  ldloca.s 0
0xfa52  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::get_HasValue()
0xfa57  brfalse  loc_FB00
0xfa5c  ldloca.s 0
0xfa5e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::get_Value()
0xfa63  stloc.1
0xfa64  ldloca.s 1
0xfa66  call     instance valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.ResultType::get_DataType()
0xfa6b  ldarg.0
0xfa6c  ldfld    valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.ModelAttribute::m_dataType
0xfa71  beq.s    loc_FAAB
0xfa73  ldloca.s 1
0xfa75  call     instance valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.ResultType::get_DataType()
0xfa7a  ldc.i4.8
0xfa7b  beq.s    loc_FAAB
0xfa7d  ldarg.1
0xfa7e  ldc.i4.s 0x27
0xfa80  ldarg.1
0xfa81  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0xfa86  ldarg.1
0xfa87  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0xfa8c  stloc.2
0xfa8d  ldloca.s 2
0xfa8f  call     instance string Microsoft.ReportingServices.Modeling.SRObjectDescriptor::get_ObjectName()
0xfa94  ldarg.0
0xfa95  ldfld    valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.ModelAttribute::m_dataType
0xfa9a  ldloca.s 1
0xfa9c  call     instance valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.ResultType::get_DataType()
0xfaa1  call     string Microsoft.ReportingServices.Modeling.SRErrors::ExpressionDataTypeMismatch(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string objectName, valuetype Microsoft.ReportingServices.Modeling.DataType attributeDataType, valuetype Microsoft.ReportingServices.Modeling.DataType expressionDataType)
0xfaa6  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0xfaab  ldloca.s 1
0xfaad  call     instance bool Microsoft.ReportingServices.Modeling.ResultType::get_Nullable()
0xfab2  brfalse.s loc_FADD
0xfab4  ldarg.0
0xfab5  ldfld    bool Microsoft.ReportingServices.Modeling.ModelAttribute::m_nullable
0xfaba  brtrue.s loc_FADD
0xfabc  ldarg.1
0xfabd  ldc.i4.s 0x28
0xfabf  ldarg.1
0xfac0  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0xfac5  ldarg.1
0xfac6  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0xfacb  stloc.2
0xfacc  ldloca.s 2
0xface  call     instance string Microsoft.ReportingServices.Modeling.SRObjectDescriptor::get_ObjectName()
0xfad3  call     string Microsoft.ReportingServices.Modeling.SRErrors::ExpressionNullableMismatch(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string objectName)
0xfad8  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0xfadd  ldloca.s 1
0xfadf  call     instance valuetype Microsoft.ReportingServices.Modeling.Cardinality Microsoft.ReportingServices.Modeling.ResultType::get_Cardinality()
0xfae4  ldc.i4.1
0xfae5  bne.un.s loc_FB00
0xfae7  ldarg.1
0xfae8  ldc.i4.s 0x57
0xfaea  ldarg.1
0xfaeb  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0xfaf0  ldarg.1
0xfaf1  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.CompilationContext::get_ContextEntityDescriptor()
0xfaf6  call     string Microsoft.ReportingServices.Modeling.SRErrors::TopLevelSetExpression_Attribute(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor entityTypeAndName)
0xfafb  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0xfb00  ldarg.0
0xfb01  ldfld    bool Microsoft.ReportingServices.Modeling.ModelAttribute::m_filter
0xfb06  brfalse.s loc_FB2A
0xfb08  ldarg.0
0xfb09  ldfld    valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.ModelAttribute::m_dataType
0xfb0e  ldc.i4.4
0xfb0f  beq.s    loc_FB2A
0xfb11  ldarg.1
0xfb12  ldc.i4.s 0x45
0xfb14  ldarg.1
0xfb15  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0xfb1a  ldarg.0
0xfb1b  ldfld    valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.ModelAttribute::m_dataType
0xfb20  call     string Microsoft.ReportingServices.Modeling.SRErrors::NonBooleanFilterAttribute(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.DataType dataType)
0xfb25  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0xfb2a  ldarg.0
0xfb2b  ldfld    valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.ModelAttribute::m_dataType
0xfb30  ldc.i4.6
0xfb31  bne.un.s loc_FB53
0xfb33  ldarg.0
0xfb34  ldfld    string Microsoft.ReportingServices.Modeling.ModelAttribute::m_mimeType
0xfb39  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xfb3e  brfalse.s loc_FB53
0xfb40  ldarg.1
0xfb41  ldc.i4.s 0x29
0xfb43  ldarg.1
0xfb44  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0xfb49  call     string Microsoft.ReportingServices.Modeling.SRErrors::MissingMimeType(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0xfb4e  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedWarning(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0xfb53  ldarg.0
0xfb54  call     instance class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.ModelAttribute::get_DefaultAggregate()
0xfb59  brfalse  loc_FC2A
0xfb5e  ldarg.0
0xfb5f  ldfld    bool Microsoft.ReportingServices.Modeling.ModelAttribute::m_aggregate
0xfb64  brfalse.s loc_FB79
0xfb66  ldarg.1
0xfb67  ldc.i4.s 0x2A
0xfb69  ldarg.1
0xfb6a  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0xfb6f  call     string Microsoft.ReportingServices.Modeling.SRErrors::IsAggregateWithDefaultAggregate(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0xfb74  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0xfb79  ldarg.1
0xfb7a  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldCheckInvalidRefsDuringCompilation()
0xfb7f  brfalse.s loc_FBC0
0xfb81  ldarg.0
0xfb82  call     instance class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.ModelAttribute::get_DefaultAggregate()
0xfb87  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelItem::get_IsInvalidRefTarget()
0xfb8c  brfalse.s loc_FBC0
0xfb8e  ldarg.1
0xfb8f  ldc.i4.s 0x11
0xfb91  ldstr    aDefaultaggrega// "DefaultAggregateAttributeID"
0xfb96  ldarg.1
0xfb97  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0xfb9c  ldarg.0
0xfb9d  call     instance class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.ModelAttribute::get_DefaultAggregate()
0xfba2  callvirt instance valuetype Microsoft.ReportingServices.Modeling.QName Microsoft.ReportingServices.Modeling.ModelItem::get_ID()
0xfba7  stloc.3
0xfba8  ldloca.s 3
0xfbaa  constrained. Microsoft.ReportingServices.Modeling.QName
0xfbb0  callvirt instance string [mscorlib]System.Object::ToString()
0xfbb5  call     string Microsoft.ReportingServices.Modeling.SRErrors::ItemNotFound(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string reference)
0xfbba  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0xfbbf  ret
0xfbc0  ldarg.0
0xfbc1  call     instance class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.ModelAttribute::get_DefaultAggregate()
0xfbc6  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelAttribute::get_IsAggregate()
0xfbcb  brtrue.s loc_FBEB
0xfbcd  ldarg.1
0xfbce  ldc.i4.s 0x2B
0xfbd0  ldarg.1
0xfbd1  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0xfbd6  ldarg.0
0xfbd7  call     instance class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.ModelAttribute::get_DefaultAggregate()
0xfbdc  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0xfbe1  call     string Microsoft.ReportingServices.Modeling.SRErrors::NonAggregateAsDefaultAggregate(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor defaultAggregateTypeAndName)
0xfbe6  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0xfbeb  ldarg.0
0xfbec  call     instance class Microsoft.ReportingServices.Modeling.ModelFieldCollection Microsoft.ReportingServices.Modeling.ModelField::get_Variations()
0xfbf1  ldarg.0
0xfbf2  call     instance class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.ModelAttribute::get_DefaultAggregate()
0xfbf7  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.ModelField>::Contains(var<u1>)
0xfbfc  brtrue.s loc_FC2A
0xfbfe  ldarg.1
0xfbff  ldc.i4.s 0x2C
0xfc01  ldarg.1
0xfc02  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0xfc07  ldarg.1
0xfc08  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0xfc0d  stloc.2
0xfc0e  ldloca.s 2
0xfc10  call     instance string Microsoft.ReportingServices.Modeling.SRObjectDescriptor::get_ObjectName()
0xfc15  ldarg.0
0xfc16  call     instance class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.ModelAttribute::get_DefaultAggregate()
0xfc1b  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0xfc20  call     string Microsoft.ReportingServices.Modeling.SRErrors::NonVariationAsDefaultAggregate(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string objectName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor defaultAggregateTypeAndName)
0xfc25  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0xfc2a  ldarg.1
0xfc2b  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldCheckBindings()
0xfc30  brfalse.s loc_FC39
0xfc32  ldarg.0
0xfc33  ldarg.1
0xfc34  call     instance void Microsoft.ReportingServices.Modeling.ModelAttribute::CompileCheckBindings(class Microsoft.ReportingServices.Modeling.CompilationContext ctx)
0xfc39  ret
```
