# Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkDataRegionOrMap

- ea: `0x6d60`
- end: `0x6d85`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkDataRegionOrMap`
- size: `37`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1cf0`
- `0x1d70`
- `0x1e90`
- `0x2200`
- `0x4a00`
- `0x7ad0`

## callees

- `0x6d60`
- `0x6d90`
- `0x6e80`

## pseudocode

```c

```

## disassembly

```asm
0x6d60  ldarg.0
0x6d61  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_instanceWalk
0x6d66  brfalse.s loc_6D6F
0x6d68  ldarg.0
0x6d69  ldc.i4.1
0x6d6a  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_firstInstancePass
0x6d6f  ldarg.0
0x6d70  ldarg.1
0x6d71  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::InitializeDataRegionOrMap(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem reportItem)
0x6d76  stloc.0
0x6d77  br.s     loc_6D81
0x6d79  ldarg.0
0x6d7a  ldarg.1
0x6d7b  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkNextDataRegionOrMapRow(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem reportItem)
0x6d80  stloc.0
0x6d81  ldloc.0
0x6d82  brtrue.s loc_6D79
0x6d84  ret
```
