# Microsoft.ReportingServices.Interfaces.Extension::.ctor

- ea: `0x9a0`
- end: `0x9bc`
- name: `Microsoft.ReportingServices.Interfaces.Extension::.ctor`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x9a0  ldarg.0
0x9a1  call     instance void [mscorlib]System.Object::.ctor()
0x9a6  ldarg.0
0x9a7  ldarg.1
0x9a8  stfld    string Microsoft.ReportingServices.Interfaces.Extension::m_name
0x9ad  ldarg.0
0x9ae  ldarg.2
0x9af  stfld    string Microsoft.ReportingServices.Interfaces.Extension::m_localizedName
0x9b4  ldarg.0
0x9b5  ldarg.3
0x9b6  stfld    bool Microsoft.ReportingServices.Interfaces.Extension::m_visible
0x9bb  ret
```
