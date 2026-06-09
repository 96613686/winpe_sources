# Microsoft.ReportingServices.Diagnostics.StreamSupport::CopyStreamUsingBuffer

- ea: `0x4430`
- end: `0x4483`
- name: `Microsoft.ReportingServices.Diagnostics.StreamSupport::CopyStreamUsingBuffer`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x4350`
- `0x4430`

## string_xrefs

- `0x4449`: `Buffers size is non optimal size for copying streams`

## pseudocode

```c

```

## disassembly

```asm
0x4430  ldarg.2
0x4431  ldc.i4.0
0x4432  bgt.s    loc_443B
0x4434  ldc.i4   0x400
0x4439  starg.s  2
0x443b  ldarg.2
0x443c  call     int32 Microsoft.ReportingServices.Diagnostics.StreamSupport::get_MemoryBufferLimit()
0x4441  ble.s    loc_4453
0x4443  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x4448  ldc.i4.0
0x4449  ldstr    aBuffersSizeIsN// "Buffers size is non optimal size for co"...
0x444e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x4453  ldarg.2
0x4454  newarr   [mscorlib]System.Byte
0x4459  stloc.0
0x445a  ldc.i4.0
0x445b  stloc.1
0x445c  ldc.i4.0
0x445d  conv.i8
0x445e  stloc.2
0x445f  ldarg.0
0x4460  ldloc.0
0x4461  ldc.i4.0
0x4462  ldloc.0
0x4463  ldlen
0x4464  conv.i4
0x4465  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x446a  stloc.1
0x446b  ldloc.1
0x446c  ldc.i4.0
0x446d  ble.s    loc_447D
0x446f  ldarg.1
0x4470  ldloc.0
0x4471  ldc.i4.0
0x4472  ldloc.1
0x4473  callvirt instance void [mscorlib]System.IO.Stream::Write(unsigned int8[], int32, int32)
0x4478  ldloc.2
0x4479  ldloc.1
0x447a  conv.i8
0x447b  add
0x447c  stloc.2
0x447d  ldloc.1
0x447e  ldc.i4.0
0x447f  bgt.s    loc_445F
0x4481  ldloc.2
0x4482  ret
```
