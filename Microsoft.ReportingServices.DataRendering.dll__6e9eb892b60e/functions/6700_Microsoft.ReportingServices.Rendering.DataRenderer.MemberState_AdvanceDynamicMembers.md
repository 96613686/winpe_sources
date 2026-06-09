# Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::AdvanceDynamicMembers

- ea: `0x6700`
- end: `0x67bb`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::AdvanceDynamicMembers`
- size: `187`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x67c0`
- `0x6b90`
- `0x6e80`
- `0x6f70`

## callees

- `0x6400`
- `0x6610`
- `0x66c0`
- `0x6700`
- `0x67c0`
- `0x6920`
- `0x6a80`

## pseudocode

```c

```

## disassembly

```asm
0x6700  ldc.i4.0
0x6701  stloc.0
0x6702  ldarg.0
0x6703  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::TouchSubReportMember()
0x6708  ldarg.0
0x6709  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::AdvanceChildren()
0x670e  stloc.0
0x670f  ldloc.0
0x6710  brtrue   loc_67B9
0x6715  ldarg.0
0x6716  ldc.i4.0
0x6717  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::ChangeMemberInstances(bool reset)
0x671c  stloc.0
0x671d  ldloc.0
0x671e  brfalse  loc_67B9
0x6723  ldarg.0
0x6724  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState> Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_children
0x6729  brfalse.s loc_675F
0x672b  ldarg.0
0x672c  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState> Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_children
0x6731  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>::GetEnumerator()
0x6736  stloc.1
0x6737  br.s     loc_6746
0x6739  ldloca.s 1
0x673b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>::get_Current()
0x6740  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::ResetDynamicMembers()
0x6745  pop
0x6746  ldloca.s 1
0x6748  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>::MoveNext()
0x674d  brtrue.s loc_6739
0x674f  leave.s  loc_675F
0x6751  ldloca.s 1
0x6753  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>
0x6759  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x675e  endfinally
0x675f  ldarg.0
0x6760  ldc.i4.0
0x6761  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeChild
0x6766  ldarg.0
0x6767  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState> Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_children
0x676c  brfalse.s loc_67B9
0x676e  ldarg.0
0x676f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState> Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_children
0x6774  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>::GetEnumerator()
0x6779  stloc.1
0x677a  br.s     loc_67A0
0x677c  ldloca.s 1
0x677e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>::get_Current()
0x6783  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_IsDynamic()
0x6788  brfalse.s loc_6792
0x678a  ldarg.0
0x678b  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::SetActiveDynamicMemberPath()
0x6790  leave.s  loc_67B9
0x6792  ldarg.0
0x6793  ldarg.0
0x6794  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeChild
0x6799  ldc.i4.1
0x679a  add
0x679b  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeChild
0x67a0  ldloca.s 1
0x67a2  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>::MoveNext()
0x67a7  brtrue.s loc_677C
0x67a9  leave.s  loc_67B9
0x67ab  ldloca.s 1
0x67ad  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>
0x67b3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x67b8  endfinally
0x67b9  ldloc.0
0x67ba  ret
```
