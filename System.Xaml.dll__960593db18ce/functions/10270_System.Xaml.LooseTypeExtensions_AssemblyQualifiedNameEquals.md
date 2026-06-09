# System.Xaml.LooseTypeExtensions::AssemblyQualifiedNameEquals

- ea: `0x10270`
- end: `0x10321`
- name: `System.Xaml.LooseTypeExtensions::AssemblyQualifiedNameEquals`
- size: `177`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x103a0`
- `0x10410`
- `0x10460`
- `0x12f60`
- `0x131d0`
- `0x13330`
- `0x134b0`
- `0x13620`
- `0x178b0`

## callees

- `0xc10`
- `0x10270`
- `0x10330`

## pseudocode

```c

```

## disassembly

```asm
0x10270  ldarg.0
0x10271  brtrue.s loc_10278
0x10273  ldarg.1
0x10274  ldnull
0x10275  ceq
0x10277  ret
0x10278  ldarg.1
0x10279  brtrue.s loc_1027D
0x1027b  ldc.i4.0
0x1027c  ret
0x1027d  ldarg.0
0x1027e  callvirt instance string [mscorlib]System.Type::get_FullName()
0x10283  ldarg.1
0x10284  callvirt instance string [mscorlib]System.Type::get_FullName()
0x10289  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x1028e  brfalse.s loc_10292
0x10290  ldc.i4.0
0x10291  ret
0x10292  ldarg.0
0x10293  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x10298  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x1029d  ldarg.1
0x1029e  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x102a3  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x102a8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x102ad  brfalse.s loc_102B1
0x102af  ldc.i4.1
0x102b0  ret
0x102b1  ldarg.0
0x102b2  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x102b7  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x102bc  newobj   instance void [mscorlib]System.Reflection.AssemblyName::.ctor(string)
0x102c1  stloc.0
0x102c2  ldarg.1
0x102c3  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x102c8  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x102cd  newobj   instance void [mscorlib]System.Reflection.AssemblyName::.ctor(string)
0x102d2  stloc.1
0x102d3  ldloc.0
0x102d4  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_Name()
0x102d9  ldloc.1
0x102da  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_Name()
0x102df  call     bool [mscorlib]System.String::op_Equality(string, string)
0x102e4  brfalse.s loc_1030D
0x102e6  ldloc.0
0x102e7  callvirt instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Reflection.AssemblyName::get_CultureInfo()
0x102ec  ldloc.1
0x102ed  callvirt instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Reflection.AssemblyName::get_CultureInfo()
0x102f2  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x102f7  brfalse.s loc_1030B
0x102f9  ldloc.0
0x102fa  callvirt instance unsigned int8[] [mscorlib]System.Reflection.AssemblyName::GetPublicKeyToken()
0x102ff  ldloc.1
0x10300  callvirt instance unsigned int8[] [mscorlib]System.Reflection.AssemblyName::GetPublicKeyToken()
0x10305  call     bool System.Xaml.SafeSecurityHelper::IsSameKeyToken(unsigned int8[] reqKeyToken, unsigned int8[] curKeyToken)
0x1030a  ret
0x1030b  ldc.i4.0
0x1030c  ret
0x1030d  ldarg.0
0x1030e  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x10313  ldarg.1
0x10314  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x10319  ldloc.0
0x1031a  ldloc.1
0x1031b  call     bool System.Xaml.LooseTypeExtensions::IsWindowsBaseToSystemXamlComparison(class [mscorlib]System.Reflection.Assembly a1, class [mscorlib]System.Reflection.Assembly a2, class [mscorlib]System.Reflection.AssemblyName name1, class [mscorlib]System.Reflection.AssemblyName name2)
0x10320  ret
```
