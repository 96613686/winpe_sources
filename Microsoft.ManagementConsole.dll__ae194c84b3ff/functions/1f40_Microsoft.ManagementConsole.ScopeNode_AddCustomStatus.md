# Microsoft.ManagementConsole.ScopeNode::AddCustomStatus

- ea: `0x1f40`
- end: `0x1f4d`
- name: `Microsoft.ManagementConsole.ScopeNode::AddCustomStatus`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x7410`

## pseudocode

```c

```

## disassembly

```asm
0x1f40  ldarg.0
0x1f41  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ManagementConsole.CustomStatus> Microsoft.ManagementConsole.ScopeNode::_customStatusList
0x1f46  ldarg.1
0x1f47  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ManagementConsole.CustomStatus>::Add(var<u1>)
0x1f4c  ret
```
