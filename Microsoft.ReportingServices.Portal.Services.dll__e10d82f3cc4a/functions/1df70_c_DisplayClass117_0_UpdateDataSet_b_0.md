# <>c__DisplayClass117_0::<UpdateDataSet>b__0

- ea: `0x1df70`
- end: `0x1e08c`
- name: `<>c__DisplayClass117_0::<UpdateDataSet>b__0`
- size: `284`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x3ed0`
- `0x3f30`
- `0x4180`
- `0x1df70`

## pseudocode

```c

```

## disassembly

```asm
0x1df70  ldarg.0
0x1df71  ldfld    bool <>c__DisplayClass117_0::updateProperties
0x1df76  brfalse  loc_1E00F
0x1df7b  ldarg.0
0x1df7c  ldfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass117_0::<>4__this
0x1df81  ldarg.0
0x1df82  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet <>c__DisplayClass117_0::item
0x1df87  ldloca.s 0
0x1df89  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ResolveCommonCatalogItemProperties(class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem item, [out] class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property[]& soapProperties)
0x1df8e  ldnull
0x1df8f  stloc.1
0x1df90  ldarg.0
0x1df91  ldfld    string[] <>c__DisplayClass117_0::delta
0x1df96  brfalse.s loc_1DFF1
0x1df98  ldarg.0
0x1df99  ldfld    string[] <>c__DisplayClass117_0::delta
0x1df9e  stloc.2
0x1df9f  ldc.i4.0
0x1dfa0  stloc.3
0x1dfa1  br.s     loc_1DFEB
0x1dfa3  ldloc.2
0x1dfa4  ldloc.3
0x1dfa5  ldelem.ref
0x1dfa6  ldstr    aQueryexecution// "QueryExecutionTimeOut"
0x1dfab  ldc.i4.5
0x1dfac  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x1dfb1  brfalse.s loc_1DFE7
0x1dfb3  ldc.i4.1
0x1dfb4  newarr   [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property
0x1dfb9  dup
0x1dfba  ldc.i4.0
0x1dfbb  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x1dfc0  dup
0x1dfc1  ldstr    aQueryexecution// "QueryExecutionTimeOut"
0x1dfc6  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x1dfcb  dup
0x1dfcc  ldarg.0
0x1dfcd  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet <>c__DisplayClass117_0::item
0x1dfd2  callvirt instance int32 [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet::get_QueryExecutionTimeOut()
0x1dfd7  stloc.s  4
0x1dfd9  ldloca.s 4
0x1dfdb  call     instance string [mscorlib]System.Int32::ToString()
0x1dfe0  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x1dfe5  stelem.ref
0x1dfe6  stloc.1
0x1dfe7  ldloc.3
0x1dfe8  ldc.i4.1
0x1dfe9  add
0x1dfea  stloc.3
0x1dfeb  ldloc.3
0x1dfec  ldloc.2
0x1dfed  ldlen
0x1dfee  conv.i4
0x1dfef  blt.s    loc_1DFA3
0x1dff1  ldarg.0
0x1dff2  ldfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass117_0::<>4__this
0x1dff7  ldarg.0
0x1dff8  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass117_0::rsService
0x1dffd  ldarg.0
0x1dffe  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet <>c__DisplayClass117_0::item
0x1e003  ldarg.0
0x1e004  ldfld    string <>c__DisplayClass117_0::origItemPath
0x1e009  ldloc.1
0x1e00a  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateItemProperties(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem item, string itemPath, [opt] class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property[] additionalProperties)
0x1e00f  ldarg.0
0x1e010  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet <>c__DisplayClass117_0::item
0x1e015  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Content()
0x1e01a  brfalse.s loc_1E061
0x1e01c  ldarg.0
0x1e01d  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet <>c__DisplayClass117_0::item
0x1e022  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Content()
0x1e027  ldlen
0x1e028  brfalse.s loc_1E061
0x1e02a  ldarg.0
0x1e02b  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass117_0::rsService
0x1e030  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetDataSetDefinitionAction [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_SetDataSetDefinitionAction()
0x1e035  dup
0x1e036  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetDataSetDefinitionActionParameters>::get_ActionParameters()
0x1e03b  ldarg.0
0x1e03c  ldfld    string <>c__DisplayClass117_0::origItemPath
0x1e041  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.UpdateItemActionParameters::set_ItemPath(string)
0x1e046  dup
0x1e047  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetDataSetDefinitionActionParameters>::get_ActionParameters()
0x1e04c  ldarg.0
0x1e04d  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet <>c__DisplayClass117_0::item
0x1e052  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Content()
0x1e057  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetDataSetDefinitionActionParameters::set_DataSetDefinition(unsigned int8[])
0x1e05c  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetDataSetDefinitionActionParameters>::PerformActionNow()
0x1e061  ldarg.0
0x1e062  ldfld    bool <>c__DisplayClass117_0::renameOrMove
0x1e067  brfalse.s loc_1E08B
0x1e069  ldarg.0
0x1e06a  ldfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass117_0::<>4__this
0x1e06f  ldarg.0
0x1e070  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass117_0::rsService
0x1e075  ldarg.0
0x1e076  ldfld    string <>c__DisplayClass117_0::origItemPath
0x1e07b  ldarg.0
0x1e07c  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet <>c__DisplayClass117_0::item
0x1e081  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x1e086  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::RenameOrMoveItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string sourcePath, string destPath)
0x1e08b  ret
```
