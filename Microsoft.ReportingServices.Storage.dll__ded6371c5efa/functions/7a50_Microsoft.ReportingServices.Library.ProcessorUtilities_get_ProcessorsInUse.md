# Microsoft.ReportingServices.Library.ProcessorUtilities::get_ProcessorsInUse

- ea: `0x7a50`
- end: `0x7aae`
- name: `Microsoft.ReportingServices.Library.ProcessorUtilities::get_ProcessorsInUse`
- size: `94`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1320`
- `0x19b0`
- `0x7ab0`

## callees

- `0x7a50`

## pseudocode

```c

```

## disassembly

```asm
0x7a50  ldsfld   int32 Microsoft.ReportingServices.Library.ProcessorUtilities::m_numberOfProcessors
0x7a55  brtrue.s loc_7AA8
0x7a57  ldnull
0x7a58  stloc.0
0x7a59  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x7a5e  callvirt instance class [mscorlib]System.AppDomainManager [mscorlib]System.AppDomain::get_DomainManager()
0x7a63  isinst   [mscorlib]System.IServiceProvider
0x7a68  stloc.1
0x7a69  ldloc.1
0x7a6a  brfalse.s loc_7A82
0x7a6c  ldloc.1
0x7a6d  ldtoken  [ReportingServicesAppDomainManager]Microsoft.ReportingServices.HostingInterfaces.IRsUnmanagedCallback
0x7a72  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7a77  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x7a7c  castclass [ReportingServicesAppDomainManager]Microsoft.ReportingServices.HostingInterfaces.IRsUnmanagedCallback
0x7a81  stloc.0
0x7a82  ldloc.0
0x7a83  brtrue.s loc_7A91
0x7a85  call     int32 [mscorlib]System.Environment::get_ProcessorCount()
0x7a8a  stsfld   int32 Microsoft.ReportingServices.Library.ProcessorUtilities::m_numberOfProcessors
0x7a8f  br.s     loc_7AA8
0x7a91  ldloc.0
0x7a92  callvirt instance int64 [ReportingServicesAppDomainManager]Microsoft.ReportingServices.HostingInterfaces.IRsUnmanagedCallback::GetConcurrencyLimit()
0x7a97  ldc.i4   0x7FFFFFFF
0x7a9c  conv.i8
0x7a9d  call     int64 [mscorlib]System.Math::Min(int64, int64)
0x7aa2  conv.i4
0x7aa3  stsfld   int32 Microsoft.ReportingServices.Library.ProcessorUtilities::m_numberOfProcessors
0x7aa8  ldsfld   int32 Microsoft.ReportingServices.Library.ProcessorUtilities::m_numberOfProcessors
0x7aad  ret
```
