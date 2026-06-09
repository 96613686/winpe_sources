# NGenTask.LogWalker::WalkOldLogs

- ea: `0x3f30`
- end: `0x3f38`
- name: `NGenTask.LogWalker::WalkOldLogs`
- size: `8`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x3830`

## callees

- `0x3f50`

## pseudocode

```c

```

## disassembly

```asm
0x3f30  ldarg.0
0x3f31  ldc.i4.1
0x3f32  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class NGenTask.ContainerFileInfo> NGenTask.LogWalker::WalkLogFiles(bool fOldLogs)
0x3f37  ret
```
