# Microsoft.BIServer.BIService.ManagedProcesses::.ctor

- ea: `0x17e0`
- end: `0x17f2`
- name: `Microsoft.BIServer.BIService.ManagedProcesses::.ctor`
- size: `18`
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
0x17e0  ldarg.0
0x17e1  call     instance void [mscorlib]System.Object::.ctor()
0x17e6  ldarg.0
0x17e7  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.BIServer.BIService.ManagedProcess>::.ctor()
0x17ec  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.BIServer.BIService.ManagedProcess> Microsoft.BIServer.BIService.ManagedProcesses::_managedProcesses
0x17f1  ret
```
