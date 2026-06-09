# NGenTask.AppDataDirectoryWalker::.ctor

- ea: `0x3f80`
- end: `0x3fac`
- name: `NGenTask.AppDataDirectoryWalker::.ctor`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x310`

## pseudocode

```c

```

## disassembly

```asm
0x3f80  ldarg.0
0x3f81  call     instance void [mscorlib]System.Object::.ctor()
0x3f86  ldarg.0
0x3f87  ldarg.1
0x3f88  stfld    class NGenTask.TaskExecutive NGenTask.AppDataDirectoryWalker::m_task
0x3f8d  ldarg.0
0x3f8e  ldarg.2
0x3f8f  stfld    bool NGenTask.AppDataDirectoryWalker::m_userLocal
0x3f94  ldarg.0
0x3f95  ldarg.3
0x3f96  stfld    string NGenTask.AppDataDirectoryWalker::m_version
0x3f9b  ldarg.0
0x3f9c  ldarg.s  4
0x3f9e  stfld    class NGenTask.ContainerDirectoryInfo NGenTask.AppDataDirectoryWalker::m_logDirectoryOverride
0x3fa3  ldarg.0
0x3fa4  ldarg.s  5
0x3fa6  stfld    class NGenTask.ContainerDirectoryInfo NGenTask.AppDataDirectoryWalker::m_niDirectoryOverride
0x3fab  ret
```
