# Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Round2

- ea: `0x810`
- end: `0xbd3`
- name: `Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Round2`
- size: `963`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x3e0`

## callees

- `0x480`
- `0xfe0`

## pseudocode

```c

```

## disassembly

```asm
0x810  ldc.i4.s 0x10
0x812  ldarg.1
0x813  mul
0x814  stloc.0
0x815  ldarg.0
0x816  ldarg.0
0x817  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x81c  ldarg.0
0x81d  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x822  ldarg.0
0x823  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x828  ldarg.0
0x829  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x82e  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::G(int32 x, int32 y, int32 z)
0x833  add
0x834  ldarg.0
0x835  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0x83a  ldloc.0
0x83b  ldelem.i4
0x83c  add
0x83d  ldc.i4   0x5A827999
0x842  add
0x843  ldc.i4.3
0x844  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0x849  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x84e  ldarg.0
0x84f  ldarg.0
0x850  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x855  ldarg.0
0x856  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x85b  ldarg.0
0x85c  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x861  ldarg.0
0x862  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x867  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::G(int32 x, int32 y, int32 z)
0x86c  add
0x86d  ldarg.0
0x86e  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0x873  ldc.i4.4
0x874  ldloc.0
0x875  add
0x876  ldelem.i4
0x877  add
0x878  ldc.i4   0x5A827999
0x87d  add
0x87e  ldc.i4.5
0x87f  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0x884  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x889  ldarg.0
0x88a  ldarg.0
0x88b  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x890  ldarg.0
0x891  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x896  ldarg.0
0x897  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x89c  ldarg.0
0x89d  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x8a2  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::G(int32 x, int32 y, int32 z)
0x8a7  add
0x8a8  ldarg.0
0x8a9  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0x8ae  ldc.i4.8
0x8af  ldloc.0
0x8b0  add
0x8b1  ldelem.i4
0x8b2  add
0x8b3  ldc.i4   0x5A827999
0x8b8  add
0x8b9  ldc.i4.s 9
0x8bb  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0x8c0  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x8c5  ldarg.0
0x8c6  ldarg.0
0x8c7  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x8cc  ldarg.0
0x8cd  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x8d2  ldarg.0
0x8d3  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x8d8  ldarg.0
0x8d9  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x8de  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::G(int32 x, int32 y, int32 z)
0x8e3  add
0x8e4  ldarg.0
0x8e5  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0x8ea  ldc.i4.s 0xC
0x8ec  ldloc.0
0x8ed  add
0x8ee  ldelem.i4
0x8ef  add
0x8f0  ldc.i4   0x5A827999
0x8f5  add
0x8f6  ldc.i4.s 0xD
0x8f8  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0x8fd  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x902  ldarg.0
0x903  ldarg.0
0x904  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x909  ldarg.0
0x90a  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x90f  ldarg.0
0x910  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x915  ldarg.0
0x916  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x91b  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::G(int32 x, int32 y, int32 z)
0x920  add
0x921  ldarg.0
0x922  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0x927  ldc.i4.1
0x928  ldloc.0
0x929  add
0x92a  ldelem.i4
0x92b  add
0x92c  ldc.i4   0x5A827999
0x931  add
0x932  ldc.i4.3
0x933  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0x938  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x93d  ldarg.0
0x93e  ldarg.0
0x93f  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x944  ldarg.0
0x945  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x94a  ldarg.0
0x94b  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x950  ldarg.0
0x951  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x956  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::G(int32 x, int32 y, int32 z)
0x95b  add
0x95c  ldarg.0
0x95d  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0x962  ldc.i4.5
0x963  ldloc.0
0x964  add
0x965  ldelem.i4
0x966  add
0x967  ldc.i4   0x5A827999
0x96c  add
0x96d  ldc.i4.5
0x96e  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0x973  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x978  ldarg.0
0x979  ldarg.0
0x97a  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x97f  ldarg.0
0x980  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x985  ldarg.0
0x986  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x98b  ldarg.0
0x98c  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x991  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::G(int32 x, int32 y, int32 z)
0x996  add
0x997  ldarg.0
0x998  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0x99d  ldc.i4.s 9
0x99f  ldloc.0
0x9a0  add
0x9a1  ldelem.i4
0x9a2  add
0x9a3  ldc.i4   0x5A827999
0x9a8  add
0x9a9  ldc.i4.s 9
0x9ab  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0x9b0  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x9b5  ldarg.0
0x9b6  ldarg.0
0x9b7  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x9bc  ldarg.0
0x9bd  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x9c2  ldarg.0
0x9c3  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x9c8  ldarg.0
0x9c9  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x9ce  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::G(int32 x, int32 y, int32 z)
0x9d3  add
0x9d4  ldarg.0
0x9d5  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0x9da  ldc.i4.s 0xD
0x9dc  ldloc.0
0x9dd  add
0x9de  ldelem.i4
0x9df  add
0x9e0  ldc.i4   0x5A827999
0x9e5  add
0x9e6  ldc.i4.s 0xD
0x9e8  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0x9ed  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x9f2  ldarg.0
0x9f3  ldarg.0
0x9f4  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x9f9  ldarg.0
0x9fa  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x9ff  ldarg.0
0xa00  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0xa05  ldarg.0
0xa06  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0xa0b  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::G(int32 x, int32 y, int32 z)
0xa10  add
0xa11  ldarg.0
0xa12  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0xa17  ldc.i4.2
0xa18  ldloc.0
0xa19  add
0xa1a  ldelem.i4
0xa1b  add
0xa1c  ldc.i4   0x5A827999
0xa21  add
0xa22  ldc.i4.3
0xa23  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0xa28  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0xa2d  ldarg.0
0xa2e  ldarg.0
0xa2f  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0xa34  ldarg.0
0xa35  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0xa3a  ldarg.0
0xa3b  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0xa40  ldarg.0
0xa41  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0xa46  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::G(int32 x, int32 y, int32 z)
0xa4b  add
0xa4c  ldarg.0
0xa4d  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0xa52  ldc.i4.6
0xa53  ldloc.0
0xa54  add
0xa55  ldelem.i4
0xa56  add
0xa57  ldc.i4   0x5A827999
0xa5c  add
0xa5d  ldc.i4.5
0xa5e  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0xa63  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0xa68  ldarg.0
0xa69  ldarg.0
0xa6a  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0xa6f  ldarg.0
0xa70  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0xa75  ldarg.0
0xa76  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0xa7b  ldarg.0
0xa7c  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0xa81  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::G(int32 x, int32 y, int32 z)
0xa86  add
0xa87  ldarg.0
0xa88  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0xa8d  ldc.i4.s 0xA
0xa8f  ldloc.0
0xa90  add
0xa91  ldelem.i4
0xa92  add
0xa93  ldc.i4   0x5A827999
0xa98  add
0xa99  ldc.i4.s 9
0xa9b  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0xaa0  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0xaa5  ldarg.0
0xaa6  ldarg.0
0xaa7  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0xaac  ldarg.0
0xaad  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0xab2  ldarg.0
0xab3  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0xab8  ldarg.0
0xab9  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0xabe  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::G(int32 x, int32 y, int32 z)
0xac3  add
0xac4  ldarg.0
0xac5  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0xaca  ldc.i4.s 0xE
0xacc  ldloc.0
0xacd  add
0xace  ldelem.i4
0xacf  add
0xad0  ldc.i4   0x5A827999
0xad5  add
0xad6  ldc.i4.s 0xD
0xad8  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0xadd  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0xae2  ldarg.0
0xae3  ldarg.0
0xae4  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0xae9  ldarg.0
0xaea  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0xaef  ldarg.0
0xaf0  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0xaf5  ldarg.0
0xaf6  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0xafb  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::G(int32 x, int32 y, int32 z)
0xb00  add
0xb01  ldarg.0
0xb02  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0xb07  ldc.i4.3
0xb08  ldloc.0
0xb09  add
0xb0a  ldelem.i4
0xb0b  add
0xb0c  ldc.i4   0x5A827999
0xb11  add
0xb12  ldc.i4.3
0xb13  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
  ... truncated ...
```
