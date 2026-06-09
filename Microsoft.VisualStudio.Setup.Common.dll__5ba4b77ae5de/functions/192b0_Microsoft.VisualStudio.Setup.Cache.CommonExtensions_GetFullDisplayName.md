# Microsoft.VisualStudio.Setup.Cache.CommonExtensions::GetFullDisplayName

- ea: `0x192b0`
- end: `0x1933b`
- name: `Microsoft.VisualStudio.Setup.Cache.CommonExtensions::GetFullDisplayName`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x34b0`
- `0x34d0`
- `0x34f0`
- `0xc1a0`
- `0x192b0`
- `0x19c20`
- `0x19d00`
- `0x19d80`

## pseudocode

```c

```

## disassembly

```asm
0x192b0  ldarg.0
0x192b1  ldstr    aInstance// "instance"
0x192b6  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x192bb  ldarg.0
0x192bc  ldnull
0x192bd  callvirt instance string Microsoft.VisualStudio.Setup.Cache.IInstance::GetDisplayName([opt] class [mscorlib]System.Globalization.CultureInfo culture)
0x192c2  stloc.0
0x192c3  ldarg.0
0x192c4  ldnull
0x192c5  ldc.i4.3
0x192c6  callvirt instance string Microsoft.VisualStudio.Setup.Cache.IInstance::GetChannelSuffix([opt] class [mscorlib]System.Globalization.CultureInfo culture, [opt] valuetype Microsoft.VisualStudio.Setup.LocalizedResourceFallback languageFallback)
0x192cb  stloc.1
0x192cc  ldloc.1
0x192cd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x192d2  ldc.i4.0
0x192d3  ceq
0x192d5  ldarg.0
0x192d6  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string> Microsoft.VisualStudio.Setup.Cache.IInstance::get_Properties()
0x192db  ldsfld   string Microsoft.VisualStudio.Setup.Cache.CommonExtensions::Nickname
0x192e0  ldloca.s 3
0x192e2  callvirt instance bool class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string>::TryGetValue(var<u1>, !!T0)
0x192e7  brfalse.s loc_192F4
0x192e9  ldloc.3
0x192ea  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x192ef  ldc.i4.0
0x192f0  ceq
0x192f2  br.s     loc_192F5
0x192f4  ldc.i4.0
0x192f5  stloc.2
0x192f6  brfalse.s loc_19324
0x192f8  ldloc.2
0x192f9  brfalse.s loc_19310
0x192fb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x19300  call     string Microsoft.VisualStudio.Setup.CommonResources::get_DisplayNameWithChannelSuffixAndNickName_Args3()
0x19305  ldloc.0
0x19306  ldloc.1
0x19307  ldloc.3
0x19308  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object, object)
0x1930d  stloc.0
0x1930e  br.s     loc_19339
0x19310  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x19315  call     string Microsoft.VisualStudio.Setup.CommonResources::get_DisplayNameWithChannelSuffix_Args2()
0x1931a  ldloc.0
0x1931b  ldloc.1
0x1931c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x19321  stloc.0
0x19322  br.s     loc_19339
0x19324  ldloc.2
0x19325  brfalse.s loc_19339
0x19327  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x1932c  call     string Microsoft.VisualStudio.Setup.CommonResources::get_DisplayNameWithNickname_Args2()
0x19331  ldloc.0
0x19332  ldloc.3
0x19333  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x19338  stloc.0
0x19339  ldloc.0
0x1933a  ret
```
