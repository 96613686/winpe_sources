# Microsoft.ReportingServices.Library.UpdatePoliciesTimer::DoTimerAction

- ea: `0xfea0`
- end: `0xff32`
- name: `Microsoft.ReportingServices.Library.UpdatePoliciesTimer::DoTimerAction`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x45d0`
- `0xfea0`
- `0x10020`
- `0x48ac0`
- `0x49190`

## string_xrefs

- `0xfea6`: `Starting policy update based on the update policies timer`
- `0xff00`: `Error on policy update.\n`
- `0xff27`: `Policy update based on the update policies timer executed`

## pseudocode

```c

```

## disassembly

```asm
0xfea0  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0xfea5  ldc.i4.4
0xfea6  ldstr    aStartingPolicy// "Starting policy update based on the upd"...
0xfeab  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xfeb0  ldc.i4.1
0xfeb1  ldc.i4   0x1000
0xfeb6  newobj   instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::.ctor(valuetype [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionTransactionType, valuetype [System.Data]System.Data.IsolationLevel)
0xfebb  stloc.0
0xfebc  ldloc.0
0xfebd  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage()
0xfec2  newobj   instance void Microsoft.ReportingServices.Library.DBInterface::.ctor()
0xfec7  ldloc.0
0xfec8  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::set_ConnectionManager(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager)
0xfecd  call     valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType Microsoft.ReportingServices.Library.WebConfigUtil::get_WebServerAuthMode()
0xfed2  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType)
0xfed7  ldc.i4.0
0xfed8  newobj   instance void Microsoft.ReportingServices.Library.Security::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext userContext, bool checkSecurity)
0xfedd  stloc.1
0xfede  ldloc.1
0xfedf  ldloc.0
0xfee0  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::set_ConnectionManager(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager)
0xfee5  ldloc.1
0xfee6  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0xfeeb  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_UpdatePoliciesChunkSizeParam()
0xfef0  callvirt instance int32 Microsoft.ReportingServices.Library.Security::UpdateSecurityPolicies(int32 updatePoliciesChunkSize)
0xfef5  brtrue.s loc_FEE5
0xfef7  leave.s  loc_FF21
0xfef9  stloc.2
0xfefa  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0xfeff  ldc.i4.1
0xff00  ldstr    aErrorOnPolicyU// "Error on policy update.\n"
0xff05  ldloc.2
0xff06  callvirt instance string [mscorlib]System.Object::ToString()
0xff0b  call     string [mscorlib]System.String::Concat(string, string)
0xff10  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xff15  leave.s  loc_FF21
0xff17  ldloc.0
0xff18  brfalse.s loc_FF20
0xff1a  ldloc.0
0xff1b  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::DisconnectStorage()
0xff20  endfinally
0xff21  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0xff26  ldc.i4.4
0xff27  ldstr    aPolicyUpdateBa// "Policy update based on the update polic"...
0xff2c  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xff31  ret
```
