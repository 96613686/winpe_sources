# Microsoft.ReportingServices.Diagnostics.Extension::.ctor

- ea: `0x5100`
- end: `0x514c`
- name: `Microsoft.ReportingServices.Diagnostics.Extension::.ctor`
- size: `76`
- prototype: ``
- caller_count: `9`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x4dc0`
- `0x4ea0`
- `0x5180`
- `0x5a00`
- `0x5b60`
- `0x5bd0`
- `0x5e80`
- `0x6330`
- `0x6400`

## pseudocode

```c

```

## disassembly

```asm
0x5100  ldarg.0
0x5101  ldstr    asc_19000// ""
0x5106  stfld    string Microsoft.ReportingServices.Diagnostics.Extension::m_name
0x510b  ldarg.0
0x510c  ldstr    asc_19000// ""
0x5111  stfld    string Microsoft.ReportingServices.Diagnostics.Extension::m_class
0x5116  ldarg.0
0x5117  ldstr    asc_19000// ""
0x511c  stfld    string Microsoft.ReportingServices.Diagnostics.Extension::m_assembly
0x5121  ldarg.0
0x5122  ldstr    asc_19000// ""
0x5127  stfld    string Microsoft.ReportingServices.Diagnostics.Extension::m_configuration
0x512c  ldarg.0
0x512d  ldstr    asc_19000// ""
0x5132  stfld    string Microsoft.ReportingServices.Diagnostics.Extension::m_type
0x5137  ldarg.0
0x5138  ldc.i4.1
0x5139  stfld    bool Microsoft.ReportingServices.Diagnostics.Extension::m_visible
0x513e  ldarg.0
0x513f  ldc.i4.1
0x5140  stfld    bool Microsoft.ReportingServices.Diagnostics.Extension::m_logAllExecutionRequests
0x5145  ldarg.0
0x5146  call     instance void [mscorlib]System.Object::.ctor()
0x514b  ret
```
