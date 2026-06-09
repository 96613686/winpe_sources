# Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::RegisterDeclaration

- ea: `0x1e20`
- end: `0x1ea6`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::RegisterDeclaration`
- size: `134`
- prototype: ``
- caller_count: `57`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

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
- `0x31c80`

## callees

- `0x1e20`
- `0x6ac0`
- `0x6ad0`
- `0x6af0`
- `0x6b50`
- `0x7110`

## pseudocode

```c

```

## disassembly

```asm
0x1e20  ldarg.0
0x1e21  ldc.i4.m1
0x1e22  stfld    int32 Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentMemberIndex
0x1e27  ldarg.0
0x1e28  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType, class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration> Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_readDecls
0x1e2d  ldarg.1
0x1e2e  callvirt instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration::get_ObjectType()
0x1e33  ldarg.0
0x1e34  ldflda   class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentPersistedDeclaration
0x1e39  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType, class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration>::TryGetValue(var<u1>, !!T0)
0x1e3e  brtrue.s loc_1E76
0x1e40  ldarg.0
0x1e41  ldarg.0
0x1e42  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x1e47  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::ReadDeclaration()
0x1e4c  stfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentPersistedDeclaration
0x1e51  ldarg.0
0x1e52  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentPersistedDeclaration
0x1e57  ldarg.1
0x1e58  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration::RegisterCurrentDeclaration(class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration currentDeclaration)
0x1e5d  ldarg.0
0x1e5e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType, class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration> Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_readDecls
0x1e63  ldarg.1
0x1e64  callvirt instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration::get_ObjectType()
0x1e69  ldarg.0
0x1e6a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentPersistedDeclaration
0x1e6f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType, class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration>::Add(var<u1>, !!T0)
0x1e74  br.s     loc_1E8F
0x1e76  ldarg.0
0x1e77  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentPersistedDeclaration
0x1e7c  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration::get_RegisteredCurrentDeclaration()
0x1e81  brtrue.s loc_1E8F
0x1e83  ldarg.0
0x1e84  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentPersistedDeclaration
0x1e89  ldarg.1
0x1e8a  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration::RegisterCurrentDeclaration(class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration currentDeclaration)
0x1e8f  ldarg.0
0x1e90  ldarg.0
0x1e91  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentPersistedDeclaration
0x1e96  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo> Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration::get_MemberInfoList()
0x1e9b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo>::get_Count()
0x1ea0  stfld    int32 Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentMemberInfoCount
0x1ea5  ret
```
