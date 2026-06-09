# Microsoft.ReportingServices.Portal.Services.Extensions.IncludedPropertiesContractResolver::CreateProperties

- ea: `0x10a10`
- end: `0x10bf7`
- name: `Microsoft.ReportingServices.Portal.Services.Extensions.IncludedPropertiesContractResolver::CreateProperties`
- size: `487`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x10a10`
- `0x22180`
- `0x221b0`

## pseudocode

```c

```

## disassembly

```asm
0x10a10  newobj   instance void <>c__DisplayClass2_0::.ctor()
0x10a15  stloc.0
0x10a16  ldloc.0
0x10a17  ldarg.1
0x10a18  stfld    class [mscorlib]System.Type <>c__DisplayClass2_0::type
0x10a1d  ldarg.0
0x10a1e  ldloc.0
0x10a1f  ldfld    class [mscorlib]System.Type <>c__DisplayClass2_0::type
0x10a24  ldarg.2
0x10a25  call     instance class [mscorlib]System.Collections.Generic.IList`1<class [Newtonsoft.Json]Newtonsoft.Json.Serialization.JsonProperty> [Newtonsoft.Json]Newtonsoft.Json.Serialization.DefaultContractResolver::CreateProperties(class [mscorlib]System.Type, valuetype [Newtonsoft.Json]Newtonsoft.Json.MemberSerialization)
0x10a2a  call     T0x2B0000D3
0x10a2f  stloc.1
0x10a30  ldarg.0
0x10a31  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> Microsoft.ReportingServices.Portal.Services.Extensions.IncludedPropertiesContractResolver::includedPropertiesMap
0x10a36  brfalse  loc_10BF0
0x10a3b  newobj   instance void <>c__DisplayClass2_1::.ctor()
0x10a40  stloc.2
0x10a41  ldloc.2
0x10a42  ldnull
0x10a43  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<string> <>c__DisplayClass2_1::includedProperties
0x10a48  ldarg.0
0x10a49  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> Microsoft.ReportingServices.Portal.Services.Extensions.IncludedPropertiesContractResolver::includedPropertiesMap
0x10a4e  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::get_Keys()
0x10a53  ldloc.0
0x10a54  ldftn    instance bool <>c__DisplayClass2_0::<CreateProperties>b__0(class [mscorlib]System.Type key)
0x10a5a  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Type, bool>::.ctor(object, native int)
0x10a5f  call     T0x2B0000D4
0x10a64  stloc.3
0x10a65  ldloc.3
0x10a66  ldnull
0x10a67  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x10a6c  brfalse.s loc_10A81
0x10a6e  ldarg.0
0x10a6f  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> Microsoft.ReportingServices.Portal.Services.Extensions.IncludedPropertiesContractResolver::includedPropertiesMap
0x10a74  ldloc.3
0x10a75  ldloc.2
0x10a76  ldflda   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> <>c__DisplayClass2_1::includedProperties
0x10a7b  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::TryGetValue(var<u1>, !!T0)
0x10a80  pop
0x10a81  ldloc.2
0x10a82  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<string> <>c__DisplayClass2_1::includedProperties
0x10a87  brtrue.s loc_10AA5
0x10a89  ldarg.0
0x10a8a  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> Microsoft.ReportingServices.Portal.Services.Extensions.IncludedPropertiesContractResolver::includedPropertiesMap
0x10a8f  ldtoken  [mscorlib]System.Object
0x10a94  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10a99  ldloc.2
0x10a9a  ldflda   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> <>c__DisplayClass2_1::includedProperties
0x10a9f  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::TryGetValue(var<u1>, !!T0)
0x10aa4  pop
0x10aa5  ldloc.2
0x10aa6  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<string> <>c__DisplayClass2_1::includedProperties
0x10aab  brfalse  loc_10BF0
0x10ab0  ldloc.1
0x10ab1  ldtoken  [Newtonsoft.Json]Newtonsoft.Json.Serialization.JsonProperty
0x10ab6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10abb  ldstr    aX// "x"
0x10ac0  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x10ac5  stloc.s  4
0x10ac7  ldnull
0x10ac8  ldtoken  T0x2B000068
0x10acd  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x10ad2  castclass [mscorlib]System.Reflection.MethodInfo
0x10ad7  ldc.i4.2
0x10ad8  newarr   [System.Core]System.Linq.Expressions.Expression
0x10add  dup
0x10ade  ldc.i4.0
0x10adf  ldloc.2
0x10ae0  ldtoken  <>c__DisplayClass2_1
0x10ae5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10aea  call     class [System.Core]System.Linq.Expressions.ConstantExpression [System.Core]System.Linq.Expressions.Expression::Constant(object, class [mscorlib]System.Type)
0x10aef  ldtoken  class [mscorlib]System.Collections.Generic.IEnumerable`1<string> <>c__DisplayClass2_1::includedProperties
0x10af4  call     class [mscorlib]System.Reflection.FieldInfo [mscorlib]System.Reflection.FieldInfo::GetFieldFromHandle(valuetype [mscorlib]System.RuntimeFieldHandle)
0x10af9  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Field(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.FieldInfo)
0x10afe  stelem.ref
0x10aff  dup
0x10b00  ldc.i4.1
0x10b01  ldloc.s  4
0x10b03  ldtoken  instance string [Newtonsoft.Json]Newtonsoft.Json.Serialization.JsonProperty::get_PropertyName()
0x10b08  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x10b0d  castclass [mscorlib]System.Reflection.MethodInfo
0x10b12  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x10b17  stelem.ref
0x10b18  call     class [System.Core]System.Linq.Expressions.MethodCallExpression [System.Core]System.Linq.Expressions.Expression::Call(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo, class [System.Core]System.Linq.Expressions.Expression[])
0x10b1d  ldnull
0x10b1e  ldtoken  T0x2B000068
0x10b23  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x10b28  castclass [mscorlib]System.Reflection.MethodInfo
0x10b2d  ldc.i4.2
0x10b2e  newarr   [System.Core]System.Linq.Expressions.Expression
0x10b33  dup
0x10b34  ldc.i4.0
0x10b35  ldloc.2
0x10b36  ldtoken  <>c__DisplayClass2_1
0x10b3b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10b40  call     class [System.Core]System.Linq.Expressions.ConstantExpression [System.Core]System.Linq.Expressions.Expression::Constant(object, class [mscorlib]System.Type)
0x10b45  ldtoken  class [mscorlib]System.Collections.Generic.IEnumerable`1<string> <>c__DisplayClass2_1::includedProperties
0x10b4a  call     class [mscorlib]System.Reflection.FieldInfo [mscorlib]System.Reflection.FieldInfo::GetFieldFromHandle(valuetype [mscorlib]System.RuntimeFieldHandle)
0x10b4f  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Field(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.FieldInfo)
0x10b54  stelem.ref
0x10b55  dup
0x10b56  ldc.i4.1
0x10b57  ldnull
0x10b58  ldtoken  string [mscorlib]System.String::Format(string, object, object)
0x10b5d  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x10b62  castclass [mscorlib]System.Reflection.MethodInfo
0x10b67  ldc.i4.3
0x10b68  newarr   [System.Core]System.Linq.Expressions.Expression
0x10b6d  dup
0x10b6e  ldc.i4.0
0x10b6f  ldstr    a01_0// "{0}.{1}"
0x10b74  ldtoken  [mscorlib]System.String
0x10b79  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10b7e  call     class [System.Core]System.Linq.Expressions.ConstantExpression [System.Core]System.Linq.Expressions.Expression::Constant(object, class [mscorlib]System.Type)
0x10b83  stelem.ref
0x10b84  dup
0x10b85  ldc.i4.1
0x10b86  ldloc.s  4
0x10b88  ldtoken  instance class [mscorlib]System.Type [Newtonsoft.Json]Newtonsoft.Json.Serialization.JsonProperty::get_DeclaringType()
0x10b8d  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x10b92  castclass [mscorlib]System.Reflection.MethodInfo
0x10b97  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x10b9c  ldtoken  instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x10ba1  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x10ba6  castclass [mscorlib]System.Reflection.MethodInfo
0x10bab  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x10bb0  stelem.ref
0x10bb1  dup
0x10bb2  ldc.i4.2
0x10bb3  ldloc.s  4
0x10bb5  ldtoken  instance string [Newtonsoft.Json]Newtonsoft.Json.Serialization.JsonProperty::get_PropertyName()
0x10bba  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x10bbf  castclass [mscorlib]System.Reflection.MethodInfo
0x10bc4  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x10bc9  stelem.ref
0x10bca  call     class [System.Core]System.Linq.Expressions.MethodCallExpression [System.Core]System.Linq.Expressions.Expression::Call(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo, class [System.Core]System.Linq.Expressions.Expression[])
0x10bcf  stelem.ref
0x10bd0  call     class [System.Core]System.Linq.Expressions.MethodCallExpression [System.Core]System.Linq.Expressions.Expression::Call(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo, class [System.Core]System.Linq.Expressions.Expression[])
0x10bd5  call     class [System.Core]System.Linq.Expressions.BinaryExpression [System.Core]System.Linq.Expressions.Expression::OrElse(class [System.Core]System.Linq.Expressions.Expression, class [System.Core]System.Linq.Expressions.Expression)
0x10bda  ldc.i4.1
0x10bdb  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x10be0  dup
0x10be1  ldc.i4.0
0x10be2  ldloc.s  4
0x10be4  stelem.ref
0x10be5  call     T0x2B0000D5
0x10bea  call     T0x2B0000D6
0x10bef  stloc.1
0x10bf0  ldloc.1
0x10bf1  call     T0x2B0000D7
0x10bf6  ret
```
