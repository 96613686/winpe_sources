# Microsoft.VisualStudio.Setup.Planner::PlanInstallable

- ea: `0x17f30`
- end: `0x18444`
- name: `Microsoft.VisualStudio.Setup.Planner::PlanInstallable`
- size: `1300`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `installer_update, broker_com_uri`

## callers

- `0x175e0`

## callees

- `0x7630`
- `0x16e90`
- `0x16ea0`
- `0x16f00`
- `0x16f10`
- `0x16f20`
- `0x16f30`
- `0x16f40`
- `0x16f50`
- `0x17410`
- `0x174f0`
- `0x17510`
- `0x175c0`
- `0x17f30`
- `0x18450`
- `0x18890`
- `0x22930`
- `0x2af00`
- `0x2af20`
- `0x2b750`
- `0x2b790`
- `0x2b7d0`
- `0x69d40`
- `0x69d60`
- `0x69d80`

## string_xrefs

- `0x17fce`: `' for repair since a package with duplicate files is being removed.`
- `0x18008`: `' for install since it is a downgrading (v1) package.`
- `0x1811f`: `Skipping install of '`
- `0x18169`: `Skipping install of '`
- `0x182da`: `Resetting planned action to '{0}' for package '{1}' since its superseding package is already installed/superseded.`
- `0x18336`: `Skipping uninstall of '`
- `0x18380`: `Skipping uninstall of '`
- `0x183e2`: `Skipping uninstall of '`
- `0x1838b`: `' because it is not uninstallable.`
- `0x183ed`: `' because it will be upgraded by Windows Installer.`

## pseudocode

```c

```

## disassembly

```asm
0x17f30  ldnull
0x17f31  stloc.0
0x17f32  ldarg.1
0x17f33  brtrue.s loc_17F37
0x17f35  ldloc.0
0x17f36  ret
0x17f37  ldarg.1
0x17f38  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RequestedState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_RequestedState()
0x17f3d  ldarg.1
0x17f3e  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CurrentState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_CurrentState()
0x17f43  ldarg.0
0x17f44  ldfld    valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction Microsoft.VisualStudio.Setup.Planner::bootstrapperAction
0x17f49  call     valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction Microsoft.VisualStudio.Setup.Planner::ConvertToExecuteAction(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RequestedState requestedState, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CurrentState currentState, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction bootstrapperActionToConvert)
0x17f4e  stloc.1
0x17f4f  ldarg.0
0x17f50  ldfld    class Microsoft.VisualStudio.Setup.Installer.IInstallerFactory Microsoft.VisualStudio.Setup.Planner::installerFactory
0x17f55  ldarg.1
0x17f56  ldarg.0
0x17f57  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions Microsoft.VisualStudio.Setup.Planner::serviceOptions
0x17f5c  callvirt instance class Microsoft.VisualStudio.Setup.Installer.IInstaller Microsoft.VisualStudio.Setup.Installer.IInstallerFactory::CreateInstaller(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage package, class [mscorlib]System.IServiceProvider services)
0x17f61  dup
0x17f62  ldarg.0
0x17f63  ldfld    class Microsoft.VisualStudio.Setup.IEngineContext Microsoft.VisualStudio.Setup.Planner::engineContext
0x17f68  callvirt instance void Microsoft.VisualStudio.Setup.Installer.IInstaller::set_EngineContext(class Microsoft.VisualStudio.Setup.IEngineContext value)
0x17f6d  ldarg.1
0x17f6e  call     bool Microsoft.VisualStudio.Setup.Planner::IsPresent(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage package)
0x17f73  stloc.2
0x17f74  ldarg.1
0x17f75  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_PackageToDowngrade()
0x17f7a  ldnull
0x17f7b  ceq
0x17f7d  ldc.i4.0
0x17f7e  ceq
0x17f80  stloc.3
0x17f81  ldarg.1
0x17f82  ldloc.1
0x17f83  ldloca.s 4
0x17f85  ldloca.s 5
0x17f87  ldloc.2
0x17f88  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x17f8d  ldnull
0x17f8e  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.IInstaller::PlanExecuteAction(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage pkg, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction requestedAction, [out] valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction& plannedAction, [out] valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageState& currentState, valuetype [mscorlib]System.Nullable`1<bool> softDetectionHint, string localPath)
0x17f93  pop
0x17f94  ldarg.s  4
0x17f96  brfalse.s loc_17FE5
0x17f98  ldloc.1
0x17f99  ldc.i4.3
0x17f9a  beq.s    loc_17FE5
0x17f9c  ldloc.s  5
0x17f9e  brtrue.s loc_17FE5
0x17fa0  ldsfld   class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.Planner::PackagesWithDuplicateFiles
0x17fa5  ldarg.1
0x17fa6  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Id()
0x17fab  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<string>::Contains(var<u1>)
0x17fb0  brfalse.s loc_17FE5
0x17fb2  ldarg.0
0x17fb3  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions Microsoft.VisualStudio.Setup.Planner::serviceOptions
0x17fb8  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions::get_Logger()
0x17fbd  dup
0x17fbe  brtrue.s loc_17FC3
0x17fc0  pop
0x17fc1  br.s     loc_17FE2
0x17fc3  ldstr    aSchedulingPack// "Scheduling package '"
0x17fc8  ldarg.1
0x17fc9  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::GetUniqueId()
0x17fce  ldstr    aForRepairSince// "' for repair since a package with dupli"...
0x17fd3  call     string [mscorlib]System.String::Concat(string, string, string)
0x17fd8  call     T0x2B000003
0x17fdd  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x17fe2  ldc.i4.2
0x17fe3  stloc.s  4
0x17fe5  ldloc.3
0x17fe6  brfalse.s loc_1801F
0x17fe8  ldloc.1
0x17fe9  ldc.i4.1
0x17fea  bne.un.s loc_1801F
0x17fec  ldarg.0
0x17fed  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions Microsoft.VisualStudio.Setup.Planner::serviceOptions
0x17ff2  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions::get_Logger()
0x17ff7  dup
0x17ff8  brtrue.s loc_17FFD
0x17ffa  pop
0x17ffb  br.s     loc_1801C
0x17ffd  ldstr    aSchedulingPack// "Scheduling package '"
0x18002  ldarg.1
0x18003  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::GetUniqueId()
0x18008  ldstr    aForInstallSinc// "' for install since it is a downgrading"...
0x1800d  call     string [mscorlib]System.String::Concat(string, string, string)
0x18012  call     T0x2B000003
0x18017  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x1801c  ldc.i4.1
0x1801d  stloc.s  4
0x1801f  ldarg.3
0x18020  ldind.ref
0x18021  ldloc.s  5
0x18023  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageState>::.ctor(var<u1>)
0x18028  callvirt instance void Microsoft.VisualStudio.Setup.PackagePlan::set_DeepDetectionState(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageState> value)
0x1802d  ldarg.3
0x1802e  ldind.ref
0x1802f  ldloc.s  4
0x18031  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction>::.ctor(var<u1>)
0x18036  callvirt instance void Microsoft.VisualStudio.Setup.PackagePlan::set_PlannedActionBeforeRefCount(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction> value)
0x1803b  ldarg.3
0x1803c  ldind.ref
0x1803d  ldarg.0
0x1803e  ldfld    class Microsoft.VisualStudio.Setup.DependencyActionManager Microsoft.VisualStudio.Setup.Planner::dependencyActionManager
0x18043  ldarg.1
0x18044  ldarg.3
0x18045  ldind.ref
0x18046  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction> Microsoft.VisualStudio.Setup.PackagePlan::get_PlannedActionBeforeRefCount()
0x1804b  stloc.s  6
0x1804d  ldloca.s 6
0x1804f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction>::get_Value()
0x18054  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction Microsoft.VisualStudio.Setup.DependencyActionManager::PlanPackageWithLegacyDependencies(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage package, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction requestedAction)
0x18059  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction>::.ctor(var<u1>)
0x1805e  callvirt instance void Microsoft.VisualStudio.Setup.PackagePlan::set_PlannedActionAfterRefCount(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction> value)
0x18063  ldarg.1
0x18064  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RequestedState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_RequestedState()
0x18069  ldc.i4.3
0x1806a  bne.un   loc_181F3
0x1806f  ldarg.1
0x18070  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Replace()
0x18075  brfalse.s loc_180C8
0x18077  ldarg.3
0x18078  ldind.ref
0x18079  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction> Microsoft.VisualStudio.Setup.PackagePlan::get_PlannedActionAfterRefCount()
0x1807e  stloc.s  6
0x18080  ldc.i4.0
0x18081  stloc.s  7
0x18083  ldloca.s 6
0x18085  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction>::GetValueOrDefault()
0x1808a  ldloc.s  7
0x1808c  ceq
0x1808e  ldloca.s 6
0x18090  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction>::get_HasValue()
0x18095  and
0x18096  brfalse.s loc_180C8
0x18098  ldarg.3
0x18099  ldind.ref
0x1809a  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageState> Microsoft.VisualStudio.Setup.PackagePlan::get_DeepDetectionState()
0x1809f  stloc.s  8
0x180a1  ldc.i4.0
0x180a2  stloc.s  9
0x180a4  ldloca.s 8
0x180a6  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageState>::GetValueOrDefault()
0x180ab  ldloc.s  9
0x180ad  ceq
0x180af  ldloca.s 8
0x180b1  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageState>::get_HasValue()
0x180b6  and
0x180b7  brfalse.s loc_180C8
0x180b9  ldarg.3
0x180ba  ldind.ref
0x180bb  ldc.i4.1
0x180bc  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction>::.ctor(var<u1>)
0x180c1  callvirt instance void Microsoft.VisualStudio.Setup.PackagePlan::set_PlannedActionAfterRefCount(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction> value)
0x180c6  ldc.i4.0
0x180c7  stloc.2
0x180c8  ldarg.3
0x180c9  ldind.ref
0x180ca  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction> Microsoft.VisualStudio.Setup.PackagePlan::get_PlannedActionAfterRefCount()
0x180cf  stloc.s  6
0x180d1  ldloca.s 6
0x180d3  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction>::GetValueOrDefault()
0x180d8  ldc.i4.1
0x180d9  beq.s    loc_180F1
0x180db  ldarg.3
0x180dc  ldind.ref
0x180dd  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction> Microsoft.VisualStudio.Setup.PackagePlan::get_PlannedActionAfterRefCount()
0x180e2  stloc.s  6
0x180e4  ldloca.s 6
0x180e6  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction>::GetValueOrDefault()
0x180eb  ldc.i4.2
0x180ec  bne.un   loc_181F3
0x180f1  ldarg.1
0x180f2  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_OutOfSupport()
0x180f7  ldloc.2
0x180f8  and
0x180f9  brfalse.s loc_18150
0x180fb  ldarg.3
0x180fc  ldind.ref
0x180fd  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageState> Microsoft.VisualStudio.Setup.PackagePlan::get_DeepDetectionState()
0x18102  stloc.s  8
0x18104  ldloca.s 8
0x18106  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageState>::GetValueOrDefault()
0x1810b  ldc.i4.1
0x1810c  bne.un.s loc_18150
0x1810e  ldarg.0
0x1810f  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions Microsoft.VisualStudio.Setup.Planner::serviceOptions
0x18114  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions::get_Logger()
0x18119  dup
0x1811a  brtrue.s loc_1811F
0x1811c  pop
0x1811d  br.s     loc_1813E
0x1811f  ldstr    aSkippingInstal// "Skipping install of '"
0x18124  ldarg.1
0x18125  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::GetUniqueId()
0x1812a  ldstr    aBecauseItIsOut// "' because it is out of support."
0x1812f  call     string [mscorlib]System.String::Concat(string, string, string)
0x18134  call     T0x2B000003
0x18139  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x1813e  ldarg.3
0x1813f  ldind.ref
0x18140  ldc.i4.0
0x18141  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction>::.ctor(var<u1>)
0x18146  callvirt instance void Microsoft.VisualStudio.Setup.PackagePlan::set_FinalPlannedAction(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction> value)
0x1814b  br       loc_181F3
0x18150  ldarg.1
0x18151  call     bool Microsoft.VisualStudio.Setup.Planner::IsDowngradePackagePermanent(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage installable)
0x18156  brfalse.s loc_18197
0x18158  ldarg.0
0x18159  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions Microsoft.VisualStudio.Setup.Planner::serviceOptions
0x1815e  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions::get_Logger()
0x18163  dup
0x18164  brtrue.s loc_18169
0x18166  pop
0x18167  br.s     loc_18188
0x18169  ldstr    aSkippingInstal// "Skipping install of '"
0x1816e  ldarg.1
0x1816f  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::GetUniqueId()
0x18174  ldstr    aBecauseThePack// "' because the package to downgrade from"...
0x18179  call     string [mscorlib]System.String::Concat(string, string, string)
0x1817e  call     T0x2B000003
0x18183  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x18188  ldarg.3
0x18189  ldind.ref
0x1818a  ldc.i4.0
0x1818b  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction>::.ctor(var<u1>)
0x18190  callvirt instance void Microsoft.VisualStudio.Setup.PackagePlan::set_FinalPlannedAction(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction> value)
0x18195  br.s     loc_181F3
0x18197  ldarg.0
0x18198  ldarg.1
0x18199  ldarg.3
0x1819a  ldind.ref
0x1819b  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction> Microsoft.VisualStudio.Setup.PackagePlan::get_PlannedActionAfterRefCount()
0x181a0  stloc.s  6
0x181a2  ldloca.s 6
0x181a4  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction>::get_Value()
0x181a9  ldloc.2
0x181aa  ldarg.s  7
0x181ac  ldarg.s  0xB
0x181ae  call     instance class PackageActivities Microsoft.VisualStudio.Setup.Planner::CreateDownloadInstallActivities(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage installable, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action, bool isPresent, string installDir, class [mscorlib]System.EventHandler`1<class [mscorlib]System.EventArgs> downloadOnCanceledHandler)
0x181b3  stloc.0
0x181b4  ldloc.0
0x181b5  callvirt instance class Microsoft.VisualStudio.Setup.Activities.VerifyPackageAndDeleteCorruptFiles PackageActivities::get_Verify()
0x181ba  brfalse.s loc_181C9
0x181bc  ldarg.s  0xA
0x181be  ldloc.0
0x181bf  callvirt instance class Microsoft.VisualStudio.Setup.Activities.VerifyPackageAndDeleteCorruptFiles PackageActivities::get_Verify()
0x181c4  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.VisualStudio.Setup.Activities.IActivity>::Add(var<u1>)
0x181c9  ldloc.0
0x181ca  callvirt instance class Microsoft.VisualStudio.Setup.Activities.Install PackageActivities::get_Install()
0x181cf  brfalse.s loc_181DE
0x181d1  ldarg.s  9
0x181d3  ldloc.0
0x181d4  callvirt instance class Microsoft.VisualStudio.Setup.Activities.Install PackageActivities::get_Install()
0x181d9  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.VisualStudio.Setup.Activities.IActivity>::Add(var<u1>)
0x181de  ldloc.0
0x181df  callvirt instance class Microsoft.VisualStudio.Setup.Activities.DownloadPackage PackageActivities::get_Download()
0x181e4  brfalse.s loc_181F3
0x181e6  ldarg.2
0x181e7  ldarg.1
0x181e8  ldloc.0
0x181e9  callvirt instance class Microsoft.VisualStudio.Setup.Activities.DownloadPackage PackageActivities::get_Download()
0x181ee  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity, class Microsoft.VisualStudio.Setup.Activities.DownloadPackage>::set_Item(var<u1>, !!T0)
0x181f3  ldarg.1
0x181f4  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RequestedState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_RequestedState()
0x181f9  ldc.i4.1
0x181fa  beq.s    loc_18208
0x181fc  ldarg.1
0x181fd  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RequestedState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_RequestedState()
0x18202  ldc.i4.4
0x18203  bne.un   loc_18442
0x18208  ldarg.3
0x18209  ldind.ref
0x1820a  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction> Microsoft.VisualStudio.Setup.PackagePlan::get_PlannedActionAfterRefCount()
0x1820f  stloc.s  6
0x18211  ldloca.s 6
0x18213  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction>::GetValueOrDefault()
0x18218  ldc.i4.3
0x18219  bne.un   loc_18442
0x1821e  ldarg.3
0x1821f  ldind.ref
0x18220  ldarg.3
0x18221  ldind.ref
0x18222  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction> Microsoft.VisualStudio.Setup.PackagePlan::get_PlannedActionAfterRefCount()
0x18227  callvirt instance void Microsoft.VisualStudio.Setup.PackagePlan::set_FinalPlannedAction(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction> value)
0x1822c  ldarg.0
0x1822d  ldarg.1
0x1822e  ldarg.s  6
0x18230  ldarg.s  8
0x18232  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage Microsoft.VisualStudio.Setup.Planner::GetOrphanedSupersedingPackage(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage, bool orphan, class [System]System.Collections.Generic.ISet`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage> isOrphan)
0x18237  stloc.s  0xA
0x18239  ldarg.1
0x1823a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_SupersedingPackage()
0x1823f  isinst   [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage
0x18244  dup
0x18245  brtrue.s loc_1824A
0x18247  pop
0x18248  ldloc.s  0xA
  ... truncated ...
```
