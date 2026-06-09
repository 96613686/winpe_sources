# Microsoft.ReportingServices.Library.SQLScheduleParameters::AddFrequencyType

- ea: `0x4a20`
- end: `0x4a82`
- name: `Microsoft.ReportingServices.Library.SQLScheduleParameters::AddFrequencyType`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x5330`

## callees

- `0x4a10`
- `0x4a20`
- `0x4db0`

## pseudocode

```c

```

## disassembly

```asm
0x4a20  ldarg.0
0x4a21  ldarg.1
0x4a22  ldc.i4.1
0x4a23  beq.s    loc_4A4A
0x4a25  ldarg.1
0x4a26  ldc.i4.2
0x4a27  beq.s    loc_4A4A
0x4a29  ldarg.1
0x4a2a  ldc.i4.4
0x4a2b  beq.s    loc_4A4A
0x4a2d  ldarg.1
0x4a2e  ldc.i4.8
0x4a2f  beq.s    loc_4A4A
0x4a31  ldarg.1
0x4a32  ldc.i4.s 0x10
0x4a34  beq.s    loc_4A4A
0x4a36  ldarg.1
0x4a37  ldc.i4.s 0x20
0x4a39  beq.s    loc_4A4A
0x4a3b  ldarg.1
0x4a3c  ldc.i4.s 0x40
0x4a3e  beq.s    loc_4A4A
0x4a40  ldarg.1
0x4a41  ldc.i4   0x80
0x4a46  ceq
0x4a48  br.s     loc_4A4B
0x4a4a  ldc.i4.1
0x4a4b  ldstr    aIncorrectFrequ// "Incorrect frequency type for a SQL sche"...
0x4a50  call     instance void Microsoft.ReportingServices.Library.SQLScheduleParameters::Assert(bool condition, string message)
0x4a55  newobj   instance void Microsoft.ReportingServices.Library.SQLScheduleParameter::.ctor()
0x4a5a  stloc.0
0x4a5b  ldloc.0
0x4a5c  ldstr    aFreqType// "@freq_type"
0x4a61  stfld    string Microsoft.ReportingServices.Library.SQLScheduleParameter::Name
0x4a66  ldloc.0
0x4a67  ldc.i4.8
0x4a68  stfld    valuetype [System.Data]System.Data.SqlDbType Microsoft.ReportingServices.Library.SQLScheduleParameter::Type
0x4a6d  ldloc.0
0x4a6e  ldarg.1
0x4a6f  box      [mscorlib]System.Int32
0x4a74  stfld    object Microsoft.ReportingServices.Library.SQLScheduleParameter::Value
0x4a79  ldarg.0
0x4a7a  ldloc.0
0x4a7b  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x4a80  pop
0x4a81  ret
```
