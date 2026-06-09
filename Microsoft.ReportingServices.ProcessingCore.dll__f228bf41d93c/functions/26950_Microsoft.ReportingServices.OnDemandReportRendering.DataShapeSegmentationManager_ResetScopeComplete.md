# Microsoft.ReportingServices.OnDemandReportRendering.DataShapeSegmentationManager::ResetScopeComplete

- ea: `0x26950`
- end: `0x26993`
- name: `Microsoft.ReportingServices.OnDemandReportRendering.DataShapeSegmentationManager::ResetScopeComplete`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x288e0`

## callees

- `0x26a40`
- `0x27d90`
- `0x6d640`

## string_xrefs

- `0x2695e`: `ResetScopeComplete should only be called for dynamic members.`
- `0x26976`: `ResetScopeComplete should only be called for row members.`

## pseudocode

```c

```

## disassembly

```asm
0x26950  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ProcessingTracer()
0x26955  ldarg.1
0x26956  callvirt instance bool Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_IsStatic()
0x2695b  ldc.i4.0
0x2695c  ceq
0x2695e  ldstr    aResetscopecomp// "ResetScopeComplete should only be calle"...
0x26963  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x26968  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ProcessingTracer()
0x2696d  ldarg.1
0x2696e  callvirt instance bool Microsoft.ReportingServices.OnDemandReportRendering.DataShapeMember::get_IsColumn()
0x26973  ldc.i4.0
0x26974  ceq
0x26976  ldstr    aResetscopecomp_0// "ResetScopeComplete should only be calle"...
0x2697b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x26980  ldarg.0
0x26981  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<int32> Microsoft.ReportingServices.OnDemandReportRendering.DataShapeSegmentationManager::m_parentsWithScopeComplete
0x26986  ldarg.1
0x26987  call     int32 Microsoft.ReportingServices.OnDemandReportRendering.DataShapeSegmentationManager::GetParentID(class Microsoft.ReportingServices.OnDemandReportRendering.DataShapeMember member)
0x2698c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<int32>::Remove(var<u1>)
0x26991  pop
0x26992  ret
```
