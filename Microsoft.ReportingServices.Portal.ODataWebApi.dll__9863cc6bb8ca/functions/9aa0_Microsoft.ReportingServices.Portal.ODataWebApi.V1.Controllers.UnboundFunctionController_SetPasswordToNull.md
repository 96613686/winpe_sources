# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::SetPasswordToNull

- ea: `0x9aa0`
- end: `0x9add`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::SetPasswordToNull`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x96a0`

## callees

- `0x9aa0`

## pseudocode

```c

```

## disassembly

```asm
0x9aa0  ldarg.1
0x9aa1  brtrue.s loc_9AA4
0x9aa3  ret
0x9aa4  ldarg.1
0x9aa5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::GetEnumerator()
0x9aaa  stloc.0
0x9aab  br.s     loc_9AC8
0x9aad  ldloc.0
0x9aae  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::get_Current()
0x9ab3  stloc.1
0x9ab4  ldloc.1
0x9ab5  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsStoredInServer [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_CredentialsInServer()
0x9aba  brfalse.s loc_9AC8
0x9abc  ldloc.1
0x9abd  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsStoredInServer [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_CredentialsInServer()
0x9ac2  ldnull
0x9ac3  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialsStoredInServer::set_Password(string)
0x9ac8  ldloc.0
0x9ac9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9ace  brtrue.s loc_9AAD
0x9ad0  leave.s  loc_9ADC
0x9ad2  ldloc.0
0x9ad3  brfalse.s loc_9ADB
0x9ad5  ldloc.0
0x9ad6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9adb  endfinally
0x9adc  ret
```
