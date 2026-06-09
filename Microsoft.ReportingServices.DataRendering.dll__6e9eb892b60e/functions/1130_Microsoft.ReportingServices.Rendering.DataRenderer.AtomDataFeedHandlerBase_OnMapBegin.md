# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::OnMapBegin

- ea: `0x1130`
- end: `0x115e`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::OnMapBegin`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1000`
- `0x1040`
- `0x1130`
- `0x5610`

## pseudocode

```c

```

## disassembly

```asm
0x1130  ldarg.3
0x1131  ldind.u1
0x1132  stloc.0
0x1133  ldloc.0
0x1134  brtrue.s loc_113F
0x1136  ldarg.0
0x1137  ldarg.1
0x1138  ldarg.2
0x1139  ldarg.3
0x113a  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnMapBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Map map, bool outputMap, bool& walkMap)
0x113f  ldarg.3
0x1140  ldind.u1
0x1141  brfalse.s loc_115D
0x1143  ldloc.0
0x1144  brtrue.s loc_1154
0x1146  ldarg.3
0x1147  ldarg.0
0x1148  ldarg.1
0x1149  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_DefinitionPath()
0x114e  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::IsPartOfDefinitionPathSteps(string definitionPath)
0x1153  stind.i1
0x1154  ldarg.0
0x1155  ldarg.3
0x1156  ldind.u1
0x1157  ldarg.2
0x1158  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::ValidateCurrentRow(bool walk, bool output)
0x115d  ret
```
