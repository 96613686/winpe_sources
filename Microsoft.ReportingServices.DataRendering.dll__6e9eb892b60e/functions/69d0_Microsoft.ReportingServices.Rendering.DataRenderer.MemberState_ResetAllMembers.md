# Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::ResetAllMembers

- ea: `0x69d0`
- end: `0x6a74`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::ResetAllMembers`
- size: `164`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x69d0`
- `0x6e80`
- `0x6f70`

## callees

- `0x6400`
- `0x6610`
- `0x66c0`
- `0x6920`
- `0x69d0`

## pseudocode

```c

```

## disassembly

```asm
0x69d0  ldarg.0
0x69d1  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::TouchSubReportMember()
0x69d6  ldc.i4.0
0x69d7  stloc.0
0x69d8  ldc.i4.0
0x69d9  stloc.1
0x69da  ldarg.1
0x69db  brtrue.s loc_69E5
0x69dd  ldarg.0
0x69de  ldc.i4.1
0x69df  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::ChangeMemberInstances(bool reset)
0x69e4  stloc.0
0x69e5  ldarg.0
0x69e6  ldc.i4.0
0x69e7  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeChild
0x69ec  ldarg.0
0x69ed  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState> Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_children
0x69f2  brfalse.s loc_6A72
0x69f4  ldarg.0
0x69f5  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState> Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_children
0x69fa  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>::get_Count()
0x69ff  ldc.i4.0
0x6a00  ble.s    loc_6A72
0x6a02  ldarg.0
0x6a03  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState> Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_children
0x6a08  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>::GetEnumerator()
0x6a0d  stloc.2
0x6a0e  br.s     loc_6A59
0x6a10  ldloca.s 2
0x6a12  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>::get_Current()
0x6a17  stloc.3
0x6a18  ldloc.0
0x6a19  ldloc.3
0x6a1a  ldc.i4.0
0x6a1b  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::ResetAllMembers(bool atomHeaderInstanceWalk)
0x6a20  or
0x6a21  stloc.0
0x6a22  ldloc.3
0x6a23  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_IsDynamic()
0x6a28  stloc.s  4
0x6a2a  ldarg.0
0x6a2b  ldarg.0
0x6a2c  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_isDynamic
0x6a31  ldloc.s  4
0x6a33  or
0x6a34  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_isDynamic
0x6a39  ldloc.s  4
0x6a3b  brfalse.s loc_6A48
0x6a3d  ldloc.1
0x6a3e  brtrue.s loc_6A48
0x6a40  ldc.i4.1
0x6a41  stloc.1
0x6a42  ldarg.0
0x6a43  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::SetActiveDynamicMemberPath()
0x6a48  ldloc.1
0x6a49  brtrue.s loc_6A59
0x6a4b  ldarg.0
0x6a4c  ldarg.0
0x6a4d  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeChild
0x6a52  ldc.i4.1
0x6a53  add
0x6a54  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeChild
0x6a59  ldloca.s 2
0x6a5b  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>::MoveNext()
0x6a60  brtrue.s loc_6A10
0x6a62  leave.s  loc_6A72
0x6a64  ldloca.s 2
0x6a66  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>
0x6a6c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6a71  endfinally
0x6a72  ldloc.0
0x6a73  ret
```
