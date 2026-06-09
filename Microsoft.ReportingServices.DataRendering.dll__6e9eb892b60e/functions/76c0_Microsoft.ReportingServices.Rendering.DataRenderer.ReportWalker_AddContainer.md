# Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::AddContainer

- ea: `0x76c0`
- end: `0x76eb`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::AddContainer`
- size: `43`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x6d90`
- `0x6f70`
- `0x7610`

## callees

- `0x62f0`
- `0x63d0`
- `0x63e0`
- `0x6b30`
- `0x76c0`

## pseudocode

```c

```

## disassembly

```asm
0x76c0  ldarg.2
0x76c1  brfalse.s loc_76D6
0x76c3  ldarg.2
0x76c4  dup
0x76c5  callvirt instance int32 Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_NextID()
0x76ca  stloc.1
0x76cb  ldloc.1
0x76cc  ldc.i4.1
0x76cd  add
0x76ce  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::set_NextID(int32 value)
0x76d3  ldloc.1
0x76d4  br.s     loc_76D7
0x76d6  ldc.i4.0
0x76d7  stloc.0
0x76d8  ldnull
0x76d9  ldloc.0
0x76da  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::.ctor(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember member, int32 id)
0x76df  ldarg.2
0x76e0  brfalse.s loc_76EA
0x76e2  ldarg.2
0x76e3  ldarg.1
0x76e4  ldloc.0
0x76e5  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::AddToMemoryMapper(string stringId, int32 id)
0x76ea  ret
```
