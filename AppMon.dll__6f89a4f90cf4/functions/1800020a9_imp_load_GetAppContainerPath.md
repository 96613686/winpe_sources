# __imp_load_GetAppContainerPath

- ea: `0x1800020a9`
- end: `0x1800020b5`
- name: `__imp_load_GetAppContainerPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000202a`

## import_xrefs

- `profapi!__imp_GetAppContainerPath` at `0x1800020a9`

## pseudocode

```c
__int64 load_GetAppContainerPath()
{
  return _tailMerge_profapi_dll();
}

```

## disassembly

```asm
0x1800020a9  lea     rax, __imp_GetAppContainerPath
0x1800020b0  jmp     __tailMerge_profapi_dll
```
