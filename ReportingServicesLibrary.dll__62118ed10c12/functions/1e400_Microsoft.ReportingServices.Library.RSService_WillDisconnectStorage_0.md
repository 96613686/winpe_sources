# Microsoft.ReportingServices.Library.RSService::WillDisconnectStorage_0

- ea: `0x1e400`
- end: `0x1e456`
- name: `Microsoft.ReportingServices.Library.RSService::WillDisconnectStorage_0`
- size: `86`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x3d10`
- `0x2ed50`

## callees

- `0x1e290`
- `0x1e3c0`
- `0x1e3e0`
- `0x1e940`

## string_xrefs

- `0x1e409`: `Attempting to set connection manager to null`
- `0x1e421`: `Attempting to set connection level more then once`

## pseudocode

```c

```

## disassembly

```asm
0x1e400  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0x1e405  ldarg.1
0x1e406  ldnull
0x1e407  cgt.un
0x1e409  ldstr    aAttemptingToSe_1// "Attempting to set connection manager to"...
0x1e40e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x1e413  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0x1e418  ldarg.0
0x1e419  ldfld    class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.RSService::m_connManager
0x1e41e  ldnull
0x1e41f  ceq
0x1e421  ldstr    aAttemptingToSe_2// "Attempting to set connection level more"...
0x1e426  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x1e42b  ldarg.0
0x1e42c  ldarg.1
0x1e42d  stfld    class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.RSService::m_connManager
0x1e432  ldarg.0
0x1e433  call     instance void Microsoft.ReportingServices.Library.RSService::WillDisconnectStorage()
0x1e438  ldarg.0
0x1e439  ldarg.0
0x1e43a  call     instance class Microsoft.ReportingServices.Library.RSServiceHelper Microsoft.ReportingServices.Library.RSService::get_ServiceHelper()
0x1e43f  callvirt instance class Microsoft.ReportingServices.Library.DBInterface Microsoft.ReportingServices.Library.RSServiceHelper::GetStorageInternal()
0x1e444  stfld    class Microsoft.ReportingServices.Library.DBInterface Microsoft.ReportingServices.Library.RSService::m_Storage
0x1e449  ldarg.0
0x1e44a  ldarg.0
0x1e44b  ldfld    class Microsoft.ReportingServices.Library.DBInterface Microsoft.ReportingServices.Library.RSService::m_Storage
0x1e450  call     instance void Microsoft.ReportingServices.Library.RSService::ConnectStorage(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage storage)
0x1e455  ret
```
