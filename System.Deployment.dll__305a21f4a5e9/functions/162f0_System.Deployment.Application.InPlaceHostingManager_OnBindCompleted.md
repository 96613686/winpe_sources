# System.Deployment.Application.InPlaceHostingManager::OnBindCompleted

- ea: `0x162f0`
- end: `0x165f9`
- name: `System.Deployment.Application.InPlaceHostingManager::OnBindCompleted`
- size: `777`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x110e0`
- `0x11240`
- `0x12730`
- `0x162f0`
- `0x16780`
- `0x16830`
- `0x16850`
- `0x168a0`
- `0x16a00`
- `0x16a20`
- `0x17d30`
- `0x23020`
- `0x23dc0`
- `0x23fa0`
- `0x23fe0`
- `0x24b20`
- `0x24b90`
- `0x24f90`

## string_xrefs

- `0x16360`: `GetManifestAsync call cancelled.`
- `0x1645f`: `Ex_InstallFlagMustBeFalse`
- `0x16492`: `Ex_CannotHaveUseManifestForTrustFlag`

## pseudocode

```c

```

## disassembly

```asm
0x162f0  ldarg.0
0x162f1  ldfld    object System.Deployment.Application.InPlaceHostingManager::_lock
0x162f6  stloc.0
0x162f7  ldc.i4.0
0x162f8  stloc.1
0x162f9  ldloc.0
0x162fa  ldloca.s 1
0x162fc  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x16301  ldnull
0x16302  stloc.2
0x16303  ldarg.0
0x16304  ldc.i4.1
0x16305  ldc.i4.7
0x16306  call     instance void System.Deployment.Application.InPlaceHostingManager::AssertState(valuetype State validState0, valuetype State validState1)
0x1630b  ldarg.0
0x1630c  ldfld    valuetype State System.Deployment.Application.InPlaceHostingManager::_state
0x16311  ldc.i4.7
0x16312  beq.s    loc_16335
0x16314  ldarg.2
0x16315  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x1631a  brtrue.s loc_16324
0x1631c  ldarg.2
0x1631d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x16322  brfalse.s loc_1632D
0x16324  ldarg.0
0x16325  ldc.i4.7
0x16326  call     instance void System.Deployment.Application.InPlaceHostingManager::ChangeState(valuetype State nextState)
0x1632b  br.s     loc_16335
0x1632d  ldarg.0
0x1632e  ldc.i4.2
0x1632f  ldarg.2
0x16330  call     instance void System.Deployment.Application.InPlaceHostingManager::ChangeState(valuetype State nextState, class [System]System.ComponentModel.AsyncCompletedEventArgs e)
0x16335  ldarg.0
0x16336  ldfld    class [mscorlib]System.EventHandler`1<class System.Deployment.Application.GetManifestCompletedEventArgs> System.Deployment.Application.InPlaceHostingManager::GetManifestCompleted
0x1633b  brtrue.s loc_16342
0x1633d  leave    loc_165F8
0x16342  ldarg.2
0x16343  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x16348  brtrue.s loc_16352
0x1634a  ldarg.2
0x1634b  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x16350  brfalse.s loc_16381
0x16352  ldarg.2
0x16353  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x16358  brfalse.s loc_1636A
0x1635a  ldarg.0
0x1635b  ldfld    class LogIdentity System.Deployment.Application.InPlaceHostingManager::_log
0x16360  ldstr    aGetmanifestasy// "GetManifestAsync call cancelled."
0x16365  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x1636a  ldarg.2
0x1636b  ldarg.0
0x1636c  ldfld    class System.Deployment.Application.DeploymentManager System.Deployment.Application.InPlaceHostingManager::_deploymentManager
0x16371  callvirt instance string System.Deployment.Application.DeploymentManager::get_LogFilePath()
0x16376  newobj   instance void System.Deployment.Application.GetManifestCompletedEventArgs::.ctor(class System.Deployment.Application.BindCompletedEventArgs e, string logFilePath)
0x1637b  stloc.2
0x1637c  br       loc_165A5
0x16381  ldarg.0
0x16382  ldarg.2
0x16383  callvirt instance bool System.Deployment.Application.BindCompletedEventArgs::get_IsCached()
0x16388  stfld    bool System.Deployment.Application.InPlaceHostingManager::_isCached
0x1638d  ldarg.0
0x1638e  ldfld    class System.Deployment.Application.DeploymentManager System.Deployment.Application.InPlaceHostingManager::_deploymentManager
0x16393  callvirt instance class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::get_ActivationDescription()
0x16398  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0x1639d  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0x163a2  callvirt instance bool System.Deployment.Application.Manifest.Deployment::get_Install()
0x163a7  stloc.3
0x163a8  ldarg.0
0x163a9  ldfld    class System.Deployment.Application.DeploymentManager System.Deployment.Application.InPlaceHostingManager::_deploymentManager
0x163ae  callvirt instance class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::get_ActivationDescription()
0x163b3  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::AppManifest
0x163b8  callvirt instance class System.Deployment.Application.Manifest.EntryPoint[] System.Deployment.Application.Manifest.AssemblyManifest::get_EntryPoints()
0x163bd  ldc.i4.0
0x163be  ldelem.ref
0x163bf  callvirt instance bool System.Deployment.Application.Manifest.EntryPoint::get_HostInBrowser()
0x163c4  stloc.s  4
0x163c6  ldarg.0
0x163c7  ldarg.0
0x163c8  ldfld    class System.Deployment.Application.DeploymentManager System.Deployment.Application.InPlaceHostingManager::_deploymentManager
0x163cd  callvirt instance class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::get_ActivationDescription()
0x163d2  ldfld    valuetype System.Deployment.Application.AppType System.Deployment.Application.CommitApplicationParams::appType
0x163d7  stfld    valuetype System.Deployment.Application.AppType System.Deployment.Application.InPlaceHostingManager::_appType
0x163dc  ldarg.0
0x163dd  ldfld    class System.Deployment.Application.DeploymentManager System.Deployment.Application.InPlaceHostingManager::_deploymentManager
0x163e2  callvirt instance class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::get_ActivationDescription()
0x163e7  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::AppManifest
0x163ec  callvirt instance bool System.Deployment.Application.Manifest.AssemblyManifest::get_UseManifestForTrust()
0x163f1  stloc.s  5
0x163f3  ldarg.0
0x163f4  ldfld    class System.Deployment.Application.DeploymentManager System.Deployment.Application.InPlaceHostingManager::_deploymentManager
0x163f9  callvirt instance class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::get_ActivationDescription()
0x163fe  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0x16403  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0x16408  callvirt instance class [System]System.Uri System.Deployment.Application.Manifest.Deployment::get_ProviderCodebaseUri()
0x1640d  stloc.s  6
0x1640f  ldarg.0
0x16410  ldfld    bool System.Deployment.Application.InPlaceHostingManager::_isLaunchInHostProcess
0x16415  brfalse.s loc_1644A
0x16417  ldarg.0
0x16418  ldfld    valuetype System.Deployment.Application.AppType System.Deployment.Application.InPlaceHostingManager::_appType
0x1641d  ldc.i4.3
0x1641e  beq.s    loc_1644A
0x16420  ldloc.s  4
0x16422  brtrue.s loc_1644A
0x16424  ldarg.2
0x16425  ldstr    aExHostinbrowse_0// "Ex_HostInBrowserFlagMustBeTrue"
0x1642a  call     string System.Deployment.Application.Resources::GetString(string s)
0x1642f  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x16434  ldarg.0
0x16435  ldfld    class System.Deployment.Application.DeploymentManager System.Deployment.Application.InPlaceHostingManager::_deploymentManager
0x1643a  callvirt instance string System.Deployment.Application.DeploymentManager::get_LogFilePath()
0x1643f  newobj   instance void System.Deployment.Application.GetManifestCompletedEventArgs::.ctor(class System.Deployment.Application.BindCompletedEventArgs e, class [mscorlib]System.Exception error, string logFilePath)
0x16444  stloc.2
0x16445  br       loc_16540
0x1644a  ldloc.3
0x1644b  brfalse.s loc_16484
0x1644d  ldarg.0
0x1644e  ldfld    bool System.Deployment.Application.InPlaceHostingManager::_isLaunchInHostProcess
0x16453  brtrue.s loc_1645E
0x16455  ldarg.0
0x16456  ldfld    valuetype System.Deployment.Application.AppType System.Deployment.Application.InPlaceHostingManager::_appType
0x1645b  ldc.i4.3
0x1645c  bne.un.s loc_16484
0x1645e  ldarg.2
0x1645f  ldstr    aExInstallflagm// "Ex_InstallFlagMustBeFalse"
0x16464  call     string System.Deployment.Application.Resources::GetString(string s)
0x16469  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1646e  ldarg.0
0x1646f  ldfld    class System.Deployment.Application.DeploymentManager System.Deployment.Application.InPlaceHostingManager::_deploymentManager
0x16474  callvirt instance string System.Deployment.Application.DeploymentManager::get_LogFilePath()
0x16479  newobj   instance void System.Deployment.Application.GetManifestCompletedEventArgs::.ctor(class System.Deployment.Application.BindCompletedEventArgs e, class [mscorlib]System.Exception error, string logFilePath)
0x1647e  stloc.2
0x1647f  br       loc_16540
0x16484  ldloc.s  5
0x16486  brfalse.s loc_164B7
0x16488  ldarg.0
0x16489  ldfld    valuetype System.Deployment.Application.AppType System.Deployment.Application.InPlaceHostingManager::_appType
0x1648e  ldc.i4.3
0x1648f  bne.un.s loc_164B7
0x16491  ldarg.2
0x16492  ldstr    aExCannothaveus// "Ex_CannotHaveUseManifestForTrustFlag"
0x16497  call     string System.Deployment.Application.Resources::GetString(string s)
0x1649c  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x164a1  ldarg.0
0x164a2  ldfld    class System.Deployment.Application.DeploymentManager System.Deployment.Application.InPlaceHostingManager::_deploymentManager
0x164a7  callvirt instance string System.Deployment.Application.DeploymentManager::get_LogFilePath()
0x164ac  newobj   instance void System.Deployment.Application.GetManifestCompletedEventArgs::.ctor(class System.Deployment.Application.BindCompletedEventArgs e, class [mscorlib]System.Exception error, string logFilePath)
0x164b1  stloc.2
0x164b2  br       loc_16540
0x164b7  ldloc.s  6
0x164b9  ldnull
0x164ba  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x164bf  brfalse.s loc_164ED
0x164c1  ldarg.0
0x164c2  ldfld    valuetype System.Deployment.Application.AppType System.Deployment.Application.InPlaceHostingManager::_appType
0x164c7  ldc.i4.3
0x164c8  bne.un.s loc_164ED
0x164ca  ldarg.2
0x164cb  ldstr    aExCannothavede// "Ex_CannotHaveDeploymentProvider"
0x164d0  call     string System.Deployment.Application.Resources::GetString(string s)
0x164d5  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x164da  ldarg.0
0x164db  ldfld    class System.Deployment.Application.DeploymentManager System.Deployment.Application.InPlaceHostingManager::_deploymentManager
0x164e0  callvirt instance string System.Deployment.Application.DeploymentManager::get_LogFilePath()
0x164e5  newobj   instance void System.Deployment.Application.GetManifestCompletedEventArgs::.ctor(class System.Deployment.Application.BindCompletedEventArgs e, class [mscorlib]System.Exception error, string logFilePath)
0x164ea  stloc.2
0x164eb  br.s     loc_16540
0x164ed  ldloc.s  4
0x164ef  brfalse.s loc_1651D
0x164f1  ldarg.0
0x164f2  ldfld    valuetype System.Deployment.Application.AppType System.Deployment.Application.InPlaceHostingManager::_appType
0x164f7  ldc.i4.4
0x164f8  bne.un.s loc_1651D
0x164fa  ldarg.2
0x164fb  ldstr    aExCannothavecu// "Ex_CannotHaveCustomUXFlag"
0x16500  call     string System.Deployment.Application.Resources::GetString(string s)
0x16505  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1650a  ldarg.0
0x1650b  ldfld    class System.Deployment.Application.DeploymentManager System.Deployment.Application.InPlaceHostingManager::_deploymentManager
0x16510  callvirt instance string System.Deployment.Application.DeploymentManager::get_LogFilePath()
0x16515  newobj   instance void System.Deployment.Application.GetManifestCompletedEventArgs::.ctor(class System.Deployment.Application.BindCompletedEventArgs e, class [mscorlib]System.Exception error, string logFilePath)
0x1651a  stloc.2
0x1651b  br.s     loc_16540
0x1651d  ldarg.2
0x1651e  ldarg.0
0x1651f  ldfld    class System.Deployment.Application.DeploymentManager System.Deployment.Application.InPlaceHostingManager::_deploymentManager
0x16524  callvirt instance class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::get_ActivationDescription()
0x16529  ldarg.0
0x1652a  ldfld    class System.Deployment.Application.DeploymentManager System.Deployment.Application.InPlaceHostingManager::_deploymentManager
0x1652f  callvirt instance string System.Deployment.Application.DeploymentManager::get_LogFilePath()
0x16534  ldarg.0
0x16535  ldfld    class LogIdentity System.Deployment.Application.InPlaceHostingManager::_log
0x1653a  newobj   instance void System.Deployment.Application.GetManifestCompletedEventArgs::.ctor(class System.Deployment.Application.BindCompletedEventArgs e, class System.Deployment.Application.ActivationDescription activationDescription, string logFilePath, class LogIdentity log)
0x1653f  stloc.2
0x16540  ldloc.2
0x16541  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x16546  brfalse.s loc_165A5
0x16548  ldarg.0
0x16549  ldfld    class LogIdentity System.Deployment.Application.InPlaceHostingManager::_log
0x1654e  ldc.i4.6
0x1654f  newarr   [mscorlib]System.String
0x16554  dup
0x16555  ldc.i4.0
0x16556  ldstr    aExceptionThrow_12// "Exception thrown after binding: "
0x1655b  stelem.ref
0x1655c  dup
0x1655d  ldc.i4.1
0x1655e  ldloc.2
0x1655f  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x16564  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x16569  callvirt instance string [mscorlib]System.Object::ToString()
0x1656e  stelem.ref
0x1656f  dup
0x16570  ldc.i4.2
0x16571  ldstr    asc_3345E// " : "
0x16576  stelem.ref
0x16577  dup
0x16578  ldc.i4.3
0x16579  ldloc.2
0x1657a  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x1657f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x16584  stelem.ref
0x16585  dup
0x16586  ldc.i4.4
0x16587  ldstr    asc_3279C// "\r\n"
0x1658c  stelem.ref
0x1658d  dup
0x1658e  ldc.i4.5
0x1658f  ldloc.2
0x16590  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x16595  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x1659a  stelem.ref
0x1659b  call     string [mscorlib]System.String::Concat(string[])
0x165a0  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x165a5  leave.s  loc_165DF
0x165a7  stloc.s  7
0x165a9  ldarg.0
0x165aa  ldfld    class LogIdentity System.Deployment.Application.InPlaceHostingManager::_log
0x165af  ldstr    aExceptionThrow_13// "Exception thrown:"
0x165b4  ldloc.s  7
0x165b6  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x165bb  callvirt instance string [mscorlib]System.Object::ToString()
0x165c0  ldstr    asc_3345E// " : "
0x165c5  ldloc.s  7
0x165c7  callvirt instance string [mscorlib]System.Exception::get_Message()
0x165cc  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x165d1  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x165d6  ldarg.0
0x165d7  ldc.i4.7
0x165d8  call     instance void System.Deployment.Application.InPlaceHostingManager::ChangeState(valuetype State nextState)
0x165dd  rethrow
0x165df  ldarg.0
0x165e0  ldfld    class [mscorlib]System.EventHandler`1<class System.Deployment.Application.GetManifestCompletedEventArgs> System.Deployment.Application.InPlaceHostingManager::GetManifestCompleted
0x165e5  ldarg.0
0x165e6  ldloc.2
0x165e7  callvirt instance void class [mscorlib]System.EventHandler`1<class System.Deployment.Application.GetManifestCompletedEventArgs>::Invoke(object, var<u1>)
0x165ec  leave.s  loc_165F8
0x165ee  ldloc.1
0x165ef  brfalse.s loc_165F7
0x165f1  ldloc.0
0x165f2  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x165f7  endfinally
0x165f8  ret
```
