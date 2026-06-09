# Microsoft.ReportingServices.Library.SQLScheduleParameters::AddFrequency_SubDay_Type

- ea: `0x4ac0`
- end: `0x4b07`
- name: `Microsoft.ReportingServices.Library.SQLScheduleParameters::AddFrequency_SubDay_Type`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x5330`

## callees

- `0x4a10`
- `0x4ac0`
- `0x4db0`

## pseudocode

```c

```

## disassembly

```asm
0x4ac0  ldarg.0
0x4ac1  ldarg.1
0x4ac2  ldc.i4.1
0x4ac3  beq.s    loc_4ACF
0x4ac5  ldarg.1
0x4ac6  ldc.i4.4
0x4ac7  beq.s    loc_4ACF
0x4ac9  ldarg.1
0x4aca  ldc.i4.8
0x4acb  ceq
0x4acd  br.s     loc_4AD0
0x4acf  ldc.i4.1
0x4ad0  ldstr    aIncorrectFrequ_0// "Incorrect frequency sub day type for a "...
0x4ad5  call     instance void Microsoft.ReportingServices.Library.SQLScheduleParameters::Assert(bool condition, string message)
0x4ada  newobj   instance void Microsoft.ReportingServices.Library.SQLScheduleParameter::.ctor()
0x4adf  stloc.0
0x4ae0  ldloc.0
0x4ae1  ldstr    aFreqSubdayType// "@freq_subday_type"
0x4ae6  stfld    string Microsoft.ReportingServices.Library.SQLScheduleParameter::Name
0x4aeb  ldloc.0
0x4aec  ldc.i4.8
0x4aed  stfld    valuetype [System.Data]System.Data.SqlDbType Microsoft.ReportingServices.Library.SQLScheduleParameter::Type
0x4af2  ldloc.0
0x4af3  ldarg.1
0x4af4  box      [mscorlib]System.Int32
0x4af9  stfld    object Microsoft.ReportingServices.Library.SQLScheduleParameter::Value
0x4afe  ldarg.0
0x4aff  ldloc.0
0x4b00  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x4b05  pop
0x4b06  ret
```
