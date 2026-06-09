# NGenTask.AppDataDirectoryWalker::IsStopRequested

- ea: `0x3fb0`
- end: `0x3fbc`
- name: `NGenTask.AppDataDirectoryWalker::IsStopRequested`
- size: `12`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x45f0`
- `0x4980`
- `0x4dc0`
- `0x4fe0`
- `0x5310`

## callees

- `0x2530`

## pseudocode

```c

```

## disassembly

```asm
0x3fb0  ldarg.0
0x3fb1  ldfld    class NGenTask.TaskExecutive NGenTask.AppDataDirectoryWalker::m_task
0x3fb6  callvirt instance bool NGenTask.TaskExecutive::IsStopRequested()
0x3fbb  ret
```
