# NGenTask.ChildProcess::WaitForExit_0

- ea: `0x30d0`
- end: `0x30e0`
- name: `NGenTask.ChildProcess::WaitForExit_0`
- size: `16`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x10b0`
- `0x30c0`
- `0x30e0`

## callees

- `0x31f0`

## pseudocode

```c

```

## disassembly

```asm
0x30d0  ldarg.0
0x30d1  ldfld    native int [mscorlib]System.Runtime.InteropServices.SafeHandle::handle
0x30d6  ldarg.1
0x30d7  call     int32 NGenTask.Win32Native::WaitForSingleObject(native int handle, int32 timeout)
0x30dc  ldc.i4.0
0x30dd  ceq
0x30df  ret
```
