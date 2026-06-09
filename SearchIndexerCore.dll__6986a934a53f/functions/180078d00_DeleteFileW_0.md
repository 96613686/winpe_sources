# DeleteFileW_0

- ea: `0x180078d00`
- end: `0x180078d06`
- name: `DeleteFileW_0`
- size: `6`
- prototype: `BOOL __stdcall(LPCWSTR lpFileName)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180078d00`

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
0x180078d00  jmp     cs:__imp_DeleteFileW
```
