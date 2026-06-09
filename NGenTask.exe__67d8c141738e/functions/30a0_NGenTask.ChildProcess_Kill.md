# NGenTask.ChildProcess::Kill

- ea: `0x30a0`
- end: `0x30b5`
- name: `NGenTask.ChildProcess::Kill`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x10b0`
- `0x2790`

## callees

- `0x30a0`
- `0x31e0`

## pseudocode

```c

```

## disassembly

```asm
0x30a0  ldarg.0
0x30a1  ldfld    native int [mscorlib]System.Runtime.InteropServices.SafeHandle::handle
0x30a6  ldc.i4.1
0x30a7  call     bool NGenTask.Win32Native::TerminateProcess(native int hProcess, unsigned int32 uExitCode)
0x30ac  brtrue.s loc_30B4
0x30ae  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor()
0x30b3  throw
0x30b4  ret
```
