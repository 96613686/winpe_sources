# Microsoft.VisualStudio.Setup.Installer.VsixInstaller::InstallProgIds

- ea: `0x332a0`
- end: `0x335e3`
- name: `Microsoft.VisualStudio.Setup.Installer.VsixInstaller::InstallProgIds`
- size: `835`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x331c0`

## callees

- `0xf0e0`
- `0x332a0`
- `0x34000`

## string_xrefs

- `0x332d0`: `Cannot process empty ProgId for install`
- `0x33303`: `Installing ProgId: {0}`
- `0x33425`: `shell\Open\Command`
- `0x334b6`: `shell\Open\ddeexec`
- `0x334c6`: `Open("%1")`
- `0x33589`: `CLSID`

## pseudocode

```c

```

## disassembly

```asm
0x332a0  ldarg.2
0x332a1  ldc.i4.1
0x332a2  ldc.i4.0
0x332a3  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry::OpenBaseKey(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryHive, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryView)
0x332a8  stloc.0
0x332a9  ldarg.1
0x332aa  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ProgId> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage::get_ProgIds()
0x332af  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ProgId>::GetEnumerator()
0x332b4  stloc.1
0x332b5  br       loc_335C1
0x332ba  ldloc.1
0x332bb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ProgId>::get_Current()
0x332c0  stloc.2
0x332c1  ldloc.2
0x332c2  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ProgId::get_Id()
0x332c7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x332cc  brfalse.s loc_332E4
0x332ce  ldarg.s  4
0x332d0  ldstr    aCannotProcessE// "Cannot process empty ProgId for install"
0x332d5  call     T0x2B000003
0x332da  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x332df  br       loc_335C1
0x332e4  ldloc.2
0x332e5  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ProgId::get_Id()
0x332ea  ldarg.3
0x332eb  ldnull
0x332ec  ldc.i4.0
0x332ed  call     string Microsoft.VisualStudio.Setup.Extensions::ReplaceVariables(string value, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties, [opt] class [System]System.Collections.Generic.ISet`1<string> variablesToIgnore, [opt] bool recursive)
0x332f2  stloc.3
0x332f3  ldarg.0
0x332f4  ldloc.3
0x332f5  ldarg.s  4
0x332f7  call     instance bool Microsoft.VisualStudio.Setup.Installer.VsixInstaller::ValidateProgId(string progId, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x332fc  brfalse  loc_335C1
0x33301  ldarg.s  4
0x33303  ldstr    aInstallingProg// "Installing ProgId: {0}"
0x33308  ldc.i4.1
0x33309  newarr   [mscorlib]System.Object
0x3330e  dup
0x3330f  ldc.i4.0
0x33310  ldloc.3
0x33311  stelem.ref
0x33312  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x33317  ldloc.0
0x33318  ldloc.3
0x33319  ldc.i4.0
0x3331a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::CreateSubKey(string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryOptions)
0x3331f  stloc.s  4
0x33321  ldloc.2
0x33322  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ProgId::get_DisplayName()
0x33327  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x3332c  brtrue.s loc_3333D
0x3332e  ldloc.s  4
0x33330  ldnull
0x33331  ldloc.2
0x33332  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ProgId::get_DisplayName()
0x33337  ldc.i4.1
0x33338  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x3333d  ldloc.2
0x3333e  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ProgId::get_AlwaysShowExtension()
0x33343  brfalse.s loc_33357
0x33345  ldloc.s  4
0x33347  ldstr    aAlwaysshowext// "AlwaysShowExt"
0x3334c  ldstr    a1// "1"
0x33351  ldc.i4.1
0x33352  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x33357  ldloc.2
0x33358  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ProgId::get_AppUserModelId()
0x3335d  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x33362  brtrue.s loc_33383
0x33364  ldloc.2
0x33365  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ProgId::get_AppUserModelId()
0x3336a  ldarg.3
0x3336b  ldnull
0x3336c  ldc.i4.0
0x3336d  call     string Microsoft.VisualStudio.Setup.Extensions::ReplaceVariables(string value, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties, [opt] class [System]System.Collections.Generic.ISet`1<string> variablesToIgnore, [opt] bool recursive)
0x33372  stloc.s  5
0x33374  ldloc.s  4
0x33376  ldstr    aAppusermodelid// "AppUserModelID"
0x3337b  ldloc.s  5
0x3337d  ldc.i4.1
0x3337e  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x33383  ldloc.2
0x33384  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ProgId::get_AllowSilentDefaultTakeOver()
0x33389  brfalse.s loc_3339D
0x3338b  ldloc.s  4
0x3338d  ldstr    aAllowsilentdef// "AllowSilentDefaultTakeOver"
0x33392  ldsfld   string [mscorlib]System.String::Empty
0x33397  ldc.i4.1
0x33398  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x3339d  ldloc.2
0x3339e  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ProgId::get_DefaultIconPath()
0x333a3  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x333a8  brtrue.s loc_33413
0x333aa  ldloc.s  4
0x333ac  ldstr    aDefaulticon// "DefaultIcon"
0x333b1  ldc.i4.0
0x333b2  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::CreateSubKey(string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryOptions)
0x333b7  stloc.s  6
0x333b9  ldloc.2
0x333ba  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ProgId::get_DefaultIconPath()
0x333bf  ldarg.3
0x333c0  ldnull
0x333c1  ldc.i4.0
0x333c2  call     string Microsoft.VisualStudio.Setup.Extensions::ReplaceVariables(string value, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties, [opt] class [System]System.Collections.Generic.ISet`1<string> variablesToIgnore, [opt] bool recursive)
0x333c7  stloc.s  7
0x333c9  ldloc.2
0x333ca  callvirt instance int32 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ProgId::get_DefaultIconPosition()
0x333cf  ldc.i4   0x80000000
0x333d4  bne.un.s loc_333DC
0x333d6  ldloc.s  7
0x333d8  stloc.s  8
0x333da  br.s     loc_333FA
0x333dc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x333e1  ldstr    a01_6// "\"{0}\",{1}"
0x333e6  ldloc.s  7
0x333e8  ldloc.2
0x333e9  callvirt instance int32 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ProgId::get_DefaultIconPosition()
0x333ee  box      [mscorlib]System.Int32
0x333f3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x333f8  stloc.s  8
0x333fa  ldloc.s  6
0x333fc  ldnull
0x333fd  ldloc.s  8
0x333ff  ldc.i4.1
0x33400  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x33405  leave.s  loc_33413
0x33407  ldloc.s  6
0x33409  brfalse.s loc_33412
0x3340b  ldloc.s  6
0x3340d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33412  endfinally
0x33413  ldloc.2
0x33414  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ProgId::get_Path()
0x33419  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x3341e  brtrue   loc_334A9
0x33423  ldloc.s  4
0x33425  ldstr    aShellOpenComma// "shell\\Open\\Command"
0x3342a  ldc.i4.0
0x3342b  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::CreateSubKey(string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryOptions)
0x33430  stloc.s  9
0x33432  ldloc.2
0x33433  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ProgId::get_Path()
0x33438  ldarg.3
0x33439  ldnull
0x3343a  ldc.i4.0
0x3343b  call     string Microsoft.VisualStudio.Setup.Extensions::ReplaceVariables(string value, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties, [opt] class [System]System.Collections.Generic.ISet`1<string> variablesToIgnore, [opt] bool recursive)
0x33440  stloc.s  0xA
0x33442  ldloc.2
0x33443  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ProgId::get_Dde()
0x33448  brtrue.s loc_33451
0x3344a  ldstr    a011// "\"{0}\" {1}\"%1\""
0x3344f  br.s     loc_33456
0x33451  ldstr    a0Dde// "\"{0}\" /dde"
0x33456  stloc.s  0xB
0x33458  ldloc.2
0x33459  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ProgId::get_Arguments()
0x3345e  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x33463  brtrue.s loc_33477
0x33465  ldloc.2
0x33466  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ProgId::get_Arguments()
0x3346b  ldstr    asc_853DA// " "
0x33470  call     string [mscorlib]System.String::Concat(string, string)
0x33475  br.s     loc_3347C
0x33477  ldsfld   string [mscorlib]System.String::Empty
0x3347c  stloc.s  0xC
0x3347e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x33483  ldloc.s  0xB
0x33485  ldloc.s  0xA
0x33487  ldloc.s  0xC
0x33489  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x3348e  stloc.s  0xD
0x33490  ldloc.s  9
0x33492  ldnull
0x33493  ldloc.s  0xD
0x33495  ldc.i4.1
0x33496  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x3349b  leave.s  loc_334A9
0x3349d  ldloc.s  9
0x3349f  brfalse.s loc_334A8
0x334a1  ldloc.s  9
0x334a3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x334a8  endfinally
0x334a9  ldloc.2
0x334aa  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ProgId::get_Dde()
0x334af  brfalse  loc_33541
0x334b4  ldloc.s  4
0x334b6  ldstr    aShellOpenDdeex// "shell\\Open\\ddeexec"
0x334bb  ldc.i4.0
0x334bc  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::CreateSubKey(string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryOptions)
0x334c1  stloc.s  0xE
0x334c3  ldloc.s  0xE
0x334c5  ldnull
0x334c6  ldstr    aOpen1// "Open(\"%1\")"
0x334cb  ldc.i4.1
0x334cc  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x334d1  ldloc.s  0xE
0x334d3  ldstr    aApplication// "Application"
0x334d8  ldc.i4.0
0x334d9  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::CreateSubKey(string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryOptions)
0x334de  stloc.s  0xF
0x334e0  ldloc.2
0x334e1  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ProgId::get_DdeApplication()
0x334e6  ldarg.3
0x334e7  ldnull
0x334e8  ldc.i4.0
0x334e9  call     string Microsoft.VisualStudio.Setup.Extensions::ReplaceVariables(string value, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties, [opt] class [System]System.Collections.Generic.ISet`1<string> variablesToIgnore, [opt] bool recursive)
0x334ee  stloc.s  0x10
0x334f0  ldloc.s  0xF
0x334f2  ldnull
0x334f3  ldloc.s  0x10
0x334f5  ldc.i4.1
0x334f6  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x334fb  leave.s  loc_33509
0x334fd  ldloc.s  0xF
0x334ff  brfalse.s loc_33508
0x33501  ldloc.s  0xF
0x33503  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33508  endfinally
0x33509  ldloc.s  0xE
0x3350b  ldstr    aTopic// "Topic"
0x33510  ldc.i4.0
0x33511  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::CreateSubKey(string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryOptions)
0x33516  stloc.s  0x11
0x33518  ldloc.s  0x11
0x3351a  ldnull
0x3351b  ldloc.2
0x3351c  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ProgId::get_DdeTopic()
0x33521  ldc.i4.1
0x33522  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x33527  leave.s  loc_33541
0x33529  ldloc.s  0x11
0x3352b  brfalse.s loc_33534
0x3352d  ldloc.s  0x11
0x3352f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33534  endfinally
0x33535  ldloc.s  0xE
0x33537  brfalse.s loc_33540
0x33539  ldloc.s  0xE
0x3353b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33540  endfinally
0x33541  ldloc.2
0x33542  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ProgId::get_IconHandler()
0x33547  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x3354c  brtrue.s loc_3357A
0x3354e  ldloc.s  4
0x33550  ldstr    aShellexIconhan// "ShellEx\\IconHandler"
0x33555  ldc.i4.0
0x33556  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::CreateSubKey(string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryOptions)
0x3355b  stloc.s  0x12
0x3355d  ldloc.s  0x12
0x3355f  ldnull
0x33560  ldloc.2
0x33561  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ProgId::get_IconHandler()
0x33566  ldc.i4.1
0x33567  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x3356c  leave.s  loc_3357A
0x3356e  ldloc.s  0x12
0x33570  brfalse.s loc_33579
0x33572  ldloc.s  0x12
0x33574  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33579  endfinally
0x3357a  ldloc.2
0x3357b  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ProgId::get_Clsid()
0x33580  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x33585  brtrue.s loc_335B3
0x33587  ldloc.s  4
0x33589  ldstr    aClsid// "CLSID"
0x3358e  ldc.i4.0
0x3358f  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::CreateSubKey(string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryOptions)
0x33594  stloc.s  0x13
0x33596  ldloc.s  0x13
0x33598  ldnull
0x33599  ldloc.2
0x3359a  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ProgId::get_Clsid()
0x3359f  ldc.i4.1
0x335a0  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x335a5  leave.s  loc_335C1
0x335a7  ldloc.s  0x13
0x335a9  brfalse.s loc_335B2
0x335ab  ldloc.s  0x13
0x335ad  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x335b2  endfinally
0x335b3  leave.s  loc_335C1
0x335b5  ldloc.s  4
0x335b7  brfalse.s loc_335C0
0x335b9  ldloc.s  4
0x335bb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x335c0  endfinally
0x335c1  ldloc.1
0x335c2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x335c7  brtrue   loc_332BA
0x335cc  leave.s  loc_335E2
0x335ce  ldloc.1
0x335cf  brfalse.s loc_335D7
0x335d1  ldloc.1
0x335d2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x335d7  endfinally
0x335d8  ldloc.0
0x335d9  brfalse.s loc_335E1
  ... truncated ...
```
