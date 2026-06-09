# Microsoft.BIServer.BIService.SafeUnmanagedMemoryHandle::.ctor_0

- ea: `0x25f0`
- end: `0x25ff`
- name: `Microsoft.BIServer.BIService.SafeUnmanagedMemoryHandle::.ctor_0`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1b00`

## pseudocode

```c

```

## disassembly

```asm
0x25f0  ldarg.0
0x25f1  ldarg.2
0x25f2  call     instance void [mscorlib]Microsoft.Win32.SafeHandles.SafeHandleZeroOrMinusOneIsInvalid::.ctor(bool)
0x25f7  ldarg.0
0x25f8  ldarg.1
0x25f9  call     instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::SetHandle(native int)
0x25fe  ret
```
