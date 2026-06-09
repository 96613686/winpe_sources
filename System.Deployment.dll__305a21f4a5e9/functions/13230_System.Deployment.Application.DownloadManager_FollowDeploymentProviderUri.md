# System.Deployment.Application.DownloadManager::FollowDeploymentProviderUri

- ea: `0x13230`
- end: `0x1347e`
- name: `System.Deployment.Application.DownloadManager::FollowDeploymentProviderUri`
- size: `590`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x13180`
- `0x13480`

## callees

- `0x13230`
- `0x13950`
- `0x14740`
- `0x147a0`
- `0x147b0`
- `0x177b0`
- `0x177e0`
- `0x17cd0`
- `0x17d40`
- `0x1ece0`
- `0x1f8b0`
- `0x23020`
- `0x23320`
- `0x23fa0`
- `0x24390`
- `0x24b90`
- `0x25050`

## string_xrefs

- `0x13230`: `FollowDeploymentProviderUri called.`
- `0x13256`: `Deployment manifest zone is not local machine. Zone = `
- `0x13280`: `Deployment manifest zone is local machine. Zone = `
- `0x132bb`: `Ex_NoAppInDeploymentManifest`
- `0x132f2`: `Application manifest zone is local machine. Zone = `
- `0x13357`: `providerUri=`
- `0x1336a`: `,sourceUri=`
- `0x133f2`: `Ex_InvalidProviderManifest`

## pseudocode

```c

```

## disassembly

```asm
0x13230  ldstr    aFollowdeployme// "FollowDeploymentProviderUri called."
0x13235  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0x1323a  ldarg.3
0x1323b  ldnull
0x1323c  stind.ref
0x1323d  ldc.i4.0
0x1323e  stloc.0
0x1323f  ldarg.2
0x13240  ldind.ref
0x13241  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x13246  call     class [mscorlib]System.Security.Policy.Zone [mscorlib]System.Security.Policy.Zone::CreateFromUrl(string)
0x1324b  stloc.1
0x1324c  ldc.i4.0
0x1324d  stloc.2
0x1324e  ldloc.1
0x1324f  callvirt instance valuetype [mscorlib]System.Security.SecurityZone [mscorlib]System.Security.Policy.Zone::get_SecurityZone()
0x13254  brfalse.s loc_13280
0x13256  ldstr    aDeploymentMani// "Deployment manifest zone is not local m"...
0x1325b  ldloc.1
0x1325c  callvirt instance valuetype [mscorlib]System.Security.SecurityZone [mscorlib]System.Security.Policy.Zone::get_SecurityZone()
0x13261  stloc.3
0x13262  ldloca.s 3
0x13264  constrained. [mscorlib]System.Security.SecurityZone
0x1326a  callvirt instance string [mscorlib]System.Object::ToString()
0x1326f  call     string [mscorlib]System.String::Concat(string, string)
0x13274  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x13279  ldc.i4.1
0x1327a  stloc.2
0x1327b  br       loc_1333C
0x13280  ldstr    aDeploymentMani_0// "Deployment manifest zone is local machi"...
0x13285  ldloc.1
0x13286  callvirt instance valuetype [mscorlib]System.Security.SecurityZone [mscorlib]System.Security.Policy.Zone::get_SecurityZone()
0x1328b  stloc.3
0x1328c  ldloca.s 3
0x1328e  constrained. [mscorlib]System.Security.SecurityZone
0x13294  callvirt instance string [mscorlib]System.Object::ToString()
0x13299  call     string [mscorlib]System.String::Concat(string, string)
0x1329e  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x132a3  ldarg.1
0x132a4  ldind.ref
0x132a5  callvirt instance class System.Deployment.Application.Manifest.DependentAssembly System.Deployment.Application.Manifest.AssemblyManifest::get_MainDependentAssembly()
0x132aa  stloc.s  4
0x132ac  ldloc.s  4
0x132ae  brfalse.s loc_132B9
0x132b0  ldloc.s  4
0x132b2  callvirt instance string System.Deployment.Application.Manifest.DependentAssembly::get_Codebase()
0x132b7  brtrue.s loc_132CB
0x132b9  ldc.i4.s 0x10
0x132bb  ldstr    aExNoappindeplo// "Ex_NoAppInDeploymentManifest"
0x132c0  call     string System.Deployment.Application.Resources::GetString(string s)
0x132c5  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x132ca  throw
0x132cb  ldarg.2
0x132cc  ldind.ref
0x132cd  ldloc.s  4
0x132cf  callvirt instance string System.Deployment.Application.Manifest.DependentAssembly::get_Codebase()
0x132d4  newobj   instance void [System]System.Uri::.ctor(class [System]System.Uri, string)
0x132d9  stloc.s  5
0x132db  ldloc.s  5
0x132dd  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x132e2  call     class [mscorlib]System.Security.Policy.Zone [mscorlib]System.Security.Policy.Zone::CreateFromUrl(string)
0x132e7  stloc.s  6
0x132e9  ldloc.s  6
0x132eb  callvirt instance valuetype [mscorlib]System.Security.SecurityZone [mscorlib]System.Security.Policy.Zone::get_SecurityZone()
0x132f0  brtrue.s loc_1333C
0x132f2  ldstr    aApplicationMan// "Application manifest zone is local mach"...
0x132f7  ldloc.s  6
0x132f9  callvirt instance valuetype [mscorlib]System.Security.SecurityZone [mscorlib]System.Security.Policy.Zone::get_SecurityZone()
0x132fe  stloc.3
0x132ff  ldloca.s 3
0x13301  constrained. [mscorlib]System.Security.SecurityZone
0x13307  callvirt instance string [mscorlib]System.Object::ToString()
0x1330c  call     string [mscorlib]System.String::Concat(string, string)
0x13311  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x13316  ldloc.s  5
0x13318  callvirt instance string [System]System.Uri::get_LocalPath()
0x1331d  call     bool [mscorlib]System.IO.File::Exists(string)
0x13322  brtrue.s loc_1333C
0x13324  ldloc.s  5
0x13326  callvirt instance string [System]System.Uri::get_LocalPath()
0x1332b  ldstr    aDoesNotExistIn// " does not exist in local machine."
0x13330  call     string [mscorlib]System.String::Concat(string, string)
0x13335  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1333a  ldc.i4.1
0x1333b  stloc.2
0x1333c  ldloc.2
0x1333d  brfalse  loc_1346F
0x13342  ldarg.1
0x13343  ldind.ref
0x13344  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0x13349  callvirt instance class [System]System.Uri System.Deployment.Application.Manifest.Deployment::get_ProviderCodebaseUri()
0x1334e  stloc.s  7
0x13350  ldloc.s  7
0x13352  call     void System.Deployment.Application.Logger::SetDeploymentProviderUrl(class [System]System.Uri deploymentProviderUri)
0x13357  ldstr    aProvideruri// "providerUri="
0x1335c  ldloc.s  7
0x1335e  dup
0x1335f  brtrue.s loc_13365
0x13361  pop
0x13362  ldnull
0x13363  br.s     loc_1336A
0x13365  callvirt instance string [mscorlib]System.Object::ToString()
0x1336a  ldstr    aSourceuri_0// ",sourceUri="
0x1336f  ldarg.2
0x13370  ldind.ref
0x13371  dup
0x13372  brtrue.s loc_13378
0x13374  pop
0x13375  ldnull
0x13376  br.s     loc_1337D
0x13378  callvirt instance string [mscorlib]System.Object::ToString()
0x1337d  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x13382  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x13387  call     bool System.Deployment.Application.PolicyKeys::SkipDeploymentProvider()
0x1338c  brtrue   loc_1346F
0x13391  ldloc.s  7
0x13393  ldnull
0x13394  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x13399  brfalse  loc_1346F
0x1339e  ldloc.s  7
0x133a0  ldarg.2
0x133a1  ldind.ref
0x133a2  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x133a7  brtrue   loc_1346F
0x133ac  ldnull
0x133ad  stloc.s  8
0x133af  ldarg.0
0x133b0  ldloca.s 7
0x133b2  ldarg.3
0x133b3  ldarg.s  4
0x133b5  ldarg.s  5
0x133b7  ldloca.s 9
0x133b9  call     class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.DownloadManager::DownloadDeploymentManifestDirect(class System.Deployment.Application.SubscriptionStore subStore, class [System]System.Uri& sourceUri, [out] class System.Deployment.Application.TempFile& tempFile, class System.Deployment.Application.IDownloadNotification notification, class System.Deployment.Application.DownloadOptions options, [out] class System.Deployment.Application.ServerInformation& serverInformation)
0x133be  stloc.s  8
0x133c0  leave.s  loc_13406
0x133c2  stloc.s  0xC
0x133c4  ldloc.s  0xC
0x133c6  callvirt instance valuetype System.Deployment.Application.ExceptionTypes System.Deployment.Application.DeploymentException::get_SubType()
0x133cb  ldc.i4.s 0xD
0x133cd  beq.s    loc_133F0
0x133cf  ldloc.s  0xC
0x133d1  callvirt instance valuetype System.Deployment.Application.ExceptionTypes System.Deployment.Application.DeploymentException::get_SubType()
0x133d6  ldc.i4.s 0xE
0x133d8  beq.s    loc_133F0
0x133da  ldloc.s  0xC
0x133dc  callvirt instance valuetype System.Deployment.Application.ExceptionTypes System.Deployment.Application.DeploymentException::get_SubType()
0x133e1  ldc.i4.s 0xF
0x133e3  beq.s    loc_133F0
0x133e5  ldloc.s  0xC
0x133e7  callvirt instance valuetype System.Deployment.Application.ExceptionTypes System.Deployment.Application.DeploymentException::get_SubType()
0x133ec  ldc.i4.s 0x10
0x133ee  bne.un.s loc_13404
0x133f0  ldc.i4.s 0xD
0x133f2  ldstr    aExInvalidprovi// "Ex_InvalidProviderManifest"
0x133f7  call     string System.Deployment.Application.Resources::GetString(string s)
0x133fc  ldloc.s  0xC
0x133fe  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0x13403  throw
0x13404  rethrow
0x13406  ldloc.s  9
0x13408  call     void System.Deployment.Application.Logger::SetDeploymentProviderServerInformation(class System.Deployment.Application.ServerInformation serverInformation)
0x1340d  ldarg.0
0x1340e  ldarg.1
0x1340f  ldind.ref
0x13410  callvirt instance class System.Deployment.Application.SubscriptionState System.Deployment.Application.SubscriptionStore::GetSubscriptionState(class System.Deployment.Application.Manifest.AssemblyManifest deployment)
0x13415  stloc.s  0xA
0x13417  ldarg.0
0x13418  ldloc.s  8
0x1341a  callvirt instance class System.Deployment.Application.SubscriptionState System.Deployment.Application.SubscriptionStore::GetSubscriptionState(class System.Deployment.Application.Manifest.AssemblyManifest deployment)
0x1341f  stloc.s  0xB
0x13421  ldloc.s  0xB
0x13423  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x13428  ldloc.s  0xA
0x1342a  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1342f  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x13434  brtrue.s loc_13448
0x13436  ldc.i4.s 0x13
0x13438  ldstr    aExProvidernoti// "Ex_ProviderNotInSubscription"
0x1343d  call     string System.Deployment.Application.Resources::GetString(string s)
0x13442  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x13447  throw
0x13448  ldstr    aDeploymentProv// "Deployment provider followed: "
0x1344d  ldloc.s  7
0x1344f  dup
0x13450  brtrue.s loc_13456
0x13452  pop
0x13453  ldnull
0x13454  br.s     loc_1345B
0x13456  callvirt instance string [mscorlib]System.Object::ToString()
0x1345b  call     string [mscorlib]System.String::Concat(string, string)
0x13460  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x13465  ldarg.1
0x13466  ldloc.s  8
0x13468  stind.ref
0x13469  ldarg.2
0x1346a  ldloc.s  7
0x1346c  stind.ref
0x1346d  ldc.i4.1
0x1346e  stloc.0
0x1346f  ldloc.0
0x13470  brtrue.s loc_1347C
0x13472  ldstr    aDeploymentProv_0// "Deployment provider not followed."
0x13477  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1347c  ldloc.0
0x1347d  ret
```
