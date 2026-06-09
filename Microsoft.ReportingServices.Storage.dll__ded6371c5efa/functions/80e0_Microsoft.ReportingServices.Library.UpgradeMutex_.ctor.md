# Microsoft.ReportingServices.Library.UpgradeMutex::.ctor

- ea: `0x80e0`
- end: `0x8178`
- name: `Microsoft.ReportingServices.Library.UpgradeMutex::.ctor`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x33e0`

## callees

- `0x80e0`

## pseudocode

```c

```

## disassembly

```asm
0x80e0  ldarg.0
0x80e1  call     instance void [mscorlib]System.Object::.ctor()
0x80e6  ldstr    a0UpgradeLock// "{0}_Upgrade_Lock"
0x80eb  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x80f0  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_InstanceName()
0x80f5  call     string [mscorlib]System.String::Format(string, object)
0x80fa  stloc.0
0x80fb  ldc.i4.1
0x80fc  ldnull
0x80fd  newobj   instance void [mscorlib]System.Security.Principal.SecurityIdentifier::.ctor(valuetype [mscorlib]System.Security.Principal.WellKnownSidType, class [mscorlib]System.Security.Principal.SecurityIdentifier)
0x8102  ldc.i4   0x1F0001
0x8107  ldc.i4.0
0x8108  newobj   instance void [mscorlib]System.Security.AccessControl.MutexAccessRule::.ctor(class [mscorlib]System.Security.Principal.IdentityReference, valuetype [mscorlib]System.Security.AccessControl.MutexRights, valuetype [mscorlib]System.Security.AccessControl.AccessControlType)
0x810d  stloc.1
0x810e  newobj   instance void [mscorlib]System.Security.AccessControl.MutexSecurity::.ctor()
0x8113  stloc.2
0x8114  ldloc.2
0x8115  ldloc.1
0x8116  callvirt instance void [mscorlib]System.Security.AccessControl.MutexSecurity::AddAccessRule(class [mscorlib]System.Security.AccessControl.MutexAccessRule)
0x811b  ldc.i4.0
0x811c  stloc.3
0x811d  ldarg.0
0x811e  ldc.i4.0
0x811f  ldloc.0
0x8120  ldloca.s 3
0x8122  ldloc.2
0x8123  newobj   instance void [mscorlib]System.Threading.Mutex::.ctor(bool, string, bool&, class [mscorlib]System.Security.AccessControl.MutexSecurity)
0x8128  stfld    class [mscorlib]System.Threading.Mutex Microsoft.ReportingServices.Library.UpgradeMutex::_mutex
0x812d  ldc.i4.0
0x812e  stloc.s  4
0x8130  ldarg.0
0x8131  ldfld    class [mscorlib]System.Threading.Mutex Microsoft.ReportingServices.Library.UpgradeMutex::_mutex
0x8136  ldc.r8   10.0
0x813f  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x8144  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne(valuetype [mscorlib]System.TimeSpan)
0x8149  stloc.s  4
0x814b  leave.s  loc_8150
0x814d  pop
0x814e  leave.s  loc_8150
0x8150  ldloc.s  4
0x8152  brtrue.s loc_815F
0x8154  ldstr    aTimeoutTryingT// "Timeout trying to acquire the catalog u"...
0x8159  newobj   instance void [mscorlib]System.TimeoutException::.ctor(string)
0x815e  throw
0x815f  leave.s  loc_8177
0x8161  stloc.s  5
0x8163  ldstr    aExceptionAcqui// "Exception acquiring the catalog upgrade"...
0x8168  ldloc.0
0x8169  ldloc.s  5
0x816b  call     string [mscorlib]System.String::Format(string, object, object)
0x8170  call     void [System]System.Diagnostics.Trace::TraceError(string)
0x8175  rethrow
0x8177  ret
```
