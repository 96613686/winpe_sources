# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateExcel

- ea: `0x3da0`
- end: `0x3e3c`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateExcel`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2a20`

## callees

- `0x3da0`
- `0x128c0`
- `0x1da20`

## pseudocode

```c

```

## disassembly

```asm
0x3da0  newobj   instance void <>c__DisplayClass86_0::.ctor()
0x3da5  stloc.0
0x3da6  ldloc.0
0x3da7  ldarg.1
0x3da8  stfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass86_0::rsService
0x3dad  ldloc.0
0x3dae  ldarg.3
0x3daf  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExcelWorkbook <>c__DisplayClass86_0::item
0x3db4  ldloc.0
0x3db5  ldarg.2
0x3db6  stfld    string <>c__DisplayClass86_0::origItemPath
0x3dbb  ldloc.0
0x3dbc  ldarg.0
0x3dbd  stfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass86_0::<>4__this
0x3dc2  ldloc.0
0x3dc3  ldarg.s  4
0x3dc5  stfld    bool <>c__DisplayClass86_0::renameOrMove
0x3dca  ldc.i4.2
0x3dcb  newarr   [mscorlib]System.String
0x3dd0  dup
0x3dd1  ldc.i4.0
0x3dd2  ldstr    aHidden// "Hidden"
0x3dd7  stelem.ref
0x3dd8  dup
0x3dd9  ldc.i4.1
0x3dda  ldstr    aDescription// "Description"
0x3ddf  stelem.ref
0x3de0  stloc.1
0x3de1  ldloc.0
0x3de2  ldc.i4.1
0x3de3  stfld    bool <>c__DisplayClass86_0::updateProperties
0x3de8  ldarg.s  5
0x3dea  brfalse.s loc_3E02
0x3dec  ldloc.0
0x3ded  ldarg.s  5
0x3def  ldloc.1
0x3df0  call     T0x2B00002C
0x3df5  call     T0x2B00002D
0x3dfa  ldc.i4.0
0x3dfb  cgt
0x3dfd  stfld    bool <>c__DisplayClass86_0::updateProperties
0x3e02  ldloc.0
0x3e03  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExcelWorkbook <>c__DisplayClass86_0::item
0x3e08  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_ContentType()
0x3e0d  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x3e12  brfalse.s loc_3E24
0x3e14  ldloc.0
0x3e15  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExcelWorkbook <>c__DisplayClass86_0::item
0x3e1a  ldstr    aApplicationOct// "application/octet-stream"
0x3e1f  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_ContentType(string)
0x3e24  ldloc.0
0x3e25  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass86_0::rsService
0x3e2a  ldloc.0
0x3e2b  ldftn    instance void <>c__DisplayClass86_0::<UpdateExcel>b__0()
0x3e31  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x3e36  call     void Microsoft.ReportingServices.Portal.Services.Extensions.RsServiceExtensions::ExecuteStorageAction(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Action action)
0x3e3b  ret
```
