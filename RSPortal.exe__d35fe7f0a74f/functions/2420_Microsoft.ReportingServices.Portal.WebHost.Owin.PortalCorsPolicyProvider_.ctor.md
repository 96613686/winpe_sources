# Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsPolicyProvider::.ctor

- ea: `0x2420`
- end: `0x24cd`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsPolicyProvider::.ctor`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3660`

## pseudocode

```c

```

## disassembly

```asm
0x2420  ldarg.0
0x2421  call     instance void [mscorlib]System.Object::.ctor()
0x2426  ldsfld   class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0x242b  stloc.0
0x242c  ldarg.0
0x242d  ldloc.0
0x242e  ldc.i4.0
0x242f  stloc.1
0x2430  ldloca.s 1
0x2432  constrained. [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.CorsCongfigSettings
0x2438  callvirt instance string [mscorlib]System.Object::ToString()
0x243d  ldsfld   string [mscorlib]System.String::Empty
0x2442  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrDefault(string, string)
0x2447  stfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsPolicyProvider::_allowedOrigins
0x244c  ldarg.0
0x244d  ldloc.0
0x244e  ldc.i4.5
0x244f  stloc.1
0x2450  ldloca.s 1
0x2452  constrained. [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.CorsCongfigSettings
0x2458  callvirt instance string [mscorlib]System.Object::ToString()
0x245d  ldsfld   string [mscorlib]System.String::Empty
0x2462  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrDefault(string, string)
0x2467  stfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsPolicyProvider::_allowedHeaders
0x246c  ldarg.0
0x246d  ldloc.0
0x246e  ldc.i4.4
0x246f  stloc.1
0x2470  ldloca.s 1
0x2472  constrained. [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.CorsCongfigSettings
0x2478  callvirt instance string [mscorlib]System.Object::ToString()
0x247d  ldsfld   string [mscorlib]System.String::Empty
0x2482  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrDefault(string, string)
0x2487  stfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsPolicyProvider::_allowedMethods
0x248c  ldarg.0
0x248d  ldloc.0
0x248e  ldc.i4.2
0x248f  stloc.1
0x2490  ldloca.s 1
0x2492  constrained. [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.CorsCongfigSettings
0x2498  callvirt instance string [mscorlib]System.Object::ToString()
0x249d  ldsfld   string [mscorlib]System.String::Empty
0x24a2  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrDefault(string, string)
0x24a7  stfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsPolicyProvider::_exposedHeaders
0x24ac  ldarg.0
0x24ad  ldloc.0
0x24ae  ldc.i4.3
0x24af  stloc.1
0x24b0  ldloca.s 1
0x24b2  constrained. [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.CorsCongfigSettings
0x24b8  callvirt instance string [mscorlib]System.Object::ToString()
0x24bd  ldsfld   string [mscorlib]System.String::Empty
0x24c2  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrDefault(string, string)
0x24c7  stfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsPolicyProvider::_maxAge
0x24cc  ret
```
