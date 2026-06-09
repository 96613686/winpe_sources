# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartMemberCollection

- ea: `0x8a50`
- end: `0x8a7e`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartMemberCollection`
- size: `46`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x89e0`
- `0x8a80`

## callees

- `0x8a50`
- `0x8a80`

## pseudocode

```c

```

## disassembly

```asm
0x8a50  ldarg.1
0x8a51  brtrue.s loc_8A54
0x8a53  ret
0x8a54  ldc.i4.0
0x8a55  stloc.0
0x8a56  ldc.i4.0
0x8a57  stloc.1
0x8a58  br.s     loc_8A74
0x8a5a  ldarg.1
0x8a5b  ldloc.1
0x8a5c  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember>::get_Item(!!T0)
0x8a61  stloc.2
0x8a62  ldloc.2
0x8a63  brfalse.s loc_8A70
0x8a65  ldarg.0
0x8a66  ldloc.2
0x8a67  ldarg.2
0x8a68  ldloca.s 0
0x8a6a  ldarg.3
0x8a6b  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartMember(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember chartMember, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Chart chart, int32& noNameMemberIndex, bool firstInstance)
0x8a70  ldloc.1
0x8a71  ldc.i4.1
0x8a72  add
0x8a73  stloc.1
0x8a74  ldloc.1
0x8a75  ldarg.1
0x8a76  callvirt instance int32 class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember>::get_Count()
0x8a7b  blt.s    loc_8A5A
0x8a7d  ret
```
