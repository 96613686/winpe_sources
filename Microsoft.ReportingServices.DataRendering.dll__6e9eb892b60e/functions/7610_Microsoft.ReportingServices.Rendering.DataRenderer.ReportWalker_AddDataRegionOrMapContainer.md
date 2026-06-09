# Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::AddDataRegionOrMapContainer

- ea: `0x7610`
- end: `0x7671`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::AddDataRegionOrMapContainer`
- size: `97`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x7390`
- `0x77c0`

## callees

- `0x63c0`
- `0x64e0`
- `0x7610`
- `0x76c0`

## pseudocode

```c

```

## disassembly

```asm
0x7610  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0x7615  ldarg.1
0x7616  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix
0x761b  brtrue.s loc_7638
0x761d  ldarg.1
0x761e  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Chart
0x7623  brtrue.s loc_7638
0x7625  ldarg.1
0x7626  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Map
0x762b  brtrue.s loc_7638
0x762d  ldarg.1
0x762e  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReport
0x7633  ldnull
0x7634  cgt.un
0x7636  br.s     loc_7639
0x7638  ldc.i4.1
0x7639  ldstr    aAddingDataRegi// "Adding data region or map container mem"...
0x763e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x7643  ldarg.0
0x7644  ldarg.1
0x7645  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_ID()
0x764a  ldarg.2
0x764b  call     instance class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::AddContainer(string childID, class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState parentMemberState)
0x7650  stloc.0
0x7651  ldarg.1
0x7652  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReport
0x7657  brfalse.s loc_7665
0x7659  ldloc.0
0x765a  ldarg.1
0x765b  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReport
0x7660  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::set_SubReportMember(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReport value)
0x7665  ldarg.2
0x7666  brfalse.s loc_766F
0x7668  ldarg.2
0x7669  ldloc.0
0x766a  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::AddChild(class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState MemberState)
0x766f  ldloc.0
0x7670  ret
```
