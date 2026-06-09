# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkReportItemCollection

- ea: `0x80e0`
- end: `0x8109`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkReportItemCollection`
- size: `41`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x80a0`
- `0x80c0`

## callees

- `0x80e0`
- `0x8130`

## pseudocode

```c

```

## disassembly

```asm
0x80e0  ldc.i4.0
0x80e1  stloc.0
0x80e2  ldarg.1
0x80e3  callvirt instance int32 class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem>::get_Count()
0x80e8  stloc.1
0x80e9  ldc.i4.0
0x80ea  stloc.2
0x80eb  br.s     loc_8103
0x80ed  ldloc.0
0x80ee  ldarg.0
0x80ef  ldarg.1
0x80f0  ldloc.2
0x80f1  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem>::get_Item(!!T0)
0x80f6  ldarg.2
0x80f7  ldarg.3
0x80f8  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkReportItem(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem ri, bool attributesOnly, bool firstInstance)
0x80fd  or
0x80fe  stloc.0
0x80ff  ldloc.2
0x8100  ldc.i4.1
0x8101  add
0x8102  stloc.2
0x8103  ldloc.2
0x8104  ldloc.1
0x8105  blt.s    loc_80ED
0x8107  ldloc.0
0x8108  ret
```
