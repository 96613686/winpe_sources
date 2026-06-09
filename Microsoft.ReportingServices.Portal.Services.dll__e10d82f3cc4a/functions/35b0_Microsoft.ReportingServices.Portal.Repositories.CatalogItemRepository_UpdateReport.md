# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateReport

- ea: `0x35b0`
- end: `0x375f`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateReport`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2a20`

## callees

- `0x35b0`
- `0x4940`
- `0x9e80`
- `0x128c0`
- `0x1d760`

## pseudocode

```c

```

## disassembly

```asm
0x35b0  newobj   instance void <>c__DisplayClass76_0::.ctor()
0x35b5  stloc.0
0x35b6  ldloc.0
0x35b7  ldarg.0
0x35b8  stfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass76_0::<>4__this
0x35bd  ldloc.0
0x35be  ldarg.3
0x35bf  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report <>c__DisplayClass76_0::item
0x35c4  ldloc.0
0x35c5  ldarg.2
0x35c6  stfld    string <>c__DisplayClass76_0::origItemPath
0x35cb  ldloc.0
0x35cc  ldarg.s  4
0x35ce  stfld    bool <>c__DisplayClass76_0::renameOrMove
0x35d3  ldc.i4.2
0x35d4  newarr   [mscorlib]System.String
0x35d9  dup
0x35da  ldc.i4.0
0x35db  ldstr    aHidden// "Hidden"
0x35e0  stelem.ref
0x35e1  dup
0x35e2  ldc.i4.1
0x35e3  ldstr    aDescription// "Description"
0x35e8  stelem.ref
0x35e9  stloc.1
0x35ea  ldc.i4.5
0x35eb  newarr   [mscorlib]System.String
0x35f0  dup
0x35f1  ldc.i4.0
0x35f2  ldstr    aHasdatasources// "HasDataSources"
0x35f7  stelem.ref
0x35f8  dup
0x35f9  ldc.i4.1
0x35fa  ldstr    aHasparameters// "HasParameters"
0x35ff  stelem.ref
0x3600  dup
0x3601  ldc.i4.2
0x3602  ldstr    aSubscriptions// "Subscriptions"
0x3607  stelem.ref
0x3608  dup
0x3609  ldc.i4.3
0x360a  ldstr    aDatasources// "DataSources"
0x360f  stelem.ref
0x3610  dup
0x3611  ldc.i4.4
0x3612  ldstr    aReporthistorys// "ReportHistorySnapshots"
0x3617  stelem.ref
0x3618  stloc.2
0x3619  ldloc.0
0x361a  ldc.i4.1
0x361b  stfld    bool <>c__DisplayClass76_0::updateProperties
0x3620  ldc.i4.1
0x3621  stloc.3
0x3622  ldloc.0
0x3623  ldarg.1
0x3624  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x3629  stfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass76_0::rsService
0x362e  ldarg.s  5
0x3630  brfalse.s loc_3659
0x3632  ldloc.0
0x3633  ldarg.s  5
0x3635  ldloc.1
0x3636  call     T0x2B00002C
0x363b  call     T0x2B00002D
0x3640  ldc.i4.0
0x3641  cgt
0x3643  stfld    bool <>c__DisplayClass76_0::updateProperties
0x3648  ldarg.s  5
0x364a  ldloc.2
0x364b  call     T0x2B00002C
0x3650  call     T0x2B00002D
0x3655  ldc.i4.0
0x3656  cgt
0x3658  stloc.3
0x3659  ldloc.3
0x365a  brfalse.s loc_36D4
0x365c  ldloc.0
0x365d  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report <>c__DisplayClass76_0::item
0x3662  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Content()
0x3667  ldlen
0x3668  brfalse.s loc_36D4
0x366a  ldnull
0x366b  stloc.s  4
0x366d  ldloc.0
0x366e  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report <>c__DisplayClass76_0::item
0x3673  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Properties()
0x3678  stloc.s  5
0x367a  ldloc.s  5
0x367c  brfalse.s loc_36B5
0x367e  ldloc.s  5
0x3680  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>::get_Count()
0x3685  ldc.i4.0
0x3686  ble.s    loc_36B5
0x3688  ldloc.s  5
0x368a  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Property> <>c::<>9__76_2
0x368f  dup
0x3690  brtrue.s loc_36A9
0x3692  pop
0x3693  ldsfld   class <>c <>c::<>9
0x3698  ldftn    instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Property <>c::<UpdateReport>b__76_2(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property prop)
0x369e  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Property>::.ctor(object, native int)
0x36a3  dup
0x36a4  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Property> <>c::<>9__76_2
0x36a9  call     T0x2B00002A
0x36ae  call     T0x2B00002B
0x36b3  stloc.s  4
0x36b5  ldarg.0
0x36b6  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_soapRS2010Proxy
0x36bb  ldarg.1
0x36bc  ldloc.0
0x36bd  ldfld    string <>c__DisplayClass76_0::origItemPath
0x36c2  ldloc.0
0x36c3  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report <>c__DisplayClass76_0::item
0x36c8  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Content()
0x36cd  ldloc.s  4
0x36cf  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy::SetItemDefinition(class [mscorlib]System.Security.Principal.IPrincipal, string, unsigned int8[], class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Property[])
0x36d4  ldloc.0
0x36d5  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass76_0::rsService
0x36da  ldloc.0
0x36db  ldftn    instance void <>c__DisplayClass76_0::<UpdateReport>b__0()
0x36e1  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x36e6  call     void Microsoft.ReportingServices.Portal.Services.Extensions.RsServiceExtensions::ExecuteStorageAction(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Action action)
0x36eb  ldloc.0
0x36ec  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report <>c__DisplayClass76_0::item
0x36f1  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> [Microsoft.ReportingServices.Portal.Interfaces]Model.Report::get_DataSources()
0x36f6  brfalse.s loc_375E
0x36f8  ldloc.0
0x36f9  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report <>c__DisplayClass76_0::item
0x36fe  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> [Microsoft.ReportingServices.Portal.Interfaces]Model.Report::get_DataSources()
0x3703  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::get_Count()
0x3708  ldc.i4.0
0x3709  ble.s    loc_375E
0x370b  ldloc.0
0x370c  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report <>c__DisplayClass76_0::item
0x3711  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> [Microsoft.ReportingServices.Portal.Interfaces]Model.Report::get_DataSources()
0x3716  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource, bool> <>c::<>9__76_1
0x371b  dup
0x371c  brtrue.s loc_3735
0x371e  pop
0x371f  ldsfld   class <>c <>c::<>9
0x3724  ldftn    instance bool <>c::<UpdateReport>b__76_1(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource 'ds')
0x372a  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource, bool>::.ctor(object, native int)
0x372f  dup
0x3730  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource, bool> <>c::<>9__76_1
0x3735  call     T0x2B00002E
0x373a  call     T0x2B00002F
0x373f  brtrue.s loc_375E
0x3741  ldarg.0
0x3742  ldarg.1
0x3743  ldloc.0
0x3744  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report <>c__DisplayClass76_0::item
0x3749  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x374e  ldloc.0
0x374f  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report <>c__DisplayClass76_0::item
0x3754  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> [Microsoft.ReportingServices.Portal.Interfaces]Model.Report::get_DataSources()
0x3759  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::SetItemDataSources(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string itemPath, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> dataSources)
0x375e  ret
```
