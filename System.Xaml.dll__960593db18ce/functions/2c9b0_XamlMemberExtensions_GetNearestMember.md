# XamlMemberExtensions::GetNearestMember

- ea: `0x2c9b0`
- end: `0x2ca87`
- name: `XamlMemberExtensions::GetNearestMember`
- size: `215`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0xf2b0`
- `0xf2c0`
- `0xf2d0`

## callees

- `0x8a00`
- `0xa3f0`
- `0xa4c0`
- `0xa6c0`
- `0xa6e0`
- `0xa850`
- `0xa8e0`
- `0xb280`
- `0xcfb0`
- `0xd0b0`
- `0xd430`
- `0xefa0`
- `0x2c9b0`
- `0x2ca90`
- `0x2cad0`

## pseudocode

```c

```

## disassembly

```asm
0x2c9b0  ldarg.0
0x2c9b1  callvirt instance bool System.Xaml.XamlMember::get_IsAttachable()
0x2c9b6  brtrue.s loc_2C9C9
0x2c9b8  ldarg.0
0x2c9b9  callvirt instance bool System.Xaml.XamlMember::get_IsDirective()
0x2c9be  brtrue.s loc_2C9C9
0x2c9c0  ldarg.0
0x2c9c1  ldarg.1
0x2c9c2  call     bool XamlMemberExtensions::MeetsCriterion(class System.Xaml.XamlMember member, valuetype GetNearestBaseMemberCriterion criterion)
0x2c9c7  brfalse.s loc_2C9CB
0x2c9c9  ldarg.0
0x2c9ca  ret
0x2c9cb  ldarg.0
0x2c9cc  callvirt instance class [mscorlib]System.Reflection.MethodInfo System.Xaml.XamlMember::get_Getter()
0x2c9d1  dup
0x2c9d2  brtrue.s loc_2C9DB
0x2c9d4  pop
0x2c9d5  ldarg.0
0x2c9d6  callvirt instance class [mscorlib]System.Reflection.MethodInfo System.Xaml.XamlMember::get_Setter()
0x2c9db  stloc.0
0x2c9dc  ldloc.0
0x2c9dd  ldnull
0x2c9de  call     bool [mscorlib]System.Reflection.MethodInfo::op_Equality(class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Reflection.MethodInfo)
0x2c9e3  brtrue.s loc_2C9ED
0x2c9e5  ldloc.0
0x2c9e6  callvirt instance bool [mscorlib]System.Reflection.MethodBase::get_IsVirtual()
0x2c9eb  brtrue.s loc_2C9EF
0x2c9ed  ldarg.0
0x2c9ee  ret
0x2c9ef  ldloc.0
0x2c9f0  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Reflection.MethodInfo::GetBaseDefinition()
0x2c9f5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.MemberInfo::get_DeclaringType()
0x2c9fa  stloc.1
0x2c9fb  ldarg.0
0x2c9fc  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_DeclaringType()
0x2ca01  callvirt instance class [mscorlib]System.Type System.Xaml.XamlType::get_UnderlyingType()
0x2ca06  ldloc.1
0x2ca07  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2ca0c  brfalse.s loc_2CA10
0x2ca0e  ldarg.0
0x2ca0f  ret
0x2ca10  ldarg.0
0x2ca11  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_DeclaringType()
0x2ca16  callvirt instance class System.Xaml.XamlType System.Xaml.XamlType::get_BaseType()
0x2ca1b  stloc.2
0x2ca1c  br.s     loc_2CA6F
0x2ca1e  ldloc.2
0x2ca1f  ldarg.0
0x2ca20  callvirt instance string System.Xaml.XamlMember::get_Name()
0x2ca25  callvirt instance class System.Xaml.XamlMember System.Xaml.XamlType::GetMember(string name)
0x2ca2a  stloc.3
0x2ca2b  ldloc.3
0x2ca2c  ldnull
0x2ca2d  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x2ca32  brfalse.s loc_2CA4A
0x2ca34  ldloc.2
0x2ca35  ldarg.0
0x2ca36  callvirt instance string System.Xaml.XamlMember::get_Name()
0x2ca3b  call     class System.Xaml.XamlMember XamlMemberExtensions::GetExcludedReadOnlyMember(class System.Xaml.XamlType type, string name)
0x2ca40  stloc.3
0x2ca41  ldloc.3
0x2ca42  ldnull
0x2ca43  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x2ca48  brtrue.s loc_2CA85
0x2ca4a  ldloc.3
0x2ca4b  ldarg.1
0x2ca4c  call     bool XamlMemberExtensions::MeetsCriterion(class System.Xaml.XamlMember member, valuetype GetNearestBaseMemberCriterion criterion)
0x2ca51  brfalse.s loc_2CA55
0x2ca53  ldloc.3
0x2ca54  ret
0x2ca55  ldloc.2
0x2ca56  callvirt instance class [mscorlib]System.Type System.Xaml.XamlType::get_UnderlyingType()
0x2ca5b  ldloc.1
0x2ca5c  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2ca61  brtrue.s loc_2CA85
0x2ca63  ldloc.3
0x2ca64  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_DeclaringType()
0x2ca69  callvirt instance class System.Xaml.XamlType System.Xaml.XamlType::get_BaseType()
0x2ca6e  stloc.2
0x2ca6f  ldloc.2
0x2ca70  ldnull
0x2ca71  call     bool System.Xaml.XamlType::op_Inequality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x2ca76  brfalse.s loc_2CA85
0x2ca78  ldloc.2
0x2ca79  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_Object()
0x2ca7e  call     bool System.Xaml.XamlType::op_Inequality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x2ca83  brtrue.s loc_2CA1E
0x2ca85  ldarg.0
0x2ca86  ret
```
