# Microsoft.ManagementConsole.ScopeNodeCollection::Notify

- ea: `0x5c40`
- end: `0x5c5d`
- name: `Microsoft.ManagementConsole.ScopeNodeCollection::Notify`
- size: `29`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x5b20`
- `0x5b50`
- `0x5bf0`

## callees

- `0x5990`
- `0x5c40`
- `0x5cc0`

## pseudocode

```c

```

## disassembly

```asm
0x5c40  ldarg.0
0x5c41  ldfld    class ScopeNodeCollectionEventHandler Microsoft.ManagementConsole.ScopeNodeCollection::ItemsChanged
0x5c46  brfalse.s loc_5C5C
0x5c48  ldarg.0
0x5c49  ldfld    class ScopeNodeCollectionEventHandler Microsoft.ManagementConsole.ScopeNodeCollection::ItemsChanged
0x5c4e  ldarg.0
0x5c4f  ldarg.1
0x5c50  ldarg.2
0x5c51  ldarg.3
0x5c52  newobj   instance void Microsoft.ManagementConsole.ScopeNodeCollectionEventArgs::.ctor(int32 index, class Microsoft.ManagementConsole.ScopeNode[] items, valuetype Microsoft.ManagementConsole.ScopeNodeCollectionChangeType changeType)
0x5c57  callvirt instance void ScopeNodeCollectionEventHandler::Invoke(object sender, class Microsoft.ManagementConsole.ScopeNodeCollectionEventArgs e)
0x5c5c  ret
```
