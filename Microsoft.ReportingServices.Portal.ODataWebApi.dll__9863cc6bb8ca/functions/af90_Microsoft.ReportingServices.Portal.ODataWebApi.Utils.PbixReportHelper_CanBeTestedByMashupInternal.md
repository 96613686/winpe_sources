# Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::CanBeTestedByMashupInternal

- ea: `0xaf90`
- end: `0xaffe`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::CanBeTestedByMashupInternal`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xaf80`

## callees

- `0xaf90`
- `0xb000`
- `0xb030`

## pseudocode

```c

```

## disassembly

```asm
0xaf90  ldarg.0
0xaf91  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0xaf96  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceKind [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_Kind()
0xaf9b  ldc.i4.s 0x1C
0xaf9d  beq.s    loc_AFBD
0xaf9f  ldarg.0
0xafa0  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0xafa5  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceKind [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_Kind()
0xafaa  ldc.i4.s 0x1E
0xafac  beq.s    loc_AFBD
0xafae  ldarg.0
0xafaf  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0xafb4  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceKind [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_Kind()
0xafb9  ldc.i4.s 0x15
0xafbb  bne.un.s loc_AFCA
0xafbd  ldarg.0
0xafbe  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_ConnectionString()
0xafc3  call     bool Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::IsNativeDQConnectionString(string connectionString)
0xafc8  br.s     loc_AFCB
0xafca  ldc.i4.0
0xafcb  stloc.0
0xafcc  ldarg.0
0xafcd  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0xafd2  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceType [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_Type()
0xafd7  ldc.i4.2
0xafd8  bne.un.s loc_AFEC
0xafda  ldloc.0
0xafdb  brtrue.s loc_AFEA
0xafdd  ldarg.0
0xafde  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_ConnectionString()
0xafe3  call     bool Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::UsesHanaOdbcProvider(string connectionString)
0xafe8  brfalse.s loc_AFEC
0xafea  ldc.i4.0
0xafeb  ret
0xafec  ldarg.0
0xafed  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0xaff2  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceType [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_Type()
0xaff7  ldc.i4.1
0xaff8  bne.un.s loc_AFFC
0xaffa  ldc.i4.0
0xaffb  ret
0xaffc  ldc.i4.1
0xaffd  ret
```
