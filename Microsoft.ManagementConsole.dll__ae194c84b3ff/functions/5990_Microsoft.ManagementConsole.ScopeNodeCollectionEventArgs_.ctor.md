# Microsoft.ManagementConsole.ScopeNodeCollectionEventArgs::.ctor

- ea: `0x5990`
- end: `0x59ac`
- name: `Microsoft.ManagementConsole.ScopeNodeCollectionEventArgs::.ctor`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x5c40`

## pseudocode

```c

```

## disassembly

```asm
0x5990  ldarg.0
0x5991  call     instance void [mscorlib]System.EventArgs::.ctor()
0x5996  ldarg.0
0x5997  ldarg.1
0x5998  stfld    int32 Microsoft.ManagementConsole.ScopeNodeCollectionEventArgs::_index
0x599d  ldarg.0
0x599e  ldarg.2
0x599f  stfld    class Microsoft.ManagementConsole.ScopeNode[] Microsoft.ManagementConsole.ScopeNodeCollectionEventArgs::_items
0x59a4  ldarg.0
0x59a5  ldarg.3
0x59a6  stfld    valuetype Microsoft.ManagementConsole.ScopeNodeCollectionChangeType Microsoft.ManagementConsole.ScopeNodeCollectionEventArgs::_changeType
0x59ab  ret
```
