# Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandlerSql11::ContainsDynamicChartMember

- ea: `0x2a50`
- end: `0x2a9b`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandlerSql11::ContainsDynamicChartMember`
- size: `75`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x2a20`
- `0x2a50`

## callees

- `0x2a50`

## pseudocode

```c

```

## disassembly

```asm
0x2a50  ldarg.1
0x2a51  brtrue.s loc_2A55
0x2a53  ldc.i4.0
0x2a54  ret
0x2a55  ldarg.1
0x2a56  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember>::GetEnumerator()
0x2a5b  stloc.0
0x2a5c  br.s     loc_2A83
0x2a5e  ldloc.0
0x2a5f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember>::get_Current()
0x2a64  stloc.1
0x2a65  ldloc.1
0x2a66  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_IsStatic()
0x2a6b  brtrue.s loc_2A71
0x2a6d  ldc.i4.1
0x2a6e  stloc.2
0x2a6f  leave.s  loc_2A99
0x2a71  ldarg.0
0x2a72  ldloc.1
0x2a73  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMemberCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember::get_Children()
0x2a78  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandlerSql11::ContainsDynamicChartMember(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMemberCollection chartMemberCollection)
0x2a7d  brfalse.s loc_2A83
0x2a7f  ldc.i4.1
0x2a80  stloc.2
0x2a81  leave.s  loc_2A99
0x2a83  ldloc.0
0x2a84  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2a89  brtrue.s loc_2A5E
0x2a8b  leave.s  loc_2A97
0x2a8d  ldloc.0
0x2a8e  brfalse.s loc_2A96
0x2a90  ldloc.0
0x2a91  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a96  endfinally
0x2a97  ldc.i4.0
0x2a98  ret
0x2a99  ldloc.2
0x2a9a  ret
```
