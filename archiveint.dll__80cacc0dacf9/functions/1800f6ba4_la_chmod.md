# la_chmod

- ea: `0x1800f6ba4`
- end: `0x1800f6c33`
- name: `la_chmod`
- size: `143`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800f49d0`
- `0x1800f6cd0`
- `0x1800f7920`

## callees

- `0x1800149c0`
- `0x1800ef3f8`
- `0x1800f6ba4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f6c22`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f6c22`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800f6c05`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800f6c05`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800f6bb5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800f6bdd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800f6bb5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800f6bdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f6bc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f6c0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f6bc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f6c0f`

## pseudocode

```c
__int64 __fastcall la_chmod(LPCWSTR lpFileName, char a2)
{
  wchar_t *v4; // rdi
  DWORD FileAttributesW; // edx
  unsigned int v6; // ebx
  int v7; // eax
  DWORD v8; // edx
  const WCHAR *v9; // rcx
  DWORD LastError; // eax

  v4 = 0;
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW == -1 )
  {
    if ( GetLastError() != 123 )
      goto LABEL_9;
    v4 = _la_win_permissive_name_w(lpFileName);
    FileAttributesW = GetFileAttributesW(v4);
    if ( FileAttributesW == -1 )
      goto LABEL_9;
  }
  v6 = 0;
  v7 = FileAttributesW | 1;
  v8 = FileAttributesW & 0xFFFFFFFE;
  v9 = v4;
  if ( (a2 & 0x80) == 0 )
    v8 = v7;
  if ( !v4 )
    v9 = lpFileName;
  if ( !SetFileAttributesW(v9, v8) )
  {
LABEL_9:
    LastError = GetLastError();
    _la_dosmaperr(LastError);
    v6 = -1;
  }
  free(v4);
  return v6;
}

```

## disassembly

```asm
0x1800f6ba4  push    rbx
0x1800f6ba6  push    rbp
0x1800f6ba7  push    rsi
0x1800f6ba8  push    rdi
0x1800f6ba9  sub     rsp, 28h
0x1800f6bad  movzx   ebp, dx
0x1800f6bb0  mov     rsi, rcx
0x1800f6bb3  xor     edi, edi
0x1800f6bb5  call    cs:__imp_GetFileAttributesW
0x1800f6bbb  or      ebx, 0FFFFFFFFh
0x1800f6bbe  mov     edx, eax
0x1800f6bc0  cmp     eax, ebx
0x1800f6bc2  jnz     short loc_1800F6BE9
0x1800f6bc4  call    cs:__imp_GetLastError
0x1800f6bca  cmp     eax, 7Bh ; '{'
0x1800f6bcd  jnz     short loc_1800F6C0F
0x1800f6bcf  mov     rcx, rsi; lpFileName
0x1800f6bd2  call    __la_win_permissive_name_w
0x1800f6bd7  mov     rcx, rax; lpFileName
0x1800f6bda  mov     rdi, rax
0x1800f6bdd  call    cs:__imp_GetFileAttributesW
0x1800f6be3  mov     edx, eax
0x1800f6be5  cmp     eax, ebx
0x1800f6be7  jz      short loc_1800F6C0F
0x1800f6be9  mov     eax, edx
0x1800f6beb  xor     ebx, ebx
0x1800f6bed  or      eax, 1
0x1800f6bf0  and     edx, 0FFFFFFFEh
0x1800f6bf3  and     bpl, 80h
0x1800f6bf7  mov     rcx, rdi
0x1800f6bfa  cmovz   edx, eax; dwFileAttributes
0x1800f6bfd  test    rdi, rdi
0x1800f6c00  jnz     short loc_1800F6C05
0x1800f6c02  mov     rcx, rsi; lpFileName
0x1800f6c05  call    cs:__imp_SetFileAttributesW
0x1800f6c0b  test    eax, eax
0x1800f6c0d  jnz     short loc_1800F6C1F
0x1800f6c0f  call    cs:__imp_GetLastError
0x1800f6c15  mov     ecx, eax
0x1800f6c17  call    __la_dosmaperr
0x1800f6c1c  or      ebx, 0FFFFFFFFh
0x1800f6c1f  mov     rcx, rdi; Block
0x1800f6c22  call    cs:__imp_free
0x1800f6c28  mov     eax, ebx
0x1800f6c2a  add     rsp, 28h
0x1800f6c2e  pop     rdi
0x1800f6c2f  pop     rsi
0x1800f6c30  pop     rbp
0x1800f6c31  pop     rbx
0x1800f6c32  retn
```
