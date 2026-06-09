# Microsoft.BIServer.BIService.ManagedProcesses::RestartProcessByName

- ea: `0x1a50`
- end: `0x1a5f`
- name: `Microsoft.BIServer.BIService.ManagedProcesses::RestartProcessByName`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xce0`

## callees

- `0x19f0`
- `0x1a20`

## pseudocode

```c

```

## disassembly

```asm
0x1a50  ldarg.0
0x1a51  ldarg.1
0x1a52  call     instance void Microsoft.BIServer.BIService.ManagedProcesses::StopProcessByName(string procName)
0x1a57  ldarg.0
0x1a58  ldarg.1
0x1a59  call     instance void Microsoft.BIServer.BIService.ManagedProcesses::StartProcessByName(string procName)
0x1a5e  ret
```
