# Microsoft.ReportingServices.Library.ServerSnapshot::InitializeChunkConnection

- ea: `0x5f7c0`
- end: `0x5f854`
- name: `Microsoft.ReportingServices.Library.ServerSnapshot::InitializeChunkConnection`
- size: `148`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x5f000`
- `0x5f160`
- `0x5f200`

## callees

- `0x5f7c0`
- `0x5f860`
- `0x5f870`

## string_xrefs

- `0x5f7c8`: `Snapshot access outside of transaction scope`
- `0x5f81b`: `ConnectionManager is MultithreadedConnectionManager`

## pseudocode

```c

```

## disassembly

```asm
0x5f7c0  ldarg.0
0x5f7c1  ldfld    bool Microsoft.ReportingServices.Library.ServerSnapshot::m_inTransactionScope
0x5f7c6  brtrue.s loc_5F7D3
0x5f7c8  ldstr    aSnapshotAccess// "Snapshot access outside of transaction "...
0x5f7cd  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x5f7d2  throw
0x5f7d3  ldarg.0
0x5f7d4  call     instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.ServerSnapshot::get_ConnectionManager()
0x5f7d9  brfalse.s loc_5F7DC
0x5f7db  ret
0x5f7dc  ldarg.0
0x5f7dd  ldfld    object Microsoft.ReportingServices.Library.ServerSnapshot::m_initializeConnectionLock
0x5f7e2  stloc.0
0x5f7e3  ldc.i4.0
0x5f7e4  stloc.1
0x5f7e5  ldloc.0
0x5f7e6  ldloca.s 1
0x5f7e8  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x5f7ed  ldarg.0
0x5f7ee  call     instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.ServerSnapshot::get_ConnectionManager()
0x5f7f3  brfalse.s loc_5F7F7
0x5f7f5  leave.s  loc_5F853
0x5f7f7  ldarg.0
0x5f7f8  ldc.i4.0
0x5f7f9  ldc.i4   0x1000
0x5f7fe  call     class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::Create(valuetype [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionTransactionType, valuetype [System.Data]System.Data.IsolationLevel)
0x5f803  call     instance void Microsoft.ReportingServices.Library.ServerSnapshot::set_ConnectionManager(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager value)
0x5f808  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x5f80d  ldarg.0
0x5f80e  call     instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.ServerSnapshot::get_ConnectionManager()
0x5f813  isinst   [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.MultithreadedConnectionManager
0x5f818  ldnull
0x5f819  cgt.un
0x5f81b  ldstr    aConnectionmana_0// "ConnectionManager is MultithreadedConne"...
0x5f820  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x5f825  ldarg.0
0x5f826  call     instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.ServerSnapshot::get_ConnectionManager()
0x5f82b  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage()
0x5f830  ldarg.0
0x5f831  call     instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.ServerSnapshot::get_ConnectionManager()
0x5f836  ldc.i4.1
0x5f837  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::set_SingleCommitEnabled(bool)
0x5f83c  ldarg.0
0x5f83d  call     instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.ServerSnapshot::get_ConnectionManager()
0x5f842  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::BeginTransaction()
0x5f847  leave.s  loc_5F853
0x5f849  ldloc.1
0x5f84a  brfalse.s loc_5F852
0x5f84c  ldloc.0
0x5f84d  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x5f852  endfinally
0x5f853  ret
```
