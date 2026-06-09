# Microsoft.VisualStudio.Setup.Cache.FileStateManager::.cctor

- ea: `0x55100`
- end: `0x55143`
- name: `Microsoft.VisualStudio.Setup.Cache.FileStateManager::.cctor`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## string_xrefs

- `0x55100`: `state.json`
- `0x5510a`: `state.packages.json`
- `0x55114`: `state.errors.json`
- `0x5511e`: `state.groups.json`
- `0x55128`: `state.ngen.json`

## pseudocode

```c

```

## disassembly

```asm
0x55100  ldstr    aStateJson// "state.json"
0x55105  stsfld   string Microsoft.VisualStudio.Setup.Cache.FileStateManager::StateFileName
0x5510a  ldstr    aStatePackagesJ// "state.packages.json"
0x5510f  stsfld   string Microsoft.VisualStudio.Setup.Cache.FileStateManager::StatePackagesFileName
0x55114  ldstr    aStateErrorsJso// "state.errors.json"
0x55119  stsfld   string Microsoft.VisualStudio.Setup.Cache.FileStateManager::StateErrorsFileName
0x5511e  ldstr    aStateGroupsJso// "state.groups.json"
0x55123  stsfld   string Microsoft.VisualStudio.Setup.Cache.FileStateManager::StateGroupConfigsFileName
0x55128  ldstr    aStateNgenJson// "state.ngen.json"
0x5512d  stsfld   string Microsoft.VisualStudio.Setup.Cache.FileStateManager::StateNgenFileName
0x55132  ldc.i4.1
0x55133  ldc.i4.s 0xF
0x55135  ldc.i4.s 0x23
0x55137  ldc.i4.0
0x55138  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x5513d  stsfld   class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Cache.FileStateManager::RequiredEngineVersion
0x55142  ret
```
