# Microsoft.BIServer.Configuration.RsService::SetServiceAccountPassword

- ea: `0x32c0`
- end: `0x333f`
- name: `Microsoft.BIServer.Configuration.RsService::SetServiceAccountPassword`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x32c0`
- `0x3500`

## string_xrefs

- `0x32f2`: `Win32_Service.Name='{0}'`

## pseudocode

```c

```

## disassembly

```asm
0x32c0  ldarg.1
0x32c1  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials::get_DomainUser()
0x32c6  stloc.0
0x32c7  ldarg.1
0x32c8  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials::get_Password()
0x32cd  stloc.1
0x32ce  ldloc.0
0x32cf  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x32d4  brfalse.s loc_32F2
0x32d6  call     string Microsoft.BIServer.Configuration.RsService::get_NtServiceName()
0x32db  ldstr    asc_94A6// "\\"
0x32e0  ldarg.0
0x32e1  ldfld    string Microsoft.BIServer.Configuration.RsService::_serviceName
0x32e6  call     string [mscorlib]System.String::Concat(string, string, string)
0x32eb  stloc.0
0x32ec  ldsfld   string [mscorlib]System.String::Empty
0x32f1  stloc.1
0x32f2  ldstr    aWin32ServiceNa// "Win32_Service.Name='{0}'"
0x32f7  ldarg.0
0x32f8  ldfld    string Microsoft.BIServer.Configuration.RsService::_serviceName
0x32fd  call     string [mscorlib]System.String::Format(string, object)
0x3302  newobj   instance void [System.Management]System.Management.ManagementPath::.ctor(string)
0x3307  newobj   instance void [System.Management]System.Management.ManagementObject::.ctor(class [System.Management]System.Management.ManagementPath)
0x330c  stloc.2
0x330d  ldc.i4.s 0xB
0x330f  newarr   [mscorlib]System.Object
0x3314  stloc.3
0x3315  ldloc.3
0x3316  ldc.i4.6
0x3317  ldloc.0
0x3318  stelem.ref
0x3319  ldloc.1
0x331a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x331f  brtrue.s loc_3325
0x3321  ldloc.3
0x3322  ldc.i4.7
0x3323  ldloc.1
0x3324  stelem.ref
0x3325  ldloc.2
0x3326  ldstr    aChange// "Change"
0x332b  ldloc.3
0x332c  callvirt instance object [System.Management]System.Management.ManagementObject::InvokeMethod(string, object[])
0x3331  pop
0x3332  leave.s  loc_333E
0x3334  ldloc.2
0x3335  brfalse.s loc_333D
0x3337  ldloc.2
0x3338  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x333d  endfinally
0x333e  ret
```
