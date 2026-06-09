# Microsoft.ReportingServices.Library.SQLScheduleParameters::GetStartMonthDate

- ea: `0x4cc0`
- end: `0x4d99`
- name: `Microsoft.ReportingServices.Library.SQLScheduleParameters::GetStartMonthDate`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5330`

## callees

- `0x4cc0`

## pseudocode

```c

```

## disassembly

```asm
0x4cc0  ldc.i4.0
0x4cc1  stloc.0
0x4cc2  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x4cc7  stloc.1
0x4cc8  ldarg.1
0x4cc9  ldc.i4.s 0x40
0x4ccb  bgt.s    loc_4D00
0x4ccd  ldarg.1
0x4cce  ldc.i4.8
0x4ccf  bgt.s    loc_4CEF
0x4cd1  ldarg.1
0x4cd2  ldc.i4.1
0x4cd3  sub
0x4cd4  switch   loc_4D34, loc_4D38, loc_4D66, loc_4D3C
0x4ce9  ldarg.1
0x4cea  ldc.i4.8
0x4ceb  beq.s    loc_4D40
0x4ced  br.s     loc_4D66
0x4cef  ldarg.1
0x4cf0  ldc.i4.s 0x10
0x4cf2  beq.s    loc_4D44
0x4cf4  ldarg.1
0x4cf5  ldc.i4.s 0x20
0x4cf7  beq.s    loc_4D48
0x4cf9  ldarg.1
0x4cfa  ldc.i4.s 0x40
0x4cfc  beq.s    loc_4D4C
0x4cfe  br.s     loc_4D66
0x4d00  ldarg.1
0x4d01  ldc.i4   0x100
0x4d06  bgt.s    loc_4D1A
0x4d08  ldarg.1
0x4d09  ldc.i4   0x80
0x4d0e  beq.s    loc_4D50
0x4d10  ldarg.1
0x4d11  ldc.i4   0x100
0x4d16  beq.s    loc_4D54
0x4d18  br.s     loc_4D66
0x4d1a  ldarg.1
0x4d1b  ldc.i4   0x200
0x4d20  beq.s    loc_4D59
0x4d22  ldarg.1
0x4d23  ldc.i4   0x400
0x4d28  beq.s    loc_4D5E
0x4d2a  ldarg.1
0x4d2b  ldc.i4   0x800
0x4d30  beq.s    loc_4D63
0x4d32  br.s     loc_4D66
0x4d34  ldc.i4.1
0x4d35  stloc.0
0x4d36  br.s     loc_4D66
0x4d38  ldc.i4.2
0x4d39  stloc.0
0x4d3a  br.s     loc_4D66
0x4d3c  ldc.i4.3
0x4d3d  stloc.0
0x4d3e  br.s     loc_4D66
0x4d40  ldc.i4.4
0x4d41  stloc.0
0x4d42  br.s     loc_4D66
0x4d44  ldc.i4.5
0x4d45  stloc.0
0x4d46  br.s     loc_4D66
0x4d48  ldc.i4.6
0x4d49  stloc.0
0x4d4a  br.s     loc_4D66
0x4d4c  ldc.i4.7
0x4d4d  stloc.0
0x4d4e  br.s     loc_4D66
0x4d50  ldc.i4.8
0x4d51  stloc.0
0x4d52  br.s     loc_4D66
0x4d54  ldc.i4.s 9
0x4d56  stloc.0
0x4d57  br.s     loc_4D66
0x4d59  ldc.i4.s 0xA
0x4d5b  stloc.0
0x4d5c  br.s     loc_4D66
0x4d5e  ldc.i4.s 0xB
0x4d60  stloc.0
0x4d61  br.s     loc_4D66
0x4d63  ldc.i4.s 0xC
0x4d65  stloc.0
0x4d66  ldloc.0
0x4d67  ldarga.s 2
0x4d69  call     instance int32 [mscorlib]System.DateTime::get_Month()
0x4d6e  bne.un.s loc_4D74
0x4d70  ldarg.2
0x4d71  stloc.1
0x4d72  br.s     loc_4D97
0x4d74  ldloca.s 1
0x4d76  ldarga.s 2
0x4d78  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x4d7d  ldloc.0
0x4d7e  ldc.i4.1
0x4d7f  call     instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32)
0x4d84  ldloc.0
0x4d85  ldarga.s 2
0x4d87  call     instance int32 [mscorlib]System.DateTime::get_Month()
0x4d8c  bge.s    loc_4D97
0x4d8e  ldloca.s 1
0x4d90  ldc.i4.1
0x4d91  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddYears(int32)
0x4d96  stloc.1
0x4d97  ldloc.1
0x4d98  ret
```
