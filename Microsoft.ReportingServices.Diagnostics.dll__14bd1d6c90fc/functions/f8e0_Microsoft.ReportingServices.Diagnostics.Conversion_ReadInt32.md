# Microsoft.ReportingServices.Diagnostics.Conversion::ReadInt32

- ea: `0xf8e0`
- end: `0xf910`
- name: `Microsoft.ReportingServices.Diagnostics.Conversion::ReadInt32`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xf8a0`
- `0xf8e0`

## string_xrefs

- `0xf8f3`: `Could not read 4 bytes buffer`

## pseudocode

```c

```

## disassembly

```asm
0xf8e0  ldc.i4.4
0xf8e1  newarr   [mscorlib]System.Byte
0xf8e6  stloc.0
0xf8e7  ldarg.0
0xf8e8  ldloc.0
0xf8e9  ldc.i4.0
0xf8ea  ldc.i4.4
0xf8eb  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0xf8f0  ldc.i4.4
0xf8f1  beq.s    loc_F8FE
0xf8f3  ldstr    aCouldNotRead4B// "Could not read 4 bytes buffer"
0xf8f8  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0xf8fd  throw
0xf8fe  ldloc.0
0xf8ff  ldc.i4.0
0xf900  ldelem.u1
0xf901  ldloc.0
0xf902  ldc.i4.1
0xf903  ldelem.u1
0xf904  ldloc.0
0xf905  ldc.i4.2
0xf906  ldelem.u1
0xf907  ldloc.0
0xf908  ldc.i4.3
0xf909  ldelem.u1
0xf90a  call     unsigned int32 Microsoft.ReportingServices.Diagnostics.Conversion::BytesToUInt32(unsigned int8 lowest, unsigned int8 lower, unsigned int8 higher, unsigned int8 highest)
0xf90f  ret
```
