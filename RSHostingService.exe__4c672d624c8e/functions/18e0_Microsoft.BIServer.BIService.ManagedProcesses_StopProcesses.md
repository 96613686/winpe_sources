# Microsoft.BIServer.BIService.ManagedProcesses::StopProcesses

- ea: `0x18e0`
- end: `0x1919`
- name: `Microsoft.BIServer.BIService.ManagedProcesses::StopProcesses`
- size: `57`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1080`
- `0x1760`
- `0x32c0`

## callees

- `0x18e0`
- `0x1da0`

## pseudocode

```c

```

## disassembly

```asm
0x18e0  ldarg.0
0x18e1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.BIServer.BIService.ManagedProcess> Microsoft.BIServer.BIService.ManagedProcesses::_managedProcesses
0x18e6  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.BIServer.BIService.ManagedProcess>::get_Values()
0x18eb  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<string, class Microsoft.BIServer.BIService.ManagedProcess>::GetEnumerator()
0x18f0  stloc.0
0x18f1  br.s     loc_18FF
0x18f3  ldloca.s 0
0x18f5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.BIServer.BIService.ManagedProcess>::get_Current()
0x18fa  callvirt instance void Microsoft.BIServer.BIService.ManagedProcess::Stop()
0x18ff  ldloca.s 0
0x1901  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.BIServer.BIService.ManagedProcess>::MoveNext()
0x1906  brtrue.s loc_18F3
0x1908  leave.s  loc_1918
0x190a  ldloca.s 0
0x190c  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.BIServer.BIService.ManagedProcess>
0x1912  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1917  endfinally
0x1918  ret
```
