# __imp_load_GetPersistedRegistryLocationW

- ea: `0x18000a575`
- end: `0x18000a581`
- name: `__imp_load_GetPersistedRegistryLocationW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18000a4f6`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000a575`

## pseudocode

```c
__int64 load_GetPersistedRegistryLocationW()
{
  return _tailMerge_api_ms_win_stateseparation_helpers_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000a575  lea     rax, __imp_GetPersistedRegistryLocationW
0x18000a57c  jmp     __tailMerge_api_ms_win_stateseparation_helpers_l1_1_0_dll
```
