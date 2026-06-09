# Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::AdvanceChildren

- ea: `0x67c0`
- end: `0x6876`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::AdvanceChildren`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x6700`

## callees

- `0x6390`
- `0x6600`
- `0x6700`
- `0x67c0`
- `0x6920`
- `0x6a80`

## pseudocode

```c

```

## disassembly

```asm
0x67c0  ldc.i4.0
0x67c1  stloc.0
0x67c2  ldarg.0
0x67c3  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState> Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_children
0x67c8  brfalse  loc_6874
0x67cd  ldarg.0
0x67ce  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState> Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_children
0x67d3  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>::get_Count()
0x67d8  stloc.1
0x67d9  ldarg.0
0x67da  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeChild
0x67df  ldloc.1
0x67e0  bge      loc_6874
0x67e5  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0x67ea  ldarg.0
0x67eb  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeChild
0x67f0  ldloc.1
0x67f1  clt
0x67f3  ldstr    aActiveChildInd// "Active Child index out of range in Adva"...
0x67f8  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x67fd  ldarg.0
0x67fe  call     instance class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_ActiveChild()
0x6803  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_ActiveDynamicMemberPath()
0x6808  stloc.2
0x6809  ldarg.0
0x680a  call     instance class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_ActiveChild()
0x680f  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::AdvanceDynamicMembers()
0x6814  stloc.0
0x6815  br.s     loc_6844
0x6817  ldarg.0
0x6818  ldarg.0
0x6819  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeChild
0x681e  ldc.i4.1
0x681f  add
0x6820  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeChild
0x6825  ldloc.2
0x6826  ldarg.0
0x6827  call     instance class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_ActiveChild()
0x682c  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_ActiveDynamicMemberPath()
0x6831  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x6836  brfalse.s loc_6844
0x6838  ldarg.0
0x6839  call     instance class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_ActiveChild()
0x683e  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::ResetDynamicMembers()
0x6843  stloc.0
0x6844  ldloc.0
0x6845  brtrue.s loc_6852
0x6847  ldarg.0
0x6848  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeChild
0x684d  ldc.i4.1
0x684e  add
0x684f  ldloc.1
0x6850  blt.s    loc_6817
0x6852  ldarg.0
0x6853  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeChild
0x6858  ldloc.1
0x6859  bge.s    loc_6874
0x685b  ldloc.2
0x685c  ldarg.0
0x685d  call     instance class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_ActiveChild()
0x6862  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_ActiveDynamicMemberPath()
0x6867  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x686c  brfalse.s loc_6874
0x686e  ldarg.0
0x686f  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::SetActiveDynamicMemberPath()
0x6874  ldloc.0
0x6875  ret
```
