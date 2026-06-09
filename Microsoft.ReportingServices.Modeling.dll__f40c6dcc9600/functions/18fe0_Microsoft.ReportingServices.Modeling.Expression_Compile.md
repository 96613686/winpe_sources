# Microsoft.ReportingServices.Modeling.Expression::Compile

- ea: `0x18fe0`
- end: `0x190db`
- name: `Microsoft.ReportingServices.Modeling.Expression::Compile`
- size: `251`
- prototype: ``
- caller_count: `13`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0xfd10`
- `0x10a50`
- `0x18fa0`
- `0x19430`
- `0x19a10`
- `0x1a670`
- `0x1a8a0`
- `0x1ab10`
- `0x1b600`
- `0x1c1a0`
- `0x21b30`
- `0x21f00`
- `0x22d70`

## callees

- `0x8720`
- `0x8740`
- `0x8750`
- `0x8790`
- `0x9cf0`
- `0x18fe0`
- `0x190e0`
- `0x192f0`
- `0x197b0`
- `0x197f0`
- `0x19830`
- `0x24d80`
- `0x24da0`
- `0x24ff0`
- `0x25a70`
- `0x25a90`
- `0x25b70`
- `0x25bb0`
- `0x25be0`

## pseudocode

```c

```

## disassembly

```asm
0x18fe0  ldarg.1
0x18fe1  ldarg.0
0x18fe2  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::PushUniqueExpression(class Microsoft.ReportingServices.Modeling.Expression expression)
0x18fe7  brtrue.s loc_19023
0x18fe9  ldarg.1
0x18fea  callvirt instance class Microsoft.ReportingServices.Modeling.IValidationScope Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentScope()
0x18fef  isinst   Microsoft.ReportingServices.Modeling.Expression
0x18ff4  brfalse.s loc_19004
0x18ff6  ldarg.1
0x18ff7  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x18ffc  call     string Microsoft.ReportingServices.Modeling.SRErrors::CyclicExpression_ExpressionObject(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0x19001  stloc.0
0x19002  br.s     loc_19010
0x19004  ldarg.1
0x19005  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x1900a  call     string Microsoft.ReportingServices.Modeling.SRErrors::CyclicExpression(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0x1900f  stloc.0
0x19010  ldarg.1
0x19011  ldc.i4.s 0x46
0x19013  ldloc.0
0x19014  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x19019  ldloca.s 1
0x1901b  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>
0x19021  ldloc.1
0x19022  ret
0x19023  nop
0x19024  ldarga.s 2
0x19026  call     instance bool Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags::get_AllowPrecompiled()
0x1902b  brfalse.s loc_19041
0x1902d  ldarg.0
0x1902e  call     instance bool Microsoft.ReportingServices.Modeling.ModelingObject::get_IsCompiled()
0x19033  brfalse.s loc_19041
0x19035  ldarg.0
0x19036  ldfld    valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType> Microsoft.ReportingServices.Modeling.Expression::m_compiledResultType
0x1903b  stloc.1
0x1903c  leave    loc_190D9
0x19041  ldc.i4.0
0x19042  stloc.2
0x19043  ldc.i4.0
0x19044  stloc.3
0x19045  ldarga.s 2
0x19047  call     instance bool Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags::get_Named()
0x1904c  brfalse.s loc_19077
0x1904e  ldarg.0
0x1904f  ldfld    string Microsoft.ReportingServices.Modeling.Expression::m_name
0x19054  callvirt instance int32 [mscorlib]System.String::get_Length()
0x19059  brtrue.s loc_1906E
0x1905b  ldarg.1
0x1905c  ldc.i4.s 0x56
0x1905e  ldarg.1
0x1905f  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x19064  call     string Microsoft.ReportingServices.Modeling.SRErrors::MissingExpressionName(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0x19069  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x1906e  ldarg.1
0x1906f  ldarg.0
0x19070  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::PushScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x19075  ldc.i4.1
0x19076  stloc.2
0x19077  ldarga.s 2
0x19079  call     instance bool Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags::get_IsCalculatedAttribute()
0x1907e  brfalse.s loc_19089
0x19080  ldarg.1
0x19081  ldnull
0x19082  callvirt instance void Microsoft.ReportingServices.Modeling.CompilationContext::PushContextEntity(class Microsoft.ReportingServices.Modeling.IQueryEntity entity)
0x19087  ldc.i4.1
0x19088  stloc.3
0x19089  ldarg.0
0x1908a  ldarg.1
0x1908b  ldarg.2
0x1908c  call     instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType> Microsoft.ReportingServices.Modeling.Expression::CompileCore(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags flags)
0x19091  stloc.s  4
0x19093  ldloca.s 4
0x19095  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::get_HasValue()
0x1909a  brfalse.s loc_190BA
0x1909c  ldarg.0
0x1909d  ldarg.1
0x1909e  ldarg.2
0x1909f  ldloca.s 4
0x190a1  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::get_Value()
0x190a6  call     instance bool Microsoft.ReportingServices.Modeling.Expression::ProcessCompilationFlags(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags flags, valuetype Microsoft.ReportingServices.Modeling.ResultType result)
0x190ab  brtrue.s loc_190BA
0x190ad  ldloca.s 5
0x190af  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>
0x190b5  ldloc.s  5
0x190b7  stloc.1
0x190b8  leave.s  loc_190D9
0x190ba  ldloc.s  4
0x190bc  stloc.1
0x190bd  leave.s  loc_190D9
0x190bf  ldloc.3
0x190c0  brfalse.s loc_190C8
0x190c2  ldarg.1
0x190c3  callvirt instance void Microsoft.ReportingServices.Modeling.CompilationContext::PopContextEntity()
0x190c8  ldloc.2
0x190c9  brfalse.s loc_190D1
0x190cb  ldarg.1
0x190cc  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::PopScope()
0x190d1  endfinally
0x190d2  ldarg.1
0x190d3  callvirt instance void Microsoft.ReportingServices.Modeling.CompilationContext::PopUniqueExpression()
0x190d8  endfinally
0x190d9  ldloc.1
0x190da  ret
```
