# Microsoft.ReportingServices.Portal.Services.ODataExtensions.IncludedPropertiesContractResolver::CreateProperties

- ea: `0xf940`
- end: `0xfb27`
- name: `Microsoft.ReportingServices.Portal.Services.ODataExtensions.IncludedPropertiesContractResolver::CreateProperties`
- size: `487`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0xf940`
- `0x22130`
- `0x22160`

## pseudocode

```c

```

## disassembly

```asm
0xf940  newobj   instance void <>c__DisplayClass2_0::.ctor()
0xf945  stloc.0
0xf946  ldloc.0
0xf947  ldarg.1
0xf948  stfld    class [mscorlib]System.Type <>c__DisplayClass2_0::type
0xf94d  ldarg.0
0xf94e  ldloc.0
0xf94f  ldfld    class [mscorlib]System.Type <>c__DisplayClass2_0::type
0xf954  ldarg.2
0xf955  call     instance class [mscorlib]System.Collections.Generic.IList`1<class [Newtonsoft.Json]Newtonsoft.Json.Serialization.JsonProperty> [Newtonsoft.Json]Newtonsoft.Json.Serialization.DefaultContractResolver::CreateProperties(class [mscorlib]System.Type, valuetype [Newtonsoft.Json]Newtonsoft.Json.MemberSerialization)
0xf95a  call     T0x2B0000D3
0xf95f  stloc.1
0xf960  ldarg.0
0xf961  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> Microsoft.ReportingServices.Portal.Services.ODataExtensions.IncludedPropertiesContractResolver::includedPropertiesMap
0xf966  brfalse  loc_FB20
0xf96b  newobj   instance void <>c__DisplayClass2_1::.ctor()
0xf970  stloc.2
0xf971  ldloc.2
0xf972  ldnull
0xf973  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<string> <>c__DisplayClass2_1::includedProperties
0xf978  ldarg.0
0xf979  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> Microsoft.ReportingServices.Portal.Services.ODataExtensions.IncludedPropertiesContractResolver::includedPropertiesMap
0xf97e  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::get_Keys()
0xf983  ldloc.0
0xf984  ldftn    instance bool <>c__DisplayClass2_0::<CreateProperties>b__0(class [mscorlib]System.Type key)
0xf98a  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Type, bool>::.ctor(object, native int)
0xf98f  call     T0x2B0000D4
0xf994  stloc.3
0xf995  ldloc.3
0xf996  ldnull
0xf997  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xf99c  brfalse.s loc_F9B1
0xf99e  ldarg.0
0xf99f  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> Microsoft.ReportingServices.Portal.Services.ODataExtensions.IncludedPropertiesContractResolver::includedPropertiesMap
0xf9a4  ldloc.3
0xf9a5  ldloc.2
0xf9a6  ldflda   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> <>c__DisplayClass2_1::includedProperties
0xf9ab  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::TryGetValue(var<u1>, !!T0)
0xf9b0  pop
0xf9b1  ldloc.2
0xf9b2  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<string> <>c__DisplayClass2_1::includedProperties
0xf9b7  brtrue.s loc_F9D5
0xf9b9  ldarg.0
0xf9ba  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> Microsoft.ReportingServices.Portal.Services.ODataExtensions.IncludedPropertiesContractResolver::includedPropertiesMap
0xf9bf  ldtoken  [mscorlib]System.Object
0xf9c4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf9c9  ldloc.2
0xf9ca  ldflda   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> <>c__DisplayClass2_1::includedProperties
0xf9cf  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::TryGetValue(var<u1>, !!T0)
0xf9d4  pop
0xf9d5  ldloc.2
0xf9d6  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<string> <>c__DisplayClass2_1::includedProperties
0xf9db  brfalse  loc_FB20
0xf9e0  ldloc.1
0xf9e1  ldtoken  [Newtonsoft.Json]Newtonsoft.Json.Serialization.JsonProperty
0xf9e6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf9eb  ldstr    aX// "x"
0xf9f0  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0xf9f5  stloc.s  4
0xf9f7  ldnull
0xf9f8  ldtoken  T0x2B000068
0xf9fd  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0xfa02  castclass [mscorlib]System.Reflection.MethodInfo
0xfa07  ldc.i4.2
0xfa08  newarr   [System.Core]System.Linq.Expressions.Expression
0xfa0d  dup
0xfa0e  ldc.i4.0
0xfa0f  ldloc.2
0xfa10  ldtoken  <>c__DisplayClass2_1
0xfa15  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xfa1a  call     class [System.Core]System.Linq.Expressions.ConstantExpression [System.Core]System.Linq.Expressions.Expression::Constant(object, class [mscorlib]System.Type)
0xfa1f  ldtoken  class [mscorlib]System.Collections.Generic.IEnumerable`1<string> <>c__DisplayClass2_1::includedProperties
0xfa24  call     class [mscorlib]System.Reflection.FieldInfo [mscorlib]System.Reflection.FieldInfo::GetFieldFromHandle(valuetype [mscorlib]System.RuntimeFieldHandle)
0xfa29  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Field(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.FieldInfo)
0xfa2e  stelem.ref
0xfa2f  dup
0xfa30  ldc.i4.1
0xfa31  ldloc.s  4
0xfa33  ldtoken  instance string [Newtonsoft.Json]Newtonsoft.Json.Serialization.JsonProperty::get_PropertyName()
0xfa38  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0xfa3d  castclass [mscorlib]System.Reflection.MethodInfo
0xfa42  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0xfa47  stelem.ref
0xfa48  call     class [System.Core]System.Linq.Expressions.MethodCallExpression [System.Core]System.Linq.Expressions.Expression::Call(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo, class [System.Core]System.Linq.Expressions.Expression[])
0xfa4d  ldnull
0xfa4e  ldtoken  T0x2B000068
0xfa53  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0xfa58  castclass [mscorlib]System.Reflection.MethodInfo
0xfa5d  ldc.i4.2
0xfa5e  newarr   [System.Core]System.Linq.Expressions.Expression
0xfa63  dup
0xfa64  ldc.i4.0
0xfa65  ldloc.2
0xfa66  ldtoken  <>c__DisplayClass2_1
0xfa6b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xfa70  call     class [System.Core]System.Linq.Expressions.ConstantExpression [System.Core]System.Linq.Expressions.Expression::Constant(object, class [mscorlib]System.Type)
0xfa75  ldtoken  class [mscorlib]System.Collections.Generic.IEnumerable`1<string> <>c__DisplayClass2_1::includedProperties
0xfa7a  call     class [mscorlib]System.Reflection.FieldInfo [mscorlib]System.Reflection.FieldInfo::GetFieldFromHandle(valuetype [mscorlib]System.RuntimeFieldHandle)
0xfa7f  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Field(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.FieldInfo)
0xfa84  stelem.ref
0xfa85  dup
0xfa86  ldc.i4.1
0xfa87  ldnull
0xfa88  ldtoken  string [mscorlib]System.String::Format(string, object, object)
0xfa8d  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0xfa92  castclass [mscorlib]System.Reflection.MethodInfo
0xfa97  ldc.i4.3
0xfa98  newarr   [System.Core]System.Linq.Expressions.Expression
0xfa9d  dup
0xfa9e  ldc.i4.0
0xfa9f  ldstr    a01_0// "{0}.{1}"
0xfaa4  ldtoken  [mscorlib]System.String
0xfaa9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xfaae  call     class [System.Core]System.Linq.Expressions.ConstantExpression [System.Core]System.Linq.Expressions.Expression::Constant(object, class [mscorlib]System.Type)
0xfab3  stelem.ref
0xfab4  dup
0xfab5  ldc.i4.1
0xfab6  ldloc.s  4
0xfab8  ldtoken  instance class [mscorlib]System.Type [Newtonsoft.Json]Newtonsoft.Json.Serialization.JsonProperty::get_DeclaringType()
0xfabd  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0xfac2  castclass [mscorlib]System.Reflection.MethodInfo
0xfac7  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0xfacc  ldtoken  instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xfad1  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0xfad6  castclass [mscorlib]System.Reflection.MethodInfo
0xfadb  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0xfae0  stelem.ref
0xfae1  dup
0xfae2  ldc.i4.2
0xfae3  ldloc.s  4
0xfae5  ldtoken  instance string [Newtonsoft.Json]Newtonsoft.Json.Serialization.JsonProperty::get_PropertyName()
0xfaea  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0xfaef  castclass [mscorlib]System.Reflection.MethodInfo
0xfaf4  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0xfaf9  stelem.ref
0xfafa  call     class [System.Core]System.Linq.Expressions.MethodCallExpression [System.Core]System.Linq.Expressions.Expression::Call(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo, class [System.Core]System.Linq.Expressions.Expression[])
0xfaff  stelem.ref
0xfb00  call     class [System.Core]System.Linq.Expressions.MethodCallExpression [System.Core]System.Linq.Expressions.Expression::Call(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo, class [System.Core]System.Linq.Expressions.Expression[])
0xfb05  call     class [System.Core]System.Linq.Expressions.BinaryExpression [System.Core]System.Linq.Expressions.Expression::OrElse(class [System.Core]System.Linq.Expressions.Expression, class [System.Core]System.Linq.Expressions.Expression)
0xfb0a  ldc.i4.1
0xfb0b  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0xfb10  dup
0xfb11  ldc.i4.0
0xfb12  ldloc.s  4
0xfb14  stelem.ref
0xfb15  call     T0x2B0000D5
0xfb1a  call     T0x2B0000D6
0xfb1f  stloc.1
0xfb20  ldloc.1
0xfb21  call     T0x2B0000D7
0xfb26  ret
```
