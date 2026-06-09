# Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::SkipMembers

- ea: `0x1fb0`
- end: `0x21d5`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::SkipMembers`
- size: `549`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x1eb0`
- `0x23f0`

## callees

- `0xf60`
- `0x1fb0`
- `0x21e0`
- `0x22d0`
- `0x2310`
- `0x2350`
- `0x2390`
- `0x23c0`
- `0x2460`
- `0x24a0`
- `0x24e0`
- `0x2520`
- `0x2570`
- `0x6930`
- `0x6940`
- `0x6ac0`
- `0x7190`
- `0x71c0`
- `0x71d0`

## pseudocode

```c

```

## disassembly

```asm
0x1fb0  ldc.i4.0
0x1fb1  stloc.0
0x1fb2  br       loc_21BF
0x1fb7  ldarg.0
0x1fb8  ldarg.0
0x1fb9  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentPersistedDeclaration
0x1fbe  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo> Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Declaration::get_MemberInfoList()
0x1fc3  ldarg.0
0x1fc4  ldfld    int32 Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentMemberIndex
0x1fc9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo>::get_Item(!!T0)
0x1fce  stfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentMember
0x1fd3  ldarg.0
0x1fd4  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentMember
0x1fd9  callvirt instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo::get_ObjectType()
0x1fde  stloc.1
0x1fdf  ldloc.1
0x1fe0  switch   loc_21AD, loc_2179, loc_20FF, loc_2123, loc_2141, loc_2149, loc_2022, loc_2151, loc_218C, loc_218C, loc_2171, loc_2159, loc_2161, loc_2169
0x201d  br       loc_218C
0x2022  ldarg.0
0x2023  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentMember
0x2028  callvirt instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo::get_Token()
0x202d  stloc.2
0x202e  ldloc.2
0x202f  ldc.i4   0xED
0x2034  sub
0x2035  switch   loc_20CC, loc_20EF, loc_20CC, loc_20EF, loc_20BB, loc_20BB, loc_2099, loc_20EF, loc_2099, loc_20AA, loc_20BB, loc_2099, loc_20AA, loc_20BB, loc_2088, loc_2088, loc_20AA, loc_20BB, loc_20DE
0x2086  br.s     loc_20EF
0x2088  ldarg.0
0x2089  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x208e  ldc.i4.1
0x208f  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::SkipTypedArray(int32 elementSize)
0x2094  br       loc_21AD
0x2099  ldarg.0
0x209a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x209f  ldc.i4.2
0x20a0  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::SkipTypedArray(int32 elementSize)
0x20a5  br       loc_21AD
0x20aa  ldarg.0
0x20ab  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x20b0  ldc.i4.4
0x20b1  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::SkipTypedArray(int32 elementSize)
0x20b6  br       loc_21AD
0x20bb  ldarg.0
0x20bc  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x20c1  ldc.i4.8
0x20c2  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::SkipTypedArray(int32 elementSize)
0x20c7  br       loc_21AD
0x20cc  ldarg.0
0x20cd  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x20d2  ldc.i4.s 0x10
0x20d4  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::SkipBytes(int32 bytesToSkip)
0x20d9  br       loc_21AD
0x20de  ldarg.0
0x20df  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x20e4  callvirt instance valuetype [mscorlib]System.Decimal [mscorlib]System.IO.BinaryReader::ReadDecimal()
0x20e9  pop
0x20ea  br       loc_21AD
0x20ef  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::get_Tracer()
0x20f4  ldc.i4.0
0x20f5  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool)
0x20fa  br       loc_21AD
0x20ff  ldarg.0
0x2100  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentMember
0x2105  callvirt instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo::get_Token()
0x210a  ldc.i4.2
0x210b  bne.un.s loc_2118
0x210d  ldarg.0
0x210e  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::SkipListOrArrayOfReferences()
0x2113  br       loc_21AD
0x2118  ldarg.0
0x2119  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::SkipListOrArrayOfRIFObjects()
0x211e  br       loc_21AD
0x2123  ldarg.0
0x2124  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentMember
0x2129  callvirt instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo::get_Token()
0x212e  ldc.i4.2
0x212f  bne.un.s loc_2139
0x2131  ldarg.0
0x2132  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::SkipListOrArrayOfReferences()
0x2137  br.s     loc_21AD
0x2139  ldarg.0
0x213a  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::SkipListOrArrayOfRIFObjects()
0x213f  br.s     loc_21AD
0x2141  ldarg.0
0x2142  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::SkipArrayOfPrimitives()
0x2147  br.s     loc_21AD
0x2149  ldarg.0
0x214a  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::SkipListOfPrimitives()
0x214f  br.s     loc_21AD
0x2151  ldarg.0
0x2152  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::SkipStringRIFObjectDictionary()
0x2157  br.s     loc_21AD
0x2159  ldarg.0
0x215a  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::SkipInt32PrimitiveListHashtable()
0x215f  br.s     loc_21AD
0x2161  ldarg.0
0x2162  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::SkipObjectHashtableHashtable()
0x2167  br.s     loc_21AD
0x2169  ldarg.0
0x216a  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::SkipStringObjectHashtable()
0x216f  br.s     loc_21AD
0x2171  ldarg.0
0x2172  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::SkipInt32RIFObjectDictionary()
0x2177  br.s     loc_21AD
0x2179  ldarg.0
0x217a  ldarg.0
0x217b  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentMember
0x2180  callvirt instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo::get_Token()
0x2185  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::SkipPrimitive(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token token)
0x218a  br.s     loc_21AD
0x218c  ldarg.0
0x218d  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentMember
0x2192  callvirt instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.Token Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.MemberInfo::get_Token()
0x2197  ldc.i4.2
0x2198  bne.un.s loc_21A7
0x219a  ldarg.0
0x219b  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_reader
0x21a0  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::SkipMultiByteInt()
0x21a5  br.s     loc_21AD
0x21a7  ldarg.0
0x21a8  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::SkipRIFObject()
0x21ad  ldarg.0
0x21ae  ldarg.0
0x21af  ldfld    int32 Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentMemberIndex
0x21b4  ldc.i4.1
0x21b5  add
0x21b6  stfld    int32 Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentMemberIndex
0x21bb  ldloc.0
0x21bc  ldc.i4.1
0x21bd  add
0x21be  stloc.0
0x21bf  ldloc.0
0x21c0  ldarg.1
0x21c1  blt      loc_1FB7
0x21c6  ldarg.0
0x21c7  ldarg.0
0x21c8  ldfld    int32 Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentMemberIndex
0x21cd  ldc.i4.1
0x21ce  sub
0x21cf  stfld    int32 Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::m_currentMemberIndex
0x21d4  ret
```
