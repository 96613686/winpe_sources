# Microsoft.BIServer.Configuration.CustomHeaderHelper::GetHeaderRules

- ea: `0x130`
- end: `0x1a4`
- name: `Microsoft.BIServer.Configuration.CustomHeaderHelper::GetHeaderRules`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x70`
- `0x130`
- `0x1b0`
- `0x730`
- `0x67c0`

## pseudocode

```c

```

## disassembly

```asm
0x130  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.BIServer.Configuration.IPathMatcher, class Microsoft.BIServer.Configuration.Header>::.ctor()
0x135  stloc.0
0x136  ldarg.0
0x137  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.Header> Microsoft.BIServer.Configuration.CustomHeaderHelper::GetCustomHeaders()
0x13c  stloc.1
0x13d  ldloc.1
0x13e  brfalse.s loc_189
0x140  ldloc.1
0x141  call     instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.Header>::get_Count()
0x146  ldc.i4.0
0x147  ble.s    loc_189
0x149  ldloc.1
0x14a  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.Header>::GetEnumerator()
0x14f  stloc.2
0x150  br.s     loc_170
0x152  ldloca.s 2
0x154  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.BIServer.Configuration.Header>::get_Current()
0x159  stloc.3
0x15a  ldloc.3
0x15b  callvirt instance string Microsoft.BIServer.Configuration.Header::get_Pattern()
0x160  newobj   instance void Microsoft.BIServer.Configuration.PathMatcher::.ctor(string regexPath)
0x165  stloc.s  4
0x167  ldloc.0
0x168  ldloc.s  4
0x16a  ldloc.3
0x16b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.BIServer.Configuration.IPathMatcher, class Microsoft.BIServer.Configuration.Header>::Add(var<u1>, !!T0)
0x170  ldloca.s 2
0x172  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.BIServer.Configuration.Header>::MoveNext()
0x177  brtrue.s loc_152
0x179  leave.s  loc_18E
0x17b  ldloca.s 2
0x17d  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.BIServer.Configuration.Header>
0x183  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x188  endfinally
0x189  ldloc.0
0x18a  stloc.s  5
0x18c  leave.s  loc_1A1
0x18e  leave.s  loc_19F
0x190  stloc.s  6
0x192  ldstr    aFailedToGenera// "Failed to generate custom headers rules"...
0x197  ldloc.s  6
0x199  newobj   instance void Microsoft.BIServer.Configuration.Exceptions.ConfigException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x19e  throw
0x19f  ldloc.0
0x1a0  ret
0x1a1  ldloc.s  5
0x1a3  ret
```
