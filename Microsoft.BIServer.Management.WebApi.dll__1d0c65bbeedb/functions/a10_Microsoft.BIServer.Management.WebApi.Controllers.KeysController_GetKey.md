# Microsoft.BIServer.Management.WebApi.Controllers.KeysController::GetKey

- ea: `0xa10`
- end: `0xa43`
- name: `Microsoft.BIServer.Management.WebApi.Controllers.KeysController::GetKey`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xa10`

## pseudocode

```c

```

## disassembly

```asm
0xa10  newobj   instance void [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.Key.KeyRepository::.ctor()
0xa15  stloc.0
0xa16  ldloc.0
0xa17  callvirt instance unsigned int8[] [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.Key.IKeyRepository::GetEncryptedSymmetricKey()
0xa1c  stloc.1
0xa1d  ldloc.1
0xa1e  brfalse.s loc_A24
0xa20  ldloc.1
0xa21  ldlen
0xa22  brtrue.s loc_A2D
0xa24  ldarg.0
0xa25  callvirt instance class [System.Web.Http]System.Web.Http.Results.NotFoundResult [System.Web.Http]System.Web.Http.ApiController::NotFound()
0xa2a  stloc.2
0xa2b  leave.s  loc_A41
0xa2d  ldarg.0
0xa2e  ldloc.1
0xa2f  callvirt T0x2B00000A
0xa34  stloc.2
0xa35  leave.s  loc_A41
0xa37  ldloc.0
0xa38  brfalse.s loc_A40
0xa3a  ldloc.0
0xa3b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa40  endfinally
0xa41  ldloc.2
0xa42  ret
```
