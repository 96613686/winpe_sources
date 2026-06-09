# Microsoft.VisualStudio.Setup.Services.RpcServiceFacade::Dispose_0

- ea: `0x1bd0`
- end: `0x1bee`
- name: `Microsoft.VisualStudio.Setup.Services.RpcServiceFacade::Dispose_0`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1bc0`

## callees

- `0x1bd0`

## pseudocode

```c

```

## disassembly

```asm
0x1bd0  ldarg.0
0x1bd1  ldfld    bool Microsoft.VisualStudio.Setup.Services.RpcServiceFacade::isDisposed
0x1bd6  brtrue.s loc_1BED
0x1bd8  ldarg.1
0x1bd9  brfalse.s loc_1BE6
0x1bdb  ldarg.0
0x1bdc  ldfld    class [StreamJsonRpc]StreamJsonRpc.JsonRpc Microsoft.VisualStudio.Setup.Services.RpcServiceFacade::rpc
0x1be1  callvirt instance void [StreamJsonRpc]StreamJsonRpc.JsonRpc::Dispose()
0x1be6  ldarg.0
0x1be7  ldc.i4.1
0x1be8  stfld    bool Microsoft.VisualStudio.Setup.Services.RpcServiceFacade::isDisposed
0x1bed  ret
```
