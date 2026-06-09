# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateKpi

- ea: `0x3ff0`
- end: `0x40d4`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateKpi`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2a20`

## callees

- `0x3ff0`
- `0x5610`
- `0x128c0`
- `0x1dc60`

## pseudocode

```c

```

## disassembly

```asm
0x3ff0  newobj   instance void <>c__DisplayClass92_0::.ctor()
0x3ff5  stloc.0
0x3ff6  ldloc.0
0x3ff7  ldarg.1
0x3ff8  stfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass92_0::rsService
0x3ffd  ldloc.0
0x3ffe  ldarg.0
0x3fff  stfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass92_0::<>4__this
0x4004  ldloc.0
0x4005  ldarg.3
0x4006  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi <>c__DisplayClass92_0::item
0x400b  ldloc.0
0x400c  ldarg.s  4
0x400e  stfld    bool <>c__DisplayClass92_0::renameOrMove
0x4013  ldloc.0
0x4014  ldarg.2
0x4015  stfld    string <>c__DisplayClass92_0::origItemPath
0x401a  ldc.i4.8
0x401b  newarr   [mscorlib]System.String
0x4020  dup
0x4021  ldc.i4.0
0x4022  ldstr    aHidden// "Hidden"
0x4027  stelem.ref
0x4028  dup
0x4029  ldc.i4.1
0x402a  ldstr    aDescription// "Description"
0x402f  stelem.ref
0x4030  dup
0x4031  ldc.i4.2
0x4032  ldstr    aValues// "Values"
0x4037  stelem.ref
0x4038  dup
0x4039  ldc.i4.3
0x403a  ldstr    aData// "Data"
0x403f  stelem.ref
0x4040  dup
0x4041  ldc.i4.4
0x4042  ldstr    aValueformat// "ValueFormat"
0x4047  stelem.ref
0x4048  dup
0x4049  ldc.i4.5
0x404a  ldstr    aVisualization// "Visualization"
0x404f  stelem.ref
0x4050  dup
0x4051  ldc.i4.6
0x4052  ldstr    aCurrency// "Currency"
0x4057  stelem.ref
0x4058  dup
0x4059  ldc.i4.7
0x405a  ldstr    aDrillthroughta_2// "DrillthroughTarget"
0x405f  stelem.ref
0x4060  stloc.1
0x4061  ldloc.0
0x4062  ldloc.0
0x4063  ldfld    string <>c__DisplayClass92_0::origItemPath
0x4068  call     string Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetNameFromFullPath(string itemPath)
0x406d  stfld    string <>c__DisplayClass92_0::oldName
0x4072  ldloc.0
0x4073  ldloc.0
0x4074  ldfld    string <>c__DisplayClass92_0::origItemPath
0x4079  call     string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::GetParentPathFromFullPath(string)
0x407e  stfld    string <>c__DisplayClass92_0::parentPath
0x4083  ldloc.0
0x4084  ldc.i4.1
0x4085  stfld    bool <>c__DisplayClass92_0::updateProperties
0x408a  ldarg.s  5
0x408c  brfalse.s loc_40A4
0x408e  ldloc.0
0x408f  ldarg.s  5
0x4091  ldloc.1
0x4092  call     T0x2B00002C
0x4097  call     T0x2B00002D
0x409c  ldc.i4.0
0x409d  cgt
0x409f  stfld    bool <>c__DisplayClass92_0::updateProperties
0x40a4  ldloc.0
0x40a5  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass92_0::rsService
0x40aa  ldloc.0
0x40ab  ldftn    instance void <>c__DisplayClass92_0::<UpdateKpi>b__0()
0x40b1  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x40b6  call     void Microsoft.ReportingServices.Portal.Services.Extensions.RsServiceExtensions::ExecuteStorageAction(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Action action)
0x40bb  ldarg.0
0x40bc  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x40c1  ldc.i4.3
0x40c2  ldloc.0
0x40c3  ldftn    instance string <>c__DisplayClass92_0::<UpdateKpi>b__1()
0x40c9  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0x40ce  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0x40d3  ret
```
