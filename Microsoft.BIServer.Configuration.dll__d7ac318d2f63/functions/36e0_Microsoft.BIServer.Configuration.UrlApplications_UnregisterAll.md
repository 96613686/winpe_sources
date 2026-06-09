# Microsoft.BIServer.Configuration.UrlApplications::UnregisterAll

- ea: `0x36e0`
- end: `0x374b`
- name: `Microsoft.BIServer.Configuration.UrlApplications::UnregisterAll`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x36e0`
- `0x4730`
- `0x4770`
- `0x4810`

## pseudocode

```c

```

## disassembly

```asm
0x36e0  ldarg.0
0x36e1  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.Application> Microsoft.BIServer.Configuration.UrlApplications::_urlApplications
0x36e6  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.Application>::GetEnumerator()
0x36eb  stloc.0
0x36ec  br.s     loc_3731
0x36ee  ldloca.s 0
0x36f0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.BIServer.Configuration.Application>::get_Current()
0x36f5  stloc.1
0x36f6  ldstr    aRemovingReserv// "Removing reserved Urls for application "...
0x36fb  ldc.i4.1
0x36fc  newarr   [mscorlib]System.Object
0x3701  dup
0x3702  ldc.i4.0
0x3703  ldloc.1
0x3704  callvirt instance string Microsoft.BIServer.Configuration.Application::get_Name()
0x3709  stelem.ref
0x370a  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x370f  ldloc.1
0x3710  callvirt instance class Microsoft.BIServer.Configuration.URL[] Microsoft.BIServer.Configuration.Application::get_URLs()
0x3715  stloc.2
0x3716  ldc.i4.0
0x3717  stloc.3
0x3718  br.s     loc_372B
0x371a  ldloc.2
0x371b  ldloc.3
0x371c  ldelem.ref
0x371d  stloc.s  4
0x371f  ldloc.1
0x3720  ldloc.s  4
0x3722  callvirt instance void Microsoft.BIServer.Configuration.Application::Unregister(class Microsoft.BIServer.Configuration.URL url)
0x3727  ldloc.3
0x3728  ldc.i4.1
0x3729  add
0x372a  stloc.3
0x372b  ldloc.3
0x372c  ldloc.2
0x372d  ldlen
0x372e  conv.i4
0x372f  blt.s    loc_371A
0x3731  ldloca.s 0
0x3733  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.BIServer.Configuration.Application>::MoveNext()
0x3738  brtrue.s loc_36EE
0x373a  leave.s  loc_374A
0x373c  ldloca.s 0
0x373e  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.BIServer.Configuration.Application>
0x3744  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3749  endfinally
0x374a  ret
```
