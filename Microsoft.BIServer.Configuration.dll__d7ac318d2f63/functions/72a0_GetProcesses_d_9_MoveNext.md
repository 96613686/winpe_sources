# <GetProcesses>d__9::MoveNext

- ea: `0x72a0`
- end: `0x7389`
- name: `<GetProcesses>d__9::MoveNext`
- size: `233`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callees

- `0x7280`
- `0x72a0`
- `0x7390`

## string_xrefs

- `0x72c6`: `SELECT ProcessId FROM Win32_Service WHERE Name='{0}'`
- `0x7307`: `ProcessId`
- `0x7326`: `Service process '{0}' not found`

## pseudocode

```c

```

## disassembly

```asm
0x72a0  ldarg.0
0x72a1  ldfld    int32 <GetProcesses>d__9::<>1__state
0x72a6  stloc.1
0x72a7  ldarg.0
0x72a8  ldfld    class Microsoft.BIServer.Configuration.RsService <GetProcesses>d__9::<>4__this
0x72ad  stloc.2
0x72ae  ldloc.1
0x72af  brfalse.s loc_72BF
0x72b1  ldloc.1
0x72b2  ldc.i4.1
0x72b3  beq      loc_735A
0x72b8  ldc.i4.0
0x72b9  stloc.0
0x72ba  leave    loc_7387
0x72bf  ldarg.0
0x72c0  ldc.i4.m1
0x72c1  stfld    int32 <GetProcesses>d__9::<>1__state
0x72c6  ldstr    aSelectProcessi// "SELECT ProcessId FROM Win32_Service WHE"...
0x72cb  ldloc.2
0x72cc  ldfld    string Microsoft.BIServer.Configuration.RsService::_serviceName
0x72d1  call     string [mscorlib]System.String::Format(string, object)
0x72d6  newobj   instance void [System.Management]System.Management.ManagementObjectSearcher::.ctor(string)
0x72db  stloc.3
0x72dc  ldarg.0
0x72dd  ldloc.3
0x72de  callvirt instance class [System.Management]System.Management.ManagementObjectCollection [System.Management]System.Management.ManagementObjectSearcher::Get()
0x72e3  callvirt instance class [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator [System.Management]System.Management.ManagementObjectCollection::GetEnumerator()
0x72e8  stfld    class [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator <GetProcesses>d__9::<>7__wrap1
0x72ed  ldarg.0
0x72ee  ldc.i4.s 0xFD
0x72f0  stfld    int32 <GetProcesses>d__9::<>1__state
0x72f5  br.s     loc_7362
0x72f7  ldarg.0
0x72f8  ldfld    class [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator <GetProcesses>d__9::<>7__wrap1
0x72fd  callvirt instance class [System.Management]System.Management.ManagementBaseObject [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator::get_Current()
0x7302  castclass [System.Management]System.Management.ManagementObject
0x7307  ldstr    aProcessid// "ProcessId"
0x730c  callvirt instance object [System.Management]System.Management.ManagementBaseObject::get_Item(string)
0x7311  unbox.any [mscorlib]System.UInt32
0x7316  stloc.s  4
0x7318  ldnull
0x7319  stloc.s  5
0x731b  ldloc.s  4
0x731d  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::GetProcessById(int32)
0x7322  stloc.s  5
0x7324  leave.s  loc_7343
0x7326  ldstr    aServiceProcess// "Service process '{0}' not found"
0x732b  ldloc.s  4
0x732d  box      [mscorlib]System.UInt32
0x7332  call     string [mscorlib]System.String::Format(string, object)
0x7337  call     T0x2B000015
0x733c  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Warning(class [mscorlib]System.Exception, string, object[])
0x7341  leave.s  loc_7343
0x7343  ldloc.s  5
0x7345  brfalse.s loc_7362
0x7347  ldarg.0
0x7348  ldloc.s  5
0x734a  stfld    class [System]System.Diagnostics.Process <GetProcesses>d__9::<>2__current
0x734f  ldarg.0
0x7350  ldc.i4.1
0x7351  stfld    int32 <GetProcesses>d__9::<>1__state
0x7356  ldc.i4.1
0x7357  stloc.0
0x7358  leave.s  loc_7387
0x735a  ldarg.0
0x735b  ldc.i4.s 0xFD
0x735d  stfld    int32 <GetProcesses>d__9::<>1__state
0x7362  ldarg.0
0x7363  ldfld    class [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator <GetProcesses>d__9::<>7__wrap1
0x7368  callvirt instance bool [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator::MoveNext()
0x736d  brtrue.s loc_72F7
0x736f  ldarg.0
0x7370  call     instance void <GetProcesses>d__9::<>m__Finally1()
0x7375  ldarg.0
0x7376  ldnull
0x7377  stfld    class [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator <GetProcesses>d__9::<>7__wrap1
0x737c  ldc.i4.0
0x737d  stloc.0
0x737e  leave.s  loc_7387
0x7380  ldarg.0
0x7381  call     instance void <GetProcesses>d__9::System.IDisposable.Dispose()
0x7386  endfinally
0x7387  ldloc.0
0x7388  ret
```
