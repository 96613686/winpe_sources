# Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkNextDataRegionOrMapRow

- ea: `0x6e80`
- end: `0x6f66`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkNextDataRegionOrMapRow`
- size: `230`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x6d60`
- `0xb7f0`

## callees

- `0x57f0`
- `0x5a10`
- `0x5a20`
- `0x5a40`
- `0x6700`
- `0x69d0`
- `0x6d30`
- `0x6e20`
- `0x6e80`
- `0x7390`

## pseudocode

```c

```

## disassembly

```asm
0x6e80  ldc.i4.0
0x6e81  stloc.0
0x6e82  ldarg.0
0x6e83  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_outputRowHandler
0x6e88  brfalse.s loc_6E95
0x6e8a  ldarg.0
0x6e8b  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_outputRowHandler
0x6e90  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler::OnRowBegin()
0x6e95  ldc.i4.1
0x6e96  stloc.1
0x6e97  ldarg.0
0x6e98  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_instanceWalk
0x6e9d  brfalse.s loc_6EAE
0x6e9f  ldarg.0
0x6ea0  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_firstInstancePass
0x6ea5  brtrue.s loc_6EAE
0x6ea7  ldarg.0
0x6ea8  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkRowWithActiveDynamicMemberPath()
0x6ead  stloc.1
0x6eae  ldloc.1
0x6eaf  brfalse.s loc_6EBF
0x6eb1  ldarg.0
0x6eb2  ldarg.1
0x6eb3  ldarg.0
0x6eb4  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_dynamicMemberHierarchyRoot
0x6eb9  ldc.i4.1
0x6eba  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkReportItem(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem reportItem, class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState parentMemberState, bool outputMembers)
0x6ebf  ldarg.0
0x6ec0  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_instanceWalk
0x6ec5  brtrue.s loc_6ECF
0x6ec7  ldarg.0
0x6ec8  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_atomHeaderInstanceWalk
0x6ecd  brfalse.s loc_6F21
0x6ecf  ldarg.0
0x6ed0  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_firstInstancePass
0x6ed5  brtrue.s loc_6EED
0x6ed7  ldarg.0
0x6ed8  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_atomHeaderInstanceWalk
0x6edd  brtrue.s loc_6F21
0x6edf  ldarg.0
0x6ee0  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_dynamicMemberHierarchyRoot
0x6ee5  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::AdvanceDynamicMembers()
0x6eea  stloc.0
0x6eeb  br.s     loc_6F21
0x6eed  ldc.i4.0
0x6eee  stloc.2
0x6eef  ldarg.0
0x6ef0  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_dynamicMemberHierarchyRoot
0x6ef5  ldarg.0
0x6ef6  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::get_AtomHeaderInstanceWalk()
0x6efb  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::ResetAllMembers(bool atomHeaderInstanceWalk)
0x6f00  stloc.2
0x6f01  ldarg.0
0x6f02  ldc.i4.0
0x6f03  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_firstInstancePass
0x6f08  ldarg.0
0x6f09  ldc.i4.1
0x6f0a  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_renderOutDataInWalk
0x6f0f  ldarg.0
0x6f10  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_reportHandler
0x6f15  isinst   Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler
0x6f1a  brtrue.s loc_6F1F
0x6f1c  ldc.i4.1
0x6f1d  br.s     loc_6F20
0x6f1f  ldloc.2
0x6f20  stloc.0
0x6f21  ldarg.0
0x6f22  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_reportHandler
0x6f27  brfalse.s loc_6F38
0x6f29  ldarg.0
0x6f2a  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_reportHandler
0x6f2f  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler::get_Done()
0x6f34  brfalse.s loc_6F38
0x6f36  ldc.i4.0
0x6f37  stloc.0
0x6f38  ldarg.0
0x6f39  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_outputRowHandler
0x6f3e  brfalse.s loc_6F4E
0x6f40  ldloc.1
0x6f41  brfalse.s loc_6F4E
0x6f43  ldarg.0
0x6f44  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_outputRowHandler
0x6f49  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler::OnRowEnd()
0x6f4e  ldarg.0
0x6f4f  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_outputRowHandler
0x6f54  brfalse.s loc_6F64
0x6f56  ldloc.0
0x6f57  brtrue.s loc_6F64
0x6f59  ldarg.0
0x6f5a  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_outputRowHandler
0x6f5f  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler::OnRegionEnd()
0x6f64  ldloc.0
0x6f65  ret
```
