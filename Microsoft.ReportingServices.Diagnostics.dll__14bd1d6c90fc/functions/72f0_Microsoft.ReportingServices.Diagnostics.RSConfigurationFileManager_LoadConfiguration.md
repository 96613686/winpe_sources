# Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::LoadConfiguration

- ea: `0x72f0`
- end: `0x7331`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::LoadConfiguration`
- size: `65`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7210`
- `0x90d0`

## callees

- `0x72f0`
- `0x7340`

## string_xrefs

- `0x730e`: `Error loading configuration file: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x72f0  ldnull
0x72f1  stloc.0
0x72f2  ldarg.0
0x72f3  call     instance class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::LoadDocument()
0x72f8  stloc.0
0x72f9  leave.s  loc_732F
0x72fb  stloc.1
0x72fc  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_Tracer
0x7301  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x7306  brfalse.s loc_7327
0x7308  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_Tracer
0x730d  ldc.i4.1
0x730e  ldstr    aErrorLoadingCo// "Error loading configuration file: {0}"
0x7313  ldc.i4.1
0x7314  newarr   [mscorlib]System.Object
0x7319  dup
0x731a  ldc.i4.0
0x731b  ldloc.1
0x731c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x7321  stelem.ref
0x7322  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x7327  ldloc.1
0x7328  ldnull
0x7329  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(class [mscorlib]System.Exception, string)
0x732e  throw
0x732f  ldloc.0
0x7330  ret
```
