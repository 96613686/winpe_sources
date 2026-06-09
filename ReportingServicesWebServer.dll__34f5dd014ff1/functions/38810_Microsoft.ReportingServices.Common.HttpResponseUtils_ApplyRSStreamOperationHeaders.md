# Microsoft.ReportingServices.Common.HttpResponseUtils::ApplyRSStreamOperationHeaders

- ea: `0x38810`
- end: `0x388a9`
- name: `Microsoft.ReportingServices.Common.HttpResponseUtils::ApplyRSStreamOperationHeaders`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x32630`

## callees

- `0x38810`
- `0x388b0`
- `0x38aa0`

## string_xrefs

- `0x38823`: `FileExtension`

## pseudocode

```c

```

## disassembly

```asm
0x38810  ldarg.0
0x38811  ldarg.1
0x38812  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x38817  ldarg.0
0x38818  ldarg.2
0x38819  call     void Microsoft.ReportingServices.Common.HttpResponseUtils::ApplyContentEncodingHeaders(class [System.Web]System.Web.HttpResponse response, class [mscorlib]System.Text.Encoding encoding)
0x3881e  ldarg.s  4
0x38820  brfalse.s loc_3882F
0x38822  ldarg.0
0x38823  ldstr    aFileextension// "FileExtension"
0x38828  ldarg.s  4
0x3882a  callvirt instance void [System.Web]System.Web.HttpResponse::AddHeader(string, string)
0x3882f  ldarg.3
0x38830  ldstr    asc_42AB6// "."
0x38835  ldarg.s  4
0x38837  call     string [mscorlib]System.String::Concat(string, string, string)
0x3883c  stloc.0
0x3883d  ldstr    aTextHtml// "text/html"
0x38842  ldarg.1
0x38843  ldc.i4.4
0x38844  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x38849  brfalse.s loc_38855
0x3884b  ldloc.0
0x3884c  ldarg.0
0x3884d  ldc.i4.0
0x3884e  call     void Microsoft.ReportingServices.Common.HttpResponseUtils::AddContentDisposition(string fileName, class [System.Web]System.Web.HttpResponse response, valuetype Microsoft.ReportingServices.Common.ContentDisposition contentDisposition)
0x38853  br.s     loc_3885D
0x38855  ldloc.0
0x38856  ldarg.0
0x38857  ldc.i4.1
0x38858  call     void Microsoft.ReportingServices.Common.HttpResponseUtils::AddContentDisposition(string fileName, class [System.Web]System.Web.HttpResponse response, valuetype Microsoft.ReportingServices.Common.ContentDisposition contentDisposition)
0x3885d  ldarg.0
0x3885e  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x38863  ldc.i4.2
0x38864  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetCacheability(valuetype [System.Web]System.Web.HttpCacheability)
0x38869  ldarg.1
0x3886a  ldstr    aMultipartRelat// "multipart/related"
0x3886f  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x38874  brfalse.s loc_388A1
0x38876  ldarg.s  4
0x38878  ldstr    aMhtml_0// "mhtml"
0x3887d  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x38882  brfalse.s loc_388A1
0x38884  ldarg.1
0x38885  ldstr    aImagePng// "image/png"
0x3888a  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3888f  brfalse.s loc_388A1
0x38891  ldarg.0
0x38892  callvirt instance class [System.Web]System.Web.HttpCachePolicy [System.Web]System.Web.HttpResponse::get_Cache()
0x38897  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x3889c  callvirt instance void [System.Web]System.Web.HttpCachePolicy::SetLastModified(valuetype [mscorlib]System.DateTime)
0x388a1  ldarg.0
0x388a2  ldc.i4.m1
0x388a3  callvirt instance void [System.Web]System.Web.HttpResponse::set_Expires(int32)
0x388a8  ret
```
