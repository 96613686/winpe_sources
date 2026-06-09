# Microsoft.ReportingServices.Portal.WebHost.Owin.UrlRewriterMiddleware::Invoke

- ea: `0x31f0`
- end: `0x32c3`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.UrlRewriterMiddleware::Invoke`
- size: `211`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x31f0`
- `0x3550`

## pseudocode

```c

```

## disassembly

```asm
0x31f0  ldc.i4.2
0x31f1  newarr   [mscorlib]System.String
0x31f6  dup
0x31f7  ldc.i4.0
0x31f8  ldstr    aOwin// "owin"
0x31fd  stelem.ref
0x31fe  dup
0x31ff  ldc.i4.1
0x3200  ldarg.0
0x3201  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3206  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x320b  stelem.ref
0x320c  call     class [mscorlib]System.IDisposable [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[])
0x3211  stloc.0
0x3212  ldarg.1
0x3213  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x3218  callvirt instance class [System]System.Uri [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Uri()
0x321d  stloc.1
0x321e  ldarg.1
0x321f  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x3224  callvirt instance class [System]System.Uri [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Uri()
0x3229  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x322e  ldstr    aBrandCss// "brand.css"
0x3233  callvirt instance bool [mscorlib]System.String::EndsWith(string)
0x3238  brfalse.s loc_3287
0x323a  call     valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.ProductType [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuStore::GetProductType()
0x323f  ldc.i4.2
0x3240  beq.s    loc_3249
0x3242  ldstr    aSsrs// "SSRS"
0x3247  br.s     loc_324E
0x3249  ldstr    aPbirs// "PBIRS"
0x324e  stloc.2
0x324f  ldarg.1
0x3250  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x3255  ldarg.1
0x3256  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x325b  callvirt instance valuetype [Microsoft.Owin]Microsoft.Owin.PathString [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Path()
0x3260  stloc.3
0x3261  ldloca.s 3
0x3263  call     instance string [Microsoft.Owin]Microsoft.Owin.PathString::get_Value()
0x3268  ldstr    aBrand// "brand"
0x326d  ldstr    aBrand_0// "brand_"
0x3272  ldloc.2
0x3273  call     string [mscorlib]System.String::Concat(string, string)
0x3278  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x327d  newobj   instance void [Microsoft.Owin]Microsoft.Owin.PathString::.ctor(string)
0x3282  callvirt instance void [Microsoft.Owin]Microsoft.Owin.IOwinRequest::set_Path(valuetype [Microsoft.Owin]Microsoft.Owin.PathString)
0x3287  ldarg.0
0x3288  ldfld    class Microsoft.ReportingServices.Portal.WebHost.Owin.IUrlRewritingRule Microsoft.ReportingServices.Portal.WebHost.Owin.UrlRewriterMiddleware::_rewritingRules
0x328d  ldloc.1
0x328e  callvirt instance bool Microsoft.ReportingServices.Portal.WebHost.Owin.IUrlRewritingRule::IsRewriteNeeded(class [System]System.Uri uri)
0x3293  brfalse.s loc_32AA
0x3295  ldarg.1
0x3296  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x329b  ldstr    asc_571A// "/"
0x32a0  newobj   instance void [Microsoft.Owin]Microsoft.Owin.PathString::.ctor(string)
0x32a5  callvirt instance void [Microsoft.Owin]Microsoft.Owin.IOwinRequest::set_Path(valuetype [Microsoft.Owin]Microsoft.Owin.PathString)
0x32aa  leave.s  loc_32B6
0x32ac  ldloc.0
0x32ad  brfalse.s loc_32B5
0x32af  ldloc.0
0x32b0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32b5  endfinally
0x32b6  ldarg.0
0x32b7  call     instance class [Microsoft.Owin]Microsoft.Owin.OwinMiddleware [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::get_Next()
0x32bc  ldarg.1
0x32bd  callvirt instance class [mscorlib]System.Threading.Tasks.Task [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::Invoke(class [Microsoft.Owin]Microsoft.Owin.IOwinContext)
0x32c2  ret
```
