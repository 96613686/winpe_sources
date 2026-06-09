# System.Windows.Markup.XmlLanguage::GetSpecificCulture

- ea: `0x2f230`
- end: `0x2f2f9`
- name: `System.Windows.Markup.XmlLanguage::GetSpecificCulture`
- size: `201`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x2f1d0`
- `0x2f230`
- `0x2f300`
- `0x145c00`
- `0x146e70`

## string_xrefs

- `0x2f27f`: `XmlLangGetSpecificCulture`
- `0x2f2d0`: `XmlLangGetSpecificCulture`

## pseudocode

```c

```

## disassembly

```asm
0x2f230  ldarg.0
0x2f231  ldfld    class [mscorlib]System.Globalization.CultureInfo System.Windows.Markup.XmlLanguage::_specificCulture
0x2f236  brtrue   loc_2F2F2
0x2f23b  ldarg.0
0x2f23c  ldfld    string System.Windows.Markup.XmlLanguage::_lowerCaseTag
0x2f241  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2f246  brfalse.s loc_2F25A
0x2f248  ldarg.0
0x2f249  ldfld    string System.Windows.Markup.XmlLanguage::_lowerCaseTag
0x2f24e  ldstr    aUnd// "und"
0x2f253  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x2f258  brtrue.s loc_2F26B
0x2f25a  ldarg.0
0x2f25b  ldarg.0
0x2f25c  call     instance class [mscorlib]System.Globalization.CultureInfo System.Windows.Markup.XmlLanguage::GetEquivalentCulture()
0x2f261  stfld    class [mscorlib]System.Globalization.CultureInfo System.Windows.Markup.XmlLanguage::_specificCulture
0x2f266  br       loc_2F2F2
0x2f26b  ldarg.0
0x2f26c  call     instance class [mscorlib]System.Globalization.CultureInfo System.Windows.Markup.XmlLanguage::GetCompatibleCulture()
0x2f271  stloc.0
0x2f272  ldloc.0
0x2f273  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_IetfLanguageTag()
0x2f278  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2f27d  brtrue.s loc_2F29E
0x2f27f  ldstr    aXmllanggetspec// "XmlLangGetSpecificCulture"
0x2f284  ldc.i4.1
0x2f285  newarr   [mscorlib]System.Object
0x2f28a  dup
0x2f28b  ldc.i4.0
0x2f28c  ldarg.0
0x2f28d  ldfld    string System.Windows.Markup.XmlLanguage::_lowerCaseTag
0x2f292  stelem.ref
0x2f293  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x2f298  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2f29d  throw
0x2f29e  ldloc.0
0x2f29f  callvirt instance bool [mscorlib]System.Globalization.CultureInfo::get_IsNeutralCulture()
0x2f2a4  brtrue.s loc_2F2AF
0x2f2a6  ldarg.0
0x2f2a7  ldloc.0
0x2f2a8  stfld    class [mscorlib]System.Globalization.CultureInfo System.Windows.Markup.XmlLanguage::_specificCulture
0x2f2ad  br.s     loc_2F2F2
0x2f2af  nop
0x2f2b0  ldloc.0
0x2f2b1  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0x2f2b6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::CreateSpecificCulture(string)
0x2f2bb  stloc.0
0x2f2bc  ldarg.0
0x2f2bd  ldloc.0
0x2f2be  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_IetfLanguageTag()
0x2f2c3  call     class [mscorlib]System.Globalization.CultureInfo MS.Internal.PresentationCore.SafeSecurityHelper::GetCultureInfoByIetfLanguageTag(string languageTag)
0x2f2c8  stfld    class [mscorlib]System.Globalization.CultureInfo System.Windows.Markup.XmlLanguage::_specificCulture
0x2f2cd  leave.s  loc_2F2F2
0x2f2cf  stloc.1
0x2f2d0  ldstr    aXmllanggetspec// "XmlLangGetSpecificCulture"
0x2f2d5  ldc.i4.1
0x2f2d6  newarr   [mscorlib]System.Object
0x2f2db  dup
0x2f2dc  ldc.i4.0
0x2f2dd  ldarg.0
0x2f2de  ldfld    string System.Windows.Markup.XmlLanguage::_lowerCaseTag
0x2f2e3  stelem.ref
0x2f2e4  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x2f2e9  ldloc.1
0x2f2ea  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string, class [mscorlib]System.Exception)
0x2f2ef  throw
0x2f2f0  leave.s  loc_2F2F2
0x2f2f2  ldarg.0
0x2f2f3  ldfld    class [mscorlib]System.Globalization.CultureInfo System.Windows.Markup.XmlLanguage::_specificCulture
0x2f2f8  ret
```
