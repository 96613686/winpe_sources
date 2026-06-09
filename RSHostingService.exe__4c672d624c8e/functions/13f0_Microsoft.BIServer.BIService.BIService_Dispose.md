# Microsoft.BIServer.BIService.BIService::Dispose

- ea: `0x13f0`
- end: `0x140e`
- name: `Microsoft.BIServer.BIService.BIService::Dispose`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x13f0`

## pseudocode

```c

```

## disassembly

```asm
0x13f0  ldarg.1
0x13f1  brfalse.s loc_1406
0x13f3  ldarg.0
0x13f4  ldfld    class [System]System.ComponentModel.IContainer Microsoft.BIServer.BIService.BIService::components
0x13f9  brfalse.s loc_1406
0x13fb  ldarg.0
0x13fc  ldfld    class [System]System.ComponentModel.IContainer Microsoft.BIServer.BIService.BIService::components
0x1401  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1406  ldarg.0
0x1407  ldarg.1
0x1408  call     instance void [System.ServiceProcess]System.ServiceProcess.ServiceBase::Dispose(bool)
0x140d  ret
```
