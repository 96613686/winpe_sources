# Microsoft.ManagementConsole.ScopeNode::Expand

- ea: `0x1970`
- end: `0x197f`
- name: `Microsoft.ManagementConsole.ScopeNode::Expand`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xe00`

## callees

- `0x1dc0`
- `0x73d0`

## pseudocode

```c

```

## disassembly

```asm
0x1970  ldarg.1
0x1971  newobj   instance void Microsoft.ManagementConsole.AsyncStatus::.ctor(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus requestStatus)
0x1976  stloc.0
0x1977  ldarg.0
0x1978  ldloc.0
0x1979  callvirt instance void Microsoft.ManagementConsole.ScopeNode::OnExpand(class Microsoft.ManagementConsole.AsyncStatus status)
0x197e  ret
```
