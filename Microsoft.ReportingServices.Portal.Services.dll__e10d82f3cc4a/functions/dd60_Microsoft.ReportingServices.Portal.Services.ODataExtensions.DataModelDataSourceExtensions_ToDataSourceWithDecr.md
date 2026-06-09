# Microsoft.ReportingServices.Portal.Services.ODataExtensions.DataModelDataSourceExtensions::ToDataSourceWithDecryptedSecret

- ea: `0xdd60`
- end: `0xdee5`
- name: `Microsoft.ReportingServices.Portal.Services.ODataExtensions.DataModelDataSourceExtensions::ToDataSourceWithDecryptedSecret`
- size: `389`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x6ed0`
- `0x1d280`
- `0x1d290`
- `0x1d480`

## callees

- `0xdd60`
- `0xe050`

## pseudocode

```c

```

## disassembly

```asm
0xdd60  ldarg.0
0xdd61  callvirt instance valuetype [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity/DataModelDataSourceKind [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_DSKind()
0xdd66  call     string Microsoft.ReportingServices.Portal.Services.ODataExtensions.DataModelDataSourceExtensions::GetDataSourceType(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceKind kind)
0xdd6b  stloc.0
0xdd6c  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::.ctor()
0xdd71  dup
0xdd72  ldarg.0
0xdd73  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_DataSourceId()
0xdd78  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_Id(valuetype [mscorlib]System.Guid)
0xdd7d  dup
0xdd7e  ldarg.0
0xdd7f  callvirt instance string [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_CreatedBy()
0xdd84  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_CreatedBy(string)
0xdd89  dup
0xdd8a  ldarg.0
0xdd8b  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_CreatedDate()
0xdd90  call     valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::op_Implicit(valuetype [mscorlib]System.DateTime)
0xdd95  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_CreatedDate(valuetype [mscorlib]System.DateTimeOffset)
0xdd9a  dup
0xdd9b  ldarg.0
0xdd9c  callvirt instance string [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_ModifiedBy()
0xdda1  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_ModifiedBy(string)
0xdda6  dup
0xdda7  ldarg.0
0xdda8  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_ModifiedDate()
0xddad  call     valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::op_Implicit(valuetype [mscorlib]System.DateTime)
0xddb2  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_ModifiedDate(valuetype [mscorlib]System.DateTimeOffset)
0xddb7  dup
0xddb8  ldnull
0xddb9  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::set_DataSourceSubType(string)
0xddbe  dup
0xddbf  ldc.i4.1
0xddc0  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::set_IsEnabled(bool)
0xddc5  dup
0xddc6  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::.ctor()
0xddcb  dup
0xddcc  ldarg.0
0xddcd  callvirt instance valuetype [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity/DataModelDataSourceType [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_DSType()
0xddd2  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::set_Type(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceType)
0xddd7  dup
0xddd8  ldarg.0
0xddd9  callvirt instance valuetype [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity/DataModelDataSourceKind [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_DSKind()
0xddde  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::set_Kind(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceKind)
0xdde3  dup
0xdde4  ldarg.0
0xdde5  callvirt instance valuetype [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity/DataModelDataSourceAuthType [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_AuthType()
0xddea  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::set_AuthType(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceAuthType)
0xddef  dup
0xddf0  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::get_Current()
0xddf5  callvirt instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::get_CatalogCrypto()
0xddfa  ldarg.0
0xddfb  callvirt instance unsigned int8[] [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_Username()
0xde00  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto::DecryptToString(unsigned int8[])
0xde05  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::set_Username(string)
0xde0a  dup
0xde0b  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::get_Current()
0xde10  callvirt instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::get_CatalogCrypto()
0xde15  ldarg.0
0xde16  callvirt instance unsigned int8[] [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_Password()
0xde1b  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto::DecryptToString(unsigned int8[])
0xde20  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::set_Secret(string)
0xde25  dup
0xde26  ldarg.0
0xde27  callvirt instance string [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_ModelConnectionName()
0xde2c  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::set_ModelConnectionName(string)
0xde31  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::set_DataModelDataSource(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource)
0xde36  dup
0xde37  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::get_Current()
0xde3c  callvirt instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::get_CatalogCrypto()
0xde41  ldarg.0
0xde42  callvirt instance unsigned int8[] [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_ConnectionString()
0xde47  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto::DecryptToString(unsigned int8[])
0xde4c  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::set_ConnectionString(string)
0xde51  dup
0xde52  ldloc.0
0xde53  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::set_DataSourceType(string)
0xde58  dup
0xde59  ldarg.0
0xde5a  callvirt instance valuetype [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity/DataModelDataSourceAuthType [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_AuthType()
0xde5f  ldc.i4.2
0xde60  beq.s    loc_DE65
0xde62  ldc.i4.1
0xde63  br.s     loc_DE66
0xde65  ldc.i4.2
0xde66  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::set_CredentialRetrieval(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialRetrievalType)
0xde6b  dup
0xde6c  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsStoredInServer::.ctor()
0xde71  dup
0xde72  ldarg.0
0xde73  callvirt instance valuetype [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity/DataModelDataSourceAuthType [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_AuthType()
0xde78  ldc.i4.6
0xde79  ceq
0xde7b  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsStoredInServer::set_ImpersonateAuthenticatedUser(bool)
0xde80  dup
0xde81  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::get_Current()
0xde86  callvirt instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::get_CatalogCrypto()
0xde8b  ldarg.0
0xde8c  callvirt instance unsigned int8[] [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_Password()
0xde91  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto::DecryptToString(unsigned int8[])
0xde96  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsStoredInServer::set_Password(string)
0xde9b  dup
0xde9c  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::get_Current()
0xdea1  callvirt instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::get_CatalogCrypto()
0xdea6  ldarg.0
0xdea7  callvirt instance unsigned int8[] [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_Username()
0xdeac  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto::DecryptToString(unsigned int8[])
0xdeb1  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsStoredInServer::set_UserName(string)
0xdeb6  dup
0xdeb7  ldarg.0
0xdeb8  callvirt instance valuetype [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity/DataModelDataSourceAuthType [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_AuthType()
0xdebd  ldc.i4.3
0xdebe  beq.s    loc_DECB
0xdec0  ldarg.0
0xdec1  callvirt instance valuetype [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity/DataModelDataSourceAuthType [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity::get_AuthType()
0xdec6  ldc.i4.6
0xdec7  ceq
0xdec9  br.s     loc_DECC
0xdecb  ldc.i4.1
0xdecc  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsStoredInServer::set_UseAsWindowsCredentials(bool)
0xded1  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::set_CredentialsInServer(class [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsStoredInServer)
0xded6  dup
0xded7  ldc.i4.0
0xded8  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::set_IsReference(bool)
0xdedd  dup
0xdede  ldc.i4.1
0xdedf  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::set_IsConnectionStringOverridden(bool)
0xdee4  ret
```
