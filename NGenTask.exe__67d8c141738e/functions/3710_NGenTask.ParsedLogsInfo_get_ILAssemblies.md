# NGenTask.ParsedLogsInfo::get_ILAssemblies

- ea: `0x3710`
- end: `0x3717`
- name: `NGenTask.ParsedLogsInfo::get_ILAssemblies`
- size: `7`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x12d0`
- `0x3620`

## pseudocode

```c

```

## disassembly

```asm
0x3710  ldarg.0
0x3711  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<class NGenTask.ILAssembly> NGenTask.ParsedLogsInfo::m_ilAssemblies
0x3716  ret
```
