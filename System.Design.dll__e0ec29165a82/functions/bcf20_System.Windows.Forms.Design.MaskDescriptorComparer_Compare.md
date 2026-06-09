# System.Windows.Forms.Design.MaskDescriptorComparer::Compare

- ea: `0xbcf20`
- end: `0xbcfc3`
- name: `System.Windows.Forms.Design.MaskDescriptorComparer::Compare`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x8ef40`
- `0xbcc40`
- `0xbcc50`
- `0xbcc60`
- `0xbcf20`

## string_xrefs

- `0xbcf7c`: `MaskDescriptorValidatingTypeNone`
- `0xbcfa2`: `MaskDescriptorValidatingTypeNone`

## pseudocode

```c

```

## disassembly

```asm
0xbcf20  ldarg.1
0xbcf21  brfalse.s loc_BCF26
0xbcf23  ldarg.2
0xbcf24  brtrue.s loc_BCF28
0xbcf26  ldc.i4.0
0xbcf27  ret
0xbcf28  ldarg.0
0xbcf29  ldfld    valuetype SortType System.Windows.Forms.Design.MaskDescriptorComparer::sortType
0xbcf2e  stloc.3
0xbcf2f  ldloc.3
0xbcf30  switch   loc_BCF41, loc_BCF51, loc_BCF61
0xbcf41  ldarg.1
0xbcf42  callvirt instance string System.Windows.Forms.Design.MaskDescriptor::get_Name()
0xbcf47  stloc.0
0xbcf48  ldarg.2
0xbcf49  callvirt instance string System.Windows.Forms.Design.MaskDescriptor::get_Name()
0xbcf4e  stloc.1
0xbcf4f  br.s     loc_BCFAD
0xbcf51  ldarg.1
0xbcf52  callvirt instance string System.Windows.Forms.Design.MaskDescriptor::get_Sample()
0xbcf57  stloc.0
0xbcf58  ldarg.2
0xbcf59  callvirt instance string System.Windows.Forms.Design.MaskDescriptor::get_Sample()
0xbcf5e  stloc.1
0xbcf5f  br.s     loc_BCFAD
0xbcf61  ldarg.1
0xbcf62  callvirt instance class [mscorlib]System.Type System.Windows.Forms.Design.MaskDescriptor::get_ValidatingType()
0xbcf67  ldnull
0xbcf68  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xbcf6d  brtrue.s loc_BCF7C
0xbcf6f  ldarg.1
0xbcf70  callvirt instance class [mscorlib]System.Type System.Windows.Forms.Design.MaskDescriptor::get_ValidatingType()
0xbcf75  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xbcf7a  br.s     loc_BCF86
0xbcf7c  ldstr    aMaskdescriptor_1// "MaskDescriptorValidatingTypeNone"
0xbcf81  call     string System.Design.SR::GetString(string name)
0xbcf86  stloc.0
0xbcf87  ldarg.2
0xbcf88  callvirt instance class [mscorlib]System.Type System.Windows.Forms.Design.MaskDescriptor::get_ValidatingType()
0xbcf8d  ldnull
0xbcf8e  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xbcf93  brtrue.s loc_BCFA2
0xbcf95  ldarg.2
0xbcf96  callvirt instance class [mscorlib]System.Type System.Windows.Forms.Design.MaskDescriptor::get_ValidatingType()
0xbcf9b  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xbcfa0  br.s     loc_BCFAC
0xbcfa2  ldstr    aMaskdescriptor_1// "MaskDescriptorValidatingTypeNone"
0xbcfa7  call     string System.Design.SR::GetString(string name)
0xbcfac  stloc.1
0xbcfad  ldloc.0
0xbcfae  ldloc.1
0xbcfaf  call     int32 [mscorlib]System.String::Compare(string, string)
0xbcfb4  stloc.2
0xbcfb5  ldarg.0
0xbcfb6  ldfld    valuetype [System.Windows.Forms]System.Windows.Forms.SortOrder System.Windows.Forms.Design.MaskDescriptorComparer::sortOrder
0xbcfbb  ldc.i4.2
0xbcfbc  beq.s    loc_BCFC0
0xbcfbe  ldloc.2
0xbcfbf  ret
0xbcfc0  ldloc.2
0xbcfc1  neg
0xbcfc2  ret
```
