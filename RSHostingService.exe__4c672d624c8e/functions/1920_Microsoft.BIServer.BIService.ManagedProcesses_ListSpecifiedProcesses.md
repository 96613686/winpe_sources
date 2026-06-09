# Microsoft.BIServer.BIService.ManagedProcesses::ListSpecifiedProcesses

- ea: `0x1920`
- end: `0x196d`
- name: `Microsoft.BIServer.BIService.ManagedProcesses::ListSpecifiedProcesses`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x16a0`

## callees

- `0x1920`

## pseudocode

```c

```

## disassembly

```asm
0x1920  ldarg.1
0x1921  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x1926  stloc.0
0x1927  br.s     loc_1958
0x1929  ldloc.0
0x192a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x192f  stloc.1
0x1930  ldarg.0
0x1931  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.BIServer.BIService.ManagedProcess> Microsoft.BIServer.BIService.ManagedProcesses::_managedProcesses
0x1936  ldloc.1
0x1937  ldloca.s 2
0x1939  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.BIServer.BIService.ManagedProcess>::TryGetValue(var<u1>, !!T0)
0x193e  brfalse.s loc_194D
0x1940  ldstr    aProcessN0// "Process : \\n{0}"
0x1945  ldloc.2
0x1946  call     void [mscorlib]System.Console::WriteLine(string, object)
0x194b  br.s     loc_1958
0x194d  ldstr    a0IsNotTheNameO// "{0} is not the name of a managed proces"...
0x1952  ldloc.1
0x1953  call     void [mscorlib]System.Console::WriteLine(string, object)
0x1958  ldloc.0
0x1959  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x195e  brtrue.s loc_1929
0x1960  leave.s  loc_196C
0x1962  ldloc.0
0x1963  brfalse.s loc_196B
0x1965  ldloc.0
0x1966  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x196b  endfinally
0x196c  ret
```
