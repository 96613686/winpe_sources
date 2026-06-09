# Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::RegisterDeclaration

- ea: `0x4070`
- end: `0x40b4`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::RegisterDeclaration`
- size: `68`
- prototype: ``
- caller_count: `57`
- callee_count: `4`
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

- `0x3ff0`
- `0x4070`
- `0x6ac0`
- `0x6ad0`

## pseudocode

```c

```

## disassembly

```asm
0x4070  ldarg.0
0x4071  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType, class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration> Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_writtenDecls
0x4076  ldarg.1
0x4077  callvirt instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration::get_ObjectType()
0x407c  ldloca.s 0
0x407e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType, class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration>::TryGetValue(var<u1>, !!T0)
0x4083  brtrue.s loc_408D
0x4085  ldarg.0
0x4086  ldarg.1
0x4087  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::WriteDeclaration(class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration decl)
0x408c  stloc.0
0x408d  ldarg.0
0x408e  ldloc.0
0x408f  stfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_currentDeclaration
0x4094  ldarg.0
0x4095  ldarg.0
0x4096  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_currentDeclaration
0x409b  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo> Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration::get_MemberInfoList()
0x40a0  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo>::get_Count()
0x40a5  ldc.i4.1
0x40a6  sub
0x40a7  stfld    int32 Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_lastMemberInfoIndex
0x40ac  ldarg.0
0x40ad  ldc.i4.m1
0x40ae  stfld    int32 Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatWriter::m_currentMemberIndex
0x40b3  ret
```
