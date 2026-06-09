# Microsoft.BIServer.HostingEnvironment.ImpersonationContext::.ctor

- ea: `0xac0`
- end: `0xb1f`
- name: `Microsoft.BIServer.HostingEnvironment.ImpersonationContext::.ctor`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xa80`

## callees

- `0x80`
- `0x90`
- `0xa0`
- `0xac0`
- `0xbc0`

## string_xrefs

- `0xaf2`: `Could not impersonate the user.  LogonUser returned error code {0}.`

## pseudocode

```c

```

## disassembly

```asm
0xac0  ldarg.0
0xac1  call     instance void [mscorlib]System.Object::.ctor()
0xac6  ldarg.1
0xac7  callvirt instance string Microsoft.BIServer.HostingEnvironment.AccountCredentials::get_UserId()
0xacc  ldarg.1
0xacd  callvirt instance string Microsoft.BIServer.HostingEnvironment.AccountCredentials::get_Domain()
0xad2  ldarg.1
0xad3  callvirt instance string Microsoft.BIServer.HostingEnvironment.AccountCredentials::get_Password()
0xad8  ldc.i4.8
0xad9  ldc.i4.0
0xada  ldarg.0
0xadb  ldflda   class Microsoft.BIServer.HostingEnvironment.SafeTokenHandle Microsoft.BIServer.HostingEnvironment.ImpersonationContext::_handle
0xae0  call     bool Microsoft.BIServer.HostingEnvironment.ImpersonationContext::LogonUser(string lpszUsername, string lpszDomain, string lpszPassword, int32 dwLogonType, int32 dwLogonProvider, [out] class Microsoft.BIServer.HostingEnvironment.SafeTokenHandle& phToken)
0xae5  brtrue.s loc_B08
0xae7  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0xaec  stloc.0
0xaed  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xaf2  ldstr    aCouldNotImpers// "Could not impersonate the user.  LogonU"...
0xaf7  ldloc.0
0xaf8  box      [mscorlib]System.Int32
0xafd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0xb02  newobj   instance void [mscorlib]System.ApplicationException::.ctor(string)
0xb07  throw
0xb08  ldarg.0
0xb09  ldarg.0
0xb0a  ldfld    class Microsoft.BIServer.HostingEnvironment.SafeTokenHandle Microsoft.BIServer.HostingEnvironment.ImpersonationContext::_handle
0xb0f  callvirt instance native int [mscorlib]System.Runtime.InteropServices.SafeHandle::DangerousGetHandle()
0xb14  call     class [mscorlib]System.Security.Principal.WindowsImpersonationContext [mscorlib]System.Security.Principal.WindowsIdentity::Impersonate(native int)
0xb19  stfld    class [mscorlib]System.Security.Principal.WindowsImpersonationContext Microsoft.BIServer.HostingEnvironment.ImpersonationContext::_context
0xb1e  ret
```
