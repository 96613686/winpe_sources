# Microsoft.ReportingServices.Library.SubreportRetrieval::.ctor

- ea: `0x6a2f0`
- end: `0x6a32b`
- name: `Microsoft.ReportingServices.Library.SubreportRetrieval::.ctor`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x6a2d0`
- `0x8ce50`

## string_xrefs

- `0x6a312`: `service`
- `0x6a2ff`: `compiledDefinition`

## pseudocode

```c

```

## disassembly

```asm
0x6a2f0  ldarg.0
0x6a2f1  call     instance void [mscorlib]System.Object::.ctor()
0x6a2f6  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x6a2fb  ldarg.1
0x6a2fc  ldnull
0x6a2fd  cgt.un
0x6a2ff  ldstr    aCompileddefini// "compiledDefinition"
0x6a304  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x6a309  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x6a30e  ldarg.2
0x6a30f  ldnull
0x6a310  cgt.un
0x6a312  ldstr    aService// "service"
0x6a317  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x6a31c  ldarg.0
0x6a31d  ldarg.2
0x6a31e  stfld    class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.SubreportRetrieval::m_service
0x6a323  ldarg.0
0x6a324  ldarg.1
0x6a325  stfld    class Microsoft.ReportingServices.Library.ReportSnapshot Microsoft.ReportingServices.Library.SubreportRetrieval::m_originalCompiledDefinition
0x6a32a  ret
```
