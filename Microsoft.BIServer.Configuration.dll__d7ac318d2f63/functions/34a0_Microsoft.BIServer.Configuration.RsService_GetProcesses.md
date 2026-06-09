# Microsoft.BIServer.Configuration.RsService::GetProcesses

- ea: `0x34a0`
- end: `0x34af`
- name: `Microsoft.BIServer.Configuration.RsService::GetProcesses`
- size: `15`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3390`
- `0x34b0`

## callees

- `0x7260`

## pseudocode

```c

```

## disassembly

```asm
0x34a0  ldc.i4.s 0xFE
0x34a2  newobj   instance void <GetProcesses>d__9::.ctor(int32 <>1__state)
0x34a7  dup
0x34a8  ldarg.0
0x34a9  stfld    class Microsoft.BIServer.Configuration.RsService <GetProcesses>d__9::<>4__this
0x34ae  ret
```
