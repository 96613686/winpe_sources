# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ValidateUpdateForFields

- ea: `0x4c80`
- end: `0x4d74`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ValidateUpdateForFields`
- size: `244`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x49e0`
- `0x4b50`

## callees

- `0x4c80`

## string_xrefs

- `0x4d68`: `Did not update password.`

## pseudocode

```c

```

## disassembly

```asm
0x4c80  ldc.i4.0
0x4c81  stloc.0
0x4c82  ldc.i4.0
0x4c83  stloc.1
0x4c84  ldarg.3
0x4c85  ldc.i4.0
0x4c86  stind.i1
0x4c87  ldarg.s  4
0x4c89  ldc.i4.0
0x4c8a  stind.i1
0x4c8b  ldarg.1
0x4c8c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x4c91  stloc.2
0x4c92  br       loc_4D42
0x4c97  ldloc.2
0x4c98  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x4c9d  stloc.3
0x4c9e  ldloc.3
0x4c9f  ldstr    aName// "Name"
0x4ca4  ldc.i4.5
0x4ca5  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x4caa  brfalse.s loc_4CD9
0x4cac  ldloc.3
0x4cad  ldstr    aDescription// "Description"
0x4cb2  ldc.i4.5
0x4cb3  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x4cb8  brfalse.s loc_4CD9
0x4cba  ldloc.3
0x4cbb  ldstr    aHidden// "Hidden"
0x4cc0  ldc.i4.5
0x4cc1  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x4cc6  brfalse.s loc_4CD9
0x4cc8  ldloc.3
0x4cc9  ldstr    aPath// "Path"
0x4cce  ldc.i4.5
0x4ccf  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x4cd4  brfalse.s loc_4CD9
0x4cd6  ldarg.3
0x4cd7  ldc.i4.1
0x4cd8  stind.i1
0x4cd9  ldloc.3
0x4cda  ldstr    aCredentialsins// "CredentialsInServer"
0x4cdf  ldc.i4.5
0x4ce0  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x4ce5  brtrue.s loc_4D06
0x4ce7  ldarg.2
0x4ce8  brfalse.s loc_4D06
0x4cea  ldarg.2
0x4ceb  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsStoredInServer [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_CredentialsInServer()
0x4cf0  brfalse.s loc_4D06
0x4cf2  ldarg.2
0x4cf3  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsStoredInServer [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_CredentialsInServer()
0x4cf8  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsStoredInServer::get_Password()
0x4cfd  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x4d02  brtrue.s loc_4D06
0x4d04  ldc.i4.1
0x4d05  stloc.0
0x4d06  ldloc.3
0x4d07  ldstr    aConnectiontype// "ConnectionType"
0x4d0c  ldc.i4.5
0x4d0d  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x4d12  brtrue.s loc_4D22
0x4d14  ldarg.2
0x4d15  brfalse.s loc_4D22
0x4d17  ldarg.2
0x4d18  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialRetrievalType [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_CredentialRetrieval()
0x4d1d  ldc.i4.1
0x4d1e  bne.un.s loc_4D22
0x4d20  ldc.i4.1
0x4d21  stloc.1
0x4d22  ldloc.3
0x4d23  ldstr    aDescription// "Description"
0x4d28  ldc.i4.5
0x4d29  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x4d2e  brfalse.s loc_4D3E
0x4d30  ldloc.3
0x4d31  ldstr    aHidden// "Hidden"
0x4d36  ldc.i4.5
0x4d37  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x4d3c  brtrue.s loc_4D42
0x4d3e  ldarg.s  4
0x4d40  ldc.i4.1
0x4d41  stind.i1
0x4d42  ldloc.2
0x4d43  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4d48  brtrue   loc_4C97
0x4d4d  leave.s  loc_4D59
0x4d4f  ldloc.2
0x4d50  brfalse.s loc_4D58
0x4d52  ldloc.2
0x4d53  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4d58  endfinally
0x4d59  ldarg.3
0x4d5a  ldind.u1
0x4d5b  brfalse.s loc_4D63
0x4d5d  ldloc.0
0x4d5e  ldc.i4.0
0x4d5f  ceq
0x4d61  br.s     loc_4D64
0x4d63  ldc.i4.0
0x4d64  ldloc.1
0x4d65  and
0x4d66  brfalse.s loc_4D73
0x4d68  ldstr    aDidNotUpdatePa// "Did not update password."
0x4d6d  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4d72  throw
0x4d73  ret
```
