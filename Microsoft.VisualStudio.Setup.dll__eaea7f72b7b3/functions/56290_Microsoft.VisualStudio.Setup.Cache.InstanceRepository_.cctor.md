# Microsoft.VisualStudio.Setup.Cache.InstanceRepository::.cctor

- ea: `0x56290`
- end: `0x562d7`
- name: `Microsoft.VisualStudio.Setup.Cache.InstanceRepository::.cctor`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## string_xrefs

- `0x56290`: `catalog.json`
- `0x5629a`: `catalog.previous.json`
- `0x562a4`: `components.json`
- `0x562cc`: `Extensions`

## pseudocode

```c

```

## disassembly

```asm
0x56290  ldstr    aCatalogJson_0// "catalog.json"
0x56295  stsfld   string Microsoft.VisualStudio.Setup.Cache.InstanceRepository::CatalogFileName
0x5629a  ldstr    aCatalogPreviou// "catalog.previous.json"
0x5629f  stsfld   string Microsoft.VisualStudio.Setup.Cache.InstanceRepository::PreviousCatalogFileName
0x562a4  ldstr    aComponentsJson// "components.json"
0x562a9  stsfld   string Microsoft.VisualStudio.Setup.Cache.InstanceRepository::ComponentCacheFileName
0x562ae  ldsfld   string Microsoft.VisualStudio.Setup.Cache.FileStateManager::StateFileName
0x562b3  stsfld   string Microsoft.VisualStudio.Setup.Cache.InstanceRepository::StateFileName
0x562b8  ldstr    aInstances// "_Instances"
0x562bd  stsfld   string Microsoft.VisualStudio.Setup.Cache.InstanceRepository::SubdirectoryName
0x562c2  newobj   instance void [mscorlib]System.Object::.ctor()
0x562c7  stsfld   object Microsoft.VisualStudio.Setup.Cache.InstanceRepository::SyncRoot
0x562cc  ldstr    aExtensions// "Extensions"
0x562d1  stsfld   string Microsoft.VisualStudio.Setup.Cache.InstanceRepository::ExtensionsDirectoryName
0x562d6  ret
```
