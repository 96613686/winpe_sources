# Microsoft.BIServer.BIService.ManagedProcesses::StartProcessByName

- ea: `0x19f0`
- end: `0x1a13`
- name: `Microsoft.BIServer.BIService.ManagedProcesses::StartProcessByName`
- size: `35`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1700`
- `0x1a50`

## callees

- `0x19f0`
- `0x1ee0`

## pseudocode

```c

```

## disassembly

```asm
0x19f0  ldarg.0
0x19f1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.BIServer.BIService.ManagedProcess> Microsoft.BIServer.BIService.ManagedProcesses::_managedProcesses
0x19f6  ldarg.1
0x19f7  ldloca.s 0
0x19f9  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.BIServer.BIService.ManagedProcess>::TryGetValue(var<u1>, !!T0)
0x19fe  brfalse.s loc_1A07
0x1a00  ldloc.0
0x1a01  callvirt instance void Microsoft.BIServer.BIService.ManagedProcess::ThrottledStart()
0x1a06  ret
0x1a07  ldstr    aCanTStartUnkno// "Can't start unknown process [{0}]"
0x1a0c  ldarg.1
0x1a0d  call     void [mscorlib]System.Console::WriteLine(string, object)
0x1a12  ret
```
