# Microsoft.ReportingServices.Library.KeyStorage::GetKeyCount

- ea: `0x2f40`
- end: `0x2f66`
- name: `Microsoft.ReportingServices.Library.KeyStorage::GetKeyCount`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2f00`

## callees

- `0x2f40`
- `0x6c60`
- `0x7190`

## string_xrefs

- `0x2f41`: `select count(*) from (select distinct [InstallationID] from [keys] where [SymmetricKey] is not null and [client] >= 0) as A`

## pseudocode

```c

```

## disassembly

```asm
0x2f40  ldarg.0
0x2f41  ldstr    aSelectCountFro// "select count(*) from (select distinct ["...
0x2f46  call     instance class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommandQuery(string query)
0x2f4b  stloc.0
0x2f4c  ldloc.0
0x2f4d  callvirt instance object Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteScalar()
0x2f52  unbox.any [mscorlib]System.Int32
0x2f57  stloc.1
0x2f58  leave.s  loc_2F64
0x2f5a  ldloc.0
0x2f5b  brfalse.s loc_2F63
0x2f5d  ldloc.0
0x2f5e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2f63  endfinally
0x2f64  ldloc.1
0x2f65  ret
```
