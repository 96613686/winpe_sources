# Microsoft.SharePoint.Taxonomy.Hybrid.TermStoreFactory::GetRemoteTermStore_1

- ea: `0x5fda0`
- end: `0x60167`
- name: `Microsoft.SharePoint.Taxonomy.Hybrid.TermStoreFactory::GetRemoteTermStore_1`
- size: `967`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3a180`
- `0x3ae20`
- `0x5fd70`
- `0x5fd90`

## callees

- `0x242a0`
- `0x5fda0`

## string_xrefs

- `0x600fa`: `Getting remote term store failed. Attempt times: {0}. Error: {1}.`
- `0x60147`: `Got remote TermStore successfully. Attempt times: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x5fda0  ldarg.0
0x5fda1  ldstr    aClientcontext_0// "ClientContext"
0x5fda6  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x5fdab  ldnull
0x5fdac  stloc.0
0x5fdad  ldc.i4.1
0x5fdae  stloc.1
0x5fdaf  br       loc_60134
0x5fdb4  ldarg.0
0x5fdb5  call     class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TaxonomySession [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TaxonomySession::GetTaxonomySession(class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ClientRuntimeContext)
0x5fdba  stloc.2
0x5fdbb  ldloc.2
0x5fdbc  callvirt instance class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TaxonomySession::GetDefaultSiteCollectionTermStore()
0x5fdc1  stloc.0
0x5fdc2  ldarg.0
0x5fdc3  callvirt instance void [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ClientRuntimeContext::ExecuteQuery()
0x5fdc8  ldarg.0
0x5fdc9  ldloc.0
0x5fdca  ldc.i4.5
0x5fdcb  newarr   class [System.Core]System.Linq.Expressions.Expression`1<class [mscorlib]System.Func`2<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore, object>>
0x5fdd0  stloc.s  4
0x5fdd2  ldloc.s  4
0x5fdd4  ldc.i4.0
0x5fdd5  ldtoken  [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore
0x5fdda  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5fddf  ldstr    aTs_0// "ts"
0x5fde4  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x5fde9  stloc.s  5
0x5fdeb  ldloc.s  5
0x5fded  ldtoken  instance class [mscorlib]System.Collections.Generic.IEnumerable`1<int32> [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore::get_Languages()
0x5fdf2  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x5fdf7  castclass [mscorlib]System.Reflection.MethodInfo
0x5fdfc  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x5fe01  ldc.i4.1
0x5fe02  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x5fe07  stloc.s  6
0x5fe09  ldloc.s  6
0x5fe0b  ldc.i4.0
0x5fe0c  ldloc.s  5
0x5fe0e  stelem.ref
0x5fe0f  ldloc.s  6
0x5fe11  call     T0x2B000076
0x5fe16  stelem.ref
0x5fe17  ldloc.s  4
0x5fe19  ldc.i4.1
0x5fe1a  ldtoken  [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore
0x5fe1f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5fe24  ldstr    aTs_0// "ts"
0x5fe29  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x5fe2e  stloc.s  7
0x5fe30  ldloc.s  7
0x5fe32  ldtoken  instance int32 [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore::get_WorkingLanguage()
0x5fe37  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x5fe3c  castclass [mscorlib]System.Reflection.MethodInfo
0x5fe41  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x5fe46  ldtoken  [mscorlib]System.Object
0x5fe4b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5fe50  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::ConvertChecked(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x5fe55  ldc.i4.1
0x5fe56  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x5fe5b  stloc.s  8
0x5fe5d  ldloc.s  8
0x5fe5f  ldc.i4.0
0x5fe60  ldloc.s  7
0x5fe62  stelem.ref
0x5fe63  ldloc.s  8
0x5fe65  call     T0x2B000076
0x5fe6a  stelem.ref
0x5fe6b  ldloc.s  4
0x5fe6d  ldc.i4.2
0x5fe6e  ldtoken  [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore
0x5fe73  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5fe78  ldstr    aTs_0// "ts"
0x5fe7d  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x5fe82  stloc.s  9
0x5fe84  ldloc.s  9
0x5fe86  ldtoken  instance string [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore::get_Name()
0x5fe8b  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x5fe90  castclass [mscorlib]System.Reflection.MethodInfo
0x5fe95  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x5fe9a  ldc.i4.1
0x5fe9b  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x5fea0  stloc.s  0xA
0x5fea2  ldloc.s  0xA
0x5fea4  ldc.i4.0
0x5fea5  ldloc.s  9
0x5fea7  stelem.ref
0x5fea8  ldloc.s  0xA
0x5feaa  call     T0x2B000076
0x5feaf  stelem.ref
0x5feb0  ldloc.s  4
0x5feb2  ldc.i4.3
0x5feb3  ldtoken  [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore
0x5feb8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5febd  ldstr    aTs_0// "ts"
0x5fec2  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x5fec7  stloc.s  0xB
0x5fec9  ldloc.s  0xB
0x5fecb  ldtoken  instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore::get_Id()
0x5fed0  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x5fed5  castclass [mscorlib]System.Reflection.MethodInfo
0x5feda  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x5fedf  ldtoken  [mscorlib]System.Object
0x5fee4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5fee9  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::ConvertChecked(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x5feee  ldc.i4.1
0x5feef  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x5fef4  stloc.s  0xC
0x5fef6  ldloc.s  0xC
0x5fef8  ldc.i4.0
0x5fef9  ldloc.s  0xB
0x5fefb  stelem.ref
0x5fefc  ldloc.s  0xC
0x5fefe  call     T0x2B000076
0x5ff03  stelem.ref
0x5ff04  ldloc.s  4
0x5ff06  ldc.i4.4
0x5ff07  ldtoken  [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore
0x5ff0c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5ff11  ldstr    aTs_0// "ts"
0x5ff16  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x5ff1b  stloc.s  0xD
0x5ff1d  ldnull
0x5ff1e  ldtoken  T0x2B000077
0x5ff23  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x5ff28  castclass [mscorlib]System.Reflection.MethodInfo
0x5ff2d  ldc.i4.2
0x5ff2e  newarr   [System.Core]System.Linq.Expressions.Expression
0x5ff33  stloc.s  0xE
0x5ff35  ldloc.s  0xE
0x5ff37  ldc.i4.0
0x5ff38  ldloc.s  0xD
0x5ff3a  ldtoken  instance class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermGroupCollection [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore::get_Groups()
0x5ff3f  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x5ff44  castclass [mscorlib]System.Reflection.MethodInfo
0x5ff49  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x5ff4e  stelem.ref
0x5ff4f  ldloc.s  0xE
0x5ff51  ldc.i4.1
0x5ff52  ldtoken  class [System.Core]System.Linq.Expressions.Expression`1<class [mscorlib]System.Func`2<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermGroup, object>>
0x5ff57  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5ff5c  ldc.i4.4
0x5ff5d  newarr   [System.Core]System.Linq.Expressions.Expression
0x5ff62  stloc.s  0xF
0x5ff64  ldloc.s  0xF
0x5ff66  ldc.i4.0
0x5ff67  ldtoken  [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermGroup
0x5ff6c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5ff71  ldstr    aG_0// "g"
0x5ff76  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x5ff7b  stloc.s  0x10
0x5ff7d  ldloc.s  0x10
0x5ff7f  ldtoken  instance string [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TaxonomyItem::get_Name()
0x5ff84  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x5ff89  castclass [mscorlib]System.Reflection.MethodInfo
0x5ff8e  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x5ff93  ldc.i4.1
0x5ff94  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x5ff99  stloc.s  0x11
0x5ff9b  ldloc.s  0x11
0x5ff9d  ldc.i4.0
0x5ff9e  ldloc.s  0x10
0x5ffa0  stelem.ref
0x5ffa1  ldloc.s  0x11
0x5ffa3  call     T0x2B000078
0x5ffa8  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::Quote(class [System.Core]System.Linq.Expressions.Expression)
0x5ffad  stelem.ref
0x5ffae  ldloc.s  0xF
0x5ffb0  ldc.i4.1
0x5ffb1  ldtoken  [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermGroup
0x5ffb6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5ffbb  ldstr    aG_0// "g"
0x5ffc0  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x5ffc5  stloc.s  0x12
0x5ffc7  ldloc.s  0x12
0x5ffc9  ldtoken  instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TaxonomyItem::get_Id()
0x5ffce  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x5ffd3  castclass [mscorlib]System.Reflection.MethodInfo
0x5ffd8  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x5ffdd  ldtoken  [mscorlib]System.Object
0x5ffe2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5ffe7  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::ConvertChecked(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x5ffec  ldc.i4.1
0x5ffed  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x5fff2  stloc.s  0x13
0x5fff4  ldloc.s  0x13
0x5fff6  ldc.i4.0
0x5fff7  ldloc.s  0x12
0x5fff9  stelem.ref
0x5fffa  ldloc.s  0x13
0x5fffc  call     T0x2B000078
0x60001  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::Quote(class [System.Core]System.Linq.Expressions.Expression)
0x60006  stelem.ref
0x60007  ldloc.s  0xF
0x60009  ldc.i4.2
0x6000a  ldtoken  [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermGroup
0x6000f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x60014  ldstr    aG_0// "g"
0x60019  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x6001e  stloc.s  0x14
0x60020  ldloc.s  0x14
0x60022  ldtoken  instance bool [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermGroup::get_IsSystemGroup()
0x60027  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x6002c  castclass [mscorlib]System.Reflection.MethodInfo
0x60031  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x60036  ldtoken  [mscorlib]System.Object
0x6003b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x60040  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::ConvertChecked(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x60045  ldc.i4.1
0x60046  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x6004b  stloc.s  0x15
0x6004d  ldloc.s  0x15
0x6004f  ldc.i4.0
0x60050  ldloc.s  0x14
0x60052  stelem.ref
0x60053  ldloc.s  0x15
0x60055  call     T0x2B000078
0x6005a  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::Quote(class [System.Core]System.Linq.Expressions.Expression)
0x6005f  stelem.ref
0x60060  ldloc.s  0xF
0x60062  ldc.i4.3
0x60063  ldtoken  [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermGroup
0x60068  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6006d  ldstr    aG_0// "g"
0x60072  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x60077  stloc.s  0x16
0x60079  ldloc.s  0x16
0x6007b  ldtoken  instance bool [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermGroup::get_IsSiteCollectionGroup()
0x60080  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x60085  castclass [mscorlib]System.Reflection.MethodInfo
0x6008a  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x6008f  ldtoken  [mscorlib]System.Object
0x60094  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x60099  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::ConvertChecked(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x6009e  ldc.i4.1
0x6009f  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x600a4  stloc.s  0x17
0x600a6  ldloc.s  0x17
0x600a8  ldc.i4.0
0x600a9  ldloc.s  0x16
0x600ab  stelem.ref
0x600ac  ldloc.s  0x17
0x600ae  call     T0x2B000078
0x600b3  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::Quote(class [System.Core]System.Linq.Expressions.Expression)
0x600b8  stelem.ref
0x600b9  ldloc.s  0xF
0x600bb  call     class [System.Core]System.Linq.Expressions.NewArrayExpression [System.Core]System.Linq.Expressions.Expression::NewArrayInit(class [mscorlib]System.Type, class [System.Core]System.Linq.Expressions.Expression[])
0x600c0  stelem.ref
0x600c1  ldloc.s  0xE
0x600c3  call     class [System.Core]System.Linq.Expressions.MethodCallExpression [System.Core]System.Linq.Expressions.Expression::Call(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo, class [System.Core]System.Linq.Expressions.Expression[])
0x600c8  ldc.i4.1
0x600c9  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x600ce  stloc.s  0x18
0x600d0  ldloc.s  0x18
0x600d2  ldc.i4.0
0x600d3  ldloc.s  0xD
0x600d5  stelem.ref
0x600d6  ldloc.s  0x18
0x600d8  call     T0x2B000076
0x600dd  stelem.ref
0x600de  ldloc.s  4
0x600e0  callvirt T0x2B000079
0x600e5  ldarg.0
0x600e6  callvirt instance void [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ClientRuntimeContext::ExecuteQuery()
0x600eb  leave.s  loc_6013B
0x600ed  stloc.3
0x600ee  ldc.i4   0x1317890
0x600f3  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x600f8  ldc.i4.s 0x14
0x600fa  ldstr    aGettingRemoteT// "Getting remote term store failed. Attem"...
0x600ff  ldc.i4.2
0x60100  newarr   [mscorlib]System.Object
0x60105  stloc.s  0x19
0x60107  ldloc.s  0x19
0x60109  ldc.i4.0
0x6010a  ldloc.1
0x6010b  box      [mscorlib]System.Int32
0x60110  stelem.ref
0x60111  ldloc.s  0x19
0x60113  ldc.i4.1
0x60114  ldloc.3
0x60115  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6011a  stelem.ref
0x6011b  ldloc.s  0x19
0x6011d  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x60122  ldloc.1
0x60123  dup
0x60124  ldc.i4.1
0x60125  add.ovf
0x60126  stloc.1
0x60127  ldc.i4.3
0x60128  blt.s    loc_60132
0x6012a  ldarg.0
0x6012b  callvirt instance void [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ClientRuntimeContext::Dispose()
0x60130  rethrow
0x60132  leave.s  loc_60134
0x60134  ldloc.1
0x60135  ldc.i4.3
0x60136  ble      loc_5FDB4
0x6013b  ldc.i4   0x120E44D
  ... truncated ...
```
