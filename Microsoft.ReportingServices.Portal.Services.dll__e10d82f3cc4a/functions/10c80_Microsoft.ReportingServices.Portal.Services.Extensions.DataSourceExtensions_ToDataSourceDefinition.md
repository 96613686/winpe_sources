# Microsoft.ReportingServices.Portal.Services.Extensions.DataSourceExtensions::ToDataSourceDefinition

- ea: `0x10c80`
- end: `0x10d92`
- name: `Microsoft.ReportingServices.Portal.Services.Extensions.DataSourceExtensions::ToDataSourceDefinition`
- size: `274`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x2850`
- `0x49e0`
- `0x11300`
- `0x11460`
- `0x11510`

## callees

- `0x10c80`

## pseudocode

```c

```

## disassembly

```asm
0x10c80  ldarg.0
0x10c81  brtrue.s loc_10C85
0x10c83  ldnull
0x10c84  ret
0x10c85  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::.ctor()
0x10c8a  dup
0x10c8b  ldarg.0
0x10c8c  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_IsEnabled()
0x10c91  stfld    bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::Enabled
0x10c96  dup
0x10c97  ldc.i4.1
0x10c98  stfld    bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::EnabledSpecified
0x10c9d  dup
0x10c9e  ldarg.0
0x10c9f  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_ConnectionString()
0x10ca4  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::ConnectString
0x10ca9  dup
0x10caa  ldarg.0
0x10cab  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_IsConnectionStringOverridden()
0x10cb0  ldc.i4.0
0x10cb1  ceq
0x10cb3  stfld    bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::UseOriginalConnectString
0x10cb8  dup
0x10cb9  ldarg.0
0x10cba  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_IsOriginalConnectionStringExpressionBased()
0x10cbf  stfld    bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::OriginalConnectStringExpressionBased
0x10cc4  dup
0x10cc5  ldarg.0
0x10cc6  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataSourceType()
0x10ccb  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::Extension
0x10cd0  stloc.0
0x10cd1  ldloc.0
0x10cd2  ldarg.0
0x10cd3  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialRetrievalType [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_CredentialRetrieval()
0x10cd8  stfld    valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.CredentialRetrievalEnum [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::CredentialRetrieval
0x10cdd  ldloc.0
0x10cde  ldfld    valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.CredentialRetrievalEnum [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::CredentialRetrieval
0x10ce3  stloc.1
0x10ce4  ldloc.1
0x10ce5  switch   loc_10D5D, loc_10CFB, loc_10D89
0x10cf6  br       loc_10D90
0x10cfb  ldarg.0
0x10cfc  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsStoredInServer [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_CredentialsInServer()
0x10d01  brfalse  loc_10D90
0x10d06  ldloc.0
0x10d07  ldarg.0
0x10d08  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsStoredInServer [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_CredentialsInServer()
0x10d0d  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsStoredInServer::get_UserName()
0x10d12  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::UserName
0x10d17  ldloc.0
0x10d18  ldarg.0
0x10d19  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsStoredInServer [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_CredentialsInServer()
0x10d1e  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsStoredInServer::get_Password()
0x10d23  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::Password
0x10d28  ldloc.0
0x10d29  ldarg.0
0x10d2a  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsStoredInServer [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_CredentialsInServer()
0x10d2f  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsStoredInServer::get_UseAsWindowsCredentials()
0x10d34  stfld    bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::WindowsCredentials
0x10d39  ldloc.0
0x10d3a  ldarg.0
0x10d3b  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsStoredInServer [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_CredentialsInServer()
0x10d40  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsStoredInServer::get_ImpersonateAuthenticatedUser()
0x10d45  stfld    bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::ImpersonateUser
0x10d4a  ldloc.0
0x10d4b  ldarg.0
0x10d4c  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsStoredInServer [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_CredentialsInServer()
0x10d51  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsStoredInServer::get_ImpersonateAuthenticatedUser()
0x10d56  stfld    bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::ImpersonateUserSpecified
0x10d5b  br.s     loc_10D90
0x10d5d  ldarg.0
0x10d5e  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsSuppliedByUser [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_CredentialsByUser()
0x10d63  brfalse.s loc_10D90
0x10d65  ldloc.0
0x10d66  ldarg.0
0x10d67  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsSuppliedByUser [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_CredentialsByUser()
0x10d6c  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsSuppliedByUser::get_DisplayText()
0x10d71  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::Prompt
0x10d76  ldloc.0
0x10d77  ldarg.0
0x10d78  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsSuppliedByUser [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_CredentialsByUser()
0x10d7d  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsSuppliedByUser::get_UseAsWindowsCredentials()
0x10d82  stfld    bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::WindowsCredentials
0x10d87  br.s     loc_10D90
0x10d89  ldloc.0
0x10d8a  ldc.i4.1
0x10d8b  stfld    bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::WindowsCredentials
0x10d90  ldloc.0
0x10d91  ret
```
