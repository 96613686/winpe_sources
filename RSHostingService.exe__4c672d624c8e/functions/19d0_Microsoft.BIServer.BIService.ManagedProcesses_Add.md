# Microsoft.BIServer.BIService.ManagedProcesses::Add

- ea: `0x19d0`
- end: `0x19e8`
- name: `Microsoft.BIServer.BIService.ManagedProcesses::Add`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1320`

## callees

- `0x1bd0`
- `0x20d0`

## pseudocode

```c

```

## disassembly

```asm
0x19d0  ldarg.0
0x19d1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.BIServer.BIService.ManagedProcess> Microsoft.BIServer.BIService.ManagedProcesses::_managedProcesses
0x19d6  ldarg.1
0x19d7  callvirt instance class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ManagedProcess::get_ProcessConfig()
0x19dc  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_Name()
0x19e1  ldarg.1
0x19e2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.BIServer.BIService.ManagedProcess>::Add(var<u1>, !!T0)
0x19e7  ret
```
