# Microsoft.ReportingServices.Portal.Services.Extensions.DataSourceExtensions::ToDataSourceDefinition2010

- ea: `0x11460`
- end: `0x11509`
- name: `Microsoft.ReportingServices.Portal.Services.Extensions.DataSourceExtensions::ToDataSourceDefinition2010`
- size: `169`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x5b20`
- `0x113e0`
- `0x11510`

## callees

- `0x10c80`
- `0x11540`

## pseudocode

```c

```

## disassembly

```asm
0x11460  ldarg.0
0x11461  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition Microsoft.ReportingServices.Portal.Services.Extensions.DataSourceExtensions::ToDataSourceDefinition(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource dataSource)
0x11466  stloc.0
0x11467  newobj   instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceDefinition::.ctor()
0x1146c  dup
0x1146d  ldloc.0
0x1146e  ldfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::Extension
0x11473  callvirt instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceDefinition::set_Extension(string)
0x11478  dup
0x11479  ldloc.0
0x1147a  ldfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::ConnectString
0x1147f  callvirt instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceDefinition::set_ConnectString(string)
0x11484  dup
0x11485  ldloc.0
0x11486  ldfld    bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::UseOriginalConnectString
0x1148b  callvirt instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceDefinition::set_UseOriginalConnectString(bool)
0x11490  dup
0x11491  ldloc.0
0x11492  ldfld    bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::OriginalConnectStringExpressionBased
0x11497  callvirt instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceDefinition::set_OriginalConnectStringExpressionBased(bool)
0x1149c  dup
0x1149d  ldloc.0
0x1149e  ldfld    valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.CredentialRetrievalEnum [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::CredentialRetrieval
0x114a3  call     valuetype [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.CredentialRetrievalEnum Microsoft.ReportingServices.Portal.Services.Extensions.DataSourceExtensions::ConvertTo2010(valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.CredentialRetrievalEnum credentialsRetrival)
0x114a8  callvirt instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceDefinition::set_CredentialRetrieval(valuetype [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.CredentialRetrievalEnum)
0x114ad  dup
0x114ae  ldloc.0
0x114af  ldfld    bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::WindowsCredentials
0x114b4  callvirt instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceDefinition::set_WindowsCredentials(bool)
0x114b9  dup
0x114ba  ldloc.0
0x114bb  ldfld    bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::ImpersonateUser
0x114c0  callvirt instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceDefinition::set_ImpersonateUser(bool)
0x114c5  dup
0x114c6  ldloc.0
0x114c7  ldfld    bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::ImpersonateUserSpecified
0x114cc  callvirt instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceDefinition::set_ImpersonateUserSpecified(bool)
0x114d1  dup
0x114d2  ldloc.0
0x114d3  ldfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::Prompt
0x114d8  callvirt instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceDefinition::set_Prompt(string)
0x114dd  dup
0x114de  ldloc.0
0x114df  ldfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::UserName
0x114e4  callvirt instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceDefinition::set_UserName(string)
0x114e9  dup
0x114ea  ldloc.0
0x114eb  ldfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::Password
0x114f0  callvirt instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceDefinition::set_Password(string)
0x114f5  dup
0x114f6  ldloc.0
0x114f7  ldfld    bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition::Enabled
0x114fc  callvirt instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceDefinition::set_Enabled(bool)
0x11501  dup
0x11502  ldc.i4.1
0x11503  callvirt instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceDefinition::set_EnabledSpecified(bool)
0x11508  ret
```
