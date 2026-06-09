# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateResource

- ea: `0x52c0`
- end: `0x538e`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateResource`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2a20`

## callees

- `0x52c0`
- `0x5570`
- `0x128c0`
- `0x1e0a0`

## pseudocode

```c

```

## disassembly

```asm
0x52c0  newobj   instance void <>c__DisplayClass119_0::.ctor()
0x52c5  stloc.0
0x52c6  ldloc.0
0x52c7  ldarg.0
0x52c8  stfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass119_0::<>4__this
0x52cd  ldloc.0
0x52ce  ldarg.1
0x52cf  stfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass119_0::rsService
0x52d4  ldloc.0
0x52d5  ldarg.3
0x52d6  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem <>c__DisplayClass119_0::item
0x52db  ldloc.0
0x52dc  ldarg.2
0x52dd  stfld    string <>c__DisplayClass119_0::origItemPath
0x52e2  ldloc.0
0x52e3  ldarg.s  4
0x52e5  stfld    bool <>c__DisplayClass119_0::renameOrMove
0x52ea  ldc.i4.2
0x52eb  newarr   [mscorlib]System.String
0x52f0  dup
0x52f1  ldc.i4.0
0x52f2  ldstr    aHidden// "Hidden"
0x52f7  stelem.ref
0x52f8  dup
0x52f9  ldc.i4.1
0x52fa  ldstr    aDescription// "Description"
0x52ff  stelem.ref
0x5300  stloc.1
0x5301  ldloc.0
0x5302  ldc.i4.1
0x5303  stfld    bool <>c__DisplayClass119_0::updateProperties
0x5308  ldloc.0
0x5309  ldloc.0
0x530a  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem <>c__DisplayClass119_0::item
0x530f  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_ContentType()
0x5314  stfld    string <>c__DisplayClass119_0::mimeType
0x5319  ldloc.0
0x531a  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem <>c__DisplayClass119_0::item
0x531f  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Properties()
0x5324  call     T0x2B000020
0x5329  stloc.2
0x532a  ldarg.s  5
0x532c  brfalse.s loc_5344
0x532e  ldloc.0
0x532f  ldarg.s  5
0x5331  ldloc.1
0x5332  call     T0x2B00002C
0x5337  call     T0x2B00002D
0x533c  ldc.i4.0
0x533d  cgt
0x533f  stfld    bool <>c__DisplayClass119_0::updateProperties
0x5344  ldloc.0
0x5345  ldfld    string <>c__DisplayClass119_0::mimeType
0x534a  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x534f  brfalse.s loc_535E
0x5351  ldloc.0
0x5352  ldloca.s 2
0x5354  call     string Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::MimeTypeFromProperties(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property[]& properties)
0x5359  stfld    string <>c__DisplayClass119_0::mimeType
0x535e  ldloc.0
0x535f  ldfld    string <>c__DisplayClass119_0::mimeType
0x5364  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x5369  brfalse.s loc_5376
0x536b  ldloc.0
0x536c  ldstr    aApplicationOct// "application/octet-stream"
0x5371  stfld    string <>c__DisplayClass119_0::mimeType
0x5376  ldloc.0
0x5377  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass119_0::rsService
0x537c  ldloc.0
0x537d  ldftn    instance void <>c__DisplayClass119_0::<UpdateResource>b__0()
0x5383  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x5388  call     void Microsoft.ReportingServices.Portal.Services.Extensions.RsServiceExtensions::ExecuteStorageAction(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Action action)
0x538d  ret
```
