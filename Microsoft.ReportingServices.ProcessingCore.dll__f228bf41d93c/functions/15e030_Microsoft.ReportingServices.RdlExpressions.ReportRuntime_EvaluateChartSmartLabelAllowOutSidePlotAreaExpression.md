# Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluateChartSmartLabelAllowOutSidePlotAreaExpression

- ea: `0x15e030`
- end: `0x15e091`
- name: `Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluateChartSmartLabelAllowOutSidePlotAreaExpression`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0xff990`

## callees

- `0xff210`
- `0xff220`
- `0x15e030`
- `0x163f10`
- `0x164200`
- `0x164ac0`
- `0x237fb0`

## string_xrefs

- `0x15e04c`: `AllowOutSidePlotArea`

## pseudocode

```c

```

## disassembly

```asm
0x15e030  newobj   instance void <>c__DisplayClass410_0::.ctor()
0x15e035  stloc.0
0x15e036  ldloc.0
0x15e037  ldarg.1
0x15e038  stfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel <>c__DisplayClass410_0::chartSmartLabel
0x15e03d  ldarg.0
0x15e03e  ldloc.0
0x15e03f  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel <>c__DisplayClass410_0::chartSmartLabel
0x15e044  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::get_AllowOutSidePlotArea()
0x15e049  ldc.i4.s 0x10
0x15e04b  ldarg.2
0x15e04c  ldstr    aAllowoutsidepl// "AllowOutSidePlotArea"
0x15e051  ldloca.s 1
0x15e053  call     instance bool Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluateSimpleExpression(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, [out] valuetype Microsoft.ReportingServices.RdlExpressions.VariantResult& result)
0x15e058  brtrue.s loc_15E084
0x15e05a  ldarg.0
0x15e05b  ldloc.0
0x15e05c  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel <>c__DisplayClass410_0::chartSmartLabel
0x15e061  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::get_AllowOutSidePlotArea()
0x15e066  ldloca.s 1
0x15e068  ldloc.0
0x15e069  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel <>c__DisplayClass410_0::chartSmartLabel
0x15e06e  callvirt instance class [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ChartSmartLabelExprHost Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::get_ExprHost()
0x15e073  ldloc.0
0x15e074  ldftn    instance object <>c__DisplayClass410_0::<EvaluateChartSmartLabelAllowOutSidePlotAreaExpression>b__0()
0x15e07a  newobj   instance void class [mscorlib]System.Func`1<object>::.ctor(object, native int)
0x15e07f  call     instance void Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluateComplexExpression(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression, valuetype Microsoft.ReportingServices.RdlExpressions.VariantResult& result, class [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy exprHost, class [mscorlib]System.Func`1<object> expressionExecution)
0x15e084  ldarg.0
0x15e085  ldloc.1
0x15e086  call     instance valuetype Microsoft.ReportingServices.RdlExpressions.StringResult Microsoft.ReportingServices.RdlExpressions.ReportRuntime::ProcessStringResult(valuetype Microsoft.ReportingServices.RdlExpressions.VariantResult result)
0x15e08b  ldfld    string Microsoft.ReportingServices.RdlExpressions.StringResult::Value
0x15e090  ret
```
