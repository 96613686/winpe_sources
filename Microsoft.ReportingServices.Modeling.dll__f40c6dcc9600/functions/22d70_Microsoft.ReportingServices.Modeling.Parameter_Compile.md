# Microsoft.ReportingServices.Modeling.Parameter::Compile

- ea: `0x22d70`
- end: `0x22f06`
- name: `Microsoft.ReportingServices.Modeling.Parameter::Compile`
- size: `406`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x23110`

## callees

- `0x84f0`
- `0x9d20`
- `0x18fe0`
- `0x19cd0`
- `0x19cf0`
- `0x19d10`
- `0x22d70`
- `0x22f10`
- `0x25250`
- `0x25270`
- `0x25290`
- `0x252b0`
- `0x252d0`
- `0x252f0`
- `0x25540`
- `0x25a90`
- `0x25b70`
- `0x25bb0`
- `0x25be0`

## pseudocode

```c

```

## disassembly

```asm
0x22d70  ldarg.0
0x22d71  ldarg.1
0x22d72  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldPersist()
0x22d77  call     instance void Microsoft.ReportingServices.Modeling.ModelingObject::Compile(bool shouldPersist)
0x22d7c  ldarg.0
0x22d7d  ldfld    string Microsoft.ReportingServices.Modeling.Parameter::m_name
0x22d82  callvirt instance int32 [mscorlib]System.String::get_Length()
0x22d87  brtrue.s loc_22D9C
0x22d89  ldarg.1
0x22d8a  ldc.i4.s 0x66
0x22d8c  ldarg.1
0x22d8d  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x22d92  call     string Microsoft.ReportingServices.Modeling.SRErrors::MissingParameterName(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0x22d97  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x22d9c  ldarg.0
0x22d9d  ldfld    string Microsoft.ReportingServices.Modeling.Parameter::m_name
0x22da2  ldstr    aDrillthroughso// "DrillthroughSourceQuery"
0x22da7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22dac  brtrue.s loc_22DC0
0x22dae  ldarg.0
0x22daf  ldfld    string Microsoft.ReportingServices.Modeling.Parameter::m_name
0x22db4  ldstr    aDrillthroughco// "DrillthroughContext"
0x22db9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22dbe  brfalse.s loc_22DDF
0x22dc0  ldarg.1
0x22dc1  ldc.i4.s 0x67
0x22dc3  ldarg.1
0x22dc4  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x22dc9  ldarg.0
0x22dca  ldfld    string Microsoft.ReportingServices.Modeling.Parameter::m_name
0x22dcf  ldarg.0
0x22dd0  ldfld    string Microsoft.ReportingServices.Modeling.Parameter::m_name
0x22dd5  call     string Microsoft.ReportingServices.Modeling.SRErrors::InvalidParameterName(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string parameterName, string reservedName)
0x22dda  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x22ddf  ldarg.1
0x22de0  ldarg.0
0x22de1  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::PushScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x22de6  ldarg.0
0x22de7  ldc.i4.0
0x22de8  stfld    bool Microsoft.ReportingServices.Modeling.Parameter::m_compiledExprIsValid
0x22ded  ldarg.0
0x22dee  ldfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Parameter::m_defaultValueExpr
0x22df3  brfalse  loc_22EFC
0x22df8  ldarg.0
0x22df9  ldfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Parameter::m_defaultValueExpr
0x22dfe  ldarg.1
0x22dff  ldsfld   valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags::None
0x22e04  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType> Microsoft.ReportingServices.Modeling.Expression::Compile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags flags)
0x22e09  stloc.0
0x22e0a  ldloca.s 0
0x22e0c  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::get_HasValue()
0x22e11  brfalse  loc_22EFC
0x22e16  ldc.i4.1
0x22e17  stloc.1
0x22e18  ldloca.s 0
0x22e1a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::get_Value()
0x22e1f  stloc.2
0x22e20  ldarg.0
0x22e21  ldarg.0
0x22e22  ldfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Parameter::m_defaultValueExpr
0x22e27  call     instance bool Microsoft.ReportingServices.Modeling.Parameter::CheckDefaultValue(class Microsoft.ReportingServices.Modeling.Expression expr)
0x22e2c  brtrue.s loc_22E43
0x22e2e  ldarg.1
0x22e2f  ldc.i4.s 0x68
0x22e31  ldarg.1
0x22e32  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x22e37  call     string Microsoft.ReportingServices.Modeling.SRErrors::InvalidParameterExpression(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0x22e3c  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x22e41  ldc.i4.0
0x22e42  stloc.1
0x22e43  ldloca.s 2
0x22e45  call     instance valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.ResultType::get_DataType()
0x22e4a  ldarg.0
0x22e4b  ldfld    valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.Parameter::m_dataType
0x22e50  beq.s    loc_22E8C
0x22e52  ldloca.s 2
0x22e54  call     instance valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.ResultType::get_DataType()
0x22e59  ldc.i4.8
0x22e5a  beq.s    loc_22E8C
0x22e5c  ldarg.1
0x22e5d  ldc.i4.s 0x69
0x22e5f  ldarg.1
0x22e60  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x22e65  ldarg.1
0x22e66  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x22e6b  stloc.3
0x22e6c  ldloca.s 3
0x22e6e  call     instance string Microsoft.ReportingServices.Modeling.SRObjectDescriptor::get_ObjectName()
0x22e73  ldarg.0
0x22e74  ldfld    valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.Parameter::m_dataType
0x22e79  ldloca.s 2
0x22e7b  call     instance valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.ResultType::get_DataType()
0x22e80  call     string Microsoft.ReportingServices.Modeling.SRErrors::ParameterExpressionDataTypeMismatch(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string objectName, valuetype Microsoft.ReportingServices.Modeling.DataType parameterDataType, valuetype Microsoft.ReportingServices.Modeling.DataType expressionDataType)
0x22e85  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x22e8a  ldc.i4.0
0x22e8b  stloc.1
0x22e8c  ldloca.s 2
0x22e8e  call     instance bool Microsoft.ReportingServices.Modeling.ResultType::get_Nullable()
0x22e93  brfalse.s loc_22EC0
0x22e95  ldarg.0
0x22e96  ldfld    bool Microsoft.ReportingServices.Modeling.Parameter::m_nullable
0x22e9b  brtrue.s loc_22EC0
0x22e9d  ldarg.1
0x22e9e  ldc.i4.s 0x6B
0x22ea0  ldarg.1
0x22ea1  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x22ea6  ldarg.1
0x22ea7  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x22eac  stloc.3
0x22ead  ldloca.s 3
0x22eaf  call     instance string Microsoft.ReportingServices.Modeling.SRObjectDescriptor::get_ObjectName()
0x22eb4  call     string Microsoft.ReportingServices.Modeling.SRErrors::ParameterExpressionNullableMismatch(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string objectName)
0x22eb9  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x22ebe  ldc.i4.0
0x22ebf  stloc.1
0x22ec0  ldloca.s 2
0x22ec2  call     instance valuetype Microsoft.ReportingServices.Modeling.Cardinality Microsoft.ReportingServices.Modeling.ResultType::get_Cardinality()
0x22ec7  ldc.i4.1
0x22ec8  bne.un.s loc_22EF5
0x22eca  ldarg.0
0x22ecb  ldfld    valuetype Microsoft.ReportingServices.Modeling.Cardinality Microsoft.ReportingServices.Modeling.Parameter::m_cardinality
0x22ed0  brtrue.s loc_22EF5
0x22ed2  ldarg.1
0x22ed3  ldc.i4.s 0x6A
0x22ed5  ldarg.1
0x22ed6  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x22edb  ldarg.1
0x22edc  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x22ee1  stloc.3
0x22ee2  ldloca.s 3
0x22ee4  call     instance string Microsoft.ReportingServices.Modeling.SRObjectDescriptor::get_ObjectName()
0x22ee9  call     string Microsoft.ReportingServices.Modeling.SRErrors::ParameterExpressionCardinalityMismatch(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string objectName)
0x22eee  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x22ef3  ldc.i4.0
0x22ef4  stloc.1
0x22ef5  ldarg.0
0x22ef6  ldloc.1
0x22ef7  stfld    bool Microsoft.ReportingServices.Modeling.Parameter::m_compiledExprIsValid
0x22efc  leave.s  loc_22F05
0x22efe  ldarg.1
0x22eff  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::PopScope()
0x22f04  endfinally
0x22f05  ret
```
