# Microsoft.ManagementConsole.AsyncStatus::EnableManualCompletion

- ea: `0x73e0`
- end: `0x73ed`
- name: `Microsoft.ManagementConsole.AsyncStatus::EnableManualCompletion`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x7340`

## pseudocode

```c

```

## disassembly

```asm
0x73e0  ldarg.0
0x73e1  call     instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus Microsoft.ManagementConsole.Status::get_RequestStatus()
0x73e6  ldc.i4.1
0x73e7  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus::set_RequestState(valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.RequestState)
0x73ec  ret
```
