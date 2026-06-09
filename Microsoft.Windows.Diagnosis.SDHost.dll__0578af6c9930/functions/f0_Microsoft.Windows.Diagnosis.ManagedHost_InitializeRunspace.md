# Microsoft.Windows.Diagnosis.ManagedHost::InitializeRunspace

- ea: `0xf0`
- end: `0x1f9`
- name: `Microsoft.Windows.Diagnosis.ManagedHost::InitializeRunspace`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x70`

## callees

- `0xf0`

## string_xrefs

- `0xfc`: `update-diagrootcause`
- `0x13c`: `update-diagreport`
- `0x15c`: `write-diagprogress`
- `0x17c`: `write-diagtelemetry`
- `0x1c9`: `InteractivityAgent`

## pseudocode

```c

```

## disassembly

```asm
0xf0  call     class [System.Management.Automation]System.Management.Automation.Runspaces.InitialSessionState [System.Management.Automation]System.Management.Automation.Runspaces.InitialSessionState::CreateDefault()
0xf5  stloc.0
0xf6  ldloc.0
0xf7  callvirt instance class [System.Management.Automation]System.Management.Automation.Runspaces.InitialSessionStateEntryCollection`1<class [System.Management.Automation]System.Management.Automation.Runspaces.SessionStateCommandEntry> [System.Management.Automation]System.Management.Automation.Runspaces.InitialSessionState::get_Commands()
0xfc  ldstr    aUpdateDiagroot// "update-diagrootcause"
0x101  ldtoken  [Microsoft.Windows.Diagnosis.Commands.UpdateDiagRootcause]Microsoft.Windows.Diagnosis.Commands.UpdateDiagRootCause
0x106  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10b  ldnull
0x10c  newobj   instance void [System.Management.Automation]System.Management.Automation.Runspaces.SessionStateCmdletEntry::.ctor(string, class [mscorlib]System.Type, string)
0x111  callvirt instance void class [System.Management.Automation]System.Management.Automation.Runspaces.InitialSessionStateEntryCollection`1<class [System.Management.Automation]System.Management.Automation.Runspaces.SessionStateCommandEntry>::Add(var<u1>)
0x116  ldloc.0
0x117  callvirt instance class [System.Management.Automation]System.Management.Automation.Runspaces.InitialSessionStateEntryCollection`1<class [System.Management.Automation]System.Management.Automation.Runspaces.SessionStateCommandEntry> [System.Management.Automation]System.Management.Automation.Runspaces.InitialSessionState::get_Commands()
0x11c  ldstr    aGetDiaginput// "get-diaginput"
0x121  ldtoken  [Microsoft.Windows.Diagnosis.Commands.GetDiagInput]Microsoft.Windows.Diagnosis.Commands.GetDiagInput
0x126  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12b  ldnull
0x12c  newobj   instance void [System.Management.Automation]System.Management.Automation.Runspaces.SessionStateCmdletEntry::.ctor(string, class [mscorlib]System.Type, string)
0x131  callvirt instance void class [System.Management.Automation]System.Management.Automation.Runspaces.InitialSessionStateEntryCollection`1<class [System.Management.Automation]System.Management.Automation.Runspaces.SessionStateCommandEntry>::Add(var<u1>)
0x136  ldloc.0
0x137  callvirt instance class [System.Management.Automation]System.Management.Automation.Runspaces.InitialSessionStateEntryCollection`1<class [System.Management.Automation]System.Management.Automation.Runspaces.SessionStateCommandEntry> [System.Management.Automation]System.Management.Automation.Runspaces.InitialSessionState::get_Commands()
0x13c  ldstr    aUpdateDiagrepo// "update-diagreport"
0x141  ldtoken  [Microsoft.Windows.Diagnosis.Commands.UpdateDiagReport]Microsoft.Windows.Diagnosis.Commands.UpdateDiagReport
0x146  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14b  ldnull
0x14c  newobj   instance void [System.Management.Automation]System.Management.Automation.Runspaces.SessionStateCmdletEntry::.ctor(string, class [mscorlib]System.Type, string)
0x151  callvirt instance void class [System.Management.Automation]System.Management.Automation.Runspaces.InitialSessionStateEntryCollection`1<class [System.Management.Automation]System.Management.Automation.Runspaces.SessionStateCommandEntry>::Add(var<u1>)
0x156  ldloc.0
0x157  callvirt instance class [System.Management.Automation]System.Management.Automation.Runspaces.InitialSessionStateEntryCollection`1<class [System.Management.Automation]System.Management.Automation.Runspaces.SessionStateCommandEntry> [System.Management.Automation]System.Management.Automation.Runspaces.InitialSessionState::get_Commands()
0x15c  ldstr    aWriteDiagprogr// "write-diagprogress"
0x161  ldtoken  [Microsoft.Windows.Diagnosis.Commands.WriteDiagProgress]Microsoft.Windows.Diagnosis.Commands.WriteDiagProgress
0x166  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16b  ldnull
0x16c  newobj   instance void [System.Management.Automation]System.Management.Automation.Runspaces.SessionStateCmdletEntry::.ctor(string, class [mscorlib]System.Type, string)
0x171  callvirt instance void class [System.Management.Automation]System.Management.Automation.Runspaces.InitialSessionStateEntryCollection`1<class [System.Management.Automation]System.Management.Automation.Runspaces.SessionStateCommandEntry>::Add(var<u1>)
0x176  ldloc.0
0x177  callvirt instance class [System.Management.Automation]System.Management.Automation.Runspaces.InitialSessionStateEntryCollection`1<class [System.Management.Automation]System.Management.Automation.Runspaces.SessionStateCommandEntry> [System.Management.Automation]System.Management.Automation.Runspaces.InitialSessionState::get_Commands()
0x17c  ldstr    aWriteDiagtelem// "write-diagtelemetry"
0x181  ldtoken  [Microsoft.Windows.Diagnosis.Commands.WriteDiagTelemetry]Microsoft.Windows.Diagnosis.Commands.WriteDiagTelemetry
0x186  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18b  ldnull
0x18c  newobj   instance void [System.Management.Automation]System.Management.Automation.Runspaces.SessionStateCmdletEntry::.ctor(string, class [mscorlib]System.Type, string)
0x191  callvirt instance void class [System.Management.Automation]System.Management.Automation.Runspaces.InitialSessionStateEntryCollection`1<class [System.Management.Automation]System.Management.Automation.Runspaces.SessionStateCommandEntry>::Add(var<u1>)
0x196  ldloc.0
0x197  ldstr    aScripteddiagno// "ScriptedDiagnostics"
0x19c  newobj   instance void [System.Management.Automation]Microsoft.PowerShell.PSAuthorizationManager::.ctor(string)
0x1a1  callvirt instance void [System.Management.Automation]System.Management.Automation.Runspaces.InitialSessionState::set_AuthorizationManager(class [System.Management.Automation]System.Management.Automation.AuthorizationManager)
0x1a6  ldarg.0
0x1a7  ldloc.0
0x1a8  call     class [System.Management.Automation]System.Management.Automation.Runspaces.Runspace [System.Management.Automation]System.Management.Automation.Runspaces.RunspaceFactory::CreateRunspace(class [System.Management.Automation]System.Management.Automation.Runspaces.InitialSessionState)
0x1ad  stfld    class [System.Management.Automation]System.Management.Automation.Runspaces.Runspace Microsoft.Windows.Diagnosis.ManagedHost::m_Runspace
0x1b2  ldarg.0
0x1b3  ldfld    class [System.Management.Automation]System.Management.Automation.Runspaces.Runspace Microsoft.Windows.Diagnosis.ManagedHost::m_Runspace
0x1b8  callvirt instance void [System.Management.Automation]System.Management.Automation.Runspaces.Runspace::Open()
0x1bd  ldarg.0
0x1be  ldfld    class [System.Management.Automation]System.Management.Automation.Runspaces.Runspace Microsoft.Windows.Diagnosis.ManagedHost::m_Runspace
0x1c3  callvirt instance class [System.Management.Automation]System.Management.Automation.Runspaces.SessionStateProxy [System.Management.Automation]System.Management.Automation.Runspaces.Runspace::get_SessionStateProxy()
0x1c8  dup
0x1c9  ldstr    aInteractivitya// "InteractivityAgent"
0x1ce  ldarg.0
0x1cf  ldfld    class [Microsoft.Windows.Diagnosis.SDCommon]Microsoft.Windows.Diagnosis.IScriptedDiagnosticInteraction Microsoft.Windows.Diagnosis.ManagedHost::m_Engine
0x1d4  callvirt instance void [System.Management.Automation]System.Management.Automation.Runspaces.SessionStateProxy::SetVariable(string, object)
0x1d9  ldstr    aRealmode// "RealMode"
0x1de  ldc.i4.1
0x1df  box      [mscorlib]System.Boolean
0x1e4  callvirt instance void [System.Management.Automation]System.Management.Automation.Runspaces.SessionStateProxy::SetVariable(string, object)
0x1e9  leave.s  loc_1F8
0x1eb  pop
0x1ec  ldc.i4   0x803C0102
0x1f1  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x1f6  leave.s  loc_1F8
0x1f8  ret
```
