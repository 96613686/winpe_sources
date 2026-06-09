# Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_ActiveChild

- ea: `0x6390`
- end: `0x63a2`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_ActiveChild`
- size: `18`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x6530`
- `0x67c0`
- `0x6920`
- `0x6a80`

## pseudocode

```c

```

## disassembly

```asm
0x6390  ldarg.0
0x6391  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState> Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_children
0x6396  ldarg.0
0x6397  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeChild
0x639c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>::get_Item(!!T0)
0x63a1  ret
```
