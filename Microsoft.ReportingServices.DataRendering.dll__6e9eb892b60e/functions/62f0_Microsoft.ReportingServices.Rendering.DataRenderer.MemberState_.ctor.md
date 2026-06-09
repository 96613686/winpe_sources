# Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::.ctor

- ea: `0x62f0`
- end: `0x6390`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::.ctor`
- size: `160`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x6b50`
- `0x75d0`
- `0x76c0`

## callees

- `0x62f0`
- `0x6450`

## pseudocode

```c

```

## disassembly

```asm
0x62f0  ldarg.0
0x62f1  ldc.i4.m1
0x62f2  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_id
0x62f7  ldarg.0
0x62f8  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor()
0x62fd  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_memberIDMapper
0x6302  ldarg.0
0x6303  ldsfld   string [mscorlib]System.String::Empty
0x6308  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeDynamicMemberPath
0x630d  ldarg.0
0x630e  ldc.i4.1
0x630f  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_hasRows
0x6314  ldarg.0
0x6315  ldsfld   string [mscorlib]System.String::Empty
0x631a  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_memberID
0x631f  ldarg.0
0x6320  ldsfld   string [mscorlib]System.String::Empty
0x6325  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_currentDynamicMemberPath
0x632a  ldarg.0
0x632b  call     instance void [mscorlib]System.Object::.ctor()
0x6330  ldarg.0
0x6331  ldarg.1
0x6332  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember
0x6337  stfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_tablixMember
0x633c  ldarg.0
0x633d  ldarg.1
0x633e  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember
0x6343  stfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_chartMember
0x6348  ldarg.0
0x6349  ldarg.1
0x634a  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapMember
0x634f  stfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapMember Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_mapMember
0x6354  ldarg.1
0x6355  brfalse.s loc_6388
0x6357  ldarg.0
0x6358  ldarg.1
0x6359  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_ID()
0x635e  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_memberID
0x6363  ldarg.0
0x6364  ldarg.0
0x6365  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeDynamicMemberPath
0x636a  ldarg.0
0x636b  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_memberID
0x6370  call     string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::AddMemberToDynamicPath(string path, string memberID)
0x6375  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeDynamicMemberPath
0x637a  ldarg.0
0x637b  ldc.i4.1
0x637c  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_isDynamic
0x6381  ldarg.0
0x6382  ldc.i4.1
0x6383  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_hasMember
0x6388  ldarg.0
0x6389  ldarg.2
0x638a  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_id
0x638f  ret
```
