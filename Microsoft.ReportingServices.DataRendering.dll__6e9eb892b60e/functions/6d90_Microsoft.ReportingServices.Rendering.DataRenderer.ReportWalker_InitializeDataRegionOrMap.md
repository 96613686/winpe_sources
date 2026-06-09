# Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::InitializeDataRegionOrMap

- ea: `0x6d90`
- end: `0x6e1c`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::InitializeDataRegionOrMap`
- size: `140`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x6d60`
- `0xb7f0`

## callees

- `0x5a30`
- `0x6a80`
- `0x6d90`
- `0x76c0`

## pseudocode

```c

```

## disassembly

```asm
0x6d90  ldarg.0
0x6d91  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_outputRowHandler
0x6d96  brfalse.s loc_6DA3
0x6d98  ldarg.0
0x6d99  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_outputRowHandler
0x6d9e  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler::OnRegionBegin()
0x6da3  ldarg.0
0x6da4  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_instanceWalk
0x6da9  brtrue.s loc_6DB3
0x6dab  ldarg.0
0x6dac  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_atomHeaderInstanceWalk
0x6db1  brfalse.s loc_6DEE
0x6db3  ldarg.0
0x6db4  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_dynamicMemberHierarchyRoot
0x6db9  brtrue.s loc_6DDA
0x6dbb  ldarg.0
0x6dbc  ldarg.0
0x6dbd  ldstr    aDr// "DR"
0x6dc2  ldarg.1
0x6dc3  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_ID()
0x6dc8  call     string [mscorlib]System.String::Concat(string, string)
0x6dcd  ldnull
0x6dce  call     instance class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::AddContainer(string childID, class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState parentMemberState)
0x6dd3  stfld    class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_dynamicMemberHierarchyRoot
0x6dd8  br.s     loc_6DEE
0x6dda  ldarg.0
0x6ddb  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_atomHeaderInstanceWalk
0x6de0  brtrue.s loc_6DEE
0x6de2  ldarg.0
0x6de3  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_dynamicMemberHierarchyRoot
0x6de8  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::ResetDynamicMembers()
0x6ded  pop
0x6dee  ldarg.0
0x6def  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_firstInstancePass
0x6df4  brfalse.s loc_6E13
0x6df6  ldarg.0
0x6df7  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_instanceWalk
0x6dfc  brtrue.s loc_6E06
0x6dfe  ldarg.0
0x6dff  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_atomHeaderInstanceWalk
0x6e04  brfalse.s loc_6E13
0x6e06  ldarg.0
0x6e07  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_reportHandler
0x6e0c  isinst   Microsoft.ReportingServices.Rendering.DataRenderer.XmlTypeHandler
0x6e11  brfalse.s loc_6E1A
0x6e13  ldarg.0
0x6e14  ldc.i4.1
0x6e15  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_renderOutDataInWalk
0x6e1a  ldc.i4.1
0x6e1b  ret
```
