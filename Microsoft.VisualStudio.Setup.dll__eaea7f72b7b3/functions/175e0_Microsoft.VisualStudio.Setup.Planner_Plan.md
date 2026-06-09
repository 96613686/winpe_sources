# Microsoft.VisualStudio.Setup.Planner::Plan

- ea: `0x175e0`
- end: `0x17f25`
- name: `Microsoft.VisualStudio.Setup.Planner::Plan`
- size: `2373`
- prototype: ``
- caller_count: `1`
- callee_count: `39`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140b0`

## callees

- `0x74d0`
- `0x103d0`
- `0x10410`
- `0x104e0`
- `0x16d80`
- `0x16e90`
- `0x16ee0`
- `0x16ef0`
- `0x16f20`
- `0x16f60`
- `0x17380`
- `0x173a0`
- `0x17540`
- `0x175e0`
- `0x17f30`
- `0x185b0`
- `0x18770`
- `0x1b220`
- `0x1b320`
- `0x1b340`
- `0x22930`
- `0x22940`
- `0x22950`
- `0x22960`
- `0x22990`
- `0x29260`
- `0x3eb90`
- `0x43840`
- `0x59710`
- `0x5aa20`
- `0x5e080`
- `0x5e260`
- `0x5e570`
- `0x60dc0`
- `0x60dd0`
- `0x69b20`
- `0x69d60`
- `0x69d80`
- `0x69e50`

## string_xrefs

- `0x176b8`: `InstallOperation`
- `0x176e1`: `No packages found to install/uninstall`
- `0x176f4`: `No packages were found to install/uninstall.`
- `0x17887`: `' is being removed and contains duplicate files.`
- `0x17966`: `' is requested to be present during uninstall.`

## pseudocode

```c

```

## disassembly

```asm
0x175e0  ldarg.0
0x175e1  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions Microsoft.VisualStudio.Setup.Planner::serviceOptions
0x175e6  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IMessageBus Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions::get_MessageBus()
0x175eb  brfalse.s loc_17613
0x175ed  ldarg.0
0x175ee  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.VisualStudio.Setup.Planner::DefaultDownloadMessageBusRateLimit
0x175f3  ldarg.0
0x175f4  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions Microsoft.VisualStudio.Setup.Planner::serviceOptions
0x175f9  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IMessageBus Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions::get_MessageBus()
0x175fe  ldarg.0
0x175ff  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions Microsoft.VisualStudio.Setup.Planner::serviceOptions
0x17604  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions::get_Logger()
0x17609  newobj   instance void Microsoft.VisualStudio.Setup.Services.RateLimitedMessageBusProxy::.ctor(valuetype [mscorlib]System.TimeSpan rateLimit, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IMessageBus messageBus, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x1760e  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IMessageBus Microsoft.VisualStudio.Setup.Planner::downloadMessageBus
0x17613  ldarg.0
0x17614  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions Microsoft.VisualStudio.Setup.Planner::serviceOptions
0x17619  callvirt instance class Microsoft.VisualStudio.Setup.Services.IPolicyService Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions::get_PolicyService()
0x1761e  callvirt instance int32 Microsoft.VisualStudio.Setup.Services.IPolicyService::get_ConcurrentDownloads()
0x17623  stloc.0
0x17624  ldloc.0
0x17625  ldc.i4.1
0x17626  blt.s    loc_1762D
0x17628  ldloc.0
0x17629  ldc.i4.s 0x40
0x1762b  ble.s    loc_17632
0x1762d  ldc.i4.1
0x1762e  stloc.s  0x12
0x17630  br.s     loc_17635
0x17632  ldc.i4.0
0x17633  stloc.s  0x12
0x17635  ldloc.s  0x12
0x17637  brfalse.s loc_1765F
0x17639  ldarg.0
0x1763a  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions Microsoft.VisualStudio.Setup.Planner::serviceOptions
0x1763f  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions::get_Logger()
0x17644  ldstr    aOverridingTheC// "Overriding the ConcurrentDownloads valu"...
0x17649  ldc.i4.1
0x1764a  newarr   [mscorlib]System.Object
0x1764f  dup
0x17650  ldc.i4.0
0x17651  ldloc.0
0x17652  box      [mscorlib]System.Int32
0x17657  stelem.ref
0x17658  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x1765d  ldc.i4.6
0x1765e  stloc.0
0x1765f  ldarg.0
0x17660  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions Microsoft.VisualStudio.Setup.Planner::serviceOptions
0x17665  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions::get_Logger()
0x1766a  ldstr    aConcurrentDown// "Concurrent downloads: {0}"
0x1766f  ldc.i4.1
0x17670  newarr   [mscorlib]System.Object
0x17675  dup
0x17676  ldc.i4.0
0x17677  ldloc.0
0x17678  box      [mscorlib]System.Int32
0x1767d  stelem.ref
0x1767e  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x17683  ldarg.s  4
0x17685  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::SESSIONCONCURRENTDOWNLOADS
0x1768a  ldloc.0
0x1768b  box      [mscorlib]System.Int32
0x17690  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x17695  ldarg.0
0x17696  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions Microsoft.VisualStudio.Setup.Planner::serviceOptions
0x1769b  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions::get_Telemetry()
0x176a0  stloc.1
0x176a1  ldarg.1
0x176a2  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::get_Count()
0x176a7  brtrue.s loc_17720
0x176a9  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x176ae  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTLOCATIONPROPERTY
0x176b3  stloc.s  0x15
0x176b5  dup
0x176b6  ldloc.s  0x15
0x176b8  ldstr    aInstalloperati// "InstallOperation"
0x176bd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x176c2  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTTYPEPROPERTY
0x176c7  stloc.s  0x16
0x176c9  dup
0x176ca  ldloc.s  0x16
0x176cc  ldstr    aNopackages// "NoPackages"
0x176d1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x176d6  stloc.s  0x13
0x176d8  ldloc.1
0x176d9  brfalse.s loc_176F4
0x176db  ldloc.1
0x176dc  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTEVENT
0x176e1  ldstr    aNoPackagesFoun_0// "No packages found to install/uninstall"
0x176e6  ldloc.s  0x13
0x176e8  ldnull
0x176e9  ldnull
0x176ea  ldc.i4.0
0x176eb  ldnull
0x176ec  ldc.i4.0
0x176ed  ldnull
0x176ee  ldc.i4.0
0x176ef  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x176f4  ldstr    aNoPackagesWere// "No packages were found to install/unins"...
0x176f9  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x176fe  stloc.s  0x14
0x17700  ldarg.0
0x17701  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions Microsoft.VisualStudio.Setup.Planner::serviceOptions
0x17706  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions::get_Logger()
0x1770b  ldloc.s  0x14
0x1770d  ldloc.s  0x14
0x1770f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x17714  call     T0x2B000003
0x17719  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x1771e  ldnull
0x1771f  ret
0x17720  ldsfld   class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageIdentityComparer [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageIdentityComparer::Default
0x17725  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity, class Microsoft.VisualStudio.Setup.Activities.DownloadPackage>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x1772a  stloc.2
0x1772b  ldarg.0
0x1772c  ldarg.1
0x1772d  call     instance class [System]System.Collections.Generic.ISet`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity> Microsoft.VisualStudio.Setup.Planner::AddOrphanedPackages(class [System]System.Collections.Generic.ISet`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage> plannedPackages)
0x17732  stloc.3
0x17733  ldarg.3
0x17734  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> <>c::<>9__20_0
0x17739  dup
0x1773a  brtrue.s loc_17753
0x1773c  pop
0x1773d  ldsfld   class <>c <>c::<>9
0x17742  ldftn    instance string <>c::<Plan>b__20_0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> pair)
0x17748  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string>::.ctor(object, native int)
0x1774d  dup
0x1774e  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> <>c::<>9__20_0
0x17753  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_InvariantCultureIgnoreCase()
0x17758  call     T0x2B0000ED
0x1775d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::GetEnumerator()
0x17762  stloc.s  0x17
0x17764  br.s     loc_177A1
0x17766  ldloc.s  0x17
0x17768  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Current()
0x1776d  stloc.s  0x18
0x1776f  ldarg.0
0x17770  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions Microsoft.VisualStudio.Setup.Planner::serviceOptions
0x17775  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions::get_Logger()
0x1777a  ldstr    aProperty// "Property: "
0x1777f  ldloca.s 0x18
0x17781  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x17786  ldstr    aValue// ", value: "
0x1778b  ldloca.s 0x18
0x1778d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x17792  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x17797  call     T0x2B000003
0x1779c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x177a1  ldloc.s  0x17
0x177a3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x177a8  brtrue.s loc_17766
0x177aa  leave.s  loc_177B8
0x177ac  ldloc.s  0x17
0x177ae  brfalse.s loc_177B7
0x177b0  ldloc.s  0x17
0x177b2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x177b7  endfinally
0x177b8  ldloc.1
0x177b9  brfalse.s loc_177E0
0x177bb  ldarg.0
0x177bc  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions Microsoft.VisualStudio.Setup.Planner::serviceOptions
0x177c1  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions::get_Logger()
0x177c6  ldstr    aPropertyTeleme// "Property: TelemetrySessionID, value: "
0x177cb  ldloc.1
0x177cc  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::get_TelemetrySessionID()
0x177d1  call     string [mscorlib]System.String::Concat(string, string)
0x177d6  call     T0x2B000003
0x177db  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x177e0  ldarg.0
0x177e1  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions Microsoft.VisualStudio.Setup.Planner::serviceOptions
0x177e6  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions::get_Logger()
0x177eb  dup
0x177ec  brtrue.s loc_177F1
0x177ee  pop
0x177ef  br.s     loc_1780F
0x177f1  ldstr    aPackagesWithDe// "Packages with declared 'chip' value dif"...
0x177f6  call     string Microsoft.VisualStudio.Setup.Utility.StringUtility::GetChipForMachineArchitecture()
0x177fb  ldstr    aWillBeExcluded// "' will be excluded unless explicitly re"...
0x17800  call     string [mscorlib]System.String::Concat(string, string, string)
0x17805  call     T0x2B000003
0x1780a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x1780f  newobj   instance void Microsoft.VisualStudio.Setup.Plan::.ctor()
0x17814  stloc.s  4
0x17816  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.PackagePlan>::.ctor()
0x1781b  stloc.s  5
0x1781d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.PackagePlan>::.ctor()
0x17822  stloc.s  6
0x17824  ldc.i4.0
0x17825  stloc.s  7
0x17827  ldc.i4.0
0x17828  stloc.s  8
0x1782a  ldarg.1
0x1782b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::GetEnumerator()
0x17830  stloc.s  0x19
0x17832  br       loc_178F2
0x17837  ldloc.s  0x19
0x17839  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::get_Current()
0x1783e  stloc.s  0x1A
0x17840  ldloc.s  0x1A
0x17842  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RequestedState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage::get_RequestedState()
0x17847  ldc.i4.1
0x17848  bne.un   loc_178F2
0x1784d  ldloc.s  0x1A
0x1784f  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CurrentState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage::get_CurrentState()
0x17854  ldc.i4.3
0x17855  bne.un.s loc_178A0
0x17857  ldsfld   class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.Planner::PackagesWithDuplicateFiles
0x1785c  ldloc.s  0x1A
0x1785e  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0x17863  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<string>::Contains(var<u1>)
0x17868  brfalse.s loc_178A0
0x1786a  ldarg.0
0x1786b  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions Microsoft.VisualStudio.Setup.Planner::serviceOptions
0x17870  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions::get_Logger()
0x17875  dup
0x17876  brtrue.s loc_1787B
0x17878  pop
0x17879  br.s     loc_1789B
0x1787b  ldstr    aPackage_0// "Package '"
0x17880  ldloc.s  0x1A
0x17882  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::GetUniqueId()
0x17887  ldstr    aIsBeingRemoved// "' is being removed and contains duplica"...
0x1788c  call     string [mscorlib]System.String::Concat(string, string, string)
0x17891  call     T0x2B000003
0x17896  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x1789b  ldc.i4.1
0x1789c  stloc.s  7
0x1789e  leave.s  loc_1790C
0x178a0  ldloc.s  0x1A
0x178a2  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CurrentState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage::get_CurrentState()
0x178a7  ldc.i4.2
0x178a8  bne.un.s loc_178F2
0x178aa  ldsfld   string Microsoft.VisualStudio.Setup.Planner::ConfigurationPackageId
0x178af  ldloc.s  0x1A
0x178b1  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0x178b6  ldc.i4.5
0x178b7  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x178bc  brfalse.s loc_178F2
0x178be  ldarg.0
0x178bf  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions Microsoft.VisualStudio.Setup.Planner::serviceOptions
0x178c4  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.SchedulerServiceOptions::get_Logger()
0x178c9  dup
0x178ca  brtrue.s loc_178CF
0x178cc  pop
0x178cd  br.s     loc_178ED
0x178cf  ldstr    aPackage_0// "Package '"
0x178d4  ldsfld   string Microsoft.VisualStudio.Setup.Planner::ConfigurationPackageId
0x178d9  ldstr    aWillBeUpgraded// "' will be upgraded first."
0x178de  call     string [mscorlib]System.String::Concat(string, string, string)
0x178e3  call     T0x2B000003
0x178e8  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x178ed  ldc.i4.1
0x178ee  stloc.s  8
0x178f0  leave.s  loc_1790C
0x178f2  ldloc.s  0x19
0x178f4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x178f9  brtrue   loc_17837
0x178fe  leave.s  loc_1790C
0x17900  ldloc.s  0x19
0x17902  brfalse.s loc_1790B
0x17904  ldloc.s  0x19
0x17906  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1790b  endfinally
0x1790c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Activities.IActivity>::.ctor()
0x17911  stloc.s  9
0x17913  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Activities.IActivity>::.ctor()
0x17918  stloc.s  0xA
0x1791a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Activities.DownloadPackage>::.ctor()
0x1791f  stloc.s  0xB
0x17921  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Activities.IActivity>::.ctor()
0x17926  stloc.s  0xC
0x17928  ldarg.1
0x17929  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::GetEnumerator()
0x1792e  stloc.s  0x19
0x17930  br       loc_17CA5
0x17935  ldloc.s  0x19
0x17937  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::get_Current()
0x1793c  stloc.s  0x1B
0x1793e  ldloc.s  0x1B
0x17940  newobj   instance void Microsoft.VisualStudio.Setup.PackagePlan::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage package)
0x17945  stloc.s  0x1C
0x17947  ldloc.s  0x1B
0x17949  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RequestedState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage::get_RequestedState()
0x1794e  ldc.i4.3
0x1794f  bne.un.s loc_17976
0x17951  ldarg.0
0x17952  ldfld    valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction Microsoft.VisualStudio.Setup.Planner::bootstrapperAction
0x17957  ldc.i4.3
0x17958  bne.un.s loc_17976
0x1795a  ldstr    aPackage_0// "Package '"
0x1795f  ldloc.s  0x1B
0x17961  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::GetUniqueId()
0x17966  ldstr    aIsRequestedToB// "' is requested to be present during uni"...
0x1796b  call     string [mscorlib]System.String::Concat(string, string, string)
0x17970  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x17975  throw
0x17976  ldloc.s  0x1B
0x17978  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RequestedState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage::get_RequestedState()
0x1797d  ldc.i4.4
0x1797e  bne.un.s loc_179A5
  ... truncated ...
```
