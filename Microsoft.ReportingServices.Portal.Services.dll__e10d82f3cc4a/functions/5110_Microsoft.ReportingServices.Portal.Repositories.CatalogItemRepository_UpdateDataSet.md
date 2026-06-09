# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateDataSet

- ea: `0x5110`
- end: `0x51e1`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateDataSet`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2a20`

## callees

- `0x4940`
- `0x5110`
- `0x9e80`
- `0x128c0`
- `0x1df60`

## pseudocode

```c

```

## disassembly

```asm
0x5110  newobj   instance void <>c__DisplayClass117_0::.ctor()
0x5115  stloc.0
0x5116  ldloc.0
0x5117  ldarg.0
0x5118  stfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass117_0::<>4__this
0x511d  ldloc.0
0x511e  ldarg.3
0x511f  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet <>c__DisplayClass117_0::item
0x5124  ldloc.0
0x5125  ldarg.s  5
0x5127  stfld    string[] <>c__DisplayClass117_0::delta
0x512c  ldloc.0
0x512d  ldarg.2
0x512e  stfld    string <>c__DisplayClass117_0::origItemPath
0x5133  ldloc.0
0x5134  ldarg.s  4
0x5136  stfld    bool <>c__DisplayClass117_0::renameOrMove
0x513b  ldc.i4.3
0x513c  newarr   [mscorlib]System.String
0x5141  dup
0x5142  ldc.i4.0
0x5143  ldstr    aHidden// "Hidden"
0x5148  stelem.ref
0x5149  dup
0x514a  ldc.i4.1
0x514b  ldstr    aDescription// "Description"
0x5150  stelem.ref
0x5151  dup
0x5152  ldc.i4.2
0x5153  ldstr    aQueryexecution// "QueryExecutionTimeOut"
0x5158  stelem.ref
0x5159  stloc.1
0x515a  ldloc.0
0x515b  ldc.i4.1
0x515c  stfld    bool <>c__DisplayClass117_0::updateProperties
0x5161  ldloc.0
0x5162  ldarg.1
0x5163  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x5168  stfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass117_0::rsService
0x516d  ldloc.0
0x516e  ldfld    string[] <>c__DisplayClass117_0::delta
0x5173  brfalse.s loc_518C
0x5175  ldloc.0
0x5176  ldloc.0
0x5177  ldfld    string[] <>c__DisplayClass117_0::delta
0x517c  ldloc.1
0x517d  call     T0x2B00002C
0x5182  call     T0x2B000036
0x5187  stfld    bool <>c__DisplayClass117_0::updateProperties
0x518c  ldloc.0
0x518d  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass117_0::rsService
0x5192  ldloc.0
0x5193  ldftn    instance void <>c__DisplayClass117_0::<UpdateDataSet>b__0()
0x5199  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x519e  call     void Microsoft.ReportingServices.Portal.Services.Extensions.RsServiceExtensions::ExecuteStorageAction(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Action action)
0x51a3  ldloc.0
0x51a4  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet <>c__DisplayClass117_0::item
0x51a9  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet::get_DataSources()
0x51ae  brfalse.s loc_51E0
0x51b0  ldloc.0
0x51b1  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet <>c__DisplayClass117_0::item
0x51b6  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet::get_DataSources()
0x51bb  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::get_Count()
0x51c0  ldc.i4.0
0x51c1  ble.s    loc_51E0
0x51c3  ldarg.0
0x51c4  ldarg.1
0x51c5  ldloc.0
0x51c6  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet <>c__DisplayClass117_0::item
0x51cb  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x51d0  ldloc.0
0x51d1  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet <>c__DisplayClass117_0::item
0x51d6  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet::get_DataSources()
0x51db  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::SetItemDataSources(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string itemPath, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> dataSources)
0x51e0  ret
```
