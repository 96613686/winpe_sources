# Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::TouchSubReportMember

- ea: `0x66c0`
- end: `0x66f1`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::TouchSubReportMember`
- size: `49`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6700`
- `0x69d0`
- `0x6a80`

## callees

- `0x66c0`

## pseudocode

```c

```

## disassembly

```asm
0x66c0  ldarg.0
0x66c1  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReport Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_sr
0x66c6  brfalse.s loc_66F0
0x66c8  ldarg.0
0x66c9  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReport Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_sr
0x66ce  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItemInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_Instance()
0x66d3  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReportInstance
0x66d8  stloc.0
0x66d9  ldloc.0
0x66da  brfalse.s loc_66F0
0x66dc  ldloc.0
0x66dd  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReportInstance::get_ProcessedWithError()
0x66e2  brfalse.s loc_66F0
0x66e4  ldloc.0
0x66e5  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReportInstance::get_ErrorMessage()
0x66ea  newobj   instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportRenderingException::.ctor(string)
0x66ef  throw
0x66f0  ret
```
