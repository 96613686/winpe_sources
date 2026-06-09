# ::Microsoft.Internal.GDIExporter.CopyToMemoryStream

- ea: `0x1680`
- end: `0x16c0`
- name: `::Microsoft.Internal.GDIExporter.CopyToMemoryStream`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x228a0`

## callees

- `0x1680`

## pseudocode

```c

```

## disassembly

```asm
0x1680  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x1685  stloc.2
0x1686  ldc.i4   0x8000
0x168b  newarr   [mscorlib]System.Byte
0x1690  stloc.1
0x1691  ldarg.0
0x1692  ldloc.1
0x1693  ldc.i4.0
0x1694  ldc.i4   0x8000
0x1699  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x169e  stloc.0
0x169f  ldloc.0
0x16a0  ldc.i4.0
0x16a1  ble.s    loc_16BE
0x16a3  ldloc.2
0x16a4  ldloc.1
0x16a5  ldc.i4.0
0x16a6  ldloc.0
0x16a7  callvirt instance void [mscorlib]System.IO.MemoryStream::Write(unsigned int8[], int32, int32)
0x16ac  ldarg.0
0x16ad  ldloc.1
0x16ae  ldc.i4.0
0x16af  ldc.i4   0x8000
0x16b4  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x16b9  stloc.0
0x16ba  ldloc.0
0x16bb  ldc.i4.0
0x16bc  bgt.s    loc_16A3
0x16be  ldloc.2
0x16bf  ret
```
