# __imp_load_GetBasicProfileFolderPath

- ea: `0x180077c03`
- end: `0x180077c0f`
- name: `__imp_load_GetBasicProfileFolderPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180077b84`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPath` at `0x180077c03`

## pseudocode

```c
__int64 load_GetBasicProfileFolderPath()
{
  return _tailMerge_profapi_dll();
}

```

## disassembly

```asm
0x180077c03  lea     rax, __imp_GetBasicProfileFolderPath
0x180077c0a  jmp     __tailMerge_profapi_dll
```
