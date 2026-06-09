# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::OnTablixBegin

- ea: `0x1060`
- end: `0x108e`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::OnTablixBegin`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1000`
- `0x1040`
- `0x1060`
- `0x54b0`

## pseudocode

```c

```

## disassembly

```asm
0x1060  ldarg.2
0x1061  ldind.u1
0x1062  stloc.0
0x1063  ldloc.0
0x1064  brtrue.s loc_106F
0x1066  ldarg.0
0x1067  ldarg.1
0x1068  ldarg.2
0x1069  ldarg.3
0x106a  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnTablixBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix tablix, bool& walkTablix, bool outputTablix)
0x106f  ldarg.2
0x1070  ldind.u1
0x1071  brfalse.s loc_108D
0x1073  ldloc.0
0x1074  brtrue.s loc_1084
0x1076  ldarg.2
0x1077  ldarg.0
0x1078  ldarg.1
0x1079  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_DefinitionPath()
0x107e  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::IsPartOfDefinitionPathSteps(string definitionPath)
0x1083  stind.i1
0x1084  ldarg.0
0x1085  ldarg.2
0x1086  ldind.u1
0x1087  ldarg.3
0x1088  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::ValidateCurrentRow(bool walk, bool output)
0x108d  ret
```
