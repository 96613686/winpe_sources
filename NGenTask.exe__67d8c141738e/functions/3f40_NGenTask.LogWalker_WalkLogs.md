# NGenTask.LogWalker::WalkLogs

- ea: `0x3f40`
- end: `0x3f48`
- name: `NGenTask.LogWalker::WalkLogs`
- size: `8`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x3790`

## callees

- `0x3f50`

## pseudocode

```c

```

## disassembly

```asm
0x3f40  ldarg.0
0x3f41  ldc.i4.0
0x3f42  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class NGenTask.ContainerFileInfo> NGenTask.LogWalker::WalkLogFiles(bool fOldLogs)
0x3f47  ret
```
