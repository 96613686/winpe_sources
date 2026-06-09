# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTablixMemberCollection

- ea: `0x8460`
- end: `0x84b4`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTablixMemberCollection`
- size: `84`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x82d0`
- `0x8440`
- `0x84c0`
- `0x8670`

## callees

- `0x8460`
- `0x84c0`
- `0x8670`

## pseudocode

```c

```

## disassembly

```asm
0x8460  ldc.i4.0
0x8461  stloc.0
0x8462  ldc.i4.0
0x8463  stloc.1
0x8464  ldc.i4.0
0x8465  stloc.2
0x8466  br.s     loc_84A9
0x8468  ldarg.1
0x8469  ldloc.2
0x846a  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember>::get_Item(!!T0)
0x846f  stloc.3
0x8470  ldloc.3
0x8471  brfalse.s loc_84A5
0x8473  ldloc.3
0x8474  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_IsTotal()
0x8479  brtrue.s loc_84A5
0x847b  ldloc.3
0x847c  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_IsStatic()
0x8481  brfalse.s loc_8495
0x8483  ldloc.0
0x8484  ldarg.0
0x8485  ldloc.3
0x8486  ldarg.2
0x8487  ldarg.3
0x8488  ldloca.s 1
0x848a  ldarg.s  4
0x848c  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkStaticTablixMember(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember aTablixMember, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix aTablix, bool aAttributesOnly, int32& aNonameMemberIndex, bool firstInstance)
0x8491  or
0x8492  stloc.0
0x8493  br.s     loc_84A5
0x8495  ldloc.0
0x8496  ldarg.0
0x8497  ldloc.3
0x8498  ldarg.2
0x8499  ldarg.3
0x849a  ldloca.s 1
0x849c  ldarg.s  4
0x849e  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkDynamicTablixMember(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember aTablixMember, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix aTablix, bool aAttributesOnly, int32& aNonameMemberIndex, bool aFirstInstance)
0x84a3  or
0x84a4  stloc.0
0x84a5  ldloc.2
0x84a6  ldc.i4.1
0x84a7  add
0x84a8  stloc.2
0x84a9  ldloc.2
0x84aa  ldarg.1
0x84ab  callvirt instance int32 class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember>::get_Count()
0x84b0  blt.s    loc_8468
0x84b2  ldloc.0
0x84b3  ret
```
