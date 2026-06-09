# System.Deployment.Application.DownloadManager::DownloadDeploymentManifestBypass

- ea: `0x13480`
- end: `0x134fc`
- name: `System.Deployment.Application.DownloadManager::DownloadDeploymentManifestBypass`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0xabd0`
- `0xae50`

## callees

- `0x13110`
- `0x13230`
- `0x13480`
- `0x139e0`
- `0x17760`
- `0x17cd0`

## string_xrefs

- `0x13480`: `DownloadDeploymentManifestBypass called.`

## pseudocode

```c

```

## disassembly

```asm
0x13480  ldstr    aDownloaddeploy_0// "DownloadDeploymentManifestBypass called"...
0x13485  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0x1348a  ldarg.2
0x1348b  ldnull
0x1348c  stind.ref
0x1348d  ldarg.3
0x1348e  ldnull
0x1348f  stind.ref
0x13490  ldnull
0x13491  stloc.0
0x13492  ldnull
0x13493  stloc.1
0x13494  ldnull
0x13495  stsfld   class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 System.Deployment.Application.DownloadManager::ClientCertificate
0x1349a  ldarg.0
0x1349b  ldarg.1
0x1349c  ldloca.s 0
0x1349e  ldarg.3
0x1349f  ldarg.s  4
0x134a1  ldarg.s  5
0x134a3  ldloca.s 3
0x134a5  call     class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.DownloadManager::DownloadDeploymentManifestDirectBypass(class System.Deployment.Application.SubscriptionStore subStore, class [System]System.Uri& sourceUri, [out] class System.Deployment.Application.TempFile& tempFile, [out] class System.Deployment.Application.SubscriptionState& subState, class System.Deployment.Application.IDownloadNotification notification, class System.Deployment.Application.DownloadOptions options, [out] class System.Deployment.Application.ServerInformation& serverInformation)
0x134aa  stloc.2
0x134ab  ldloc.3
0x134ac  call     void System.Deployment.Application.Logger::SetSubscriptionServerInformation(class System.Deployment.Application.ServerInformation serverInformation)
0x134b1  ldarg.3
0x134b2  ldind.ref
0x134b3  brfalse.s loc_134BD
0x134b5  ldarg.2
0x134b6  ldloc.0
0x134b7  stind.ref
0x134b8  ldloc.2
0x134b9  stloc.s  5
0x134bb  leave.s  loc_134F9
0x134bd  ldarg.0
0x134be  ldloca.s 2
0x134c0  ldarg.1
0x134c1  ldloca.s 1
0x134c3  ldarg.s  4
0x134c5  ldarg.s  5
0x134c7  call     bool System.Deployment.Application.DownloadManager::FollowDeploymentProviderUri(class System.Deployment.Application.SubscriptionStore subStore, class System.Deployment.Application.Manifest.AssemblyManifest& deployment, class [System]System.Uri& sourceUri, [out] class System.Deployment.Application.TempFile& tempFile, class System.Deployment.Application.IDownloadNotification notification, class System.Deployment.Application.DownloadOptions options)
0x134cc  stloc.s  4
0x134ce  ldarg.2
0x134cf  ldloc.s  4
0x134d1  brtrue.s loc_134D6
0x134d3  ldloc.0
0x134d4  br.s     loc_134D7
0x134d6  ldloc.1
0x134d7  stind.ref
0x134d8  leave.s  loc_134F7
0x134da  ldloc.0
0x134db  brfalse.s loc_134E8
0x134dd  ldloc.0
0x134de  ldarg.2
0x134df  ldind.ref
0x134e0  beq.s    loc_134E8
0x134e2  ldloc.0
0x134e3  callvirt instance void System.Deployment.Application.DisposableBase::Dispose()
0x134e8  ldloc.1
0x134e9  brfalse.s loc_134F6
0x134eb  ldloc.1
0x134ec  ldarg.2
0x134ed  ldind.ref
0x134ee  beq.s    loc_134F6
0x134f0  ldloc.1
0x134f1  callvirt instance void System.Deployment.Application.DisposableBase::Dispose()
0x134f6  endfinally
0x134f7  ldloc.2
0x134f8  ret
0x134f9  ldloc.s  5
0x134fb  ret
```
