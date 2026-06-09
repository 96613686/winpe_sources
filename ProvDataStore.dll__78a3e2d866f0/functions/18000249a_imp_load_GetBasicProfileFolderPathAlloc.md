# __imp_load_GetBasicProfileFolderPathAlloc

- ea: `0x18000249a`
- end: `0x1800024a6`
- name: `__imp_load_GetBasicProfileFolderPathAlloc`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000241b`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x18000249a`

## pseudocode

```c
__int64 load_GetBasicProfileFolderPathAlloc()
{
  return _tailMerge_profapi_dll();
}

```

## disassembly

```asm
0x18000249a  lea     rax, __imp_GetBasicProfileFolderPathAlloc
0x1800024a1  jmp     __tailMerge_profapi_dll
```
