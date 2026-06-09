# Microsoft.ReportingServices.Interfaces.LocalizedNameAttribute::.ctor_0

- ea: `0x1500`
- end: `0x1515`
- name: `Microsoft.ReportingServices.Interfaces.LocalizedNameAttribute::.ctor_0`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1500  ldarg.0
0x1501  call     instance void [mscorlib]System.Attribute::.ctor()
0x1506  ldarg.0
0x1507  ldarg.1
0x1508  stfld    string Microsoft.ReportingServices.Interfaces.LocalizedNameAttribute::m_name
0x150d  ldarg.0
0x150e  ldc.i4.0
0x150f  stfld    bool Microsoft.ReportingServices.Interfaces.LocalizedNameAttribute::m_localized
0x1514  ret
```
