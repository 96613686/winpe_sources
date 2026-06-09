# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2::.ctor

- ea: `0x1930`
- end: `0x1965`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2::.ctor`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1930`

## string_xrefs

- `0x194b`: `readonlyObj`

## pseudocode

```c

```

## disassembly

```asm
0x1930  ldarg.1
0x1931  box      var<u1>
0x1936  brtrue.s loc_1943
0x1938  ldstr    aMutableobj// "mutableObj"
0x193d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1942  throw
0x1943  ldarg.2
0x1944  box      var<u1>
0x1949  brtrue.s loc_1956
0x194b  ldstr    aReadonlyobj// "readonlyObj"
0x1950  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1955  throw
0x1956  ldarg.0
0x1957  ldarg.1
0x1958  stfld    var<u1> valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<var<u1>, !!T0>::m_mutable
0x195d  ldarg.0
0x195e  ldarg.2
0x195f  stfld    var<u1> valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<var<u1>, !!T0>::m_readonly
0x1964  ret
```
