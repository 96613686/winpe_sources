# ObjectMarkupInfo::GetConstructorInfo

- ea: `0x2ad80`
- end: `0x2afc8`
- name: `ObjectMarkupInfo::GetConstructorInfo`
- size: `584`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x2ac60`

## callees

- `0x8810`
- `0xa590`
- `0xb280`
- `0xd0b0`
- `0xd110`
- `0xd130`
- `0xd480`
- `0xd930`
- `0xd970`
- `0xf2c0`
- `0x11f50`
- `0x202a0`
- `0x2ad80`
- `0x2bc60`
- `0x2c1f0`

## string_xrefs

- `0x2af89`: `ObjectReaderNoDefaultConstructor`
- `0x2afa8`: `ObjectReaderNoMatchingConstructor`

## pseudocode

```c

```

## disassembly

```asm
0x2ad80  ldarg.s  4
0x2ad82  ldnull
0x2ad83  stind.ref
0x2ad84  ldarg.s  5
0x2ad86  ldnull
0x2ad87  stind.ref
0x2ad88  ldarg.s  6
0x2ad8a  ldc.i4.0
0x2ad8b  stind.i1
0x2ad8c  ldarg.2
0x2ad8d  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class System.Xaml.XamlMember> System.Xaml.XamlType::GetAllMembers()
0x2ad92  stloc.0
0x2ad93  ldarg.2
0x2ad94  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class System.Xaml.XamlMember> System.Xaml.XamlType::GetAllExcludedReadOnlyMembers()
0x2ad99  stloc.1
0x2ad9a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xaml.XamlMember>::.ctor()
0x2ad9f  stloc.2
0x2ada0  ldloc.0
0x2ada1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Xaml.XamlMember>::GetEnumerator()
0x2ada6  stloc.3
0x2ada7  br.s     loc_2ADD1
0x2ada9  ldloc.3
0x2adaa  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xaml.XamlMember>::get_Current()
0x2adaf  stloc.s  4
0x2adb1  ldarg.3
0x2adb2  ldloc.s  4
0x2adb4  callvirt instance bool SerializerContext::IsPropertyReadVisible(class System.Xaml.XamlMember property)
0x2adb9  brfalse.s loc_2ADD1
0x2adbb  ldloc.s  4
0x2adbd  call     string System.Xaml.XamlObjectReader::GetConstructorArgument(class System.Xaml.XamlMember member)
0x2adc2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2adc7  brtrue.s loc_2ADD1
0x2adc9  ldloc.2
0x2adca  ldloc.s  4
0x2adcc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xaml.XamlMember>::Add(var<u1>)
0x2add1  ldloc.3
0x2add2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2add7  brtrue.s loc_2ADA9
0x2add9  leave.s  loc_2ADE5
0x2addb  ldloc.3
0x2addc  brfalse.s loc_2ADE4
0x2adde  ldloc.3
0x2addf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2ade4  endfinally
0x2ade5  ldloc.1
0x2ade6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Xaml.XamlMember>::GetEnumerator()
0x2adeb  stloc.s  5
0x2aded  br.s     loc_2AE18
0x2adef  ldloc.s  5
0x2adf1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xaml.XamlMember>::get_Current()
0x2adf6  stloc.s  6
0x2adf8  ldarg.3
0x2adf9  ldloc.s  6
0x2adfb  callvirt instance bool SerializerContext::IsPropertyReadVisible(class System.Xaml.XamlMember property)
0x2ae00  brfalse.s loc_2AE18
0x2ae02  ldloc.s  6
0x2ae04  call     string System.Xaml.XamlObjectReader::GetConstructorArgument(class System.Xaml.XamlMember member)
0x2ae09  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2ae0e  brtrue.s loc_2AE18
0x2ae10  ldloc.2
0x2ae11  ldloc.s  6
0x2ae13  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xaml.XamlMember>::Add(var<u1>)
0x2ae18  ldloc.s  5
0x2ae1a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2ae1f  brtrue.s loc_2ADEF
0x2ae21  leave.s  loc_2AE2F
0x2ae23  ldloc.s  5
0x2ae25  brfalse.s loc_2AE2E
0x2ae27  ldloc.s  5
0x2ae29  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2ae2e  endfinally
0x2ae2f  ldarg.2
0x2ae30  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Reflection.ConstructorInfo> System.Xaml.XamlType::GetConstructors()
0x2ae35  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Reflection.ConstructorInfo>::GetEnumerator()
0x2ae3a  stloc.s  7
0x2ae3c  br       loc_2AF4F
0x2ae41  ldloc.s  7
0x2ae43  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Reflection.ConstructorInfo>::get_Current()
0x2ae48  stloc.s  8
0x2ae4a  ldloc.s  8
0x2ae4c  callvirt instance class [mscorlib]System.Reflection.ParameterInfo[] [mscorlib]System.Reflection.MethodBase::GetParameters()
0x2ae51  stloc.s  9
0x2ae53  ldloc.s  9
0x2ae55  ldlen
0x2ae56  conv.i4
0x2ae57  ldloc.2
0x2ae58  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Xaml.XamlMember>::get_Count()
0x2ae5d  bne.un   loc_2AF4F
0x2ae62  ldloc.s  9
0x2ae64  ldlen
0x2ae65  conv.i4
0x2ae66  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<object>::.ctor(int32)
0x2ae6b  stloc.s  0xA
0x2ae6d  ldc.i4.0
0x2ae6e  stloc.s  0xB
0x2ae70  br       loc_2AF06
0x2ae75  ldloc.s  9
0x2ae77  ldloc.s  0xB
0x2ae79  ldelem.ref
0x2ae7a  stloc.s  0xC
0x2ae7c  ldnull
0x2ae7d  stloc.s  0xD
0x2ae7f  ldloc.2
0x2ae80  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class System.Xaml.XamlMember>::GetEnumerator()
0x2ae85  stloc.s  0xE
0x2ae87  br.s     loc_2AEC7
0x2ae89  ldloca.s 0xE
0x2ae8b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xaml.XamlMember>::get_Current()
0x2ae90  stloc.s  0xF
0x2ae92  ldloc.s  0xF
0x2ae94  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_Type()
0x2ae99  callvirt instance class [mscorlib]System.Type System.Xaml.XamlType::get_UnderlyingType()
0x2ae9e  ldloc.s  0xC
0x2aea0  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.ParameterInfo::get_ParameterType()
0x2aea5  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2aeaa  brfalse.s loc_2AEC7
0x2aeac  ldloc.s  0xF
0x2aeae  call     string System.Xaml.XamlObjectReader::GetConstructorArgument(class System.Xaml.XamlMember member)
0x2aeb3  ldloc.s  0xC
0x2aeb5  callvirt instance string [mscorlib]System.Reflection.ParameterInfo::get_Name()
0x2aeba  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2aebf  brfalse.s loc_2AEC7
0x2aec1  ldloc.s  0xF
0x2aec3  stloc.s  0xD
0x2aec5  leave.s  loc_2AEE0
0x2aec7  ldloca.s 0xE
0x2aec9  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xaml.XamlMember>::MoveNext()
0x2aece  brtrue.s loc_2AE89
0x2aed0  leave.s  loc_2AEE0
0x2aed2  ldloca.s 0xE
0x2aed4  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Xaml.XamlMember>
0x2aeda  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2aedf  endfinally
0x2aee0  ldloc.s  0xD
0x2aee2  ldnull
0x2aee3  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x2aee8  brtrue.s loc_2AF11
0x2aeea  ldloc.s  0xA
0x2aeec  ldarg.3
0x2aeed  callvirt instance class MS.Internal.Xaml.Runtime.ClrObjectRuntime SerializerContext::get_Runtime()
0x2aef2  ldarg.1
0x2aef3  ldloc.s  0xD
0x2aef5  callvirt instance object MS.Internal.Xaml.Runtime.XamlRuntime::GetValue(object obj, class System.Xaml.XamlMember property)
0x2aefa  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x2aeff  pop
0x2af00  ldloc.s  0xB
0x2af02  ldc.i4.1
0x2af03  add
0x2af04  stloc.s  0xB
0x2af06  ldloc.s  0xB
0x2af08  ldloc.s  9
0x2af0a  ldlen
0x2af0b  conv.i4
0x2af0c  blt      loc_2AE75
0x2af11  ldloc.s  0xA
0x2af13  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x2af18  ldloc.2
0x2af19  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Xaml.XamlMember>::get_Count()
0x2af1e  bne.un.s loc_2AF4F
0x2af20  ldarg.s  4
0x2af22  ldloc.s  8
0x2af24  stind.ref
0x2af25  ldarg.s  5
0x2af27  ldloc.s  0xA
0x2af29  stind.ref
0x2af2a  ldloc.s  0xA
0x2af2c  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x2af31  ldloc.0
0x2af32  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class System.Xaml.XamlMember>::get_Count()
0x2af37  bne.un.s loc_2AF5B
0x2af39  ldarg.2
0x2af3a  callvirt instance bool System.Xaml.XamlType::get_IsCollection()
0x2af3f  brtrue.s loc_2AF5B
0x2af41  ldarg.2
0x2af42  callvirt instance bool System.Xaml.XamlType::get_IsDictionary()
0x2af47  brtrue.s loc_2AF5B
0x2af49  ldarg.s  6
0x2af4b  ldc.i4.1
0x2af4c  stind.i1
0x2af4d  leave.s  loc_2AF69
0x2af4f  ldloc.s  7
0x2af51  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2af56  brtrue   loc_2AE41
0x2af5b  leave.s  loc_2AF69
0x2af5d  ldloc.s  7
0x2af5f  brfalse.s loc_2AF68
0x2af61  ldloc.s  7
0x2af63  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2af68  endfinally
0x2af69  ldarg.s  4
0x2af6b  ldind.ref
0x2af6c  ldnull
0x2af6d  call     bool [mscorlib]System.Reflection.MemberInfo::op_Equality(class [mscorlib]System.Reflection.MemberInfo, class [mscorlib]System.Reflection.MemberInfo)
0x2af72  brfalse.s loc_2AFC7
0x2af74  ldarg.2
0x2af75  callvirt instance class [mscorlib]System.Type System.Xaml.XamlType::get_UnderlyingType()
0x2af7a  callvirt instance bool [mscorlib]System.Type::get_IsValueType()
0x2af7f  brtrue.s loc_2AFC7
0x2af81  ldloc.2
0x2af82  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Xaml.XamlMember>::get_Count()
0x2af87  brtrue.s loc_2AFA8
0x2af89  ldstr    aObjectreaderno// "ObjectReaderNoDefaultConstructor"
0x2af8e  ldc.i4.1
0x2af8f  newarr   [mscorlib]System.Object
0x2af94  dup
0x2af95  ldc.i4.0
0x2af96  ldarg.1
0x2af97  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2af9c  stelem.ref
0x2af9d  call     string System.Xaml.SR::Get(string id, object[] args)
0x2afa2  newobj   instance void System.Xaml.XamlObjectReaderException::.ctor(string message)
0x2afa7  throw
0x2afa8  ldstr    aObjectreaderno_0// "ObjectReaderNoMatchingConstructor"
0x2afad  ldc.i4.1
0x2afae  newarr   [mscorlib]System.Object
0x2afb3  dup
0x2afb4  ldc.i4.0
0x2afb5  ldarg.1
0x2afb6  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2afbb  stelem.ref
0x2afbc  call     string System.Xaml.SR::Get(string id, object[] args)
0x2afc1  newobj   instance void System.Xaml.XamlObjectReaderException::.ctor(string message)
0x2afc6  throw
0x2afc7  ret
```
