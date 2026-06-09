# Microsoft.ReportingServices.Modeling.Expression::ProcessCompilationFlags

- ea: `0x192f0`
- end: `0x193eb`
- name: `Microsoft.ReportingServices.Modeling.Expression::ProcessCompilationFlags`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x18fe0`

## callees

- `0x8630`
- `0x8690`
- `0x97d0`
- `0x188e0`
- `0x192f0`
- `0x197c0`
- `0x197d0`
- `0x197e0`
- `0x19800`
- `0x19810`
- `0x19cd0`
- `0x19cf0`
- `0x24e40`
- `0x24e60`
- `0x25010`
- `0x25050`
- `0x251d0`
- `0x25a90`
- `0x25b70`

## string_xrefs

- `0x19303`: `ContextEntity is null in Expression.ProcessCompilationFlags(flags.QueryResult)`
- `0x1936b`: `Unknown flags combination with flags.MustFloat`

## pseudocode

```c

```

## disassembly

```asm
0x192f0  ldc.i4.1
0x192f1  stloc.0
0x192f2  ldarga.s 2
0x192f4  call     instance bool Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags::get_QueryResult()
0x192f9  brfalse.s loc_19333
0x192fb  ldarg.1
0x192fc  callvirt instance class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.CompilationContext::get_ContextEntity()
0x19301  brtrue.s loc_1930E
0x19303  ldstr    aContextentityI// "ContextEntity is null in Expression.Pro"...
0x19308  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1930d  throw
0x1930e  ldarga.s 3
0x19310  call     instance valuetype Microsoft.ReportingServices.Modeling.Cardinality Microsoft.ReportingServices.Modeling.ResultType::get_Cardinality()
0x19315  ldc.i4.1
0x19316  bne.un.s loc_19333
0x19318  ldarg.1
0x19319  ldc.i4.s 0x57
0x1931b  ldarg.1
0x1931c  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x19321  ldarg.1
0x19322  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.CompilationContext::get_ContextEntityDescriptor()
0x19327  call     string Microsoft.ReportingServices.Modeling.SRErrors::TopLevelSetExpression(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor expressionTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor entityTypeAndName)
0x1932c  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x19331  ldc.i4.0
0x19332  stloc.0
0x19333  ldarga.s 2
0x19335  call     instance bool Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags::get_MustFloat()
0x1933a  brfalse.s loc_1938B
0x1933c  ldarg.0
0x1933d  call     instance bool Microsoft.ReportingServices.Modeling.Expression::IsSubtreeAnchored()
0x19342  brfalse.s loc_1938B
0x19344  ldarga.s 2
0x19346  call     instance bool Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags::get_IsModelAttribute()
0x1934b  brfalse.s loc_19362
0x1934d  ldarg.1
0x1934e  ldc.i4.s 0x49
0x19350  ldarg.1
0x19351  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x19356  call     string Microsoft.ReportingServices.Modeling.SRErrors::NonAggregateExpression_Attribute(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0x1935b  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x19360  br.s     loc_19389
0x19362  ldarga.s 2
0x19364  call     instance bool Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags::get_IsMeasure()
0x19369  brtrue.s loc_19376
0x1936b  ldstr    aUnknownFlagsCo// "Unknown flags combination with flags.Mu"...
0x19370  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x19375  throw
0x19376  ldarg.1
0x19377  ldc.i4.s 0x49
0x19379  ldarg.1
0x1937a  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x1937f  call     string Microsoft.ReportingServices.Modeling.SRErrors::NonAggregateExpression_Measure(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0x19384  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x19389  ldc.i4.0
0x1938a  stloc.0
0x1938b  ldarga.s 2
0x1938d  call     instance bool Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags::get_IsFilter()
0x19392  brfalse.s loc_193E9
0x19394  ldarga.s 3
0x19396  call     instance valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.ResultType::get_DataType()
0x1939b  ldc.i4.4
0x1939c  beq.s    loc_193C4
0x1939e  ldarga.s 3
0x193a0  call     instance valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.ResultType::get_DataType()
0x193a5  ldc.i4.8
0x193a6  beq.s    loc_193C4
0x193a8  ldarg.1
0x193a9  ldc.i4.s 0x62
0x193ab  ldarg.1
0x193ac  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x193b1  ldarga.s 3
0x193b3  call     instance valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.ResultType::get_DataType()
0x193b8  call     string Microsoft.ReportingServices.Modeling.SRErrors::InvalidFilter(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.DataType dataType)
0x193bd  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x193c2  ldc.i4.0
0x193c3  stloc.0
0x193c4  ldarga.s 3
0x193c6  call     instance valuetype Microsoft.ReportingServices.Modeling.Cardinality Microsoft.ReportingServices.Modeling.ResultType::get_Cardinality()
0x193cb  ldc.i4.1
0x193cc  bne.un.s loc_193E9
0x193ce  ldarg.1
0x193cf  ldc.i4.s 0x57
0x193d1  ldarg.1
0x193d2  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x193d7  ldarg.1
0x193d8  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.CompilationContext::get_ContextEntityDescriptor()
0x193dd  call     string Microsoft.ReportingServices.Modeling.SRErrors::TopLevelSetExpression_Filter(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor entityTypeAndName)
0x193e2  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x193e7  ldc.i4.0
0x193e8  stloc.0
0x193e9  ldloc.0
0x193ea  ret
```
