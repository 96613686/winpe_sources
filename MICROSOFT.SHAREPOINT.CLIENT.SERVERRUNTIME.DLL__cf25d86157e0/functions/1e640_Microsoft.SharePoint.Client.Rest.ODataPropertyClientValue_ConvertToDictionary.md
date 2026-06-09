# Microsoft.SharePoint.Client.Rest.ODataPropertyClientValue::ConvertToDictionary

- ea: `0x1e640`
- end: `0x1e8c8`
- name: `Microsoft.SharePoint.Client.Rest.ODataPropertyClientValue::ConvertToDictionary`
- size: `648`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0xe010`
- `0xee00`
- `0xee30`
- `0xee50`
- `0x12440`
- `0x152f0`
- `0x16f10`
- `0x1cd40`
- `0x1dfb0`
- `0x1e640`

## string_xrefs

- `0x1e658`: `CannotDeserializeData`
- `0x1e6af`: `CannotDeserializeData`
- `0x1e74b`: `CannotDeserializeData`
- `0x1e7ae`: `CannotDeserializeData`
- `0x1e858`: `CannotDeserializeDictionaryEntry`

## pseudocode

```c

```

## disassembly

```asm
0x1e640  ldnull
0x1e641  stloc.s  0xD
0x1e643  ldnull
0x1e644  stloc.s  0xE
0x1e646  ldnull
0x1e647  stloc.s  0xF
0x1e649  ldarg.0
0x1e64a  ldfld    object Microsoft.SharePoint.Client.Rest.ODataPropertyClientValue::m_odataValue
0x1e64f  isinst   [Microsoft.Data.OData]Microsoft.Data.OData.ODataCollectionValue
0x1e654  stloc.0
0x1e655  ldloc.0
0x1e656  brtrue.s loc_1E685
0x1e658  ldstr    aCannotdeserial// "CannotDeserializeData"
0x1e65d  ldc.i4.1
0x1e65e  newarr   [mscorlib]System.Object
0x1e663  stloc.s  0x10
0x1e665  ldloc.s  0x10
0x1e667  ldc.i4.0
0x1e668  ldtoken  class [mscorlib]System.Collections.Generic.Dictionary`2<string, mvar<u1>>
0x1e66d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1e672  callvirt instance string [mscorlib]System.Type::get_FullName()
0x1e677  stelem.ref
0x1e678  ldloc.s  0x10
0x1e67a  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x1e67f  newobj   instance void Microsoft.SharePoint.Client.ClientServiceException::.ctor(string message)
0x1e684  throw
0x1e685  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, mvar<u1>>::.ctor()
0x1e68a  stloc.1
0x1e68b  ldloc.0
0x1e68c  callvirt instance class [mscorlib]System.Collections.IEnumerable [Microsoft.Data.OData]Microsoft.Data.OData.ODataCollectionValue::get_Items()
0x1e691  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x1e696  stloc.s  0x11
0x1e698  br       loc_1E8A3
0x1e69d  ldloc.s  0x11
0x1e69f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1e6a4  stloc.2
0x1e6a5  ldloc.2
0x1e6a6  isinst   [Microsoft.Data.OData]Microsoft.Data.OData.ODataComplexValue
0x1e6ab  stloc.3
0x1e6ac  ldloc.3
0x1e6ad  brtrue.s loc_1E6DC
0x1e6af  ldstr    aCannotdeserial// "CannotDeserializeData"
0x1e6b4  ldc.i4.1
0x1e6b5  newarr   [mscorlib]System.Object
0x1e6ba  stloc.s  0x12
0x1e6bc  ldloc.s  0x12
0x1e6be  ldc.i4.0
0x1e6bf  ldtoken  class [mscorlib]System.Collections.Generic.Dictionary`2<string, mvar<u1>>
0x1e6c4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1e6c9  callvirt instance string [mscorlib]System.Type::get_FullName()
0x1e6ce  stelem.ref
0x1e6cf  ldloc.s  0x12
0x1e6d1  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x1e6d6  newobj   instance void Microsoft.SharePoint.Client.ClientServiceException::.ctor(string message)
0x1e6db  throw
0x1e6dc  ldloc.3
0x1e6dd  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataProperty> [Microsoft.Data.OData]Microsoft.Data.OData.ODataComplexValue::get_Properties()
0x1e6e2  ldloc.s  0xD
0x1e6e4  brtrue.s loc_1E6F4
0x1e6e6  ldnull
0x1e6e7  ldftn    T0x2B00003B
0x1e6ed  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataProperty, bool>::.ctor(object, native int)
0x1e6f2  stloc.s  0xD
0x1e6f4  ldloc.s  0xD
0x1e6f6  call     T0x2B00003C
0x1e6fb  stloc.s  4
0x1e6fd  ldloc.3
0x1e6fe  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataProperty> [Microsoft.Data.OData]Microsoft.Data.OData.ODataComplexValue::get_Properties()
0x1e703  ldloc.s  0xE
0x1e705  brtrue.s loc_1E715
0x1e707  ldnull
0x1e708  ldftn    T0x2B00003D
0x1e70e  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataProperty, bool>::.ctor(object, native int)
0x1e713  stloc.s  0xE
0x1e715  ldloc.s  0xE
0x1e717  call     T0x2B00003C
0x1e71c  stloc.s  5
0x1e71e  ldloc.3
0x1e71f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataProperty> [Microsoft.Data.OData]Microsoft.Data.OData.ODataComplexValue::get_Properties()
0x1e724  ldloc.s  0xF
0x1e726  brtrue.s loc_1E736
0x1e728  ldnull
0x1e729  ldftn    T0x2B00003E
0x1e72f  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataProperty, bool>::.ctor(object, native int)
0x1e734  stloc.s  0xF
0x1e736  ldloc.s  0xF
0x1e738  call     T0x2B00003C
0x1e73d  stloc.s  6
0x1e73f  ldloc.s  4
0x1e741  brfalse.s loc_1E74B
0x1e743  ldloc.s  5
0x1e745  brfalse.s loc_1E74B
0x1e747  ldloc.s  6
0x1e749  brtrue.s loc_1E778
0x1e74b  ldstr    aCannotdeserial// "CannotDeserializeData"
0x1e750  ldc.i4.1
0x1e751  newarr   [mscorlib]System.Object
0x1e756  stloc.s  0x13
0x1e758  ldloc.s  0x13
0x1e75a  ldc.i4.0
0x1e75b  ldtoken  class [mscorlib]System.Collections.Generic.Dictionary`2<string, mvar<u1>>
0x1e760  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1e765  callvirt instance string [mscorlib]System.Type::get_FullName()
0x1e76a  stelem.ref
0x1e76b  ldloc.s  0x13
0x1e76d  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x1e772  newobj   instance void Microsoft.SharePoint.Client.ClientServiceException::.ctor(string message)
0x1e777  throw
0x1e778  ldloc.s  4
0x1e77a  callvirt instance object [Microsoft.Data.OData]Microsoft.Data.OData.ODataProperty::get_Value()
0x1e77f  isinst   [mscorlib]System.String
0x1e784  stloc.s  7
0x1e786  ldloc.s  5
0x1e788  callvirt instance object [Microsoft.Data.OData]Microsoft.Data.OData.ODataProperty::get_Value()
0x1e78d  isinst   [mscorlib]System.String
0x1e792  stloc.s  8
0x1e794  ldloc.s  6
0x1e796  callvirt instance object [Microsoft.Data.OData]Microsoft.Data.OData.ODataProperty::get_Value()
0x1e79b  isinst   [mscorlib]System.String
0x1e7a0  stloc.s  9
0x1e7a2  ldloc.s  7
0x1e7a4  brfalse.s loc_1E7AE
0x1e7a6  ldloc.s  8
0x1e7a8  brfalse.s loc_1E7AE
0x1e7aa  ldloc.s  9
0x1e7ac  brtrue.s loc_1E7DB
0x1e7ae  ldstr    aCannotdeserial// "CannotDeserializeData"
0x1e7b3  ldc.i4.1
0x1e7b4  newarr   [mscorlib]System.Object
0x1e7b9  stloc.s  0x14
0x1e7bb  ldloc.s  0x14
0x1e7bd  ldc.i4.0
0x1e7be  ldtoken  class [mscorlib]System.Collections.Generic.Dictionary`2<string, mvar<u1>>
0x1e7c3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1e7c8  callvirt instance string [mscorlib]System.Type::get_FullName()
0x1e7cd  stelem.ref
0x1e7ce  ldloc.s  0x14
0x1e7d0  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x1e7d5  newobj   instance void Microsoft.SharePoint.Client.ClientServiceException::.ctor(string message)
0x1e7da  throw
0x1e7db  ldloc.s  9
0x1e7dd  ldstr    aNull_0// "Null"
0x1e7e2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e7e7  brfalse.s loc_1E7F8
0x1e7e9  ldarg.0
0x1e7ea  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.ClientValue::get_ProxyContext()
0x1e7ef  newobj   instance void Microsoft.SharePoint.Client.DefaultClientValue::.ctor(class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1e7f4  stloc.s  0xA
0x1e7f6  br.s     loc_1E807
0x1e7f8  ldloc.s  8
0x1e7fa  ldarg.0
0x1e7fb  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.ClientValue::get_ProxyContext()
0x1e800  newobj   instance void Microsoft.SharePoint.Client.Rest.ODataPropertyClientValue::.ctor(object odataValue, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1e805  stloc.s  0xA
0x1e807  ldtoken  mvar<u1>
0x1e80c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1e811  ldtoken  [mscorlib]System.Object
0x1e816  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1e81b  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1e820  brfalse.s loc_1E890
0x1e822  ldloc.s  9
0x1e824  ldloca.s 0xB
0x1e826  call     bool Microsoft.SharePoint.Client.Rest.EdmTypeUtility::TryGetTypeFromEdmPrimitiveTypeName(string typeName, [out] class [mscorlib]System.Type& type)
0x1e82b  brtrue.s loc_1E878
0x1e82d  ldarg.0
0x1e82e  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.ClientValue::get_ProxyContext()
0x1e833  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x1e838  ldc.i4   0x58E481
0x1e83d  ldc.i4.2
0x1e83e  ldstr    aValuetype0InDi// "ValueType {0} in dictionary entry is no"...
0x1e843  ldc.i4.1
0x1e844  newarr   [mscorlib]System.Object
0x1e849  stloc.s  0x15
0x1e84b  ldloc.s  0x15
0x1e84d  ldc.i4.0
0x1e84e  ldloc.s  9
0x1e850  stelem.ref
0x1e851  ldloc.s  0x15
0x1e853  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x1e858  ldstr    aCannotdeserial_0// "CannotDeserializeDictionaryEntry"
0x1e85d  ldc.i4.1
0x1e85e  newarr   [mscorlib]System.Object
0x1e863  stloc.s  0x16
0x1e865  ldloc.s  0x16
0x1e867  ldc.i4.0
0x1e868  ldloc.s  9
0x1e86a  stelem.ref
0x1e86b  ldloc.s  0x16
0x1e86d  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x1e872  newobj   instance void Microsoft.SharePoint.Client.ClientServiceException::.ctor(string message)
0x1e877  throw
0x1e878  ldloc.1
0x1e879  ldloc.s  7
0x1e87b  ldloc.s  0xA
0x1e87d  ldloc.s  0xB
0x1e87f  callvirt instance object Microsoft.SharePoint.Client.ClientValue::ConvertTo(class [mscorlib]System.Type expectedType)
0x1e884  unbox.any mvar<u1>
0x1e889  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, mvar<u1>>::set_Item(var<u1>, !!T0)
0x1e88e  br.s     loc_1E8A3
0x1e890  ldloc.s  0xA
0x1e892  callvirt T0x2B000038
0x1e897  stloc.s  0xC
0x1e899  ldloc.1
0x1e89a  ldloc.s  7
0x1e89c  ldloc.s  0xC
0x1e89e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, mvar<u1>>::set_Item(var<u1>, !!T0)
0x1e8a3  ldloc.s  0x11
0x1e8a5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1e8aa  brtrue   loc_1E69D
0x1e8af  leave.s  loc_1E8C6
0x1e8b1  ldloc.s  0x11
0x1e8b3  isinst   [mscorlib]System.IDisposable
0x1e8b8  stloc.s  0x17
0x1e8ba  ldloc.s  0x17
0x1e8bc  brfalse.s loc_1E8C5
0x1e8be  ldloc.s  0x17
0x1e8c0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e8c5  endfinally
0x1e8c6  ldloc.1
0x1e8c7  ret
```
