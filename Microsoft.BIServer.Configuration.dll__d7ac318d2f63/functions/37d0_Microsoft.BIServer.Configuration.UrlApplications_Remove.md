# Microsoft.BIServer.Configuration.UrlApplications::Remove

- ea: `0x37d0`
- end: `0x3816`
- name: `Microsoft.BIServer.Configuration.UrlApplications::Remove`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x37d0`
- `0x4830`

## pseudocode

```c

```

## disassembly

```asm
0x37d0  ldarg.0
0x37d1  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.Application> Microsoft.BIServer.Configuration.UrlApplications::_urlApplications
0x37d6  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.Application>::GetEnumerator()
0x37db  stloc.0
0x37dc  br.s     loc_37FC
0x37de  ldloca.s 0
0x37e0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.BIServer.Configuration.Application>::get_Current()
0x37e5  stloc.1
0x37e6  ldloc.1
0x37e7  ldarg.1
0x37e8  callvirt instance bool Microsoft.BIServer.Configuration.Application::Equals(class Microsoft.BIServer.Configuration.Application other)
0x37ed  brfalse.s loc_37FC
0x37ef  ldarg.0
0x37f0  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.Application> Microsoft.BIServer.Configuration.UrlApplications::_urlApplications
0x37f5  ldloc.1
0x37f6  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.Application>::Remove(var<u1>)
0x37fb  pop
0x37fc  ldloca.s 0
0x37fe  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.BIServer.Configuration.Application>::MoveNext()
0x3803  brtrue.s loc_37DE
0x3805  leave.s  loc_3815
0x3807  ldloca.s 0
0x3809  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.BIServer.Configuration.Application>
0x380f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3814  endfinally
0x3815  ret
```
