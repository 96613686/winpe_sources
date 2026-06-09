# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogPathFromGuid

- ea: `0x1a00`
- end: `0x1a70`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogPathFromGuid`
- size: `112`
- prototype: ``
- caller_count: `15`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a70`
- `0x1b30`
- `0x1e40`
- `0x1e60`
- `0x2290`
- `0x23f0`
- `0x5a50`
- `0x5ac0`
- `0x5fc0`
- `0x65d0`
- `0x6ed0`
- `0x1e6d0`
- `0x1ed70`
- `0x1ee90`
- `0x1f010`

## callees

- `0x1a00`
- `0x128e0`
- `0x1ccd0`

## pseudocode

```c

```

## disassembly

```asm
0x1a00  newobj   instance void <>c__DisplayClass16_0::.ctor()
0x1a05  stloc.0
0x1a06  ldloc.0
0x1a07  ldarg.0
0x1a08  stfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass16_0::rsService
0x1a0d  ldloc.0
0x1a0e  ldarg.1
0x1a0f  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass16_0::key
0x1a14  ldnull
0x1a15  stloc.1
0x1a16  ldloc.0
0x1a17  ldnull
0x1a18  stfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath <>c__DisplayClass16_0::catalogItemPath
0x1a1d  ldloc.0
0x1a1e  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass16_0::rsService
0x1a23  ldloc.0
0x1a24  ldftn    instance void <>c__DisplayClass16_0::<GetCatalogPathFromGuid>b__0()
0x1a2a  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x1a2f  ldc.i4.1
0x1a30  call     void Microsoft.ReportingServices.Portal.Services.Extensions.RsServiceExtensions::ExecuteStorageAction(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Action action, valuetype [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionTransactionType transactionType)
0x1a35  ldloc.0
0x1a36  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath <>c__DisplayClass16_0::catalogItemPath
0x1a3b  brtrue.s loc_1A54
0x1a3d  ldloc.0
0x1a3e  ldflda   valuetype [mscorlib]System.Guid <>c__DisplayClass16_0::key
0x1a43  constrained. [mscorlib]System.Guid
0x1a49  callvirt instance string [mscorlib]System.Object::ToString()
0x1a4e  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ItemNotFoundException::.ctor(string)
0x1a53  throw
0x1a54  ldloc.0
0x1a55  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath <>c__DisplayClass16_0::catalogItemPath
0x1a5a  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x1a5f  stloc.1
0x1a60  ldloc.1
0x1a61  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1a66  brfalse.s loc_1A6E
0x1a68  ldstr    asc_25576// "/"
0x1a6d  stloc.1
0x1a6e  ldloc.1
0x1a6f  ret
```
