# System.Windows.Markup.XmlLanguage::GetEquivalentCulture

- ea: `0x2f1d0`
- end: `0x2f22d`
- name: `System.Windows.Markup.XmlLanguage::GetEquivalentCulture`
- size: `93`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x2f230`
- `0x2f4d0`
- `0x12cea0`

## callees

- `0x2f1d0`
- `0x145c00`
- `0x146e70`

## string_xrefs

- `0x2f209`: `XmlLangGetCultureFailure`

## pseudocode

```c

```

## disassembly

```asm
0x2f1d0  ldarg.0
0x2f1d1  ldfld    class [mscorlib]System.Globalization.CultureInfo System.Windows.Markup.XmlLanguage::_equivalentCulture
0x2f1d6  brtrue.s loc_2F226
0x2f1d8  ldarg.0
0x2f1d9  ldfld    string System.Windows.Markup.XmlLanguage::_lowerCaseTag
0x2f1de  stloc.0
0x2f1df  ldloc.0
0x2f1e0  ldstr    aUnd// "und"
0x2f1e5  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x2f1ea  brtrue.s loc_2F1F2
0x2f1ec  ldsfld   string [mscorlib]System.String::Empty
0x2f1f1  stloc.0
0x2f1f2  nop
0x2f1f3  ldarg.0
0x2f1f4  ldloc.0
0x2f1f5  call     class [mscorlib]System.Globalization.CultureInfo MS.Internal.PresentationCore.SafeSecurityHelper::GetCultureInfoByIetfLanguageTag(string languageTag)
0x2f1fa  stfld    class [mscorlib]System.Globalization.CultureInfo System.Windows.Markup.XmlLanguage::_equivalentCulture
0x2f1ff  leave.s  loc_2F226
0x2f201  stloc.1
0x2f202  ldarg.0
0x2f203  ldc.i4.1
0x2f204  stfld    bool System.Windows.Markup.XmlLanguage::_equivalentCultureFailed
0x2f209  ldstr    aXmllanggetcult// "XmlLangGetCultureFailure"
0x2f20e  ldc.i4.1
0x2f20f  newarr   [mscorlib]System.Object
0x2f214  dup
0x2f215  ldc.i4.0
0x2f216  ldloc.0
0x2f217  stelem.ref
0x2f218  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x2f21d  ldloc.1
0x2f21e  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string, class [mscorlib]System.Exception)
0x2f223  throw
0x2f224  leave.s  loc_2F226
0x2f226  ldarg.0
0x2f227  ldfld    class [mscorlib]System.Globalization.CultureInfo System.Windows.Markup.XmlLanguage::_equivalentCulture
0x2f22c  ret
```
