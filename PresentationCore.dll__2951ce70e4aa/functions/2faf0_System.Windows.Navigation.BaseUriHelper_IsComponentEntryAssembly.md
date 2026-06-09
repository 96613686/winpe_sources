# System.Windows.Navigation.BaseUriHelper::IsComponentEntryAssembly

- ea: `0x2faf0`
- end: `0x2fb49`
- name: `System.Windows.Navigation.BaseUriHelper::IsComponentEntryAssembly`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x2faf0`
- `0x2fc80`
- `0x145870`

## string_xrefs

- `0x2faf1`: `;component`

## pseudocode

```c

```

## disassembly

```asm
0x2faf0  ldarg.0
0x2faf1  ldstr    aComponent// ";component"
0x2faf6  ldc.i4.5
0x2faf7  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x2fafc  brfalse.s loc_2FB47
0x2fafe  ldarg.0
0x2faff  ldc.i4.1
0x2fb00  newarr   [mscorlib]System.Char
0x2fb05  dup
0x2fb06  ldc.i4.0
0x2fb07  ldc.i4.s 0x3B
0x2fb09  stelem.i2
0x2fb0a  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x2fb0f  stloc.2
0x2fb10  ldloc.2
0x2fb11  ldlen
0x2fb12  conv.i4
0x2fb13  stloc.1
0x2fb14  ldloc.1
0x2fb15  ldc.i4.2
0x2fb16  blt.s    loc_2FB47
0x2fb18  ldloc.1
0x2fb19  ldc.i4.4
0x2fb1a  bgt.s    loc_2FB47
0x2fb1c  ldloc.2
0x2fb1d  ldc.i4.0
0x2fb1e  ldelem.ref
0x2fb1f  call     string [System]System.Uri::UnescapeDataString(string)
0x2fb24  stloc.3
0x2fb25  call     class [mscorlib]System.Reflection.Assembly System.Windows.Navigation.BaseUriHelper::get_ResourceAssembly()
0x2fb2a  stloc.0
0x2fb2b  ldloc.0
0x2fb2c  ldnull
0x2fb2d  call     bool [mscorlib]System.Reflection.Assembly::op_Inequality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0x2fb32  brfalse.s loc_2FB45
0x2fb34  ldloc.0
0x2fb35  call     string MS.Internal.PresentationCore.SafeSecurityHelper::GetAssemblyPartialName(class [mscorlib]System.Reflection.Assembly assembly)
0x2fb3a  ldloc.3
0x2fb3b  ldc.i4.5
0x2fb3c  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2fb41  ldc.i4.0
0x2fb42  ceq
0x2fb44  ret
0x2fb45  ldc.i4.0
0x2fb46  ret
0x2fb47  ldc.i4.0
0x2fb48  ret
```
