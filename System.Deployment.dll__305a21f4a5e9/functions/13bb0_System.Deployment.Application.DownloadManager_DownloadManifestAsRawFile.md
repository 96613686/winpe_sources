# System.Deployment.Application.DownloadManager::DownloadManifestAsRawFile

- ea: `0x13bb0`
- end: `0x13c24`
- name: `System.Deployment.Application.DownloadManager::DownloadManifestAsRawFile`
- size: `116`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x139e0`
- `0x13b90`

## callees

- `0x13bb0`
- `0x14e00`
- `0x14e20`
- `0x14f30`
- `0x14fa0`
- `0x14fb0`
- `0x14fc0`
- `0x14ff0`
- `0x15070`
- `0x157e0`
- `0x15830`
- `0x17cd0`

## string_xrefs

- `0x13bb0`: `DownloadManifestAsRawFile called.`

## pseudocode

```c

```

## disassembly

```asm
0x13bb0  ldstr    aDownloadmanife_0// "DownloadManifestAsRawFile called."
0x13bb5  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0x13bba  call     class System.Deployment.Application.FileDownloader System.Deployment.Application.FileDownloader::Create()
0x13bbf  stloc.0
0x13bc0  ldloc.0
0x13bc1  ldarg.3
0x13bc2  callvirt instance void System.Deployment.Application.FileDownloader::set_Options(class System.Deployment.Application.DownloadOptions value)
0x13bc7  ldarg.2
0x13bc8  brfalse.s loc_13BD1
0x13bca  ldloc.0
0x13bcb  ldarg.2
0x13bcc  callvirt instance void System.Deployment.Application.FileDownloader::AddNotification(class System.Deployment.Application.IDownloadNotification notification)
0x13bd1  nop
0x13bd2  ldloc.0
0x13bd3  ldarg.0
0x13bd4  ldind.ref
0x13bd5  ldarg.1
0x13bd6  ldc.i4   0x1000000
0x13bdb  callvirt instance void System.Deployment.Application.FileDownloader::AddFile(class [System]System.Uri sourceUri, string targetFilePath, int32 maxFileSize)
0x13be0  ldloc.0
0x13be1  ldnull
0x13be2  ldsfld   class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 System.Deployment.Application.DownloadManager::ClientCertificate
0x13be7  callvirt instance void System.Deployment.Application.FileDownloader::Download(class System.Deployment.Application.SubscriptionState subState, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 clientCertificate)
0x13bec  ldarg.0
0x13bed  ldloc.0
0x13bee  callvirt instance class System.Deployment.Application.DownloadResult[] System.Deployment.Application.FileDownloader::get_DownloadResults()
0x13bf3  ldc.i4.0
0x13bf4  ldelem.ref
0x13bf5  callvirt instance class [System]System.Uri System.Deployment.Application.DownloadResult::get_ResponseUri()
0x13bfa  stind.ref
0x13bfb  ldarg.s  4
0x13bfd  ldloc.0
0x13bfe  callvirt instance class System.Deployment.Application.DownloadResult[] System.Deployment.Application.FileDownloader::get_DownloadResults()
0x13c03  ldc.i4.0
0x13c04  ldelem.ref
0x13c05  callvirt instance class System.Deployment.Application.ServerInformation System.Deployment.Application.DownloadResult::get_ServerInformation()
0x13c0a  stind.ref
0x13c0b  ldloc.0
0x13c0c  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 System.Deployment.Application.FileDownloader::get_ClientCertificate()
0x13c11  stsfld   class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 System.Deployment.Application.DownloadManager::ClientCertificate
0x13c16  leave.s  loc_13C23
0x13c18  ldarg.2
0x13c19  brfalse.s loc_13C22
0x13c1b  ldloc.0
0x13c1c  ldarg.2
0x13c1d  callvirt instance void System.Deployment.Application.FileDownloader::RemoveNotification(class System.Deployment.Application.IDownloadNotification notification)
0x13c22  endfinally
0x13c23  ret
```
