# NGenTask.ChildProcess::ReleaseHandle

- ea: `0x3090`
- end: `0x309c`
- name: `NGenTask.ChildProcess::ReleaseHandle`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x3190`

## pseudocode

```c

```

## disassembly

```asm
0x3090  ldarg.0
0x3091  ldfld    native int [mscorlib]System.Runtime.InteropServices.SafeHandle::handle
0x3096  call     bool NGenTask.Win32Native::CloseHandle(native int handle)
0x309b  ret
```
