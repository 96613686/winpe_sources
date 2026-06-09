# __imp_load_GetAppContainerFolderPath

- ea: `0x1800088da`
- end: `0x1800088e6`
- name: `__imp_load_GetAppContainerFolderPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008849`

## import_xrefs

- `USERENV!GetAppContainerFolderPath` at `0x1800088da`

## pseudocode

```c
__int64 load_GetAppContainerFolderPath()
{
  return _tailMerge_userenv_dll();
}

```

## disassembly

```asm
0x1800088da  lea     rax, __imp_GetAppContainerFolderPath
0x1800088e1  jmp     __tailMerge_userenv_dll
```
