# Microsoft.VisualStudio.Setup.Installer.VsixInstaller::InstallFileAssociations

- ea: `0x33680`
- end: `0x33833`
- name: `Microsoft.VisualStudio.Setup.Installer.VsixInstaller::InstallFileAssociations`
- size: `435`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x331c0`

## callees

- `0xf0e0`
- `0x33680`

## string_xrefs

- `0x336b4`: `Cannot process empty extension for install`
- `0x336ca`: `Processing file extension for install {0}`
- `0x3375d`: `OpenWithProgids`
- `0x337b0`: `RegistrationPath: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x33680  ldarg.1
0x33681  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAssociation> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage::get_FileAssociations()
0x33686  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAssociation>::GetEnumerator()
0x3368b  stloc.0
0x3368c  br       loc_3381B
0x33691  ldloc.0
0x33692  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAssociation>::get_Current()
0x33697  stloc.1
0x33698  ldloc.1
0x33699  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAssociation::get_Extension()
0x3369e  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x336a3  brtrue.s loc_336B2
0x336a5  ldloc.1
0x336a6  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAssociation::get_ProgId()
0x336ab  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x336b0  brfalse.s loc_336C8
0x336b2  ldarg.s  4
0x336b4  ldstr    aCannotProcessE_1// "Cannot process empty extension for inst"...
0x336b9  call     T0x2B000003
0x336be  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x336c3  br       loc_3381B
0x336c8  ldarg.s  4
0x336ca  ldstr    aProcessingFile_0// "Processing file extension for install {"...
0x336cf  ldc.i4.1
0x336d0  newarr   [mscorlib]System.Object
0x336d5  dup
0x336d6  ldc.i4.0
0x336d7  ldloc.1
0x336d8  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAssociation::get_Extension()
0x336dd  stelem.ref
0x336de  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x336e3  ldarg.2
0x336e4  ldc.i4.1
0x336e5  ldc.i4.0
0x336e6  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry::OpenBaseKey(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryHive, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryView)
0x336eb  stloc.2
0x336ec  ldloc.2
0x336ed  ldloc.1
0x336ee  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAssociation::get_Extension()
0x336f3  ldc.i4.0
0x336f4  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::CreateSubKey(string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryOptions)
0x336f9  stloc.3
0x336fa  ldloc.1
0x336fb  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAssociation::get_ContentType()
0x33700  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x33705  brtrue.s loc_33719
0x33707  ldloc.3
0x33708  ldstr    aContentType// "Content Type"
0x3370d  ldloc.1
0x3370e  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAssociation::get_ContentType()
0x33713  ldc.i4.1
0x33714  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x33719  ldloc.1
0x3371a  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAssociation::get_PerceivedType()
0x3371f  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x33724  brtrue.s loc_33738
0x33726  ldloc.3
0x33727  ldstr    aPerceivedtype// "PerceivedType"
0x3372c  ldloc.1
0x3372d  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAssociation::get_PerceivedType()
0x33732  ldc.i4.1
0x33733  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x33738  ldloc.1
0x33739  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAssociation::get_ProgId()
0x3373e  ldarg.3
0x3373f  ldnull
0x33740  ldc.i4.0
0x33741  call     string Microsoft.VisualStudio.Setup.Extensions::ReplaceVariables(string value, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties, [opt] class [System]System.Collections.Generic.ISet`1<string> variablesToIgnore, [opt] bool recursive)
0x33746  stloc.s  4
0x33748  ldloc.1
0x33749  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAssociation::get_IsIconOnly()
0x3374e  brfalse.s loc_3375C
0x33750  ldloc.3
0x33751  ldnull
0x33752  ldloc.s  4
0x33754  ldc.i4.1
0x33755  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x3375a  br.s     loc_33787
0x3375c  ldloc.3
0x3375d  ldstr    aOpenwithprogid// "OpenWithProgids"
0x33762  ldc.i4.0
0x33763  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::CreateSubKey(string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryOptions)
0x33768  stloc.s  5
0x3376a  ldloc.s  5
0x3376c  ldloc.s  4
0x3376e  ldsfld   string [mscorlib]System.String::Empty
0x33773  ldc.i4.1
0x33774  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x33779  leave.s  loc_33787
0x3377b  ldloc.s  5
0x3377d  brfalse.s loc_33786
0x3377f  ldloc.s  5
0x33781  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33786  endfinally
0x33787  ldloc.1
0x33788  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAssociation::get_DefaultProgramRegistrationPath()
0x3378d  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x33792  brtrue.s loc_33805
0x33794  ldloc.1
0x33795  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAssociation::get_DefaultProgramRegistrationPath()
0x3379a  ldarg.3
0x3379b  ldnull
0x3379c  ldc.i4.0
0x3379d  call     string Microsoft.VisualStudio.Setup.Extensions::ReplaceVariables(string value, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties, [opt] class [System]System.Collections.Generic.ISet`1<string> variablesToIgnore, [opt] bool recursive)
0x337a2  ldsfld   string Microsoft.VisualStudio.Setup.Installer.VsixInstaller::fileAssociationName
0x337a7  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x337ac  stloc.s  6
0x337ae  ldarg.s  4
0x337b0  ldstr    aRegistrationpa// "RegistrationPath: {0}"
0x337b5  ldc.i4.1
0x337b6  newarr   [mscorlib]System.Object
0x337bb  dup
0x337bc  ldc.i4.0
0x337bd  ldloc.s  6
0x337bf  stelem.ref
0x337c0  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x337c5  ldarg.2
0x337c6  ldc.i4.2
0x337c7  ldc.i4.1
0x337c8  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry::OpenBaseKey(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryHive, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryView)
0x337cd  stloc.s  7
0x337cf  ldloc.s  7
0x337d1  ldloc.s  6
0x337d3  ldc.i4.0
0x337d4  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::CreateSubKey(string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryOptions)
0x337d9  stloc.s  8
0x337db  ldloc.s  8
0x337dd  ldloc.1
0x337de  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAssociation::get_Extension()
0x337e3  ldloc.s  4
0x337e5  ldc.i4.1
0x337e6  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x337eb  leave.s  loc_3381B
0x337ed  ldloc.s  8
0x337ef  brfalse.s loc_337F8
0x337f1  ldloc.s  8
0x337f3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x337f8  endfinally
0x337f9  ldloc.s  7
0x337fb  brfalse.s loc_33804
0x337fd  ldloc.s  7
0x337ff  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33804  endfinally
0x33805  leave.s  loc_3381B
0x33807  ldloc.3
0x33808  brfalse.s loc_33810
0x3380a  ldloc.3
0x3380b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33810  endfinally
0x33811  ldloc.2
0x33812  brfalse.s loc_3381A
0x33814  ldloc.2
0x33815  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3381a  endfinally
0x3381b  ldloc.0
0x3381c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x33821  brtrue   loc_33691
0x33826  leave.s  loc_33832
0x33828  ldloc.0
0x33829  brfalse.s loc_33831
0x3382b  ldloc.0
0x3382c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33831  endfinally
0x33832  ret
```
