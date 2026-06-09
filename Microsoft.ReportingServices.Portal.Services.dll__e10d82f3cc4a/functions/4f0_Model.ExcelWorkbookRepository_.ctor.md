# Model.ExcelWorkbookRepository::.ctor

- ea: `0x4f0`
- end: `0x536`
- name: `Model.ExcelWorkbookRepository::.ctor`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1650`

## callees

- `0x4f0`

## string_xrefs

- `0x515`: `systemService`

## pseudocode

```c

```

## disassembly

```asm
0x4f0  ldarg.0
0x4f1  call     instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ExcelWorkbook::.ctor()
0x4f6  ldarg.1
0x4f7  brtrue.s loc_504
0x4f9  ldstr    aUserprincipal// "userPrincipal"
0x4fe  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x503  throw
0x504  ldarg.2
0x505  brtrue.s loc_512
0x507  ldstr    aCatalogreposit// "catalogRepository"
0x50c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x511  throw
0x512  ldarg.3
0x513  brtrue.s loc_520
0x515  ldstr    aSystemservice// "systemService"
0x51a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x51f  throw
0x520  ldarg.0
0x521  ldarg.1
0x522  stfld    class [mscorlib]System.Security.Principal.IPrincipal Model.ExcelWorkbookRepository::_userPrincipal
0x527  ldarg.0
0x528  ldarg.2
0x529  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Model.ExcelWorkbookRepository::_catalogRepository
0x52e  ldarg.0
0x52f  ldarg.3
0x530  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Model.ExcelWorkbookRepository::_systemService
0x535  ret
```
