# set_fflags_platform

- ea: `0x1800f7890`
- end: `0x1800f7917`
- name: `set_fflags_platform`
- size: `135`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800f49d0`
- `0x1800f4c10`
- `0x1800f5838`
- `0x1800f7330`

## callees

- `0x1800149c0`
- `0x1800ef3f8`
- `0x1800f7890`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800f78f8`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800f78f8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800f78a7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800f78c8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800f78a7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800f78c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f78b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f78d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f78b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f78d3`

## pseudocode

```c
__int64 __fastcall set_fflags_platform(LPCWSTR lpFileName, unsigned __int16 a2, __int16 a3)
{
  DWORD FileAttributesW; // eax
  wchar_t *v7; // rax
  DWORD LastError; // eax

  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW != -1 )
    return !SetFileAttributesW(lpFileName, (a2 | FileAttributesW & (unsigned __int16)~a3) & 0x31A7) ? 0xFFFFFFEC : 0;
  if ( GetLastError() == 123 )
  {
    v7 = _la_win_permissive_name_w(lpFileName);
    FileAttributesW = GetFileAttributesW(v7);
    if ( FileAttributesW != -1 )
      return !SetFileAttributesW(lpFileName, (a2 | FileAttributesW & (unsigned __int16)~a3) & 0x31A7) ? 0xFFFFFFEC : 0;
  }
  LastError = GetLastError();
  _la_dosmaperr(LastError);
  return 4294967276LL;
}

```

## disassembly

```asm
0x1800f7890  mov     [rsp+arg_0], rbx
0x1800f7895  mov     [rsp+arg_8], rsi
0x1800f789a  push    rdi
0x1800f789b  sub     rsp, 20h
0x1800f789f  mov     ebx, r8d
0x1800f78a2  mov     esi, edx
0x1800f78a4  mov     rdi, rcx
0x1800f78a7  call    cs:__imp_GetFileAttributesW
0x1800f78ad  cmp     eax, 0FFFFFFFFh
0x1800f78b0  jnz     short loc_1800F78E7
0x1800f78b2  call    cs:__imp_GetLastError
0x1800f78b8  cmp     eax, 7Bh ; '{'
0x1800f78bb  jnz     short loc_1800F78D3
0x1800f78bd  mov     rcx, rdi; lpFileName
0x1800f78c0  call    __la_win_permissive_name_w
0x1800f78c5  mov     rcx, rax; lpFileName
0x1800f78c8  call    cs:__imp_GetFileAttributesW
0x1800f78ce  cmp     eax, 0FFFFFFFFh
0x1800f78d1  jnz     short loc_1800F78E7
0x1800f78d3  call    cs:__imp_GetLastError
0x1800f78d9  mov     ecx, eax
0x1800f78db  call    __la_dosmaperr
0x1800f78e0  mov     eax, 0FFFFFFECh
0x1800f78e5  jmp     short loc_1800F7907
0x1800f78e7  not     ebx
0x1800f78e9  mov     rcx, rdi; lpFileName
0x1800f78ec  and     ebx, eax
0x1800f78ee  or      ebx, esi
0x1800f78f0  and     ebx, 31A7h
0x1800f78f6  mov     edx, ebx; dwFileAttributes
0x1800f78f8  call    cs:__imp_SetFileAttributesW
0x1800f78fe  neg     eax
0x1800f7900  sbb     eax, eax
0x1800f7902  not     eax
0x1800f7904  and     eax, 0FFFFFFECh
0x1800f7907  mov     rbx, [rsp+28h+arg_0]
0x1800f790c  mov     rsi, [rsp+28h+arg_8]
0x1800f7911  add     rsp, 20h
0x1800f7915  pop     rdi
0x1800f7916  retn
```
