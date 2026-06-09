# System.Deployment.Application.DownloadManager::DownloadDependencies

- ea: `0x13720`
- end: `0x13811`
- name: `System.Deployment.Application.DownloadManager::DownloadDependencies`
- size: `241`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0xba90`
- `0x11d60`
- `0x122a0`

## callees

- `0x10200`
- `0x13720`
- `0x13820`
- `0x13c30`
- `0x14e70`
- `0x14ea0`
- `0x14fa0`
- `0x14fb0`
- `0x14fc0`
- `0x14ff0`
- `0x15100`
- `0x157e0`
- `0x158a0`
- `0x17cd0`
- `0x17d40`
- `0x252e0`
- `0x28e60`

## string_xrefs

- `0x1372a`: `sourceUriBase=`
- `0x13746`: `targetDirectory=`

## pseudocode

```c

```

## disassembly

```asm
0x13720  ldstr    aDownloaddepend// "DownloadDependencies called."
0x13725  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0x1372a  ldstr    aSourceuribase// "sourceUriBase="
0x1372f  ldarg.3
0x13730  dup
0x13731  brtrue.s loc_13737
0x13733  pop
0x13734  ldnull
0x13735  br.s     loc_1373C
0x13737  callvirt instance string [mscorlib]System.Object::ToString()
0x1373c  call     string [mscorlib]System.String::Concat(string, string)
0x13741  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x13746  ldstr    aTargetdirector// "targetDirectory="
0x1374b  ldarg.s  4
0x1374d  call     string [mscorlib]System.String::Concat(string, string)
0x13752  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x13757  ldstr    aGroup// "group="
0x1375c  ldarg.s  5
0x1375e  call     string [mscorlib]System.String::Concat(string, string)
0x13763  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x13768  ldstr    aDownloadoption// "DownloadOptions="
0x1376d  ldarg.s  7
0x1376f  dup
0x13770  brtrue.s loc_13776
0x13772  pop
0x13773  ldnull
0x13774  br.s     loc_1377B
0x13776  callvirt instance string [mscorlib]System.Object::ToString()
0x1377b  call     string [mscorlib]System.String::Concat(string, string)
0x13780  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x13785  call     class System.Deployment.Application.FileDownloader System.Deployment.Application.FileDownloader::Create()
0x1378a  stloc.0
0x1378b  ldloc.0
0x1378c  ldarg.s  7
0x1378e  callvirt instance void System.Deployment.Application.FileDownloader::set_Options(class System.Deployment.Application.DownloadOptions value)
0x13793  ldarg.s  5
0x13795  brtrue.s loc_137A4
0x13797  ldloc.0
0x13798  ldarg.2
0x13799  callvirt instance unsigned int64 System.Deployment.Application.Manifest.AssemblyManifest::CalculateDependenciesSize()
0x1379e  ldc.i4.0
0x1379f  callvirt instance void System.Deployment.Application.FileDownloader::CheckForSizeLimit(unsigned int64 bytesDownloaded, bool addToSize)
0x137a4  ldloc.0
0x137a5  ldarg.1
0x137a6  ldarg.2
0x137a7  ldarg.3
0x137a8  ldarg.s  4
0x137aa  ldarg.s  5
0x137ac  call     void System.Deployment.Application.DownloadManager::AddDependencies(class System.Deployment.Application.FileDownloader downloader, class System.Deployment.Application.Manifest.AssemblyManifest deployManifest, class System.Deployment.Application.Manifest.AssemblyManifest appManifest, class [System]System.Uri sourceUriBase, string targetDirectory, string group)
0x137b1  ldloc.0
0x137b2  ldnull
0x137b3  ldftn    void System.Deployment.Application.DownloadManager::ProcessDownloadedFile(object sender, class System.Deployment.Application.DownloadEventArgs e)
0x137b9  newobj   instance void DownloadModifiedEventHandler::.ctor(object object, native int method)
0x137be  callvirt instance void System.Deployment.Application.FileDownloader::add_DownloadModified(class DownloadModifiedEventHandler value)
0x137c3  ldarg.s  6
0x137c5  brfalse.s loc_137CF
0x137c7  ldloc.0
0x137c8  ldarg.s  6
0x137ca  callvirt instance void System.Deployment.Application.FileDownloader::AddNotification(class System.Deployment.Application.IDownloadNotification notification)
0x137cf  nop
0x137d0  ldloc.0
0x137d1  ldarg.0
0x137d2  ldsfld   class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 System.Deployment.Application.DownloadManager::ClientCertificate
0x137d7  callvirt instance void System.Deployment.Application.FileDownloader::Download(class System.Deployment.Application.SubscriptionState subState, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 clientCertificate)
0x137dc  ldloc.0
0x137dd  callvirt instance class System.Deployment.Application.ComponentVerifier System.Deployment.Application.FileDownloader::get_ComponentVerifier()
0x137e2  callvirt instance void System.Deployment.Application.ComponentVerifier::VerifyComponents()
0x137e7  ldarg.2
0x137e8  ldarg.s  4
0x137ea  call     void System.Deployment.Application.DownloadManager::VerifyRequestedPrivilegesSupport(class System.Deployment.Application.Manifest.AssemblyManifest appManifest, string targetDirectory)
0x137ef  leave.s  loc_13810
0x137f1  ldarg.s  6
0x137f3  brfalse.s loc_137FD
0x137f5  ldloc.0
0x137f6  ldarg.s  6
0x137f8  callvirt instance void System.Deployment.Application.FileDownloader::RemoveNotification(class System.Deployment.Application.IDownloadNotification notification)
0x137fd  ldloc.0
0x137fe  ldnull
0x137ff  ldftn    void System.Deployment.Application.DownloadManager::ProcessDownloadedFile(object sender, class System.Deployment.Application.DownloadEventArgs e)
0x13805  newobj   instance void DownloadModifiedEventHandler::.ctor(object object, native int method)
0x1380a  callvirt instance void System.Deployment.Application.FileDownloader::remove_DownloadModified(class DownloadModifiedEventHandler value)
0x1380f  endfinally
0x13810  ret
```
