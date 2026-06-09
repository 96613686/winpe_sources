# System.Web.UI.AuthenticationServiceManager::GenerateInitializationScript

- ea: `0xf840`
- end: `0xf8f5`
- name: `System.Web.UI.AuthenticationServiceManager::GenerateInitializationScript`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0xf7b0`

## callees

- `0xf840`
- `0x39130`

## string_xrefs

- `0xf85a`: `~/Authentication_JSON_AppService.axd`
- `0xf867`: `Sys.Services._AuthenticationService.DefaultWebServicePath = '`
- `0xf8ac`: `Sys.Services.AuthenticationService.set_path('`
- `0xf8e9`: `Sys.Services.AuthenticationService._setAuthenticated(true);\n`

## pseudocode

```c

```

## disassembly

```asm
0xf840  call     bool System.Web.ApplicationServices.ApplicationServiceHelper::get_AuthenticationServiceEnabled()
0xf845  stloc.0
0xf846  ldloc.0
0xf847  brfalse.s loc_F88D
0xf849  ldarg.0
0xf84a  ldind.ref
0xf84b  brtrue.s loc_F859
0xf84d  ldarg.0
0xf84e  ldc.i4   0x80
0xf853  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0xf858  stind.ref
0xf859  ldarg.2
0xf85a  ldstr    aAuthentication// "~/Authentication_JSON_AppService.axd"
0xf85f  callvirt instance string [System.Web]System.Web.UI.Control::ResolveClientUrl(string)
0xf864  stloc.2
0xf865  ldarg.0
0xf866  ldind.ref
0xf867  ldstr    aSysServicesAut// "Sys.Services._AuthenticationService.Def"...
0xf86c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf871  pop
0xf872  ldarg.0
0xf873  ldind.ref
0xf874  ldloc.2
0xf875  call     string [System.Web]System.Web.HttpUtility::JavaScriptStringEncode(string)
0xf87a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf87f  pop
0xf880  ldarg.0
0xf881  ldind.ref
0xf882  ldstr    asc_3FB16// "';\n"
0xf887  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf88c  pop
0xf88d  ldarg.3
0xf88e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xf893  ldc.i4.0
0xf894  ceq
0xf896  stloc.1
0xf897  ldloc.1
0xf898  brfalse.s loc_F8D2
0xf89a  ldarg.0
0xf89b  ldind.ref
0xf89c  brtrue.s loc_F8AA
0xf89e  ldarg.0
0xf89f  ldc.i4   0x80
0xf8a4  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0xf8a9  stind.ref
0xf8aa  ldarg.0
0xf8ab  ldind.ref
0xf8ac  ldstr    aSysServicesAut_0// "Sys.Services.AuthenticationService.set_"...
0xf8b1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf8b6  pop
0xf8b7  ldarg.0
0xf8b8  ldind.ref
0xf8b9  ldarg.3
0xf8ba  call     string [System.Web]System.Web.HttpUtility::JavaScriptStringEncode(string)
0xf8bf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf8c4  pop
0xf8c5  ldarg.0
0xf8c6  ldind.ref
0xf8c7  ldstr    asc_3FB7A// "');\n"
0xf8cc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf8d1  pop
0xf8d2  ldloc.0
0xf8d3  ldloc.1
0xf8d4  or
0xf8d5  brfalse.s loc_F8F4
0xf8d7  ldarg.1
0xf8d8  brfalse.s loc_F8F4
0xf8da  ldarg.1
0xf8db  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xf8e0  callvirt instance bool [System.Web]System.Web.HttpRequest::get_IsAuthenticated()
0xf8e5  brfalse.s loc_F8F4
0xf8e7  ldarg.0
0xf8e8  ldind.ref
0xf8e9  ldstr    aSysServicesAut_1// "Sys.Services.AuthenticationService._set"...
0xf8ee  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf8f3  pop
0xf8f4  ret
```
