# System.Deployment.Application.ApplicationTrust::RequestTrust_0

- ea: `0xd750`
- end: `0xd876`
- name: `System.Deployment.Application.ApplicationTrust::RequestTrust_0`
- size: `294`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0xd720`
- `0x11b00`

## callees

- `0xd640`
- `0xd750`
- `0x14780`
- `0x14790`
- `0x14880`
- `0x17cd0`
- `0x17d40`
- `0x17f10`
- `0x1ed00`
- `0x1ed20`
- `0x1ed40`
- `0x23020`

## string_xrefs

- `0xd76a`: `, isUpdate=`
- `0xd77c`: `, subState.IsInstalled=`
- `0xd7d5`: `Calling ApplicationSecurityManager.DetermineApplicationTrust().`

## pseudocode

```c

```

## disassembly

```asm
0xd750  ldc.i4.7
0xd751  newarr   [mscorlib]System.String
0xd756  dup
0xd757  ldc.i4.0
0xd758  ldstr    aApplicationtru// "ApplicationTrust.RequestTrust(isShellVi"...
0xd75d  stelem.ref
0xd75e  dup
0xd75f  ldc.i4.1
0xd760  ldarga.s 1
0xd762  call     instance string [mscorlib]System.Boolean::ToString()
0xd767  stelem.ref
0xd768  dup
0xd769  ldc.i4.2
0xd76a  ldstr    aIsupdate// ", isUpdate="
0xd76f  stelem.ref
0xd770  dup
0xd771  ldc.i4.3
0xd772  ldarga.s 2
0xd774  call     instance string [mscorlib]System.Boolean::ToString()
0xd779  stelem.ref
0xd77a  dup
0xd77b  ldc.i4.4
0xd77c  ldstr    aSubstateIsinst// ", subState.IsInstalled="
0xd781  stelem.ref
0xd782  dup
0xd783  ldc.i4.5
0xd784  ldarg.0
0xd785  callvirt instance bool System.Deployment.Application.SubscriptionState::get_IsInstalled()
0xd78a  stloc.2
0xd78b  ldloca.s 2
0xd78d  call     instance string [mscorlib]System.Boolean::ToString()
0xd792  stelem.ref
0xd793  dup
0xd794  ldc.i4.6
0xd795  ldstr    aCalled// ") called."
0xd79a  stelem.ref
0xd79b  call     string [mscorlib]System.String::Concat(string[])
0xd7a0  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0xd7a5  ldarg.0
0xd7a6  callvirt instance bool System.Deployment.Application.SubscriptionState::get_IsInstalled()
0xd7ab  brfalse.s loc_D7B6
0xd7ad  ldarg.0
0xd7ae  callvirt instance bool System.Deployment.Application.SubscriptionState::get_IsShellVisible()
0xd7b3  ldarg.1
0xd7b4  beq.s    loc_D7BE
0xd7b6  ldarg.s  4
0xd7b8  ldc.i4.1
0xd7b9  callvirt instance void [mscorlib]System.Security.Policy.TrustManagerContext::set_IgnorePersistedDecision(bool)
0xd7be  ldarg.2
0xd7bf  brfalse.s loc_D7D3
0xd7c1  ldarg.s  4
0xd7c3  ldarg.0
0xd7c4  callvirt instance class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionState::get_CurrentBind()
0xd7c9  callvirt instance class [mscorlib]System.ApplicationIdentity System.Deployment.Application.DefinitionAppId::ToApplicationIdentity()
0xd7ce  callvirt instance void [mscorlib]System.Security.Policy.TrustManagerContext::set_PreviousApplicationIdentity(class [mscorlib]System.ApplicationIdentity)
0xd7d3  ldc.i4.0
0xd7d4  stloc.0
0xd7d5  ldstr    aCallingApplica// "Calling ApplicationSecurityManager.Dete"...
0xd7da  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xd7df  ldstr    aTrustManagerCo// "Trust Manager Context="
0xd7e4  ldarg.s  4
0xd7e6  call     string System.Deployment.Application.Logger::Serialize(class [mscorlib]System.Security.Policy.TrustManagerContext tmc)
0xd7eb  call     string [mscorlib]System.String::Concat(string, string)
0xd7f0  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xd7f5  ldarg.3
0xd7f6  ldarg.s  4
0xd7f8  call     bool [mscorlib]System.Security.Policy.ApplicationSecurityManager::DetermineApplicationTrust(class [mscorlib]System.ActivationContext, class [mscorlib]System.Security.Policy.TrustManagerContext)
0xd7fd  stloc.0
0xd7fe  leave.s  loc_D812
0xd800  stloc.3
0xd801  ldstr    aExInvalidtrust// "Ex_InvalidTrustInfo"
0xd806  call     string System.Deployment.Application.Resources::GetString(string s)
0xd80b  ldloc.3
0xd80c  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(string message, class [mscorlib]System.Exception innerException)
0xd811  throw
0xd812  ldloc.0
0xd813  brtrue.s loc_D825
0xd815  ldstr    aExNotrust// "Ex_NoTrust"
0xd81a  call     string System.Deployment.Application.Resources::GetString(string s)
0xd81f  newobj   instance void System.Deployment.Application.TrustNotGrantedException::.ctor(string message)
0xd824  throw
0xd825  ldstr    aTrustGranted// "Trust granted."
0xd82a  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xd82f  ldnull
0xd830  stloc.1
0xd831  ldc.i4.0
0xd832  stloc.s  4
0xd834  br.s     loc_D85C
0xd836  call     class [mscorlib]System.Security.Policy.ApplicationTrustCollection [mscorlib]System.Security.Policy.ApplicationSecurityManager::get_UserApplicationTrusts()
0xd83b  ldarg.3
0xd83c  callvirt instance class [mscorlib]System.ApplicationIdentity [mscorlib]System.ActivationContext::get_Identity()
0xd841  callvirt instance string [mscorlib]System.ApplicationIdentity::get_FullName()
0xd846  callvirt instance class [mscorlib]System.Security.Policy.ApplicationTrust [mscorlib]System.Security.Policy.ApplicationTrustCollection::get_Item(string)
0xd84b  stloc.1
0xd84c  ldloc.1
0xd84d  brtrue.s loc_D861
0xd84f  ldc.i4.s 0xA
0xd851  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0xd856  ldloc.s  4
0xd858  ldc.i4.1
0xd859  add
0xd85a  stloc.s  4
0xd85c  ldloc.s  4
0xd85e  ldc.i4.5
0xd85f  blt.s    loc_D836
0xd861  ldloc.1
0xd862  brtrue.s loc_D874
0xd864  ldstr    aExInvalidmatch// "Ex_InvalidMatchTrust"
0xd869  call     string System.Deployment.Application.Resources::GetString(string s)
0xd86e  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(string message)
0xd873  throw
0xd874  ldloc.1
0xd875  ret
```
