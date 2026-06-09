# Microsoft.ReportingServices.ReportProcessing.ReportRuntime::EvaluateCommandText

- ea: `0x1c5930`
- end: `0x1c59c4`
- name: `Microsoft.ReportingServices.ReportProcessing.ReportRuntime::EvaluateCommandText`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x25a110`

## callees

- `0x197800`
- `0x197840`
- `0x197a60`
- `0x198440`
- `0x1c5930`
- `0x1c7d70`
- `0x1c7ee0`
- `0x1c7f80`
- `0x1c8280`
- `0x1d0820`
- `0x1d1af0`

## string_xrefs

- `0x1c5944`: `CommandText`

## pseudocode

```c

```

## disassembly

```asm
0x1c5930  ldarg.0
0x1c5931  ldarg.1
0x1c5932  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportQuery Microsoft.ReportingServices.ReportProcessing.DataSet::get_Query()
0x1c5937  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ReportQuery::get_CommandText()
0x1c593c  ldc.i4.s 0x16
0x1c593e  ldarg.1
0x1c593f  callvirt instance string Microsoft.ReportingServices.ReportProcessing.DataSet::get_Name()
0x1c5944  ldstr    aCommandtext// "CommandText"
0x1c5949  ldloca.s 0
0x1c594b  call     instance bool Microsoft.ReportingServices.ReportProcessing.ReportRuntime::EvaluateSimpleExpression(class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo expression, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, [out] valuetype Microsoft.ReportingServices.ReportProcessing.VariantResult& result)
0x1c5950  brtrue.s loc_1C59BC
0x1c5952  ldarg.0
0x1c5953  ldarg.1
0x1c5954  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportQuery Microsoft.ReportingServices.ReportProcessing.DataSet::get_Query()
0x1c5959  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ReportQuery::get_CommandText()
0x1c595e  ldloca.s 0
0x1c5960  call     instance bool Microsoft.ReportingServices.ReportProcessing.ReportRuntime::EvaluateComplexExpression(class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo expression, valuetype Microsoft.ReportingServices.ReportProcessing.VariantResult& result)
0x1c5965  brtrue.s loc_1C59AE
0x1c5967  ldarg.0
0x1c5968  ldfld    class Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ObjectModelImpl Microsoft.ReportingServices.ReportProcessing.ReportRuntime::m_reportObjectModel
0x1c596d  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.UserImpl Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ObjectModelImpl::get_UserImpl()
0x1c5972  ldc.i4.1
0x1c5973  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.UserImpl::set_UserProfileLocation(valuetype Microsoft.ReportingServices.ReportProcessing.UserProfileState value)
0x1c5978  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1c597d  ldarg.1
0x1c597e  callvirt instance class [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataSetExprHost Microsoft.ReportingServices.ReportProcessing.DataSet::get_ExprHost()
0x1c5983  ldnull
0x1c5984  cgt.un
0x1c5986  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool)
0x1c598b  ldloca.s 0
0x1c598d  ldarg.1
0x1c598e  callvirt instance class [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataSetExprHost Microsoft.ReportingServices.ReportProcessing.DataSet::get_ExprHost()
0x1c5993  callvirt instance object [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataSetExprHost::get_QueryCommandTextExpr()
0x1c5998  stfld    object Microsoft.ReportingServices.ReportProcessing.VariantResult::Value
0x1c599d  ldarg.0
0x1c599e  ldfld    class Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ObjectModelImpl Microsoft.ReportingServices.ReportProcessing.ReportRuntime::m_reportObjectModel
0x1c59a3  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.UserImpl Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ObjectModelImpl::get_UserImpl()
0x1c59a8  ldc.i4.2
0x1c59a9  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.UserImpl::set_UserProfileLocation(valuetype Microsoft.ReportingServices.ReportProcessing.UserProfileState value)
0x1c59ae  leave.s  loc_1C59BC
0x1c59b0  stloc.1
0x1c59b1  ldarg.0
0x1c59b2  ldloca.s 0
0x1c59b4  ldloc.1
0x1c59b5  call     instance void Microsoft.ReportingServices.ReportProcessing.ReportRuntime::RegisterRuntimeErrorInExpression(valuetype Microsoft.ReportingServices.ReportProcessing.VariantResult& result, class [mscorlib]System.Exception e)
0x1c59ba  leave.s  loc_1C59BC
0x1c59bc  ldarg.0
0x1c59bd  ldloc.0
0x1c59be  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.StringResult Microsoft.ReportingServices.ReportProcessing.ReportRuntime::ProcessStringResult(valuetype Microsoft.ReportingServices.ReportProcessing.VariantResult result)
0x1c59c3  ret
```
