# Microsoft.BIServer.BIService.ManagedProcesses::GetManagedProcessByName

- ea: `0x1a60`
- end: `0x1a7e`
- name: `Microsoft.BIServer.BIService.ManagedProcesses::GetManagedProcessByName`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xce0`

## callees

- `0x1a60`

## pseudocode

```c

```

## disassembly

```asm
0x1a60  ldarg.0
0x1a61  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.BIServer.BIService.ManagedProcess> Microsoft.BIServer.BIService.ManagedProcesses::_managedProcesses
0x1a66  ldarg.1
0x1a67  ldloca.s 0
0x1a69  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.BIServer.BIService.ManagedProcess>::TryGetValue(var<u1>, !!T0)
0x1a6e  brfalse.s loc_1A72
0x1a70  ldloc.0
0x1a71  ret
0x1a72  ldstr    aCanTFindProces// "Can't find process with name [{0}]"
0x1a77  ldarg.1
0x1a78  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1a7d  throw
```
