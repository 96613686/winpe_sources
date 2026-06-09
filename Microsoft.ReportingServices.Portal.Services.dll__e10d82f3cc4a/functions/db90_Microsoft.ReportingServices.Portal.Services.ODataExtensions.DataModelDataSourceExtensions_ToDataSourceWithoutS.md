# Microsoft.ReportingServices.Portal.Services.ODataExtensions.DataModelDataSourceExtensions::ToDataSourceWithoutSecret

- ea: `0xdb90`
- end: `0xdce7`
- name: `Microsoft.ReportingServices.Portal.Services.ODataExtensions.DataModelDataSourceExtensions::ToDataSourceWithoutSecret`
- size: `343`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1c7e0`
- `0x1d410`
- `0x1d450`

## callees

- `0xdb90`
- `0xdcf0`
- `0xdd30`
- `0xe080`

## pseudocode

```c

```

## disassembly

```asm
0xdb90  ldarg.0
0xdb91  brtrue.s loc_DB9E
0xdb93  ldstr    aDatasourceenti// "dataSourceEntity"
0xdb98  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xdb9d  throw
0xdb9e  ldarg.0
0xdb9f  callvirt instance valuetype [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity/DataModelDataSourceType [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_DSType()
0xdba4  ldc.i4.1
0xdba5  bne.un.s loc_DBF2
0xdba7  ldarg.0
0xdba8  callvirt instance valuetype [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity/DataModelDataSourceKind [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_DSKind()
0xdbad  ldc.i4.2
0xdbae  bne.un.s loc_DBF2
0xdbb0  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::get_Current()
0xdbb5  callvirt instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::get_CatalogCrypto()
0xdbba  ldarg.0
0xdbbb  callvirt instance unsigned int8[] [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_ConnectionString()
0xdbc0  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto::DecryptToString(unsigned int8[])
0xdbc5  ldsfld   string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.CryptoTags::ConnectionString
0xdbca  call     string Microsoft.ReportingServices.Portal.Services.ODataExtensions.DataModelDataSourceExtensions::TruncateTagIfPresent(string data, string tag)
0xdbcf  stloc.0
0xdbd0  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::get_Current()
0xdbd5  callvirt instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::get_CatalogCrypto()
0xdbda  ldarg.0
0xdbdb  callvirt instance unsigned int8[] [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_Username()
0xdbe0  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto::DecryptToString(unsigned int8[])
0xdbe5  ldsfld   string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.CryptoTags::UserName
0xdbea  call     string Microsoft.ReportingServices.Portal.Services.ODataExtensions.DataModelDataSourceExtensions::TruncateTagIfPresent(string data, string tag)
0xdbef  stloc.1
0xdbf0  br.s     loc_DC1E
0xdbf2  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::get_Current()
0xdbf7  callvirt instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::get_CatalogCrypto()
0xdbfc  ldarg.0
0xdbfd  callvirt instance unsigned int8[] [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_ConnectionString()
0xdc02  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto::DecryptToString(unsigned int8[])
0xdc07  stloc.0
0xdc08  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::get_Current()
0xdc0d  callvirt instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::get_CatalogCrypto()
0xdc12  ldarg.0
0xdc13  callvirt instance unsigned int8[] [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_Username()
0xdc18  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto::DecryptToString(unsigned int8[])
0xdc1d  stloc.1
0xdc1e  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::.ctor()
0xdc23  dup
0xdc24  ldarg.0
0xdc25  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_DataSourceId()
0xdc2a  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_Id(valuetype [mscorlib]System.Guid)
0xdc2f  dup
0xdc30  ldarg.0
0xdc31  callvirt instance string [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_CreatedBy()
0xdc36  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_CreatedBy(string)
0xdc3b  dup
0xdc3c  ldarg.0
0xdc3d  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_CreatedDate()
0xdc42  call     valuetype [mscorlib]System.DateTimeOffset Microsoft.ReportingServices.Portal.Services.ODataExtensions.DataModelDataSourceExtensions::ToDateTimeOffset(valuetype [mscorlib]System.DateTime dateTime)
0xdc47  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_CreatedDate(valuetype [mscorlib]System.DateTimeOffset)
0xdc4c  dup
0xdc4d  ldarg.0
0xdc4e  callvirt instance string [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_ModifiedBy()
0xdc53  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_ModifiedBy(string)
0xdc58  dup
0xdc59  ldarg.0
0xdc5a  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_ModifiedDate()
0xdc5f  call     valuetype [mscorlib]System.DateTimeOffset Microsoft.ReportingServices.Portal.Services.ODataExtensions.DataModelDataSourceExtensions::ToDateTimeOffset(valuetype [mscorlib]System.DateTime dateTime)
0xdc64  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_ModifiedDate(valuetype [mscorlib]System.DateTimeOffset)
0xdc69  dup
0xdc6a  ldsfld   string Microsoft.ReportingServices.Portal.Services.ODataExtensions.DataModelDataSourceExtensions::DataSourceSubTypeName
0xdc6f  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::set_DataSourceSubType(string)
0xdc74  dup
0xdc75  ldc.i4.1
0xdc76  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::set_IsEnabled(bool)
0xdc7b  dup
0xdc7c  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::.ctor()
0xdc81  dup
0xdc82  ldarg.0
0xdc83  callvirt instance valuetype [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity/DataModelDataSourceType [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_DSType()
0xdc88  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::set_Type(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceType)
0xdc8d  dup
0xdc8e  ldarg.0
0xdc8f  callvirt instance valuetype [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity/DataModelDataSourceKind [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_DSKind()
0xdc94  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::set_Kind(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceKind)
0xdc99  dup
0xdc9a  ldarg.0
0xdc9b  callvirt instance valuetype [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity/DataModelDataSourceAuthType [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_AuthType()
0xdca0  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::set_AuthType(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceAuthType)
0xdca5  dup
0xdca6  ldarg.0
0xdca7  callvirt instance valuetype [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity/DataModelDataSourceKind [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_DSKind()
0xdcac  ldarg.0
0xdcad  callvirt instance valuetype [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity/DataModelDataSourceType [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_DSType()
0xdcb2  call     valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceAuthType[] Microsoft.ReportingServices.Portal.Services.ODataExtensions.DataModelDataSourceExtensions::GetSupportedAuthKinds(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceKind datasourceKind, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceType datasourceType)
0xdcb7  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::set_SupportedAuthTypes(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceAuthType[])
0xdcbc  dup
0xdcbd  ldloc.1
0xdcbe  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::set_Username(string)
0xdcc3  dup
0xdcc4  ldsfld   string [mscorlib]System.String::Empty
0xdcc9  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::set_Secret(string)
0xdcce  dup
0xdccf  ldarg.0
0xdcd0  callvirt instance string [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_ModelConnectionName()
0xdcd5  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::set_ModelConnectionName(string)
0xdcda  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::set_DataModelDataSource(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource)
0xdcdf  dup
0xdce0  ldloc.0
0xdce1  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::set_ConnectionString(string)
0xdce6  ret
```
