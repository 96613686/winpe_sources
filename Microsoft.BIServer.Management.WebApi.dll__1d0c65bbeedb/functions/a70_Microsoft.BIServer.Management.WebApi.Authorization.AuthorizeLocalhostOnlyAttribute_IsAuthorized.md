# Microsoft.BIServer.Management.WebApi.Authorization.AuthorizeLocalhostOnlyAttribute::IsAuthorized

- ea: `0xa70`
- end: `0xab0`
- name: `Microsoft.BIServer.Management.WebApi.Authorization.AuthorizeLocalhostOnlyAttribute::IsAuthorized`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0xa70`

## pseudocode

```c

```

## disassembly

```asm
0xa70  ldarg.1
0xa71  callvirt instance class [System.Web.Http]System.Web.Http.Controllers.HttpRequestContext [System.Web.Http]System.Web.Http.Controllers.HttpActionContext::get_RequestContext()
0xa76  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.Controllers.HttpRequestContext::get_Principal()
0xa7b  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0xa80  isinst   [mscorlib]System.Security.Principal.WindowsIdentity
0xa85  stloc.0
0xa86  ldloc.0
0xa87  brtrue.s loc_A8B
0xa89  ldc.i4.0
0xa8a  ret
0xa8b  ldarg.1
0xa8c  callvirt instance class [System.Web.Http]System.Web.Http.Controllers.HttpRequestContext [System.Web.Http]System.Web.Http.Controllers.HttpActionContext::get_RequestContext()
0xa91  callvirt instance bool [System.Web.Http]System.Web.Http.Controllers.HttpRequestContext::get_IsLocal()
0xa96  brfalse.s loc_AAE
0xa98  ldloc.0
0xa99  callvirt instance class [mscorlib]System.Security.Principal.SecurityIdentifier [mscorlib]System.Security.Principal.WindowsIdentity::get_User()
0xa9e  call     class [mscorlib]System.Security.Principal.WindowsIdentity [mscorlib]System.Security.Principal.WindowsIdentity::GetCurrent()
0xaa3  callvirt instance class [mscorlib]System.Security.Principal.SecurityIdentifier [mscorlib]System.Security.Principal.WindowsIdentity::get_User()
0xaa8  call     bool [mscorlib]System.Security.Principal.SecurityIdentifier::op_Equality(class [mscorlib]System.Security.Principal.SecurityIdentifier, class [mscorlib]System.Security.Principal.SecurityIdentifier)
0xaad  ret
0xaae  ldc.i4.0
0xaaf  ret
```
