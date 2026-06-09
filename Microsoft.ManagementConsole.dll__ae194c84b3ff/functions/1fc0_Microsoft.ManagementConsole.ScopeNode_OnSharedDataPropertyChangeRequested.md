# Microsoft.ManagementConsole.ScopeNode::OnSharedDataPropertyChangeRequested

- ea: `0x1fc0`
- end: `0x1fe0`
- name: `Microsoft.ManagementConsole.ScopeNode::OnSharedDataPropertyChangeRequested`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1df0`
- `0x5490`
- `0x54a0`
- `0x54d0`
- `0x73d0`

## pseudocode

```c

```

## disassembly

```asm
0x1fc0  ldarg.2
0x1fc1  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus Microsoft.ManagementConsole.WritableSharedDataChangeRequestEventArgs::get_RequestStatus()
0x1fc6  newobj   instance void Microsoft.ManagementConsole.AsyncStatus::.ctor(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus requestStatus)
0x1fcb  stloc.0
0x1fcc  ldarg.0
0x1fcd  ldarg.2
0x1fce  callvirt instance class Microsoft.ManagementConsole.WritableSharedDataItem Microsoft.ManagementConsole.WritableSharedDataChangeRequestEventArgs::get_SharedDataItem()
0x1fd3  ldarg.2
0x1fd4  callvirt instance unsigned int8[] Microsoft.ManagementConsole.WritableSharedDataChangeRequestEventArgs::GetNewValue()
0x1fd9  ldloc.0
0x1fda  callvirt instance void Microsoft.ManagementConsole.ScopeNode::OnSharedDataChangeRequested(class Microsoft.ManagementConsole.WritableSharedDataItem item, unsigned int8[] newValue, class Microsoft.ManagementConsole.AsyncStatus status)
0x1fdf  ret
```
