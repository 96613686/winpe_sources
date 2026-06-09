# __std_fs_rename

- ea: `0x1801d2a54`
- end: `0x1801d2a7a`
- name: `__std_fs_rename`
- size: `38`
- prototype: `DWORD __fastcall(const WCHAR *, const WCHAR *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18003e920`

## callees

- `0x1801d2a54`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801d2a73`
- `KERNEL32!MoveFileExW` at `0x1801d2a5e`
- `KERNEL32!MoveFileExW` at `0x1801d2a5e`

## pseudocode

```c
DWORD __fastcall _std_fs_rename(const WCHAR *a1, const WCHAR *a2)
{
  if ( MoveFileExW(a1, a2, 3u) )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x1801d2a54  sub     rsp, 28h
0x1801d2a58  mov     r8d, 3; dwFlags
0x1801d2a5e  call    cs:__imp_MoveFileExW
0x1801d2a64  test    eax, eax
0x1801d2a66  jz      short loc_1801D2A6F
0x1801d2a68  xor     eax, eax
0x1801d2a6a  add     rsp, 28h
0x1801d2a6e  retn
0x1801d2a6f  add     rsp, 28h
0x1801d2a73  jmp     cs:__imp_GetLastError
```
