# Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.DataProcessingController::AllRowsRead

- ea: `0x210670`
- end: `0x210722`
- name: `Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.DataProcessingController::AllRowsRead`
- size: `178`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x225550`
- `0x2262b0`

## callees

- `0x121db0`
- `0x1fc860`
- `0x1fc870`
- `0x1fc930`
- `0x1fc940`
- `0x210670`
- `0x210730`
- `0x210780`
- `0x210860`
- `0x210890`
- `0x225990`

## string_xrefs

- `0x21068c`: `TablixProcessing: FirstPass Complete`
- `0x2106da`: `TablixProcessing: ApplyUserSorts Complete`
- `0x2106f0`: `TablixProcessing: SortAndFilter Complete`
- `0x210711`: `TablixProcessing: PostSortOperations Complete`

## pseudocode

```c

```

## disassembly

```asm
0x210670  ldarg.0
0x210671  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.RuntimeOnDemandDataSetObj Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.DataProcessingController::m_dataSetObj
0x210676  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.RuntimeOnDemandDataSetObj::FinishReadingRows()
0x21067b  ldarg.0
0x21067c  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.DataProcessingController::m_odpContext
0x210681  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::FirstPassPostProcess()
0x210686  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x21068b  ldc.i4.4
0x21068c  ldstr    aTablixprocessi// "TablixProcessing: FirstPass Complete"
0x210691  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x210696  ldarg.0
0x210697  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Report Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.DataProcessingController::m_report
0x21069c  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.Report::get_HasAggregatesOfAggregatesInUserSort()
0x2106a1  brfalse.s loc_2106C9
0x2106a3  ldarg.0
0x2106a4  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.DataProcessingController::m_odpContext
0x2106a9  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.RuntimeSortFilterEventInfo>> Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_RuntimeSortFilterInfo()
0x2106ae  brfalse.s loc_2106C9
0x2106b0  ldarg.0
0x2106b1  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.DataProcessingController::m_odpContext
0x2106b6  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.RuntimeSortFilterEventInfo>> Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_RuntimeSortFilterInfo()
0x2106bb  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.RuntimeSortFilterEventInfo>>::get_Count()
0x2106c0  ldc.i4.0
0x2106c1  ble.s    loc_2106C9
0x2106c3  ldarg.0
0x2106c4  call     instance void Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.DataProcessingController::PreComputeAggregatesOfAggregates()
0x2106c9  ldarg.0
0x2106ca  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.DataProcessingController::m_odpContext
0x2106cf  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::ApplyUserSorts()
0x2106d4  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x2106d9  ldc.i4.4
0x2106da  ldstr    aTablixprocessi_0// "TablixProcessing: ApplyUserSorts Comple"...
0x2106df  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x2106e4  ldarg.0
0x2106e5  call     instance void Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.DataProcessingController::SortAndFilter()
0x2106ea  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x2106ef  ldc.i4.4
0x2106f0  ldstr    aTablixprocessi_1// "TablixProcessing: SortAndFilter Complet"...
0x2106f5  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x2106fa  ldarg.0
0x2106fb  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.DataProcessingController::m_odpContext
0x210700  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::CheckAndThrowIfAborted()
0x210705  ldarg.0
0x210706  call     instance void Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.DataProcessingController::PostSortOperations()
0x21070b  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x210710  ldc.i4.4
0x210711  ldstr    aTablixprocessi_2// "TablixProcessing: PostSortOperations Co"...
0x210716  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x21071b  ldarg.0
0x21071c  call     instance void Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.DataProcessingController::StoreDataSetLevelAggregates()
0x210721  ret
```
