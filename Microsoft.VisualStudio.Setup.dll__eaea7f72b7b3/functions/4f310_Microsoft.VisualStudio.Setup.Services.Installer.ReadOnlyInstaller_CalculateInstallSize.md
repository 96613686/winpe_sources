# Microsoft.VisualStudio.Setup.Services.Installer.ReadOnlyInstaller::CalculateInstallSize

- ea: `0x4f310`
- end: `0x4f37f`
- name: `Microsoft.VisualStudio.Setup.Services.Installer.ReadOnlyInstaller::CalculateInstallSize`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0xddf0`
- `0x1cbe0`
- `0x1cda0`
- `0x4f310`

## string_xrefs

- `0x4f350`: `InstallDir`
- `0x4f35e`: `SharedInstallDrive`
- `0x4f31c`: `installPath`

## pseudocode

```c

```

## disassembly

```asm
0x4f310  ldarg.1
0x4f311  ldstr    aGraph// "graph"
0x4f316  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x4f31b  ldarg.2
0x4f31c  ldstr    aInstallpath// "installPath"
0x4f321  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x4f326  ldarg.1
0x4f327  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSize [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyGraph::GetInstallSize()
0x4f32c  stloc.0
0x4f32d  ldarg.s  4
0x4f32f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4f334  brtrue.s loc_4F33F
0x4f336  ldarg.s  4
0x4f338  call     string [mscorlib]System.IO.Path::GetPathRoot(string)
0x4f33d  br.s     loc_4F340
0x4f33f  ldnull
0x4f340  stloc.1
0x4f341  ldarg.s  5
0x4f343  dup
0x4f344  brtrue.s loc_4F34C
0x4f346  pop
0x4f347  newobj   instance void Microsoft.VisualStudio.Setup.VariableCollection::.ctor()
0x4f34c  starg.s  5
0x4f34e  ldarg.s  5
0x4f350  ldstr    aInstalldir// "InstallDir"
0x4f355  ldarg.2
0x4f356  ldc.i4.0
0x4f357  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, string value, [opt] bool persist)
0x4f35c  ldarg.s  5
0x4f35e  ldstr    aSharedinstalld_0// "SharedInstallDrive"
0x4f363  ldloc.1
0x4f364  ldc.i4.0
0x4f365  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, string value, [opt] bool persist)
0x4f36a  ldarg.0
0x4f36b  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.ReadOnlyInstallerServiceOptions Microsoft.VisualStudio.Setup.Services.Installer.ReadOnlyInstaller::serviceOptions
0x4f370  ldloc.0
0x4f371  ldarg.2
0x4f372  ldarg.s  5
0x4f374  ldarg.3
0x4f375  ldarg.s  4
0x4f377  ldc.i4.0
0x4f378  conv.i8
0x4f379  newobj   instance void Microsoft.VisualStudio.Setup.EvaluatedInstallSizes::.ctor(class [mscorlib]System.IServiceProvider services, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSize size, string targetInstallDirectory, class Microsoft.VisualStudio.Setup.VariableCollection properties, [opt] string cachePath, [opt] string sharedPath, [opt] int64 additionalBuffer)
0x4f37e  ret
```
