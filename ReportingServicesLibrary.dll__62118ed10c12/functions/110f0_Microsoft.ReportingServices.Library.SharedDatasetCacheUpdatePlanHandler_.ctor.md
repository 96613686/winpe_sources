# Microsoft.ReportingServices.Library.SharedDatasetCacheUpdatePlanHandler::.ctor

- ea: `0x110f0`
- end: `0x11257`
- name: `Microsoft.ReportingServices.Library.SharedDatasetCacheUpdatePlanHandler::.ctor`
- size: `359`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x11510`
- `0x11530`
- `0x11550`
- `0x11570`
- `0x11590`
- `0x115b0`
- `0x115d0`
- `0x115e0`
- `0x47ac0`

## string_xrefs

- `0x11141`: `Value.LastUpdateStatus`
- `0x11196`: `Goal.LastUpdateStatus`
- `0x111eb`: `Status.LastUpdateStatus`
- `0x11240`: `TrendSet.LastUpdateStatus`

## pseudocode

```c

```

## disassembly

```asm
0x110f0  ldarg.0
0x110f1  ldc.i4.4
0x110f2  newarr   Microsoft.ReportingServices.Library.KpiPropertyMapItem
0x110f7  dup
0x110f8  ldc.i4.0
0x110f9  newobj   instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::.ctor()
0x110fe  dup
0x110ff  ldstr    aValueId// "Value.Id"
0x11104  callvirt instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::set_DataSetId(string value)
0x11109  dup
0x1110a  ldstr    aValueValue// "Value.Value"
0x1110f  callvirt instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::set_DataValue(string value)
0x11114  dup
0x11115  ldstr    aValueColumn// "Value.Column"
0x1111a  callvirt instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::set_DataSetColumn(string value)
0x1111f  dup
0x11120  ldstr    aValueAggregati// "Value.Aggregation"
0x11125  callvirt instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::set_DataSetAggregation(string value)
0x1112a  dup
0x1112b  ldstr    aValueParameter// "Value.Parameters"
0x11130  callvirt instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::set_DataSetParameters(string value)
0x11135  dup
0x11136  ldstr    aValue_1// "Value"
0x1113b  callvirt instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::set_DataItemType(string value)
0x11140  dup
0x11141  ldstr    aValueLastupdat// "Value.LastUpdateStatus"
0x11146  callvirt instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::set_DataLastUpdateStatus(string value)
0x1114b  stelem.ref
0x1114c  dup
0x1114d  ldc.i4.1
0x1114e  newobj   instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::.ctor()
0x11153  dup
0x11154  ldstr    aGoalId// "Goal.Id"
0x11159  callvirt instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::set_DataSetId(string value)
0x1115e  dup
0x1115f  ldstr    aGoalValue// "Goal.Value"
0x11164  callvirt instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::set_DataValue(string value)
0x11169  dup
0x1116a  ldstr    aGoalColumn// "Goal.Column"
0x1116f  callvirt instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::set_DataSetColumn(string value)
0x11174  dup
0x11175  ldstr    aGoalAggregatio// "Goal.Aggregation"
0x1117a  callvirt instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::set_DataSetAggregation(string value)
0x1117f  dup
0x11180  ldstr    aGoalParameters// "Goal.Parameters"
0x11185  callvirt instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::set_DataSetParameters(string value)
0x1118a  dup
0x1118b  ldstr    aGoal// "Goal"
0x11190  callvirt instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::set_DataItemType(string value)
0x11195  dup
0x11196  ldstr    aGoalLastupdate// "Goal.LastUpdateStatus"
0x1119b  callvirt instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::set_DataLastUpdateStatus(string value)
0x111a0  stelem.ref
0x111a1  dup
0x111a2  ldc.i4.2
0x111a3  newobj   instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::.ctor()
0x111a8  dup
0x111a9  ldstr    aStatusId// "Status.Id"
0x111ae  callvirt instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::set_DataSetId(string value)
0x111b3  dup
0x111b4  ldstr    aStatusValue// "Status.Value"
0x111b9  callvirt instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::set_DataValue(string value)
0x111be  dup
0x111bf  ldstr    aStatusColumn// "Status.Column"
0x111c4  callvirt instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::set_DataSetColumn(string value)
0x111c9  dup
0x111ca  ldstr    aStatusAggregat// "Status.Aggregation"
0x111cf  callvirt instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::set_DataSetAggregation(string value)
0x111d4  dup
0x111d5  ldstr    aStatusParamete// "Status.Parameters"
0x111da  callvirt instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::set_DataSetParameters(string value)
0x111df  dup
0x111e0  ldstr    aStatus// "Status"
0x111e5  callvirt instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::set_DataItemType(string value)
0x111ea  dup
0x111eb  ldstr    aStatusLastupda// "Status.LastUpdateStatus"
0x111f0  callvirt instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::set_DataLastUpdateStatus(string value)
0x111f5  stelem.ref
0x111f6  dup
0x111f7  ldc.i4.3
0x111f8  newobj   instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::.ctor()
0x111fd  dup
0x111fe  ldstr    aTrendsetId// "TrendSet.Id"
0x11203  callvirt instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::set_DataSetId(string value)
0x11208  dup
0x11209  ldstr    aTrendsetValue// "TrendSet.Value"
0x1120e  callvirt instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::set_DataValue(string value)
0x11213  dup
0x11214  ldstr    aTrendsetColumn// "TrendSet.Column"
0x11219  callvirt instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::set_DataSetColumn(string value)
0x1121e  dup
0x1121f  ldstr    aTrendsetAggreg// "TrendSet.Aggregation"
0x11224  callvirt instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::set_DataSetAggregation(string value)
0x11229  dup
0x1122a  ldstr    aTrendsetParame// "TrendSet.Parameters"
0x1122f  callvirt instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::set_DataSetParameters(string value)
0x11234  dup
0x11235  ldstr    aTrendset// "TrendSet"
0x1123a  callvirt instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::set_DataItemType(string value)
0x1123f  dup
0x11240  ldstr    aTrendsetLastup// "TrendSet.LastUpdateStatus"
0x11245  callvirt instance void Microsoft.ReportingServices.Library.KpiPropertyMapItem::set_DataLastUpdateStatus(string value)
0x1124a  stelem.ref
0x1124b  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Library.KpiPropertyMapItem> Microsoft.ReportingServices.Library.SharedDatasetCacheUpdatePlanHandler::propertyMap
0x11250  ldarg.0
0x11251  call     instance void Microsoft.ReportingServices.Library.ScheduleFireEventHandlerBase::.ctor()
0x11256  ret
```
