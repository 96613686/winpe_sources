# __imp_load_GetProfilesDirectoryW

- ea: `0x180004496`
- end: `0x1800044a2`
- name: `__imp_load_GetProfilesDirectoryW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800043bd`

## import_xrefs

- `USERENV!GetProfilesDirectoryW` at `0x180004496`

## pseudocode

```c
__int64 load_GetProfilesDirectoryW()
{
  return _tailMerge_userenv_dll();
}

```

## disassembly

```asm
0x180004496  lea     rax, __imp_GetProfilesDirectoryW
0x18000449d  jmp     __tailMerge_userenv_dll
```
