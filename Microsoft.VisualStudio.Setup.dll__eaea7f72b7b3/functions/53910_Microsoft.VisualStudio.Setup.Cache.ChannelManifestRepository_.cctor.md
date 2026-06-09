# Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::.cctor

- ea: `0x53910`
- end: `0x53957`
- name: `Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::.cctor`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## string_xrefs

- `0x53910`: `channelManifest.json`
- `0x5391a`: `installChannelManifest.json`
- `0x53924`: `install_`
- `0x5394c`: `.lastupdatedate`

## pseudocode

```c

```

## disassembly

```asm
0x53910  ldstr    aChannelmanifes_9// "channelManifest.json"
0x53915  stsfld   string Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::ChannelManifestFileName
0x5391a  ldstr    aInstallchannel_2// "installChannelManifest.json"
0x5391f  stsfld   string Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::InstallChannelManifestFileName
0x53924  ldstr    aInstall_1// "install_"
0x53929  ldsfld   string Microsoft.VisualStudio.Setup.Cache.InstanceRepository::CatalogFileName
0x5392e  call     string [mscorlib]System.String::Concat(string, string)
0x53933  stsfld   string Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::InstallProductManifestFileName
0x53938  ldstr    aChannels// "_Channels"
0x5393d  stsfld   string Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::SubdirectoryName
0x53942  newobj   instance void [mscorlib]System.Object::.ctor()
0x53947  stsfld   object Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::SyncRoot
0x5394c  ldstr    aLastupdatedate// ".lastupdatedate"
0x53951  stsfld   string Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::UpdateFileName
0x53956  ret
```
