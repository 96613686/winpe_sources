# Microsoft.ReportingServices.OnDemandReportRendering.ActionInstance::Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable.Deserialize

- ea: `0x57460`
- end: `0x57646`
- name: `Microsoft.ReportingServices.OnDemandReportRendering.ActionInstance::Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable.Deserialize`
- size: `486`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x564a0`
- `0x56510`
- `0x56580`
- `0x566a0`
- `0x56960`
- `0x569b0`
- `0x56a40`
- `0x57460`
- `0x57850`
- `0x71eb0`
- `0x79310`
- `0x79320`
- `0x144fd0`
- `0x144fe0`
- `0x1450b0`
- `0x145140`
- `0x146c00`
- `0x14a240`

## string_xrefs

- `0x57528`: `(bookmarkLink == null)`
- `0x57573`: `(hyperlink == null)`

## pseudocode

```c

```

## disassembly

```asm
0x57460  ldarga.s 1
0x57462  ldsfld   class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration Microsoft.ReportingServices.OnDemandReportRendering.ActionInstance::m_Declaration
0x57467  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::RegisterDeclaration(class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration declaration)
0x5746c  br       loc_57639
0x57471  ldarga.s 1
0x57473  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::get_CurrentMember()
0x57478  callvirt instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberName Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo::get_MemberName()
0x5747d  stloc.0
0x5747e  ldloc.0
0x5747f  ldc.i4   0x8B
0x57484  beq.s    loc_574AE
0x57486  ldloc.0
0x57487  ldc.i4   0xB7
0x5748c  beq      loc_57537
0x57491  ldloc.0
0x57492  ldc.i4   0x172
0x57497  sub
0x57498  switch   loc_57582, loc_575DE, loc_574EC
0x574a9  br       loc_5762E
0x574ae  ldarga.s 1
0x574b0  call     instance string Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadString()
0x574b5  stloc.1
0x574b6  ldarg.0
0x574b7  ldfld    class Microsoft.ReportingServices.OnDemandReportRendering.Action Microsoft.ReportingServices.OnDemandReportRendering.ActionInstance::m_actionDef
0x574bc  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportStringProperty Microsoft.ReportingServices.OnDemandReportRendering.Action::get_Label()
0x574c1  callvirt instance bool Microsoft.ReportingServices.OnDemandReportRendering.ReportProperty::get_IsExpression()
0x574c6  brfalse.s loc_574D4
0x574c8  ldarg.0
0x574c9  ldloc.1
0x574ca  stfld    string Microsoft.ReportingServices.OnDemandReportRendering.ActionInstance::m_label
0x574cf  br       loc_57639
0x574d4  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x574d9  ldloc.1
0x574da  ldnull
0x574db  ceq
0x574dd  ldstr    aLabelNull// "(label == null)"
0x574e2  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x574e7  br       loc_57639
0x574ec  ldarga.s 1
0x574ee  call     instance string Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadString()
0x574f3  stloc.2
0x574f4  ldarg.0
0x574f5  ldfld    class Microsoft.ReportingServices.OnDemandReportRendering.Action Microsoft.ReportingServices.OnDemandReportRendering.ActionInstance::m_actionDef
0x574fa  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportStringProperty Microsoft.ReportingServices.OnDemandReportRendering.Action::get_BookmarkLink()
0x574ff  brfalse.s loc_5751F
0x57501  ldarg.0
0x57502  ldfld    class Microsoft.ReportingServices.OnDemandReportRendering.Action Microsoft.ReportingServices.OnDemandReportRendering.ActionInstance::m_actionDef
0x57507  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportStringProperty Microsoft.ReportingServices.OnDemandReportRendering.Action::get_BookmarkLink()
0x5750c  callvirt instance bool Microsoft.ReportingServices.OnDemandReportRendering.ReportProperty::get_IsExpression()
0x57511  brfalse.s loc_5751F
0x57513  ldarg.0
0x57514  ldloc.2
0x57515  stfld    string Microsoft.ReportingServices.OnDemandReportRendering.ActionInstance::m_bookmark
0x5751a  br       loc_57639
0x5751f  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x57524  ldloc.2
0x57525  ldnull
0x57526  ceq
0x57528  ldstr    aBookmarklinkNu// "(bookmarkLink == null)"
0x5752d  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x57532  br       loc_57639
0x57537  ldarga.s 1
0x57539  call     instance string Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadString()
0x5753e  stloc.3
0x5753f  ldarg.0
0x57540  ldfld    class Microsoft.ReportingServices.OnDemandReportRendering.Action Microsoft.ReportingServices.OnDemandReportRendering.ActionInstance::m_actionDef
0x57545  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportUrlProperty Microsoft.ReportingServices.OnDemandReportRendering.Action::get_Hyperlink()
0x5754a  brfalse.s loc_5756A
0x5754c  ldarg.0
0x5754d  ldfld    class Microsoft.ReportingServices.OnDemandReportRendering.Action Microsoft.ReportingServices.OnDemandReportRendering.ActionInstance::m_actionDef
0x57552  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportUrlProperty Microsoft.ReportingServices.OnDemandReportRendering.Action::get_Hyperlink()
0x57557  callvirt instance bool Microsoft.ReportingServices.OnDemandReportRendering.ReportProperty::get_IsExpression()
0x5755c  brfalse.s loc_5756A
0x5755e  ldarg.0
0x5755f  ldloc.3
0x57560  stfld    string Microsoft.ReportingServices.OnDemandReportRendering.ActionInstance::m_hyperlinkText
0x57565  br       loc_57639
0x5756a  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x5756f  ldloc.3
0x57570  ldnull
0x57571  ceq
0x57573  ldstr    aHyperlinkNull// "(hyperlink == null)"
0x57578  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x5757d  br       loc_57639
0x57582  ldarga.s 1
0x57584  call     instance string Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadString()
0x57589  stloc.s  4
0x5758b  ldarg.0
0x5758c  ldfld    class Microsoft.ReportingServices.OnDemandReportRendering.Action Microsoft.ReportingServices.OnDemandReportRendering.ActionInstance::m_actionDef
0x57591  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ActionDrillthrough Microsoft.ReportingServices.OnDemandReportRendering.Action::get_Drillthrough()
0x57596  brfalse.s loc_575C8
0x57598  ldarg.0
0x57599  ldfld    class Microsoft.ReportingServices.OnDemandReportRendering.Action Microsoft.ReportingServices.OnDemandReportRendering.ActionInstance::m_actionDef
0x5759e  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ActionDrillthrough Microsoft.ReportingServices.OnDemandReportRendering.Action::get_Drillthrough()
0x575a3  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportStringProperty Microsoft.ReportingServices.OnDemandReportRendering.ActionDrillthrough::get_ReportName()
0x575a8  callvirt instance bool Microsoft.ReportingServices.OnDemandReportRendering.ReportProperty::get_IsExpression()
0x575ad  brfalse.s loc_575C8
0x575af  ldarg.0
0x575b0  ldfld    class Microsoft.ReportingServices.OnDemandReportRendering.Action Microsoft.ReportingServices.OnDemandReportRendering.ActionInstance::m_actionDef
0x575b5  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ActionDrillthrough Microsoft.ReportingServices.OnDemandReportRendering.Action::get_Drillthrough()
0x575ba  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ActionDrillthroughInstance Microsoft.ReportingServices.OnDemandReportRendering.ActionDrillthrough::get_Instance()
0x575bf  ldloc.s  4
0x575c1  callvirt instance void Microsoft.ReportingServices.OnDemandReportRendering.ActionDrillthroughInstance::set_ReportName(string value)
0x575c6  br.s     loc_57639
0x575c8  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x575cd  ldloc.s  4
0x575cf  ldnull
0x575d0  ceq
0x575d2  ldstr    aReportnameNull// "(reportName == null)"
0x575d7  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x575dc  br.s     loc_57639
0x575de  ldnull
0x575df  stloc.s  5
0x575e1  ldarg.0
0x575e2  ldfld    class Microsoft.ReportingServices.OnDemandReportRendering.Action Microsoft.ReportingServices.OnDemandReportRendering.ActionInstance::m_actionDef
0x575e7  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ActionDrillthrough Microsoft.ReportingServices.OnDemandReportRendering.Action::get_Drillthrough()
0x575ec  brfalse.s loc_57600
0x575ee  ldarg.0
0x575ef  ldfld    class Microsoft.ReportingServices.OnDemandReportRendering.Action Microsoft.ReportingServices.OnDemandReportRendering.ActionInstance::m_actionDef
0x575f4  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ActionDrillthrough Microsoft.ReportingServices.OnDemandReportRendering.Action::get_Drillthrough()
0x575f9  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ParameterCollection Microsoft.ReportingServices.OnDemandReportRendering.ActionDrillthrough::get_Parameters()
0x575fe  stloc.s  5
0x57600  ldarga.s 1
0x57602  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceHelper Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::get_PersistenceHelper()
0x57607  castclass Microsoft.ReportingServices.OnDemandReportRendering.ROMInstanceObjectCreator
0x5760c  ldloc.s  5
0x5760e  callvirt instance void Microsoft.ReportingServices.OnDemandReportRendering.ROMInstanceObjectCreator::StartParameterInstancesDeserialization(class Microsoft.ReportingServices.OnDemandReportRendering.ParameterCollection paramCollection)
0x57613  ldarga.s 1
0x57615  call     T0x2B00000A
0x5761a  pop
0x5761b  ldarga.s 1
0x5761d  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceHelper Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::get_PersistenceHelper()
0x57622  castclass Microsoft.ReportingServices.OnDemandReportRendering.ROMInstanceObjectCreator
0x57627  callvirt instance void Microsoft.ReportingServices.OnDemandReportRendering.ROMInstanceObjectCreator::CompleteParameterInstancesDeserialization()
0x5762c  br.s     loc_57639
0x5762e  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x57633  ldc.i4.0
0x57634  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool)
0x57639  ldarga.s 1
0x5763b  call     instance bool Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::NextMember()
0x57640  brtrue   loc_57471
0x57645  ret
```
