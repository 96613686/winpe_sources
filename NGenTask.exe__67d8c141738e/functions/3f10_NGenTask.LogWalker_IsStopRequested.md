# NGenTask.LogWalker::IsStopRequested

- ea: `0x3f10`
- end: `0x3f1c`
- name: `NGenTask.LogWalker::IsStopRequested`
- size: `12`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x4130`
- `0x4270`

## callees

- `0x2530`

## pseudocode

```c

```

## disassembly

```asm
0x3f10  ldarg.0
0x3f11  ldfld    class NGenTask.TaskExecutive NGenTask.LogWalker::m_task
0x3f16  callvirt instance bool NGenTask.TaskExecutive::IsStopRequested()
0x3f1b  ret
```
