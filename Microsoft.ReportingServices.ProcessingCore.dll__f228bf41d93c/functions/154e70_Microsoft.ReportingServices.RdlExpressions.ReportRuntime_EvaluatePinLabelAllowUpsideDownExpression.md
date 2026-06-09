# Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluatePinLabelAllowUpsideDownExpression

- ea: `0x154e70`
- end: `0x154ed1`
- name: `Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluatePinLabelAllowUpsideDownExpression`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0xc89f0`

## callees

- `0xc83a0`
- `0xc8470`
- `0x154e70`
- `0x163f10`
- `0x164200`
- `0x164870`
- `0x23ac80`

## string_xrefs

- `0x154e8c`: `AllowUpsideDown`

## pseudocode

```c

```

## disassembly

```asm
0x154e70  newobj   instance void <>c__DisplayClass58_0::.ctor()
0x154e75  stloc.0
0x154e76  ldloc.0
0x154e77  ldarg.1
0x154e78  stfld    class Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel <>c__DisplayClass58_0::pinLabel
0x154e7d  ldarg.0
0x154e7e  ldloc.0
0x154e7f  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel <>c__DisplayClass58_0::pinLabel
0x154e84  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::get_AllowUpsideDown()
0x154e89  ldc.i4.s 0xE
0x154e8b  ldarg.2
0x154e8c  ldstr    aAllowupsidedow// "AllowUpsideDown"
0x154e91  ldloca.s 1
0x154e93  call     instance bool Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluateSimpleExpression(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, [out] valuetype Microsoft.ReportingServices.RdlExpressions.VariantResult& result)
0x154e98  brtrue.s loc_154EC4
0x154e9a  ldarg.0
0x154e9b  ldloc.0
0x154e9c  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel <>c__DisplayClass58_0::pinLabel
0x154ea1  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::get_AllowUpsideDown()
0x154ea6  ldloca.s 1
0x154ea8  ldloc.0
0x154ea9  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel <>c__DisplayClass58_0::pinLabel
0x154eae  callvirt instance class [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.PinLabelExprHost Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::get_ExprHost()
0x154eb3  ldloc.0
0x154eb4  ldftn    instance object <>c__DisplayClass58_0::<EvaluatePinLabelAllowUpsideDownExpression>b__0()
0x154eba  newobj   instance void class [mscorlib]System.Func`1<object>::.ctor(object, native int)
0x154ebf  call     instance void Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluateComplexExpression(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression, valuetype Microsoft.ReportingServices.RdlExpressions.VariantResult& result, class [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy exprHost, class [mscorlib]System.Func`1<object> expressionExecution)
0x154ec4  ldarg.0
0x154ec5  ldloc.1
0x154ec6  call     instance valuetype Microsoft.ReportingServices.RdlExpressions.BooleanResult Microsoft.ReportingServices.RdlExpressions.ReportRuntime::ProcessBooleanResult(valuetype Microsoft.ReportingServices.RdlExpressions.VariantResult result)
0x154ecb  ldfld    bool Microsoft.ReportingServices.RdlExpressions.BooleanResult::Value
0x154ed0  ret
```
