# Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::ResetDynamicMembers

- ea: `0x6a80`
- end: `0x6b11`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::ResetDynamicMembers`
- size: `145`
- prototype: ``
- caller_count: `8`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x6700`
- `0x67c0`
- `0x6a80`
- `0x6bb0`
- `0x6d90`
- `0x6f70`
- `0x7390`
- `0x76f0`

## callees

- `0x6390`
- `0x6400`
- `0x6610`
- `0x66c0`
- `0x6920`
- `0x6a80`

## pseudocode

```c

```

## disassembly

```asm
0x6a80  ldarg.0
0x6a81  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::TouchSubReportMember()
0x6a86  ldc.i4.0
0x6a87  stloc.0
0x6a88  ldloc.0
0x6a89  ldarg.0
0x6a8a  ldc.i4.1
0x6a8b  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::ChangeMemberInstances(bool reset)
0x6a90  or
0x6a91  stloc.0
0x6a92  ldarg.0
0x6a93  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState> Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_children
0x6a98  brfalse.s loc_6B0F
0x6a9a  ldarg.0
0x6a9b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState> Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_children
0x6aa0  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>::get_Count()
0x6aa5  ldc.i4.0
0x6aa6  ble.s    loc_6B0F
0x6aa8  ldarg.0
0x6aa9  ldc.i4.0
0x6aaa  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeChild
0x6aaf  ldc.i4.0
0x6ab0  stloc.1
0x6ab1  ldarg.0
0x6ab2  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState> Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_children
0x6ab7  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>::GetEnumerator()
0x6abc  stloc.2
0x6abd  br.s     loc_6ADF
0x6abf  ldloca.s 2
0x6ac1  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>::get_Current()
0x6ac6  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_IsDynamic()
0x6acb  brfalse.s loc_6AD1
0x6acd  ldc.i4.1
0x6ace  stloc.1
0x6acf  leave.s  loc_6AF8
0x6ad1  ldarg.0
0x6ad2  ldarg.0
0x6ad3  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeChild
0x6ad8  ldc.i4.1
0x6ad9  add
0x6ada  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeChild
0x6adf  ldloca.s 2
0x6ae1  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>::MoveNext()
0x6ae6  brtrue.s loc_6ABF
0x6ae8  leave.s  loc_6AF8
0x6aea  ldloca.s 2
0x6aec  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>
0x6af2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6af7  endfinally
0x6af8  ldloc.1
0x6af9  brfalse.s loc_6B0F
0x6afb  ldloc.0
0x6afc  ldarg.0
0x6afd  call     instance class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_ActiveChild()
0x6b02  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::ResetDynamicMembers()
0x6b07  or
0x6b08  stloc.0
0x6b09  ldarg.0
0x6b0a  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::SetActiveDynamicMemberPath()
0x6b0f  ldloc.0
0x6b10  ret
```
