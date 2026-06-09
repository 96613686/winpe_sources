# Microsoft.ReportingServices.Portal.ODataWebApi.WebApi.ODataWebApiOwinConfig::GetEdmModelV1

- ea: `0xbd0`
- end: `0x11b6`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.WebApi.ODataWebApiOwinConfig::GetEdmModelV1`
- size: `1510`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x860`

## callees

- `0x6f00`
- `0x7250`
- `0x7440`
- `0x7610`
- `0x7790`
- `0x8d10`
- `0x91b0`
- `0x93c0`

## string_xrefs

- `0x1116`: `CatalogItemByPath`
- `0x115d`: `ServiceState`

## pseudocode

```c

```

## disassembly

```asm
0xbd0  newobj   instance void [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ODataConventionModelBuilder::.ctor()
0xbd5  stloc.0
0xbd6  ldloc.0
0xbd7  ldstr    aModel// "Model"
0xbdc  callvirt instance void [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ODataModelBuilder::set_Namespace(string)
0xbe1  ldloc.0
0xbe2  callvirt T0x2B000006
0xbe7  dup
0xbe8  ldc.i4.1
0xbe9  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EnumMemberConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EnumTypeConfiguration`1<valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItemType>::Member(var<u1>)
0xbee  pop
0xbef  ldc.i4.0
0xbf0  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EnumMemberConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EnumTypeConfiguration`1<valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItemType>::Member(var<u1>)
0xbf5  pop
0xbf6  ldloc.0
0xbf7  callvirt T0x2B000007
0xbfc  stloc.1
0xbfd  ldloc.1
0xbfe  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem
0xc03  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc08  ldstr    aC// "c"
0xc0d  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0xc12  stloc.s  7
0xc14  ldloc.s  7
0xc16  ldtoken  instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem::get_Type()
0xc1b  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0xc20  castclass [mscorlib]System.Reflection.MethodInfo
0xc25  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0xc2a  ldc.i4.1
0xc2b  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0xc30  dup
0xc31  ldc.i4.0
0xc32  ldloc.s  7
0xc34  stelem.ref
0xc35  call     T0x2B000008
0xc3a  callvirt T0x2B000009
0xc3f  pop
0xc40  ldloc.1
0xc41  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ComplexTypeConfiguration`1<var<u1>> class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ComplexTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem>::Abstract()
0xc46  pop
0xc47  ldloc.0
0xc48  callvirt T0x2B00000A
0xc4d  stloc.2
0xc4e  ldloc.2
0xc4f  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem
0xc54  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc59  ldstr    aC// "c"
0xc5e  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0xc63  stloc.s  7
0xc65  ldloc.s  7
0xc67  ldtoken  instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem::get_Type()
0xc6c  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0xc71  castclass [mscorlib]System.Reflection.MethodInfo
0xc76  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0xc7b  ldc.i4.1
0xc7c  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0xc81  dup
0xc82  ldc.i4.0
0xc83  ldloc.s  7
0xc85  stelem.ref
0xc86  call     T0x2B00000B
0xc8b  callvirt T0x2B00000C
0xc90  ldloc.2
0xc91  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem
0xc96  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc9b  ldstr    aC// "c"
0xca0  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0xca5  stloc.s  7
0xca7  ldloc.s  7
0xca9  ldtoken  instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem::get_Id()
0xcae  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0xcb3  castclass [mscorlib]System.Reflection.MethodInfo
0xcb8  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0xcbd  ldc.i4.1
0xcbe  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0xcc3  dup
0xcc4  ldc.i4.0
0xcc5  ldloc.s  7
0xcc7  stelem.ref
0xcc8  call     T0x2B00000D
0xccd  callvirt T0x2B00000E
0xcd2  pop
0xcd3  ldloc.2
0xcd4  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem
0xcd9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xcde  ldstr    aC// "c"
0xce3  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0xce8  stloc.s  7
0xcea  ldloc.s  7
0xcec  ldtoken  instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem::get_Path()
0xcf1  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0xcf6  castclass [mscorlib]System.Reflection.MethodInfo
0xcfb  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0xd00  ldc.i4.1
0xd01  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0xd06  dup
0xd07  ldc.i4.0
0xd08  ldloc.s  7
0xd0a  stelem.ref
0xd0b  call     T0x2B00000F
0xd10  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.LengthPropertyConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.StructuralTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem>::Property(class [System.Core]System.Linq.Expressions.Expression`1<class [mscorlib]System.Func`2<var<u1>, !!T0>>)
0xd15  pop
0xd16  ldloc.2
0xd17  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem
0xd1c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd21  ldstr    aC// "c"
0xd26  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0xd2b  stloc.s  7
0xd2d  ldloc.s  7
0xd2f  ldtoken  instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter> [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem::get_Parameters()
0xd34  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0xd39  castclass [mscorlib]System.Reflection.MethodInfo
0xd3e  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0xd43  ldc.i4.1
0xd44  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0xd49  dup
0xd4a  ldc.i4.0
0xd4b  ldloc.s  7
0xd4d  stelem.ref
0xd4e  call     T0x2B000010
0xd53  callvirt T0x2B000011
0xd58  pop
0xd59  ldloc.2
0xd5a  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem
0xd5f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd64  ldstr    aC// "c"
0xd69  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0xd6e  stloc.s  7
0xd70  ldloc.s  7
0xd72  ldtoken  instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItemAggregation [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem::get_Aggregation()
0xd77  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0xd7c  castclass [mscorlib]System.Reflection.MethodInfo
0xd81  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0xd86  ldc.i4.1
0xd87  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0xd8c  dup
0xd8d  ldc.i4.0
0xd8e  ldloc.s  7
0xd90  stelem.ref
0xd91  call     T0x2B000012
0xd96  callvirt T0x2B000013
0xd9b  pop
0xd9c  ldloc.2
0xd9d  callvirt T0x2B000014
0xda2  pop
0xda3  ldloc.0
0xda4  callvirt T0x2B000015
0xda9  stloc.3
0xdaa  ldloc.3
0xdab  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiStaticDataItem
0xdb0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xdb5  ldstr    aC// "c"
0xdba  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0xdbf  stloc.s  7
0xdc1  ldloc.s  7
0xdc3  ldtoken  instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem::get_Type()
0xdc8  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0xdcd  castclass [mscorlib]System.Reflection.MethodInfo
0xdd2  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0xdd7  ldc.i4.1
0xdd8  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0xddd  dup
0xdde  ldc.i4.0
0xddf  ldloc.s  7
0xde1  stelem.ref
0xde2  call     T0x2B000016
0xde7  callvirt T0x2B000017
0xdec  ldloc.3
0xded  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiStaticDataItem
0xdf2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xdf7  ldstr    aC// "c"
0xdfc  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0xe01  stloc.s  7
0xe03  ldloc.s  7
0xe05  ldtoken  instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiStaticDataItem::get_Value()
0xe0a  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0xe0f  castclass [mscorlib]System.Reflection.MethodInfo
0xe14  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0xe19  ldc.i4.1
0xe1a  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0xe1f  dup
0xe20  ldc.i4.0
0xe21  ldloc.s  7
0xe23  stelem.ref
0xe24  call     T0x2B000018
0xe29  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.LengthPropertyConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.StructuralTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiStaticDataItem>::Property(class [System.Core]System.Linq.Expressions.Expression`1<class [mscorlib]System.Func`2<var<u1>, !!T0>>)
0xe2e  pop
0xe2f  ldloc.3
0xe30  callvirt T0x2B000019
0xe35  pop
0xe36  ldloc.0
0xe37  callvirt T0x2B00001A
0xe3c  dup
0xe3d  ldc.i4.1
0xe3e  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EnumMemberConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EnumTypeConfiguration`1<valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DrillthroughTargetType>::Member(var<u1>)
0xe43  pop
0xe44  ldc.i4.0
0xe45  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EnumMemberConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EnumTypeConfiguration`1<valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DrillthroughTargetType>::Member(var<u1>)
0xe4a  pop
0xe4b  ldloc.0
0xe4c  callvirt T0x2B00001B
0xe51  stloc.s  4
0xe53  ldloc.s  4
0xe55  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.DrillthroughTarget
0xe5a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe5f  ldstr    aC// "c"
0xe64  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0xe69  stloc.s  7
0xe6b  ldloc.s  7
0xe6d  ldtoken  instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DrillthroughTargetType [Microsoft.ReportingServices.Portal.Interfaces]Model.DrillthroughTarget::get_Type()
0xe72  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0xe77  castclass [mscorlib]System.Reflection.MethodInfo
0xe7c  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0xe81  ldc.i4.1
0xe82  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0xe87  dup
0xe88  ldc.i4.0
0xe89  ldloc.s  7
0xe8b  stelem.ref
0xe8c  call     T0x2B00001C
0xe91  callvirt T0x2B00001D
0xe96  pop
0xe97  ldloc.s  4
0xe99  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ComplexTypeConfiguration`1<var<u1>> class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ComplexTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DrillthroughTarget>::Abstract()
0xe9e  pop
0xe9f  ldloc.0
0xea0  callvirt T0x2B00001E
0xea5  stloc.s  5
0xea7  ldloc.s  5
0xea9  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemDrillthroughTarget
0xeae  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xeb3  ldstr    aC// "c"
0xeb8  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0xebd  stloc.s  7
0xebf  ldloc.s  7
0xec1  ldtoken  instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DrillthroughTargetType [Microsoft.ReportingServices.Portal.Interfaces]Model.DrillthroughTarget::get_Type()
0xec6  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0xecb  castclass [mscorlib]System.Reflection.MethodInfo
0xed0  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0xed5  ldc.i4.1
0xed6  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0xedb  dup
0xedc  ldc.i4.0
0xedd  ldloc.s  7
0xedf  stelem.ref
0xee0  call     T0x2B00001F
0xee5  callvirt T0x2B000020
0xeea  ldloc.s  5
0xeec  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemDrillthroughTarget
0xef1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xef6  ldstr    aC// "c"
0xefb  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0xf00  stloc.s  7
0xf02  ldloc.s  7
0xf04  ldtoken  instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemDrillthroughTarget::get_CatalogItemType()
0xf09  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0xf0e  castclass [mscorlib]System.Reflection.MethodInfo
0xf13  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0xf18  ldc.i4.1
0xf19  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0xf1e  dup
0xf1f  ldc.i4.0
0xf20  ldloc.s  7
0xf22  stelem.ref
0xf23  call     T0x2B000021
0xf28  callvirt T0x2B000022
0xf2d  pop
0xf2e  ldloc.s  5
0xf30  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemDrillthroughTarget
0xf35  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf3a  ldstr    aC// "c"
0xf3f  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0xf44  stloc.s  7
0xf46  ldloc.s  7
0xf48  ldtoken  instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemDrillthroughTarget::get_Path()
0xf4d  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0xf52  castclass [mscorlib]System.Reflection.MethodInfo
0xf57  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0xf5c  ldc.i4.1
0xf5d  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0xf62  dup
0xf63  ldc.i4.0
0xf64  ldloc.s  7
0xf66  stelem.ref
0xf67  call     T0x2B000023
0xf6c  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.LengthPropertyConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.StructuralTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemDrillthroughTarget>::Property(class [System.Core]System.Linq.Expressions.Expression`1<class [mscorlib]System.Func`2<var<u1>, !!T0>>)
0xf71  pop
0xf72  ldloc.s  5
0xf74  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemDrillthroughTarget
0xf79  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf7e  ldstr    aC// "c"
0xf83  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0xf88  stloc.s  7
0xf8a  ldloc.s  7
0xf8c  ldtoken  instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemDrillthroughTarget::get_Id()
0xf91  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0xf96  castclass [mscorlib]System.Reflection.MethodInfo
0xf9b  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0xfa0  ldc.i4.1
0xfa1  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
  ... truncated ...
```
