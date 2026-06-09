# Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::SetActiveDynamicMemberPath

- ea: `0x6920`
- end: `0x69cb`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::SetActiveDynamicMemberPath`
- size: `171`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x6700`
- `0x67c0`
- `0x69d0`
- `0x6a80`

## callees

- `0x6390`
- `0x6450`
- `0x6600`
- `0x6920`

## pseudocode

```c

```

## disassembly

```asm
0x6920  ldarg.0
0x6921  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState> Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_children
0x6926  brfalse  loc_69CA
0x692b  ldarg.0
0x692c  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState> Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_children
0x6931  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>::get_Count()
0x6936  ldc.i4.0
0x6937  ble      loc_69CA
0x693c  ldarg.0
0x693d  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeChild
0x6942  ldarg.0
0x6943  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState> Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_children
0x6948  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState>::get_Count()
0x694d  bge.s    loc_69CA
0x694f  ldarg.0
0x6950  ldsfld   string [mscorlib]System.String::Empty
0x6955  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeDynamicMemberPath
0x695a  ldarg.0
0x695b  ldarg.0
0x695c  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeDynamicMemberPath
0x6961  ldarg.0
0x6962  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_memberID
0x6967  call     string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::AddMemberToDynamicPath(string path, string memberID)
0x696c  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeDynamicMemberPath
0x6971  ldarg.0
0x6972  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeDynamicMemberPath
0x6977  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x697c  brtrue.s loc_69AE
0x697e  ldarg.0
0x697f  call     instance class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_ActiveChild()
0x6984  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_ActiveDynamicMemberPath()
0x6989  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x698e  brtrue.s loc_69AE
0x6990  ldarg.0
0x6991  ldarg.0
0x6992  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeDynamicMemberPath
0x6997  ldarg.0
0x6998  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeDynamicMemberPath
0x699d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x69a2  ldc.i4.1
0x69a3  sub
0x69a4  callvirt instance string [mscorlib]System.String::Remove(int32)
0x69a9  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeDynamicMemberPath
0x69ae  ldarg.0
0x69af  ldarg.0
0x69b0  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeDynamicMemberPath
0x69b5  ldarg.0
0x69b6  call     instance class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_ActiveChild()
0x69bb  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_ActiveDynamicMemberPath()
0x69c0  call     string [mscorlib]System.String::Concat(string, string)
0x69c5  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::m_activeDynamicMemberPath
0x69ca  ret
```
