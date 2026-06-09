# Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::IsNativeDQConnectionString

- ea: `0xb000`
- end: `0xb02d`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::IsNativeDQConnectionString`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xaf90`

## callees

- `0xb000`

## pseudocode

```c

```

## disassembly

```asm
0xb000  newobj   instance void [System.Data]System.Data.Common.DbConnectionStringBuilder::.ctor()
0xb005  dup
0xb006  ldarg.0
0xb007  callvirt instance void [System.Data]System.Data.Common.DbConnectionStringBuilder::set_ConnectionString(string)
0xb00c  ldstr    aDataSource// "data source"
0xb011  callvirt instance object [System.Data]System.Data.Common.DbConnectionStringBuilder::get_Item(string)
0xb016  isinst   [mscorlib]System.String
0xb01b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb020  ldc.i4.0
0xb021  ceq
0xb023  stloc.0
0xb024  leave.s  loc_B02B
0xb026  pop
0xb027  ldc.i4.0
0xb028  stloc.0
0xb029  leave.s  loc_B02B
0xb02b  ldloc.0
0xb02c  ret
```
