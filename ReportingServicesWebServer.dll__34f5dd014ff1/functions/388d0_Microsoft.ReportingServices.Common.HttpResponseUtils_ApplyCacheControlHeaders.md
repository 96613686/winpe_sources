# Microsoft.ReportingServices.Common.HttpResponseUtils::ApplyCacheControlHeaders

- ea: `0x388d0`
- end: `0x389c6`
- name: `Microsoft.ReportingServices.Common.HttpResponseUtils::ApplyCacheControlHeaders`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x32080`

## callees

- `0x388d0`

## string_xrefs

- `0x388d6`: `rs:Command`
- `0x3899b`: `pv:Command`

## pseudocode

```c

```

## disassembly

```asm
0x388d0  ldarg.0
0x388d1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x388d6  ldstr    aRsCommand// "rs:Command"
0x388db  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x388e0  stloc.0
0x388e1  ldloc.0
0x388e2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x388e7  brtrue   loc_38995
0x388ec  ldloc.0
0x388ed  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x388f2  stloc.1
0x388f3  ldloc.1
0x388f4  ldstr    aBlank// "BLANK"
0x388f9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x388fe  brtrue.s loc_38928
0x38900  ldloc.1
0x38901  ldstr    aGet// "GET"
0x38906  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3890b  brtrue.s loc_3894E
0x3890d  ldloc.1
0x3890e  ldstr    aStylesheet_1// "STYLESHEET"
0x38913  call     bool [mscorlib]System.String::op_Equality(string, string)
0x38918  brtrue.s loc_38988
0x3891a  ldloc.1
0x3891b  ldstr    aStylesheetimag_0// "STYLESHEETIMAGE"
0x38920  call     bool [mscorlib]System.String::op_Equality(string, string)
0x38925  brtrue.s loc_38988
0x38927  ret
0x38928  ldarg.1
0x38929  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x3892e  ldc.i4.4
0x3892f  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetCacheability(valuetype [System.Web]System.Web.HttpCacheability)
0x38934  ldarg.1
0x38935  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x3893a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Today()
0x3893f  stloc.2
0x38940  ldloca.s 2
0x38942  ldc.i4.1
0x38943  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMonths(int32)
0x38948  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetExpires(valuetype [mscorlib]System.DateTime)
0x3894d  ret
0x3894e  ldarg.1
0x3894f  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x38954  ldc.i4.2
0x38955  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetCacheability(valuetype [System.Web]System.Web.HttpCacheability)
0x3895a  ldarg.0
0x3895b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x38960  ldstr    aRcGetimage// "rc:GetImage"
0x38965  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3896a  brtrue.s loc_389C5
0x3896c  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x38971  stloc.2
0x38972  ldloca.s 2
0x38974  ldc.i4.1
0x38975  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMonths(int32)
0x3897a  stloc.3
0x3897b  ldarg.1
0x3897c  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x38981  ldloc.3
0x38982  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetExpires(valuetype [mscorlib]System.DateTime)
0x38987  ret
0x38988  ldarg.1
0x38989  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x3898e  ldc.i4.2
0x3898f  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetCacheability(valuetype [System.Web]System.Web.HttpCacheability)
0x38994  ret
0x38995  ldarg.0
0x38996  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3899b  ldstr    aPvCommand// "pv:Command"
0x389a0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x389a5  stloc.0
0x389a6  ldloc.0
0x389a7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x389ac  brtrue.s loc_389C5
0x389ae  ldarg.1
0x389af  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x389b4  ldc.i4.1
0x389b5  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetCacheability(valuetype [System.Web]System.Web.HttpCacheability)
0x389ba  ldarg.1
0x389bb  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x389c0  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetNoStore()
0x389c5  ret
```
