# Microsoft.VisualStudio.Setup.InstallResult::AddTelemetryProperties

- ea: `0x7600`
- end: `0x76d9`
- name: `Microsoft.VisualStudio.Setup.InstallResult::AddTelemetryProperties`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x73f0`
- `0x7410`
- `0x7450`
- `0x7490`
- `0x74b0`
- `0x74d0`
- `0x7510`
- `0x7600`

## pseudocode

```c

```

## disassembly

```asm
0x7600  ldarg.2
0x7601  brfalse  loc_76D8
0x7606  ldarg.2
0x7607  ldarg.1
0x7608  ldstr    aReturncode// ".ReturnCode"
0x760d  call     string [mscorlib]System.String::Concat(string, string)
0x7612  ldarg.0
0x7613  call     instance int32 Microsoft.VisualStudio.Setup.InstallResult::get_ReturnCode()
0x7618  box      [mscorlib]System.Int32
0x761d  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0x7622  ldarg.2
0x7623  ldarg.1
0x7624  ldstr    aMessageid// ".MessageID"
0x7629  call     string [mscorlib]System.String::Concat(string, string)
0x762e  ldarg.0
0x762f  call     instance int32 Microsoft.VisualStudio.Setup.InstallResult::get_MessageId()
0x7634  box      [mscorlib]System.Int32
0x7639  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0x763e  ldarg.2
0x763f  ldarg.1
0x7640  ldstr    aType_0// ".Type"
0x7645  call     string [mscorlib]System.String::Concat(string, string)
0x764a  ldarg.0
0x764b  call     instance valuetype Microsoft.VisualStudio.Setup.InstallResultType Microsoft.VisualStudio.Setup.InstallResult::get_Type()
0x7650  box      Microsoft.VisualStudio.Setup.InstallResultType
0x7655  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0x765a  ldarg.0
0x765b  call     instance string Microsoft.VisualStudio.Setup.InstallResult::get_Message()
0x7660  brfalse.s loc_7679
0x7662  ldarg.2
0x7663  ldarg.1
0x7664  ldstr    aMessage// ".Message"
0x7669  call     string [mscorlib]System.String::Concat(string, string)
0x766e  ldarg.0
0x766f  call     instance string Microsoft.VisualStudio.Setup.InstallResult::get_Message()
0x7674  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0x7679  ldarg.0
0x767a  call     instance string Microsoft.VisualStudio.Setup.InstallResult::get_ResourceId()
0x767f  brfalse.s loc_7698
0x7681  ldarg.2
0x7682  ldarg.1
0x7683  ldstr    aResourceid// ".ResourceID"
0x7688  call     string [mscorlib]System.String::Concat(string, string)
0x768d  ldarg.0
0x768e  call     instance string Microsoft.VisualStudio.Setup.InstallResult::get_ResourceId()
0x7693  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0x7698  ldarg.0
0x7699  call     instance string Microsoft.VisualStudio.Setup.InstallResult::get_Watson()
0x769e  brfalse.s loc_76B7
0x76a0  ldarg.2
0x76a1  ldarg.1
0x76a2  ldstr    aWatson// ".Watson"
0x76a7  call     string [mscorlib]System.String::Concat(string, string)
0x76ac  ldarg.0
0x76ad  call     instance string Microsoft.VisualStudio.Setup.InstallResult::get_Watson()
0x76b2  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0x76b7  ldarg.0
0x76b8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x76bd  call     instance string Microsoft.VisualStudio.Setup.InstallResult::GetDetails([opt] class [mscorlib]System.Globalization.CultureInfo cultureInfo)
0x76c2  stloc.0
0x76c3  ldloc.0
0x76c4  brfalse.s loc_76D8
0x76c6  ldarg.2
0x76c7  ldarg.1
0x76c8  ldstr    aNeutraldetails// ".NeutralDetails"
0x76cd  call     string [mscorlib]System.String::Concat(string, string)
0x76d2  ldloc.0
0x76d3  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0x76d8  ret
```
