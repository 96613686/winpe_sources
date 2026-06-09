# Microsoft.BIServer.BIService.ManagedProcesses::Clear

- ea: `0x19c0`
- end: `0x19cc`
- name: `Microsoft.BIServer.BIService.ManagedProcesses::Clear`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x32c0`

## pseudocode

```c

```

## disassembly

```asm
0x19c0  ldarg.0
0x19c1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.BIServer.BIService.ManagedProcess> Microsoft.BIServer.BIService.ManagedProcesses::_managedProcesses
0x19c6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.BIServer.BIService.ManagedProcess>::Clear()
0x19cb  ret
```
