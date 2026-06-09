# Microsoft.ReportingServices.Portal.WebHost.Owin.CsrfTokenCreationMiddleware::Invoke

- ea: `0x2670`
- end: `0x26df`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.CsrfTokenCreationMiddleware::Invoke`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x860`
- `0x2670`
- `0x4460`

## pseudocode

```c

```

## disassembly

```asm
0x2670  ldc.i4.2
0x2671  newarr   [mscorlib]System.String
0x2676  dup
0x2677  ldc.i4.0
0x2678  ldstr    aOwin// "owin"
0x267d  stelem.ref
0x267e  dup
0x267f  ldc.i4.1
0x2680  ldarg.0
0x2681  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2686  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x268b  stelem.ref
0x268c  call     class [mscorlib]System.IDisposable [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[])
0x2691  stloc.0
0x2692  ldarg.0
0x2693  ldfld    class Microsoft.ReportingServices.Portal.WebHost.Services.ICsrfTokenValidation Microsoft.ReportingServices.Portal.WebHost.Owin.CsrfTokenCreationMiddleware::_csrfTokenValidation
0x2698  ldarg.1
0x2699  callvirt instance void Microsoft.ReportingServices.Portal.WebHost.Services.ICsrfTokenValidation::SetToken(class [Microsoft.Owin]Microsoft.Owin.IOwinContext context)
0x269e  leave.s  loc_26D2
0x26a0  newobj   instance void <>c__DisplayClass3_0::.ctor()
0x26a5  stloc.1
0x26a6  stloc.2
0x26a7  ldloc.1
0x26a8  ldloc.2
0x26a9  stfld    class [mscorlib]System.Exception <>c__DisplayClass3_0::e
0x26ae  ldarg.0
0x26af  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Owin.CsrfTokenCreationMiddleware::_logger
0x26b4  ldc.i4.2
0x26b5  ldloc.1
0x26b6  ldftn    instance string <>c__DisplayClass3_0::<Invoke>b__0()
0x26bc  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0x26c1  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0x26c6  leave.s  loc_26D2
0x26c8  ldloc.0
0x26c9  brfalse.s loc_26D1
0x26cb  ldloc.0
0x26cc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26d1  endfinally
0x26d2  ldarg.0
0x26d3  call     instance class [Microsoft.Owin]Microsoft.Owin.OwinMiddleware [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::get_Next()
0x26d8  ldarg.1
0x26d9  callvirt instance class [mscorlib]System.Threading.Tasks.Task [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::Invoke(class [Microsoft.Owin]Microsoft.Owin.IOwinContext)
0x26de  ret
```
