# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTablixCorner

- ea: `0x83d0`
- end: `0x8438`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTablixCorner`
- size: `104`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x82d0`
- `0x83b0`

## callees

- `0x8130`
- `0x83d0`

## pseudocode

```c

```

## disassembly

```asm
0x83d0  ldc.i4.0
0x83d1  stloc.0
0x83d2  ldc.i4.0
0x83d3  stloc.1
0x83d4  br.s     loc_8428
0x83d6  ldarg.1
0x83d7  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCornerRowCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCorner::get_RowCollection()
0x83dc  ldloc.1
0x83dd  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCornerRow>::get_Item(!!T0)
0x83e2  stloc.2
0x83e3  ldloc.2
0x83e4  brfalse.s loc_8424
0x83e6  ldc.i4.0
0x83e7  stloc.3
0x83e8  br.s     loc_841B
0x83ea  ldloc.2
0x83eb  ldloc.3
0x83ec  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCornerCell>::get_Item(!!T0)
0x83f1  stloc.s  4
0x83f3  ldloc.s  4
0x83f5  brfalse.s loc_8417
0x83f7  ldloc.s  4
0x83f9  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CellContents [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCornerCell::get_CellContents()
0x83fe  brfalse.s loc_8417
0x8400  ldloc.0
0x8401  ldarg.0
0x8402  ldloc.s  4
0x8404  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CellContents [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCornerCell::get_CellContents()
0x8409  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CellContents::get_ReportItem()
0x840e  ldarg.2
0x840f  ldarg.3
0x8410  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkReportItem(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem ri, bool attributesOnly, bool firstInstance)
0x8415  or
0x8416  stloc.0
0x8417  ldloc.3
0x8418  ldc.i4.1
0x8419  add
0x841a  stloc.3
0x841b  ldloc.3
0x841c  ldloc.2
0x841d  callvirt instance int32 class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCornerCell>::get_Count()
0x8422  blt.s    loc_83EA
0x8424  ldloc.1
0x8425  ldc.i4.1
0x8426  add
0x8427  stloc.1
0x8428  ldloc.1
0x8429  ldarg.1
0x842a  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCornerRowCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCorner::get_RowCollection()
0x842f  callvirt instance int32 class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCornerRow>::get_Count()
0x8434  blt.s    loc_83D6
0x8436  ldloc.0
0x8437  ret
```
