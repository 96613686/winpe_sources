# Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObj::EvaluateParameters

- ea: `0xf10a0`
- end: `0xf113d`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObj::EvaluateParameters`
- size: `157`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x73510`
- `0xf0f50`

## callees

- `0xef690`
- `0xef6b0`
- `0xf10a0`
- `0x15c180`

## string_xrefs

- `0xf1119`: `Unfulfilled aggregate dependency outside of a previous`

## pseudocode

```c

```

## disassembly

```asm
0xf10a0  ldc.i4.0
0xf10a1  stloc.0
0xf10a2  ldarg.2
0xf10a3  ldc.i4.0
0xf10a4  stind.i4
0xf10a5  ldarg.1
0xf10a6  ldarg.0
0xf10a7  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObj::m_aggregateDef
0xf10ac  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo[] Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo::get_Expressions()
0xf10b1  ldlen
0xf10b2  conv.i4
0xf10b3  newarr   [mscorlib]System.Object
0xf10b8  stind.ref
0xf10b9  ldc.i4.0
0xf10ba  stloc.1
0xf10bb  br.s     loc_F1129
0xf10bd  nop
0xf10be  ldarg.0
0xf10bf  ldfld    class Microsoft.ReportingServices.RdlExpressions.ReportRuntime Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObj::m_reportRT
0xf10c4  ldarg.0
0xf10c5  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObj::m_aggregateDef
0xf10ca  ldloc.1
0xf10cb  ldarg.0
0xf10cc  callvirt instance valuetype Microsoft.ReportingServices.RdlExpressions.VariantResult Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluateAggregateVariantOrBinaryParamExpr(class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo aggregateInfo, int32 index, class Microsoft.ReportingServices.ReportProcessing.IErrorContext errorContext)
0xf10d1  stloc.2
0xf10d2  ldarg.1
0xf10d3  ldind.ref
0xf10d4  ldloc.1
0xf10d5  ldloc.2
0xf10d6  ldfld    object Microsoft.ReportingServices.RdlExpressions.VariantResult::Value
0xf10db  stelem.ref
0xf10dc  ldloc.0
0xf10dd  ldloc.2
0xf10de  ldfld    bool Microsoft.ReportingServices.RdlExpressions.VariantResult::ErrorOccurred
0xf10e3  or
0xf10e4  stloc.0
0xf10e5  ldloc.2
0xf10e6  ldfld    valuetype Microsoft.ReportingServices.ReportProcessing.DataFieldStatus Microsoft.ReportingServices.RdlExpressions.VariantResult::FieldStatus
0xf10eb  brfalse.s loc_F10F5
0xf10ed  ldarg.2
0xf10ee  ldloc.2
0xf10ef  ldfld    valuetype Microsoft.ReportingServices.ReportProcessing.DataFieldStatus Microsoft.ReportingServices.RdlExpressions.VariantResult::FieldStatus
0xf10f4  stind.i4
0xf10f5  leave.s  loc_F1125
0xf10f7  pop
0xf10f8  ldarg.0
0xf10f9  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObj::m_aggregateDef
0xf10fe  callvirt instance valuetype AggregateTypes Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo::get_AggregateType()
0xf1103  ldc.i4.s 0xE
0xf1105  bne.un.s loc_F1113
0xf1107  ldarg.1
0xf1108  ldind.ref
0xf1109  ldloc.1
0xf110a  ldnull
0xf110b  stelem.ref
0xf110c  ldarg.2
0xf110d  ldc.i4.0
0xf110e  stind.i4
0xf110f  ldc.i4.0
0xf1110  stloc.3
0xf1111  leave.s  loc_F113B
0xf1113  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0xf1118  ldc.i4.0
0xf1119  ldstr    aUnfulfilledAgg// "Unfulfilled aggregate dependency outsid"...
0xf111e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0xf1123  rethrow
0xf1125  ldloc.1
0xf1126  ldc.i4.1
0xf1127  add
0xf1128  stloc.1
0xf1129  ldloc.1
0xf112a  ldarg.0
0xf112b  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObj::m_aggregateDef
0xf1130  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo[] Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo::get_Expressions()
0xf1135  ldlen
0xf1136  conv.i4
0xf1137  blt.s    loc_F10BD
0xf1139  ldloc.0
0xf113a  ret
0xf113b  ldloc.3
0xf113c  ret
```
