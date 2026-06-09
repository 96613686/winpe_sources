# NGenTask.ParsedLogsInfo::AddNewILAssembly

- ea: `0x35d0`
- end: `0x35de`
- name: `NGenTask.ParsedLogsInfo::AddNewILAssembly`
- size: `14`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x310`
- `0x3620`
- `0x3c10`

## pseudocode

```c

```

## disassembly

```asm
0x35d0  ldarg.0
0x35d1  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<class NGenTask.ILAssembly> NGenTask.ParsedLogsInfo::m_ilAssemblies
0x35d6  ldarg.1
0x35d7  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<class NGenTask.ILAssembly>::Add(var<u1>)
0x35dc  pop
0x35dd  ret
```
