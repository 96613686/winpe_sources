# Microsoft.BIServer.BIService.BIService::OnStart

- ea: `0xb40`
- end: `0xb4c`
- name: `Microsoft.BIServer.BIService.BIService::OnStart`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0xb40  ldarg.0
0xb41  ldsfld   string[] Microsoft.BIServer.BIService.BIService::NoArgs
0xb46  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceBase::OnStart(string[])
0xb4b  ret
```
