# Microsoft.BIServer.BIService.ManagedProcesses::ThrottledStartProcesses

- ea: `0x18a0`
- end: `0x18d9`
- name: `Microsoft.BIServer.BIService.ManagedProcesses::ThrottledStartProcesses`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1700`

## callees

- `0x18a0`
- `0x1ee0`

## pseudocode

```c

```

## disassembly

```asm
0x18a0  ldarg.0
0x18a1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.BIServer.BIService.ManagedProcess> Microsoft.BIServer.BIService.ManagedProcesses::_managedProcesses
0x18a6  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.BIServer.BIService.ManagedProcess>::get_Values()
0x18ab  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<string, class Microsoft.BIServer.BIService.ManagedProcess>::GetEnumerator()
0x18b0  stloc.0
0x18b1  br.s     loc_18BF
0x18b3  ldloca.s 0
0x18b5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.BIServer.BIService.ManagedProcess>::get_Current()
0x18ba  callvirt instance void Microsoft.BIServer.BIService.ManagedProcess::ThrottledStart()
0x18bf  ldloca.s 0
0x18c1  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.BIServer.BIService.ManagedProcess>::MoveNext()
0x18c6  brtrue.s loc_18B3
0x18c8  leave.s  loc_18D8
0x18ca  ldloca.s 0
0x18cc  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.BIServer.BIService.ManagedProcess>
0x18d2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18d7  endfinally
0x18d8  ret
```
