# Microsoft.ManagementConsole.ScopeNode::ExpandFromLoad

- ea: `0x1980`
- end: `0x198f`
- name: `Microsoft.ManagementConsole.ScopeNode::ExpandFromLoad`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xe00`

## callees

- `0x1dd0`
- `0x73b0`

## pseudocode

```c

```

## disassembly

```asm
0x1980  ldarg.1
0x1981  newobj   instance void Microsoft.ManagementConsole.SyncStatus::.ctor(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus requestStatus)
0x1986  stloc.0
0x1987  ldarg.0
0x1988  ldloc.0
0x1989  callvirt instance bool Microsoft.ManagementConsole.ScopeNode::OnExpandFromLoad(class Microsoft.ManagementConsole.SyncStatus status)
0x198e  ret
```
