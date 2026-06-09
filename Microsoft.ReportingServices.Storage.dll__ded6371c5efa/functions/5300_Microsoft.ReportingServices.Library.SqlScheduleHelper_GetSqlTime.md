# Microsoft.ReportingServices.Library.SqlScheduleHelper::GetSqlTime

- ea: `0x5300`
- end: `0x532d`
- name: `Microsoft.ReportingServices.Library.SqlScheduleHelper::GetSqlTime`
- size: `45`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4e30`
- `0x6750`

## callees

- `0x5300`

## pseudocode

```c

```

## disassembly

```asm
0x5300  ldarga.s 0
0x5302  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5307  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x530c  stloc.0
0x530d  ldloc.0
0x530e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x5313  ldc.i4.6
0x5314  bge.s    loc_5320
0x5316  ldloc.0
0x5317  ldc.i4.6
0x5318  ldc.i4.s 0x30
0x531a  callvirt instance string [mscorlib]System.String::PadLeft(int32, char)
0x531f  stloc.0
0x5320  ldloc.0
0x5321  ldstr    aHhmmss// "HHmmss"
0x5326  ldnull
0x5327  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ParseExact(string, string, class [mscorlib]System.IFormatProvider)
0x532c  ret
```
