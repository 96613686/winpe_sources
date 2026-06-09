# Microsoft.ReportingServices.Modeling.AttributeRefNode::VisitAggregationFloatPoints

- ea: `0x1b820`
- end: `0x1b889`
- name: `Microsoft.ReportingServices.Modeling.AttributeRefNode::VisitAggregationFloatPoints`
- size: `105`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x97d0`
- `0x186b0`
- `0x1a0b0`
- `0x1a350`
- `0x1b820`
- `0x24240`
- `0x36dd0`

## string_xrefs

- `0x1b87c`: `VisitAggregationFloatPoints: attempt to modify referenced expression when allowExprModification is false.`

## pseudocode

```c

```

## disassembly

```asm
0x1b820  ldarg.0
0x1b821  ldfld    class Microsoft.ReportingServices.Modeling.IQueryAttributeInternal Microsoft.ReportingServices.Modeling.AttributeRefNode::m_attribute
0x1b826  callvirt instance bool Microsoft.ReportingServices.Modeling.IQueryAttribute::IsAnchored()
0x1b82b  brfalse.s loc_1B838
0x1b82d  ldstr    aAttributerefno_0// "AttributeRefNode.VisitAggregationFloatP"...
0x1b832  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1b837  throw
0x1b838  ldarg.2
0x1b839  brtrue.s loc_1B83E
0x1b83b  ldarg.0
0x1b83c  br.s     loc_1B844
0x1b83e  ldarg.0
0x1b83f  call     instance class Microsoft.ReportingServices.Modeling.ExpressionNode Microsoft.ReportingServices.Modeling.ExpressionNode::Clone()
0x1b844  newobj   instance void Microsoft.ReportingServices.Modeling.Expression::.ctor(class Microsoft.ReportingServices.Modeling.ExpressionNode node)
0x1b849  stloc.0
0x1b84a  ldarg.2
0x1b84b  brfalse.s loc_1B872
0x1b84d  ldarg.1
0x1b84e  ldloc.0
0x1b84f  ldarg.2
0x1b850  callvirt instance class Microsoft.ReportingServices.Modeling.Expression FloatPointVisitor::Invoke(class Microsoft.ReportingServices.Modeling.Expression expression, bool allowExprModification)
0x1b855  dup
0x1b856  brtrue.s loc_1B85A
0x1b858  pop
0x1b859  ldloc.0
0x1b85a  stloc.0
0x1b85b  ldc.i4.s 0x40
0x1b85d  ldc.i4.1
0x1b85e  newarr   Microsoft.ReportingServices.Modeling.Expression
0x1b863  dup
0x1b864  ldc.i4.0
0x1b865  ldloc.0
0x1b866  stelem.ref
0x1b867  newobj   instance void Microsoft.ReportingServices.Modeling.FunctionNode::.ctor(valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, class Microsoft.ReportingServices.Modeling.Expression[] arguments)
0x1b86c  newobj   instance void Microsoft.ReportingServices.Modeling.Expression::.ctor(class Microsoft.ReportingServices.Modeling.ExpressionNode node)
0x1b871  ret
0x1b872  ldarg.1
0x1b873  ldloc.0
0x1b874  ldarg.2
0x1b875  callvirt instance class Microsoft.ReportingServices.Modeling.Expression FloatPointVisitor::Invoke(class Microsoft.ReportingServices.Modeling.Expression expression, bool allowExprModification)
0x1b87a  brfalse.s loc_1B887
0x1b87c  ldstr    aVisitaggregati_1// "VisitAggregationFloatPoints: attempt to"...
0x1b881  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1b886  throw
0x1b887  ldnull
0x1b888  ret
```
