# Microsoft.BIServer.BIService.ManagedProcesses::StartWorkerProcesses

- ea: `0x1800`
- end: `0x1843`
- name: `Microsoft.BIServer.BIService.ManagedProcesses::StartWorkerProcesses`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x2dd0`

## callees

- `0x1800`
- `0x1be0`
- `0x1f10`

## pseudocode

```c

```

## disassembly

```asm
0x1800  ldarg.0
0x1801  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.BIServer.BIService.ManagedProcess> Microsoft.BIServer.BIService.ManagedProcesses::_managedProcesses
0x1806  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.BIServer.BIService.ManagedProcess>::get_Values()
0x180b  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<string, class Microsoft.BIServer.BIService.ManagedProcess>::GetEnumerator()
0x1810  stloc.0
0x1811  br.s     loc_1829
0x1813  ldloca.s 0
0x1815  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.BIServer.BIService.ManagedProcess>::get_Current()
0x181a  stloc.1
0x181b  ldloc.1
0x181c  callvirt instance bool Microsoft.BIServer.BIService.ManagedProcess::get_IsManagementProcess()
0x1821  brtrue.s loc_1829
0x1823  ldloc.1
0x1824  callvirt instance void Microsoft.BIServer.BIService.ManagedProcess::Start()
0x1829  ldloca.s 0
0x182b  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.BIServer.BIService.ManagedProcess>::MoveNext()
0x1830  brtrue.s loc_1813
0x1832  leave.s  loc_1842
0x1834  ldloca.s 0
0x1836  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.BIServer.BIService.ManagedProcess>
0x183c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1841  endfinally
0x1842  ret
```
