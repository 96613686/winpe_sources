# __imp_load_GetAppContainerRegistryLocation

- ea: `0x18007764d`
- end: `0x180077659`
- name: `__imp_load_GetAppContainerRegistryLocation`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800775ce`

## import_xrefs

- `USERENV!GetAppContainerRegistryLocation` at `0x18007764d`

## pseudocode

```c
__int64 load_GetAppContainerRegistryLocation()
{
  return _tailMerge_userenv_dll();
}

```

## disassembly

```asm
0x18007764d  lea     rax, __imp_GetAppContainerRegistryLocation
0x180077654  jmp     __tailMerge_userenv_dll
```
