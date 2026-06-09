# System.Xaml.XamlXmlWriter::GetTypeName

- ea: `0x10110`
- end: `0x1015c`
- name: `System.Xaml.XamlXmlWriter::GetTypeName`
- size: `76`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x10050`
- `0x28440`
- `0x28a00`
- `0x2ce10`
- `0x2ceb0`
- `0x2cf60`

## callees

- `0x10`
- `0xd070`
- `0xd150`
- `0x10110`

## string_xrefs

- `0x10125`: `Extension`
- `0x10149`: `Extension`

## pseudocode

```c

```

## disassembly

```asm
0x10110  ldarg.0
0x10111  callvirt instance string System.Xaml.XamlType::get_Name()
0x10116  stloc.0
0x10117  ldarg.0
0x10118  callvirt instance bool System.Xaml.XamlType::get_IsMarkupExtension()
0x1011d  brfalse.s loc_1015A
0x1011f  ldarg.0
0x10120  callvirt instance string System.Xaml.XamlType::get_Name()
0x10125  ldstr    aExtension// "Extension"
0x1012a  ldc.i4.0
0x1012b  call     class [mscorlib]System.Globalization.CultureInfo System.Xaml.TypeConverterHelper::get_InvariantEnglishUS()
0x10130  callvirt instance bool [mscorlib]System.String::EndsWith(string, bool, class [mscorlib]System.Globalization.CultureInfo)
0x10135  brfalse.s loc_1015A
0x10137  ldarg.0
0x10138  callvirt instance string System.Xaml.XamlType::get_Name()
0x1013d  ldc.i4.0
0x1013e  ldarg.0
0x1013f  callvirt instance string System.Xaml.XamlType::get_Name()
0x10144  callvirt instance int32 [mscorlib]System.String::get_Length()
0x10149  ldstr    aExtension// "Extension"
0x1014e  call     instance int32 [mscorlib]System.String::get_Length()
0x10153  sub
0x10154  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x10159  stloc.0
0x1015a  ldloc.0
0x1015b  ret
```
