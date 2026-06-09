# Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent::Add

- ea: `0x3d70`
- end: `0x3d9e`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent::Add`
- size: `46`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x32a0`
- `0x3370`

## callees

- `0x3d50`
- `0x3d70`

## pseudocode

```c

```

## disassembly

```asm
0x3d70  ldarg.0
0x3d71  ldarg.1
0x3d72  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent::CheckColumnIsSelected(string columnName)
0x3d77  brfalse.s loc_3D9D
0x3d79  ldarg.0
0x3d7a  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent::m_valueNames
0x3d7f  ldarg.1
0x3d80  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3d85  ldarg.0
0x3d86  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent::m_valueTypes
0x3d8b  ldarg.2
0x3d8c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3d91  ldarg.0
0x3d92  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent::m_valueContents
0x3d97  ldarg.3
0x3d98  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3d9d  ret
```
