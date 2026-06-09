# Microsoft.VisualStudio.Setup.Installer.VsixInstaller::UninstallFileAssociations

- ea: `0x33840`
- end: `0x33996`
- name: `Microsoft.VisualStudio.Setup.Installer.VsixInstaller::UninstallFileAssociations`
- size: `342`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x33230`

## callees

- `0xf0e0`
- `0x33840`

## string_xrefs

- `0x338c3`: `OpenWithProgids`
- `0x33925`: `RegistrationPath: {0}`
- `0x33874`: `Cannot process empty extension for uninstall`
- `0x3388a`: `Uninstalling file association: `

## pseudocode

```c

```

## disassembly

```asm
0x33840  ldarg.1
0x33841  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAssociation> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage::get_FileAssociations()
0x33846  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAssociation>::GetEnumerator()
0x3384b  stloc.0
0x3384c  br       loc_3397E
0x33851  ldloc.0
0x33852  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAssociation>::get_Current()
0x33857  stloc.1
0x33858  ldloc.1
0x33859  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAssociation::get_Extension()
0x3385e  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x33863  brtrue.s loc_33872
0x33865  ldloc.1
0x33866  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAssociation::get_ProgId()
0x3386b  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x33870  brfalse.s loc_33888
0x33872  ldarg.s  4
0x33874  ldstr    aCannotProcessE_2// "Cannot process empty extension for unin"...
0x33879  call     T0x2B000003
0x3387e  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x33883  br       loc_3397E
0x33888  ldarg.s  4
0x3388a  ldstr    aUninstallingFi// "Uninstalling file association: "
0x3388f  ldloc.1
0x33890  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAssociation::get_Extension()
0x33895  call     string [mscorlib]System.String::Concat(string, string)
0x3389a  call     T0x2B000003
0x3389f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x338a4  ldloc.1
0x338a5  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAssociation::get_ProgId()
0x338aa  ldarg.3
0x338ab  ldnull
0x338ac  ldc.i4.0
0x338ad  call     string Microsoft.VisualStudio.Setup.Extensions::ReplaceVariables(string value, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties, [opt] class [System]System.Collections.Generic.ISet`1<string> variablesToIgnore, [opt] bool recursive)
0x338b2  stloc.2
0x338b3  ldarg.2
0x338b4  ldc.i4.1
0x338b5  ldc.i4.0
0x338b6  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry::OpenBaseKey(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryHive, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryView)
0x338bb  stloc.3
0x338bc  ldloc.3
0x338bd  ldloc.1
0x338be  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAssociation::get_Extension()
0x338c3  ldstr    aOpenwithprogid// "OpenWithProgids"
0x338c8  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x338cd  ldc.i4.1
0x338ce  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::OpenSubKey(string, bool)
0x338d3  stloc.s  4
0x338d5  ldloc.s  4
0x338d7  brtrue.s loc_338DB
0x338d9  leave.s  loc_338FC
0x338db  ldloc.s  4
0x338dd  ldloc.2
0x338de  ldc.i4.0
0x338df  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::DeleteValue(string, bool)
0x338e4  leave.s  loc_338FC
0x338e6  ldloc.s  4
0x338e8  brfalse.s loc_338F1
0x338ea  ldloc.s  4
0x338ec  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x338f1  endfinally
0x338f2  ldloc.3
0x338f3  brfalse.s loc_338FB
0x338f5  ldloc.3
0x338f6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x338fb  endfinally
0x338fc  ldloc.1
0x338fd  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAssociation::get_DefaultProgramRegistrationPath()
0x33902  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x33907  brtrue.s loc_3397E
0x33909  ldloc.1
0x3390a  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAssociation::get_DefaultProgramRegistrationPath()
0x3390f  ldarg.3
0x33910  ldnull
0x33911  ldc.i4.0
0x33912  call     string Microsoft.VisualStudio.Setup.Extensions::ReplaceVariables(string value, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties, [opt] class [System]System.Collections.Generic.ISet`1<string> variablesToIgnore, [opt] bool recursive)
0x33917  ldsfld   string Microsoft.VisualStudio.Setup.Installer.VsixInstaller::fileAssociationName
0x3391c  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x33921  stloc.s  5
0x33923  ldarg.s  4
0x33925  ldstr    aRegistrationpa// "RegistrationPath: {0}"
0x3392a  ldc.i4.1
0x3392b  newarr   [mscorlib]System.Object
0x33930  dup
0x33931  ldc.i4.0
0x33932  ldloc.s  5
0x33934  stelem.ref
0x33935  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x3393a  ldarg.2
0x3393b  ldc.i4.2
0x3393c  ldc.i4.1
0x3393d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry::OpenBaseKey(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryHive, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryView)
0x33942  stloc.s  6
0x33944  ldloc.s  6
0x33946  ldloc.s  5
0x33948  ldc.i4.1
0x33949  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::OpenSubKey(string, bool)
0x3394e  stloc.s  7
0x33950  ldloc.s  7
0x33952  brtrue.s loc_33956
0x33954  leave.s  loc_3397E
0x33956  ldloc.s  7
0x33958  ldloc.1
0x33959  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAssociation::get_Extension()
0x3395e  ldc.i4.0
0x3395f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::DeleteValue(string, bool)
0x33964  leave.s  loc_3397E
0x33966  ldloc.s  7
0x33968  brfalse.s loc_33971
0x3396a  ldloc.s  7
0x3396c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33971  endfinally
0x33972  ldloc.s  6
0x33974  brfalse.s loc_3397D
0x33976  ldloc.s  6
0x33978  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3397d  endfinally
0x3397e  ldloc.0
0x3397f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x33984  brtrue   loc_33851
0x33989  leave.s  loc_33995
0x3398b  ldloc.0
0x3398c  brfalse.s loc_33994
0x3398e  ldloc.0
0x3398f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33994  endfinally
0x33995  ret
```
