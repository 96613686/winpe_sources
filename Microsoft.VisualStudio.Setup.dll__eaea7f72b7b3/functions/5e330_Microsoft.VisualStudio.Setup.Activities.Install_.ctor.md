# Microsoft.VisualStudio.Setup.Activities.Install::.ctor

- ea: `0x5e330`
- end: `0x5e4a0`
- name: `Microsoft.VisualStudio.Setup.Activities.Install::.ctor`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18890`

## callees

- `0x59720`
- `0x5e330`
- `0x5e560`
- `0x5e580`
- `0x60980`

## string_xrefs

- `0x5e389`: `Install`
- `0x5e3dd`: `Install`
- `0x5e433`: `Install`
- `0x5e35b`: `installerFactory is required when no factory is in the container`
- `0x5e3af`: `In Install.cs download == null`
- `0x5e3ef`: `NullInstallDir`
- `0x5e404`: `In Install.cs installDirectory == null`
- `0x5e417`: `installDirectory`
- `0x5e45a`: `In Install.cs package == null`

## pseudocode

```c

```

## disassembly

```asm
0x5e330  ldarg.0
0x5e331  ldc.i4.0
0x5e332  conv.i8
0x5e333  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int64)
0x5e338  stfld    valuetype [mscorlib]System.TimeSpan Microsoft.VisualStudio.Setup.Activities.Install::<DownloadWaitTime>k__BackingField
0x5e33d  ldarg.0
0x5e33e  ldarg.1
0x5e33f  call     instance void Microsoft.VisualStudio.Setup.Activities.SynchronizedActivity::.ctor(class [mscorlib]System.IServiceProvider services)
0x5e344  ldarg.0
0x5e345  ldarg.1
0x5e346  brtrue.s loc_5E34B
0x5e348  ldnull
0x5e349  br.s     loc_5E352
0x5e34b  ldarg.1
0x5e34c  ldc.i4.0
0x5e34d  call     T0x2B0001E4
0x5e352  dup
0x5e353  brtrue.s loc_5E366
0x5e355  pop
0x5e356  ldarg.2
0x5e357  dup
0x5e358  brtrue.s loc_5E366
0x5e35a  pop
0x5e35b  ldstr    aInstallerfacto// "installerFactory is required when no fa"...
0x5e360  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5e365  throw
0x5e366  stfld    class Microsoft.VisualStudio.Setup.Installer.IInstallerFactory Microsoft.VisualStudio.Setup.Activities.Install::factory
0x5e36b  ldarg.1
0x5e36c  brtrue.s loc_5E371
0x5e36e  ldnull
0x5e36f  br.s     loc_5E378
0x5e371  ldarg.1
0x5e372  ldc.i4.0
0x5e373  call     T0x2B000039
0x5e378  stloc.0
0x5e379  ldarg.3
0x5e37a  brtrue.s loc_5E3CC
0x5e37c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x5e381  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTLOCATIONPROPERTY
0x5e386  stloc.2
0x5e387  dup
0x5e388  ldloc.2
0x5e389  ldstr    aInstall// "Install"
0x5e38e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x5e393  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTTYPEPROPERTY
0x5e398  stloc.3
0x5e399  dup
0x5e39a  ldloc.3
0x5e39b  ldstr    aNulldownload// "NullDownload"
0x5e3a0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x5e3a5  stloc.1
0x5e3a6  ldloc.0
0x5e3a7  brfalse.s loc_5E3C1
0x5e3a9  ldloc.0
0x5e3aa  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTEVENT
0x5e3af  ldstr    aInInstallCsDow// "In Install.cs download == null"
0x5e3b4  ldloc.1
0x5e3b5  ldnull
0x5e3b6  ldnull
0x5e3b7  ldc.i4.0
0x5e3b8  ldnull
0x5e3b9  ldc.i4.0
0x5e3ba  ldnull
0x5e3bb  ldc.i4.0
0x5e3bc  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x5e3c1  ldstr    aDownload// "download"
0x5e3c6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5e3cb  throw
0x5e3cc  ldarg.s  4
0x5e3ce  brtrue.s loc_5E422
0x5e3d0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x5e3d5  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTLOCATIONPROPERTY
0x5e3da  stloc.3
0x5e3db  dup
0x5e3dc  ldloc.3
0x5e3dd  ldstr    aInstall// "Install"
0x5e3e2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x5e3e7  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTTYPEPROPERTY
0x5e3ec  stloc.2
0x5e3ed  dup
0x5e3ee  ldloc.2
0x5e3ef  ldstr    aNullinstalldir// "NullInstallDir"
0x5e3f4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x5e3f9  stloc.s  4
0x5e3fb  ldloc.0
0x5e3fc  brfalse.s loc_5E417
0x5e3fe  ldloc.0
0x5e3ff  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTEVENT
0x5e404  ldstr    aInInstallCsIns// "In Install.cs installDirectory == null"
0x5e409  ldloc.s  4
0x5e40b  ldnull
0x5e40c  ldnull
0x5e40d  ldc.i4.0
0x5e40e  ldnull
0x5e40f  ldc.i4.0
0x5e410  ldnull
0x5e411  ldc.i4.0
0x5e412  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x5e417  ldstr    aInstalldirecto// "installDirectory"
0x5e41c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5e421  throw
0x5e422  ldarg.s  5
0x5e424  brtrue.s loc_5E478
0x5e426  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x5e42b  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTLOCATIONPROPERTY
0x5e430  stloc.2
0x5e431  dup
0x5e432  ldloc.2
0x5e433  ldstr    aInstall// "Install"
0x5e438  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x5e43d  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTTYPEPROPERTY
0x5e442  stloc.3
0x5e443  dup
0x5e444  ldloc.3
0x5e445  ldstr    aNullpackage// "NullPackage"
0x5e44a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x5e44f  stloc.s  5
0x5e451  ldloc.0
0x5e452  brfalse.s loc_5E46D
0x5e454  ldloc.0
0x5e455  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTEVENT
0x5e45a  ldstr    aInInstallCsPac// "In Install.cs package == null"
0x5e45f  ldloc.s  5
0x5e461  ldnull
0x5e462  ldnull
0x5e463  ldc.i4.0
0x5e464  ldnull
0x5e465  ldc.i4.0
0x5e466  ldnull
0x5e467  ldc.i4.0
0x5e468  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x5e46d  ldstr    aPackage// "package"
0x5e472  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5e477  throw
0x5e478  ldarg.0
0x5e479  ldarg.s  5
0x5e47b  callvirt instance void Microsoft.VisualStudio.Setup.Activities.Activity::set_Package(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage value)
0x5e480  ldarg.0
0x5e481  ldarg.s  6
0x5e483  call     instance void Microsoft.VisualStudio.Setup.Activities.Install::set_RequestedAction(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction value)
0x5e488  ldarg.0
0x5e489  ldarg.s  4
0x5e48b  call     instance void Microsoft.VisualStudio.Setup.Activities.Install::set_InstallDirectory(string value)
0x5e490  ldarg.0
0x5e491  ldarg.3
0x5e492  stfld    class Microsoft.VisualStudio.Setup.Activities.IDownloadPackageActivity Microsoft.VisualStudio.Setup.Activities.Install::download
0x5e497  ldarg.0
0x5e498  ldarg.s  7
0x5e49a  stfld    valuetype [mscorlib]System.Nullable`1<bool> Microsoft.VisualStudio.Setup.Activities.Install::softDetectionHint
0x5e49f  ret
```
