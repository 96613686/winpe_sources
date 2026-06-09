# __imp_load_GetAppContainerRegistryLocation

- ea: `0x180001f79`
- end: `0x180001f85`
- name: `__imp_load_GetAppContainerRegistryLocation`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001efa`

## import_xrefs

- `USERENV!GetAppContainerRegistryLocation` at `0x180001f79`

## pseudocode

```c
__int64 load_GetAppContainerRegistryLocation()
{
  return _tailMerge_userenv_dll();
}

```

## disassembly

```asm
0x180001f79  lea     rax, __imp_GetAppContainerRegistryLocation
0x180001f80  jmp     __tailMerge_userenv_dll
```
