# Microsoft.ReportingServices.Library.SQLScheduleParameter::.ctor

- ea: `0x4db0`
- end: `0x4dca`
- name: `Microsoft.ReportingServices.Library.SQLScheduleParameter::.ctor`
- size: `26`
- prototype: ``
- caller_count: `10`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x4a20`
- `0x4a90`
- `0x4ac0`
- `0x4b10`
- `0x4b40`
- `0x4b90`
- `0x4bc0`
- `0x4c00`
- `0x4c40`
- `0x4c80`

## pseudocode

```c

```

## disassembly

```asm
0x4db0  ldarg.0
0x4db1  ldstr    asc_A0B2// ""
0x4db6  stfld    string Microsoft.ReportingServices.Library.SQLScheduleParameter::Name
0x4dbb  ldarg.0
0x4dbc  ldc.i4.s 0x17
0x4dbe  stfld    valuetype [System.Data]System.Data.SqlDbType Microsoft.ReportingServices.Library.SQLScheduleParameter::Type
0x4dc3  ldarg.0
0x4dc4  call     instance void [mscorlib]System.Object::.ctor()
0x4dc9  ret
```
