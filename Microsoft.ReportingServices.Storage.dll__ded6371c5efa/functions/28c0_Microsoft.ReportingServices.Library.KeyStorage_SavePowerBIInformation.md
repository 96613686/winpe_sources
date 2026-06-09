# Microsoft.ReportingServices.Library.KeyStorage::SavePowerBIInformation

- ea: `0x28c0`
- end: `0x2990`
- name: `Microsoft.ReportingServices.Library.KeyStorage::SavePowerBIInformation`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x28c0`
- `0x2be0`
- `0x6c60`
- `0x70e0`
- `0x7320`

## string_xrefs

- `0x28c6`: `INSERT INTO ConfigurationInfo (ConfigInfoID, Name, Value)\n                                VALUES (newid(), 'ClientId', @clientIdValue), \n                                       (newid(), 'AppObjectId', @appObjectIdValue), \n                                       (newid(), 'TenantName', @tenantNameValue),\n                                       (newid(), 'TenantId', @tenantIdValue), \n                                       (newid(), 'ClientSecret', @clientSecretValue), \n                  `
- `0x295c`: `@tokenUrlValue`

## pseudocode

```c

```

## disassembly

```asm
0x28c0  ldarg.0
0x28c1  call     instance void Microsoft.ReportingServices.Library.KeyStorage::DeletePowerBIInformation()
0x28c6  ldstr    aInsertIntoConf// "INSERT INTO ConfigurationInfo (ConfigIn"...
0x28cb  stloc.0
0x28cc  ldarg.0
0x28cd  ldloc.0
0x28ce  call     instance class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommandQuery(string query)
0x28d3  stloc.1
0x28d4  ldloc.1
0x28d5  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x28da  ldstr    aClientidvalue// "@clientIdValue"
0x28df  ldarg.1
0x28e0  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x28e5  pop
0x28e6  ldloc.1
0x28e7  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x28ec  ldstr    aAppobjectidval// "@appObjectIdValue"
0x28f1  ldarg.3
0x28f2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x28f7  pop
0x28f8  ldloc.1
0x28f9  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x28fe  ldstr    aTenantnamevalu// "@tenantNameValue"
0x2903  ldarg.s  4
0x2905  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x290a  pop
0x290b  ldloc.1
0x290c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x2911  ldstr    aTenantidvalue// "@tenantIdValue"
0x2916  ldarg.s  5
0x2918  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x291d  pop
0x291e  ldloc.1
0x291f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x2924  ldstr    aClientsecretva// "@clientSecretValue"
0x2929  ldarg.2
0x292a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x292f  pop
0x2930  ldloc.1
0x2931  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x2936  ldstr    aResourceurlval// "@resourceUrlValue"
0x293b  ldarg.s  6
0x293d  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2942  pop
0x2943  ldloc.1
0x2944  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x2949  ldstr    aAuthurlvalue// "@authUrlValue"
0x294e  ldarg.s  7
0x2950  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2955  pop
0x2956  ldloc.1
0x2957  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x295c  ldstr    aTokenurlvalue// "@tokenUrlValue"
0x2961  ldarg.s  8
0x2963  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2968  pop
0x2969  ldloc.1
0x296a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x296f  ldstr    aRedirecturlsva// "@redirectUrlsValue"
0x2974  ldarg.s  9
0x2976  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x297b  pop
0x297c  ldloc.1
0x297d  callvirt instance int32 Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x2982  pop
0x2983  leave.s  loc_298F
0x2985  ldloc.1
0x2986  brfalse.s loc_298E
0x2988  ldloc.1
0x2989  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x298e  endfinally
0x298f  ret
```
