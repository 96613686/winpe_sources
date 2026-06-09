# System.Xml.Xsl.IlGen.XmlILStorageMethods::.ctor

- ea: `0x3cc60`
- end: `0x3d089`
- name: `System.Xml.Xsl.IlGen.XmlILStorageMethods::.ctor`
- size: `1065`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x3d2e0`

## callees

- `0x3cc60`
- `0x3ef10`
- `0x3ef20`

## string_xrefs

- `0x3ccb1`: `System.Xml.Xsl.Runtime.`
- `0x3ccf0`: `Create`
- `0x3ce3c`: `CreateOrReuse`
- `0x3ce61`: `CreateOrReuse`

## pseudocode

```c

```

## disassembly

```asm
0x3cc60  ldarg.0
0x3cc61  call     instance void [mscorlib]System.Object::.ctor()
0x3cc66  ldarg.1
0x3cc67  ldtoken  [mscorlib]System.Int32
0x3cc6c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3cc71  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3cc76  brtrue.s loc_3CCB1
0x3cc78  ldarg.1
0x3cc79  ldtoken  [mscorlib]System.Int64
0x3cc7e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3cc83  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3cc88  brtrue.s loc_3CCB1
0x3cc8a  ldarg.1
0x3cc8b  ldtoken  [mscorlib]System.Decimal
0x3cc90  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3cc95  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3cc9a  brtrue.s loc_3CCB1
0x3cc9c  ldarg.1
0x3cc9d  ldtoken  [mscorlib]System.Double
0x3cca2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3cca7  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3ccac  brfalse  loc_3CD76
0x3ccb1  ldstr    aSystemXmlXslRu// "System.Xml.Xsl.Runtime."
0x3ccb6  ldarg.1
0x3ccb7  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x3ccbc  ldstr    aAggregator// "Aggregator"
0x3ccc1  call     string [mscorlib]System.String::Concat(string, string, string)
0x3ccc6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string)
0x3cccb  stloc.0
0x3cccc  ldarg.0
0x3cccd  ldloc.0
0x3ccce  ldstr    aAverage// "Average"
0x3ccd3  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3ccd8  stfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::AggAvg
0x3ccdd  ldarg.0
0x3ccde  ldloc.0
0x3ccdf  ldstr    aGetAverageresu// "get_AverageResult"
0x3cce4  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3cce9  stfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::AggAvgResult
0x3ccee  ldarg.0
0x3ccef  ldloc.0
0x3ccf0  ldstr    aCreate// "Create"
0x3ccf5  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3ccfa  stfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::AggCreate
0x3ccff  ldarg.0
0x3cd00  ldloc.0
0x3cd01  ldstr    aGetIsempty// "get_IsEmpty"
0x3cd06  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3cd0b  stfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::AggIsEmpty
0x3cd10  ldarg.0
0x3cd11  ldloc.0
0x3cd12  ldstr    aMaximum// "Maximum"
0x3cd17  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3cd1c  stfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::AggMax
0x3cd21  ldarg.0
0x3cd22  ldloc.0
0x3cd23  ldstr    aGetMaximumresu// "get_MaximumResult"
0x3cd28  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3cd2d  stfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::AggMaxResult
0x3cd32  ldarg.0
0x3cd33  ldloc.0
0x3cd34  ldstr    aMinimum// "Minimum"
0x3cd39  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3cd3e  stfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::AggMin
0x3cd43  ldarg.0
0x3cd44  ldloc.0
0x3cd45  ldstr    aGetMinimumresu// "get_MinimumResult"
0x3cd4a  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3cd4f  stfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::AggMinResult
0x3cd54  ldarg.0
0x3cd55  ldloc.0
0x3cd56  ldstr    aSum_0// "Sum"
0x3cd5b  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3cd60  stfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::AggSum
0x3cd65  ldarg.0
0x3cd66  ldloc.0
0x3cd67  ldstr    aGetSumresult// "get_SumResult"
0x3cd6c  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3cd71  stfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::AggSumResult
0x3cd76  ldarg.1
0x3cd77  ldtoken  [System.Xml]System.Xml.XPath.XPathNavigator
0x3cd7c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3cd81  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3cd86  brfalse.s loc_3CDB0
0x3cd88  ldarg.0
0x3cd89  ldtoken  System.Xml.Xsl.Runtime.XmlQueryNodeSequence
0x3cd8e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3cd93  stfld    class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILStorageMethods::SeqType
0x3cd98  ldarg.0
0x3cd99  ldarg.0
0x3cd9a  ldfld    class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILStorageMethods::SeqType
0x3cd9f  ldstr    aAddclone// "AddClone"
0x3cda4  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3cda9  stfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::SeqAdd
0x3cdae  br.s     loc_3CE1F
0x3cdb0  ldarg.1
0x3cdb1  ldtoken  [System.Xml]System.Xml.XPath.XPathItem
0x3cdb6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3cdbb  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3cdc0  brfalse.s loc_3CDEA
0x3cdc2  ldarg.0
0x3cdc3  ldtoken  System.Xml.Xsl.Runtime.XmlQueryItemSequence
0x3cdc8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3cdcd  stfld    class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILStorageMethods::SeqType
0x3cdd2  ldarg.0
0x3cdd3  ldarg.0
0x3cdd4  ldfld    class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILStorageMethods::SeqType
0x3cdd9  ldstr    aAddclone// "AddClone"
0x3cdde  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3cde3  stfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::SeqAdd
0x3cde8  br.s     loc_3CE1F
0x3cdea  ldarg.0
0x3cdeb  ldtoken  System.Xml.Xsl.Runtime.XmlQuerySequence`1
0x3cdf0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3cdf5  ldc.i4.1
0x3cdf6  newarr   [mscorlib]System.Type
0x3cdfb  dup
0x3cdfc  ldc.i4.0
0x3cdfd  ldarg.1
0x3cdfe  stelem.ref
0x3cdff  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::MakeGenericType(class [mscorlib]System.Type[])
0x3ce04  stfld    class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILStorageMethods::SeqType
0x3ce09  ldarg.0
0x3ce0a  ldarg.0
0x3ce0b  ldfld    class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILStorageMethods::SeqType
0x3ce10  ldstr    aAdd// "Add"
0x3ce15  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3ce1a  stfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::SeqAdd
0x3ce1f  ldarg.0
0x3ce20  ldarg.0
0x3ce21  ldfld    class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILStorageMethods::SeqType
0x3ce26  ldstr    aEmpty_0// "Empty"
0x3ce2b  callvirt instance class [mscorlib]System.Reflection.FieldInfo [mscorlib]System.Type::GetField(string)
0x3ce30  stfld    class [mscorlib]System.Reflection.FieldInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::SeqEmpty
0x3ce35  ldarg.0
0x3ce36  ldarg.0
0x3ce37  ldfld    class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILStorageMethods::SeqType
0x3ce3c  ldstr    aCreateorreuse// "CreateOrReuse"
0x3ce41  ldc.i4.1
0x3ce42  newarr   [mscorlib]System.Type
0x3ce47  dup
0x3ce48  ldc.i4.0
0x3ce49  ldarg.0
0x3ce4a  ldfld    class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILStorageMethods::SeqType
0x3ce4f  stelem.ref
0x3ce50  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName, class [mscorlib]System.Type[] args)
0x3ce55  stfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::SeqReuse
0x3ce5a  ldarg.0
0x3ce5b  ldarg.0
0x3ce5c  ldfld    class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILStorageMethods::SeqType
0x3ce61  ldstr    aCreateorreuse// "CreateOrReuse"
0x3ce66  ldc.i4.2
0x3ce67  newarr   [mscorlib]System.Type
0x3ce6c  dup
0x3ce6d  ldc.i4.0
0x3ce6e  ldarg.0
0x3ce6f  ldfld    class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILStorageMethods::SeqType
0x3ce74  stelem.ref
0x3ce75  dup
0x3ce76  ldc.i4.1
0x3ce77  ldarg.1
0x3ce78  stelem.ref
0x3ce79  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName, class [mscorlib]System.Type[] args)
0x3ce7e  stfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::SeqReuseSgl
0x3ce83  ldarg.0
0x3ce84  ldarg.0
0x3ce85  ldfld    class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILStorageMethods::SeqType
0x3ce8a  ldstr    aSortbykeys// "SortByKeys"
0x3ce8f  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3ce94  stfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::SeqSortByKeys
0x3ce99  ldarg.0
0x3ce9a  ldtoken  [mscorlib]System.Collections.Generic.IList`1
0x3ce9f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3cea4  ldc.i4.1
0x3cea5  newarr   [mscorlib]System.Type
0x3ceaa  dup
0x3ceab  ldc.i4.0
0x3ceac  ldarg.1
0x3cead  stelem.ref
0x3ceae  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::MakeGenericType(class [mscorlib]System.Type[])
0x3ceb3  stfld    class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILStorageMethods::IListType
0x3ceb8  ldarg.0
0x3ceb9  ldarg.0
0x3ceba  ldfld    class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILStorageMethods::IListType
0x3cebf  ldstr    aGetItem// "get_Item"
0x3cec4  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3cec9  stfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::IListItem
0x3cece  ldarg.0
0x3cecf  ldtoken  [mscorlib]System.Collections.Generic.ICollection`1
0x3ced4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3ced9  ldc.i4.1
0x3ceda  newarr   [mscorlib]System.Type
0x3cedf  dup
0x3cee0  ldc.i4.0
0x3cee1  ldarg.1
0x3cee2  stelem.ref
0x3cee3  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::MakeGenericType(class [mscorlib]System.Type[])
0x3cee8  ldstr    aGetCount// "get_Count"
0x3ceed  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3cef2  stfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::IListCount
0x3cef7  ldarg.1
0x3cef8  ldtoken  [mscorlib]System.String
0x3cefd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3cf02  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3cf07  brfalse.s loc_3CF28
0x3cf09  ldarg.0
0x3cf0a  ldtoken  [System.Xml]System.Xml.XPath.XPathItem
0x3cf0f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3cf14  ldstr    aGetValue// "get_Value"
0x3cf19  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3cf1e  stfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::ValueAs
0x3cf23  br       loc_3D012
0x3cf28  ldarg.1
0x3cf29  ldtoken  [mscorlib]System.Int32
0x3cf2e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3cf33  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3cf38  brfalse.s loc_3CF59
0x3cf3a  ldarg.0
0x3cf3b  ldtoken  [System.Xml]System.Xml.XPath.XPathItem
0x3cf40  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3cf45  ldstr    aGetValueasint// "get_ValueAsInt"
0x3cf4a  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3cf4f  stfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::ValueAs
0x3cf54  br       loc_3D012
0x3cf59  ldarg.1
0x3cf5a  ldtoken  [mscorlib]System.Int64
0x3cf5f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3cf64  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3cf69  brfalse.s loc_3CF8A
0x3cf6b  ldarg.0
0x3cf6c  ldtoken  [System.Xml]System.Xml.XPath.XPathItem
0x3cf71  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3cf76  ldstr    aGetValueaslong// "get_ValueAsLong"
0x3cf7b  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3cf80  stfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::ValueAs
0x3cf85  br       loc_3D012
0x3cf8a  ldarg.1
0x3cf8b  ldtoken  [mscorlib]System.DateTime
0x3cf90  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3cf95  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3cf9a  brfalse.s loc_3CFB8
0x3cf9c  ldarg.0
0x3cf9d  ldtoken  [System.Xml]System.Xml.XPath.XPathItem
0x3cfa2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3cfa7  ldstr    aGetValueasdate// "get_ValueAsDateTime"
0x3cfac  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3cfb1  stfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::ValueAs
0x3cfb6  br.s     loc_3D012
0x3cfb8  ldarg.1
0x3cfb9  ldtoken  [mscorlib]System.Double
0x3cfbe  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3cfc3  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3cfc8  brfalse.s loc_3CFE6
0x3cfca  ldarg.0
0x3cfcb  ldtoken  [System.Xml]System.Xml.XPath.XPathItem
0x3cfd0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3cfd5  ldstr    aGetValueasdoub// "get_ValueAsDouble"
0x3cfda  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3cfdf  stfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::ValueAs
0x3cfe4  br.s     loc_3D012
0x3cfe6  ldarg.1
0x3cfe7  ldtoken  [mscorlib]System.Boolean
0x3cfec  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3cff1  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3cff6  brfalse.s loc_3D012
0x3cff8  ldarg.0
0x3cff9  ldtoken  [System.Xml]System.Xml.XPath.XPathItem
0x3cffe  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d003  ldstr    aGetValueasbool// "get_ValueAsBoolean"
0x3d008  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d00d  stfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::ValueAs
0x3d012  ldarg.1
0x3d013  ldtoken  unsigned int8[]
0x3d018  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d01d  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3d022  brfalse.s loc_3D03F
0x3d024  ldarg.0
0x3d025  ldtoken  System.Xml.Xsl.Runtime.XmlILStorageConverter
0x3d02a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d02f  ldstr    aBytestoatomicv// "BytesToAtomicValue"
0x3d034  call     class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::GetMethod(class [mscorlib]System.Type className, string methName)
0x3d039  stfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::ToAtomicValue
0x3d03e  ret
0x3d03f  ldarg.1
0x3d040  ldtoken  [System.Xml]System.Xml.XPath.XPathItem
0x3d045  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d04a  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3d04f  brfalse.s loc_3D088
0x3d051  ldarg.1
0x3d052  ldtoken  [System.Xml]System.Xml.XPath.XPathNavigator
0x3d057  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d05c  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3d061  brfalse.s loc_3D088
0x3d063  ldarg.0
0x3d064  ldtoken  System.Xml.Xsl.Runtime.XmlILStorageConverter
0x3d069  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d06e  ldarg.1
0x3d06f  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x3d074  ldstr    aToatomicvalue// "ToAtomicValue"
0x3d079  call     string [mscorlib]System.String::Concat(string, string)
  ... truncated ...
```
