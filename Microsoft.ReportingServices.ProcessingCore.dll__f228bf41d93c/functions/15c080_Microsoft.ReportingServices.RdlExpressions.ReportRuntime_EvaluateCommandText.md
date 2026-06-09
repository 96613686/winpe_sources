# Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluateCommandText

- ea: `0x15c080`
- end: `0x15c0fe`
- name: `Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluateCommandText`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1f81a0`

## callees

- `0x114be0`
- `0x114c30`
- `0x114f90`
- `0x116490`
- `0x15c080`
- `0x163f10`
- `0x164360`
- `0x164650`
- `0x164ac0`
- `0x236c50`

## string_xrefs

- `0x15c0ab`: `CommandText`

## pseudocode

```c

```

## disassembly

```asm
0x15c080  newobj   instance void <>c__DisplayClass342_0::.ctor()
0x15c085  stloc.0
0x15c086  ldloc.0
0x15c087  ldarg.1
0x15c088  stfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet <>c__DisplayClass342_0::dataSet
0x15c08d  ldarg.0
0x15c08e  ldloc.0
0x15c08f  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet <>c__DisplayClass342_0::dataSet
0x15c094  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ReportQuery Microsoft.ReportingServices.ReportIntermediateFormat.DataSet::get_Query()
0x15c099  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ReportQuery::get_CommandText()
0x15c09e  ldc.i4.s 0x16
0x15c0a0  ldloc.0
0x15c0a1  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet <>c__DisplayClass342_0::dataSet
0x15c0a6  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSet::get_Name()
0x15c0ab  ldstr    aCommandtext// "CommandText"
0x15c0b0  ldloca.s 1
0x15c0b2  call     instance bool Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluateSimpleExpression(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, [out] valuetype Microsoft.ReportingServices.RdlExpressions.VariantResult& result)
0x15c0b7  brtrue.s loc_15C0F6
0x15c0b9  ldarg.0
0x15c0ba  ldloc.0
0x15c0bb  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet <>c__DisplayClass342_0::dataSet
0x15c0c0  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ReportQuery Microsoft.ReportingServices.ReportIntermediateFormat.DataSet::get_Query()
0x15c0c5  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ReportQuery::get_CommandText()
0x15c0ca  ldloca.s 1
0x15c0cc  ldloc.0
0x15c0cd  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet <>c__DisplayClass342_0::dataSet
0x15c0d2  callvirt instance class [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.DataSetExprHost Microsoft.ReportingServices.ReportIntermediateFormat.DataSet::get_ExprHost()
0x15c0d7  ldloc.0
0x15c0d8  ldftn    instance object <>c__DisplayClass342_0::<EvaluateCommandText>b__0()
0x15c0de  newobj   instance void class [mscorlib]System.Func`1<object>::.ctor(object, native int)
0x15c0e3  call     instance void Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluateComplexExpressionForDataset(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression, valuetype Microsoft.ReportingServices.RdlExpressions.VariantResult& result, class [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy exprHost, class [mscorlib]System.Func`1<object> expressionExecution)
0x15c0e8  leave.s  loc_15C0F6
0x15c0ea  stloc.2
0x15c0eb  ldarg.0
0x15c0ec  ldloca.s 1
0x15c0ee  ldloc.2
0x15c0ef  call     instance void Microsoft.ReportingServices.RdlExpressions.ReportRuntime::RegisterRuntimeErrorInExpression(valuetype Microsoft.ReportingServices.RdlExpressions.VariantResult& result, class [mscorlib]System.Exception e)
0x15c0f4  leave.s  loc_15C0F6
0x15c0f6  ldarg.0
0x15c0f7  ldloc.1
0x15c0f8  call     instance valuetype Microsoft.ReportingServices.RdlExpressions.StringResult Microsoft.ReportingServices.RdlExpressions.ReportRuntime::ProcessStringResult(valuetype Microsoft.ReportingServices.RdlExpressions.VariantResult result)
0x15c0fd  ret
```
