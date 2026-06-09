# Microsoft.ReportingServices.Common.HttpResponseUtils::ApplyReportBuilderFileResponseHeaders

- ea: `0x389d0`
- end: `0x38a7b`
- name: `Microsoft.ReportingServices.Common.HttpResponseUtils::ApplyReportBuilderFileResponseHeaders`
- size: `171`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x389d0`

## string_xrefs

- `0x389d1`: `.manifest`
- `0x389e4`: `application/x-ms-manifest`

## pseudocode

```c

```

## disassembly

```asm
0x389d0  ldarg.0
0x389d1  ldstr    aManifest// ".manifest"
0x389d6  ldc.i4.5
0x389d7  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x389dc  brfalse.s loc_38A16
0x389de  ldarg.1
0x389df  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x389e4  ldstr    aApplicationXMs// "application/x-ms-manifest"
0x389e9  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x389ee  ldarg.1
0x389ef  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x389f4  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x389f9  ldarg.1
0x389fa  callvirt instance valuetype [mscorlib]System.DateTime [System.Web]System.Web.HttpContext::get_Timestamp()
0x389ff  stloc.0
0x38a00  ldloca.s 0
0x38a02  ldc.r8   -1.0
0x38a0b  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x38a10  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetExpires(valuetype [mscorlib]System.DateTime)
0x38a15  ret
0x38a16  ldarg.0
0x38a17  ldstr    aApplication// ".application"
0x38a1c  ldc.i4.5
0x38a1d  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x38a22  brfalse.s loc_38A5C
0x38a24  ldarg.1
0x38a25  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x38a2a  ldstr    aApplicationXMs_0// "application/x-ms-application"
0x38a2f  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x38a34  ldarg.1
0x38a35  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x38a3a  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x38a3f  ldarg.1
0x38a40  callvirt instance valuetype [mscorlib]System.DateTime [System.Web]System.Web.HttpContext::get_Timestamp()
0x38a45  stloc.0
0x38a46  ldloca.s 0
0x38a48  ldc.r8   -1.0
0x38a51  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x38a56  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetExpires(valuetype [mscorlib]System.DateTime)
0x38a5b  ret
0x38a5c  ldarg.0
0x38a5d  ldstr    aDeploy// ".deploy"
0x38a62  ldc.i4.5
0x38a63  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x38a68  brfalse.s loc_38A7A
0x38a6a  ldarg.1
0x38a6b  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x38a70  ldstr    aApplicationOct// "application/octet-stream"
0x38a75  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x38a7a  ret
```
