# Microsoft.ReportingServices.Portal.Services.DatabaseService::EnsureDatabaseAvailable

- ea: `0x9f90`
- end: `0xa013`
- name: `Microsoft.ReportingServices.Portal.Services.DatabaseService::EnsureDatabaseAvailable`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x9f90`
- `0xa020`
- `0xa910`
- `0xa920`
- `0xa930`

## pseudocode

```c

```

## disassembly

```asm
0x9f90  ldarg.0
0x9f91  ldarg.1
0x9f92  ldc.i4.4
0x9f93  call     string Microsoft.ReportingServices.Portal.Services.SR::get_Error_DatabaseDowngradeDetected()
0x9f98  call     instance void Microsoft.ReportingServices.Portal.Services.DatabaseService::CheckStatusAndThrowIfMatching(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger, valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus statusToMatch, string errorString)
0x9f9d  ldarg.0
0x9f9e  ldarg.1
0x9f9f  ldc.i4.3
0x9fa0  call     string Microsoft.ReportingServices.Portal.Services.SR::get_Error_PbiToRsAttachDetected()
0x9fa5  call     instance void Microsoft.ReportingServices.Portal.Services.DatabaseService::CheckStatusAndThrowIfMatching(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger, valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus statusToMatch, string errorString)
0x9faa  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::get_Current()
0x9faf  callvirt instance valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::get_DatabaseValidationStatus()
0x9fb4  ldc.i4.7
0x9fb5  bne.un.s loc_9FC9
0x9fb7  ldarg.1
0x9fb8  ldc.i4.1
0x9fb9  call     string Microsoft.ReportingServices.Portal.Services.SR::get_Error_EncryptionFailure()
0x9fbe  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x9fc3  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.CannotValidateEncryptedDataException::.ctor()
0x9fc8  throw
0x9fc9  ldnull
0x9fca  stloc.0
0x9fcb  ldc.i4.0
0x9fcc  ldc.i4   0x100
0x9fd1  newobj   instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::.ctor(valuetype [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionTransactionType, valuetype [System.Data]System.Data.IsolationLevel)
0x9fd6  stloc.0
0x9fd7  ldloc.0
0x9fd8  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage()
0x9fdd  ldloc.0
0x9fde  ldc.i4.1
0x9fdf  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::VerifyConnection(bool)
0x9fe4  leave.s  loc_A012
0x9fe6  stloc.1
0x9fe7  ldloc.1
0x9fe8  callvirt instance string [mscorlib]System.Exception::get_Message()
0x9fed  ldloc.1
0x9fee  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.DatabaseUnavailableException::.ctor(string, class [mscorlib]System.Exception)
0x9ff3  throw
0x9ff4  stloc.2
0x9ff5  ldloc.2
0x9ff6  callvirt instance string [mscorlib]System.Exception::get_Message()
0x9ffb  ldloc.2
0x9ffc  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.DatabaseUnavailableException::.ctor(string, class [mscorlib]System.Exception)
0xa001  throw
0xa002  newobj   instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.KeyStateNotValidException::.ctor(class [mscorlib]System.Exception)
0xa007  throw
0xa008  ldloc.0
0xa009  brfalse.s loc_A011
0xa00b  ldloc.0
0xa00c  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::DisconnectStorage()
0xa011  endfinally
0xa012  ret
```
