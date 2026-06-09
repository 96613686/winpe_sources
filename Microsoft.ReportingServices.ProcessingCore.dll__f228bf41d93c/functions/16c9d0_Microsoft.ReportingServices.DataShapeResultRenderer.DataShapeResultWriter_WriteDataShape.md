# Microsoft.ReportingServices.DataShapeResultRenderer.DataShapeResultWriter::WriteDataShape

- ea: `0x16c9d0`
- end: `0x16ca7f`
- name: `Microsoft.ReportingServices.DataShapeResultRenderer.DataShapeResultWriter::WriteDataShape`
- size: `175`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `service_task, broker_com_uri`

## callers

- `0x16ca80`
- `0x16cb00`

## callees

- `0x26bb0`
- `0x26bc0`
- `0x26be0`
- `0x26c00`
- `0x26c30`
- `0x26c60`
- `0x26ce0`
- `0x26d00`
- `0x26d20`
- `0x26d60`
- `0x26d70`
- `0xc2d00`
- `0x16c1d0`
- `0x16c1e0`
- `0x16c270`
- `0x16c2d0`
- `0x16c730`
- `0x16c750`
- `0x16c7f0`
- `0x16c840`
- `0x16c900`
- `0x16c9d0`
- `0x16ca80`
- `0x16cad0`

## string_xrefs

- `0x16ca42`: `IsComplete`

## pseudocode

```c

```

## disassembly

```asm
0x16c9d0  ldarg.0
0x16c9d1  callvirt instance void Microsoft.ReportingServices.DataShapeResultRenderer.DataShapeResultWriter::WriteObjectStart()
0x16c9d6  ldarg.0
0x16c9d7  ldarg.1
0x16c9d8  callvirt instance string Microsoft.ReportingServices.OnDemandReportRendering.DataShape::get_ClientID()
0x16c9dd  call     instance void Microsoft.ReportingServices.DataShapeResultRenderer.DataShapeResultWriter::WriteIdProperty(string id)
0x16c9e2  ldarg.0
0x16c9e3  ldarg.1
0x16c9e4  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.DataShapeMessageCollection Microsoft.ReportingServices.OnDemandReportRendering.DataShape::get_Messages()
0x16c9e9  call     instance void Microsoft.ReportingServices.DataShapeResultRenderer.DataShapeResultWriter::WriteDataShapeMessageCollection(class Microsoft.ReportingServices.OnDemandReportRendering.DataShapeMessageCollection messageCollection)
0x16c9ee  ldarg.0
0x16c9ef  ldarg.1
0x16c9f0  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.DataShapeCalculationCollection Microsoft.ReportingServices.OnDemandReportRendering.DataShape::get_Calculations()
0x16c9f5  call     instance void Microsoft.ReportingServices.DataShapeResultRenderer.DataShapeResultWriter::WriteCalculationCollection(class Microsoft.ReportingServices.OnDemandReportRendering.DataShapeCalculationCollection calculationCollection)
0x16c9fa  ldarg.0
0x16c9fb  ldarg.1
0x16c9fc  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.DataShapeCollection Microsoft.ReportingServices.OnDemandReportRendering.DataShape::get_DataShapes()
0x16ca01  call     instance void Microsoft.ReportingServices.DataShapeResultRenderer.DataShapeResultWriter::WriteDataShapeCollection(class Microsoft.ReportingServices.OnDemandReportRendering.DataShapeCollection dataShapes)
0x16ca06  ldarg.0
0x16ca07  ldarg.1
0x16ca08  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.DataShapeMemberHierarchy Microsoft.ReportingServices.OnDemandReportRendering.DataShape::get_ColumnHierarchy()
0x16ca0d  call     instance void Microsoft.ReportingServices.DataShapeResultRenderer.DataShapeResultWriter::WriteSecondaryHierachy(class Microsoft.ReportingServices.OnDemandReportRendering.DataShapeMemberHierarchy memberHierarchy)
0x16ca12  ldarg.1
0x16ca13  callvirt instance void Microsoft.ReportingServices.OnDemandReportRendering.DataShape::PrepareRowHierarchy()
0x16ca18  ldarg.0
0x16ca19  ldstr    aPrimaryhierarc// "PrimaryHierarchy"
0x16ca1e  ldarg.1
0x16ca1f  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.DataShapeMemberHierarchy Microsoft.ReportingServices.OnDemandReportRendering.DataShape::get_RowHierarchy()
0x16ca24  ldarg.1
0x16ca25  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.DataShapeMemberHierarchy Microsoft.ReportingServices.OnDemandReportRendering.DataShape::get_ColumnHierarchy()
0x16ca2a  ldarg.1
0x16ca2b  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.DataShapeRowCollection Microsoft.ReportingServices.OnDemandReportRendering.DataShape::get_DataRows()
0x16ca30  call     instance void Microsoft.ReportingServices.DataShapeResultRenderer.DataShapeResultWriter::WriteMemberHierarchy(string collectionName, class Microsoft.ReportingServices.OnDemandReportRendering.DataShapeMemberHierarchy primaryHierachy, class Microsoft.ReportingServices.OnDemandReportRendering.DataShapeMemberHierarchy secondaryHierachy, class Microsoft.ReportingServices.OnDemandReportRendering.DataShapeRowCollection rowCollection)
0x16ca35  ldarg.0
0x16ca36  ldarg.1
0x16ca37  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.OnDemandReportRendering.DataShapeLimit> Microsoft.ReportingServices.OnDemandReportRendering.DataShape::get_Limits()
0x16ca3c  call     instance void Microsoft.ReportingServices.DataShapeResultRenderer.DataShapeResultWriter::WriteDataLimitsExceeded(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.OnDemandReportRendering.DataShapeLimit> limits)
0x16ca41  ldarg.0
0x16ca42  ldstr    aIscomplete// "IsComplete"
0x16ca47  ldarg.1
0x16ca48  callvirt instance bool Microsoft.ReportingServices.OnDemandReportRendering.DataShape::get_IsComplete()
0x16ca4d  call     instance void Microsoft.ReportingServices.DataShapeResultRenderer.DataShapeResultWriter::WriteProperty(string name, bool value)
0x16ca52  ldarg.1
0x16ca53  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.DataShape Microsoft.ReportingServices.OnDemandReportRendering.DataShape::get_RifDataShapeDefinition()
0x16ca58  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.RestartDefinition> Microsoft.ReportingServices.ReportIntermediateFormat.DataShape::get_RestartDefinitions()
0x16ca5d  brfalse.s loc_16CA78
0x16ca5f  ldarg.1
0x16ca60  callvirt instance bool Microsoft.ReportingServices.OnDemandReportRendering.DataShape::get_IsComplete()
0x16ca65  brtrue.s loc_16CA78
0x16ca67  ldarg.0
0x16ca68  ldarg.1
0x16ca69  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.DataShape Microsoft.ReportingServices.OnDemandReportRendering.DataShape::get_RifDataShapeDefinition()
0x16ca6e  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.RestartDefinition> Microsoft.ReportingServices.ReportIntermediateFormat.DataShape::get_RestartDefinitions()
0x16ca73  call     instance void Microsoft.ReportingServices.DataShapeResultRenderer.DataShapeResultWriter::WriteRestartTokens(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.RestartDefinition> restartDefinitions)
0x16ca78  ldarg.0
0x16ca79  callvirt instance void Microsoft.ReportingServices.DataShapeResultRenderer.DataShapeResultWriter::WriteObjectEnd()
0x16ca7e  ret
```
