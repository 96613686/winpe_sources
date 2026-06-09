# DeleteFileA_0

- ea: `0x1800e4f20`
- end: `0x1800e4f26`
- name: `DeleteFileA_0`
- size: `6`
- prototype: `BOOL __stdcall(LPCSTR lpFileName)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x1800e4f20`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall DeleteFileA_0(LPCSTR lpFileName)
{
  return DeleteFileA(lpFileName);
}

```

## disassembly

```asm
0x1800e4f20  jmp     cs:__imp_DeleteFileA
```
