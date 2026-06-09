# Microsoft.ReportingServices.Library.KeyStorage::DeletePowerBIInformation

- ea: `0x2be0`
- end: `0x2c02`
- name: `Microsoft.ReportingServices.Library.KeyStorage::DeletePowerBIInformation`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x28c0`

## callees

- `0x2be0`
- `0x6c60`
- `0x70e0`

## string_xrefs

- `0x2be0`: `DELETE FROM ConfigurationInfo\n                                where [NAME] IN ('ClientId', \n                                                'AppObjectId', \n                                                'TenantName', \n                                                'TenantId', \n                                                'ClientSecret', \n                                                'ResourceUrl', \n                                                'AuthorizationUrl', \n      `

## pseudocode

```c

```

## disassembly

```asm
0x2be0  ldstr    aDeleteFromConf_0// "DELETE FROM ConfigurationInfo\r\n      "...
0x2be5  stloc.0
0x2be6  ldarg.0
0x2be7  ldloc.0
0x2be8  call     instance class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommandQuery(string query)
0x2bed  stloc.1
0x2bee  ldloc.1
0x2bef  callvirt instance int32 Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x2bf4  pop
0x2bf5  leave.s  loc_2C01
0x2bf7  ldloc.1
0x2bf8  brfalse.s loc_2C00
0x2bfa  ldloc.1
0x2bfb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2c00  endfinally
0x2c01  ret
```
