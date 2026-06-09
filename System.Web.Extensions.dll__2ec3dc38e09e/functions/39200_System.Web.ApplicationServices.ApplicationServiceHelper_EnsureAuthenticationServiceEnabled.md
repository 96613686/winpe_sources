# System.Web.ApplicationServices.ApplicationServiceHelper::EnsureAuthenticationServiceEnabled

- ea: `0x39200`
- end: `0x39252`
- name: `System.Web.ApplicationServices.ApplicationServiceHelper::EnsureAuthenticationServiceEnabled`
- size: `82`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x2bb90`
- `0x2bbb0`
- `0x2bbd0`
- `0x38580`
- `0x385a0`
- `0x385c0`
- `0x385e0`

## callees

- `0x280f0`
- `0x28130`
- `0x39130`
- `0x39200`

## string_xrefs

- `0x39219`: `AuthenticationService`

## pseudocode

```c

```

## disassembly

```asm
0x39200  call     bool System.Web.ApplicationServices.ApplicationServiceHelper::get_AuthenticationServiceEnabled()
0x39205  brtrue.s loc_3922A
0x39207  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x3920c  call     string System.Web.Resources.AtlasWeb::get_AppService_Disabled()
0x39211  ldc.i4.1
0x39212  newarr   [mscorlib]System.Object
0x39217  dup
0x39218  ldc.i4.0
0x39219  ldstr    aAuthentication_2// "AuthenticationService"
0x3921e  stelem.ref
0x3921f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x39224  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x39229  throw
0x3922a  ldarg.1
0x3922b  brfalse.s loc_39251
0x3922d  ldsfld   bool System.Web.ApplicationServices.ApplicationServiceHelper::_authRequiresSSL
0x39232  brfalse.s loc_39251
0x39234  ldarg.0
0x39235  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x3923a  callvirt instance bool [System.Web]System.Web.HttpRequest::get_IsSecureConnection()
0x3923f  brtrue.s loc_39251
0x39241  ldc.i4   0x193
0x39246  call     string System.Web.Resources.AtlasWeb::get_AppService_RequiredSSL()
0x3924b  newobj   instance void [System.Web]System.Web.HttpException::.ctor(int32, string)
0x39250  throw
0x39251  ret
```
