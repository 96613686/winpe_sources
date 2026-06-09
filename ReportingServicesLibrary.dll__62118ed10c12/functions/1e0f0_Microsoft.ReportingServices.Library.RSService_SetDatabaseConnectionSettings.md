# Microsoft.ReportingServices.Library.RSService::SetDatabaseConnectionSettings

- ea: `0x1e0f0`
- end: `0x1e158`
- name: `Microsoft.ReportingServices.Library.RSService::SetDatabaseConnectionSettings`
- size: `104`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xfac0`
- `0x10940`
- `0x1a580`
- `0x1b2f0`
- `0x1c8f0`
- `0x1ef30`
- `0x28e70`

## callees

- `0x1e0f0`

## string_xrefs

- `0x1e13a`: `Attempting to set connection isolation level more then once`
- `0x1e14d`: `Attempting to set connection Transaction Type more then once`

## pseudocode

```c

```

## disassembly

```asm
0x1e0f0  ldarg.0
0x1e0f1  ldfld    class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.RSService::m_connManager
0x1e0f6  brtrue.s loc_1E119
0x1e0f8  ldarg.0
0x1e0f9  ldarg.1
0x1e0fa  ldarg.2
0x1e0fb  newobj   instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::.ctor(valuetype [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionTransactionType, valuetype [System.Data]System.Data.IsolationLevel)
0x1e100  stfld    class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.RSService::m_connManager
0x1e105  ldarg.0
0x1e106  ldfld    bool Microsoft.ReportingServices.Library.RSService::m_willDisconnectStorage
0x1e10b  brfalse.s loc_1E157
0x1e10d  ldarg.0
0x1e10e  ldfld    class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.RSService::m_connManager
0x1e113  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage()
0x1e118  ret
0x1e119  ldarg.0
0x1e11a  ldfld    class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.RSService::m_connManager
0x1e11f  callvirt instance valuetype [System.Data]System.Data.IsolationLevel [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::GetIsolationLevel()
0x1e124  stloc.0
0x1e125  ldarg.0
0x1e126  ldfld    class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.RSService::m_connManager
0x1e12b  callvirt instance valuetype [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionTransactionType [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::GetTransactionType()
0x1e130  stloc.1
0x1e131  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0x1e136  ldarg.2
0x1e137  ldloc.0
0x1e138  ceq
0x1e13a  ldstr    aAttemptingToSe// "Attempting to set connection isolation "...
0x1e13f  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x1e144  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0x1e149  ldarg.1
0x1e14a  ldloc.1
0x1e14b  ceq
0x1e14d  ldstr    aAttemptingToSe_0// "Attempting to set connection Transactio"...
0x1e152  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x1e157  ret
```
