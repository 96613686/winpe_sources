# Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkReport

- ea: `0x6f70`
- end: `0x7170`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkReport`
- size: `512`
- prototype: ``
- caller_count: `7`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x1cf0`
- `0x1d70`
- `0x1e90`
- `0x21e0`
- `0x4a00`
- `0x5aa0`
- `0x7ad0`

## callees

- `0x5760`
- `0x57f0`
- `0x5a10`
- `0x5a20`
- `0x5a30`
- `0x5a40`
- `0x6700`
- `0x69d0`
- `0x6a80`
- `0x6e20`
- `0x6f70`
- `0x7550`
- `0x76c0`

## pseudocode

```c

```

## disassembly

```asm
0x6f70  ldarg.1
0x6f71  brfalse.s loc_6F88
0x6f73  ldarg.1
0x6f74  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSectionCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_ReportSections()
0x6f79  brfalse.s loc_6F88
0x6f7b  ldarg.1
0x6f7c  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSectionCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_ReportSections()
0x6f81  callvirt instance int32 class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSection>::get_Count()
0x6f86  brtrue.s loc_6F89
0x6f88  ret
0x6f89  ldarg.0
0x6f8a  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_reportHandler
0x6f8f  brfalse.s loc_6FA1
0x6f91  ldc.i4.0
0x6f92  stloc.2
0x6f93  ldarg.0
0x6f94  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_reportHandler
0x6f99  ldarg.1
0x6f9a  ldloca.s 2
0x6f9c  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler::OnReportBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report, bool& walkChildren)
0x6fa1  ldc.i4.1
0x6fa2  stloc.0
0x6fa3  ldarg.0
0x6fa4  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_instanceWalk
0x6fa9  brtrue.s loc_6FB3
0x6fab  ldarg.0
0x6fac  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_atomHeaderInstanceWalk
0x6fb1  brfalse.s loc_6FEE
0x6fb3  ldarg.0
0x6fb4  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_dynamicMemberHierarchyRoot
0x6fb9  brtrue.s loc_6FDA
0x6fbb  ldarg.0
0x6fbc  ldarg.0
0x6fbd  ldstr    aReport// "Report"
0x6fc2  ldarg.1
0x6fc3  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_ID()
0x6fc8  call     string [mscorlib]System.String::Concat(string, string)
0x6fcd  ldnull
0x6fce  call     instance class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::AddContainer(string childID, class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState parentMemberState)
0x6fd3  stfld    class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_dynamicMemberHierarchyRoot
0x6fd8  br.s     loc_6FEE
0x6fda  ldarg.0
0x6fdb  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_atomHeaderInstanceWalk
0x6fe0  brtrue.s loc_6FEE
0x6fe2  ldarg.0
0x6fe3  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_dynamicMemberHierarchyRoot
0x6fe8  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::ResetDynamicMembers()
0x6fed  pop
0x6fee  ldarg.0
0x6fef  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_outputRowHandler
0x6ff4  brfalse.s loc_7001
0x6ff6  ldarg.0
0x6ff7  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_outputRowHandler
0x6ffc  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler::OnRegionBegin()
0x7001  ldc.i4.1
0x7002  stloc.1
0x7003  ldarg.0
0x7004  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_firstInstancePass
0x7009  brfalse.s loc_702B
0x700b  ldarg.0
0x700c  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_instanceWalk
0x7011  brtrue.s loc_701B
0x7013  ldarg.0
0x7014  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_atomHeaderInstanceWalk
0x7019  brfalse.s loc_702B
0x701b  ldarg.0
0x701c  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_reportHandler
0x7021  isinst   Microsoft.ReportingServices.Rendering.DataRenderer.XmlTypeHandler
0x7026  brfalse  loc_7156
0x702b  ldarg.0
0x702c  ldc.i4.1
0x702d  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_renderOutDataInWalk
0x7032  br       loc_7156
0x7037  ldc.i4.0
0x7038  stloc.0
0x7039  ldarg.0
0x703a  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_outputRowHandler
0x703f  brfalse.s loc_704C
0x7041  ldarg.0
0x7042  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_outputRowHandler
0x7047  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler::OnRowBegin()
0x704c  ldarg.0
0x704d  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_instanceWalk
0x7052  brfalse.s loc_7063
0x7054  ldarg.0
0x7055  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_firstInstancePass
0x705a  brtrue.s loc_7063
0x705c  ldarg.0
0x705d  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkRowWithActiveDynamicMemberPath()
0x7062  stloc.1
0x7063  ldloc.1
0x7064  brfalse.s loc_70C4
0x7066  ldarg.1
0x7067  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSectionCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_ReportSections()
0x706c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSection>::GetEnumerator()
0x7071  stloc.3
0x7072  br.s     loc_70B0
0x7074  ldloc.3
0x7075  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSection>::get_Current()
0x707a  stloc.s  4
0x707c  ldloc.s  4
0x707e  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Body [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSection::get_Body()
0x7083  brfalse.s loc_70B0
0x7085  ldloc.s  4
0x7087  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Body [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSection::get_Body()
0x708c  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItemCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Body::get_ReportItemCollection()
0x7091  stloc.s  5
0x7093  ldloc.s  5
0x7095  brfalse.s loc_70B0
0x7097  ldc.i4.1
0x7098  ldloc.s  4
0x709a  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSection::get_DataElementOutput()
0x709f  beq.s    loc_70B0
0x70a1  ldarg.0
0x70a2  ldloc.s  5
0x70a4  ldarg.0
0x70a5  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_dynamicMemberHierarchyRoot
0x70aa  ldc.i4.1
0x70ab  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkReportItemCollection(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItemCollection reportItemCollection, class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState parentMemberState, bool outputMembers)
0x70b0  ldloc.3
0x70b1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x70b6  brtrue.s loc_7074
0x70b8  leave.s  loc_70C4
0x70ba  ldloc.3
0x70bb  brfalse.s loc_70C3
0x70bd  ldloc.3
0x70be  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x70c3  endfinally
0x70c4  ldarg.0
0x70c5  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_instanceWalk
0x70ca  brtrue.s loc_70D4
0x70cc  ldarg.0
0x70cd  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_atomHeaderInstanceWalk
0x70d2  brfalse.s loc_7129
0x70d4  ldarg.0
0x70d5  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_firstInstancePass
0x70da  brtrue.s loc_70F2
0x70dc  ldarg.0
0x70dd  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_atomHeaderInstanceWalk
0x70e2  brtrue.s loc_7129
0x70e4  ldarg.0
0x70e5  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_dynamicMemberHierarchyRoot
0x70ea  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::AdvanceDynamicMembers()
0x70ef  stloc.0
0x70f0  br.s     loc_7129
0x70f2  ldc.i4.0
0x70f3  stloc.s  6
0x70f5  ldarg.0
0x70f6  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_dynamicMemberHierarchyRoot
0x70fb  ldarg.0
0x70fc  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_atomHeaderInstanceWalk
0x7101  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::ResetAllMembers(bool atomHeaderInstanceWalk)
0x7106  stloc.s  6
0x7108  ldarg.0
0x7109  ldc.i4.0
0x710a  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_firstInstancePass
0x710f  ldarg.0
0x7110  ldc.i4.1
0x7111  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_renderOutDataInWalk
0x7116  ldarg.0
0x7117  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_reportHandler
0x711c  isinst   Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler
0x7121  brtrue.s loc_7126
0x7123  ldc.i4.1
0x7124  br.s     loc_7128
0x7126  ldloc.s  6
0x7128  stloc.0
0x7129  ldarg.0
0x712a  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_reportHandler
0x712f  brfalse.s loc_7140
0x7131  ldarg.0
0x7132  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_reportHandler
0x7137  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler::get_Done()
0x713c  brfalse.s loc_7140
0x713e  ldc.i4.0
0x713f  stloc.0
0x7140  ldarg.0
0x7141  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_outputRowHandler
0x7146  brfalse.s loc_7156
0x7148  ldloc.1
0x7149  brfalse.s loc_7156
0x714b  ldarg.0
0x714c  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_outputRowHandler
0x7151  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler::OnRowEnd()
0x7156  ldloc.0
0x7157  brtrue   loc_7037
0x715c  ldarg.0
0x715d  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_outputRowHandler
0x7162  brfalse.s loc_716F
0x7164  ldarg.0
0x7165  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_outputRowHandler
0x716a  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler::OnRegionEnd()
0x716f  ret
```
