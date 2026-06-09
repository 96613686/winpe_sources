# System.Deployment.Application.DownloadManager::DownloadManifest

- ea: `0x13b90`
- end: `0x13bb0`
- name: `System.Deployment.Application.DownloadManager::DownloadManifest`
- size: `32`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x13510`
- `0x13950`

## callees

- `0x13bb0`
- `0x17cd0`
- `0x19e90`

## string_xrefs

- `0x13b90`: `DownloadManifest called.`

## pseudocode

```c

```

## disassembly

```asm
0x13b90  ldstr    aDownloadmanife// "DownloadManifest called."
0x13b95  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0x13b9a  ldarg.0
0x13b9b  ldarg.1
0x13b9c  ldarg.2
0x13b9d  ldarg.3
0x13b9e  ldarg.s  5
0x13ba0  call     void System.Deployment.Application.DownloadManager::DownloadManifestAsRawFile(class [System]System.Uri& sourceUri, string targetPath, class System.Deployment.Application.IDownloadNotification notification, class System.Deployment.Application.DownloadOptions options, [out] class System.Deployment.Application.ServerInformation& serverInformation)
0x13ba5  ldarg.1
0x13ba6  ldarg.s  4
0x13ba8  ldarg.0
0x13ba9  ldind.ref
0x13baa  call     class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.ManifestReader::FromDocument(string localPath, valuetype ManifestType manifestType, class [System]System.Uri sourceUri)
0x13baf  ret
```
