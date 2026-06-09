# System.Deployment.Application.DeploymentManager::DetermineTrustCore

- ea: `0x11b00`
- end: `0x11ca9`
- name: `System.Deployment.Application.DeploymentManager::DetermineTrustCore`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x10d40`

## callees

- `0xd750`
- `0xd880`
- `0x11b00`
- `0x12600`
- `0x12660`
- `0x17ce0`
- `0x17d30`
- `0x1ed00`
- `0x1ed40`
- `0x1efe0`
- `0x1f8b0`
- `0x20220`
- `0x23020`
- `0x23fe0`
- `0x24b90`

## string_xrefs

- `0x11b8a`: `Application family is installed but effective certificate public key token has changed between versions: subState.EffectiveCertificatePublicKeyToken=`
- `0x11b95`: `,_actDesc.EffectiveCertificatePublicKeyToken=`
- `0x11bb5`: `Removing cached trust for the CurrentBind.`

## pseudocode

```c

```

## disassembly

```asm
0x11b00  ldarg.0
0x11b01  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x11b06  ldstr    aDeploymentmana_2// "DeploymentManager.DetermineTrustCore() "...
0x11b0b  call     void System.Deployment.Application.Logger::AddMethodCall(class LogIdentity log, string message)
0x11b10  ldarg.0
0x11b11  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.DeploymentManager::_subStore
0x11b16  ldarg.0
0x11b17  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11b1c  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0x11b21  callvirt instance class System.Deployment.Application.SubscriptionState System.Deployment.Application.SubscriptionStore::GetSubscriptionState(class System.Deployment.Application.Manifest.AssemblyManifest deployment)
0x11b26  stloc.0
0x11b27  newobj   instance void [mscorlib]System.Security.Policy.TrustManagerContext::.ctor()
0x11b2c  stloc.1
0x11b2d  ldloc.1
0x11b2e  ldc.i4.0
0x11b2f  callvirt instance void [mscorlib]System.Security.Policy.TrustManagerContext::set_IgnorePersistedDecision(bool)
0x11b34  ldloc.1
0x11b35  ldc.i4.0
0x11b36  callvirt instance void [mscorlib]System.Security.Policy.TrustManagerContext::set_NoPrompt(bool)
0x11b3b  ldloc.1
0x11b3c  ldc.i4.1
0x11b3d  callvirt instance void [mscorlib]System.Security.Policy.TrustManagerContext::set_Persist(bool)
0x11b42  ldarg.2
0x11b43  brfalse.s loc_11B51
0x11b45  ldloc.1
0x11b46  ldarg.2
0x11b47  callvirt instance bool System.Deployment.Application.TrustParams::get_NoPrompt()
0x11b4c  callvirt instance void [mscorlib]System.Security.Policy.TrustManagerContext::set_NoPrompt(bool)
0x11b51  ldarg.1
0x11b52  brtrue.s loc_11B63
0x11b54  ldarg.0
0x11b55  ldfld    bool System.Deployment.Application.DeploymentManager::_cancellationPending
0x11b5a  brfalse.s loc_11B63
0x11b5c  ldc.i4.1
0x11b5d  stloc.3
0x11b5e  leave    loc_11CA7
0x11b63  ldloc.0
0x11b64  callvirt instance bool System.Deployment.Application.SubscriptionState::get_IsInstalled()
0x11b69  brfalse.s loc_11BCA
0x11b6b  ldloc.0
0x11b6c  callvirt instance string System.Deployment.Application.SubscriptionState::get_EffectiveCertificatePublicKeyToken()
0x11b71  ldarg.0
0x11b72  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11b77  callvirt instance string System.Deployment.Application.CommitApplicationParams::get_EffectiveCertificatePublicKeyToken()
0x11b7c  ldc.i4.4
0x11b7d  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x11b82  brtrue.s loc_11BCA
0x11b84  ldarg.0
0x11b85  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x11b8a  ldstr    aApplicationFam_2// "Application family is installed but eff"...
0x11b8f  ldloc.0
0x11b90  callvirt instance string System.Deployment.Application.SubscriptionState::get_EffectiveCertificatePublicKeyToken()
0x11b95  ldstr    aActdescEffecti_0// ",_actDesc.EffectiveCertificatePublicKey"...
0x11b9a  ldarg.0
0x11b9b  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11ba0  callvirt instance string System.Deployment.Application.CommitApplicationParams::get_EffectiveCertificatePublicKeyToken()
0x11ba5  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x11baa  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x11baf  ldarg.0
0x11bb0  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x11bb5  ldstr    aRemovingCached// "Removing cached trust for the CurrentBi"...
0x11bba  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x11bbf  ldloc.0
0x11bc0  callvirt instance class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionState::get_CurrentBind()
0x11bc5  call     void System.Deployment.Application.ApplicationTrust::RemoveCachedTrust(class System.Deployment.Application.DefinitionAppId appId)
0x11bca  ldc.i4.0
0x11bcb  stloc.2
0x11bcc  ldarg.0
0x11bcd  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11bd2  ldfld    bool System.Deployment.Application.CommitApplicationParams::IsUpdate
0x11bd7  brfalse.s loc_11BDB
0x11bd9  ldc.i4.1
0x11bda  stloc.2
0x11bdb  ldarg.0
0x11bdc  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11be1  ldfld    bool System.Deployment.Application.CommitApplicationParams::IsUpdateInPKTGroup
0x11be6  brfalse.s loc_11C0E
0x11be8  ldc.i4.0
0x11be9  stloc.2
0x11bea  ldarg.0
0x11beb  ldfld    class [mscorlib]System.ActivationContext System.Deployment.Application.DeploymentManager::_actCtx
0x11bf0  newobj   instance void [mscorlib]System.Security.Policy.ApplicationSecurityInfo::.ctor(class [mscorlib]System.ActivationContext)
0x11bf5  stloc.s  4
0x11bf7  ldarg.0
0x11bf8  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11bfd  ldloc.s  4
0x11bff  callvirt instance class [mscorlib]System.Security.PermissionSet [mscorlib]System.Security.Policy.ApplicationSecurityInfo::get_DefaultRequestSet()
0x11c04  callvirt instance bool [mscorlib]System.Security.PermissionSet::IsUnrestricted()
0x11c09  stfld    bool System.Deployment.Application.CommitApplicationParams::IsFullTrustRequested
0x11c0e  ldarg.0
0x11c0f  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11c14  ldloc.0
0x11c15  ldarg.0
0x11c16  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11c1b  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0x11c20  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0x11c25  callvirt instance bool System.Deployment.Application.Manifest.Deployment::get_Install()
0x11c2a  ldloc.2
0x11c2b  ldarg.0
0x11c2c  ldfld    class [mscorlib]System.ActivationContext System.Deployment.Application.DeploymentManager::_actCtx
0x11c31  ldloc.1
0x11c32  call     class [mscorlib]System.Security.Policy.ApplicationTrust System.Deployment.Application.ApplicationTrust::RequestTrust(class System.Deployment.Application.SubscriptionState subState, bool isShellVisible, bool isUpdate, class [mscorlib]System.ActivationContext actCtx, class [mscorlib]System.Security.Policy.TrustManagerContext tmc)
0x11c37  stfld    class [mscorlib]System.Security.Policy.ApplicationTrust System.Deployment.Application.CommitApplicationParams::Trust
0x11c3c  leave.s  loc_11CA5
0x11c3e  stloc.s  5
0x11c40  ldarg.0
0x11c41  ldstr    aExDeterminetru// "Ex_DetermineTrustFailed"
0x11c46  call     string System.Deployment.Application.Resources::GetString(string s)
0x11c4b  ldloc.s  5
0x11c4d  call     instance void System.Deployment.Application.DeploymentManager::LogError(string message, class [mscorlib]System.Exception ex)
0x11c52  ldarg.0
0x11c53  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x11c58  ldc.i4.6
0x11c59  newarr   [mscorlib]System.String
0x11c5e  dup
0x11c5f  ldc.i4.0
0x11c60  ldstr    aExceptionThrow_2// "Exception thrown in  DetermineTrustCore"...
0x11c65  stelem.ref
0x11c66  dup
0x11c67  ldc.i4.1
0x11c68  ldloc.s  5
0x11c6a  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x11c6f  callvirt instance string [mscorlib]System.Object::ToString()
0x11c74  stelem.ref
0x11c75  dup
0x11c76  ldc.i4.2
0x11c77  ldstr    asc_3345E// " : "
0x11c7c  stelem.ref
0x11c7d  dup
0x11c7e  ldc.i4.3
0x11c7f  ldloc.s  5
0x11c81  callvirt instance string [mscorlib]System.Exception::get_Message()
0x11c86  stelem.ref
0x11c87  dup
0x11c88  ldc.i4.4
0x11c89  ldstr    asc_3279C// "\r\n"
0x11c8e  stelem.ref
0x11c8f  dup
0x11c90  ldc.i4.5
0x11c91  ldloc.s  5
0x11c93  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x11c98  stelem.ref
0x11c99  call     string [mscorlib]System.String::Concat(string[])
0x11c9e  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x11ca3  rethrow
0x11ca5  ldc.i4.0
0x11ca6  ret
0x11ca7  ldloc.3
0x11ca8  ret
```
