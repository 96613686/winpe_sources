# Microsoft.Reporting.WebForms.ReportViewer::GetTelemetryConfiguration

- ea: `0x13f60`
- end: `0x13ffa`
- name: `Microsoft.Reporting.WebForms.ReportViewer::GetTelemetryConfiguration`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14110`

## callees

- `0x13f10`
- `0x141c0`

## string_xrefs

- `0x13fe3`: `HashedAppPath`

## pseudocode

```c

```

## disassembly

```asm
0x13f60  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x13f65  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x13f6a  stloc.0
0x13f6b  ldarg.1
0x13f6c  ldstr    aHost// "Host"
0x13f71  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x13f76  callvirt instance class [mscorlib]System.Reflection.AssemblyName [mscorlib]System.Reflection.Assembly::GetName()
0x13f7b  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_Name()
0x13f80  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x13f85  ldarg.1
0x13f86  ldstr    aBuild// "Build"
0x13f8b  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x13f90  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x13f95  call     class [System]System.Diagnostics.FileVersionInfo [System]System.Diagnostics.FileVersionInfo::GetVersionInfo(string)
0x13f9a  callvirt instance string [System]System.Diagnostics.FileVersionInfo::get_FileVersion()
0x13f9f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x13fa4  ldarg.1
0x13fa5  ldstr    aHasheduserid// "HashedUserId"
0x13faa  ldarg.0
0x13fab  ldarg.0
0x13fac  callvirt instance string Microsoft.Reporting.WebForms.ReportViewer::GetUserId()
0x13fb1  call     instance string Microsoft.Reporting.WebForms.ReportViewer::GetSHA256Hash(string input)
0x13fb6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x13fbb  ldarg.1
0x13fbc  ldstr    aHashedappsite// "HashedAppSite"
0x13fc1  ldarg.0
0x13fc2  ldloc.0
0x13fc3  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x13fc8  callvirt instance string [System]System.Uri::get_Authority()
0x13fcd  ldloc.0
0x13fce  callvirt instance string [System.Web]System.Web.HttpRequest::get_ApplicationPath()
0x13fd3  call     string [mscorlib]System.String::Concat(string, string)
0x13fd8  call     instance string Microsoft.Reporting.WebForms.ReportViewer::GetSHA256Hash(string input)
0x13fdd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x13fe2  ldarg.1
0x13fe3  ldstr    aHashedapppath// "HashedAppPath"
0x13fe8  ldarg.0
0x13fe9  ldloc.0
0x13fea  callvirt instance string [System.Web]System.Web.HttpRequest::get_Path()
0x13fef  call     instance string Microsoft.Reporting.WebForms.ReportViewer::GetSHA256Hash(string input)
0x13ff4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x13ff9  ret
```
