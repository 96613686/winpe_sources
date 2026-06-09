# Microsoft.ReportingServices.Library.SQLScheduleParameters::Add_Frequency_Relative_Interval

- ea: `0x4b40`
- end: `0x4b90`
- name: `Microsoft.ReportingServices.Library.SQLScheduleParameters::Add_Frequency_Relative_Interval`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x5330`

## callees

- `0x4a10`
- `0x4b40`
- `0x4db0`

## pseudocode

```c

```

## disassembly

```asm
0x4b40  ldarg.0
0x4b41  ldarg.1
0x4b42  ldc.i4.1
0x4b43  beq.s    loc_4B58
0x4b45  ldarg.1
0x4b46  ldc.i4.2
0x4b47  beq.s    loc_4B58
0x4b49  ldarg.1
0x4b4a  ldc.i4.4
0x4b4b  beq.s    loc_4B58
0x4b4d  ldarg.1
0x4b4e  ldc.i4.8
0x4b4f  beq.s    loc_4B58
0x4b51  ldarg.1
0x4b52  ldc.i4.s 0x10
0x4b54  ceq
0x4b56  br.s     loc_4B59
0x4b58  ldc.i4.1
0x4b59  ldstr    aIncorrectFrequ_1// "Incorrect frequency relative interval f"...
0x4b5e  call     instance void Microsoft.ReportingServices.Library.SQLScheduleParameters::Assert(bool condition, string message)
0x4b63  newobj   instance void Microsoft.ReportingServices.Library.SQLScheduleParameter::.ctor()
0x4b68  stloc.0
0x4b69  ldloc.0
0x4b6a  ldstr    aFreqRelativeIn// "@freq_relative_interval"
0x4b6f  stfld    string Microsoft.ReportingServices.Library.SQLScheduleParameter::Name
0x4b74  ldloc.0
0x4b75  ldc.i4.8
0x4b76  stfld    valuetype [System.Data]System.Data.SqlDbType Microsoft.ReportingServices.Library.SQLScheduleParameter::Type
0x4b7b  ldloc.0
0x4b7c  ldarg.1
0x4b7d  box      [mscorlib]System.Int32
0x4b82  stfld    object Microsoft.ReportingServices.Library.SQLScheduleParameter::Value
0x4b87  ldarg.0
0x4b88  ldloc.0
0x4b89  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x4b8e  pop
0x4b8f  ret
```
