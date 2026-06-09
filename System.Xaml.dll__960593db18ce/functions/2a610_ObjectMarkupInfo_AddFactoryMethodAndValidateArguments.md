# ObjectMarkupInfo::AddFactoryMethodAndValidateArguments

- ea: `0x2a610`
- end: `0x2a811`
- name: `ObjectMarkupInfo::AddFactoryMethodAndValidateArguments`
- size: `513`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x2ac60`

## callees

- `0x2100`
- `0x8810`
- `0x8b00`
- `0x11f20`
- `0x11f50`
- `0x291e0`
- `0x29230`
- `0x29240`
- `0x29f70`
- `0x29fb0`
- `0x2a0f0`
- `0x2a610`
- `0x2b220`

## string_xrefs

- `0x2a6dc`: `ObjectReaderInstanceDescriptorIncompatibleArguments`
- `0x2a710`: `ObjectReaderInstanceDescriptorIncompatibleArguments`
- `0x2a6ed`: `ObjectReaderInstanceDescriptorInvalidMethod`
- `0x2a786`: `ObjectReaderInstanceDescriptorIncompatibleArgumentTypes`
- `0x2a7c3`: `ObjectReaderInstanceDescriptorIncompatibleArgumentTypes`

## pseudocode

```c

```

## disassembly

```asm
0x2a610  ldarg.s  5
0x2a612  ldnull
0x2a613  stind.ref
0x2a614  ldarg.2
0x2a615  ldnull
0x2a616  call     bool [mscorlib]System.Reflection.MemberInfo::op_Equality(class [mscorlib]System.Reflection.MemberInfo, class [mscorlib]System.Reflection.MemberInfo)
0x2a61b  brfalse.s loc_2A62B
0x2a61d  ldarg.s  5
0x2a61f  ldc.i4.0
0x2a620  newarr   [mscorlib]System.Reflection.ParameterInfo
0x2a625  stind.ref
0x2a626  br       loc_2A6FD
0x2a62b  ldarg.2
0x2a62c  isinst   [mscorlib]System.Reflection.ConstructorInfo
0x2a631  brfalse.s loc_2A648
0x2a633  ldarg.2
0x2a634  castclass [mscorlib]System.Reflection.ConstructorInfo
0x2a639  stloc.0
0x2a63a  ldarg.s  5
0x2a63c  ldloc.0
0x2a63d  callvirt instance class [mscorlib]System.Reflection.ParameterInfo[] [mscorlib]System.Reflection.MethodBase::GetParameters()
0x2a642  stind.ref
0x2a643  br       loc_2A6FD
0x2a648  ldarg.2
0x2a649  isinst   [mscorlib]System.Reflection.MethodInfo
0x2a64e  brfalse.s loc_2A6C8
0x2a650  ldarg.2
0x2a651  castclass [mscorlib]System.Reflection.MethodInfo
0x2a656  stloc.1
0x2a657  ldarg.s  5
0x2a659  ldloc.1
0x2a65a  callvirt instance class [mscorlib]System.Reflection.ParameterInfo[] [mscorlib]System.Reflection.MethodBase::GetParameters()
0x2a65f  stind.ref
0x2a660  ldarg.2
0x2a661  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x2a666  stloc.2
0x2a667  ldarg.2
0x2a668  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.MemberInfo::get_DeclaringType()
0x2a66d  stloc.3
0x2a66e  ldloc.3
0x2a66f  ldarg.1
0x2a670  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2a675  brfalse.s loc_2A681
0x2a677  ldloc.3
0x2a678  ldloc.2
0x2a679  ldarg.s  4
0x2a67b  call     string ObjectMarkupInfo::ConvertTypeAndMethodToString(class [mscorlib]System.Type type, string methodName, class SerializerContext context)
0x2a680  stloc.2
0x2a681  ldarg.0
0x2a682  call     instance class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> ObjectMarkupInfo::get_Properties()
0x2a687  newobj   instance void MemberMarkupInfo::.ctor()
0x2a68c  dup
0x2a68d  ldc.i4.4
0x2a68e  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_FactoryMethod()
0x2a693  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x2a698  callvirt instance void MarkupInfo::set_XamlNode(valuetype System.Xaml.XamlNode value)
0x2a69d  dup
0x2a69e  ldc.i4.1
0x2a69f  callvirt instance void MemberMarkupInfo::set_IsFactoryMethod(bool value)
0x2a6a4  dup
0x2a6a5  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> MemberMarkupInfo::get_Children()
0x2a6aa  newobj   instance void ValueMarkupInfo::.ctor()
0x2a6af  dup
0x2a6b0  ldc.i4.6
0x2a6b1  ldloc.2
0x2a6b2  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x2a6b7  callvirt instance void MarkupInfo::set_XamlNode(valuetype System.Xaml.XamlNode value)
0x2a6bc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::Add(var<u1>)
0x2a6c1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::Add(var<u1>)
0x2a6c6  br.s     loc_2A6FD
0x2a6c8  ldarg.1
0x2a6c9  callvirt instance bool [mscorlib]System.Type::get_IsValueType()
0x2a6ce  brfalse.s loc_2A6ED
0x2a6d0  ldarg.3
0x2a6d1  brfalse.s loc_2A6EC
0x2a6d3  ldarg.3
0x2a6d4  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x2a6d9  ldc.i4.0
0x2a6da  ble.s    loc_2A6EC
0x2a6dc  ldstr    aObjectreaderin// "ObjectReaderInstanceDescriptorIncompati"...
0x2a6e1  call     string System.Xaml.SR::Get(string id)
0x2a6e6  newobj   instance void System.Xaml.XamlObjectReaderException::.ctor(string message)
0x2a6eb  throw
0x2a6ec  ret
0x2a6ed  ldstr    aObjectreaderin_0// "ObjectReaderInstanceDescriptorInvalidMe"...
0x2a6f2  call     string System.Xaml.SR::Get(string id)
0x2a6f7  newobj   instance void System.Xaml.XamlObjectReaderException::.ctor(string message)
0x2a6fc  throw
0x2a6fd  ldarg.3
0x2a6fe  brfalse  loc_2A810
0x2a703  ldarg.3
0x2a704  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x2a709  ldarg.s  5
0x2a70b  ldind.ref
0x2a70c  ldlen
0x2a70d  conv.i4
0x2a70e  beq.s    loc_2A720
0x2a710  ldstr    aObjectreaderin// "ObjectReaderInstanceDescriptorIncompati"...
0x2a715  call     string System.Xaml.SR::Get(string id)
0x2a71a  newobj   instance void System.Xaml.XamlObjectReaderException::.ctor(string message)
0x2a71f  throw
0x2a720  ldc.i4.0
0x2a721  stloc.s  4
0x2a723  ldarg.3
0x2a724  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x2a729  stloc.s  5
0x2a72b  br       loc_2A7ED
0x2a730  ldloc.s  5
0x2a732  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2a737  stloc.s  6
0x2a739  ldarg.s  5
0x2a73b  ldind.ref
0x2a73c  ldloc.s  4
0x2a73e  dup
0x2a73f  ldc.i4.1
0x2a740  add
0x2a741  stloc.s  4
0x2a743  ldelem.ref
0x2a744  stloc.s  7
0x2a746  ldloc.s  6
0x2a748  brtrue.s loc_2A7AE
0x2a74a  ldloc.s  7
0x2a74c  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.ParameterInfo::get_ParameterType()
0x2a751  callvirt instance bool [mscorlib]System.Type::get_IsValueType()
0x2a756  brfalse  loc_2A7ED
0x2a75b  ldloc.s  7
0x2a75d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.ParameterInfo::get_ParameterType()
0x2a762  callvirt instance bool [mscorlib]System.Type::get_IsGenericType()
0x2a767  brfalse.s loc_2A786
0x2a769  ldloc.s  7
0x2a76b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.ParameterInfo::get_ParameterType()
0x2a770  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::GetGenericTypeDefinition()
0x2a775  ldtoken  [mscorlib]System.Nullable`1
0x2a77a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a77f  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2a784  brtrue.s loc_2A7ED
0x2a786  ldstr    aObjectreaderin_1// "ObjectReaderInstanceDescriptorIncompati"...
0x2a78b  ldc.i4.2
0x2a78c  newarr   [mscorlib]System.Object
0x2a791  dup
0x2a792  ldc.i4.0
0x2a793  ldstr    aNull_0// "null"
0x2a798  stelem.ref
0x2a799  dup
0x2a79a  ldc.i4.1
0x2a79b  ldloc.s  7
0x2a79d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.ParameterInfo::get_ParameterType()
0x2a7a2  stelem.ref
0x2a7a3  call     string System.Xaml.SR::Get(string id, object[] args)
0x2a7a8  newobj   instance void System.Xaml.XamlObjectReaderException::.ctor(string message)
0x2a7ad  throw
0x2a7ae  ldloc.s  7
0x2a7b0  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.ParameterInfo::get_ParameterType()
0x2a7b5  ldloc.s  6
0x2a7b7  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2a7bc  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x2a7c1  brtrue.s loc_2A7ED
0x2a7c3  ldstr    aObjectreaderin_1// "ObjectReaderInstanceDescriptorIncompati"...
0x2a7c8  ldc.i4.2
0x2a7c9  newarr   [mscorlib]System.Object
0x2a7ce  dup
0x2a7cf  ldc.i4.0
0x2a7d0  ldloc.s  6
0x2a7d2  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2a7d7  stelem.ref
0x2a7d8  dup
0x2a7d9  ldc.i4.1
0x2a7da  ldloc.s  7
0x2a7dc  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.ParameterInfo::get_ParameterType()
0x2a7e1  stelem.ref
0x2a7e2  call     string System.Xaml.SR::Get(string id, object[] args)
0x2a7e7  newobj   instance void System.Xaml.XamlObjectReaderException::.ctor(string message)
0x2a7ec  throw
0x2a7ed  ldloc.s  5
0x2a7ef  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2a7f4  brtrue   loc_2A730
0x2a7f9  leave.s  loc_2A810
0x2a7fb  ldloc.s  5
0x2a7fd  isinst   [mscorlib]System.IDisposable
0x2a802  stloc.s  8
0x2a804  ldloc.s  8
0x2a806  brfalse.s loc_2A80F
0x2a808  ldloc.s  8
0x2a80a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a80f  endfinally
0x2a810  ret
```
