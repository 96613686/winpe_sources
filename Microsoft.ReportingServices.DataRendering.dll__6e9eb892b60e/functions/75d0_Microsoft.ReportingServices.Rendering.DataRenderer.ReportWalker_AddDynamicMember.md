# Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::AddDynamicMember

- ea: `0x75d0`
- end: `0x760e`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::AddDynamicMember`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x76f0`

## callees

- `0x62f0`
- `0x63d0`
- `0x63e0`
- `0x64e0`
- `0x6b30`
- `0x75d0`

## pseudocode

```c

```

## disassembly

```asm
0x75d0  ldarg.2
0x75d1  dup
0x75d2  callvirt instance int32 Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_NextID()
0x75d7  stloc.2
0x75d8  ldloc.2
0x75d9  ldc.i4.1
0x75da  add
0x75db  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::set_NextID(int32 value)
0x75e0  ldloc.2
0x75e1  stloc.0
0x75e2  ldarg.1
0x75e3  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_IsStatic()
0x75e8  brtrue.s loc_75ED
0x75ea  ldarg.1
0x75eb  br.s     loc_75EE
0x75ed  ldnull
0x75ee  ldloc.0
0x75ef  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::.ctor(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember member, int32 id)
0x75f4  stloc.1
0x75f5  ldarg.2
0x75f6  brfalse.s loc_75FF
0x75f8  ldarg.2
0x75f9  ldloc.1
0x75fa  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::AddChild(class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState MemberState)
0x75ff  ldarg.2
0x7600  ldarg.1
0x7601  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_ID()
0x7606  ldloc.0
0x7607  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::AddToMemoryMapper(string stringId, int32 id)
0x760c  ldloc.1
0x760d  ret
```
