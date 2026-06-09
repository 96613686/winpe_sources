# Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::AddChild

- ea: `0x64e0`
- end: `0x652a`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::AddChild`
- size: `74`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x75d0`
- `0x7610`
- `0x7680`

## callees

- `0x6420`
- `0x6430`
- `0x6440`
- `0x6450`
- `0x64e0`

## pseudocode

```c

```

## disassembly

```asm
0x64e0  ldarg.0
0x64e1  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState> Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_children
0x64e6  brtrue.s loc_64F3
0x64e8  ldarg.0
0x64e9  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>::.ctor()
0x64ee  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState> Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_children
0x64f3  ldarg.0
0x64f4  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState> Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_children
0x64f9  ldarg.1
0x64fa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>::Add(var<u1>)
0x64ff  ldarg.1
0x6500  ldarg.0
0x6501  stfld    class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_parent
0x6506  ldarg.1
0x6507  ldarg.0
0x6508  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_CurrentDynamicMemberPath()
0x650d  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::set_CurrentDynamicMemberPath(string value)
0x6512  ldarg.1
0x6513  ldarg.1
0x6514  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_CurrentDynamicMemberPath()
0x6519  ldarg.0
0x651a  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_MemberID()
0x651f  call     string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::AddMemberToDynamicPath(string path, string memberID)
0x6524  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::set_CurrentDynamicMemberPath(string value)
0x6529  ret
```
