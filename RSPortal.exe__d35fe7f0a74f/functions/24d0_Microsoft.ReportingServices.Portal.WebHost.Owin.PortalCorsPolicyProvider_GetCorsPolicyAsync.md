# Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsPolicyProvider::GetCorsPolicyAsync

- ea: `0x24d0`
- end: `0x25e7`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsPolicyProvider::GetCorsPolicyAsync`
- size: `279`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x24d0`
- `0x25f0`

## pseudocode

```c

```

## disassembly

```asm
0x24d0  newobj   instance void [System.Web.Cors]System.Web.Cors.CorsPolicy::.ctor()
0x24d5  stloc.0
0x24d6  ldarg.0
0x24d7  ldfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsPolicyProvider::_allowedOrigins
0x24dc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x24e1  brtrue.s loc_250E
0x24e3  ldarg.0
0x24e4  ldloc.0
0x24e5  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> [System.Web.Cors]System.Web.Cors.CorsPolicy::get_Origins()
0x24ea  ldarg.0
0x24eb  ldfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsPolicyProvider::_allowedOrigins
0x24f0  call     instance void Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsPolicyProvider::GetList(class [mscorlib]System.Collections.Generic.IList`1<string> corsSettings, string delimitedSetting)
0x24f5  ldloc.0
0x24f6  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> [System.Web.Cors]System.Web.Cors.CorsPolicy::get_Origins()
0x24fb  ldstr    asc_6076// "*"
0x2500  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<string>::Contains(var<u1>)
0x2505  brfalse.s loc_250E
0x2507  ldloc.0
0x2508  ldc.i4.1
0x2509  callvirt instance void [System.Web.Cors]System.Web.Cors.CorsPolicy::set_AllowAnyOrigin(bool)
0x250e  ldarg.0
0x250f  ldfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsPolicyProvider::_allowedHeaders
0x2514  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2519  brtrue.s loc_2546
0x251b  ldarg.0
0x251c  ldloc.0
0x251d  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> [System.Web.Cors]System.Web.Cors.CorsPolicy::get_Headers()
0x2522  ldarg.0
0x2523  ldfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsPolicyProvider::_allowedHeaders
0x2528  call     instance void Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsPolicyProvider::GetList(class [mscorlib]System.Collections.Generic.IList`1<string> corsSettings, string delimitedSetting)
0x252d  ldloc.0
0x252e  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> [System.Web.Cors]System.Web.Cors.CorsPolicy::get_Headers()
0x2533  ldstr    asc_6076// "*"
0x2538  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<string>::Contains(var<u1>)
0x253d  brfalse.s loc_2546
0x253f  ldloc.0
0x2540  ldc.i4.1
0x2541  callvirt instance void [System.Web.Cors]System.Web.Cors.CorsPolicy::set_AllowAnyHeader(bool)
0x2546  ldarg.0
0x2547  ldfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsPolicyProvider::_allowedMethods
0x254c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2551  brtrue.s loc_257E
0x2553  ldarg.0
0x2554  ldloc.0
0x2555  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> [System.Web.Cors]System.Web.Cors.CorsPolicy::get_Methods()
0x255a  ldarg.0
0x255b  ldfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsPolicyProvider::_allowedMethods
0x2560  call     instance void Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsPolicyProvider::GetList(class [mscorlib]System.Collections.Generic.IList`1<string> corsSettings, string delimitedSetting)
0x2565  ldloc.0
0x2566  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> [System.Web.Cors]System.Web.Cors.CorsPolicy::get_Methods()
0x256b  ldstr    asc_6076// "*"
0x2570  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<string>::Contains(var<u1>)
0x2575  brfalse.s loc_257E
0x2577  ldloc.0
0x2578  ldc.i4.1
0x2579  callvirt instance void [System.Web.Cors]System.Web.Cors.CorsPolicy::set_AllowAnyMethod(bool)
0x257e  ldarg.0
0x257f  ldfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsPolicyProvider::_exposedHeaders
0x2584  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2589  brtrue.s loc_259D
0x258b  ldarg.0
0x258c  ldloc.0
0x258d  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> [System.Web.Cors]System.Web.Cors.CorsPolicy::get_ExposedHeaders()
0x2592  ldarg.0
0x2593  ldfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsPolicyProvider::_exposedHeaders
0x2598  call     instance void Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsPolicyProvider::GetList(class [mscorlib]System.Collections.Generic.IList`1<string> corsSettings, string delimitedSetting)
0x259d  ldloc.0
0x259e  ldsfld   class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0x25a3  ldc.i4.1
0x25a4  stloc.1
0x25a5  ldloca.s 1
0x25a7  constrained. [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.CorsCongfigSettings
0x25ad  callvirt instance string [mscorlib]System.Object::ToString()
0x25b2  ldc.i4.0
0x25b3  callvirt instance bool [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrDefault(string, bool)
0x25b8  callvirt instance void [System.Web.Cors]System.Web.Cors.CorsPolicy::set_SupportsCredentials(bool)
0x25bd  ldarg.0
0x25be  ldfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsPolicyProvider::_maxAge
0x25c3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x25c8  brtrue.s loc_25E0
0x25ca  ldloc.0
0x25cb  ldarg.0
0x25cc  ldfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsPolicyProvider::_maxAge
0x25d1  call     int64 [mscorlib]System.Convert::ToInt64(string)
0x25d6  newobj   instance void valuetype [mscorlib]System.Nullable`1<int64>::.ctor(var<u1>)
0x25db  callvirt instance void [System.Web.Cors]System.Web.Cors.CorsPolicy::set_PreflightMaxAge(valuetype [mscorlib]System.Nullable`1<int64>)
0x25e0  ldloc.0
0x25e1  call     T0x2B00000A
0x25e6  ret
```
