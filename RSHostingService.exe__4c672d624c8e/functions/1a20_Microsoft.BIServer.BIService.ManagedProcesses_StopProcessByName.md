# Microsoft.BIServer.BIService.ManagedProcesses::StopProcessByName

- ea: `0x1a20`
- end: `0x1a43`
- name: `Microsoft.BIServer.BIService.ManagedProcesses::StopProcessByName`
- size: `35`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1760`
- `0x1a50`

## callees

- `0x1a20`
- `0x1da0`

## pseudocode

```c

```

## disassembly

```asm
0x1a20  ldarg.0
0x1a21  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.BIServer.BIService.ManagedProcess> Microsoft.BIServer.BIService.ManagedProcesses::_managedProcesses
0x1a26  ldarg.1
0x1a27  ldloca.s 0
0x1a29  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.BIServer.BIService.ManagedProcess>::TryGetValue(var<u1>, !!T0)
0x1a2e  brfalse.s loc_1A37
0x1a30  ldloc.0
0x1a31  callvirt instance void Microsoft.BIServer.BIService.ManagedProcess::Stop()
0x1a36  ret
0x1a37  ldstr    aCanTStopUnknow// "Can't stop unknown process [{0}]"
0x1a3c  ldarg.1
0x1a3d  call     void [mscorlib]System.Console::WriteLine(string, object)
0x1a42  ret
```
