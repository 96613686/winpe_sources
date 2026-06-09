# Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::PopulateKpiFromProperties

- ea: `0x1200`
- end: `0x14d4`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::PopulateKpiFromProperties`
- size: `724`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14e0`

## callees

- `0xf10`
- `0x11b0`
- `0x1200`
- `0x1c920`

## pseudocode

```c

```

## disassembly

```asm
0x1200  newobj   instance void <>c__DisplayClass13_0::.ctor()
0x1205  stloc.0
0x1206  ldloc.0
0x1207  ldarg.1
0x1208  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi <>c__DisplayClass13_0::modelKpi
0x120d  ldloc.0
0x120e  ldarg.2
0x120f  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, string> <>c::<>9__13_0
0x1214  dup
0x1215  brtrue.s loc_122E
0x1217  pop
0x1218  ldsfld   class <>c <>c::<>9
0x121d  ldftn    instance string <>c::<PopulateKpiFromProperties>b__13_0(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property p)
0x1223  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, string>::.ctor(object, native int)
0x1228  dup
0x1229  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, string> <>c::<>9__13_0
0x122e  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, string> <>c::<>9__13_1
0x1233  dup
0x1234  brtrue.s loc_124D
0x1236  pop
0x1237  ldsfld   class <>c <>c::<>9
0x123c  ldftn    instance string <>c::<PopulateKpiFromProperties>b__13_1(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property v)
0x1242  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, string>::.ctor(object, native int)
0x1247  dup
0x1248  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, string> <>c::<>9__13_1
0x124d  call     T0x2B000007
0x1252  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c__DisplayClass13_0::propertyDictionary
0x1257  ldloc.0
0x1258  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c__DisplayClass13_0::propertyDictionary
0x125d  ldstr    aVisualization// "Visualization"
0x1262  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x1267  brfalse.s loc_1289
0x1269  ldloc.0
0x126a  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi <>c__DisplayClass13_0::modelKpi
0x126f  ldloc.0
0x1270  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c__DisplayClass13_0::propertyDictionary
0x1275  ldstr    aVisualization// "Visualization"
0x127a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x127f  call     int16 [mscorlib]System.Convert::ToInt16(string)
0x1284  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi::set_Visualization(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiVisualization)
0x1289  ldloc.0
0x128a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c__DisplayClass13_0::propertyDictionary
0x128f  ldstr    aValueformat// "ValueFormat"
0x1294  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x1299  brfalse.s loc_12BB
0x129b  ldloc.0
0x129c  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi <>c__DisplayClass13_0::modelKpi
0x12a1  ldloc.0
0x12a2  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c__DisplayClass13_0::propertyDictionary
0x12a7  ldstr    aValueformat// "ValueFormat"
0x12ac  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12b1  call     int16 [mscorlib]System.Convert::ToInt16(string)
0x12b6  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi::set_ValueFormat(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiValueFormat)
0x12bb  ldloc.0
0x12bc  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c__DisplayClass13_0::propertyDictionary
0x12c1  ldstr    aCurrency// "Currency"
0x12c6  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x12cb  brfalse.s loc_12E8
0x12cd  ldloc.0
0x12ce  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi <>c__DisplayClass13_0::modelKpi
0x12d3  ldloc.0
0x12d4  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c__DisplayClass13_0::propertyDictionary
0x12d9  ldstr    aCurrency// "Currency"
0x12de  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12e3  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi::set_Currency(string)
0x12e8  ldloc.0
0x12e9  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi <>c__DisplayClass13_0::modelKpi
0x12ee  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiData::.ctor()
0x12f3  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi::set_Data(class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiData)
0x12f8  ldloc.0
0x12f9  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi <>c__DisplayClass13_0::modelKpi
0x12fe  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiData [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi::get_Data()
0x1303  ldarg.0
0x1304  ldstr    aGoal// "Goal"
0x1309  ldloc.0
0x130a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c__DisplayClass13_0::propertyDictionary
0x130f  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::CreateKpiDataItem(string name, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties)
0x1314  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiData::set_Goal(class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem)
0x1319  ldloc.0
0x131a  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi <>c__DisplayClass13_0::modelKpi
0x131f  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiData [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi::get_Data()
0x1324  ldarg.0
0x1325  ldstr    aValue// "Value"
0x132a  ldloc.0
0x132b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c__DisplayClass13_0::propertyDictionary
0x1330  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::CreateKpiDataItem(string name, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties)
0x1335  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiData::set_Value(class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem)
0x133a  ldloc.0
0x133b  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi <>c__DisplayClass13_0::modelKpi
0x1340  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiData [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi::get_Data()
0x1345  ldarg.0
0x1346  ldstr    aStatus// "Status"
0x134b  ldloc.0
0x134c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c__DisplayClass13_0::propertyDictionary
0x1351  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::CreateKpiDataItem(string name, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties)
0x1356  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiData::set_Status(class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem)
0x135b  ldloc.0
0x135c  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi <>c__DisplayClass13_0::modelKpi
0x1361  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiData [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi::get_Data()
0x1366  ldarg.0
0x1367  ldstr    aTrendset// "TrendSet"
0x136c  ldloc.0
0x136d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c__DisplayClass13_0::propertyDictionary
0x1372  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::CreateKpiDataItem(string name, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties)
0x1377  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiData::set_TrendSet(class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem)
0x137c  ldloc.0
0x137d  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi <>c__DisplayClass13_0::modelKpi
0x1382  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiValues::.ctor()
0x1387  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi::set_Values(class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiValues)
0x138c  ldloc.0
0x138d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c__DisplayClass13_0::propertyDictionary
0x1392  ldstr    aValueValue// "Value.Value"
0x1397  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x139c  brfalse.s loc_13B6
0x139e  ldarg.0
0x139f  ldloc.0
0x13a0  ldftn    instance void <>c__DisplayClass13_0::<PopulateKpiFromProperties>b__2()
0x13a6  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x13ab  ldstr    aValue// "Value"
0x13b0  call     instance bool Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::SafePopulateKpiProperty(class [mscorlib]System.Action populateAction, string propertyName)
0x13b5  pop
0x13b6  ldloc.0
0x13b7  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c__DisplayClass13_0::propertyDictionary
0x13bc  ldstr    aGoalValue// "Goal.Value"
0x13c1  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x13c6  brfalse.s loc_13E0
0x13c8  ldarg.0
0x13c9  ldloc.0
0x13ca  ldftn    instance void <>c__DisplayClass13_0::<PopulateKpiFromProperties>b__3()
0x13d0  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x13d5  ldstr    aGoal// "Goal"
0x13da  call     instance bool Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::SafePopulateKpiProperty(class [mscorlib]System.Action populateAction, string propertyName)
0x13df  pop
0x13e0  ldloc.0
0x13e1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c__DisplayClass13_0::propertyDictionary
0x13e6  ldstr    aStatusValue// "Status.Value"
0x13eb  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x13f0  brfalse.s loc_140A
0x13f2  ldarg.0
0x13f3  ldloc.0
0x13f4  ldftn    instance void <>c__DisplayClass13_0::<PopulateKpiFromProperties>b__4()
0x13fa  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x13ff  ldstr    aStatus// "Status"
0x1404  call     instance bool Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::SafePopulateKpiProperty(class [mscorlib]System.Action populateAction, string propertyName)
0x1409  pop
0x140a  ldloc.0
0x140b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c__DisplayClass13_0::propertyDictionary
0x1410  ldstr    aTrendsetValue// "TrendSet.Value"
0x1415  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x141a  brfalse.s loc_1434
0x141c  ldarg.0
0x141d  ldloc.0
0x141e  ldftn    instance void <>c__DisplayClass13_0::<PopulateKpiFromProperties>b__5()
0x1424  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x1429  ldstr    aTrendset// "TrendSet"
0x142e  call     instance bool Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::SafePopulateKpiProperty(class [mscorlib]System.Action populateAction, string propertyName)
0x1433  pop
0x1434  ldloc.0
0x1435  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c__DisplayClass13_0::propertyDictionary
0x143a  ldstr    aDrillthroughta// "DrillthroughTarget.Type"
0x143f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x1444  brfalse  loc_14D3
0x1449  ldloc.0
0x144a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c__DisplayClass13_0::propertyDictionary
0x144f  ldstr    aDrillthroughta// "DrillthroughTarget.Type"
0x1454  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x1459  ldloca.s 1
0x145b  call     T0x2B000008
0x1460  brfalse.s loc_14D3
0x1462  ldloc.1
0x1463  brtrue.s loc_14D3
0x1465  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.UrlDrillthroughTarget::.ctor()
0x146a  dup
0x146b  ldc.i4.0
0x146c  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DrillthroughTarget::set_Type(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DrillthroughTargetType)
0x1471  stloc.2
0x1472  ldloc.0
0x1473  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c__DisplayClass13_0::propertyDictionary
0x1478  ldstr    aDrillthroughta_0// "DrillthroughTarget.Url"
0x147d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x1482  brfalse.s loc_149A
0x1484  ldloc.2
0x1485  ldloc.0
0x1486  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c__DisplayClass13_0::propertyDictionary
0x148b  ldstr    aDrillthroughta_0// "DrillthroughTarget.Url"
0x1490  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x1495  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.UrlDrillthroughTarget::set_Url(string)
0x149a  ldloc.0
0x149b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c__DisplayClass13_0::propertyDictionary
0x14a0  ldstr    aDrillthroughta_1// "DrillthroughTarget.DirectNavigation"
0x14a5  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x14aa  brfalse.s loc_14C7
0x14ac  ldloc.2
0x14ad  ldloc.0
0x14ae  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c__DisplayClass13_0::propertyDictionary
0x14b3  ldstr    aDrillthroughta_1// "DrillthroughTarget.DirectNavigation"
0x14b8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x14bd  call     bool [mscorlib]System.Convert::ToBoolean(string)
0x14c2  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.UrlDrillthroughTarget::set_DirectNavigation(bool)
0x14c7  ldloc.0
0x14c8  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi <>c__DisplayClass13_0::modelKpi
0x14cd  ldloc.2
0x14ce  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi::set_DrillthroughTarget(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DrillthroughTarget)
0x14d3  ret
```
