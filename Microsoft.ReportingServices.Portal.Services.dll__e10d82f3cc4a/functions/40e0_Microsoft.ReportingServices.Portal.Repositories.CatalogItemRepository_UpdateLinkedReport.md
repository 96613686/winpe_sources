# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateLinkedReport

- ea: `0x40e0`
- end: `0x4177`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateLinkedReport`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2a20`

## callees

- `0x40e0`
- `0x128c0`
- `0x1dd40`

## pseudocode

```c

```

## disassembly

```asm
0x40e0  newobj   instance void <>c__DisplayClass93_0::.ctor()
0x40e5  stloc.0
0x40e6  ldloc.0
0x40e7  ldarg.1
0x40e8  stfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass93_0::rsService
0x40ed  ldloc.0
0x40ee  ldarg.0
0x40ef  stfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass93_0::<>4__this
0x40f4  ldloc.0
0x40f5  ldarg.3
0x40f6  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport <>c__DisplayClass93_0::item
0x40fb  ldloc.0
0x40fc  ldarg.2
0x40fd  stfld    string <>c__DisplayClass93_0::origItemPath
0x4102  ldloc.0
0x4103  ldarg.s  4
0x4105  stfld    bool <>c__DisplayClass93_0::renameOrMove
0x410a  ldc.i4.3
0x410b  newarr   [mscorlib]System.String
0x4110  dup
0x4111  ldc.i4.0
0x4112  ldstr    aHidden// "Hidden"
0x4117  stelem.ref
0x4118  dup
0x4119  ldc.i4.1
0x411a  ldstr    aDescription// "Description"
0x411f  stelem.ref
0x4120  dup
0x4121  ldc.i4.2
0x4122  ldstr    aLink// "Link"
0x4127  stelem.ref
0x4128  stloc.1
0x4129  ldloc.0
0x412a  ldc.i4.1
0x412b  stfld    bool <>c__DisplayClass93_0::updateProperties
0x4130  ldarg.s  5
0x4132  brfalse.s loc_4147
0x4134  ldloc.0
0x4135  ldarg.s  5
0x4137  ldloc.1
0x4138  call     T0x2B00002C
0x413d  call     T0x2B000036
0x4142  stfld    bool <>c__DisplayClass93_0::updateProperties
0x4147  ldloc.0
0x4148  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass93_0::rsService
0x414d  ldloc.0
0x414e  ldftn    instance void <>c__DisplayClass93_0::<UpdateLinkedReport>b__0()
0x4154  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x4159  call     void Microsoft.ReportingServices.Portal.Services.Extensions.RsServiceExtensions::ExecuteStorageAction(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Action action)
0x415e  ldarg.0
0x415f  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x4164  ldc.i4.3
0x4165  ldloc.0
0x4166  ldftn    instance string <>c__DisplayClass93_0::<UpdateLinkedReport>b__1()
0x416c  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0x4171  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0x4176  ret
```
