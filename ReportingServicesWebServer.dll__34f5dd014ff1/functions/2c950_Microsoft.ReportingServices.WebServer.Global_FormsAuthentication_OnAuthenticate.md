# Microsoft.ReportingServices.WebServer.Global::FormsAuthentication_OnAuthenticate

- ea: `0x2c950`
- end: `0x2c9c3`
- name: `Microsoft.ReportingServices.WebServer.Global::FormsAuthentication_OnAuthenticate`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x2c950`
- `0x2c9d0`
- `0x2e110`

## string_xrefs

- `0x2c9ad`: `Temporary user`

## pseudocode

```c

```

## disassembly

```asm
0x2c950  call     bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.WebConfigUtil::get_UsingFormsAuth()
0x2c955  brfalse.s loc_2C9C2
0x2c957  ldarg.0
0x2c958  ldarg.2
0x2c959  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.Security.FormsAuthenticationEventArgs::get_Context()
0x2c95e  call     instance string Microsoft.ReportingServices.WebServer.Global::GetSoapActionHeader(class [System.Web]System.Web.HttpContext context)
0x2c963  stloc.0
0x2c964  ldloc.0
0x2c965  brfalse.s loc_2C9C2
0x2c967  ldloc.0
0x2c968  ldstr    aLogonuser// "LogonUser"
0x2c96d  ldc.i4.4
0x2c96e  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x2c973  ldc.i4.m1
0x2c974  beq.s    loc_2C9C2
0x2c976  ldarg.0
0x2c977  call     instance bool Microsoft.ReportingServices.WebServer.Global::IsReportServerAsmx()
0x2c97c  brfalse.s loc_2C9C2
0x2c97e  ldarg.2
0x2c97f  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.Security.FormsAuthenticationEventArgs::get_Context()
0x2c984  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x2c989  callvirt instance string [System.Web]System.Web.HttpRequest::get_HttpMethod()
0x2c98e  ldstr    aPost// "POST"
0x2c993  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c998  brfalse.s loc_2C9C2
0x2c99a  ldarg.2
0x2c99b  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.Security.FormsAuthenticationEventArgs::get_Context()
0x2c9a0  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web]System.Web.HttpContext::get_User()
0x2c9a5  brtrue.s loc_2C9C2
0x2c9a7  ldarg.2
0x2c9a8  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.Security.FormsAuthenticationEventArgs::get_Context()
0x2c9ad  ldstr    aTemporaryUser// "Temporary user"
0x2c9b2  newobj   instance void [mscorlib]System.Security.Principal.GenericIdentity::.ctor(string)
0x2c9b7  ldnull
0x2c9b8  newobj   instance void [mscorlib]System.Security.Principal.GenericPrincipal::.ctor(class [mscorlib]System.Security.Principal.IIdentity, string[])
0x2c9bd  callvirt instance void [System.Web]System.Web.HttpContext::set_User(class [mscorlib]System.Security.Principal.IPrincipal)
0x2c9c2  ret
```
