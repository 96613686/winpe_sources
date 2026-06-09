# Microsoft.ReportingServices.Portal.WebHost.Owin.CustomIndexMiddleware::AddErrorIEMessageIfRequired

- ea: `0x1f40`
- end: `0x2061`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.CustomIndexMiddleware::AddErrorIEMessageIfRequired`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1d10`

## callees

- `0x1f40`

## string_xrefs

- `0x1f6c`: `User-Agent`
- `0x1fdc`: `User-Agent`
- `0x1f85`: `MSIE `
- `0x2035`: `</h5>    <a id="browser-support-link" href="https://docs.microsoft.com/power-bi/report-server/browser-support">`

## pseudocode

```c

```

## disassembly

```asm
0x1f40  ldarg.2
0x1f41  brfalse.s loc_1FAD
0x1f43  ldarg.2
0x1f44  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x1f49  dup
0x1f4a  brtrue.s loc_1F58
0x1f4c  pop
0x1f4d  ldloca.s 2
0x1f4f  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1f55  ldloc.2
0x1f56  br.s     loc_1F94
0x1f58  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Headers()
0x1f5d  dup
0x1f5e  brtrue.s loc_1F6C
0x1f60  pop
0x1f61  ldloca.s 2
0x1f63  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1f69  ldloc.2
0x1f6a  br.s     loc_1F94
0x1f6c  ldstr    aUserAgent// "User-Agent"
0x1f71  callvirt instance string [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary::get_Item(string)
0x1f76  dup
0x1f77  brtrue.s loc_1F85
0x1f79  pop
0x1f7a  ldloca.s 2
0x1f7c  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1f82  ldloc.2
0x1f83  br.s     loc_1F94
0x1f85  ldstr    aMsie// "MSIE "
0x1f8a  call     instance int32 [mscorlib]System.String::IndexOf(string)
0x1f8f  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x1f94  stloc.0
0x1f95  ldc.i4.0
0x1f96  stloc.1
0x1f97  ldloca.s 0
0x1f99  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x1f9e  ldloc.1
0x1f9f  bgt.s    loc_1FA4
0x1fa1  ldc.i4.0
0x1fa2  br.s     loc_1FAB
0x1fa4  ldloca.s 0
0x1fa6  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x1fab  brtrue.s loc_201D
0x1fad  ldarg.2
0x1fae  brfalse  loc_205F
0x1fb3  ldarg.2
0x1fb4  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x1fb9  dup
0x1fba  brtrue.s loc_1FC8
0x1fbc  pop
0x1fbd  ldloca.s 2
0x1fbf  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1fc5  ldloc.2
0x1fc6  br.s     loc_2004
0x1fc8  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Headers()
0x1fcd  dup
0x1fce  brtrue.s loc_1FDC
0x1fd0  pop
0x1fd1  ldloca.s 2
0x1fd3  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1fd9  ldloc.2
0x1fda  br.s     loc_2004
0x1fdc  ldstr    aUserAgent// "User-Agent"
0x1fe1  callvirt instance string [Microsoft.Owin]Microsoft.Owin.IHeaderDictionary::get_Item(string)
0x1fe6  dup
0x1fe7  brtrue.s loc_1FF5
0x1fe9  pop
0x1fea  ldloca.s 2
0x1fec  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1ff2  ldloc.2
0x1ff3  br.s     loc_2004
0x1ff5  ldstr    aTrident// "Trident"
0x1ffa  call     instance int32 [mscorlib]System.String::IndexOf(string)
0x1fff  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x2004  stloc.0
0x2005  ldc.i4.0
0x2006  stloc.1
0x2007  ldloca.s 0
0x2009  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x200e  ldloc.1
0x200f  bgt.s    loc_2014
0x2011  ldc.i4.0
0x2012  br.s     loc_201B
0x2014  ldloca.s 0
0x2016  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x201b  brfalse.s loc_205F
0x201d  ldc.i4.5
0x201e  newarr   [mscorlib]System.String
0x2023  dup
0x2024  ldc.i4.0
0x2025  ldstr    aDivIdIeStubH5I// "<div id=\"ie-stub\">    <h5 id=\"ie-err"...
0x202a  stelem.ref
0x202b  dup
0x202c  ldc.i4.1
0x202d  call     string [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Services.SR::get_Error_IEIsNotSupported()
0x2032  stelem.ref
0x2033  dup
0x2034  ldc.i4.2
0x2035  ldstr    aH5AIdBrowserSu// "</h5>    <a id=\"browser-support-link\""...
0x203a  stelem.ref
0x203b  dup
0x203c  ldc.i4.3
0x203d  call     string [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Services.SR::get_SupportedBrowsers()
0x2042  stelem.ref
0x2043  dup
0x2044  ldc.i4.4
0x2045  ldstr    aADiv// "</a></div>"
0x204a  stelem.ref
0x204b  call     string [mscorlib]System.String::Concat(string[])
0x2050  stloc.3
0x2051  ldarg.1
0x2052  ldstr    aInjectIeStub// "<!-- Inject:IE-stub -->"
0x2057  ldloc.3
0x2058  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x205d  starg.s  1
0x205f  ldarg.1
0x2060  ret
```
