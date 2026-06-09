# Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkReportItem

- ea: `0x7390`
- end: `0x754f`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkReportItem`
- size: `447`
- prototype: ``
- caller_count: `5`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x6e80`
- `0x7550`
- `0xc660`
- `0xc730`
- `0xc900`

## callees

- `0x63f0`
- `0x6400`
- `0x6530`
- `0x65b0`
- `0x6a80`
- `0x6b20`
- `0x7170`
- `0x7260`
- `0x7320`
- `0x7360`
- `0x7390`
- `0x7610`
- `0x7680`
- `0x77c0`
- `0xb9d0`
- `0xba00`
- `0xbe50`
- `0xbec0`
- `0xc4e0`
- `0xc510`

## pseudocode

```c

```

## disassembly

```asm
0x7390  ldarg.1
0x7391  brtrue.s loc_7394
0x7393  ret
0x7394  ldarg.1
0x7395  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TextBox
0x739a  brfalse.s loc_73AA
0x739c  ldarg.0
0x739d  ldarg.1
0x739e  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TextBox
0x73a3  ldarg.3
0x73a4  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkTextBox(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TextBox textBox, bool outputDynamic)
0x73a9  ret
0x73aa  ldarg.1
0x73ab  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix
0x73b0  brfalse.s loc_73D9
0x73b2  ldnull
0x73b3  stloc.0
0x73b4  ldarg.3
0x73b5  stloc.1
0x73b6  ldarg.2
0x73b7  brfalse.s loc_73C4
0x73b9  ldarg.0
0x73ba  ldarg.1
0x73bb  ldarg.2
0x73bc  ldloca.s 1
0x73be  call     instance class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::GetMemberStateForReportItem(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem reportItem, class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState parentMemberState, bool& outputReportItem)
0x73c3  stloc.0
0x73c4  ldarg.1
0x73c5  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix
0x73ca  ldarg.0
0x73cb  newobj   instance void TablixWalker::.ctor(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix tablix, class Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker reportWalker)
0x73d0  ldloc.0
0x73d1  ldloc.1
0x73d2  ldarg.2
0x73d3  callvirt instance void TablixWalker::WalkTablix(class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState tablixState, bool outputMembers, class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState parentMemberState)
0x73d8  ret
0x73d9  ldarg.1
0x73da  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Chart
0x73df  brfalse.s loc_7407
0x73e1  ldnull
0x73e2  stloc.2
0x73e3  ldarg.3
0x73e4  stloc.3
0x73e5  ldarg.2
0x73e6  brfalse.s loc_73F3
0x73e8  ldarg.0
0x73e9  ldarg.1
0x73ea  ldarg.2
0x73eb  ldloca.s 3
0x73ed  call     instance class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::GetMemberStateForReportItem(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem reportItem, class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState parentMemberState, bool& outputReportItem)
0x73f2  stloc.2
0x73f3  ldarg.1
0x73f4  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Chart
0x73f9  ldarg.0
0x73fa  newobj   instance void ChartWalker::.ctor(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Chart chart, class Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker reportWalker)
0x73ff  ldloc.2
0x7400  ldloc.3
0x7401  callvirt instance void ChartWalker::WalkChart(class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState chartState, bool outputMembers)
0x7406  ret
0x7407  ldarg.1
0x7408  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanel
0x740d  brfalse.s loc_748E
0x740f  ldnull
0x7410  stloc.s  4
0x7412  ldarg.3
0x7413  stloc.s  5
0x7415  ldarg.2
0x7416  brfalse.s loc_747A
0x7418  ldarg.2
0x7419  ldarg.1
0x741a  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_ID()
0x741f  ldloca.s 6
0x7421  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::GetDynamicItemID(string stringID, [out] int32& id)
0x7426  brfalse.s loc_744B
0x7428  ldarg.2
0x7429  ldloc.s  6
0x742b  callvirt instance class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::FindChild(int32 childID)
0x7430  isinst   Microsoft.ReportingServices.Rendering.DataRenderer.GaugePanelState
0x7435  stloc.s  4
0x7437  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0x743c  ldloc.s  4
0x743e  ldnull
0x743f  cgt.un
0x7441  ldstr    aGaugepanelNotF// "GaugePanel not found in the parent dyna"...
0x7446  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x744b  ldloc.s  4
0x744d  brtrue.s loc_746E
0x744f  ldarg.0
0x7450  ldarg.1
0x7451  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanel
0x7456  ldarg.2
0x7457  call     instance class Microsoft.ReportingServices.Rendering.DataRenderer.GaugePanelState Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::AddGaugePanel(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanel gaugePanel, class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState parentMemberState)
0x745c  stloc.s  4
0x745e  ldarg.0
0x745f  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_instanceWalk
0x7464  brfalse.s loc_746E
0x7466  ldloc.s  4
0x7468  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::ResetDynamicMembers()
0x746d  pop
0x746e  ldloc.s  4
0x7470  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::IsActiveChild()
0x7475  brtrue.s loc_747A
0x7477  ldc.i4.0
0x7478  stloc.s  5
0x747a  ldarg.0
0x747b  newobj   instance void GaugePanelWalker::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker reportWalker)
0x7480  ldarg.1
0x7481  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanel
0x7486  ldloc.s  5
0x7488  callvirt instance void GaugePanelWalker::WalkGaugePanel(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanel gaugePanel, bool outputGaugePanelData)
0x748d  ret
0x748e  ldarg.1
0x748f  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Map
0x7494  brfalse.s loc_74BC
0x7496  ldnull
0x7497  stloc.s  7
0x7499  ldarg.3
0x749a  stloc.s  8
0x749c  ldarg.2
0x749d  brfalse.s loc_74AB
0x749f  ldarg.0
0x74a0  ldarg.1
0x74a1  ldarg.2
0x74a2  ldloca.s 8
0x74a4  call     instance class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::GetMemberStateForReportItem(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem reportItem, class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState parentMemberState, bool& outputReportItem)
0x74a9  stloc.s  7
0x74ab  ldarg.0
0x74ac  ldarg.1
0x74ad  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Map
0x74b2  ldloc.s  7
0x74b4  ldloc.s  8
0x74b6  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkMap(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Map map, class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState mapState, bool outputMapData)
0x74bb  ret
0x74bc  ldarg.1
0x74bd  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Rectangle
0x74c2  brfalse.s loc_74D3
0x74c4  ldarg.0
0x74c5  ldarg.1
0x74c6  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Rectangle
0x74cb  ldarg.2
0x74cc  ldarg.3
0x74cd  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkRectangle(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Rectangle rectangle, class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState parentMemberState, bool outputMembers)
0x74d2  ret
0x74d3  ldarg.1
0x74d4  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReport
0x74d9  brfalse.s loc_754E
0x74db  ldnull
0x74dc  stloc.s  9
0x74de  ldarg.3
0x74df  stloc.s  0xA
0x74e1  ldarg.2
0x74e2  brfalse.s loc_753E
0x74e4  ldarg.2
0x74e5  ldarg.1
0x74e6  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_ID()
0x74eb  ldloca.s 0xB
0x74ed  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::GetDynamicItemID(string stringID, [out] int32& id)
0x74f2  brfalse.s loc_7512
0x74f4  ldarg.2
0x74f5  ldloc.s  0xB
0x74f7  callvirt instance class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::FindChild(int32 childID)
0x74fc  stloc.s  9
0x74fe  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0x7503  ldloc.s  9
0x7505  ldnull
0x7506  cgt.un
0x7508  ldstr    aSubreportNotFo// "SubReport not found in the parent dynam"...
0x750d  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x7512  ldloc.s  9
0x7514  brtrue.s loc_7520
0x7516  ldarg.0
0x7517  ldarg.1
0x7518  ldarg.2
0x7519  call     instance class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::AddDataRegionOrMapContainer(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem dataRegionOrMap, class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState parentMemberState)
0x751e  stloc.s  9
0x7520  ldloc.s  9
0x7522  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_IsDynamic()
0x7527  brfalse.s loc_753E
0x7529  ldloc.s  9
0x752b  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::IsActiveChild()
0x7530  brfalse.s loc_753B
0x7532  ldloc.s  9
0x7534  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_HasRows()
0x7539  brtrue.s loc_753E
0x753b  ldc.i4.0
0x753c  stloc.s  0xA
0x753e  ldarg.0
0x753f  ldarg.1
0x7540  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReport
0x7545  ldloc.s  9
0x7547  ldloc.s  0xA
0x7549  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkSubReport(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReport subReport, class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState parentMemberState, bool outputMembers)
0x754e  ret
```
