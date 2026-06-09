# Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::NextMember

- ea: `0x1eb0`
- end: `0x1f2a`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::NextMember`
- size: `122`
- prototype: ``
- caller_count: `58`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1eb0`
- `0x6270`
- `0x7a10`
- `0x81b0`
- `0x8c50`
- `0x9050`
- `0x9dc0`
- `0x9fb0`
- `0xbf70`
- `0xc2e0`
- `0xc730`
- `0xcb00`
- `0xd4a0`
- `0x10010`
- `0x114e0`
- `0x11b80`
- `0x11e60`
- `0x121d0`
- `0x12400`
- `0x12a80`
- `0x12d70`
- `0x12f00`
- `0x13360`
- `0x13600`
- `0x137e0`
- `0x14750`
- `0x14bb0`
- `0x150c0`
- `0x16090`
- `0x16380`
- `0x167c0`
- `0x19620`
- `0x19b60`
- `0x1a250`
- `0x1b180`
- `0x1b9c0`
- `0x1bea0`
- `0x1d750`
- `0x1dd20`
- `0x1e650`
- `0x1ec10`
- `0x1f0c0`
- `0x1f420`
- `0x2df30`
- `0x2fbd0`
- `0x303e0`
- `0x30970`
- `0x31150`
- `0x315a0`
- `0x31910`

## callees

- `0x1eb0`
- `0x1fb0`
- `0x6ac0`
- `0x6b00`
- `0x6b20`
- `0x6b40`

## pseudocode

```c

```

## disassembly

```asm
0x1eb0  ldarg.0
0x1eb1  ldarg.0
0x1eb2  ldfld    int32 Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentMemberIndex
0x1eb7  ldc.i4.1
0x1eb8  add
0x1eb9  stfld    int32 Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentMemberIndex
0x1ebe  ldarg.0
0x1ebf  ldfld    int32 Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentMemberIndex
0x1ec4  ldarg.0
0x1ec5  ldfld    int32 Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentMemberInfoCount
0x1eca  bge.s    loc_1F28
0x1ecc  ldarg.0
0x1ecd  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentPersistedDeclaration
0x1ed2  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration::get_HasSkippedMembers()
0x1ed7  brfalse.s loc_1F0A
0x1ed9  ldarg.0
0x1eda  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentPersistedDeclaration
0x1edf  ldarg.0
0x1ee0  ldfld    int32 Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentMemberIndex
0x1ee5  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration::IsMemberSkipped(int32 index)
0x1eea  brfalse.s loc_1F0A
0x1eec  ldarg.0
0x1eed  ldarg.0
0x1eee  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentPersistedDeclaration
0x1ef3  ldarg.0
0x1ef4  ldfld    int32 Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentMemberIndex
0x1ef9  callvirt instance int32 Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration::MembersToSkip(int32 index)
0x1efe  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::SkipMembers(int32 toSkip)
0x1f03  ldarg.0
0x1f04  call     instance bool Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::NextMember()
0x1f09  ret
0x1f0a  ldarg.0
0x1f0b  ldarg.0
0x1f0c  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentPersistedDeclaration
0x1f11  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo> Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration::get_MemberInfoList()
0x1f16  ldarg.0
0x1f17  ldfld    int32 Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentMemberIndex
0x1f1c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo>::get_Item(!!T0)
0x1f21  stfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentMember
0x1f26  ldc.i4.1
0x1f27  ret
0x1f28  ldc.i4.0
0x1f29  ret
```
