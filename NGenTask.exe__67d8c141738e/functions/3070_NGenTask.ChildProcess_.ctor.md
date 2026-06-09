# NGenTask.ChildProcess::.ctor

- ea: `0x3070`
- end: `0x3086`
- name: `NGenTask.ChildProcess::.ctor`
- size: `22`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1560`
- `0x2790`

## callees

- `0x3120`

## pseudocode

```c

```

## disassembly

```asm
0x3070  ldarg.0
0x3071  ldc.i4.1
0x3072  call     instance void [mscorlib]Microsoft.Win32.SafeHandles.SafeHandleZeroOrMinusOneIsInvalid::.ctor(bool)
0x3077  ldarg.0
0x3078  ldarg.1
0x3079  call     instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::SetHandle(native int)
0x307e  ldarg.0
0x307f  ldarg.2
0x3080  call     instance void NGenTask.ChildProcess::set_Type(valuetype ProcessType value)
0x3085  ret
```
