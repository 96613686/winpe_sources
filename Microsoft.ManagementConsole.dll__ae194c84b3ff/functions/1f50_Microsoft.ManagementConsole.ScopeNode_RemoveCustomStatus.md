# Microsoft.ManagementConsole.ScopeNode::RemoveCustomStatus

- ea: `0x1f50`
- end: `0x1f5e`
- name: `Microsoft.ManagementConsole.ScopeNode::RemoveCustomStatus`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x74a0`

## pseudocode

```c

```

## disassembly

```asm
0x1f50  ldarg.0
0x1f51  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ManagementConsole.CustomStatus> Microsoft.ManagementConsole.ScopeNode::_customStatusList
0x1f56  ldarg.1
0x1f57  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ManagementConsole.CustomStatus>::Remove(var<u1>)
0x1f5c  pop
0x1f5d  ret
```
