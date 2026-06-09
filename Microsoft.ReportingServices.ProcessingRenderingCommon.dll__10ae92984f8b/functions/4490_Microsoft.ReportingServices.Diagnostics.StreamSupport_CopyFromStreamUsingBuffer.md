# Microsoft.ReportingServices.Diagnostics.StreamSupport::CopyFromStreamUsingBuffer

- ea: `0x4490`
- end: `0x451a`
- name: `Microsoft.ReportingServices.Diagnostics.StreamSupport::CopyFromStreamUsingBuffer`
- size: `138`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x4350`
- `0x4490`

## string_xrefs

- `0x44ab`: `Buffers size is non optimal size for copying streams`
- `0x44fe`: `unexpected number of bytes to copy ({0})`

## pseudocode

```c

```

## disassembly

```asm
0x4490  ldarg.2
0x4491  stloc.0
0x4492  ldarg.3
0x4493  ldc.i4.0
0x4494  bgt.s    loc_449D
0x4496  ldc.i4   0x400
0x449b  starg.s  3
0x449d  ldarg.3
0x449e  call     int32 Microsoft.ReportingServices.Diagnostics.StreamSupport::get_MemoryBufferLimit()
0x44a3  ble.s    loc_44B5
0x44a5  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x44aa  ldc.i4.0
0x44ab  ldstr    aBuffersSizeIsN// "Buffers size is non optimal size for co"...
0x44b0  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x44b5  ldarg.3
0x44b6  newarr   [mscorlib]System.Byte
0x44bb  stloc.1
0x44bc  ldc.i4.0
0x44bd  stloc.2
0x44be  ldloc.1
0x44bf  ldlen
0x44c0  conv.i4
0x44c1  stloc.3
0x44c2  ldc.i4.0
0x44c3  conv.i8
0x44c4  stloc.s  4
0x44c6  ldloc.3
0x44c7  conv.i8
0x44c8  ldloc.0
0x44c9  ble.s    loc_44CE
0x44cb  ldloc.0
0x44cc  conv.i4
0x44cd  stloc.3
0x44ce  ldarg.0
0x44cf  ldloc.1
0x44d0  ldc.i4.0
0x44d1  ldloc.3
0x44d2  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x44d7  stloc.2
0x44d8  ldloc.2
0x44d9  ldc.i4.0
0x44da  ble.s    loc_44F1
0x44dc  ldarg.1
0x44dd  ldloc.1
0x44de  ldc.i4.0
0x44df  ldloc.2
0x44e0  callvirt instance void [mscorlib]System.IO.Stream::Write(unsigned int8[], int32, int32)
0x44e5  ldloc.s  4
0x44e7  ldloc.2
0x44e8  conv.i8
0x44e9  add
0x44ea  stloc.s  4
0x44ec  ldloc.0
0x44ed  ldloc.2
0x44ee  conv.i8
0x44ef  sub
0x44f0  stloc.0
0x44f1  ldloc.2
0x44f2  ldc.i4.0
0x44f3  bgt.s    loc_44C6
0x44f5  ldloc.0
0x44f6  brfalse.s loc_4517
0x44f8  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x44fd  ldc.i4.0
0x44fe  ldstr    aUnexpectedNumb// "unexpected number of bytes to copy ({0}"...
0x4503  ldc.i4.1
0x4504  newarr   [mscorlib]System.Object
0x4509  dup
0x450a  ldc.i4.0
0x450b  ldloc.0
0x450c  box      [mscorlib]System.Int64
0x4511  stelem.ref
0x4512  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string, object[])
0x4517  ldloc.s  4
0x4519  ret
```
