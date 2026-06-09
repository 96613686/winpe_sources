# Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.AggregatesImpl::GetAggregateValue

- ea: `0x1ee840`
- end: `0x1ee8f9`
- name: `Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.AggregatesImpl::GetAggregateValue`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1ee790`

## callees

- `0xf0ee0`
- `0xf1030`
- `0x175920`
- `0x175950`
- `0x175e20`
- `0x17c2a0`
- `0x1ee840`
- `0x1ee900`
- `0x1fc460`

## string_xrefs

- `0x1ee861`: `Missing aggregate result outside of tablix processing`

## pseudocode

```c

```

## disassembly

```asm
0x1ee840  ldarg.2
0x1ee841  ldc.i4.1
0x1ee842  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObj::set_UsedInExpression(bool value)
0x1ee847  ldarg.2
0x1ee848  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObjResult Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObj::AggregateResult()
0x1ee84d  stloc.0
0x1ee84e  ldloc.0
0x1ee84f  brtrue.s loc_1EE871
0x1ee851  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1ee856  ldarg.0
0x1ee857  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.AggregatesImpl::m_odpContext
0x1ee85c  callvirt instance bool Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_IsTablixProcessingMode()
0x1ee861  ldstr    aMissingAggrega_0// "Missing aggregate result outside of tab"...
0x1ee866  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x1ee86b  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException_MissingAggregateDependency::.ctor()
0x1ee870  throw
0x1ee871  ldloc.0
0x1ee872  ldfld    bool Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObjResult::HasCode
0x1ee877  brfalse.s loc_1EE8DF
0x1ee879  ldloc.0
0x1ee87a  ldfld    valuetype Microsoft.ReportingServices.ReportProcessing.DataFieldStatus Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObjResult::FieldStatus
0x1ee87f  brfalse.s loc_1EE88A
0x1ee881  ldloc.0
0x1ee882  ldfld    valuetype Microsoft.ReportingServices.ReportProcessing.DataFieldStatus Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObjResult::FieldStatus
0x1ee887  ldc.i4.8
0x1ee888  bne.un.s loc_1EE8B1
0x1ee88a  ldloc.0
0x1ee88b  ldfld    valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObjResult::Code
0x1ee890  brfalse.s loc_1EE8B1
0x1ee892  ldarg.0
0x1ee893  call     instance class Microsoft.ReportingServices.ReportProcessing.IErrorContext Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.AggregatesImpl::get_ErrorContext()
0x1ee898  ldloc.0
0x1ee899  ldfld    valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObjResult::Code
0x1ee89e  ldloc.0
0x1ee89f  ldfld    valuetype Microsoft.ReportingServices.ReportProcessing.Severity Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObjResult::Severity
0x1ee8a4  ldloc.0
0x1ee8a5  ldfld    string[] Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObjResult::Arguments
0x1ee8aa  callvirt instance void Microsoft.ReportingServices.ReportProcessing.IErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, string[] arguments)
0x1ee8af  br.s     loc_1EE8D1
0x1ee8b1  ldloc.0
0x1ee8b2  ldfld    valuetype Microsoft.ReportingServices.ReportProcessing.DataFieldStatus Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObjResult::FieldStatus
0x1ee8b7  ldc.i4.2
0x1ee8b8  bne.un.s loc_1EE8D1
0x1ee8ba  ldarg.0
0x1ee8bb  call     instance class Microsoft.ReportingServices.ReportProcessing.IErrorContext Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.AggregatesImpl::get_ErrorContext()
0x1ee8c0  ldc.i4   0x1A0
0x1ee8c5  ldc.i4.1
0x1ee8c6  ldloc.0
0x1ee8c7  ldfld    string[] Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObjResult::Arguments
0x1ee8cc  callvirt instance void Microsoft.ReportingServices.ReportProcessing.IErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, string[] arguments)
0x1ee8d1  ldloc.0
0x1ee8d2  ldfld    bool Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObjResult::ErrorOccurred
0x1ee8d7  brfalse.s loc_1EE8DF
0x1ee8d9  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException_InvalidOperationException::.ctor()
0x1ee8de  throw
0x1ee8df  ldloc.0
0x1ee8e0  ldfld    bool Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObjResult::ErrorOccurred
0x1ee8e5  brfalse.s loc_1EE8F2
0x1ee8e7  ldc.i4   0xFC
0x1ee8ec  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code)
0x1ee8f1  throw
0x1ee8f2  ldloc.0
0x1ee8f3  ldfld    object Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObjResult::Value
0x1ee8f8  ret
```
