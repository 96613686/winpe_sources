# Microsoft.ReportingServices.Modeling.FunctionNode::ResolveAggregateAndCompile

- ea: `0x1a8a0`
- end: `0x1a998`
- name: `Microsoft.ReportingServices.Modeling.FunctionNode::ResolveAggregateAndCompile`
- size: `248`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a670`

## callees

- `0x84f0`
- `0x8530`
- `0x97d0`
- `0x9cf0`
- `0x186b0`
- `0x18830`
- `0x189a0`
- `0x18fe0`
- `0x1a0b0`
- `0x1a0f0`
- `0x1a1b0`
- `0x1a8a0`
- `0x1aad0`
- `0x1b330`
- `0x24e80`
- `0x25a90`
- `0x25b70`
- `0x36dc0`
- `0x36ee0`

## string_xrefs

- `0x1a8d4`: `ResolveAggregateAndCompile: aggregate argument must be compiled.`

## pseudocode

```c

```

## disassembly

```asm
0x1a8a0  newobj   instance void <>c__DisplayClass33_0::.ctor()
0x1a8a5  stloc.0
0x1a8a6  ldloc.0
0x1a8a7  ldarg.0
0x1a8a8  stfld    class Microsoft.ReportingServices.Modeling.FunctionNode <>c__DisplayClass33_0::<>4__this
0x1a8ad  ldloc.0
0x1a8ae  ldarg.0
0x1a8af  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionCollection Microsoft.ReportingServices.Modeling.FunctionNode::m_arguments
0x1a8b4  ldc.i4.0
0x1a8b5  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.Expression>::get_Item(!!T0)
0x1a8ba  stfld    class Microsoft.ReportingServices.Modeling.Expression <>c__DisplayClass33_0::floatPath
0x1a8bf  ldarg.1
0x1a8c0  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldNormalize()
0x1a8c5  brfalse.s loc_1A8DF
0x1a8c7  ldloc.0
0x1a8c8  ldfld    class Microsoft.ReportingServices.Modeling.Expression <>c__DisplayClass33_0::floatPath
0x1a8cd  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingObject::get_IsCompiled()
0x1a8d2  brtrue.s loc_1A8DF
0x1a8d4  ldstr    aResolveaggrega// "ResolveAggregateAndCompile: aggregate a"...
0x1a8d9  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1a8de  throw
0x1a8df  ldloc.0
0x1a8e0  ldarg.0
0x1a8e1  ldloc.0
0x1a8e2  ldfld    class Microsoft.ReportingServices.Modeling.Expression <>c__DisplayClass33_0::floatPath
0x1a8e7  call     instance class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.FunctionNode::FindFirstNonPassThruExpression(class Microsoft.ReportingServices.Modeling.Expression expression)
0x1a8ec  stfld    class Microsoft.ReportingServices.Modeling.Expression <>c__DisplayClass33_0::floatRootExpr
0x1a8f1  ldloc.0
0x1a8f2  ldfld    class Microsoft.ReportingServices.Modeling.Expression <>c__DisplayClass33_0::floatRootExpr
0x1a8f7  callvirt instance class Microsoft.ReportingServices.Modeling.ExpressionNode Microsoft.ReportingServices.Modeling.Expression::get_Node()
0x1a8fc  stloc.1
0x1a8fd  ldloc.1
0x1a8fe  callvirt instance bool Microsoft.ReportingServices.Modeling.ExpressionNode::IsSubtreeAnchored()
0x1a903  brfalse.s loc_1A91A
0x1a905  ldarg.1
0x1a906  ldc.i4.s 0x4A
0x1a908  ldarg.1
0x1a909  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x1a90e  call     string Microsoft.ReportingServices.Modeling.SRErrors::AggregateWithNonAggregateArgument(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0x1a913  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x1a918  ldnull
0x1a919  ret
0x1a91a  ldloc.1
0x1a91b  isinst   Microsoft.ReportingServices.Modeling.AttributeRefNode
0x1a920  brfalse.s loc_1A931
0x1a922  ldloc.1
0x1a923  castclass Microsoft.ReportingServices.Modeling.AttributeRefNode
0x1a928  callvirt instance bool Microsoft.ReportingServices.Modeling.AttributeRefNode::get_ReplaceWithExpression()
0x1a92d  brtrue.s loc_1A931
0x1a92f  ldnull
0x1a930  ret
0x1a931  ldarg.1
0x1a932  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldNormalize()
0x1a937  brfalse.s loc_1A996
0x1a939  ldarg.1
0x1a93a  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldPersist()
0x1a93f  brtrue.s loc_1A94C
0x1a941  ldstr    aNormalizeWitho// "Normalize without persist."
0x1a946  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1a94b  throw
0x1a94c  ldloc.1
0x1a94d  callvirt instance class Microsoft.ReportingServices.Modeling.ExpressionNode Microsoft.ReportingServices.Modeling.ExpressionNode::Clone()
0x1a952  newobj   instance void Microsoft.ReportingServices.Modeling.Expression::.ctor(class Microsoft.ReportingServices.Modeling.ExpressionNode node)
0x1a957  stloc.2
0x1a958  ldloc.2
0x1a959  callvirt instance void Microsoft.ReportingServices.Modeling.Expression::MarkAsSkipSecurityFilters()
0x1a95e  ldloc.2
0x1a95f  callvirt instance class Microsoft.ReportingServices.Modeling.ExpressionNode Microsoft.ReportingServices.Modeling.Expression::get_Node()
0x1a964  ldloc.0
0x1a965  ldftn    instance class Microsoft.ReportingServices.Modeling.Expression <>c__DisplayClass33_0::<ResolveAggregateAndCompile>b__0(class Microsoft.ReportingServices.Modeling.Expression expression, bool allowExprModification)
0x1a96b  newobj   instance void FloatPointVisitor::.ctor(object object, native int method)
0x1a970  ldc.i4.1
0x1a971  callvirt instance class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.ExpressionNode::VisitAggregationFloatPoints(class FloatPointVisitor visitor, bool allowExprModification)
0x1a976  dup
0x1a977  brtrue.s loc_1A97B
0x1a979  pop
0x1a97a  ldloc.2
0x1a97b  stloc.2
0x1a97c  ldloc.2
0x1a97d  ldarg.1
0x1a97e  ldsfld   valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags::None
0x1a983  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType> Microsoft.ReportingServices.Modeling.Expression::Compile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags flags)
0x1a988  stloc.3
0x1a989  ldloca.s 3
0x1a98b  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::get_HasValue()
0x1a990  brfalse.s loc_1A994
0x1a992  ldloc.2
0x1a993  ret
0x1a994  ldnull
0x1a995  ret
0x1a996  ldnull
0x1a997  ret
```
