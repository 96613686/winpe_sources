# __imp_load_GetBasicProfileFolderPath

- ea: `0x1800027a2`
- end: `0x1800027ae`
- name: `__imp_load_GetBasicProfileFolderPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002723`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800027a2`

## pseudocode

```c
__int64 load_GetBasicProfileFolderPath()
{
  return _tailMerge_profapi_dll();
}

```

## disassembly

```asm
0x1800027a2  lea     rax, __imp_GetBasicProfileFolderPath
0x1800027a9  jmp     __tailMerge_profapi_dll
```
