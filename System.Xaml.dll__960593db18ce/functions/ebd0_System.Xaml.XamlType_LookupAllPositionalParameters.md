# System.Xaml.XamlType::LookupAllPositionalParameters

- ea: `0xebd0`
- end: `0xecfc`
- name: `System.Xaml.XamlType::LookupAllPositionalParameters`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0xe300`

## callees

- `0x87c0`
- `0x89a0`
- `0xbcb0`
- `0xbf20`
- `0xd0b0`
- `0xd420`
- `0xd970`
- `0xebd0`
- `0x11f50`

## string_xrefs

- `0xeca4`: `MarkupExtensionWithDuplicateArity`

## pseudocode

```c

```

## disassembly

```asm
0xebd0  ldarg.0
0xebd1  call     instance class [mscorlib]System.Type System.Xaml.XamlType::get_UnderlyingType()
0xebd6  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_Type()
0xebdb  callvirt instance class [mscorlib]System.Type System.Xaml.XamlType::get_UnderlyingType()
0xebe0  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xebe5  brfalse.s loc_EC1D
0xebe7  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class System.Xaml.XamlType>>::.ctor()
0xebec  stloc.1
0xebed  ldarg.0
0xebee  call     instance class System.Xaml.XamlSchemaContext System.Xaml.XamlType::get_SchemaContext()
0xebf3  ldtoken  [mscorlib]System.Type
0xebf8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xebfd  callvirt instance class System.Xaml.XamlType System.Xaml.XamlSchemaContext::GetXamlType(class [mscorlib]System.Type type)
0xec02  stloc.2
0xec03  ldc.i4.1
0xec04  newarr   System.Xaml.XamlType
0xec09  dup
0xec0a  ldc.i4.0
0xec0b  ldloc.2
0xec0c  stelem.ref
0xec0d  stloc.3
0xec0e  ldloc.1
0xec0f  ldc.i4.1
0xec10  ldloc.3
0xec11  call     T0x2B000027
0xec16  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class System.Xaml.XamlType>>::Add(var<u1>, !!T0)
0xec1b  ldloc.1
0xec1c  ret
0xec1d  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class System.Xaml.XamlType>>::.ctor()
0xec22  stloc.0
0xec23  ldarg.0
0xec24  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Reflection.ConstructorInfo> System.Xaml.XamlType::GetConstructors()
0xec29  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Reflection.ConstructorInfo>::GetEnumerator()
0xec2e  stloc.s  4
0xec30  br       loc_ECE0
0xec35  ldloc.s  4
0xec37  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Reflection.ConstructorInfo>::get_Current()
0xec3c  stloc.s  5
0xec3e  ldloc.s  5
0xec40  callvirt instance class [mscorlib]System.Reflection.ParameterInfo[] [mscorlib]System.Reflection.MethodBase::GetParameters()
0xec45  stloc.s  6
0xec47  ldloc.s  6
0xec49  ldlen
0xec4a  conv.i4
0xec4b  newarr   System.Xaml.XamlType
0xec50  stloc.s  7
0xec52  ldc.i4.0
0xec53  stloc.s  8
0xec55  br.s     loc_EC83
0xec57  ldloc.s  6
0xec59  ldloc.s  8
0xec5b  ldelem.ref
0xec5c  stloc.s  9
0xec5e  ldloc.s  9
0xec60  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.ParameterInfo::get_ParameterType()
0xec65  stloc.s  0xA
0xec67  ldarg.0
0xec68  call     instance class System.Xaml.XamlSchemaContext System.Xaml.XamlType::get_SchemaContext()
0xec6d  ldloc.s  0xA
0xec6f  callvirt instance class System.Xaml.XamlType System.Xaml.XamlSchemaContext::GetXamlType(class [mscorlib]System.Type type)
0xec74  stloc.s  0xB
0xec76  ldloc.s  7
0xec78  ldloc.s  8
0xec7a  ldloc.s  0xB
0xec7c  stelem.ref
0xec7d  ldloc.s  8
0xec7f  ldc.i4.1
0xec80  add
0xec81  stloc.s  8
0xec83  ldloc.s  8
0xec85  ldloc.s  6
0xec87  ldlen
0xec88  conv.i4
0xec89  blt.s    loc_EC57
0xec8b  ldloc.0
0xec8c  ldloc.s  7
0xec8e  ldlen
0xec8f  conv.i4
0xec90  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class System.Xaml.XamlType>>::ContainsKey(var<u1>)
0xec95  brfalse.s loc_ECCF
0xec97  ldarg.0
0xec98  call     instance class System.Xaml.XamlSchemaContext System.Xaml.XamlType::get_SchemaContext()
0xec9d  callvirt instance bool System.Xaml.XamlSchemaContext::get_SupportMarkupExtensionsWithDuplicateArity()
0xeca2  brtrue.s loc_ECE0
0xeca4  ldstr    aMarkupextensio// "MarkupExtensionWithDuplicateArity"
0xeca9  ldc.i4.2
0xecaa  newarr   [mscorlib]System.Object
0xecaf  dup
0xecb0  ldc.i4.0
0xecb1  ldarg.0
0xecb2  call     instance class [mscorlib]System.Type System.Xaml.XamlType::get_UnderlyingType()
0xecb7  stelem.ref
0xecb8  dup
0xecb9  ldc.i4.1
0xecba  ldloc.s  7
0xecbc  ldlen
0xecbd  conv.i4
0xecbe  box      [mscorlib]System.Int32
0xecc3  stelem.ref
0xecc4  call     string System.Xaml.SR::Get(string id, object[] args)
0xecc9  newobj   instance void System.Xaml.XamlSchemaException::.ctor(string message)
0xecce  throw
0xeccf  ldloc.0
0xecd0  ldloc.s  7
0xecd2  ldlen
0xecd3  conv.i4
0xecd4  ldloc.s  7
0xecd6  call     T0x2B000027
0xecdb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class System.Xaml.XamlType>>::Add(var<u1>, !!T0)
0xece0  ldloc.s  4
0xece2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xece7  brtrue   loc_EC35
0xecec  leave.s  loc_ECFA
0xecee  ldloc.s  4
0xecf0  brfalse.s loc_ECF9
0xecf2  ldloc.s  4
0xecf4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xecf9  endfinally
0xecfa  ldloc.0
0xecfb  ret
```
