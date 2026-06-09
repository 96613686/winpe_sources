# Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::FindChild

- ea: `0x65b0`
- end: `0x65f8`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::FindChild`
- size: `72`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x7390`
- `0x76f0`
- `0x77c0`

## callees

- `0x65b0`

## pseudocode

```c

```

## disassembly

```asm
0x65b0  ldarg.0
0x65b1  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState> Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_children
0x65b6  brfalse.s loc_65F4
0x65b8  ldarg.0
0x65b9  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState> Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_children
0x65be  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>::GetEnumerator()
0x65c3  stloc.0
0x65c4  br.s     loc_65DB
0x65c6  ldloca.s 0
0x65c8  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>::get_Current()
0x65cd  stloc.1
0x65ce  ldarg.1
0x65cf  ldloc.1
0x65d0  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_id
0x65d5  bne.un.s loc_65DB
0x65d7  ldloc.1
0x65d8  stloc.2
0x65d9  leave.s  loc_65F6
0x65db  ldloca.s 0
0x65dd  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>::MoveNext()
0x65e2  brtrue.s loc_65C6
0x65e4  leave.s  loc_65F4
0x65e6  ldloca.s 0
0x65e8  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>
0x65ee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x65f3  endfinally
0x65f4  ldnull
0x65f5  ret
0x65f6  ldloc.2
0x65f7  ret
```
