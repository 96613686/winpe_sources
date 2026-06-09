# Microsoft.ReportingServices.Diagnostics.Dumper::ShouldDump

- ea: `0x98d0`
- end: `0x9915`
- name: `Microsoft.ReportingServices.Diagnostics.Dumper::ShouldDump`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x10420`

## callees

- `0x9600`
- `0x98d0`
- `0x9920`
- `0xa960`

## pseudocode

```c

```

## disassembly

```asm
0x98d0  call     valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.Globals::get_CurrentApplication()
0x98d5  ldc.i4.1
0x98d6  beq.s    loc_9902
0x98d8  call     valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.Globals::get_CurrentApplication()
0x98dd  brfalse.s loc_9902
0x98df  call     valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.Globals::get_CurrentApplication()
0x98e4  ldc.i4.s 0xA
0x98e6  beq.s    loc_9902
0x98e8  call     valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.Globals::get_CurrentApplication()
0x98ed  ldc.i4.3
0x98ee  beq.s    loc_9902
0x98f0  call     valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.Globals::get_CurrentApplication()
0x98f5  ldc.i4.4
0x98f6  beq.s    loc_9902
0x98f8  call     valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.Globals::get_CurrentApplication()
0x98fd  ldc.i4.5
0x98fe  beq.s    loc_9902
0x9900  ldc.i4.0
0x9901  ret
0x9902  call     valuetype [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.DumperFlags Microsoft.ReportingServices.Diagnostics.Dumper::get_SqlDumperFlagRetriver()
0x9907  ldc.i4.2
0x9908  and
0x9909  ldc.i4.2
0x990a  bne.un.s loc_990E
0x990c  ldc.i4.0
0x990d  ret
0x990e  ldarg.0
0x990f  call     bool Microsoft.ReportingServices.Diagnostics.Dumper::IsDumpException(class [mscorlib]System.Exception optionalException)
0x9914  ret
```
