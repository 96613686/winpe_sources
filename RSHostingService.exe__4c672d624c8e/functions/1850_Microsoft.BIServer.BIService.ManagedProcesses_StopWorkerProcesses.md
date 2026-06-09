# Microsoft.BIServer.BIService.ManagedProcesses::StopWorkerProcesses

- ea: `0x1850`
- end: `0x1893`
- name: `Microsoft.BIServer.BIService.ManagedProcesses::StopWorkerProcesses`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1850`
- `0x1be0`
- `0x1f10`

## pseudocode

```c

```

## disassembly

```asm
0x1850  ldarg.0
0x1851  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.BIServer.BIService.ManagedProcess> Microsoft.BIServer.BIService.ManagedProcesses::_managedProcesses
0x1856  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.BIServer.BIService.ManagedProcess>::get_Values()
0x185b  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<string, class Microsoft.BIServer.BIService.ManagedProcess>::GetEnumerator()
0x1860  stloc.0
0x1861  br.s     loc_1879
0x1863  ldloca.s 0
0x1865  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.BIServer.BIService.ManagedProcess>::get_Current()
0x186a  stloc.1
0x186b  ldloc.1
0x186c  callvirt instance bool Microsoft.BIServer.BIService.ManagedProcess::get_IsManagementProcess()
0x1871  brtrue.s loc_1879
0x1873  ldloc.1
0x1874  callvirt instance void Microsoft.BIServer.BIService.ManagedProcess::Start()
0x1879  ldloca.s 0
0x187b  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.BIServer.BIService.ManagedProcess>::MoveNext()
0x1880  brtrue.s loc_1863
0x1882  leave.s  loc_1892
0x1884  ldloca.s 0
0x1886  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.BIServer.BIService.ManagedProcess>
0x188c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1891  endfinally
0x1892  ret
```
