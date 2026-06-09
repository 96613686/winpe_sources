# System.Deployment.Application.GetManifestCompletedEventArgs::.ctor

- ea: `0x168a0`
- end: `0x169f2`
- name: `System.Deployment.Application.GetManifestCompletedEventArgs::.ctor`
- size: `338`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x162f0`

## callees

- `0xd590`
- `0xd600`
- `0xda80`
- `0xdbd0`
- `0x12710`
- `0x12720`
- `0x12730`
- `0x168a0`
- `0x17d30`
- `0x23c40`
- `0x24b30`

## string_xrefs

- `0x168d6`: `Creating GetManifestCompletedEventArgs.`
- `0x16970`: `IsCached=`

## pseudocode

```c

```

## disassembly

```asm
0x168a0  ldarg.0
0x168a1  ldarg.1
0x168a2  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x168a7  ldarg.1
0x168a8  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x168ad  ldarg.1
0x168ae  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x168b3  call     instance void [System]System.ComponentModel.AsyncCompletedEventArgs::.ctor(class [mscorlib]System.Exception, bool, object)
0x168b8  ldarg.0
0x168b9  ldarg.1
0x168ba  callvirt instance class [mscorlib]System.ActivationContext System.Deployment.Application.BindCompletedEventArgs::get_ActivationContext()
0x168bf  brtrue.s loc_168C4
0x168c1  ldnull
0x168c2  br.s     loc_168CF
0x168c4  ldarg.1
0x168c5  callvirt instance class [mscorlib]System.ActivationContext System.Deployment.Application.BindCompletedEventArgs::get_ActivationContext()
0x168ca  callvirt instance class [mscorlib]System.ApplicationIdentity [mscorlib]System.ActivationContext::get_Identity()
0x168cf  stfld    class [mscorlib]System.ApplicationIdentity System.Deployment.Application.GetManifestCompletedEventArgs::_applicationIdentity
0x168d4  ldarg.s  4
0x168d6  ldstr    aCreatingGetman// "Creating GetManifestCompletedEventArgs."
0x168db  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x168e0  ldarg.0
0x168e1  ldfld    class [mscorlib]System.ApplicationIdentity System.Deployment.Application.GetManifestCompletedEventArgs::_applicationIdentity
0x168e6  callvirt instance string [mscorlib]System.Object::ToString()
0x168eb  stloc.0
0x168ec  ldloc.0
0x168ed  newobj   instance void System.Deployment.Application.DefinitionAppId::.ctor(string text)
0x168f2  stloc.1
0x168f3  ldloc.1
0x168f4  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.DefinitionAppId::get_DeploymentIdentity()
0x168f9  stloc.2
0x168fa  ldarg.0
0x168fb  ldloc.2
0x168fc  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.DefinitionIdentity::ToSubscriptionId()
0x16901  stfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.GetManifestCompletedEventArgs::_subId
0x16906  ldarg.0
0x16907  ldarg.3
0x16908  stfld    string System.Deployment.Application.GetManifestCompletedEventArgs::_logFilePath
0x1690d  ldarg.0
0x1690e  ldarg.1
0x1690f  callvirt instance bool System.Deployment.Application.BindCompletedEventArgs::get_IsCached()
0x16914  stfld    bool System.Deployment.Application.GetManifestCompletedEventArgs::_isCached
0x16919  ldarg.0
0x1691a  ldarg.1
0x1691b  callvirt instance string System.Deployment.Application.BindCompletedEventArgs::get_FriendlyName()
0x16920  stfld    string System.Deployment.Application.GetManifestCompletedEventArgs::_name
0x16925  ldarg.0
0x16926  ldarg.1
0x16927  callvirt instance class [mscorlib]System.ActivationContext System.Deployment.Application.BindCompletedEventArgs::get_ActivationContext()
0x1692c  stfld    class [mscorlib]System.ActivationContext System.Deployment.Application.GetManifestCompletedEventArgs::_actContext
0x16931  ldarg.s  4
0x16933  ldstr    aApplicationIde// "Application identity="
0x16938  ldloc.0
0x16939  call     string [mscorlib]System.String::Concat(string, string)
0x1693e  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x16943  ldarg.s  4
0x16945  ldstr    aSubscriptionId// "Subscription identity="
0x1694a  ldarg.0
0x1694b  ldfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.GetManifestCompletedEventArgs::_subId
0x16950  brtrue.s loc_16959
0x16952  ldstr    aNull// "null"
0x16957  br.s     loc_16964
0x16959  ldarg.0
0x1695a  ldfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.GetManifestCompletedEventArgs::_subId
0x1695f  callvirt instance string [mscorlib]System.Object::ToString()
0x16964  call     string [mscorlib]System.String::Concat(string, string)
0x16969  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x1696e  ldarg.s  4
0x16970  ldstr    aIscached// "IsCached="
0x16975  ldarg.0
0x16976  ldflda   bool System.Deployment.Application.GetManifestCompletedEventArgs::_isCached
0x1697b  call     instance string [mscorlib]System.Boolean::ToString()
0x16980  call     string [mscorlib]System.String::Concat(string, string)
0x16985  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x1698a  ldarg.0
0x1698b  ldfld    bool System.Deployment.Application.GetManifestCompletedEventArgs::_isCached
0x16990  brfalse.s loc_169B4
0x16992  ldarg.0
0x16993  ldarg.1
0x16994  callvirt instance class [mscorlib]System.ActivationContext System.Deployment.Application.BindCompletedEventArgs::get_ActivationContext()
0x16999  callvirt instance unsigned int8[] [mscorlib]System.ActivationContext::get_DeploymentManifestBytes()
0x1699e  stfld    unsigned int8[] System.Deployment.Application.GetManifestCompletedEventArgs::_rawDeploymentManifest
0x169a3  ldarg.0
0x169a4  ldarg.1
0x169a5  callvirt instance class [mscorlib]System.ActivationContext System.Deployment.Application.BindCompletedEventArgs::get_ActivationContext()
0x169aa  callvirt instance unsigned int8[] [mscorlib]System.ActivationContext::get_ApplicationManifestBytes()
0x169af  stfld    unsigned int8[] System.Deployment.Application.GetManifestCompletedEventArgs::_rawApplicationManifest
0x169b4  ldarg.0
0x169b5  ldarg.2
0x169b6  stfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.GetManifestCompletedEventArgs::_activationDescription
0x169bb  ldarg.0
0x169bc  ldarg.0
0x169bd  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.GetManifestCompletedEventArgs::_activationDescription
0x169c2  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.CommitApplicationParams::AppId
0x169c7  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.DefinitionAppId::get_DeploymentIdentity()
0x169cc  callvirt instance class [mscorlib]System.Version System.Deployment.Application.DefinitionIdentity::get_Version()
0x169d1  stfld    class [mscorlib]System.Version System.Deployment.Application.GetManifestCompletedEventArgs::_version
0x169d6  ldarg.0
0x169d7  ldarg.0
0x169d8  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.GetManifestCompletedEventArgs::_activationDescription
0x169dd  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0x169e2  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x169e7  callvirt instance class [System]System.Uri System.Deployment.Application.Manifest.Description::get_SupportUri()
0x169ec  stfld    class [System]System.Uri System.Deployment.Application.GetManifestCompletedEventArgs::_support
0x169f1  ret
```
