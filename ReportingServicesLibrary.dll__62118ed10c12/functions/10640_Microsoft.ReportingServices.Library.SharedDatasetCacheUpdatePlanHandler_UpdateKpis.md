# Microsoft.ReportingServices.Library.SharedDatasetCacheUpdatePlanHandler::UpdateKpis

- ea: `0x10640`
- end: `0x10937`
- name: `Microsoft.ReportingServices.Library.SharedDatasetCacheUpdatePlanHandler::UpdateKpis`
- size: `759`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x105e0`

## callees

- `0x10640`
- `0x10940`
- `0x10d50`
- `0x10ee0`
- `0x110a0`
- `0x11270`
- `0x112a0`
- `0x11500`
- `0x11520`
- `0x11540`
- `0x11560`
- `0x11580`
- `0x13ac0`
- `0x14c30`
- `0x22ed0`

## string_xrefs

- `0x107a4`: `Found cached value for KPI SharedDataSet Hash Key {0}`
- `0x108a5`: `KPI SharedDataSet Hash Key {0} not found in cache, adding value`

## pseudocode

```c

```

## disassembly

```asm
0x10640  ldarg.3
0x10641  ldarg.s  4
0x10643  newobj   instance void Microsoft.ReportingServices.Library.DataSetCache::.ctor(string dataSetId, string dataSetPath)
0x10648  stloc.0
0x10649  ldarg.2
0x1064a  call     T0x2B000006
0x1064f  ldsfld   class [mscorlib]System.Func`2<class Microsoft.ReportingServices.Library.ItemScheduleAction, class <>f__AnonymousType0`2<valuetype Microsoft.ReportingServices.Library.ItemType, string>> <>c::<>9__12_0
0x10654  dup
0x10655  brtrue.s loc_1066E
0x10657  pop
0x10658  ldsfld   class <>c <>c::<>9
0x1065d  ldftn    instance class <>f__AnonymousType0`2<valuetype Microsoft.ReportingServices.Library.ItemType, string> <>c::<UpdateKpis>b__12_0(class Microsoft.ReportingServices.Library.ItemScheduleAction x)
0x10663  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.ReportingServices.Library.ItemScheduleAction, class <>f__AnonymousType0`2<valuetype Microsoft.ReportingServices.Library.ItemType, string>>::.ctor(object, native int)
0x10668  dup
0x10669  stsfld   class [mscorlib]System.Func`2<class Microsoft.ReportingServices.Library.ItemScheduleAction, class <>f__AnonymousType0`2<valuetype Microsoft.ReportingServices.Library.ItemType, string>> <>c::<>9__12_0
0x1066e  call     T0x2B000007
0x10673  ldsfld   class [mscorlib]System.Func`2<class [System.Core]System.Linq.IGrouping`2<class <>f__AnonymousType0`2<valuetype Microsoft.ReportingServices.Library.ItemType, string>, class Microsoft.ReportingServices.Library.ItemScheduleAction>, bool> <>c::<>9__12_1
0x10678  dup
0x10679  brtrue.s loc_10692
0x1067b  pop
0x1067c  ldsfld   class <>c <>c::<>9
0x10681  ldftn    instance bool <>c::<UpdateKpis>b__12_1(class [System.Core]System.Linq.IGrouping`2<class <>f__AnonymousType0`2<valuetype Microsoft.ReportingServices.Library.ItemType, string>, class Microsoft.ReportingServices.Library.ItemScheduleAction> x)
0x10687  newobj   instance void class [mscorlib]System.Func`2<class [System.Core]System.Linq.IGrouping`2<class <>f__AnonymousType0`2<valuetype Microsoft.ReportingServices.Library.ItemType, string>, class Microsoft.ReportingServices.Library.ItemScheduleAction>, bool>::.ctor(object, native int)
0x1068c  dup
0x1068d  stsfld   class [mscorlib]System.Func`2<class [System.Core]System.Linq.IGrouping`2<class <>f__AnonymousType0`2<valuetype Microsoft.ReportingServices.Library.ItemType, string>, class Microsoft.ReportingServices.Library.ItemScheduleAction>, bool> <>c::<>9__12_1
0x10692  call     T0x2B000008
0x10697  ldsfld   class [mscorlib]System.Func`2<class [System.Core]System.Linq.IGrouping`2<class <>f__AnonymousType0`2<valuetype Microsoft.ReportingServices.Library.ItemType, string>, class Microsoft.ReportingServices.Library.ItemScheduleAction>, class Microsoft.ReportingServices.Library.ItemScheduleAction> <>c::<>9__12_2
0x1069c  dup
0x1069d  brtrue.s loc_106B6
0x1069f  pop
0x106a0  ldsfld   class <>c <>c::<>9
0x106a5  ldftn    instance class Microsoft.ReportingServices.Library.ItemScheduleAction <>c::<UpdateKpis>b__12_2(class [System.Core]System.Linq.IGrouping`2<class <>f__AnonymousType0`2<valuetype Microsoft.ReportingServices.Library.ItemType, string>, class Microsoft.ReportingServices.Library.ItemScheduleAction> x)
0x106ab  newobj   instance void class [mscorlib]System.Func`2<class [System.Core]System.Linq.IGrouping`2<class <>f__AnonymousType0`2<valuetype Microsoft.ReportingServices.Library.ItemType, string>, class Microsoft.ReportingServices.Library.ItemScheduleAction>, class Microsoft.ReportingServices.Library.ItemScheduleAction>::.ctor(object, native int)
0x106b0  dup
0x106b1  stsfld   class [mscorlib]System.Func`2<class [System.Core]System.Linq.IGrouping`2<class <>f__AnonymousType0`2<valuetype Microsoft.ReportingServices.Library.ItemType, string>, class Microsoft.ReportingServices.Library.ItemScheduleAction>, class Microsoft.ReportingServices.Library.ItemScheduleAction> <>c::<>9__12_2
0x106b6  call     T0x2B000009
0x106bb  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Library.ItemScheduleAction>::GetEnumerator()
0x106c0  stloc.1
0x106c1  br       loc_1091F
0x106c6  ldloc.1
0x106c7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.ReportingServices.Library.ItemScheduleAction>::get_Current()
0x106cc  stloc.2
0x106cd  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ScheduleTracer()
0x106d2  ldc.i4.3
0x106d3  ldstr    aUpdatingDatase// "Updating dataset-bound properties for K"...
0x106d8  ldc.i4.1
0x106d9  newarr   [mscorlib]System.Object
0x106de  dup
0x106df  ldc.i4.0
0x106e0  ldloc.2
0x106e1  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath Microsoft.ReportingServices.Library.ItemScheduleAction::ItemPath
0x106e6  stelem.ref
0x106e7  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x106ec  ldarg.0
0x106ed  ldarg.1
0x106ee  ldloc.2
0x106ef  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath Microsoft.ReportingServices.Library.ItemScheduleAction::ItemPath
0x106f4  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x106f9  call     instance class Microsoft.ReportingServices.Library.CatalogItem Microsoft.ReportingServices.Library.SharedDatasetCacheUpdatePlanHandler::GetCatalogItem(class Microsoft.ReportingServices.Library.RSService rsService, string path)
0x106fe  stloc.3
0x106ff  ldarg.0
0x10700  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Library.KpiPropertyMapItem> Microsoft.ReportingServices.Library.SharedDatasetCacheUpdatePlanHandler::propertyMap
0x10705  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Library.KpiPropertyMapItem>::GetEnumerator()
0x1070a  stloc.s  4
0x1070c  br       loc_10905
0x10711  ldloc.s  4
0x10713  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.ReportingServices.Library.KpiPropertyMapItem>::get_Current()
0x10718  stloc.s  5
0x1071a  ldarg.3
0x1071b  ldloc.3
0x1071c  callvirt instance class Microsoft.ReportingServices.Library.ItemProperties Microsoft.ReportingServices.Library.CatalogItem::get_Properties()
0x10721  ldloc.s  5
0x10723  callvirt instance string Microsoft.ReportingServices.Library.KpiPropertyMapItem::get_DataSetId()
0x10728  callvirt instance string Microsoft.ReportingServices.Library.PropertyCollection::get_Item(string name)
0x1072d  ldc.i4.5
0x1072e  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x10733  brfalse  loc_10905
0x10738  ldc.i4.0
0x10739  stloc.s  6
0x1073b  ldnull
0x1073c  stloc.s  7
0x1073e  ldloc.3
0x1073f  callvirt instance class Microsoft.ReportingServices.Library.ItemProperties Microsoft.ReportingServices.Library.CatalogItem::get_Properties()
0x10744  ldloc.s  5
0x10746  callvirt instance string Microsoft.ReportingServices.Library.KpiPropertyMapItem::get_DataSetColumn()
0x1074b  callvirt instance string Microsoft.ReportingServices.Library.PropertyCollection::get_Item(string name)
0x10750  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10755  brtrue   loc_108F5
0x1075a  ldarg.0
0x1075b  ldloc.3
0x1075c  ldloc.s  5
0x1075e  call     instance string Microsoft.ReportingServices.Library.SharedDatasetCacheUpdatePlanHandler::GenerateKpiSharedDataSetKey(class Microsoft.ReportingServices.Library.CatalogItem catalogItem, class Microsoft.ReportingServices.Library.KpiPropertyMapItem kpiProperty)
0x10763  stloc.s  8
0x10765  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ScheduleTracer()
0x1076a  ldc.i4.4
0x1076b  ldstr    aKpiShareddatas// "KPI SharedDataSet Hash Key {0}"
0x10770  ldc.i4.1
0x10771  newarr   [mscorlib]System.Object
0x10776  dup
0x10777  ldc.i4.0
0x10778  ldloc.s  8
0x1077a  stelem.ref
0x1077b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x10780  ldloc.0
0x10781  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string[]> Microsoft.ReportingServices.Library.DataSetCache::Cache
0x10786  ldloc.s  8
0x10788  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string[]>::ContainsKey(var<u1>)
0x1078d  brfalse.s loc_107BE
0x1078f  ldloc.0
0x10790  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string[]> Microsoft.ReportingServices.Library.DataSetCache::Cache
0x10795  ldloc.s  8
0x10797  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string[]>::get_Item(void)
0x1079c  stloc.s  7
0x1079e  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ScheduleTracer()
0x107a3  ldc.i4.4
0x107a4  ldstr    aFoundCachedVal// "Found cached value for KPI SharedDataSe"...
0x107a9  ldc.i4.1
0x107aa  newarr   [mscorlib]System.Object
0x107af  dup
0x107b0  ldc.i4.0
0x107b1  ldloc.s  8
0x107b3  stelem.ref
0x107b4  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x107b9  br       loc_108F8
0x107be  nop
0x107bf  ldloc.3
0x107c0  callvirt instance class Microsoft.ReportingServices.Library.ItemProperties Microsoft.ReportingServices.Library.CatalogItem::get_Properties()
0x107c5  ldloc.s  5
0x107c7  callvirt instance string Microsoft.ReportingServices.Library.KpiPropertyMapItem::get_DataSetAggregation()
0x107cc  callvirt instance string Microsoft.ReportingServices.Library.PropertyCollection::get_Item(string name)
0x107d1  call     int32 [mscorlib]System.Convert::ToInt32(string)
0x107d6  stloc.s  9
0x107d8  ldarg.0
0x107d9  ldarg.1
0x107da  ldarg.s  4
0x107dc  ldloc.3
0x107dd  callvirt instance class Microsoft.ReportingServices.Library.ItemProperties Microsoft.ReportingServices.Library.CatalogItem::get_Properties()
0x107e2  ldloc.s  5
0x107e4  callvirt instance string Microsoft.ReportingServices.Library.KpiPropertyMapItem::get_DataSetColumn()
0x107e9  callvirt instance string Microsoft.ReportingServices.Library.PropertyCollection::get_Item(string name)
0x107ee  ldloc.3
0x107ef  callvirt instance class Microsoft.ReportingServices.Library.ItemProperties Microsoft.ReportingServices.Library.CatalogItem::get_Properties()
0x107f4  ldloc.s  5
0x107f6  callvirt instance string Microsoft.ReportingServices.Library.KpiPropertyMapItem::get_DataSetParameters()
0x107fb  callvirt instance string Microsoft.ReportingServices.Library.PropertyCollection::get_Item(string name)
0x10800  ldloc.s  9
0x10802  call     instance unsigned int8[] Microsoft.ReportingServices.Library.SharedDatasetCacheUpdatePlanHandler::LoadXmlSharedDataSetBytes(class Microsoft.ReportingServices.Library.RSService rsService, string dataSetPath, string columnName, string parameters, valuetype Microsoft.ReportingServices.Library.KpiSharedDataItemAggregation aggregation)
0x10807  stloc.s  0xA
0x10809  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ScheduleTracer()
0x1080e  ldc.i4.4
0x1080f  ldstr    aParsingDataset// "Parsing DataSet for KPI {0}"
0x10814  ldc.i4.1
0x10815  newarr   [mscorlib]System.Object
0x1081a  dup
0x1081b  ldc.i4.0
0x1081c  ldloc.3
0x1081d  callvirt instance class Microsoft.ReportingServices.Library.ItemProperties Microsoft.ReportingServices.Library.CatalogItem::get_Properties()
0x10822  callvirt instance string Microsoft.ReportingServices.Library.ItemProperties::get_Path()
0x10827  stelem.ref
0x10828  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1082d  ldloc.s  5
0x1082f  callvirt instance string Microsoft.ReportingServices.Library.KpiPropertyMapItem::get_DataValue()
0x10834  ldstr    aTrendsetValue// "TrendSet.Value"
0x10839  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1083e  brfalse.s loc_10863
0x10840  ldloc.s  0xA
0x10842  ldloc.3
0x10843  callvirt instance class Microsoft.ReportingServices.Library.ItemProperties Microsoft.ReportingServices.Library.CatalogItem::get_Properties()
0x10848  ldloc.s  5
0x1084a  callvirt instance string Microsoft.ReportingServices.Library.KpiPropertyMapItem::get_DataSetColumn()
0x1084f  callvirt instance string Microsoft.ReportingServices.Library.PropertyCollection::get_Item(string name)
0x10854  ldc.i4.1
0x10855  ldc.i4   0x2710
0x1085a  call     string[] Microsoft.ReportingServices.Library.XmlRdlParser::GetValues(unsigned int8[] xmlDataSetbytes, string columnName, valuetype Microsoft.ReportingServices.Library.XmlRdlParserMode mode, [opt] int32 maxRows)
0x1085f  stloc.s  7
0x10861  br.s     loc_10887
0x10863  ldloc.s  0xA
0x10865  ldloc.3
0x10866  callvirt instance class Microsoft.ReportingServices.Library.ItemProperties Microsoft.ReportingServices.Library.CatalogItem::get_Properties()
0x1086b  ldloc.s  5
0x1086d  callvirt instance string Microsoft.ReportingServices.Library.KpiPropertyMapItem::get_DataSetColumn()
0x10872  callvirt instance string Microsoft.ReportingServices.Library.PropertyCollection::get_Item(string name)
0x10877  ldloc.s  9
0x10879  brfalse.s loc_1087E
0x1087b  ldc.i4.2
0x1087c  br.s     loc_1087F
0x1087e  ldc.i4.0
0x1087f  ldc.i4.0
0x10880  call     string[] Microsoft.ReportingServices.Library.XmlRdlParser::GetValues(unsigned int8[] xmlDataSetbytes, string columnName, valuetype Microsoft.ReportingServices.Library.XmlRdlParserMode mode, [opt] int32 maxRows)
0x10885  stloc.s  7
0x10887  ldloc.s  7
0x10889  brfalse.s loc_108BC
0x1088b  ldloc.s  7
0x1088d  ldlen
0x1088e  brfalse.s loc_108BC
0x10890  ldloc.0
0x10891  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string[]> Microsoft.ReportingServices.Library.DataSetCache::Cache
0x10896  ldloc.s  8
0x10898  ldloc.s  7
0x1089a  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string[]>::Add(var<u1>, !!T0)
0x1089f  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ScheduleTracer()
0x108a4  ldc.i4.4
0x108a5  ldstr    aKpiShareddatas_0// "KPI SharedDataSet Hash Key {0} not foun"...
0x108aa  ldc.i4.1
0x108ab  newarr   [mscorlib]System.Object
0x108b0  dup
0x108b1  ldc.i4.0
0x108b2  ldloc.s  8
0x108b4  stelem.ref
0x108b5  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x108ba  br.s     loc_108BF
0x108bc  ldc.i4.4
0x108bd  stloc.s  6
0x108bf  leave.s  loc_108DA
0x108c1  stloc.s  0xB
0x108c3  ldc.i4.3
0x108c4  stloc.s  6
0x108c6  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ScheduleTracer()
0x108cb  ldc.i4.1
0x108cc  ldloc.s  0xB
0x108ce  callvirt instance string [mscorlib]System.Exception::get_Message()
0x108d3  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::TraceException(valuetype [System]System.Diagnostics.TraceLevel, string)
0x108d8  leave.s  loc_108DA
0x108da  leave.s  loc_108F8
0x108dc  stloc.s  0xC
0x108de  ldc.i4.2
0x108df  stloc.s  6
0x108e1  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ScheduleTracer()
0x108e6  ldc.i4.1
0x108e7  ldloc.s  0xC
0x108e9  callvirt instance string [mscorlib]System.Exception::get_Message()
0x108ee  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::TraceException(valuetype [System]System.Diagnostics.TraceLevel, string)
0x108f3  leave.s  loc_108F8
0x108f5  ldc.i4.5
0x108f6  stloc.s  6
0x108f8  ldarg.0
0x108f9  ldloc.3
0x108fa  ldloc.s  5
0x108fc  ldloc.s  7
0x108fe  ldloc.s  6
0x10900  call     instance void Microsoft.ReportingServices.Library.SharedDatasetCacheUpdatePlanHandler::UpdateKpi(class Microsoft.ReportingServices.Library.CatalogItem catalogItem, class Microsoft.ReportingServices.Library.KpiPropertyMapItem property, string[] newValues, [opt] valuetype Microsoft.ReportingServices.Library.KpiDataSetLastUpdateStatus status)
0x10905  ldloc.s  4
0x10907  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1090c  brtrue   loc_10711
0x10911  leave.s  loc_1091F
0x10913  ldloc.s  4
0x10915  brfalse.s loc_1091E
0x10917  ldloc.s  4
0x10919  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1091e  endfinally
0x1091f  ldloc.1
0x10920  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x10925  brtrue   loc_106C6
0x1092a  leave.s  loc_10936
0x1092c  ldloc.1
0x1092d  brfalse.s loc_10935
0x1092f  ldloc.1
0x10930  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10935  endfinally
0x10936  ret
```
