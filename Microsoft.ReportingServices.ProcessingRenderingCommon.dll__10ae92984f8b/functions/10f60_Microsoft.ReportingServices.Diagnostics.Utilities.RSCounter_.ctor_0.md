# Microsoft.ReportingServices.Diagnostics.Utilities.RSCounter::.ctor_0

- ea: `0x10f60`
- end: `0x10f7c`
- name: `Microsoft.ReportingServices.Diagnostics.Utilities.RSCounter::.ctor_0`
- size: `28`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x10e30`
- `0x10e50`
- `0x10e70`
- `0x10e90`
- `0x10eb0`
- `0x10ef0`

## callees

- `0x10f80`

## pseudocode

```c

```

## disassembly

```asm
0x10f60  ldarg.0
0x10f61  call     instance void [mscorlib]System.Object::.ctor()
0x10f66  ldarg.0
0x10f67  ldarg.s  5
0x10f69  stfld    bool Microsoft.ReportingServices.Diagnostics.Utilities.RSCounter::m_isPrivateCounter
0x10f6e  ldarg.0
0x10f6f  ldarg.1
0x10f70  ldarg.2
0x10f71  ldarg.3
0x10f72  ldarg.s  4
0x10f74  ldarg.s  6
0x10f76  call     instance void Microsoft.ReportingServices.Diagnostics.Utilities.RSCounter::Init(string categoryName, string counterName, string instanceName, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace tracer, bool resetCounter)
0x10f7b  ret
```
