# System.Deployment.Application.DownloadManager::DownloadDeploymentManifest_0

- ea: `0x13180`
- end: `0x13229`
- name: `System.Deployment.Application.DownloadManager::DownloadDeploymentManifest_0`
- size: `169`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x113b0`
- `0x13170`

## callees

- `0x13110`
- `0x13180`
- `0x13230`
- `0x13950`
- `0x17760`
- `0x17cd0`
- `0x17d40`

## string_xrefs

- `0x13180`: `DownloadDeploymentManifest called.`
- `0x1318a`: `SourceUri=`

## pseudocode

```c

```

## disassembly

```asm
0x13180  ldstr    aDownloaddeploy// "DownloadDeploymentManifest called."
0x13185  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0x1318a  ldstr    aSourceuri// "SourceUri="
0x1318f  ldarg.1
0x13190  ldind.ref
0x13191  dup
0x13192  brtrue.s loc_13198
0x13194  pop
0x13195  ldnull
0x13196  br.s     loc_1319D
0x13198  callvirt instance string [mscorlib]System.Object::ToString()
0x1319d  call     string [mscorlib]System.String::Concat(string, string)
0x131a2  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x131a7  ldstr    aDownloadoption// "DownloadOptions="
0x131ac  ldarg.s  4
0x131ae  brtrue.s loc_131B7
0x131b0  ldstr    aNull// "null"
0x131b5  br.s     loc_131BE
0x131b7  ldarg.s  4
0x131b9  callvirt instance string [mscorlib]System.Object::ToString()
0x131be  call     string [mscorlib]System.String::Concat(string, string)
0x131c3  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x131c8  ldarg.2
0x131c9  ldnull
0x131ca  stind.ref
0x131cb  ldnull
0x131cc  stloc.0
0x131cd  ldnull
0x131ce  stloc.1
0x131cf  ldnull
0x131d0  stsfld   class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 System.Deployment.Application.DownloadManager::ClientCertificate
0x131d5  ldarg.0
0x131d6  ldarg.1
0x131d7  ldloca.s 0
0x131d9  ldarg.3
0x131da  ldarg.s  4
0x131dc  ldloca.s 3
0x131de  call     class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.DownloadManager::DownloadDeploymentManifestDirect(class System.Deployment.Application.SubscriptionStore subStore, class [System]System.Uri& sourceUri, [out] class System.Deployment.Application.TempFile& tempFile, class System.Deployment.Application.IDownloadNotification notification, class System.Deployment.Application.DownloadOptions options, [out] class System.Deployment.Application.ServerInformation& serverInformation)
0x131e3  stloc.2
0x131e4  ldloc.3
0x131e5  call     void System.Deployment.Application.Logger::SetSubscriptionServerInformation(class System.Deployment.Application.ServerInformation serverInformation)
0x131ea  ldarg.0
0x131eb  ldloca.s 2
0x131ed  ldarg.1
0x131ee  ldloca.s 1
0x131f0  ldarg.3
0x131f1  ldarg.s  4
0x131f3  call     bool System.Deployment.Application.DownloadManager::FollowDeploymentProviderUri(class System.Deployment.Application.SubscriptionStore subStore, class System.Deployment.Application.Manifest.AssemblyManifest& deployment, class [System]System.Uri& sourceUri, [out] class System.Deployment.Application.TempFile& tempFile, class System.Deployment.Application.IDownloadNotification notification, class System.Deployment.Application.DownloadOptions options)
0x131f8  stloc.s  4
0x131fa  ldarg.2
0x131fb  ldloc.s  4
0x131fd  brtrue.s loc_13202
0x131ff  ldloc.0
0x13200  br.s     loc_13203
0x13202  ldloc.1
0x13203  stind.ref
0x13204  leave.s  loc_13227
0x13206  ldloc.0
0x13207  brfalse.s loc_13216
0x13209  ldloc.0
0x1320a  ldarg.2
0x1320b  ldind.ref
0x1320c  beq.s    loc_13216
0x1320e  ldloc.0
0x1320f  callvirt instance void System.Deployment.Application.DisposableBase::Dispose()
0x13214  ldnull
0x13215  stloc.0
0x13216  ldloc.1
0x13217  brfalse.s loc_13226
0x13219  ldloc.1
0x1321a  ldarg.2
0x1321b  ldind.ref
0x1321c  beq.s    loc_13226
0x1321e  ldloc.1
0x1321f  callvirt instance void System.Deployment.Application.DisposableBase::Dispose()
0x13224  ldnull
0x13225  stloc.1
0x13226  endfinally
0x13227  ldloc.2
0x13228  ret
```
