# Microsoft.ReportingServices.DataExtensions.CommandWrapper::RewriteMultiValueParameters

- ea: `0x2b30`
- end: `0x2bdd`
- name: `Microsoft.ReportingServices.DataExtensions.CommandWrapper::RewriteMultiValueParameters`
- size: `173`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x2b30`
- `0x30e0`
- `0x13a70`

## string_xrefs

- `0x2b57`: `Oracle.ManagedDataAccess.Client.OracleCommand`
- `0x2b85`: `Teradata.Client.Provider.TdCommand`
- `0x2baa`: `MultiValueRewrite was called for unsupported data provider`

## pseudocode

```c

```

## disassembly

```asm
0x2b30  ldarg.0
0x2b31  call     instance class [System.Data]System.Data.IDbCommand Microsoft.ReportingServices.DataExtensions.CommandWrapper::get_UnderlyingCommand()
0x2b36  stloc.0
0x2b37  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DataExtensionTracer()
0x2b3c  ldloc.0
0x2b3d  isinst   [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand
0x2b42  brtrue.s loc_2BA9
0x2b44  ldloc.0
0x2b45  isinst   [System.Data.OracleClient]System.Data.OracleClient.OracleCommand
0x2b4a  brtrue.s loc_2BA9
0x2b4c  ldloc.0
0x2b4d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2b52  callvirt instance string [mscorlib]System.Type::get_FullName()
0x2b57  ldstr    aOracleManagedd// "Oracle.ManagedDataAccess.Client.OracleC"...
0x2b5c  callvirt instance bool [mscorlib]System.String::Contains(string)
0x2b61  brtrue.s loc_2BA9
0x2b63  ldloc.0
0x2b64  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2b69  callvirt instance string [mscorlib]System.Type::get_FullName()
0x2b6e  ldstr    aMicrosoftSqlse// "Microsoft.SqlServer.DataWarehouse"
0x2b73  callvirt instance bool [mscorlib]System.String::Contains(string)
0x2b78  brtrue.s loc_2BA9
0x2b7a  ldloc.0
0x2b7b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2b80  callvirt instance string [mscorlib]System.Type::get_FullName()
0x2b85  ldstr    aTeradataClient// "Teradata.Client.Provider.TdCommand"
0x2b8a  ldc.i4.4
0x2b8b  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x2b90  brtrue.s loc_2BA9
0x2b92  ldloc.0
0x2b93  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2b98  callvirt instance string [mscorlib]System.Type::get_FullName()
0x2b9d  ldstr    aCastleProxies// "Castle.Proxies"
0x2ba2  callvirt instance bool [mscorlib]System.String::Contains(string)
0x2ba7  br.s     loc_2BAA
0x2ba9  ldc.i4.1
0x2baa  ldstr    aMultivaluerewr// "MultiValueRewrite was called for unsupp"...
0x2baf  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x2bb4  ldloc.0
0x2bb5  ldarg.0
0x2bb6  ldfld    class Microsoft.ReportingServices.DataExtensions.ParameterCollectionWrapper Microsoft.ReportingServices.DataExtensions.CommandWrapper::m_parameterCollection
0x2bbb  ldarg.1
0x2bbc  ldarg.2
0x2bbd  call     string Microsoft.ReportingServices.ProcessingRenderingCommon.CommandWrapperHelper::WriteMultiValueParametersIntoCommandText(class [System.Data]System.Data.IDbCommand command, class Microsoft.ReportingServices.DataExtensions.ParameterCollectionWrapper parameters, int32 sysParameterCount, valuetype Microsoft.ReportingServices.ProcessingRenderingCommon.ServerType serverType)
0x2bc2  stloc.1
0x2bc3  ldloc.1
0x2bc4  ldloc.0
0x2bc5  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x2bca  ldc.i4.4
0x2bcb  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x2bd0  brtrue.s loc_2BDB
0x2bd2  ldloc.0
0x2bd3  ldloc.1
0x2bd4  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x2bd9  ldc.i4.1
0x2bda  ret
0x2bdb  ldc.i4.0
0x2bdc  ret
```
