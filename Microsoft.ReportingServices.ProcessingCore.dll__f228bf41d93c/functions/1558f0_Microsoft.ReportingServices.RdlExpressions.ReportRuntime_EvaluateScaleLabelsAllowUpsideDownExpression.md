# Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluateScaleLabelsAllowUpsideDownExpression

- ea: `0x1558f0`
- end: `0x155951`
- name: `Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluateScaleLabelsAllowUpsideDownExpression`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0xd07c0`

## callees

- `0xcfee0`
- `0xcfff0`
- `0x1558f0`
- `0x163f10`
- `0x164200`
- `0x164870`
- `0x23c0a0`

## string_xrefs

- `0x15590c`: `AllowUpsideDown`

## pseudocode

```c

```

## disassembly

```asm
0x1558f0  newobj   instance void <>c__DisplayClass82_0::.ctor()
0x1558f5  stloc.0
0x1558f6  ldloc.0
0x1558f7  ldarg.1
0x1558f8  stfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels <>c__DisplayClass82_0::scaleLabels
0x1558fd  ldarg.0
0x1558fe  ldloc.0
0x1558ff  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels <>c__DisplayClass82_0::scaleLabels
0x155904  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::get_AllowUpsideDown()
0x155909  ldc.i4.s 0xE
0x15590b  ldarg.2
0x15590c  ldstr    aAllowupsidedow// "AllowUpsideDown"
0x155911  ldloca.s 1
0x155913  call     instance bool Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluateSimpleExpression(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, [out] valuetype Microsoft.ReportingServices.RdlExpressions.VariantResult& result)
0x155918  brtrue.s loc_155944
0x15591a  ldarg.0
0x15591b  ldloc.0
0x15591c  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels <>c__DisplayClass82_0::scaleLabels
0x155921  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::get_AllowUpsideDown()
0x155926  ldloca.s 1
0x155928  ldloc.0
0x155929  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels <>c__DisplayClass82_0::scaleLabels
0x15592e  callvirt instance class [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ScaleLabelsExprHost Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::get_ExprHost()
0x155933  ldloc.0
0x155934  ldftn    instance object <>c__DisplayClass82_0::<EvaluateScaleLabelsAllowUpsideDownExpression>b__0()
0x15593a  newobj   instance void class [mscorlib]System.Func`1<object>::.ctor(object, native int)
0x15593f  call     instance void Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluateComplexExpression(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression, valuetype Microsoft.ReportingServices.RdlExpressions.VariantResult& result, class [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy exprHost, class [mscorlib]System.Func`1<object> expressionExecution)
0x155944  ldarg.0
0x155945  ldloc.1
0x155946  call     instance valuetype Microsoft.ReportingServices.RdlExpressions.BooleanResult Microsoft.ReportingServices.RdlExpressions.ReportRuntime::ProcessBooleanResult(valuetype Microsoft.ReportingServices.RdlExpressions.VariantResult result)
0x15594b  ldfld    bool Microsoft.ReportingServices.RdlExpressions.BooleanResult::Value
0x155950  ret
```
