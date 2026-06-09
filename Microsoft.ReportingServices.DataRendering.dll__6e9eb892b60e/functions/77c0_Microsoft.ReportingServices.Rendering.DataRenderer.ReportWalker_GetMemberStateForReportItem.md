# Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::GetMemberStateForReportItem

- ea: `0x77c0`
- end: `0x780e`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::GetMemberStateForReportItem`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x7390`

## callees

- `0x6400`
- `0x6530`
- `0x65b0`
- `0x6b20`
- `0x7610`
- `0x77c0`

## pseudocode

```c

```

## disassembly

```asm
0x77c0  ldarg.2
0x77c1  ldarg.1
0x77c2  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_ID()
0x77c7  ldloca.s 0
0x77c9  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::GetDynamicItemID(string stringID, [out] int32& id)
0x77ce  ldnull
0x77cf  stloc.1
0x77d0  brfalse.s loc_77ED
0x77d2  ldarg.2
0x77d3  ldloc.0
0x77d4  callvirt instance class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::FindChild(int32 childID)
0x77d9  stloc.1
0x77da  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0x77df  ldloc.1
0x77e0  ldnull
0x77e1  cgt.un
0x77e3  ldstr    aReportItemStat// "Report Item State not found in the pare"...
0x77e8  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x77ed  ldloc.1
0x77ee  brtrue.s loc_77F9
0x77f0  ldarg.0
0x77f1  ldarg.1
0x77f2  ldarg.2
0x77f3  call     instance class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::AddDataRegionOrMapContainer(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem dataRegionOrMap, class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState parentMemberState)
0x77f8  stloc.1
0x77f9  ldloc.1
0x77fa  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::IsActiveChild()
0x77ff  brtrue.s loc_780C
0x7801  ldloc.1
0x7802  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_IsDynamic()
0x7807  brfalse.s loc_780C
0x7809  ldarg.3
0x780a  ldc.i4.0
0x780b  stind.i1
0x780c  ldloc.1
0x780d  ret
```
