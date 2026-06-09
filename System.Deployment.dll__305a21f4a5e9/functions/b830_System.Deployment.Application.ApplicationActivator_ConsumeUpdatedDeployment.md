# System.Deployment.Application.ApplicationActivator::ConsumeUpdatedDeployment

- ea: `0xb830`
- end: `0xb957`
- name: `System.Deployment.Application.ApplicationActivator::ConsumeUpdatedDeployment`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0xb4c0`

## callees

- `0xb830`
- `0xb960`
- `0x17cc0`
- `0x17d40`
- `0x17d50`
- `0x1efa0`
- `0x1f7d0`
- `0x21c10`
- `0x21ee0`
- `0x228d0`
- `0x23020`
- `0x23c30`
- `0x23c50`
- `0x24970`

## string_xrefs

- `0xb845`: `PhaseLog_ConsumeUpdatedDeployment`
- `0xb854`: `Consuming new update.`
- `0xb869`: `Update is not a required update.`
- `0xb884`: `UI_UpdateTitle`
- `0xb8f7`: `Upd_DeployUpdateSkipping`
- `0xb906`: `User has decided to skip the update.`
- `0xb916`: `Do not update now, but prompt for update on next activation.`
- `0xb94c`: `Update consumed.`

## pseudocode

```c

```

## disassembly

```asm
0xb830  ldarg.2
0xb831  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0xb836  stloc.0
0xb837  ldloc.0
0xb838  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0xb83d  stloc.1
0xb83e  ldarg.2
0xb83f  ldfld    class [System]System.Uri System.Deployment.Application.CommitApplicationParams::DeploySourceUri
0xb844  stloc.2
0xb845  ldstr    aPhaselogConsum// "PhaseLog_ConsumeUpdatedDeployment"
0xb84a  call     string System.Deployment.Application.Resources::GetString(string s)
0xb84f  call     void System.Deployment.Application.Logger::AddPhaseInformation(string message)
0xb854  ldstr    aConsumingNewUp// "Consuming new update."
0xb859  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xb85e  ldarg.2
0xb85f  ldfld    bool System.Deployment.Application.CommitApplicationParams::IsRequiredUpdate
0xb864  brtrue   loc_B921
0xb869  ldstr    aUpdateIsNotARe// "Update is not a required update."
0xb86e  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xb873  ldarg.1
0xb874  ldind.ref
0xb875  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.SubscriptionState::get_EffectiveDescription()
0xb87a  stloc.3
0xb87b  newobj   instance void System.Deployment.Application.UserInterfaceInfo::.ctor()
0xb880  stloc.s  4
0xb882  ldloc.s  4
0xb884  ldstr    aUiUpdatetitle// "UI_UpdateTitle"
0xb889  call     string System.Deployment.Application.Resources::GetString(string s)
0xb88e  stfld    string System.Deployment.Application.UserInterfaceInfo::formTitle
0xb893  ldloc.s  4
0xb895  ldloc.3
0xb896  callvirt instance string System.Deployment.Application.Manifest.Description::get_Product()
0xb89b  stfld    string System.Deployment.Application.UserInterfaceInfo::productName
0xb8a0  ldloc.s  4
0xb8a2  ldloc.3
0xb8a3  callvirt instance string System.Deployment.Application.Manifest.Description::get_SupportUrl()
0xb8a8  stfld    string System.Deployment.Application.UserInterfaceInfo::supportUrl
0xb8ad  ldloc.s  4
0xb8af  ldloc.2
0xb8b0  call     string System.Deployment.Application.UserInterface::GetDisplaySite(class [System]System.Uri sourceUri)
0xb8b5  stfld    string System.Deployment.Application.UserInterfaceInfo::sourceSite
0xb8ba  ldarg.0
0xb8bb  ldfld    class System.Deployment.Application.UserInterface System.Deployment.Application.ApplicationActivator::_ui
0xb8c0  ldloc.s  4
0xb8c2  callvirt instance valuetype System.Deployment.Application.UserInterfaceModalResult System.Deployment.Application.UserInterface::ShowUpdate(class System.Deployment.Application.UserInterfaceInfo info)
0xb8c7  stloc.s  5
0xb8c9  ldloc.s  5
0xb8cb  ldc.i4.3
0xb8cc  bne.un.s loc_B911
0xb8ce  ldloca.s 6
0xb8d0  ldc.i4.7
0xb8d1  ldc.i4.0
0xb8d2  ldc.i4.0
0xb8d3  ldc.i4.0
0xb8d4  call     instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32, int32)
0xb8d9  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xb8de  ldloc.s  6
0xb8e0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0xb8e5  stloc.s  7
0xb8e7  ldarg.0
0xb8e8  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.ApplicationActivator::_subStore
0xb8ed  ldarg.1
0xb8ee  ldind.ref
0xb8ef  ldloc.1
0xb8f0  ldloc.s  7
0xb8f2  callvirt instance void System.Deployment.Application.SubscriptionStore::SetUpdateSkipTime(class System.Deployment.Application.SubscriptionState subState, class System.Deployment.Application.DefinitionIdentity updateSkippedDeployment, valuetype [mscorlib]System.DateTime updateSkipTime)
0xb8f7  ldstr    aUpdDeployupdat// "Upd_DeployUpdateSkipping"
0xb8fc  call     string System.Deployment.Application.Resources::GetString(string s)
0xb901  call     void System.Deployment.Application.Logger::AddPhaseInformation(string message)
0xb906  ldstr    aUserHasDecided// "User has decided to skip the update."
0xb90b  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xb910  ret
0xb911  ldloc.s  5
0xb913  ldc.i4.2
0xb914  bne.un.s loc_B921
0xb916  ldstr    aDoNotUpdateNow// "Do not update now, but prompt for updat"...
0xb91b  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xb920  ret
0xb921  ldarg.0
0xb922  ldarg.1
0xb923  ldarg.2
0xb924  call     instance bool System.Deployment.Application.ApplicationActivator::InstallApplication(class System.Deployment.Application.SubscriptionState& subState, class System.Deployment.Application.ActivationDescription actDesc)
0xb929  pop
0xb92a  ldstr    aUpdConsumed// "Upd_Consumed"
0xb92f  call     string System.Deployment.Application.Resources::GetString(string s)
0xb934  ldc.i4.2
0xb935  newarr   [mscorlib]System.Object
0xb93a  dup
0xb93b  ldc.i4.0
0xb93c  ldloc.1
0xb93d  callvirt instance string [mscorlib]System.Object::ToString()
0xb942  stelem.ref
0xb943  dup
0xb944  ldc.i4.1
0xb945  ldloc.2
0xb946  stelem.ref
0xb947  call     void System.Deployment.Application.Logger::AddPhaseInformation(string messageFormat, object[] args)
0xb94c  ldstr    aUpdateConsumed// "Update consumed."
0xb951  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xb956  ret
```
