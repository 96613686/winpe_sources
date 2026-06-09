# Microsoft.BIServer.Configuration.UrlApplications::RegisterAll

- ea: `0x3670`
- end: `0x36db`
- name: `Microsoft.BIServer.Configuration.UrlApplications::RegisterAll`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3670`
- `0x4730`
- `0x4770`
- `0x47f0`

## pseudocode

```c

```

## disassembly

```asm
0x3670  ldarg.0
0x3671  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.Application> Microsoft.BIServer.Configuration.UrlApplications::_urlApplications
0x3676  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.Application>::GetEnumerator()
0x367b  stloc.0
0x367c  br.s     loc_36C1
0x367e  ldloca.s 0
0x3680  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.BIServer.Configuration.Application>::get_Current()
0x3685  stloc.1
0x3686  ldstr    aReservingUrlsF// "Reserving Urls for application {0}"
0x368b  ldc.i4.1
0x368c  newarr   [mscorlib]System.Object
0x3691  dup
0x3692  ldc.i4.0
0x3693  ldloc.1
0x3694  callvirt instance string Microsoft.BIServer.Configuration.Application::get_Name()
0x3699  stelem.ref
0x369a  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x369f  ldloc.1
0x36a0  callvirt instance class Microsoft.BIServer.Configuration.URL[] Microsoft.BIServer.Configuration.Application::get_URLs()
0x36a5  stloc.2
0x36a6  ldc.i4.0
0x36a7  stloc.3
0x36a8  br.s     loc_36BB
0x36aa  ldloc.2
0x36ab  ldloc.3
0x36ac  ldelem.ref
0x36ad  stloc.s  4
0x36af  ldloc.1
0x36b0  ldloc.s  4
0x36b2  callvirt instance void Microsoft.BIServer.Configuration.Application::Register(class Microsoft.BIServer.Configuration.URL url)
0x36b7  ldloc.3
0x36b8  ldc.i4.1
0x36b9  add
0x36ba  stloc.3
0x36bb  ldloc.3
0x36bc  ldloc.2
0x36bd  ldlen
0x36be  conv.i4
0x36bf  blt.s    loc_36AA
0x36c1  ldloca.s 0
0x36c3  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.BIServer.Configuration.Application>::MoveNext()
0x36c8  brtrue.s loc_367E
0x36ca  leave.s  loc_36DA
0x36cc  ldloca.s 0
0x36ce  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.BIServer.Configuration.Application>
0x36d4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36d9  endfinally
0x36da  ret
```
