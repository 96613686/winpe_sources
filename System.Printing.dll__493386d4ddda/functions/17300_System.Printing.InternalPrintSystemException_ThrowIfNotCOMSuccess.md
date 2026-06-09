# System.Printing.InternalPrintSystemException::ThrowIfNotCOMSuccess

- ea: `0x17300`
- end: `0x17315`
- name: `System.Printing.InternalPrintSystemException::ThrowIfNotCOMSuccess`
- size: `21`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x7480`
- `0x76f0`
- `0x77a0`

## callees

- `0x17270`
- `0x17300`

## pseudocode

```c

```

## disassembly

```asm
0x17300  ldarg.0
0x17301  ldc.i4.0
0x17302  bge.s    loc_17314
0x17304  ldc.i4.0
0x17305  newobj   instance void System.Printing.InternalPrintSystemException::.ctor(int32 lastWin32Error)
0x1730a  stloc.0
0x1730b  ldloc.0
0x1730c  ldarg.0
0x1730d  stfld    int32 System.Printing.InternalPrintSystemException::hresult
0x17312  ldloc.0
0x17313  throw
0x17314  ret
```
