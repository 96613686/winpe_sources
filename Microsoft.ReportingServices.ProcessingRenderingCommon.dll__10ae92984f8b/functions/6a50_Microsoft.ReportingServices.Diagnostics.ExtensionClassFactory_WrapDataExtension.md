# Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::WrapDataExtension

- ea: `0x6a50`
- end: `0x6aa5`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::WrapDataExtension`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x6960`

## callees

- `0x3100`
- `0x3200`
- `0x6a50`

## string_xrefs

- `0x6a5f`: `Report Server Data Extension {0} does not implement IExtension or System.Data.IDbConnection.`
- `0x6a8f`: `A wrapper has been created for the connection to the {0} data source.`

## pseudocode

```c

```

## disassembly

```asm
0x6a50  ldarg.1
0x6a51  isinst   [System.Data]System.Data.IDbConnection
0x6a56  dup
0x6a57  brtrue.s loc_6A70
0x6a59  ldnull
0x6a5a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6a5f  ldstr    aReportServerDa// "Report Server Data Extension {0} does n"...
0x6a64  ldarg.2
0x6a65  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x6a6a  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(class [mscorlib]System.Exception, string)
0x6a6f  throw
0x6a70  newobj   instance void Microsoft.ReportingServices.DataExtensions.ConnectionWrapper::.ctor(class [System.Data]System.Data.IDbConnection underlyingConnection)
0x6a75  stloc.0
0x6a76  ldloc.0
0x6a77  ldc.i4.1
0x6a78  callvirt instance void Microsoft.ReportingServices.DataExtensions.ConnectionWrapper::set_WrappedManagedProvider(bool value)
0x6a7d  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::m_Tracer
0x6a82  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x6a87  brfalse.s loc_6AA3
0x6a89  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::m_Tracer
0x6a8e  ldc.i4.3
0x6a8f  ldstr    aAWrapperHasBee// "A wrapper has been created for the conn"...
0x6a94  ldc.i4.1
0x6a95  newarr   [mscorlib]System.Object
0x6a9a  dup
0x6a9b  ldc.i4.0
0x6a9c  ldarg.2
0x6a9d  stelem.ref
0x6a9e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x6aa3  ldloc.0
0x6aa4  ret
```
