# Microsoft.VisualStudio.Setup.Installer.ExeInstaller::RunCommands

- ea: `0x2a530`
- end: `0x2a9dc`
- name: `Microsoft.VisualStudio.Setup.Installer.ExeInstaller::RunCommands`
- size: `1196`
- prototype: ``
- caller_count: `4`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callers

- `0x6c480`
- `0x6c4f0`
- `0x6c560`
- `0x6c5e0`

## callees

- `0xf0e0`
- `0x11d40`
- `0x11dd0`
- `0x11df0`
- `0x11e30`
- `0x11e50`
- `0x2a470`
- `0x2a490`
- `0x2a530`
- `0x2aa70`
- `0x2aa90`
- `0x2aba0`
- `0x2ac20`
- `0x2b720`
- `0x2b920`
- `0x2b940`
- `0x2b9e0`
- `0x2ba70`
- `0x2bb70`
- `0x3ce50`
- `0x3cea0`

## string_xrefs

- `0x2a6dc`: ` commands so skipping it.`
- `0x2a76f`: `[ResponseFilePath]`

## pseudocode

```c

```

## disassembly

```asm
0x2a530  ldarg.s  5
0x2a532  ldnull
0x2a533  stind.ref
0x2a534  ldarg.s  6
0x2a536  ldnull
0x2a537  stind.ref
0x2a538  ldarg.s  7
0x2a53a  ldnull
0x2a53b  stind.ref
0x2a53c  ldarg.0
0x2a53d  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_Services()
0x2a542  dup
0x2a543  brtrue.s loc_2A549
0x2a545  pop
0x2a546  ldnull
0x2a547  br.s     loc_2A54F
0x2a549  ldc.i4.0
0x2a54a  call     T0x2B00000C
0x2a54f  dup
0x2a550  brtrue.s loc_2A558
0x2a552  pop
0x2a553  ldsfld   class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Services.FileSystem::Default
0x2a558  stloc.0
0x2a559  ldarg.1
0x2a55a  brtrue.s loc_2A55F
0x2a55c  ldnull
0x2a55d  br.s     loc_2A565
0x2a55f  ldarg.1
0x2a560  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CommandParameter::get_FileName()
0x2a565  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2a56a  brtrue.s loc_2A589
0x2a56c  ldarg.1
0x2a56d  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CommandParameter::get_FileName()
0x2a572  call     valuetype [System.Memory]System.ReadOnlySpan`1<char> [System.Memory]System.MemoryExtensions::AsSpan(string)
0x2a577  ldsfld   string Microsoft.VisualStudio.Setup.Installer.ExeInstaller::FirstPayloadAlias
0x2a57c  call     valuetype [System.Memory]System.ReadOnlySpan`1<char> [System.Memory]System.MemoryExtensions::AsSpan(string)
0x2a581  ldc.i4.5
0x2a582  call     bool [System.Memory]System.MemoryExtensions::Contains(valuetype [System.Memory]System.ReadOnlySpan`1<char>, valuetype [System.Memory]System.ReadOnlySpan`1<char>, valuetype [mscorlib]System.StringComparison)
0x2a587  br.s     loc_2A58A
0x2a589  ldc.i4.1
0x2a58a  stloc.1
0x2a58b  ldc.i4.1
0x2a58c  stloc.2
0x2a58d  ldarg.0
0x2a58e  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.VisualStudio.Setup.Installer.InstallerBase::GetProperties()
0x2a593  stloc.3
0x2a594  ldarg.3
0x2a595  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2a59a  brtrue.s loc_2A5B4
0x2a59c  ldloc.3
0x2a59d  ldstr    aPayload// "[payload]"
0x2a5a2  ldarg.3
0x2a5a3  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0x2a5a8  ldloc.3
0x2a5a9  ldstr    aPackagedir// "[packageDir]"
0x2a5ae  ldarg.3
0x2a5af  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0x2a5b4  ldarg.s  4
0x2a5b6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2a5bb  brtrue.s loc_2A5CA
0x2a5bd  ldloc.3
0x2a5be  ldstr    aLogfile_0// "[logfile]"
0x2a5c3  ldarg.s  4
0x2a5c5  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0x2a5ca  ldarg.0
0x2a5cb  ldarg.2
0x2a5cc  call     instance string Microsoft.VisualStudio.Setup.Installer.ExeInstaller::GetPackageLayoutDir(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package pkg)
0x2a5d1  stloc.s  4
0x2a5d3  ldloc.s  4
0x2a5d5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2a5da  brtrue.s loc_2A5E9
0x2a5dc  ldloc.3
0x2a5dd  ldstr    aPackagelayoutd// "[PackageLayoutDir]"
0x2a5e2  ldloc.s  4
0x2a5e4  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0x2a5e9  ldarg.0
0x2a5ea  ldarg.2
0x2a5eb  call     instance string Microsoft.VisualStudio.Setup.Installer.ExeInstaller::GetPackageOriginalSource(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package pkg)
0x2a5f0  stloc.s  5
0x2a5f2  ldloc.s  5
0x2a5f4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2a5f9  brtrue.s loc_2A608
0x2a5fb  ldloc.3
0x2a5fc  ldstr    aPackageorigina// "[PackageOriginalSource]"
0x2a601  ldloc.s  5
0x2a603  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0x2a608  ldarg.s  9
0x2a60a  brfalse.s loc_2A64B
0x2a60c  ldarg.s  9
0x2a60e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::GetEnumerator()
0x2a613  stloc.s  0xB
0x2a615  br.s     loc_2A634
0x2a617  ldloc.s  0xB
0x2a619  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Current()
0x2a61e  stloc.s  0xC
0x2a620  ldloc.3
0x2a621  ldloca.s 0xC
0x2a623  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x2a628  ldloca.s 0xC
0x2a62a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x2a62f  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0x2a634  ldloc.s  0xB
0x2a636  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2a63b  brtrue.s loc_2A617
0x2a63d  leave.s  loc_2A64B
0x2a63f  ldloc.s  0xB
0x2a641  brfalse.s loc_2A64A
0x2a643  ldloc.s  0xB
0x2a645  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a64a  endfinally
0x2a64b  ldarg.0
0x2a64c  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2a651  stloc.s  6
0x2a653  ldarg.2
0x2a654  isinst   [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage
0x2a659  stloc.s  7
0x2a65b  ldnull
0x2a65c  stloc.s  8
0x2a65e  ldnull
0x2a65f  stloc.s  9
0x2a661  ldarg.1
0x2a662  brtrue.s loc_2A667
0x2a664  ldnull
0x2a665  br.s     loc_2A66D
0x2a667  ldarg.1
0x2a668  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CommandParameter::get_FileName()
0x2a66d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2a672  brtrue.s loc_2A68F
0x2a674  ldarg.0
0x2a675  ldarg.1
0x2a676  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CommandParameter::get_FileName()
0x2a67b  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x2a680  ldloc.3
0x2a681  ldnull
0x2a682  ldc.i4.0
0x2a683  call     string Microsoft.VisualStudio.Setup.Extensions::ReplaceVariables(string value, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties, [opt] class [System]System.Collections.Generic.ISet`1<string> variablesToIgnore, [opt] bool recursive)
0x2a688  stfld    string Microsoft.VisualStudio.Setup.Installer.ExeInstaller::fileName
0x2a68d  br.s     loc_2A6F3
0x2a68f  ldloc.s  7
0x2a691  brfalse.s loc_2A6B0
0x2a693  ldloc.s  6
0x2a695  ldnull
0x2a696  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CommonResources::get_EmptyFilePath()
0x2a69b  call     T0x2B000003
0x2a6a0  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x2a6a5  ldarg.s  5
0x2a6a7  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CommonResources::get_EmptyFilePath()
0x2a6ac  stind.ref
0x2a6ad  ldc.i4.s 0x57
0x2a6af  ret
0x2a6b0  ldarg.0
0x2a6b1  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2a6b6  ldc.i4.5
0x2a6b7  newarr   [mscorlib]System.String
0x2a6bc  dup
0x2a6bd  ldc.i4.0
0x2a6be  ldstr    aProduct_1// "Product "
0x2a6c3  stelem.ref
0x2a6c4  dup
0x2a6c5  ldc.i4.1
0x2a6c6  ldarg.2
0x2a6c7  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::GetUniqueId()
0x2a6cc  stelem.ref
0x2a6cd  dup
0x2a6ce  ldc.i4.2
0x2a6cf  ldstr    aDoesNotContain// " does not contain "
0x2a6d4  stelem.ref
0x2a6d5  dup
0x2a6d6  ldc.i4.3
0x2a6d7  ldarg.s  8
0x2a6d9  stelem.ref
0x2a6da  dup
0x2a6db  ldc.i4.4
0x2a6dc  ldstr    aCommandsSoSkip// " commands so skipping it."
0x2a6e1  stelem.ref
0x2a6e2  call     string [mscorlib]System.String::Concat(string[])
0x2a6e7  call     T0x2B000003
0x2a6ec  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2a6f1  ldc.i4.0
0x2a6f2  ret
0x2a6f3  ldarg.1
0x2a6f4  brtrue.s loc_2A6F9
0x2a6f6  ldnull
0x2a6f7  br.s     loc_2A6FF
0x2a6f9  ldarg.1
0x2a6fa  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CommandParameter::get_Parameters()
0x2a6ff  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2a704  brtrue   loc_2A78B
0x2a709  ldarg.1
0x2a70a  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CommandParameter::get_Parameters()
0x2a70f  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x2a714  ldstr    aLogfile_0// "[logfile]"
0x2a719  callvirt instance bool [mscorlib]System.String::Contains(string)
0x2a71e  brfalse.s loc_2A722
0x2a720  ldc.i4.0
0x2a721  stloc.2
0x2a722  ldarg.0
0x2a723  ldfld    string Microsoft.VisualStudio.Setup.Installer.ExeInstaller::fileName
0x2a728  ldsfld   string Microsoft.VisualStudio.Setup.Installer.ExeInstaller::PowerShellFileName
0x2a72d  ldc.i4.5
0x2a72e  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x2a733  ldc.i4.0
0x2a734  clt
0x2a736  ldc.i4.0
0x2a737  ceq
0x2a739  stloc.s  0xD
0x2a73b  ldarg.1
0x2a73c  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CommandParameter::get_Parameters()
0x2a741  ldloc.3
0x2a742  ldloc.s  0xD
0x2a744  brtrue.s loc_2A749
0x2a746  ldnull
0x2a747  br.s     loc_2A74E
0x2a749  ldsfld   class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.Installer.ExeInstaller::PowerShellVariablesToIgnore
0x2a74e  ldc.i4.0
0x2a74f  call     string Microsoft.VisualStudio.Setup.Extensions::ReplaceVariables(string value, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties, [opt] class [System]System.Collections.Generic.ISet`1<string> variablesToIgnore, [opt] bool recursive)
0x2a754  stloc.s  8
0x2a756  ldarg.1
0x2a757  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CommandParameter::get_ResponseFileParameters()
0x2a75c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2a761  brtrue.s loc_2A78B
0x2a763  ldarg.0
0x2a764  ldloc.0
0x2a765  ldloc.s  8
0x2a767  call     instance string Microsoft.VisualStudio.Setup.Installer.ExeInstaller::WriteResponseFile(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string resolvedParameters)
0x2a76c  stloc.s  9
0x2a76e  ldloc.3
0x2a76f  ldstr    aResponsefilepa// "[ResponseFilePath]"
0x2a774  ldloc.s  9
0x2a776  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x2a77b  ldarg.1
0x2a77c  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CommandParameter::get_ResponseFileParameters()
0x2a781  ldloc.3
0x2a782  ldnull
0x2a783  ldc.i4.0
0x2a784  call     string Microsoft.VisualStudio.Setup.Extensions::ReplaceVariables(string value, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties, [opt] class [System]System.Collections.Generic.ISet`1<string> variablesToIgnore, [opt] bool recursive)
0x2a789  stloc.s  8
0x2a78b  ldnull
0x2a78c  stloc.s  0xA
0x2a78e  ldloc.s  7
0x2a790  brfalse.s loc_2A7EA
0x2a792  ldarg.0
0x2a793  ldarg.3
0x2a794  ldloc.s  7
0x2a796  ldloca.s 0xA
0x2a798  ldloc.1
0x2a799  call     instance bool Microsoft.VisualStudio.Setup.Installer.ExeInstaller::TryGetValidatedInstallerFilePathForExe(string localPath, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage pkg, [out] string& primaryPayloadPath, [opt] bool fallbackToFirstPayload)
0x2a79e  brtrue   loc_2A85F
0x2a7a3  ldloc.s  6
0x2a7a5  ldnull
0x2a7a6  ldarg.0
0x2a7a7  ldfld    string Microsoft.VisualStudio.Setup.Installer.ExeInstaller::fileName
0x2a7ac  ldstr    aCannotBeFound// " cannot be found."
0x2a7b1  call     string [mscorlib]System.String::Concat(string, string)
0x2a7b6  call     T0x2B000003
0x2a7bb  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x2a7c0  ldarg.0
0x2a7c1  ldnull
0x2a7c2  stfld    string Microsoft.VisualStudio.Setup.Installer.ExeInstaller::fileName
0x2a7c7  ldloc.s  6
0x2a7c9  ldnull
0x2a7ca  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CommonResources::get_InvalidInputPaths()
0x2a7cf  call     T0x2B000003
0x2a7d4  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x2a7d9  ldarg.s  5
0x2a7db  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CommonResources::get_InvalidInputPaths()
0x2a7e0  stind.ref
0x2a7e1  ldc.i4.s 0x57
0x2a7e3  stloc.s  0x13
0x2a7e5  leave    loc_2A9D9
0x2a7ea  ldarg.2
0x2a7eb  isinst   [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product
0x2a7f0  brfalse.s loc_2A85F
0x2a7f2  ldarg.0
0x2a7f3  ldfld    string Microsoft.VisualStudio.Setup.Installer.ExeInstaller::fileName
0x2a7f8  stloc.s  0xA
0x2a7fa  ldarg.0
0x2a7fb  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_FileSystem()
0x2a800  ldloc.s  0xA
0x2a802  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x2a807  brtrue.s loc_2A85F
0x2a809  ldarg.0
0x2a80a  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2a80f  ldc.i4.7
0x2a810  newarr   [mscorlib]System.String
0x2a815  dup
0x2a816  ldc.i4.0
0x2a817  ldstr    aProduct_1// "Product "
0x2a81c  stelem.ref
0x2a81d  dup
0x2a81e  ldc.i4.1
0x2a81f  ldarg.2
0x2a820  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::GetUniqueId()
0x2a825  stelem.ref
0x2a826  dup
0x2a827  ldc.i4.2
0x2a828  ldstr    asc_853DA// " "
0x2a82d  stelem.ref
0x2a82e  dup
0x2a82f  ldc.i4.3
  ... truncated ...
```
