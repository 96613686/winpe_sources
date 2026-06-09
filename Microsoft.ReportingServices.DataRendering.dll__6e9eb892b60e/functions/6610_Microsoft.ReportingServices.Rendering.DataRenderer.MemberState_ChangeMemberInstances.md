# Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::ChangeMemberInstances

- ea: `0x6610`
- end: `0x66bd`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::ChangeMemberInstances`
- size: `173`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6700`
- `0x69d0`
- `0x6a80`

## callees

- `0x6610`

## pseudocode

```c

```

## disassembly

```asm
0x6610  ldc.i4.0
0x6611  stloc.0
0x6612  ldarg.0
0x6613  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_tablixMember
0x6618  brfalse.s loc_664D
0x661a  ldarg.0
0x661b  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_tablixMember
0x6620  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_Instance()
0x6625  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixDynamicMemberInstance
0x662a  stloc.1
0x662b  ldloc.1
0x662c  brfalse  loc_66BB
0x6631  ldarg.1
0x6632  brfalse.s loc_663A
0x6634  ldloc.1
0x6635  callvirt instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixDynamicMemberInstance::ResetContext()
0x663a  ldloc.1
0x663b  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixDynamicMemberInstance::MoveNext()
0x6640  stloc.0
0x6641  ldarg.1
0x6642  brfalse.s loc_66BB
0x6644  ldarg.0
0x6645  ldloc.0
0x6646  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_hasRows
0x664b  br.s     loc_66BB
0x664d  ldarg.0
0x664e  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_chartMember
0x6653  brfalse.s loc_6685
0x6655  ldarg.0
0x6656  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_chartMember
0x665b  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMemberInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember::get_Instance()
0x6660  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDynamicMemberInstance
0x6665  stloc.2
0x6666  ldloc.2
0x6667  brfalse.s loc_66BB
0x6669  ldarg.1
0x666a  brfalse.s loc_6672
0x666c  ldloc.2
0x666d  callvirt instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDynamicMemberInstance::ResetContext()
0x6672  ldloc.2
0x6673  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDynamicMemberInstance::MoveNext()
0x6678  stloc.0
0x6679  ldarg.1
0x667a  brfalse.s loc_66BB
0x667c  ldarg.0
0x667d  ldloc.0
0x667e  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_hasRows
0x6683  br.s     loc_66BB
0x6685  ldarg.0
0x6686  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapMember Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_mapMember
0x668b  brfalse.s loc_66BB
0x668d  ldarg.0
0x668e  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapMember Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_mapMember
0x6693  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapMemberInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapMember::get_Instance()
0x6698  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapDynamicMemberInstance
0x669d  stloc.3
0x669e  ldloc.3
0x669f  brfalse.s loc_66BB
0x66a1  ldarg.1
0x66a2  brfalse.s loc_66AA
0x66a4  ldloc.3
0x66a5  callvirt instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapDynamicMemberInstance::ResetContext()
0x66aa  ldloc.3
0x66ab  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapDynamicMemberInstance::MoveNext()
0x66b0  stloc.0
0x66b1  ldarg.1
0x66b2  brfalse.s loc_66BB
0x66b4  ldarg.0
0x66b5  ldloc.0
0x66b6  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_hasRows
0x66bb  ldloc.0
0x66bc  ret
```
