# Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::ContainsDynamicMemberPath

- ea: `0x6880`
- end: `0x6912`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::ContainsDynamicMemberPath`
- size: `146`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x6880`
- `0x6e20`

## callees

- `0x64b0`
- `0x6880`

## pseudocode

```c

```

## disassembly

```asm
0x6880  ldarg.0
0x6881  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_memberID
0x6886  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x688b  brtrue.s loc_68AE
0x688d  ldarga.s 1
0x688f  ldarg.0
0x6890  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_memberID
0x6895  call     bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::RemoveMemberFromDynamicPath(string& path, string memberID)
0x689a  brtrue.s loc_68AE
0x689c  ldarg.1
0x689d  ldstr    a0_0// "_0"
0x68a2  ldstr    a1// "_1"
0x68a7  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x68ac  starg.s  1
0x68ae  ldstr    a1x// "_1x"
0x68b3  ldarg.1
0x68b4  ldc.i4.4
0x68b5  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x68ba  brtrue.s loc_68BE
0x68bc  ldc.i4.1
0x68bd  ret
0x68be  ldarg.0
0x68bf  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState> Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_children
0x68c4  brfalse.s loc_690E
0x68c6  ldarg.0
0x68c7  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState> Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_children
0x68cc  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>::get_Count()
0x68d1  ldc.i4.0
0x68d2  ble.s    loc_690E
0x68d4  ldarg.0
0x68d5  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState> Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_children
0x68da  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>::GetEnumerator()
0x68df  stloc.0
0x68e0  br.s     loc_68F5
0x68e2  ldloca.s 0
0x68e4  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>::get_Current()
0x68e9  ldarg.1
0x68ea  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::ContainsDynamicMemberPath(string dynamicMemberPaths)
0x68ef  brfalse.s loc_68F5
0x68f1  ldc.i4.1
0x68f2  stloc.1
0x68f3  leave.s  loc_6910
0x68f5  ldloca.s 0
0x68f7  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>::MoveNext()
0x68fc  brtrue.s loc_68E2
0x68fe  leave.s  loc_690E
0x6900  ldloca.s 0
0x6902  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>
0x6908  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x690d  endfinally
0x690e  ldc.i4.0
0x690f  ret
0x6910  ldloc.1
0x6911  ret
```
