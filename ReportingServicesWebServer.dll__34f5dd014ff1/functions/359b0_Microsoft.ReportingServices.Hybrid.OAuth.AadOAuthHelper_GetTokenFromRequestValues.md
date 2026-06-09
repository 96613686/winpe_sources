# Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthHelper::GetTokenFromRequestValues

- ea: `0x359b0`
- end: `0x35a50`
- name: `Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthHelper::GetTokenFromRequestValues`
- size: `160`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x35fa0`
- `0x36080`

## callees

- `0x358a0`
- `0x359b0`
- `0x35ae0`

## string_xrefs

- `0x359c5`: `AAD: tokenUrl or payload values are null`
- `0x35a0a`: `AAD returned '{0}'. You may need to reregister your application with PowerBI in the RS Config Tool.`

## pseudocode

```c

```

## disassembly

```asm
0x359b0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x359b5  ldarg.0
0x359b6  ldnull
0x359b7  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x359bc  brfalse.s loc_359C4
0x359be  ldarg.1
0x359bf  ldnull
0x359c0  cgt.un
0x359c2  br.s     loc_359C5
0x359c4  ldc.i4.0
0x359c5  ldstr    aAadTokenurlOrP// "AAD: tokenUrl or payload values are nul"...
0x359ca  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x359cf  ldarg.2
0x359d0  ldarg.0
0x359d1  ldstr    aPost// "POST"
0x359d6  ldarg.1
0x359d7  callvirt instance unsigned int8[] Microsoft.ReportingServices.Hybrid.OAuth.IServiceTokenStore::UploadValuesPort(class [System]System.Uri tokenUrl, string httpWebRequestMethod, class [System]System.Collections.Specialized.NameValueCollection values)
0x359dc  call     class Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthHelper::GetOAuthTokenResponseFromResponseBytes(unsigned int8[] responseBytes)
0x359e1  stloc.0
0x359e2  leave.s  loc_35A4E
0x359e4  pop
0x359e5  ldstr    aPbiuser// "PBIUser"
0x359ea  ldc.i4.s 0x59
0x359ec  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.AccessDeniedException::.ctor(string, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode)
0x359f1  throw
0x359f2  stloc.1
0x359f3  ldloc.1
0x359f4  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x359f9  callvirt instance string [mscorlib]System.Object::ToString()
0x359fe  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x35a03  brtrue.s loc_35A28
0x35a05  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_UITracer()
0x35a0a  ldstr    aAadReturned0Yo// "AAD returned '{0}'. You may need to rer"...
0x35a0f  ldc.i4.1
0x35a10  newarr   [mscorlib]System.Object
0x35a15  dup
0x35a16  ldc.i4.0
0x35a17  ldloc.1
0x35a18  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x35a1d  callvirt instance string [mscorlib]System.Object::ToString()
0x35a22  stelem.ref
0x35a23  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x35a28  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_UITracer()
0x35a2d  ldstr    aWebexception0// "WebException: {0}"
0x35a32  ldc.i4.1
0x35a33  newarr   [mscorlib]System.Object
0x35a38  dup
0x35a39  ldc.i4.0
0x35a3a  ldloc.1
0x35a3b  stelem.ref
0x35a3c  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x35a41  ldstr    aPbiuser// "PBIUser"
0x35a46  ldc.i4.s 0x59
0x35a48  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.AccessDeniedException::.ctor(string, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode)
0x35a4d  throw
0x35a4e  ldloc.0
0x35a4f  ret
```
