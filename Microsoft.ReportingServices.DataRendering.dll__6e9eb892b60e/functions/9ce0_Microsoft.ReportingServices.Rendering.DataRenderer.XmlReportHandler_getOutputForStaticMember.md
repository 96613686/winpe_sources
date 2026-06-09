# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::getOutputForStaticMember

- ea: `0x9ce0`
- end: `0x9dd8`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::getOutputForStaticMember`
- size: `248`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x9ce0`

## callees

- `0x9ce0`
- `0x9de0`

## pseudocode

```c

```

## disassembly

```asm
0x9ce0  ldc.i4.0
0x9ce1  stloc.0
0x9ce2  ldarg.1
0x9ce3  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_Children()
0x9ce8  brfalse.s loc_9D4C
0x9cea  ldc.i4.0
0x9ceb  stloc.1
0x9cec  br.s     loc_9D39
0x9cee  ldarg.1
0x9cef  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_Children()
0x9cf4  ldloc.1
0x9cf5  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember>::get_Item(!!T0)
0x9cfa  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_IsStatic()
0x9cff  brfalse.s loc_9D19
0x9d01  ldloc.0
0x9d02  ldarg.0
0x9d03  ldarg.1
0x9d04  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_Children()
0x9d09  ldloc.1
0x9d0a  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember>::get_Item(!!T0)
0x9d0f  ldarg.2
0x9d10  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::getOutputForStaticMember(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember aTablixMember, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix aTablix)
0x9d15  or
0x9d16  stloc.0
0x9d17  br.s     loc_9D35
0x9d19  ldloc.0
0x9d1a  ldarg.1
0x9d1b  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_Children()
0x9d20  ldloc.1
0x9d21  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember>::get_Item(!!T0)
0x9d26  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_Group()
0x9d2b  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group::get_DataElementOutput()
0x9d30  ldc.i4.0
0x9d31  ceq
0x9d33  or
0x9d34  stloc.0
0x9d35  ldloc.1
0x9d36  ldc.i4.1
0x9d37  add
0x9d38  stloc.1
0x9d39  ldloc.1
0x9d3a  ldarg.1
0x9d3b  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_Children()
0x9d40  callvirt instance int32 class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember>::get_Count()
0x9d45  blt.s    loc_9CEE
0x9d47  br       loc_9DD6
0x9d4c  ldarg.1
0x9d4d  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_IsColumn()
0x9d52  brfalse.s loc_9D96
0x9d54  ldc.i4.0
0x9d55  stloc.2
0x9d56  br.s     loc_9D81
0x9d58  ldloc.0
0x9d59  ldarg.0
0x9d5a  ldarg.2
0x9d5b  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixBody [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix::get_Body()
0x9d60  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixRowCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixBody::get_RowCollection()
0x9d65  ldloc.2
0x9d66  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixRow>::get_Item(!!T0)
0x9d6b  ldarg.1
0x9d6c  callvirt instance int32 [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_MemberCellIndex()
0x9d71  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCell>::get_Item(!!T0)
0x9d76  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::getOutputForTablixCell(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCell aTablixCell)
0x9d7b  or
0x9d7c  stloc.0
0x9d7d  ldloc.2
0x9d7e  ldc.i4.1
0x9d7f  add
0x9d80  stloc.2
0x9d81  ldloc.2
0x9d82  ldarg.2
0x9d83  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixBody [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix::get_Body()
0x9d88  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixRowCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixBody::get_RowCollection()
0x9d8d  callvirt instance int32 class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixRow>::get_Count()
0x9d92  blt.s    loc_9D58
0x9d94  br.s     loc_9DD6
0x9d96  ldc.i4.0
0x9d97  stloc.3
0x9d98  br.s     loc_9DC3
0x9d9a  ldloc.0
0x9d9b  ldarg.0
0x9d9c  ldarg.2
0x9d9d  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixBody [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix::get_Body()
0x9da2  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixRowCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixBody::get_RowCollection()
0x9da7  ldarg.1
0x9da8  callvirt instance int32 [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_MemberCellIndex()
0x9dad  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixRow>::get_Item(!!T0)
0x9db2  ldloc.3
0x9db3  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCell>::get_Item(!!T0)
0x9db8  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::getOutputForTablixCell(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCell aTablixCell)
0x9dbd  or
0x9dbe  stloc.0
0x9dbf  ldloc.3
0x9dc0  ldc.i4.1
0x9dc1  add
0x9dc2  stloc.3
0x9dc3  ldloc.3
0x9dc4  ldarg.2
0x9dc5  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixBody [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix::get_Body()
0x9dca  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixColumnCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixBody::get_ColumnCollection()
0x9dcf  callvirt instance int32 class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixColumn>::get_Count()
0x9dd4  blt.s    loc_9D9A
0x9dd6  ldloc.0
0x9dd7  ret
```
