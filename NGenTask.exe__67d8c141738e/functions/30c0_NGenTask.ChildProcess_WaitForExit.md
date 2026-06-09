# NGenTask.ChildProcess::WaitForExit

- ea: `0x30c0`
- end: `0x30c8`
- name: `NGenTask.ChildProcess::WaitForExit`
- size: `8`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1560`
- `0x2790`

## callees

- `0x30d0`

## pseudocode

```c

```

## disassembly

```asm
0x30c0  ldarg.0
0x30c1  ldc.i4.m1
0x30c2  call     instance bool NGenTask.ChildProcess::WaitForExit(int32 timeout)
0x30c7  ret
```
