# System.Deployment.Application.ApplicationActivator::InstallApplication

- ea: `0xb960`
- end: `0xba07`
- name: `System.Deployment.Application.ApplicationActivator::InstallApplication`
- size: `167`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0xae50`
- `0xb830`

## callees

- `0xb960`
- `0xba10`
- `0xba90`
- `0x13110`
- `0x17cc0`
- `0x17cd0`
- `0x1f1c0`
- `0x1f890`
- `0x1fad0`
- `0x23020`

## string_xrefs

- `0xb962`: `InstallApplication called.`
- `0xb96c`: `PhaseLog_InstallApplication`
- `0xb9d3`: `PhaseLog_CommitApplication`

## pseudocode

```c

```

## disassembly

```asm
0xb960  ldc.i4.0
0xb961  stloc.0
0xb962  ldstr    aInstallapplica// "InstallApplication called."
0xb967  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0xb96c  ldstr    aPhaselogInstal_0// "PhaseLog_InstallApplication"
0xb971  call     string System.Deployment.Application.Resources::GetString(string s)
0xb976  call     void System.Deployment.Application.Logger::AddPhaseInformation(string message)
0xb97b  ldarg.0
0xb97c  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.ApplicationActivator::_subStore
0xb981  ldarg.1
0xb982  ldind.ref
0xb983  ldarg.2
0xb984  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0xb989  callvirt instance void System.Deployment.Application.SubscriptionStore::CheckDeploymentSubscriptionState(class System.Deployment.Application.SubscriptionState subState, class System.Deployment.Application.Manifest.AssemblyManifest deployment)
0xb98e  ldarg.0
0xb98f  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.ApplicationActivator::_subStore
0xb994  ldloca.s 1
0xb996  callvirt instance class [mscorlib]System.IO.FileStream System.Deployment.Application.SubscriptionStore::AcquireReferenceTransaction([out] int64& transactionId)
0xb99b  stloc.2
0xb99c  ldnull
0xb99d  stloc.3
0xb99e  ldarg.0
0xb99f  ldarg.1
0xb9a0  ldind.ref
0xb9a1  ldarg.2
0xb9a2  ldloc.1
0xb9a3  ldloca.s 3
0xb9a5  call     instance bool System.Deployment.Application.ApplicationActivator::DownloadApplication(class System.Deployment.Application.SubscriptionState subState, class System.Deployment.Application.ActivationDescription actDesc, int64 transactionId, [out] class System.Deployment.Application.TempDirectory& downloadTemp)
0xb9aa  stloc.0
0xb9ab  ldarg.2
0xb9ac  ldc.i4.1
0xb9ad  stfld    bool System.Deployment.Application.CommitApplicationParams::CommitDeploy
0xb9b2  ldarg.2
0xb9b3  ldc.i4.1
0xb9b4  stfld    bool System.Deployment.Application.CommitApplicationParams::IsConfirmed
0xb9b9  ldarg.2
0xb9ba  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xb9bf  stfld    valuetype [mscorlib]System.DateTime System.Deployment.Application.CommitApplicationParams::TimeStamp
0xb9c4  ldarg.2
0xb9c5  ldfld    bool System.Deployment.Application.CommitApplicationParams::CommitApp
0xb9ca  brfalse.s loc_B9D3
0xb9cc  ldarg.0
0xb9cd  ldarg.2
0xb9ce  call     instance void System.Deployment.Application.ApplicationActivator::SetMarkOfTheWebIfNeeded(class System.Deployment.Application.CommitApplicationParams p)
0xb9d3  ldstr    aPhaselogCommit// "PhaseLog_CommitApplication"
0xb9d8  call     string System.Deployment.Application.Resources::GetString(string s)
0xb9dd  call     void System.Deployment.Application.Logger::AddPhaseInformation(string message)
0xb9e2  ldarg.0
0xb9e3  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.ApplicationActivator::_subStore
0xb9e8  ldarg.1
0xb9e9  ldarg.2
0xb9ea  callvirt instance void System.Deployment.Application.SubscriptionStore::CommitApplication(class System.Deployment.Application.SubscriptionState& subState, class System.Deployment.Application.CommitApplicationParams commitParams)
0xb9ef  leave.s  loc_BA05
0xb9f1  ldloc.3
0xb9f2  brfalse.s loc_B9FA
0xb9f4  ldloc.3
0xb9f5  callvirt instance void System.Deployment.Application.DisposableBase::Dispose()
0xb9fa  endfinally
0xb9fb  ldloc.2
0xb9fc  brfalse.s loc_BA04
0xb9fe  ldloc.2
0xb9ff  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xba04  endfinally
0xba05  ldloc.0
0xba06  ret
```
