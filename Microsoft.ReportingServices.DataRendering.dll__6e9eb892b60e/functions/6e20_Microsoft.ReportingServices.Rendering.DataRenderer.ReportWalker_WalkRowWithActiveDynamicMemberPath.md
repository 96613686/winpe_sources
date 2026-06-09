# Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkRowWithActiveDynamicMemberPath

- ea: `0x6e20`
- end: `0x6e7c`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkRowWithActiveDynamicMemberPath`
- size: `92`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x6e80`
- `0x6f70`

## callees

- `0x6600`
- `0x6880`
- `0x6e20`

## pseudocode

```c

```

## disassembly

```asm
0x6e20  ldc.i4.1
0x6e21  stloc.0
0x6e22  ldarg.0
0x6e23  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_dynamicMemberHierarchyRoot
0x6e28  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_ActiveDynamicMemberPath()
0x6e2d  stloc.1
0x6e2e  ldloc.1
0x6e2f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6e34  brtrue.s loc_6E7A
0x6e36  ldarg.0
0x6e37  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_activeDefinitionPaths
0x6e3c  ldloc.1
0x6e3d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::ContainsKey(var<u1>)
0x6e42  brtrue.s loc_6E6D
0x6e44  ldarg.0
0x6e45  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_dynamicMemberHierarchyRoot
0x6e4a  ldstr    a0_0// "_0"
0x6e4f  ldloc.1
0x6e50  call     string [mscorlib]System.String::Concat(string, string)
0x6e55  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::ContainsDynamicMemberPath(string dynamicMemberPaths)
0x6e5a  ldc.i4.0
0x6e5b  ceq
0x6e5d  stloc.0
0x6e5e  ldarg.0
0x6e5f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_activeDefinitionPaths
0x6e64  ldloc.1
0x6e65  ldloc.0
0x6e66  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::set_Item(var<u1>, !!T0)
0x6e6b  br.s     loc_6E7A
0x6e6d  ldarg.0
0x6e6e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_activeDefinitionPaths
0x6e73  ldloc.1
0x6e74  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::get_Item(void)
0x6e79  stloc.0
0x6e7a  ldloc.0
0x6e7b  ret
```
