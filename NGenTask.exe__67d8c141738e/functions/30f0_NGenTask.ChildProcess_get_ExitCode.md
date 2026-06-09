# NGenTask.ChildProcess::get_ExitCode

- ea: `0x30f0`
- end: `0x3105`
- name: `NGenTask.ChildProcess::get_ExitCode`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1560`
- `0x2790`

## callees

- `0x30f0`
- `0x3210`

## pseudocode

```c

```

## disassembly

```asm
0x30f0  ldc.i4.m1
0x30f1  stloc.0
0x30f2  ldarg.0
0x30f3  ldfld    native int [mscorlib]System.Runtime.InteropServices.SafeHandle::handle
0x30f8  ldloca.s 0
0x30fa  call     bool NGenTask.Win32Native::GetExitCodeProcess(native int handle, [out] int32& exitCode)
0x30ff  brtrue.s loc_3103
0x3101  ldc.i4.m1
0x3102  ret
0x3103  ldloc.0
0x3104  ret
```
