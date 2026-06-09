# NGenTask.TaskExecutive::.ctor

- ea: `0x2960`
- end: `0x2972`
- name: `NGenTask.TaskExecutive::.ctor`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x2990`

## pseudocode

```c

```

## disassembly

```asm
0x2960  ldarg.0
0x2961  newobj   instance void [mscorlib]System.Object::.ctor()
0x2966  stfld    object NGenTask.TaskExecutive::m_stopLock
0x296b  ldarg.0
0x296c  call     instance void [mscorlib]System.Object::.ctor()
0x2971  ret
```
