# Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::NextMember

- ea: `0x40c0`
- end: `0x40fc`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::NextMember`
- size: `60`
- prototype: ``
- caller_count: `57`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x61f0`
- `0x79a0`
- `0x80d0`
- `0x8bb0`
- `0x8fd0`
- `0x9d50`
- `0x9f40`
- `0xbf00`
- `0xc280`
- `0xc6c0`
- `0xca90`
- `0xd3b0`
- `0xfdf0`
- `0x11360`
- `0x11af0`
- `0x11de0`
- `0x12140`
- `0x12380`
- `0x12a00`
- `0x12d00`
- `0x12ea0`
- `0x132e0`
- `0x13590`
- `0x13780`
- `0x14690`
- `0x14b50`
- `0x15040`
- `0x15f40`
- `0x16310`
- `0x166b0`
- `0x19510`
- `0x19ae0`
- `0x1a1e0`
- `0x1b0d0`
- `0x1b950`
- `0x1be30`
- `0x1d630`
- `0x1dcc0`
- `0x1e5d0`
- `0x1ebb0`
- `0x1f050`
- `0x1f3a0`
- `0x2dec0`
- `0x2fb30`
- `0x30300`
- `0x30900`
- `0x31050`
- `0x31530`
- `0x31870`
- `0x31c00`

## callees

- `0x40c0`
- `0x6ac0`

## pseudocode

```c

```

## disassembly

```asm
0x40c0  ldarg.0
0x40c1  ldfld    int32 Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_currentMemberIndex
0x40c6  ldarg.0
0x40c7  ldfld    int32 Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_lastMemberInfoIndex
0x40cc  bge.s    loc_40FA
0x40ce  ldarg.0
0x40cf  ldarg.0
0x40d0  ldfld    int32 Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_currentMemberIndex
0x40d5  ldc.i4.1
0x40d6  add
0x40d7  stfld    int32 Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_currentMemberIndex
0x40dc  ldarg.0
0x40dd  ldarg.0
0x40de  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_currentDeclaration
0x40e3  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo> Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration::get_MemberInfoList()
0x40e8  ldarg.0
0x40e9  ldfld    int32 Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_currentMemberIndex
0x40ee  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo>::get_Item(!!T0)
0x40f3  stfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_currentMember
0x40f8  ldc.i4.1
0x40f9  ret
0x40fa  ldc.i4.0
0x40fb  ret
```
