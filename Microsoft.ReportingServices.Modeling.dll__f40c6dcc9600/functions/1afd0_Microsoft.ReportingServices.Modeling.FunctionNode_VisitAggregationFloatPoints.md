# Microsoft.ReportingServices.Modeling.FunctionNode::VisitAggregationFloatPoints

- ea: `0x1afd0`
- end: `0x1b075`
- name: `Microsoft.ReportingServices.Modeling.FunctionNode::VisitAggregationFloatPoints`
- size: `165`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x97d0`
- `0x18830`
- `0x1a1b0`
- `0x1afb0`
- `0x1afd0`
- `0x21140`
- `0x211b0`
- `0x36dd0`

## string_xrefs

- `0x1b049`: `VisitAggregationFloatPoints: attempt to modify function argument when allowExprModification is false.`

## pseudocode

```c

```

## disassembly

```asm
0x1afd0  ldarg.0
0x1afd1  call     instance class Microsoft.ReportingServices.Modeling.FunctionInfo Microsoft.ReportingServices.Modeling.FunctionNode::GetApproxFunctionInfo()
0x1afd6  stloc.0
0x1afd7  ldloc.0
0x1afd8  brtrue.s loc_1AFDC
0x1afda  ldnull
0x1afdb  ret
0x1afdc  ldloc.0
0x1afdd  callvirt instance bool Microsoft.ReportingServices.Modeling.FunctionInfo::get_IsPassthrough()
0x1afe2  brfalse.s loc_1B005
0x1afe4  ldstr    aVisitaggregati// "VisitAggregationFloatPoints is called o"...
0x1afe9  ldarg.0
0x1afea  ldflda   valuetype Microsoft.ReportingServices.Modeling.FunctionName Microsoft.ReportingServices.Modeling.FunctionNode::m_functionName
0x1afef  constrained. Microsoft.ReportingServices.Modeling.FunctionName
0x1aff5  callvirt instance string [mscorlib]System.Object::ToString()
0x1affa  call     string [mscorlib]System.String::Concat(string, string)
0x1afff  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1b004  throw
0x1b005  ldc.i4.0
0x1b006  stloc.1
0x1b007  br.s     loc_1B065
0x1b009  ldnull
0x1b00a  stloc.2
0x1b00b  ldloc.0
0x1b00c  ldloc.1
0x1b00d  callvirt instance bool Microsoft.ReportingServices.Modeling.FunctionInfo::IsAggregateArgument(int32 argumentIndex)
0x1b012  brfalse.s loc_1B02A
0x1b014  ldarg.1
0x1b015  ldarg.0
0x1b016  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionCollection Microsoft.ReportingServices.Modeling.FunctionNode::m_arguments
0x1b01b  ldloc.1
0x1b01c  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.Expression>::get_Item(!!T0)
0x1b021  ldarg.2
0x1b022  callvirt instance class Microsoft.ReportingServices.Modeling.Expression FloatPointVisitor::Invoke(class Microsoft.ReportingServices.Modeling.Expression expression, bool allowExprModification)
0x1b027  stloc.2
0x1b028  br.s     loc_1B043
0x1b02a  ldarg.0
0x1b02b  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionCollection Microsoft.ReportingServices.Modeling.FunctionNode::m_arguments
0x1b030  ldloc.1
0x1b031  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.Expression>::get_Item(!!T0)
0x1b036  callvirt instance class Microsoft.ReportingServices.Modeling.ExpressionNode Microsoft.ReportingServices.Modeling.Expression::get_Node()
0x1b03b  ldarg.1
0x1b03c  ldarg.2
0x1b03d  callvirt instance class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.ExpressionNode::VisitAggregationFloatPoints(class FloatPointVisitor visitor, bool allowExprModification)
0x1b042  stloc.2
0x1b043  ldloc.2
0x1b044  brfalse.s loc_1B061
0x1b046  ldarg.2
0x1b047  brtrue.s loc_1B054
0x1b049  ldstr    aVisitaggregati_0// "VisitAggregationFloatPoints: attempt to"...
0x1b04e  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1b053  throw
0x1b054  ldarg.0
0x1b055  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionCollection Microsoft.ReportingServices.Modeling.FunctionNode::m_arguments
0x1b05a  ldloc.1
0x1b05b  ldloc.2
0x1b05c  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.Expression>::set_Item(int32, var<u1>)
0x1b061  ldloc.1
0x1b062  ldc.i4.1
0x1b063  add
0x1b064  stloc.1
0x1b065  ldloc.1
0x1b066  ldarg.0
0x1b067  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionCollection Microsoft.ReportingServices.Modeling.FunctionNode::m_arguments
0x1b06c  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.Expression>::get_Count()
0x1b071  blt.s    loc_1B009
0x1b073  ldnull
0x1b074  ret
```
