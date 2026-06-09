# DeleteFileW_0

- ea: `0x180003790`
- end: `0x180003796`
- name: `DeleteFileW_0`
- size: `6`
- prototype: `BOOL __stdcall(LPCWSTR lpFileName)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180003790`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall DeleteFileW_0(LPCWSTR lpFileName)
{
  return DeleteFileW(lpFileName);
}

```

## disassembly

```asm
0x180003790  jmp     cs:__imp_DeleteFileW
```
