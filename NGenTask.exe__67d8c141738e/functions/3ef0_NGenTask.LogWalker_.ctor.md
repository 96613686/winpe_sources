# NGenTask.LogWalker::.ctor

- ea: `0x3ef0`
- end: `0x3f0c`
- name: `NGenTask.LogWalker::.ctor`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x1120`
- `0x11c0`

## pseudocode

```c

```

## disassembly

```asm
0x3ef0  ldarg.0
0x3ef1  call     instance void [mscorlib]System.Object::.ctor()
0x3ef6  ldarg.0
0x3ef7  ldarg.1
0x3ef8  stfld    class NGenTask.TaskExecutive NGenTask.LogWalker::m_task
0x3efd  ldarg.0
0x3efe  ldarg.2
0x3eff  stfld    class NGenTask.ContainerDirectoryInfo NGenTask.LogWalker::m_logDirectory
0x3f04  ldarg.0
0x3f05  ldarg.3
0x3f06  stfld    float64 NGenTask.LogWalker::m_logsScavengeThreshold
0x3f0b  ret
```
