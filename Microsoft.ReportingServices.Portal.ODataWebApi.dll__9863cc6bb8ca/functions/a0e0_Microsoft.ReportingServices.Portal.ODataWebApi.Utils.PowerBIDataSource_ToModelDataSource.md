# Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PowerBIDataSource::ToModelDataSource

- ea: `0xa0e0`
- end: `0xa145`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PowerBIDataSource::ToModelDataSource`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0xf0f0`

## callees

- `0xa000`
- `0xa020`
- `0xa040`
- `0xa060`
- `0xa080`
- `0xa0a0`
- `0xa0c0`

## pseudocode

```c

```

## disassembly

```asm
0xa0e0  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::.ctor()
0xa0e5  dup
0xa0e6  ldarg.0
0xa0e7  call     instance string Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PowerBIDataSource::get_ConnectionString()
0xa0ec  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::set_ConnectionString(string)
0xa0f1  dup
0xa0f2  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::.ctor()
0xa0f7  dup
0xa0f8  ldarg.0
0xa0f9  call     instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceAuthType Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PowerBIDataSource::get_AuthType()
0xa0fe  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::set_AuthType(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceAuthType)
0xa103  dup
0xa104  ldarg.0
0xa105  call     instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceType Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PowerBIDataSource::get_Type()
0xa10a  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::set_Type(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceType)
0xa10f  dup
0xa110  ldarg.0
0xa111  call     instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceKind Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PowerBIDataSource::get_Kind()
0xa116  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::set_Kind(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceKind)
0xa11b  dup
0xa11c  ldarg.0
0xa11d  call     instance string Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PowerBIDataSource::get_Username()
0xa122  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::set_Username(string)
0xa127  dup
0xa128  ldarg.0
0xa129  call     instance string Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PowerBIDataSource::get_Secret()
0xa12e  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::set_Secret(string)
0xa133  dup
0xa134  ldarg.0
0xa135  call     instance string Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PowerBIDataSource::get_DataSourceIdentifier()
0xa13a  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::set_ModelConnectionName(string)
0xa13f  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::set_DataModelDataSource(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource)
0xa144  ret
```
