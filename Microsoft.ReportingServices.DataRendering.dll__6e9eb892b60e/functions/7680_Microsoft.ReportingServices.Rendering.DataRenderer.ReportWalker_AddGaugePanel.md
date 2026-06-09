# Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::AddGaugePanel

- ea: `0x7680`
- end: `0x76b8`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::AddGaugePanel`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x7390`

## callees

- `0x63d0`
- `0x63e0`
- `0x64e0`
- `0x6b30`
- `0x6b50`
- `0x7680`

## pseudocode

```c

```

## disassembly

```asm
0x7680  ldarg.2
0x7681  dup
0x7682  callvirt instance int32 Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_NextID()
0x7687  stloc.2
0x7688  ldloc.2
0x7689  ldc.i4.1
0x768a  add
0x768b  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::set_NextID(int32 value)
0x7690  ldloc.2
0x7691  stloc.0
0x7692  ldloc.0
0x7693  ldarg.1
0x7694  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_ID()
0x7699  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.GaugePanelState::.ctor(int32 id, string gaugePanelPath)
0x769e  stloc.1
0x769f  ldarg.2
0x76a0  brfalse.s loc_76A9
0x76a2  ldarg.2
0x76a3  ldloc.1
0x76a4  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::AddChild(class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState MemberState)
0x76a9  ldarg.2
0x76aa  ldarg.1
0x76ab  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_ID()
0x76b0  ldloc.0
0x76b1  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::AddToMemoryMapper(string stringId, int32 id)
0x76b6  ldloc.1
0x76b7  ret
```
