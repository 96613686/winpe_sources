# Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Round1

- ea: `0x4a0`
- end: `0x803`
- name: `Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Round1`
- size: `867`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x3e0`

## callees

- `0x470`
- `0xfe0`

## pseudocode

```c

```

## disassembly

```asm
0x4a0  ldc.i4.s 0x10
0x4a2  ldarg.1
0x4a3  mul
0x4a4  stloc.0
0x4a5  ldarg.0
0x4a6  ldarg.0
0x4a7  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x4ac  ldarg.0
0x4ad  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x4b2  ldarg.0
0x4b3  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x4b8  ldarg.0
0x4b9  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x4be  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::F(int32 x, int32 y, int32 z)
0x4c3  add
0x4c4  ldarg.0
0x4c5  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0x4ca  ldloc.0
0x4cb  ldelem.i4
0x4cc  add
0x4cd  ldc.i4.3
0x4ce  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0x4d3  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x4d8  ldarg.0
0x4d9  ldarg.0
0x4da  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x4df  ldarg.0
0x4e0  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x4e5  ldarg.0
0x4e6  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x4eb  ldarg.0
0x4ec  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x4f1  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::F(int32 x, int32 y, int32 z)
0x4f6  add
0x4f7  ldarg.0
0x4f8  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0x4fd  ldc.i4.1
0x4fe  ldloc.0
0x4ff  add
0x500  ldelem.i4
0x501  add
0x502  ldc.i4.7
0x503  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0x508  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x50d  ldarg.0
0x50e  ldarg.0
0x50f  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x514  ldarg.0
0x515  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x51a  ldarg.0
0x51b  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x520  ldarg.0
0x521  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x526  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::F(int32 x, int32 y, int32 z)
0x52b  add
0x52c  ldarg.0
0x52d  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0x532  ldc.i4.2
0x533  ldloc.0
0x534  add
0x535  ldelem.i4
0x536  add
0x537  ldc.i4.s 0xB
0x539  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0x53e  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x543  ldarg.0
0x544  ldarg.0
0x545  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x54a  ldarg.0
0x54b  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x550  ldarg.0
0x551  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x556  ldarg.0
0x557  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x55c  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::F(int32 x, int32 y, int32 z)
0x561  add
0x562  ldarg.0
0x563  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0x568  ldc.i4.3
0x569  ldloc.0
0x56a  add
0x56b  ldelem.i4
0x56c  add
0x56d  ldc.i4.s 0x13
0x56f  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0x574  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x579  ldarg.0
0x57a  ldarg.0
0x57b  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x580  ldarg.0
0x581  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x586  ldarg.0
0x587  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x58c  ldarg.0
0x58d  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x592  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::F(int32 x, int32 y, int32 z)
0x597  add
0x598  ldarg.0
0x599  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0x59e  ldc.i4.4
0x59f  ldloc.0
0x5a0  add
0x5a1  ldelem.i4
0x5a2  add
0x5a3  ldc.i4.3
0x5a4  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0x5a9  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x5ae  ldarg.0
0x5af  ldarg.0
0x5b0  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x5b5  ldarg.0
0x5b6  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x5bb  ldarg.0
0x5bc  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x5c1  ldarg.0
0x5c2  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x5c7  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::F(int32 x, int32 y, int32 z)
0x5cc  add
0x5cd  ldarg.0
0x5ce  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0x5d3  ldc.i4.5
0x5d4  ldloc.0
0x5d5  add
0x5d6  ldelem.i4
0x5d7  add
0x5d8  ldc.i4.7
0x5d9  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0x5de  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x5e3  ldarg.0
0x5e4  ldarg.0
0x5e5  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x5ea  ldarg.0
0x5eb  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x5f0  ldarg.0
0x5f1  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x5f6  ldarg.0
0x5f7  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x5fc  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::F(int32 x, int32 y, int32 z)
0x601  add
0x602  ldarg.0
0x603  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0x608  ldc.i4.6
0x609  ldloc.0
0x60a  add
0x60b  ldelem.i4
0x60c  add
0x60d  ldc.i4.s 0xB
0x60f  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0x614  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x619  ldarg.0
0x61a  ldarg.0
0x61b  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x620  ldarg.0
0x621  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x626  ldarg.0
0x627  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x62c  ldarg.0
0x62d  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x632  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::F(int32 x, int32 y, int32 z)
0x637  add
0x638  ldarg.0
0x639  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0x63e  ldc.i4.7
0x63f  ldloc.0
0x640  add
0x641  ldelem.i4
0x642  add
0x643  ldc.i4.s 0x13
0x645  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0x64a  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x64f  ldarg.0
0x650  ldarg.0
0x651  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x656  ldarg.0
0x657  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x65c  ldarg.0
0x65d  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x662  ldarg.0
0x663  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x668  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::F(int32 x, int32 y, int32 z)
0x66d  add
0x66e  ldarg.0
0x66f  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0x674  ldc.i4.8
0x675  ldloc.0
0x676  add
0x677  ldelem.i4
0x678  add
0x679  ldc.i4.3
0x67a  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0x67f  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x684  ldarg.0
0x685  ldarg.0
0x686  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x68b  ldarg.0
0x68c  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x691  ldarg.0
0x692  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x697  ldarg.0
0x698  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x69d  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::F(int32 x, int32 y, int32 z)
0x6a2  add
0x6a3  ldarg.0
0x6a4  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0x6a9  ldc.i4.s 9
0x6ab  ldloc.0
0x6ac  add
0x6ad  ldelem.i4
0x6ae  add
0x6af  ldc.i4.7
0x6b0  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0x6b5  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x6ba  ldarg.0
0x6bb  ldarg.0
0x6bc  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x6c1  ldarg.0
0x6c2  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x6c7  ldarg.0
0x6c8  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x6cd  ldarg.0
0x6ce  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x6d3  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::F(int32 x, int32 y, int32 z)
0x6d8  add
0x6d9  ldarg.0
0x6da  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0x6df  ldc.i4.s 0xA
0x6e1  ldloc.0
0x6e2  add
0x6e3  ldelem.i4
0x6e4  add
0x6e5  ldc.i4.s 0xB
0x6e7  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0x6ec  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x6f1  ldarg.0
0x6f2  ldarg.0
0x6f3  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x6f8  ldarg.0
0x6f9  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x6fe  ldarg.0
0x6ff  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x704  ldarg.0
0x705  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x70a  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::F(int32 x, int32 y, int32 z)
0x70f  add
0x710  ldarg.0
0x711  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0x716  ldc.i4.s 0xB
0x718  ldloc.0
0x719  add
0x71a  ldelem.i4
0x71b  add
0x71c  ldc.i4.s 0x13
0x71e  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0x723  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x728  ldarg.0
0x729  ldarg.0
0x72a  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x72f  ldarg.0
0x730  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x735  ldarg.0
0x736  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x73b  ldarg.0
0x73c  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x741  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::F(int32 x, int32 y, int32 z)
0x746  add
0x747  ldarg.0
0x748  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0x74d  ldc.i4.s 0xC
0x74f  ldloc.0
0x750  add
0x751  ldelem.i4
0x752  add
0x753  ldc.i4.3
0x754  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0x759  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x75e  ldarg.0
0x75f  ldarg.0
0x760  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x765  ldarg.0
0x766  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_a
0x76b  ldarg.0
0x76c  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_b
0x771  ldarg.0
0x772  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x777  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::F(int32 x, int32 y, int32 z)
0x77c  add
0x77d  ldarg.0
0x77e  ldfld    int32[] Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_dd
0x783  ldc.i4.s 0xD
0x785  ldloc.0
0x786  add
0x787  ldelem.i4
0x788  add
0x789  ldc.i4.7
0x78a  call     int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::Rotintlft(int32 val, int32 numbits)
0x78f  stfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_d
0x794  ldarg.0
0x795  ldarg.0
0x796  ldfld    int32 Microsoft.ReportingServices.LegacyOfficeRender.OfficeImageHasher::m_c
0x79b  ldarg.0
  ... truncated ...
```
