# Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::IsActiveChild

- ea: `0x6530`
- end: `0x65ad`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::IsActiveChild`
- size: `125`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x7390`
- `0x76f0`
- `0x77c0`

## callees

- `0x6390`
- `0x6530`
- `0x6600`

## pseudocode

```c

```

## disassembly

```asm
0x6530  ldarg.0
0x6531  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_parent
0x6536  brfalse.s loc_65AB
0x6538  ldarg.0
0x6539  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_parent
0x653e  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState> Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_children
0x6543  brfalse.s loc_65AB
0x6545  ldarg.0
0x6546  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_parent
0x654b  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeChild
0x6550  ldarg.0
0x6551  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_parent
0x6556  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState> Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_children
0x655b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>::get_Count()
0x6560  bge.s    loc_65AB
0x6562  ldarg.0
0x6563  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_id
0x6568  ldarg.0
0x6569  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_parent
0x656e  callvirt instance class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_ActiveChild()
0x6573  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_id
0x6578  bne.un.s loc_657C
0x657a  ldc.i4.1
0x657b  ret
0x657c  ldarg.0
0x657d  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_ActiveDynamicMemberPath()
0x6582  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6587  brtrue.s loc_65A6
0x6589  ldarg.0
0x658a  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_parent
0x658f  callvirt instance class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_ActiveChild()
0x6594  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_ActiveDynamicMemberPath()
0x6599  ldarg.0
0x659a  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_ActiveDynamicMemberPath()
0x659f  callvirt instance bool [mscorlib]System.String::Contains(string)
0x65a4  br.s     loc_65A7
0x65a6  ldc.i4.0
0x65a7  brfalse.s loc_65AB
0x65a9  ldc.i4.1
0x65aa  ret
0x65ab  ldc.i4.0
0x65ac  ret
```
