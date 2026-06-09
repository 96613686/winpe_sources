# Microsoft.VisualStudio.Setup.Services.RpcServiceFacade::.ctor

- ea: `0x1b70`
- end: `0x1b7e`
- name: `Microsoft.VisualStudio.Setup.Services.RpcServiceFacade::.ctor`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1c30`

## pseudocode

```c

```

## disassembly

```asm
0x1b70  ldarg.0
0x1b71  call     instance void [mscorlib]System.Object::.ctor()
0x1b76  ldarg.0
0x1b77  ldarg.1
0x1b78  stfld    class [StreamJsonRpc]StreamJsonRpc.JsonRpc Microsoft.VisualStudio.Setup.Services.RpcServiceFacade::rpc
0x1b7d  ret
```
