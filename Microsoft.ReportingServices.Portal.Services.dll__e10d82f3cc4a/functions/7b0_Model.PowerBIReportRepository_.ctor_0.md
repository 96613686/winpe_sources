# Model.PowerBIReportRepository::.ctor_0

- ea: `0x7b0`
- end: `0x807`
- name: `Model.PowerBIReportRepository::.ctor_0`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x790`

## callees

- `0x7b0`

## string_xrefs

- `0x7d6`: `systemService`

## pseudocode

```c

```

## disassembly

```asm
0x7b0  ldarg.0
0x7b1  call     instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport::.ctor()
0x7b6  ldarg.1
0x7b7  brtrue.s loc_7C4
0x7b9  ldstr    aUserprincipal// "userPrincipal"
0x7be  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7c3  throw
0x7c4  ldarg.2
0x7c5  brtrue.s loc_7D2
0x7c7  ldstr    aCatalogreposit// "catalogRepository"
0x7cc  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7d1  throw
0x7d2  ldarg.s  5
0x7d4  brtrue.s loc_7E1
0x7d6  ldstr    aSystemservice// "systemService"
0x7db  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7e0  throw
0x7e1  ldarg.0
0x7e2  ldarg.1
0x7e3  stfld    class [mscorlib]System.Security.Principal.IPrincipal Model.PowerBIReportRepository::_userPrincipal
0x7e8  ldarg.0
0x7e9  ldarg.2
0x7ea  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Model.PowerBIReportRepository::_catalogRepository
0x7ef  ldarg.0
0x7f0  ldarg.3
0x7f1  stfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataAccessor Model.PowerBIReportRepository::_catalogAccessor
0x7f6  ldarg.0
0x7f7  ldarg.s  4
0x7f9  stfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelDataSourceAccessor Model.PowerBIReportRepository::_catalogDataModelDataSourceAccessor
0x7fe  ldarg.0
0x7ff  ldarg.s  5
0x801  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Model.PowerBIReportRepository::_systemService
0x806  ret
```
