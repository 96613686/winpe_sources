# System.Web.Script.Services.WebServiceData::GetApplicationService

- ea: `0x2e400`
- end: `0x2e473`
- name: `System.Web.Script.Services.WebServiceData::GetApplicationService`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x2e4b0`

## callees

- `0x2e400`
- `0x2e660`

## string_xrefs

- `0x2e415`: `Profile_JSON_AppService.axd`
- `0x2e434`: `Authentication_JSON_AppService.axd`
- `0x2e453`: `Role_JSON_AppService.axd`

## pseudocode

```c

```

## disassembly

```asm
0x2e400  ldarg.0
0x2e401  ldc.i4.s 0x2F
0x2e403  callvirt instance int32 [mscorlib]System.String::LastIndexOf(char)
0x2e408  stloc.0
0x2e409  ldloc.0
0x2e40a  ldc.i4.1
0x2e40b  bne.un.s loc_2E471
0x2e40d  ldarg.0
0x2e40e  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x2e413  stloc.1
0x2e414  ldloc.1
0x2e415  ldstr    aProfileJsonApp_0// "Profile_JSON_AppService.axd"
0x2e41a  ldc.i4.5
0x2e41b  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x2e420  brfalse.s loc_2E433
0x2e422  ldtoken  System.Web.Profile.ProfileService
0x2e427  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2e42c  ldc.i4.0
0x2e42d  newobj   instance void System.Web.Script.Services.WebServiceData::.ctor(class [mscorlib]System.Type type, bool pageMethods)
0x2e432  ret
0x2e433  ldloc.1
0x2e434  ldstr    aAuthentication_1// "Authentication_JSON_AppService.axd"
0x2e439  ldc.i4.5
0x2e43a  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x2e43f  brfalse.s loc_2E452
0x2e441  ldtoken  System.Web.Security.AuthenticationService
0x2e446  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2e44b  ldc.i4.0
0x2e44c  newobj   instance void System.Web.Script.Services.WebServiceData::.ctor(class [mscorlib]System.Type type, bool pageMethods)
0x2e451  ret
0x2e452  ldloc.1
0x2e453  ldstr    aRoleJsonAppser_0// "Role_JSON_AppService.axd"
0x2e458  ldc.i4.5
0x2e459  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x2e45e  brfalse.s loc_2E471
0x2e460  ldtoken  System.Web.Security.RoleService
0x2e465  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2e46a  ldc.i4.0
0x2e46b  newobj   instance void System.Web.Script.Services.WebServiceData::.ctor(class [mscorlib]System.Type type, bool pageMethods)
0x2e470  ret
0x2e471  ldnull
0x2e472  ret
```
