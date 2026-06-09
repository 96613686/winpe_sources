# System.Deployment.Application.DeploymentManager::BindCore

- ea: `0x113b0`
- end: `0x11851`
- name: `System.Deployment.Application.DeploymentManager::BindCore`
- size: `1185`
- prototype: ``
- caller_count: `2`
- callee_count: `39`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x10c80`
- `0x112f0`

## callees

- `0xc1b0`
- `0xc200`
- `0xc220`
- `0xc2c0`
- `0xd530`
- `0xd960`
- `0x113b0`
- `0x11860`
- `0x125c0`
- `0x12600`
- `0x13180`
- `0x13510`
- `0x146f0`
- `0x147a0`
- `0x147b0`
- `0x17840`
- `0x17960`
- `0x17a00`
- `0x17d30`
- `0x1ed40`
- `0x1ede0`
- `0x1f800`
- `0x1f890`
- `0x1f8b0`
- `0x1fc90`
- `0x201e0`
- `0x20a60`
- `0x20b30`
- `0x23020`
- `0x23c30`
- `0x23cd0`
- `0x23fa0`
- `0x23fe0`
- `0x24380`
- `0x24970`
- `0x24b30`
- `0x24b90`
- `0x25050`
- `0x25b70`

## string_xrefs

- `0x11507`: `Ex_DeploymentUriDifferentExText`
- `0x1177b`: `_cached=`
- `0x1179b`: `_isupdate=`
- `0x117e8`: `Ex_FailedToDownloadManifest`

## pseudocode

```c

```

## disassembly

```asm
0x113b0  ldarg.0
0x113b1  ldfld    class [System]System.Uri System.Deployment.Application.DeploymentManager::_deploySource
0x113b6  ldnull
0x113b7  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x113bc  brfalse.s loc_113D0
0x113be  ldarg.0
0x113bf  ldarg.1
0x113c0  ldarg.s  4
0x113c2  ldarg.s  5
0x113c4  call     instance bool System.Deployment.Application.DeploymentManager::BindCoreWithAppId(bool blocking, class [mscorlib]System.IO.FileStream& refTransaction, string& productName)
0x113c9  stloc.s  0xC
0x113cb  leave    loc_1184E
0x113d0  ldc.i4.0
0x113d1  stloc.0
0x113d2  ldnull
0x113d3  stloc.1
0x113d4  ldnull
0x113d5  stloc.2
0x113d6  ldarg.0
0x113d7  ldfld    class [System]System.Uri System.Deployment.Application.DeploymentManager::_deploySource
0x113dc  stloc.3
0x113dd  ldarg.0
0x113de  ldc.i4.0
0x113df  stfld    valuetype System.Deployment.Application.DeploymentProgressState System.Deployment.Application.DeploymentManager::_state
0x113e4  ldarg.0
0x113e5  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x113ea  ldstr    aInternalState// "Internal state="
0x113ef  ldarg.0
0x113f0  ldflda   valuetype System.Deployment.Application.DeploymentProgressState System.Deployment.Application.DeploymentManager::_state
0x113f5  constrained. System.Deployment.Application.DeploymentProgressState
0x113fb  callvirt instance string [mscorlib]System.Object::ToString()
0x11400  call     string [mscorlib]System.String::Concat(string, string)
0x11405  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x1140a  ldarg.0
0x1140b  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.DeploymentManager::_subStore
0x11410  ldloca.s 3
0x11412  ldarg.2
0x11413  ldarg.1
0x11414  brtrue.s loc_11419
0x11416  ldarg.0
0x11417  br.s     loc_1141A
0x11419  ldnull
0x1141a  ldarg.0
0x1141b  ldfld    class System.Deployment.Application.DownloadOptions System.Deployment.Application.DeploymentManager::_downloadOptions
0x11420  call     class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.DownloadManager::DownloadDeploymentManifest(class System.Deployment.Application.SubscriptionStore subStore, class [System]System.Uri& sourceUri, [out] class System.Deployment.Application.TempFile& tempFile, class System.Deployment.Application.IDownloadNotification notification, class System.Deployment.Application.DownloadOptions options)
0x11425  stloc.1
0x11426  ldarg.2
0x11427  ldind.ref
0x11428  callvirt instance string System.Deployment.Application.TempFile::get_Path()
0x1142d  stloc.2
0x1142e  newobj   instance void System.Deployment.Application.ActivationDescription::.ctor()
0x11433  stloc.s  4
0x11435  ldloc.s  4
0x11437  ldloc.1
0x11438  ldloc.3
0x11439  ldloc.2
0x1143a  callvirt instance void System.Deployment.Application.ActivationDescription::SetDeploymentManifest(class System.Deployment.Application.Manifest.AssemblyManifest manifest, class [System]System.Uri manifestUri, string manifestPath)
0x1143f  ldarg.0
0x11440  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x11445  ldloc.1
0x11446  call     void System.Deployment.Application.Logger::SetDeploymentManifest(class LogIdentity log, class System.Deployment.Application.Manifest.AssemblyManifest deploymentManifest)
0x1144b  ldloc.s  4
0x1144d  ldarg.0
0x1144e  ldfld    bool System.Deployment.Application.DeploymentManager::_isupdate
0x11453  stfld    bool System.Deployment.Application.CommitApplicationParams::IsUpdate
0x11458  ldloc.s  4
0x1145a  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0x1145f  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0x11464  brtrue.s loc_11478
0x11466  ldc.i4.s 0xC
0x11468  ldstr    aExNotdeploymen// "Ex_NotDeploymentOrShortcut"
0x1146d  call     string System.Deployment.Application.Resources::GetString(string s)
0x11472  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x11477  throw
0x11478  ldarg.1
0x11479  brtrue.s loc_1148B
0x1147b  ldarg.0
0x1147c  ldfld    bool System.Deployment.Application.DeploymentManager::_cancellationPending
0x11481  brfalse.s loc_1148B
0x11483  ldc.i4.1
0x11484  stloc.s  0xC
0x11486  leave    loc_1184E
0x1148b  ldarg.s  4
0x1148d  ldarg.0
0x1148e  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.DeploymentManager::_subStore
0x11493  ldloca.s 5
0x11495  callvirt instance class [mscorlib]System.IO.FileStream System.Deployment.Application.SubscriptionStore::AcquireReferenceTransaction([out] int64& transactionId)
0x1149a  stind.ref
0x1149b  ldarg.0
0x1149c  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.DeploymentManager::_subStore
0x114a1  ldloc.s  4
0x114a3  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0x114a8  callvirt instance class System.Deployment.Application.SubscriptionState System.Deployment.Application.SubscriptionStore::GetSubscriptionState(class System.Deployment.Application.Manifest.AssemblyManifest deployment)
0x114ad  stloc.s  6
0x114af  ldloc.s  4
0x114b1  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0x114b6  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0x114bb  callvirt instance bool System.Deployment.Application.Manifest.Deployment::get_Install()
0x114c0  brfalse  loc_1154E
0x114c5  ldloc.s  4
0x114c7  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0x114cc  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0x114d1  callvirt instance class [System]System.Uri System.Deployment.Application.Manifest.Deployment::get_ProviderCodebaseUri()
0x114d6  ldnull
0x114d7  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x114dc  brfalse.s loc_1154E
0x114de  ldloc.s  6
0x114e0  brfalse.s loc_1154E
0x114e2  ldloc.s  6
0x114e4  callvirt instance class [System]System.Uri System.Deployment.Application.SubscriptionState::get_DeploymentProviderUri()
0x114e9  ldnull
0x114ea  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x114ef  brfalse.s loc_1154E
0x114f1  ldloc.s  6
0x114f3  callvirt instance class [System]System.Uri System.Deployment.Application.SubscriptionState::get_DeploymentProviderUri()
0x114f8  ldloc.3
0x114f9  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x114fe  brtrue.s loc_1154E
0x11500  ldc.i4.s 0x16
0x11502  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x11507  ldstr    aExDeploymentur// "Ex_DeploymentUriDifferentExText"
0x1150c  call     string System.Deployment.Application.Resources::GetString(string s)
0x11511  ldc.i4.3
0x11512  newarr   [mscorlib]System.Object
0x11517  dup
0x11518  ldc.i4.0
0x11519  ldloc.s  4
0x1151b  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0x11520  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x11525  callvirt instance string System.Deployment.Application.Manifest.Description::get_FilteredProduct()
0x1152a  stelem.ref
0x1152b  dup
0x1152c  ldc.i4.1
0x1152d  ldloc.3
0x1152e  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x11533  stelem.ref
0x11534  dup
0x11535  ldc.i4.2
0x11536  ldloc.s  6
0x11538  callvirt instance class [System]System.Uri System.Deployment.Application.SubscriptionState::get_DeploymentProviderUri()
0x1153d  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x11542  stelem.ref
0x11543  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x11548  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x1154d  throw
0x1154e  ldnull
0x1154f  stloc.s  7
0x11551  ldloc.s  4
0x11553  callvirt instance string System.Deployment.Application.ActivationDescription::ToAppCodebase()
0x11558  ldc.i4.2
0x11559  newarr   System.Deployment.Application.DefinitionIdentity
0x1155e  dup
0x1155f  ldc.i4.0
0x11560  ldloc.s  4
0x11562  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0x11567  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x1156c  stelem.ref
0x1156d  dup
0x1156e  ldc.i4.1
0x1156f  ldloc.s  4
0x11571  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0x11576  callvirt instance class System.Deployment.Application.Manifest.DependentAssembly System.Deployment.Application.Manifest.AssemblyManifest::get_MainDependentAssembly()
0x1157b  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x11580  newobj   instance void System.Deployment.Application.DefinitionIdentity::.ctor(class System.Deployment.Application.ReferenceIdentity refId)
0x11585  stelem.ref
0x11586  newobj   instance void System.Deployment.Application.DefinitionAppId::.ctor(string codebase, class System.Deployment.Application.DefinitionIdentity[] idPath)
0x1158b  stloc.s  7
0x1158d  leave.s  loc_115BB
0x1158f  stloc.s  0xD
0x11591  ldc.i4.s 0xC
0x11593  ldstr    aExIdentityisno// "Ex_IdentityIsNotValid"
0x11598  call     string System.Deployment.Application.Resources::GetString(string s)
0x1159d  ldloc.s  0xD
0x1159f  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0x115a4  throw
0x115a5  stloc.s  0xE
0x115a7  ldc.i4.s 0xC
0x115a9  ldstr    aExIdentityisno// "Ex_IdentityIsNotValid"
0x115ae  call     string System.Deployment.Application.Resources::GetString(string s)
0x115b3  ldloc.s  0xE
0x115b5  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0x115ba  throw
0x115bb  ldarg.0
0x115bc  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x115c1  ldstr    aExpectedappid// "expectedAppId="
0x115c6  ldloc.s  7
0x115c8  callvirt instance string [mscorlib]System.Object::ToString()
0x115cd  call     string [mscorlib]System.String::Concat(string, string)
0x115d2  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x115d7  ldarg.0
0x115d8  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.DeploymentManager::_subStore
0x115dd  ldloc.s  6
0x115df  ldloc.s  7
0x115e1  ldloc.s  5
0x115e3  callvirt instance bool System.Deployment.Application.SubscriptionStore::CheckAndReferenceApplication(class System.Deployment.Application.SubscriptionState subState, class System.Deployment.Application.DefinitionAppId appId, int64 transactionId)
0x115e8  stloc.0
0x115e9  ldloc.0
0x115ea  brfalse.s loc_11626
0x115ec  ldloc.s  7
0x115ee  ldloc.s  6
0x115f0  callvirt instance class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionState::get_CurrentBind()
0x115f5  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x115fa  brfalse.s loc_11626
0x115fc  ldarg.0
0x115fd  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x11602  ldstr    aApplicationIsF// "Application is found in store and it is"...
0x11607  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x1160c  ldarg.0
0x1160d  ldloc.s  7
0x1160f  stfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.DeploymentManager::_bindAppId
0x11614  ldarg.0
0x11615  ldarg.1
0x11616  ldarg.s  4
0x11618  ldarg.s  5
0x1161a  call     instance bool System.Deployment.Application.DeploymentManager::BindCoreWithAppId(bool blocking, class [mscorlib]System.IO.FileStream& refTransaction, string& productName)
0x1161f  stloc.s  0xC
0x11621  leave    loc_1184E
0x11626  ldloc.0
0x11627  brfalse.s loc_1163B
0x11629  ldarg.0
0x1162a  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x1162f  ldstr    aApplicationIsF_0// "Application is found in store but it is"...
0x11634  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x11639  br.s     loc_1164B
0x1163b  ldarg.0
0x1163c  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x11641  ldstr    aApplicationIsN// "Application is not found in store."
0x11646  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x1164b  ldarg.1
0x1164c  brtrue.s loc_1165E
0x1164e  ldarg.0
0x1164f  ldfld    bool System.Deployment.Application.DeploymentManager::_cancellationPending
0x11654  brfalse.s loc_1165E
0x11656  ldc.i4.1
0x11657  stloc.s  0xC
0x11659  leave    loc_1184E
0x1165e  ldarg.0
0x1165f  ldc.i4.1
0x11660  stfld    valuetype System.Deployment.Application.DeploymentProgressState System.Deployment.Application.DeploymentManager::_state
0x11665  ldarg.0
0x11666  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x1166b  ldstr    aInternalState// "Internal state="
0x11670  ldarg.0
0x11671  ldflda   valuetype System.Deployment.Application.DeploymentProgressState System.Deployment.Application.DeploymentManager::_state
0x11676  constrained. System.Deployment.Application.DeploymentProgressState
0x1167c  callvirt instance string [mscorlib]System.Object::ToString()
0x11681  call     string [mscorlib]System.String::Concat(string, string)
0x11686  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x1168b  ldarg.3
0x1168c  ldarg.0
0x1168d  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.DeploymentManager::_subStore
0x11692  callvirt instance class System.Deployment.Application.TempDirectory System.Deployment.Application.SubscriptionStore::AcquireTempDirectory()
0x11697  stind.ref
0x11698  ldloc.s  4
0x1169a  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0x1169f  ldarg.3
0x116a0  ldind.ref
0x116a1  callvirt instance string System.Deployment.Application.TempDirectory::get_Path()
0x116a6  ldloc.s  4
0x116a8  ldfld    class [System]System.Uri System.Deployment.Application.CommitApplicationParams::DeploySourceUri
0x116ad  ldarg.1
0x116ae  brtrue.s loc_116B3
0x116b0  ldarg.0
0x116b1  br.s     loc_116B4
0x116b3  ldnull
0x116b4  ldarg.0
0x116b5  ldfld    class System.Deployment.Application.DownloadOptions System.Deployment.Application.DeploymentManager::_downloadOptions
0x116ba  ldloca.s 8
0x116bc  ldloca.s 9
0x116be  call     class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.DownloadManager::DownloadApplicationManifest(class System.Deployment.Application.Manifest.AssemblyManifest deploymentManifest, string targetDir, class [System]System.Uri deploymentUri, class System.Deployment.Application.IDownloadNotification notification, class System.Deployment.Application.DownloadOptions options, [out] class [System]System.Uri& appSourceUri, [out] string& appManifestPath)
0x116c3  stloc.s  0xA
0x116c5  ldloc.s  4
0x116c7  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0x116cc  ldloc.s  0xA
0x116ce  call     void System.Deployment.Application.Manifest.AssemblyManifest::ReValidateManifestSignatures(class System.Deployment.Application.Manifest.AssemblyManifest depManifest, class System.Deployment.Application.Manifest.AssemblyManifest appManifest)
0x116d3  ldarg.0
0x116d4  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x116d9  ldloc.s  0xA
0x116db  call     void System.Deployment.Application.Logger::SetApplicationManifest(class LogIdentity log, class System.Deployment.Application.Manifest.AssemblyManifest applicationManifest)
0x116e0  ldarg.0
0x116e1  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x116e6  ldloc.s  8
0x116e8  call     void System.Deployment.Application.Logger::SetApplicationUrl(class LogIdentity log, class [System]System.Uri applicationUri)
0x116ed  ldloc.s  4
0x116ef  ldloc.s  0xA
0x116f1  ldloc.s  8
0x116f3  ldloc.s  9
0x116f5  callvirt instance void System.Deployment.Application.ActivationDescription::SetApplicationManifest(class System.Deployment.Application.Manifest.AssemblyManifest manifest, class [System]System.Uri manifestUri, string manifestPath)
0x116fa  ldloc.s  4
0x116fc  ldloc.s  4
0x116fe  callvirt instance string System.Deployment.Application.ActivationDescription::ToAppCodebase()
0x11703  ldc.i4.2
0x11704  newarr   System.Deployment.Application.DefinitionIdentity
0x11709  dup
0x1170a  ldc.i4.0
0x1170b  ldloc.s  4
0x1170d  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0x11712  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x11717  stelem.ref
0x11718  dup
  ... truncated ...
```
