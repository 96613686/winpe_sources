# NGenTask.ChildProcess::get_HasExited

- ea: `0x30e0`
- end: `0x30e8`
- name: `NGenTask.ChildProcess::get_HasExited`
- size: `8`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x10b0`

## callees

- `0x30d0`

## pseudocode

```c

```

## disassembly

```asm
0x30e0  ldarg.0
0x30e1  ldc.i4.0
0x30e2  call     instance bool NGenTask.ChildProcess::WaitForExit(int32 timeout)
0x30e7  ret
```
