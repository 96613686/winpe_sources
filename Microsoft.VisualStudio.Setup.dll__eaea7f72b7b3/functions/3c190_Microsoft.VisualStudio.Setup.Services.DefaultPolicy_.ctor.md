# Microsoft.VisualStudio.Setup.Services.DefaultPolicy::.ctor

- ea: `0x3c190`
- end: `0x3c22c`
- name: `Microsoft.VisualStudio.Setup.Services.DefaultPolicy::.ctor`
- size: `156`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0xa7a0`
- `0x131d0`
- `0x41910`

## callees

- `0x3c190`
- `0x3c2a0`

## string_xrefs

- `0x3c1fc`: `Compatibility`
- `0x3c21c`: `updates.config`

## pseudocode

```c

```

## disassembly

```asm
0x3c190  ldarg.0
0x3c191  call     instance void [mscorlib]System.Object::.ctor()
0x3c196  ldarg.1
0x3c197  brtrue.s loc_3C19C
0x3c199  ldnull
0x3c19a  br.s     loc_3C1A3
0x3c19c  ldarg.1
0x3c19d  ldc.i4.0
0x3c19e  call     T0x2B00000C
0x3c1a3  stloc.0
0x3c1a4  ldloc.0
0x3c1a5  brtrue.s loc_3C1AA
0x3c1a7  ldnull
0x3c1a8  br.s     loc_3C1B0
0x3c1aa  ldloc.0
0x3c1ab  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::get_SharedDirectory()
0x3c1b0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3c1b5  brtrue.s loc_3C22B
0x3c1b7  ldarg.0
0x3c1b8  ldloc.0
0x3c1b9  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::get_SharedDirectory()
0x3c1be  ldsfld   string Microsoft.VisualStudio.Setup.Cache.CacheRepository::DefaultSubdirectory
0x3c1c3  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x3c1c8  call     instance void Microsoft.VisualStudio.Setup.Services.DefaultPolicy::set_CachePath(string value)
0x3c1cd  ldloc.0
0x3c1ce  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::get_SharedProgramsDirectory()
0x3c1d3  brfalse.s loc_3C22B
0x3c1d5  ldarg.0
0x3c1d6  ldloc.0
0x3c1d7  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::get_SharedProgramsDirectory()
0x3c1dc  ldstr    aMicrosoftVisua_57// "Microsoft Visual Studio"
0x3c1e1  ldstr    aShared// "Shared"
0x3c1e6  call     string [mscorlib]System.IO.Path::Combine(string, string, string)
0x3c1eb  stfld    string Microsoft.VisualStudio.Setup.Services.DefaultPolicy::<SharedInstallationPath>k__BackingField
0x3c1f0  ldarg.0
0x3c1f1  ldloc.0
0x3c1f2  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::get_SharedProgramsDirectory()
0x3c1f7  ldstr    aMicrosoftVisua_57// "Microsoft Visual Studio"
0x3c1fc  ldstr    aCompatibility// "Compatibility"
0x3c201  call     string [mscorlib]System.IO.Path::Combine(string, string, string)
0x3c206  stfld    string Microsoft.VisualStudio.Setup.Services.DefaultPolicy::<CompatibilityInstallationPath>k__BackingField
0x3c20b  ldarg.0
0x3c20c  ldloc.0
0x3c20d  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::get_SharedDirectory()
0x3c212  ldstr    aMicrosoft// "Microsoft"
0x3c217  ldstr    aVisualstudio// "VisualStudio"
0x3c21c  ldstr    aUpdatesConfig// "updates.config"
0x3c221  call     string [mscorlib]System.IO.Path::Combine(string, string, string, string)
0x3c226  stfld    string Microsoft.VisualStudio.Setup.Services.DefaultPolicy::<UpdateConfigurationFile>k__BackingField
0x3c22b  ret
```
