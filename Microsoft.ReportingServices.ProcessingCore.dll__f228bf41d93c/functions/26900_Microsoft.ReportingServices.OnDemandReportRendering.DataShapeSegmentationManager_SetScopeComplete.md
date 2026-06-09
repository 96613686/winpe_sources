# Microsoft.ReportingServices.OnDemandReportRendering.DataShapeSegmentationManager::SetScopeComplete

- ea: `0x26900`
- end: `0x26943`
- name: `Microsoft.ReportingServices.OnDemandReportRendering.DataShapeSegmentationManager::SetScopeComplete`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x28910`

## callees

- `0x26a40`
- `0x27d90`
- `0x6d640`

## string_xrefs

- `0x2690e`: `SetScopeComplete should only be called for dynamic members.`
- `0x26926`: `SetScopeComplete should only be called for row members.`

## pseudocode

```c

```

## disassembly

```asm
0x26900  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ProcessingTracer()
0x26905  ldarg.1
0x26906  callvirt instance bool Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_IsStatic()
0x2690b  ldc.i4.0
0x2690c  ceq
0x2690e  ldstr    aSetscopecomple// "SetScopeComplete should only be called "...
0x26913  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x26918  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ProcessingTracer()
0x2691d  ldarg.1
0x2691e  callvirt instance bool Microsoft.ReportingServices.OnDemandReportRendering.DataShapeMember::get_IsColumn()
0x26923  ldc.i4.0
0x26924  ceq
0x26926  ldstr    aSetscopecomple_0// "SetScopeComplete should only be called "...
0x2692b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x26930  ldarg.0
0x26931  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<int32> Microsoft.ReportingServices.OnDemandReportRendering.DataShapeSegmentationManager::m_parentsWithScopeComplete
0x26936  ldarg.1
0x26937  call     int32 Microsoft.ReportingServices.OnDemandReportRendering.DataShapeSegmentationManager::GetParentID(class Microsoft.ReportingServices.OnDemandReportRendering.DataShapeMember member)
0x2693c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<int32>::Add(var<u1>)
0x26941  pop
0x26942  ret
```
