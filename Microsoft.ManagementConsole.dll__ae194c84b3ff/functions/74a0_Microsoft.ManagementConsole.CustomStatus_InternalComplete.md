# Microsoft.ManagementConsole.CustomStatus::InternalComplete

- ea: `0x74a0`
- end: `0x74d2`
- name: `Microsoft.ManagementConsole.CustomStatus::InternalComplete`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1f50`
- `0x71f0`
- `0x7340`
- `0x74a0`
- `0x7560`

## pseudocode

```c

```

## disassembly

```asm
0x74a0  ldarg.0
0x74a1  call     instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus Microsoft.ManagementConsole.Status::get_RequestStatus()
0x74a6  brfalse.s loc_74B0
0x74a8  ldarg.0
0x74a9  ldarg.1
0x74aa  ldarg.2
0x74ab  call     instance void Microsoft.ManagementConsole.Status::InternalComplete(string completionText, bool success)
0x74b0  ldarg.0
0x74b1  ldfld    class Microsoft.ManagementConsole.ScopeNode Microsoft.ManagementConsole.CustomStatus::_owner
0x74b6  brfalse.s loc_74D1
0x74b8  ldarg.0
0x74b9  ldfld    class Microsoft.ManagementConsole.ScopeNode Microsoft.ManagementConsole.CustomStatus::_owner
0x74be  ldarg.0
0x74bf  callvirt instance void Microsoft.ManagementConsole.ScopeNode::RemoveCustomStatus(class Microsoft.ManagementConsole.CustomStatus status)
0x74c4  ldarg.0
0x74c5  call     instance void Microsoft.ManagementConsole.CustomStatus::DetachRequestStatus()
0x74ca  ldarg.0
0x74cb  ldnull
0x74cc  stfld    class Microsoft.ManagementConsole.ScopeNode Microsoft.ManagementConsole.CustomStatus::_owner
0x74d1  ret
```
