# Microsoft.ReportingServices.Library.ConnectionConfig::.ctor

- ea: `0x7b80`
- end: `0x7c38`
- name: `Microsoft.ReportingServices.Library.ConnectionConfig::.ctor`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3060`

## callees

- `0x7b50`
- `0x7b80`

## pseudocode

```c

```

## disassembly

```asm
0x7b80  ldarg.0
0x7b81  newobj   instance void [mscorlib]System.Object::.ctor()
0x7b86  stfld    object Microsoft.ReportingServices.Library.ConnectionConfig::_catUserSync
0x7b8b  ldarg.0
0x7b8c  call     instance void [mscorlib]System.Object::.ctor()
0x7b91  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x7b96  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_BaseConnectionString()
0x7b9b  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnectionStringBuilder::.ctor(string)
0x7ba0  stloc.0
0x7ba1  ldc.i4   0x100
0x7ba6  stloc.1
0x7ba7  ldsfld   int32 Microsoft.ReportingServices.Library.ConnectionConfig::_maxWorkers
0x7bac  brtrue.s loc_7BC4
0x7bae  call     class [ReportingServicesAppDomainManager]Microsoft.ReportingServices.HostingInterfaces.IRsUnmanagedCallback Microsoft.ReportingServices.Library.ConnectionConfig::get_IRsUnmanagedCallback()
0x7bb3  brfalse.s loc_7BC4
0x7bb5  call     class [ReportingServicesAppDomainManager]Microsoft.ReportingServices.HostingInterfaces.IRsUnmanagedCallback Microsoft.ReportingServices.Library.ConnectionConfig::get_IRsUnmanagedCallback()
0x7bba  callvirt instance int32 [ReportingServicesAppDomainManager]Microsoft.ReportingServices.HostingInterfaces.IRsUnmanagedCallback::GetMaxWorkers()
0x7bbf  stsfld   int32 Microsoft.ReportingServices.Library.ConnectionConfig::_maxWorkers
0x7bc4  ldsfld   int32 Microsoft.ReportingServices.Library.ConnectionConfig::_maxWorkers
0x7bc9  brfalse.s loc_7BD1
0x7bcb  ldsfld   int32 Microsoft.ReportingServices.Library.ConnectionConfig::_maxWorkers
0x7bd0  stloc.1
0x7bd1  ldloc.0
0x7bd2  ldloc.1
0x7bd3  ldc.i4.3
0x7bd4  mul
0x7bd5  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnectionStringBuilder::set_MaxPoolSize(int32)
0x7bda  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x7bdf  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_MaxCatalogConnectionPoolSizePerProcess()
0x7be4  brfalse.s loc_7BF6
0x7be6  ldloc.0
0x7be7  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x7bec  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_MaxCatalogConnectionPoolSizePerProcess()
0x7bf1  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnectionStringBuilder::set_MaxPoolSize(int32)
0x7bf6  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x7bfb  ldc.i4.3
0x7bfc  ldstr    aCatalogMaxConn// "Catalog max connection pool size: {0}"
0x7c01  ldloc.0
0x7c02  callvirt instance int32 [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnectionStringBuilder::get_MaxPoolSize()
0x7c07  box      [mscorlib]System.Int32
0x7c0c  call     string [mscorlib]System.String::Format(string, object)
0x7c11  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x7c16  ldloc.0
0x7c17  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x7c1c  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ConnectionTimeout()
0x7c21  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnectionStringBuilder::set_ConnectTimeout(int32)
0x7c26  ldarg.0
0x7c27  ldloc.0
0x7c28  callvirt instance string [mscorlib]System.Object::ToString()
0x7c2d  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SecureStringWrapper::.ctor(string)
0x7c32  stfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SecureStringWrapper Microsoft.ReportingServices.Library.ConnectionConfig::_connectionString
0x7c37  ret
```
