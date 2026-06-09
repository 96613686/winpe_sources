# Microsoft.BIServer.BIService.ManagedProcesses::ListAllProcesses

- ea: `0x1970`
- end: `0x19b8`
- name: `Microsoft.BIServer.BIService.ManagedProcesses::ListAllProcesses`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x16a0`

## callees

- `0x1970`

## pseudocode

```c

```

## disassembly

```asm
0x1970  ldarg.0
0x1971  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.BIServer.BIService.ManagedProcess> Microsoft.BIServer.BIService.ManagedProcesses::_managedProcesses
0x1976  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.BIServer.BIService.ManagedProcess>::GetEnumerator()
0x197b  stloc.0
0x197c  br.s     loc_199E
0x197e  ldloca.s 0
0x1980  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.BIServer.BIService.ManagedProcess>::get_Current()
0x1985  stloc.1
0x1986  ldstr    aProcess01// "Process : {0}{1}"
0x198b  ldloca.s 1
0x198d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.BIServer.BIService.ManagedProcess>::get_Key()
0x1992  ldloca.s 1
0x1994  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.BIServer.BIService.ManagedProcess>::get_Value()
0x1999  call     void [mscorlib]System.Console::WriteLine(string, object, object)
0x199e  ldloca.s 0
0x19a0  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.BIServer.BIService.ManagedProcess>::MoveNext()
0x19a5  brtrue.s loc_197E
0x19a7  leave.s  loc_19B7
0x19a9  ldloca.s 0
0x19ab  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.BIServer.BIService.ManagedProcess>
0x19b1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19b6  endfinally
0x19b7  ret
```
