# Microsoft.ReportingServices.Modeling.Expression::CompileCore

- ea: `0x190e0`
- end: `0x19213`
- name: `Microsoft.ReportingServices.Modeling.Expression::CompileCore`
- size: `307`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x18a60`
- `0x18fe0`

## callees

- `0x84f0`
- `0x8720`
- `0x8740`
- `0x97d0`
- `0x9cf0`
- `0x9f10`
- `0x18820`
- `0x18830`
- `0x190e0`
- `0x19220`
- `0x19250`
- `0x193f0`
- `0x19d00`
- `0x19d20`
- `0x1a190`
- `0x1df90`
- `0x1dfa0`
- `0x1e170`
- `0x25a70`

## string_xrefs

- `0x19127`: `Failed to compile expression path after applying security filters.`
- `0x19199`: `replacementExpr must be compiled`

## pseudocode

```c

```

## disassembly

```asm
0x190e0  ldarg.0
0x190e1  ldarg.1
0x190e2  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldPersist()
0x190e7  call     instance void Microsoft.ReportingServices.Modeling.ExtensibleModelingObject::Compile(bool shouldPersist)
0x190ec  ldloca.s 0
0x190ee  initobj  Microsoft.ReportingServices.Modeling.ResultType
0x190f4  ldarg.0
0x190f5  ldarg.1
0x190f6  ldloca.s 1
0x190f8  ldloca.s 2
0x190fa  call     instance class Microsoft.ReportingServices.Modeling.ExpressionPath Microsoft.ReportingServices.Modeling.Expression::CompilePath(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, [out] class Microsoft.ReportingServices.Modeling.IQueryEntity& desiredTargetEntity, [out] class Microsoft.ReportingServices.Modeling.IQueryEntity& actualTargetEntity)
0x190ff  stloc.3
0x19100  ldloc.3
0x19101  brtrue.s loc_1910E
0x19103  ldloca.s 4
0x19105  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>
0x1910b  ldloc.s  4
0x1910d  ret
0x1910e  ldarg.0
0x1910f  ldarg.1
0x19110  ldarg.2
0x19111  call     instance bool Microsoft.ReportingServices.Modeling.Expression::ApplySecurityFilters(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags flags)
0x19116  brfalse.s loc_19132
0x19118  ldarg.0
0x19119  ldarg.1
0x1911a  ldloca.s 1
0x1911c  ldloca.s 2
0x1911e  call     instance class Microsoft.ReportingServices.Modeling.ExpressionPath Microsoft.ReportingServices.Modeling.Expression::CompilePath(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, [out] class Microsoft.ReportingServices.Modeling.IQueryEntity& desiredTargetEntity, [out] class Microsoft.ReportingServices.Modeling.IQueryEntity& actualTargetEntity)
0x19123  stloc.3
0x19124  ldloc.3
0x19125  brtrue.s loc_19132
0x19127  ldstr    aFailedToCompil// "Failed to compile expression path after"...
0x1912c  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x19131  throw
0x19132  ldarg.1
0x19133  ldloc.2
0x19134  callvirt instance void Microsoft.ReportingServices.Modeling.CompilationContext::PushContextEntity(class Microsoft.ReportingServices.Modeling.IQueryEntity entity)
0x19139  ldarg.0
0x1913a  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionNode Microsoft.ReportingServices.Modeling.Expression::m_node
0x1913f  brtrue.s loc_19159
0x19141  ldarg.0
0x19142  ldarg.1
0x19143  call     instance void Microsoft.ReportingServices.Modeling.Expression::AddInvalidExpressionError(class Microsoft.ReportingServices.Modeling.ValidationContext ctx)
0x19148  ldloca.s 4
0x1914a  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>
0x19150  ldloc.s  4
0x19152  stloc.s  4
0x19154  leave    loc_19210
0x19159  ldarg.0
0x1915a  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionNode Microsoft.ReportingServices.Modeling.Expression::m_node
0x1915f  ldarg.1
0x19160  ldarg.1
0x19161  callvirt instance class Microsoft.ReportingServices.Modeling.IValidationScope Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentScope()
0x19166  ldarg.0
0x19167  ceq
0x19169  ldloca.s 5
0x1916b  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType> Microsoft.ReportingServices.Modeling.ExpressionNode::Compile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, bool topLevel, [out] class Microsoft.ReportingServices.Modeling.Expression& replacementExpr)
0x19170  stloc.s  6
0x19172  ldloca.s 6
0x19174  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::get_HasValue()
0x19179  brtrue.s loc_1918C
0x1917b  ldloca.s 7
0x1917d  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>
0x19183  ldloc.s  7
0x19185  stloc.s  4
0x19187  leave    loc_19210
0x1918c  ldloc.s  5
0x1918e  brfalse.s loc_191C3
0x19190  ldloc.s  5
0x19192  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingObject::get_IsCompiled()
0x19197  brtrue.s loc_191A4
0x19199  ldstr    aReplacementexp// "replacementExpr must be compiled"
0x1919e  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x191a3  throw
0x191a4  ldarg.0
0x191a5  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionPath Microsoft.ReportingServices.Modeling.Expression::m_path
0x191aa  ldloc.s  5
0x191ac  callvirt instance class Microsoft.ReportingServices.Modeling.ExpressionPath Microsoft.ReportingServices.Modeling.Expression::get_Path()
0x191b1  callvirt instance void Microsoft.ReportingServices.Modeling.ExpressionPath::AddRangeInternal(class Microsoft.ReportingServices.Modeling.ExpressionPath path)
0x191b6  ldarg.0
0x191b7  ldloc.s  5
0x191b9  callvirt instance class Microsoft.ReportingServices.Modeling.ExpressionNode Microsoft.ReportingServices.Modeling.Expression::get_Node()
0x191be  stfld    class Microsoft.ReportingServices.Modeling.ExpressionNode Microsoft.ReportingServices.Modeling.Expression::m_node
0x191c3  ldloca.s 6
0x191c5  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::get_Value()
0x191ca  stloc.0
0x191cb  ldloc.3
0x191cc  callvirt instance valuetype Microsoft.ReportingServices.Modeling.Cardinality Microsoft.ReportingServices.Modeling.ExpressionPath::GetCardinality()
0x191d1  ldc.i4.1
0x191d2  bne.un.s loc_191DC
0x191d4  ldloca.s 0
0x191d6  ldc.i4.1
0x191d7  call     instance void Microsoft.ReportingServices.Modeling.ResultType::set_Cardinality(valuetype Microsoft.ReportingServices.Modeling.Cardinality value)
0x191dc  ldloc.3
0x191dd  callvirt instance valuetype Microsoft.ReportingServices.Modeling.Optionality Microsoft.ReportingServices.Modeling.ExpressionPath::GetOptionality()
0x191e2  brtrue.s loc_191EC
0x191e4  ldloca.s 0
0x191e6  ldc.i4.1
0x191e7  call     instance void Microsoft.ReportingServices.Modeling.ResultType::set_Nullable(bool value)
0x191ec  leave.s  loc_191F5
0x191ee  ldarg.1
0x191ef  callvirt instance void Microsoft.ReportingServices.Modeling.CompilationContext::PopContextEntity()
0x191f4  endfinally
0x191f5  ldarg.1
0x191f6  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldPersist()
0x191fb  brfalse.s loc_19209
0x191fd  ldarg.0
0x191fe  ldloc.0
0x191ff  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::.ctor(var<u1>)
0x19204  stfld    valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType> Microsoft.ReportingServices.Modeling.Expression::m_compiledResultType
0x19209  ldloc.0
0x1920a  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::.ctor(var<u1>)
0x1920f  ret
0x19210  ldloc.s  4
0x19212  ret
```
