# Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::GetMemberState

- ea: `0x76f0`
- end: `0x77bf`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::GetMemberState`
- size: `207`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0xbad0`
- `0xc6d0`
- `0xca30`

## callees

- `0x63f0`
- `0x6400`
- `0x6430`
- `0x6530`
- `0x65b0`
- `0x6600`
- `0x6a80`
- `0x6b20`
- `0x6d10`
- `0x75d0`
- `0x76f0`

## pseudocode

```c

```

## disassembly

```asm
0x76f0  ldnull
0x76f1  stloc.1
0x76f2  ldarg.2
0x76f3  ldarg.1
0x76f4  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_ID()
0x76f9  ldloca.s 0
0x76fb  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::GetDynamicItemID(string stringID, [out] int32& id)
0x7700  brfalse.s loc_771D
0x7702  ldarg.2
0x7703  ldloc.0
0x7704  callvirt instance class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::FindChild(int32 childID)
0x7709  stloc.1
0x770a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0x770f  ldloc.1
0x7710  ldnull
0x7711  cgt.un
0x7713  ldstr    aDynamicMemberN// "Dynamic member not found in the parent "...
0x7718  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x771d  ldloc.1
0x771e  brtrue.s loc_7748
0x7720  ldarg.0
0x7721  ldarg.1
0x7722  ldarg.2
0x7723  call     instance class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::AddDynamicMember(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember member, class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState parentMemberState)
0x7728  stloc.1
0x7729  ldarg.0
0x772a  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_instanceWalk
0x772f  brfalse.s loc_7748
0x7731  ldarg.1
0x7732  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_IsStatic()
0x7737  brtrue.s loc_7748
0x7739  ldarg.0
0x773a  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_atomHeaderInstanceWalk
0x773f  brtrue.s loc_7748
0x7741  ldloc.1
0x7742  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::ResetDynamicMembers()
0x7747  pop
0x7748  ldloc.1
0x7749  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_IsDynamic()
0x774e  brfalse.s loc_77BD
0x7750  ldloc.1
0x7751  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::IsActiveChild()
0x7756  brfalse.s loc_7760
0x7758  ldloc.1
0x7759  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_HasRows()
0x775e  brtrue.s loc_77BD
0x7760  ldarg.3
0x7761  ldc.i4.0
0x7762  stind.i1
0x7763  ldloc.1
0x7764  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_HasRows()
0x7769  brfalse.s loc_77BD
0x776b  ldloc.1
0x776c  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_CurrentDynamicMemberPath()
0x7771  stloc.2
0x7772  ldloc.2
0x7773  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7778  brtrue.s loc_7796
0x777a  ldloc.1
0x777b  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_ActiveDynamicMemberPath()
0x7780  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7785  brtrue.s loc_7796
0x7787  ldloc.2
0x7788  ldloc.2
0x7789  callvirt instance int32 [mscorlib]System.String::get_Length()
0x778e  ldc.i4.1
0x778f  sub
0x7790  callvirt instance string [mscorlib]System.String::Remove(int32)
0x7795  stloc.2
0x7796  ldloc.2
0x7797  ldloc.1
0x7798  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_ActiveDynamicMemberPath()
0x779d  call     string [mscorlib]System.String::Concat(string, string)
0x77a2  stloc.2
0x77a3  ldarg.0
0x77a4  call     instance class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::get_DynamicMemberHierarchy()
0x77a9  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_ActiveDynamicMemberPath()
0x77ae  ldloc.2
0x77af  callvirt instance bool [mscorlib]System.String::Contains(string)
0x77b4  brfalse.s loc_77BD
0x77b6  ldarg.3
0x77b7  ldc.i4.1
0x77b8  stind.i1
0x77b9  ldarg.s  4
0x77bb  ldc.i4.1
0x77bc  stind.i1
0x77bd  ldloc.1
0x77be  ret
```
