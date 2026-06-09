# Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Calc

- ea: `0x3e0`
- end: `0x465`
- name: `Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Calc`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x130`
- `0x170`

## callees

- `0x3e0`
- `0x4a0`
- `0x810`
- `0xbe0`

## pseudocode

```c

```

## disassembly

```asm
0x3e0  ldc.i4.0
0x3e1  stloc.s  4
0x3e3  br.s     loc_457
0x3e5  ldarg.0
0x3e6  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x3eb  stloc.0
0x3ec  ldarg.0
0x3ed  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x3f2  stloc.1
0x3f3  ldarg.0
0x3f4  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x3f9  stloc.2
0x3fa  ldarg.0
0x3fb  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x400  stloc.3
0x401  ldarg.0
0x402  ldloc.s  4
0x404  call     instance void Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Round1(int32 blk)
0x409  ldarg.0
0x40a  ldloc.s  4
0x40c  call     instance void Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Round2(int32 blk)
0x411  ldarg.0
0x412  ldloc.s  4
0x414  call     instance void Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Round3(int32 blk)
0x419  ldarg.0
0x41a  ldarg.0
0x41b  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x420  ldloc.0
0x421  add
0x422  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x427  ldarg.0
0x428  ldarg.0
0x429  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x42e  ldloc.1
0x42f  add
0x430  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x435  ldarg.0
0x436  ldarg.0
0x437  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x43c  ldloc.2
0x43d  add
0x43e  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x443  ldarg.0
0x444  ldarg.0
0x445  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x44a  ldloc.3
0x44b  add
0x44c  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x451  ldloc.s  4
0x453  ldc.i4.1
0x454  add
0x455  stloc.s  4
0x457  ldloc.s  4
0x459  ldarg.0
0x45a  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_numwords
0x45f  ldc.i4.s 0x10
0x461  div
0x462  blt.s    loc_3E5
0x464  ret
```
