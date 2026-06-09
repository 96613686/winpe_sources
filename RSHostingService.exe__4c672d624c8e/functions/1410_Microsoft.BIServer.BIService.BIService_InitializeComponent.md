# Microsoft.BIServer.BIService.BIService::InitializeComponent

- ea: `0x1410`
- end: `0x1427`
- name: `Microsoft.BIServer.BIService.BIService::InitializeComponent`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xa60`

## pseudocode

```c

```

## disassembly

```asm
0x1410  ldarg.0
0x1411  newobj   instance void [System]System.ComponentModel.Container::.ctor()
0x1416  stfld    class [System]System.ComponentModel.IContainer Microsoft.BIServer.BIService.BIService::components
0x141b  ldarg.0
0x141c  ldstr    aBiserver// "BIServer"
0x1421  call     instance void [System.ServiceProcess]System.ServiceProcess.ServiceBase::set_ServiceName(string)
0x1426  ret
```
