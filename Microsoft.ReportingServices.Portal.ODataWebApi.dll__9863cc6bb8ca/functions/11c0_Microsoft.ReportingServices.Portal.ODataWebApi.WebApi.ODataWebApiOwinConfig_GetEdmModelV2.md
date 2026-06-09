# Microsoft.ReportingServices.Portal.ODataWebApi.WebApi.ODataWebApiOwinConfig::GetEdmModelV2

- ea: `0x11c0`
- end: `0x17a5`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.WebApi.ODataWebApiOwinConfig::GetEdmModelV2`
- size: `1509`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x9d0`

## callees

- `0x1a10`
- `0x1c00`
- `0x2ad0`
- `0x3100`
- `0x31a0`
- `0x3290`
- `0x36a0`
- `0x3860`
- `0x3f20`
- `0x42d0`
- `0x43f0`
- `0x4560`
- `0x4730`
- `0x49a0`
- `0x51e0`
- `0x5410`
- `0x5440`
- `0x5d50`
- `0x5e40`
- `0x5f50`
- `0x5fb0`
- `0x60c0`
- `0x62e0`

## pseudocode

```c

```

## disassembly

```asm
0x11c0  newobj   instance void [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ODataConventionModelBuilder::.ctor()
0x11c5  stloc.0
0x11c6  ldloc.0
0x11c7  ldstr    aModel// "Model"
0x11cc  callvirt instance void [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ODataModelBuilder::set_Namespace(string)
0x11d1  ldloc.0
0x11d2  callvirt T0x2B000006
0x11d7  dup
0x11d8  ldc.i4.1
0x11d9  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EnumMemberConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EnumTypeConfiguration`1<valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItemType>::Member(var<u1>)
0x11de  pop
0x11df  ldc.i4.0
0x11e0  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EnumMemberConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EnumTypeConfiguration`1<valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItemType>::Member(var<u1>)
0x11e5  pop
0x11e6  ldloc.0
0x11e7  callvirt T0x2B000007
0x11ec  stloc.1
0x11ed  ldloc.1
0x11ee  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem
0x11f3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11f8  ldstr    aC// "c"
0x11fd  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x1202  stloc.s  9
0x1204  ldloc.s  9
0x1206  ldtoken  instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem::get_Type()
0x120b  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x1210  castclass [mscorlib]System.Reflection.MethodInfo
0x1215  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x121a  ldc.i4.1
0x121b  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x1220  dup
0x1221  ldc.i4.0
0x1222  ldloc.s  9
0x1224  stelem.ref
0x1225  call     T0x2B000008
0x122a  callvirt T0x2B000009
0x122f  pop
0x1230  ldloc.1
0x1231  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ComplexTypeConfiguration`1<var<u1>> class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ComplexTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem>::Abstract()
0x1236  pop
0x1237  ldloc.0
0x1238  callvirt T0x2B00000A
0x123d  stloc.2
0x123e  ldloc.2
0x123f  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem
0x1244  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1249  ldstr    aC// "c"
0x124e  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x1253  stloc.s  9
0x1255  ldloc.s  9
0x1257  ldtoken  instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem::get_Type()
0x125c  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x1261  castclass [mscorlib]System.Reflection.MethodInfo
0x1266  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x126b  ldc.i4.1
0x126c  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x1271  dup
0x1272  ldc.i4.0
0x1273  ldloc.s  9
0x1275  stelem.ref
0x1276  call     T0x2B00000B
0x127b  callvirt T0x2B00000C
0x1280  ldloc.2
0x1281  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem
0x1286  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x128b  ldstr    aC// "c"
0x1290  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x1295  stloc.s  9
0x1297  ldloc.s  9
0x1299  ldtoken  instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem::get_Id()
0x129e  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x12a3  castclass [mscorlib]System.Reflection.MethodInfo
0x12a8  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x12ad  ldc.i4.1
0x12ae  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x12b3  dup
0x12b4  ldc.i4.0
0x12b5  ldloc.s  9
0x12b7  stelem.ref
0x12b8  call     T0x2B00000D
0x12bd  callvirt T0x2B00000E
0x12c2  pop
0x12c3  ldloc.2
0x12c4  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem
0x12c9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12ce  ldstr    aC// "c"
0x12d3  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x12d8  stloc.s  9
0x12da  ldloc.s  9
0x12dc  ldtoken  instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem::get_Path()
0x12e1  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x12e6  castclass [mscorlib]System.Reflection.MethodInfo
0x12eb  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x12f0  ldc.i4.1
0x12f1  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x12f6  dup
0x12f7  ldc.i4.0
0x12f8  ldloc.s  9
0x12fa  stelem.ref
0x12fb  call     T0x2B00000F
0x1300  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.LengthPropertyConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.StructuralTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem>::Property(class [System.Core]System.Linq.Expressions.Expression`1<class [mscorlib]System.Func`2<var<u1>, !!T0>>)
0x1305  pop
0x1306  ldloc.2
0x1307  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem
0x130c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1311  ldstr    aC// "c"
0x1316  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x131b  stloc.s  9
0x131d  ldloc.s  9
0x131f  ldtoken  instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter> [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem::get_Parameters()
0x1324  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x1329  castclass [mscorlib]System.Reflection.MethodInfo
0x132e  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x1333  ldc.i4.1
0x1334  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x1339  dup
0x133a  ldc.i4.0
0x133b  ldloc.s  9
0x133d  stelem.ref
0x133e  call     T0x2B000010
0x1343  callvirt T0x2B000011
0x1348  pop
0x1349  ldloc.2
0x134a  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem
0x134f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1354  ldstr    aC// "c"
0x1359  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x135e  stloc.s  9
0x1360  ldloc.s  9
0x1362  ldtoken  instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItemAggregation [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem::get_Aggregation()
0x1367  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x136c  castclass [mscorlib]System.Reflection.MethodInfo
0x1371  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x1376  ldc.i4.1
0x1377  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x137c  dup
0x137d  ldc.i4.0
0x137e  ldloc.s  9
0x1380  stelem.ref
0x1381  call     T0x2B000012
0x1386  callvirt T0x2B000013
0x138b  pop
0x138c  ldloc.2
0x138d  callvirt T0x2B000014
0x1392  pop
0x1393  ldloc.0
0x1394  callvirt T0x2B000015
0x1399  stloc.3
0x139a  ldloc.3
0x139b  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiStaticDataItem
0x13a0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13a5  ldstr    aC// "c"
0x13aa  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x13af  stloc.s  9
0x13b1  ldloc.s  9
0x13b3  ldtoken  instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem::get_Type()
0x13b8  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x13bd  castclass [mscorlib]System.Reflection.MethodInfo
0x13c2  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x13c7  ldc.i4.1
0x13c8  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x13cd  dup
0x13ce  ldc.i4.0
0x13cf  ldloc.s  9
0x13d1  stelem.ref
0x13d2  call     T0x2B000016
0x13d7  callvirt T0x2B000017
0x13dc  ldloc.3
0x13dd  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiStaticDataItem
0x13e2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13e7  ldstr    aC// "c"
0x13ec  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x13f1  stloc.s  9
0x13f3  ldloc.s  9
0x13f5  ldtoken  instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiStaticDataItem::get_Value()
0x13fa  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x13ff  castclass [mscorlib]System.Reflection.MethodInfo
0x1404  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x1409  ldc.i4.1
0x140a  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x140f  dup
0x1410  ldc.i4.0
0x1411  ldloc.s  9
0x1413  stelem.ref
0x1414  call     T0x2B000018
0x1419  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.LengthPropertyConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.StructuralTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiStaticDataItem>::Property(class [System.Core]System.Linq.Expressions.Expression`1<class [mscorlib]System.Func`2<var<u1>, !!T0>>)
0x141e  pop
0x141f  ldloc.3
0x1420  callvirt T0x2B000019
0x1425  pop
0x1426  ldloc.0
0x1427  callvirt T0x2B00001A
0x142c  dup
0x142d  ldc.i4.1
0x142e  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EnumMemberConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EnumTypeConfiguration`1<valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DrillthroughTargetType>::Member(var<u1>)
0x1433  pop
0x1434  ldc.i4.0
0x1435  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EnumMemberConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EnumTypeConfiguration`1<valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DrillthroughTargetType>::Member(var<u1>)
0x143a  pop
0x143b  ldloc.0
0x143c  callvirt T0x2B00001B
0x1441  stloc.s  4
0x1443  ldloc.s  4
0x1445  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.DrillthroughTarget
0x144a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x144f  ldstr    aC// "c"
0x1454  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x1459  stloc.s  9
0x145b  ldloc.s  9
0x145d  ldtoken  instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DrillthroughTargetType [Microsoft.ReportingServices.Portal.Interfaces]Model.DrillthroughTarget::get_Type()
0x1462  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x1467  castclass [mscorlib]System.Reflection.MethodInfo
0x146c  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x1471  ldc.i4.1
0x1472  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x1477  dup
0x1478  ldc.i4.0
0x1479  ldloc.s  9
0x147b  stelem.ref
0x147c  call     T0x2B00001C
0x1481  callvirt T0x2B00001D
0x1486  pop
0x1487  ldloc.s  4
0x1489  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ComplexTypeConfiguration`1<var<u1>> class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ComplexTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DrillthroughTarget>::Abstract()
0x148e  pop
0x148f  ldloc.0
0x1490  callvirt T0x2B00001E
0x1495  stloc.s  5
0x1497  ldloc.s  5
0x1499  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemDrillthroughTarget
0x149e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14a3  ldstr    aC// "c"
0x14a8  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x14ad  stloc.s  9
0x14af  ldloc.s  9
0x14b1  ldtoken  instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DrillthroughTargetType [Microsoft.ReportingServices.Portal.Interfaces]Model.DrillthroughTarget::get_Type()
0x14b6  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x14bb  castclass [mscorlib]System.Reflection.MethodInfo
0x14c0  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x14c5  ldc.i4.1
0x14c6  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x14cb  dup
0x14cc  ldc.i4.0
0x14cd  ldloc.s  9
0x14cf  stelem.ref
0x14d0  call     T0x2B00001F
0x14d5  callvirt T0x2B000020
0x14da  ldloc.s  5
0x14dc  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemDrillthroughTarget
0x14e1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14e6  ldstr    aC// "c"
0x14eb  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x14f0  stloc.s  9
0x14f2  ldloc.s  9
0x14f4  ldtoken  instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemDrillthroughTarget::get_CatalogItemType()
0x14f9  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x14fe  castclass [mscorlib]System.Reflection.MethodInfo
0x1503  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x1508  ldc.i4.1
0x1509  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x150e  dup
0x150f  ldc.i4.0
0x1510  ldloc.s  9
0x1512  stelem.ref
0x1513  call     T0x2B000021
0x1518  callvirt T0x2B000022
0x151d  pop
0x151e  ldloc.s  5
0x1520  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemDrillthroughTarget
0x1525  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x152a  ldstr    aC// "c"
0x152f  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x1534  stloc.s  9
0x1536  ldloc.s  9
0x1538  ldtoken  instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemDrillthroughTarget::get_Path()
0x153d  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x1542  castclass [mscorlib]System.Reflection.MethodInfo
0x1547  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x154c  ldc.i4.1
0x154d  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x1552  dup
0x1553  ldc.i4.0
0x1554  ldloc.s  9
0x1556  stelem.ref
0x1557  call     T0x2B000023
0x155c  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.LengthPropertyConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.StructuralTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemDrillthroughTarget>::Property(class [System.Core]System.Linq.Expressions.Expression`1<class [mscorlib]System.Func`2<var<u1>, !!T0>>)
0x1561  pop
0x1562  ldloc.s  5
0x1564  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemDrillthroughTarget
0x1569  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x156e  ldstr    aC// "c"
0x1573  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x1578  stloc.s  9
0x157a  ldloc.s  9
0x157c  ldtoken  instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemDrillthroughTarget::get_Id()
0x1581  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x1586  castclass [mscorlib]System.Reflection.MethodInfo
0x158b  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x1590  ldc.i4.1
0x1591  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
  ... truncated ...
```
