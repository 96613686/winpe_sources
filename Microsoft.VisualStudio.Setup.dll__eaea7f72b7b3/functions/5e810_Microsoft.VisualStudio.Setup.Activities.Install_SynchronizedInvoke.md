# Microsoft.VisualStudio.Setup.Activities.Install::SynchronizedInvoke

- ea: `0x5e810`
- end: `0x5ed8e`
- name: `Microsoft.VisualStudio.Setup.Activities.Install::SynchronizedInvoke`
- size: `1406`
- prototype: ``
- caller_count: `0`
- callee_count: `35`
- tags: `installer_update, broker_com_uri`

## callees

- `0xe3c0`
- `0xe450`
- `0x14850`
- `0x14860`
- `0x2b750`
- `0x2b760`
- `0x2b770`
- `0x2b780`
- `0x2b7a0`
- `0x2b7d0`
- `0x2ba10`
- `0x596d0`
- `0x596f0`
- `0x59710`
- `0x59960`
- `0x599a0`
- `0x59aa0`
- `0x5e1b0`
- `0x5e1d0`
- `0x5e240`
- `0x5e530`
- `0x5e550`
- `0x5e570`
- `0x5e590`
- `0x5e5a0`
- `0x5e5b0`
- `0x5e5c0`
- `0x5e5e0`
- `0x5e5f0`
- `0x5e600`
- `0x5e690`
- `0x5e810`
- `0x5ed90`
- `0x5edf0`
- `0x5f050`

## string_xrefs

- `0x5e908`: ` is not installable`
- `0x5e9cf`: `Cache failed. Retrying download of '`
- `0x5ebfd`: `'. Manual clean up is required for future installation attempts to succeed. Error: `

## pseudocode

```c

```

## disassembly

```asm
0x5e810  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x5e815  stloc.0
0x5e816  ldarg.0
0x5e817  ldfld    class Microsoft.VisualStudio.Setup.Activities.IDownloadPackageActivity Microsoft.VisualStudio.Setup.Activities.Install::download
0x5e81c  dup
0x5e81d  brtrue.s loc_5E822
0x5e81f  pop
0x5e820  br.s     loc_5E827
0x5e822  callvirt instance void Microsoft.VisualStudio.Setup.Activities.ISynchronizedActivity::Wait()
0x5e827  ldarg.0
0x5e828  ldarg.0
0x5e829  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.VisualStudio.Setup.Activities.Install::get_DownloadWaitTime()
0x5e82e  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x5e833  ldloc.0
0x5e834  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x5e839  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::op_Addition(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x5e83e  callvirt instance void Microsoft.VisualStudio.Setup.Activities.Install::set_DownloadWaitTime(valuetype [mscorlib]System.TimeSpan value)
0x5e843  ldarg.0
0x5e844  ldfld    class Microsoft.VisualStudio.Setup.Activities.IDownloadPackageActivity Microsoft.VisualStudio.Setup.Activities.Install::download
0x5e849  dup
0x5e84a  brtrue.s loc_5E850
0x5e84c  pop
0x5e84d  ldnull
0x5e84e  br.s     loc_5E855
0x5e850  callvirt instance class [mscorlib]System.Exception Microsoft.VisualStudio.Setup.Activities.IActivity::get_Error()
0x5e855  brfalse.s loc_5E88D
0x5e857  ldarg.0
0x5e858  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5e85d  dup
0x5e85e  brtrue.s loc_5E862
0x5e860  pop
0x5e861  ret
0x5e862  ldstr    aSkipping0Of1Si// "Skipping {0} of '{1}' since downloading"...
0x5e867  ldarg.0
0x5e868  call     instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction Microsoft.VisualStudio.Setup.Activities.Install::get_RequestedAction()
0x5e86d  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction
0x5e872  ldarg.0
0x5e873  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.Activity::get_Package()
0x5e878  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::GetUniqueId()
0x5e87d  call     string [mscorlib]System.String::Format(string, object, object)
0x5e882  call     T0x2B000003
0x5e887  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x5e88c  ret
0x5e88d  ldarg.0
0x5e88e  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.Activity::get_Package()
0x5e893  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::ShouldSkip(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage)
0x5e898  brfalse.s loc_5E8E2
0x5e89a  ldarg.0
0x5e89b  call     instance void Microsoft.VisualStudio.Setup.Activities.Activity::AddSkippedPackageToInstance()
0x5e8a0  ldarg.0
0x5e8a1  ldc.i4.1
0x5e8a2  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x5e8a7  call     instance void Microsoft.VisualStudio.Setup.Activities.Install::set_SkippedPackage(valuetype [mscorlib]System.Nullable`1<bool> value)
0x5e8ac  ldarg.0
0x5e8ad  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5e8b2  dup
0x5e8b3  brtrue.s loc_5E8B7
0x5e8b5  pop
0x5e8b6  ret
0x5e8b7  ldstr    aSkipping0Of1Si_0// "Skipping {0} of '{1}' since the package"...
0x5e8bc  ldarg.0
0x5e8bd  call     instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction Microsoft.VisualStudio.Setup.Activities.Install::get_RequestedAction()
0x5e8c2  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction
0x5e8c7  ldarg.0
0x5e8c8  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.Activity::get_Package()
0x5e8cd  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::GetUniqueId()
0x5e8d2  call     string [mscorlib]System.String::Format(string, object, object)
0x5e8d7  call     T0x2B000003
0x5e8dc  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x5e8e1  ret
0x5e8e2  ldarg.0
0x5e8e3  ldc.i4.0
0x5e8e4  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x5e8e9  call     instance void Microsoft.VisualStudio.Setup.Activities.Install::set_SkippedPackage(valuetype [mscorlib]System.Nullable`1<bool> value)
0x5e8ee  ldarg.0
0x5e8ef  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.Activity::get_Package()
0x5e8f4  isinst   [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage
0x5e8f9  dup
0x5e8fa  brtrue.s loc_5E918
0x5e8fc  pop
0x5e8fd  ldarg.0
0x5e8fe  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.Activity::get_Package()
0x5e903  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::GetUniqueId()
0x5e908  ldstr    aIsNotInstallab// " is not installable"
0x5e90d  call     string [mscorlib]System.String::Concat(string, string)
0x5e912  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x5e917  throw
0x5e918  stloc.1
0x5e919  ldarg.0
0x5e91a  ldfld    class Microsoft.VisualStudio.Setup.Installer.IInstallerFactory Microsoft.VisualStudio.Setup.Activities.Install::factory
0x5e91f  ldloc.1
0x5e920  ldarg.0
0x5e921  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.Activity::get_Services()
0x5e926  callvirt instance class Microsoft.VisualStudio.Setup.Installer.IInstaller Microsoft.VisualStudio.Setup.Installer.IInstallerFactory::CreateInstaller(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage package, class [mscorlib]System.IServiceProvider services)
0x5e92b  stloc.2
0x5e92c  ldloc.2
0x5e92d  ldarg.0
0x5e92e  call     instance class Microsoft.VisualStudio.Setup.IEngineContext Microsoft.VisualStudio.Setup.Activities.Install::get_EngineContext()
0x5e933  callvirt instance void Microsoft.VisualStudio.Setup.Installer.IInstaller::set_EngineContext(class Microsoft.VisualStudio.Setup.IEngineContext value)
0x5e938  ldloc.2
0x5e939  ldarg.0
0x5e93a  ldftn    instance void Microsoft.VisualStudio.Setup.Activities.Install::Installer_ProgressReceived(object sender, class Microsoft.VisualStudio.Setup.ProgressDataEventArgs e)
0x5e940  newobj   instance void class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.ProgressDataEventArgs>::.ctor(object, native int)
0x5e945  callvirt instance void Microsoft.VisualStudio.Setup.IProgressProvider::add_ProgressReceived(class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.ProgressDataEventArgs> value)
0x5e94a  ldarg.0
0x5e94b  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.Activity::get_Services()
0x5e950  ldc.i4.1
0x5e951  call     T0x2B00012B
0x5e956  stloc.3
0x5e957  ldloc.1
0x5e958  brfalse.s loc_5E979
0x5e95a  ldloc.1
0x5e95b  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_RebootCheckBeforeInstall()
0x5e960  brfalse.s loc_5E979
0x5e962  ldloc.3
0x5e963  ldarg.0
0x5e964  call     instance string Microsoft.VisualStudio.Setup.Activities.Install::get_InstallDirectory()
0x5e969  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRestartManager::CheckSystemPendingReboot(string)
0x5e96e  brfalse.s loc_5E979
0x5e970  ldarg.0
0x5e971  ldloc.3
0x5e972  ldc.i4.1
0x5e973  ldc.i4.3
0x5e974  call     instance void Microsoft.VisualStudio.Setup.Activities.Activity::HandleRebootRequired(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRestartManager restartManager, bool isBeforeInstall, [opt] valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RebootType rebootType)
0x5e979  nop
0x5e97a  ldarg.0
0x5e97b  call     instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction Microsoft.VisualStudio.Setup.Activities.Install::get_RequestedAction()
0x5e980  ldc.i4.1
0x5e981  bne.un.s loc_5E98D
0x5e983  ldloc.1
0x5e984  brfalse.s loc_5E98D
0x5e986  ldarg.0
0x5e987  ldloc.1
0x5e988  call     instance void Microsoft.VisualStudio.Setup.Activities.Install::EnsureSufficientDiskSpaceAvailable(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage installable)
0x5e98d  nop
0x5e98e  ldarg.0
0x5e98f  call     instance void Microsoft.VisualStudio.Setup.Activities.Install::CachePackage()
0x5e994  leave    loc_5EA93
0x5e999  isinst   [mscorlib]System.Exception
0x5e99e  dup
0x5e99f  brtrue.s loc_5E9A5
0x5e9a1  pop
0x5e9a2  ldc.i4.0
0x5e9a3  br.s     loc_5E9C0
0x5e9a5  stloc.s  4
0x5e9a7  ldloc.s  4
0x5e9a9  isinst   [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.InvalidSignatureException
0x5e9ae  brtrue.s loc_5E9BC
0x5e9b0  ldloc.s  4
0x5e9b2  isinst   [mscorlib]System.IO.FileNotFoundException
0x5e9b7  ldnull
0x5e9b8  cgt.un
0x5e9ba  br.s     loc_5E9BD
0x5e9bc  ldc.i4.1
0x5e9bd  ldc.i4.0
0x5e9be  cgt.un
0x5e9c0  endfilter
0x5e9c2  pop
0x5e9c3  ldarg.0
0x5e9c4  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5e9c9  dup
0x5e9ca  brtrue.s loc_5E9CF
0x5e9cc  pop
0x5e9cd  br.s     loc_5E9F3
0x5e9cf  ldstr    aCacheFailedRet// "Cache failed. Retrying download of '"
0x5e9d4  ldarg.0
0x5e9d5  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.Activity::get_Package()
0x5e9da  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::GetUniqueId()
0x5e9df  ldstr    asc_7F7FA// "'."
0x5e9e4  call     string [mscorlib]System.String::Concat(string, string, string)
0x5e9e9  call     T0x2B000003
0x5e9ee  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x5e9f3  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x5e9f8  stloc.s  5
0x5e9fa  ldarg.0
0x5e9fb  ldfld    class Microsoft.VisualStudio.Setup.Activities.IDownloadPackageActivity Microsoft.VisualStudio.Setup.Activities.Install::download
0x5ea00  dup
0x5ea01  brtrue.s loc_5EA06
0x5ea03  pop
0x5ea04  br.s     loc_5EA0C
0x5ea06  ldarg.1
0x5ea07  callvirt instance void Microsoft.VisualStudio.Setup.Activities.IActivity::Run(valuetype [mscorlib]System.Threading.CancellationToken token)
0x5ea0c  ldarg.0
0x5ea0d  ldfld    class Microsoft.VisualStudio.Setup.Activities.IDownloadPackageActivity Microsoft.VisualStudio.Setup.Activities.Install::download
0x5ea12  dup
0x5ea13  brtrue.s loc_5EA18
0x5ea15  pop
0x5ea16  br.s     loc_5EA1D
0x5ea18  callvirt instance void Microsoft.VisualStudio.Setup.Activities.ISynchronizedActivity::Wait()
0x5ea1d  ldarg.0
0x5ea1e  ldarg.0
0x5ea1f  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.VisualStudio.Setup.Activities.Install::get_DownloadWaitTime()
0x5ea24  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x5ea29  ldloc.s  5
0x5ea2b  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x5ea30  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::op_Addition(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x5ea35  callvirt instance void Microsoft.VisualStudio.Setup.Activities.Install::set_DownloadWaitTime(valuetype [mscorlib]System.TimeSpan value)
0x5ea3a  ldarg.0
0x5ea3b  ldfld    class Microsoft.VisualStudio.Setup.Activities.IDownloadPackageActivity Microsoft.VisualStudio.Setup.Activities.Install::download
0x5ea40  dup
0x5ea41  brtrue.s loc_5EA47
0x5ea43  pop
0x5ea44  ldnull
0x5ea45  br.s     loc_5EA4C
0x5ea47  callvirt instance class [mscorlib]System.Exception Microsoft.VisualStudio.Setup.Activities.IActivity::get_Error()
0x5ea4c  brfalse.s loc_5EA88
0x5ea4e  ldarg.0
0x5ea4f  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5ea54  dup
0x5ea55  brtrue.s loc_5EA5A
0x5ea57  pop
0x5ea58  br.s     loc_5EA86
0x5ea5a  ldloc.s  4
0x5ea5c  ldstr    aSkipping0Of1Si// "Skipping {0} of '{1}' since downloading"...
0x5ea61  ldarg.0
0x5ea62  call     instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction Microsoft.VisualStudio.Setup.Activities.Install::get_RequestedAction()
0x5ea67  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction
0x5ea6c  ldarg.0
0x5ea6d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.Activity::get_Package()
0x5ea72  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::GetUniqueId()
0x5ea77  call     string [mscorlib]System.String::Format(string, object, object)
0x5ea7c  call     T0x2B000003
0x5ea81  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x5ea86  rethrow
0x5ea88  ldarg.0
0x5ea89  call     instance void Microsoft.VisualStudio.Setup.Activities.Install::CachePackage()
0x5ea8e  leave.s  loc_5EA93
0x5ea90  pop
0x5ea91  rethrow
0x5ea93  ldloc.2
0x5ea94  isinst   Microsoft.VisualStudio.Setup.Installer.InstallerBase
0x5ea99  dup
0x5ea9a  brtrue.s loc_5EA9F
0x5ea9c  pop
0x5ea9d  br.s     loc_5EAB9
0x5ea9f  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_AdditionalTelemetryProperties()
0x5eaa4  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEDOWNLOADWAITTIME
0x5eaa9  ldarg.0
0x5eaaa  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.VisualStudio.Setup.Activities.Install::get_DownloadWaitTime()
0x5eaaf  box      [mscorlib]System.TimeSpan
0x5eab4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x5eab9  ldarg.0
0x5eaba  call     instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction Microsoft.VisualStudio.Setup.Activities.Install::get_RequestedAction()
0x5eabf  ldc.i4.1
0x5eac0  bne.un.s loc_5EAFD
0x5eac2  ldarg.0
0x5eac3  ldloc.2
0x5eac4  ldarg.0
0x5eac5  call     instance string Microsoft.VisualStudio.Setup.Activities.Install::get_InstallDirectory()
0x5eaca  ldloc.1
0x5eacb  ldarg.0
0x5eacc  ldfld    class Microsoft.VisualStudio.Setup.Activities.IDownloadPackageActivity Microsoft.VisualStudio.Setup.Activities.Install::download
0x5ead1  dup
0x5ead2  brtrue.s loc_5EAD8
0x5ead4  pop
0x5ead5  ldnull
0x5ead6  br.s     loc_5EADD
0x5ead8  callvirt instance string Microsoft.VisualStudio.Setup.Activities.IDownloadPackageActivity::get_Directory()
0x5eadd  dup
0x5eade  brtrue.s loc_5EAE7
0x5eae0  pop
0x5eae1  ldarg.0
0x5eae2  ldfld    string Microsoft.VisualStudio.Setup.Activities.Install::localPath
0x5eae7  ldarg.0
0x5eae8  ldfld    valuetype [mscorlib]System.Nullable`1<bool> Microsoft.VisualStudio.Setup.Activities.Install::softDetectionHint
0x5eaed  ldarg.1
0x5eaee  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.IInstaller::Install(string destination, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage package, string path, [opt] valuetype [mscorlib]System.Nullable`1<bool> isDetected, [opt] valuetype [mscorlib]System.Threading.CancellationToken token)
0x5eaf3  call     instance void Microsoft.VisualStudio.Setup.Activities.Install::set_ReturnCode(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult value)
0x5eaf8  br       loc_5EB7D
0x5eafd  ldarg.0
0x5eafe  call     instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction Microsoft.VisualStudio.Setup.Activities.Install::get_RequestedAction()
0x5eb03  ldc.i4.2
0x5eb04  bne.un.s loc_5EB3E
0x5eb06  ldarg.0
0x5eb07  ldloc.2
0x5eb08  ldarg.0
0x5eb09  call     instance string Microsoft.VisualStudio.Setup.Activities.Install::get_InstallDirectory()
0x5eb0e  ldloc.1
0x5eb0f  ldarg.0
0x5eb10  ldfld    class Microsoft.VisualStudio.Setup.Activities.IDownloadPackageActivity Microsoft.VisualStudio.Setup.Activities.Install::download
0x5eb15  dup
0x5eb16  brtrue.s loc_5EB1C
0x5eb18  pop
0x5eb19  ldnull
0x5eb1a  br.s     loc_5EB21
0x5eb1c  callvirt instance string Microsoft.VisualStudio.Setup.Activities.IDownloadPackageActivity::get_Directory()
0x5eb21  dup
0x5eb22  brtrue.s loc_5EB2B
0x5eb24  pop
0x5eb25  ldarg.0
0x5eb26  ldfld    string Microsoft.VisualStudio.Setup.Activities.Install::localPath
0x5eb2b  ldarg.0
0x5eb2c  ldfld    valuetype [mscorlib]System.Nullable`1<bool> Microsoft.VisualStudio.Setup.Activities.Install::softDetectionHint
0x5eb31  ldarg.1
0x5eb32  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.IInstaller::Repair(string destination, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage package, [opt] string path, [opt] valuetype [mscorlib]System.Nullable`1<bool> isDetected, [opt] valuetype [mscorlib]System.Threading.CancellationToken token)
0x5eb37  call     instance void Microsoft.VisualStudio.Setup.Activities.Install::set_ReturnCode(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult value)
0x5eb3c  br.s     loc_5EB7D
0x5eb3e  ldarg.0
0x5eb3f  call     instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction Microsoft.VisualStudio.Setup.Activities.Install::get_RequestedAction()
0x5eb44  ldc.i4.3
  ... truncated ...
```
