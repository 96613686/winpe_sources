# NGenTask.TaskExecutive::IsStopRequested

- ea: `0x2530`
- end: `0x2539`
- name: `NGenTask.TaskExecutive::IsStopRequested`
- size: `9`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x3f10`
- `0x3fb0`

## pseudocode

```c

```

## disassembly

```asm
0x2530  ldarg.0
0x2531  volatile.
0x2533  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool NGenTask.TaskExecutive::m_stopRequested
0x2538  ret
```
