# Microsoft.VisualStudio.Setup.Installer.VsixInstaller::InstallUrlAssociations

- ea: `0x339a0`
- end: `0x33b06`
- name: `Microsoft.VisualStudio.Setup.Installer.VsixInstaller::InstallUrlAssociations`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x331c0`

## callees

- `0xf0e0`
- `0x339a0`

## string_xrefs

- `0x33a9c`: `RegistrationPath: {0}`
- `0x339e1`: `Cannot process incomplete URL protocol definition for install`
- `0x339f7`: `Installing URL protocol '{0}'`
- `0x33a48`: `URL Protocol`

## pseudocode

```c

```

## disassembly

```asm
0x339a0  ldarg.1
0x339a1  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.UrlAssociation> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage::get_UrlAssociations()
0x339a6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.UrlAssociation>::GetEnumerator()
0x339ab  stloc.0
0x339ac  br       loc_33AEE
0x339b1  ldloc.0
0x339b2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.UrlAssociation>::get_Current()
0x339b7  stloc.1
0x339b8  ldloc.1
0x339b9  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.UrlAssociation::get_Protocol()
0x339be  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x339c3  brtrue.s loc_339DF
0x339c5  ldloc.1
0x339c6  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.UrlAssociation::get_ProgId()
0x339cb  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x339d0  brtrue.s loc_339DF
0x339d2  ldloc.1
0x339d3  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.UrlAssociation::get_DefaultProgramRegistrationPath()
0x339d8  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x339dd  brfalse.s loc_339F5
0x339df  ldarg.s  4
0x339e1  ldstr    aCannotProcessI// "Cannot process incomplete URL protocol "...
0x339e6  call     T0x2B000003
0x339eb  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x339f0  br       loc_33AEE
0x339f5  ldarg.s  4
0x339f7  ldstr    aInstallingUrlP// "Installing URL protocol '{0}'"
0x339fc  ldc.i4.1
0x339fd  newarr   [mscorlib]System.Object
0x33a02  dup
0x33a03  ldc.i4.0
0x33a04  ldloc.1
0x33a05  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.UrlAssociation::get_Protocol()
0x33a0a  stelem.ref
0x33a0b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x33a10  ldarg.2
0x33a11  ldc.i4.1
0x33a12  ldc.i4.0
0x33a13  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry::OpenBaseKey(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryHive, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryView)
0x33a18  stloc.s  4
0x33a1a  ldloc.s  4
0x33a1c  ldloc.1
0x33a1d  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.UrlAssociation::get_Protocol()
0x33a22  ldc.i4.0
0x33a23  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::CreateSubKey(string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryOptions)
0x33a28  stloc.s  5
0x33a2a  ldloc.1
0x33a2b  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.UrlAssociation::get_DisplayName()
0x33a30  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x33a35  brtrue.s loc_33A46
0x33a37  ldloc.s  5
0x33a39  ldnull
0x33a3a  ldloc.1
0x33a3b  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.UrlAssociation::get_DisplayName()
0x33a40  ldc.i4.1
0x33a41  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x33a46  ldloc.s  5
0x33a48  ldstr    aUrlProtocol// "URL Protocol"
0x33a4d  ldsfld   string [mscorlib]System.String::Empty
0x33a52  ldc.i4.1
0x33a53  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x33a58  leave.s  loc_33A72
0x33a5a  ldloc.s  5
0x33a5c  brfalse.s loc_33A65
0x33a5e  ldloc.s  5
0x33a60  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33a65  endfinally
0x33a66  ldloc.s  4
0x33a68  brfalse.s loc_33A71
0x33a6a  ldloc.s  4
0x33a6c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33a71  endfinally
0x33a72  ldloc.1
0x33a73  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.UrlAssociation::get_ProgId()
0x33a78  ldarg.3
0x33a79  ldnull
0x33a7a  ldc.i4.0
0x33a7b  call     string Microsoft.VisualStudio.Setup.Extensions::ReplaceVariables(string value, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties, [opt] class [System]System.Collections.Generic.ISet`1<string> variablesToIgnore, [opt] bool recursive)
0x33a80  stloc.2
0x33a81  ldloc.1
0x33a82  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.UrlAssociation::get_DefaultProgramRegistrationPath()
0x33a87  ldarg.3
0x33a88  ldnull
0x33a89  ldc.i4.0
0x33a8a  call     string Microsoft.VisualStudio.Setup.Extensions::ReplaceVariables(string value, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties, [opt] class [System]System.Collections.Generic.ISet`1<string> variablesToIgnore, [opt] bool recursive)
0x33a8f  ldsfld   string Microsoft.VisualStudio.Setup.Installer.VsixInstaller::urlAssociationName
0x33a94  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x33a99  stloc.3
0x33a9a  ldarg.s  4
0x33a9c  ldstr    aRegistrationpa// "RegistrationPath: {0}"
0x33aa1  ldc.i4.1
0x33aa2  newarr   [mscorlib]System.Object
0x33aa7  dup
0x33aa8  ldc.i4.0
0x33aa9  ldloc.3
0x33aaa  stelem.ref
0x33aab  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x33ab0  ldarg.2
0x33ab1  ldc.i4.2
0x33ab2  ldc.i4.1
0x33ab3  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry::OpenBaseKey(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryHive, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryView)
0x33ab8  stloc.s  6
0x33aba  ldloc.s  6
0x33abc  ldloc.3
0x33abd  ldc.i4.0
0x33abe  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::CreateSubKey(string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryOptions)
0x33ac3  stloc.s  7
0x33ac5  ldloc.s  7
0x33ac7  ldloc.1
0x33ac8  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.UrlAssociation::get_Protocol()
0x33acd  ldloc.2
0x33ace  ldc.i4.1
0x33acf  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x33ad4  leave.s  loc_33AEE
0x33ad6  ldloc.s  7
0x33ad8  brfalse.s loc_33AE1
0x33ada  ldloc.s  7
0x33adc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33ae1  endfinally
0x33ae2  ldloc.s  6
0x33ae4  brfalse.s loc_33AED
0x33ae6  ldloc.s  6
0x33ae8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33aed  endfinally
0x33aee  ldloc.0
0x33aef  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x33af4  brtrue   loc_339B1
0x33af9  leave.s  loc_33B05
0x33afb  ldloc.0
0x33afc  brfalse.s loc_33B04
0x33afe  ldloc.0
0x33aff  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33b04  endfinally
0x33b05  ret
```
