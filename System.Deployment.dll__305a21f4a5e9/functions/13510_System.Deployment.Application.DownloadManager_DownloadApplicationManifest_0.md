# System.Deployment.Application.DownloadManager::DownloadApplicationManifest_0

- ea: `0x13510`
- end: `0x13713`
- name: `System.Deployment.Application.DownloadManager::DownloadApplicationManifest_0`
- size: `515`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x113b0`
- `0x13500`

## callees

- `0xdb00`
- `0xdd30`
- `0x10240`
- `0x13510`
- `0x13890`
- `0x13b90`
- `0x14740`
- `0x147a0`
- `0x147b0`
- `0x17810`
- `0x17870`
- `0x17cd0`
- `0x17d40`
- `0x23020`
- `0x23350`
- `0x24380`
- `0x24390`
- `0x24420`
- `0x24970`
- `0x24a70`
- `0x24b10`
- `0x25050`

## string_xrefs

- `0x1352e`: `Ex_NoAppInDeploymentManifest`
- `0x13510`: `DownloadApplicationManifest called.`
- `0x13570`: `Deployment and application does not have matching security zones. deploymentZone=`
- `0x13605`: `Deployment and application does not have matching security zones. deploymentZone=`
- `0x135be`: `.manifest`
- `0x136fa`: `Application manifest has RequestedExecutionLevel specified. Check requested privileges.`

## pseudocode

```c

```

## disassembly

```asm
0x13510  ldstr    aDownloadapplic_0// "DownloadApplicationManifest called."
0x13515  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0x1351a  ldarg.0
0x1351b  callvirt instance class System.Deployment.Application.Manifest.DependentAssembly System.Deployment.Application.Manifest.AssemblyManifest::get_MainDependentAssembly()
0x13520  stloc.0
0x13521  ldloc.0
0x13522  brfalse.s loc_1352C
0x13524  ldloc.0
0x13525  callvirt instance string System.Deployment.Application.Manifest.DependentAssembly::get_Codebase()
0x1352a  brtrue.s loc_1353E
0x1352c  ldc.i4.s 0x10
0x1352e  ldstr    aExNoappindeplo// "Ex_NoAppInDeploymentManifest"
0x13533  call     string System.Deployment.Application.Resources::GetString(string s)
0x13538  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x1353d  throw
0x1353e  ldarg.s  5
0x13540  ldarg.2
0x13541  ldloc.0
0x13542  callvirt instance string System.Deployment.Application.Manifest.DependentAssembly::get_Codebase()
0x13547  newobj   instance void [System]System.Uri::.ctor(class [System]System.Uri, string)
0x1354c  stind.ref
0x1354d  ldarg.2
0x1354e  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x13553  call     class [mscorlib]System.Security.Policy.Zone [mscorlib]System.Security.Policy.Zone::CreateFromUrl(string)
0x13558  stloc.1
0x13559  ldarg.s  5
0x1355b  ldind.ref
0x1355c  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x13561  call     class [mscorlib]System.Security.Policy.Zone [mscorlib]System.Security.Policy.Zone::CreateFromUrl(string)
0x13566  stloc.2
0x13567  ldloc.1
0x13568  ldloc.2
0x13569  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x1356e  brtrue.s loc_135B0
0x13570  ldstr    aDeploymentAndA// "Deployment and application does not hav"...
0x13575  ldloc.1
0x13576  dup
0x13577  brtrue.s loc_1357D
0x13579  pop
0x1357a  ldnull
0x1357b  br.s     loc_13582
0x1357d  callvirt instance string [mscorlib]System.Object::ToString()
0x13582  ldstr    aApplicationzon// ",applicationZone="
0x13587  ldloc.2
0x13588  dup
0x13589  brtrue.s loc_1358F
0x1358b  pop
0x1358c  ldnull
0x1358d  br.s     loc_13594
0x1358f  callvirt instance string [mscorlib]System.Object::ToString()
0x13594  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x13599  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1359e  ldc.i4.s 0x15
0x135a0  ldstr    aExDeployappzon// "Ex_DeployAppZoneMismatch"
0x135a5  call     string System.Deployment.Application.Resources::GetString(string s)
0x135aa  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x135af  throw
0x135b0  ldarg.s  6
0x135b2  ldarg.1
0x135b3  ldloc.0
0x135b4  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x135b9  callvirt instance string System.Deployment.Application.ReferenceIdentity::get_Name()
0x135be  ldstr    aManifest// ".manifest"
0x135c3  call     string [mscorlib]System.String::Concat(string, string)
0x135c8  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x135cd  stind.ref
0x135ce  ldarg.s  5
0x135d0  ldarg.s  6
0x135d2  ldind.ref
0x135d3  ldarg.3
0x135d4  ldarg.s  4
0x135d6  ldc.i4.0
0x135d7  ldloca.s 3
0x135d9  call     class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.DownloadManager::DownloadManifest(class [System]System.Uri& sourceUri, string targetPath, class System.Deployment.Application.IDownloadNotification notification, class System.Deployment.Application.DownloadOptions options, valuetype ManifestType manifestType, [out] class System.Deployment.Application.ServerInformation& serverInformation)
0x135de  stloc.s  4
0x135e0  ldarg.s  5
0x135e2  ldind.ref
0x135e3  call     void System.Deployment.Application.Logger::SetApplicationUrl(class [System]System.Uri applicationUri)
0x135e8  ldloc.3
0x135e9  call     void System.Deployment.Application.Logger::SetApplicationServerInformation(class System.Deployment.Application.ServerInformation serverInformation)
0x135ee  ldarg.s  5
0x135f0  ldind.ref
0x135f1  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x135f6  call     class [mscorlib]System.Security.Policy.Zone [mscorlib]System.Security.Policy.Zone::CreateFromUrl(string)
0x135fb  stloc.2
0x135fc  ldloc.1
0x135fd  ldloc.2
0x135fe  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x13603  brtrue.s loc_13645
0x13605  ldstr    aDeploymentAndA// "Deployment and application does not hav"...
0x1360a  ldloc.1
0x1360b  dup
0x1360c  brtrue.s loc_13612
0x1360e  pop
0x1360f  ldnull
0x13610  br.s     loc_13617
0x13612  callvirt instance string [mscorlib]System.Object::ToString()
0x13617  ldstr    aApplicationzon// ",applicationZone="
0x1361c  ldloc.2
0x1361d  dup
0x1361e  brtrue.s loc_13624
0x13620  pop
0x13621  ldnull
0x13622  br.s     loc_13629
0x13624  callvirt instance string [mscorlib]System.Object::ToString()
0x13629  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x1362e  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x13633  ldc.i4.s 0x15
0x13635  ldstr    aExDeployappzon// "Ex_DeployAppZoneMismatch"
0x1363a  call     string System.Deployment.Application.Resources::GetString(string s)
0x1363f  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x13644  throw
0x13645  ldloc.s  4
0x13647  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x1364c  ldarg.0
0x1364d  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x13652  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x13657  brfalse.s loc_1368A
0x13659  ldc.i4.s 0x10
0x1365b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x13660  ldstr    aExDepsamedeplo// "Ex_DepSameDeploymentAndApplicationIdent"...
0x13665  call     string System.Deployment.Application.Resources::GetString(string s)
0x1366a  ldc.i4.1
0x1366b  newarr   [mscorlib]System.Object
0x13670  dup
0x13671  ldc.i4.0
0x13672  ldloc.s  4
0x13674  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x13679  callvirt instance string [mscorlib]System.Object::ToString()
0x1367e  stelem.ref
0x1367f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13684  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x13689  throw
0x1368a  ldloc.s  4
0x1368c  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x13691  ldloc.0
0x13692  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x13697  ldloc.s  4
0x13699  callvirt instance bool System.Deployment.Application.Manifest.AssemblyManifest::get_Application()
0x1369e  callvirt instance bool System.Deployment.Application.DefinitionIdentity::Matches(class System.Deployment.Application.ReferenceIdentity refId, bool exact)
0x136a3  brtrue.s loc_136B7
0x136a5  ldc.i4.s 0x13
0x136a7  ldstr    aExRefdefmismat// "Ex_RefDefMismatch"
0x136ac  call     string System.Deployment.Application.Resources::GetString(string s)
0x136b1  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x136b6  throw
0x136b7  call     bool System.Deployment.Application.PolicyKeys::SkipApplicationDependencyHashCheck()
0x136bc  brtrue.s loc_136F1
0x136be  ldarg.s  6
0x136c0  ldind.ref
0x136c1  ldloc.0
0x136c2  callvirt instance class System.Deployment.Application.HashCollection System.Deployment.Application.Manifest.DependentAssembly::get_HashCollection()
0x136c7  call     void System.Deployment.Application.ComponentVerifier::VerifyFileHash(string filePath, class System.Deployment.Application.HashCollection hashCollection)
0x136cc  leave.s  loc_136F1
0x136ce  stloc.s  5
0x136d0  ldloc.s  5
0x136d2  callvirt instance valuetype System.Deployment.Application.ExceptionTypes System.Deployment.Application.DeploymentException::get_SubType()
0x136d7  ldc.i4.s 0x19
0x136d9  bne.un.s loc_136EF
0x136db  ldc.i4.s 0x19
0x136dd  ldstr    aExAppmaninvali// "Ex_AppManInvalidHash"
0x136e2  call     string System.Deployment.Application.Resources::GetString(string s)
0x136e7  ldloc.s  5
0x136e9  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0x136ee  throw
0x136ef  rethrow
0x136f1  ldloc.s  4
0x136f3  callvirt instance string System.Deployment.Application.Manifest.AssemblyManifest::get_RequestedExecutionLevel()
0x136f8  brfalse.s loc_13710
0x136fa  ldstr    aApplicationMan_0// "Application manifest has RequestedExecu"...
0x136ff  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x13704  ldloc.s  4
0x13706  callvirt instance string System.Deployment.Application.Manifest.AssemblyManifest::get_RequestedExecutionLevel()
0x1370b  call     void System.Deployment.Application.DownloadManager::VerifyRequestedPrivilegesSupport(string requestedExecutionLevel)
0x13710  ldloc.s  4
0x13712  ret
```
