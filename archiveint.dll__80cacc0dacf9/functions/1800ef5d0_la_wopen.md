# __la_wopen

- ea: `0x1800ef5d0`
- end: `0x1800ef76d`
- name: `__la_wopen`
- size: `413`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800c10b0`
- `0x1800f8380`

## callees

- `0x1800149c0`
- `0x1800ef3f8`
- `0x1800ef5d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ef635`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ef708`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ef73e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ef74c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ef635`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ef708`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ef73e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ef74c`
- `api-ms-win-crt-private-l1-1-0!_o__open_osfhandle` at `0x1800ef6d1`
- `api-ms-win-crt-private-l1-1-0!_o__open_osfhandle` at `0x1800ef6d1`
- `api-ms-win-crt-private-l1-1-0!_o__wsopen_s` at `0x1800ef6fb`
- `api-ms-win-crt-private-l1-1-0!_o__wsopen_s` at `0x1800ef6fb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ef696`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ef6c1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ef75b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ef696`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ef6c1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ef75b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ef68a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ef68a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800ef60b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800ef64c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800ef720`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800ef60b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800ef64c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800ef720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef616`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef6a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef6b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef72b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef616`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef6a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef6b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef72b`

## pseudocode

```c
__int64 __fastcall _la_wopen(LPCWSTR lpFileName, unsigned int a2, __int16 a3)
{
  WCHAR *v3; // rbx
  const WCHAR *v5; // rdi
  DWORD FileAttributesW; // eax
  const WCHAR *v7; // rax
  const WCHAR *v9; // rcx
  HANDLE FileW; // rdi
  DWORD v11; // eax
  DWORD LastError; // eax
  DWORD v13; // eax
  DWORD v14; // eax
  _QWORD v15[5]; // [rsp+40h] [rbp-28h] BYREF
  unsigned int v16; // [rsp+78h] [rbp+10h]

  v16 = a2;
  v15[0] = 0;
  v3 = 0;
  v5 = lpFileName;
  if ( (a2 & 0xFFFF7FFF) != 0 )
    goto LABEL_17;
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW == -1 )
  {
    if ( GetLastError() != 3 )
      goto LABEL_14;
    v7 = (const WCHAR *)_la_win_permissive_name_w(v5);
    v3 = (WCHAR *)v7;
    if ( !v7 )
    {
      *(_DWORD *)_o__errno() = 22;
      return 0xFFFFFFFFLL;
    }
    FileAttributesW = GetFileAttributesW(v7);
    if ( FileAttributesW == -1 )
    {
LABEL_14:
      LastError = GetLastError();
      _la_dosmaperr(LastError);
      free(v3);
      return 0xFFFFFFFFLL;
    }
    v5 = v3;
  }
  if ( (FileAttributesW & 0x10) == 0 )
  {
    a2 = v16;
LABEL_17:
    _o__wsopen_s(v15, v5, a2, 64, a3 & 0x180);
    if ( SLODWORD(v15[0]) < 0 && *(_DWORD *)_o__errno() == 13 && (v16 & 0x100) != 0 )
    {
      v13 = GetFileAttributesW(v5);
      if ( v13 == -1 )
      {
        v14 = GetLastError();
        _la_dosmaperr(v14);
      }
      else if ( (v13 & 0x10) != 0 )
      {
        *(_DWORD *)_o__errno() = 21;
      }
      else
      {
        *(_DWORD *)_o__errno() = 13;
      }
    }
    free(v3);
    return LODWORD(v15[0]);
  }
  v9 = v3;
  if ( !v3 )
    v9 = v5;
  FileW = CreateFileW(v9, 0, 0, 0, 3u, 0x2000001u, 0);
  free(v3);
  if ( FileW == (HANDLE)-1LL )
  {
    v11 = GetLastError();
    _la_dosmaperr(v11);
    return 0xFFFFFFFFLL;
  }
  return _o__open_osfhandle(FileW, 0);
}

```

## disassembly

```asm
0x1800ef5d0  mov     rax, rsp
0x1800ef5d3  mov     [rax+10h], edx
0x1800ef5d6  mov     [rax+18h], r8
0x1800ef5da  mov     [rax+20h], r9
0x1800ef5de  push    rbx
0x1800ef5df  push    rsi
0x1800ef5e0  push    rdi
0x1800ef5e1  sub     rsp, 50h
0x1800ef5e5  mov     qword ptr [rax-28h], 0
0x1800ef5ed  lea     rsi, [rax+18h]
0x1800ef5f1  xor     ebx, ebx
0x1800ef5f3  mov     dword ptr [rax-28h], 0
0x1800ef5fa  mov     esi, [rsi]
0x1800ef5fc  mov     rdi, rcx
0x1800ef5ff  test    edx, 0FFFF7FFFh
0x1800ef605  jnz     loc_1800EF6E0
0x1800ef60b  call    cs:__imp_GetFileAttributesW
0x1800ef611  cmp     eax, 0FFFFFFFFh
0x1800ef614  jnz     short loc_1800EF65A
0x1800ef616  call    cs:__imp_GetLastError
0x1800ef61c  cmp     eax, 3
0x1800ef61f  jnz     loc_1800EF6B1
0x1800ef625  mov     rcx, rdi; lpFileName
0x1800ef628  call    __la_win_permissive_name_w
0x1800ef62d  mov     rbx, rax
0x1800ef630  test    rax, rax
0x1800ef633  jnz     short loc_1800EF649
0x1800ef635  call    cs:__imp__o__errno
0x1800ef63b  mov     dword ptr [rax], 16h
0x1800ef641  or      eax, 0FFFFFFFFh
0x1800ef644  jmp     loc_1800EF765
0x1800ef649  mov     rcx, rbx; lpFileName
0x1800ef64c  call    cs:__imp_GetFileAttributesW
0x1800ef652  cmp     eax, 0FFFFFFFFh
0x1800ef655  jz      short loc_1800EF6B1
0x1800ef657  mov     rdi, rbx
0x1800ef65a  test    al, 10h
0x1800ef65c  jz      short loc_1800EF6DC
0x1800ef65e  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1800ef667  xor     r9d, r9d; lpSecurityAttributes
0x1800ef66a  xor     r8d, r8d; dwShareMode
0x1800ef66d  mov     [rsp+68h+dwFlagsAndAttributes], 2000001h; dwFlagsAndAttributes
0x1800ef675  xor     edx, edx; dwDesiredAccess
0x1800ef677  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x1800ef67f  mov     rcx, rbx
0x1800ef682  test    rbx, rbx
0x1800ef685  jnz     short loc_1800EF68A
0x1800ef687  mov     rcx, rdi; lpFileName
0x1800ef68a  call    cs:__imp_CreateFileW
0x1800ef690  mov     rcx, rbx; Block
0x1800ef693  mov     rdi, rax
0x1800ef696  call    cs:__imp_free
0x1800ef69c  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800ef6a0  jnz     short loc_1800EF6CC
0x1800ef6a2  call    cs:__imp_GetLastError
0x1800ef6a8  mov     ecx, eax
0x1800ef6aa  call    __la_dosmaperr
0x1800ef6af  jmp     short loc_1800EF641
0x1800ef6b1  call    cs:__imp_GetLastError
0x1800ef6b7  mov     ecx, eax
0x1800ef6b9  call    __la_dosmaperr
0x1800ef6be  mov     rcx, rbx; Block
0x1800ef6c1  call    cs:__imp_free
0x1800ef6c7  jmp     loc_1800EF641
0x1800ef6cc  xor     edx, edx
0x1800ef6ce  mov     rcx, rdi
0x1800ef6d1  call    cs:__imp__o__open_osfhandle
0x1800ef6d7  jmp     loc_1800EF765
0x1800ef6dc  mov     edx, [rsp+68h+arg_8]
0x1800ef6e0  mov     r8d, edx
0x1800ef6e3  lea     rcx, [rsp+68h+var_28]
0x1800ef6e8  and     esi, 180h
0x1800ef6ee  mov     rdx, rdi
0x1800ef6f1  mov     r9d, 40h ; '@'
0x1800ef6f7  mov     [rsp+68h+dwCreationDisposition], esi
0x1800ef6fb  call    cs:__imp__o__wsopen_s
0x1800ef701  cmp     dword ptr [rsp+68h+var_28], 0
0x1800ef706  jge     short loc_1800EF758
0x1800ef708  call    cs:__imp__o__errno
0x1800ef70e  cmp     dword ptr [rax], 0Dh
0x1800ef711  jnz     short loc_1800EF758
0x1800ef713  test    [rsp+68h+arg_8], 100h
0x1800ef71b  jz      short loc_1800EF758
0x1800ef71d  mov     rcx, rdi; lpFileName
0x1800ef720  call    cs:__imp_GetFileAttributesW
0x1800ef726  cmp     eax, 0FFFFFFFFh
0x1800ef729  jnz     short loc_1800EF73A
0x1800ef72b  call    cs:__imp_GetLastError
0x1800ef731  mov     ecx, eax
0x1800ef733  call    __la_dosmaperr
0x1800ef738  jmp     short loc_1800EF758
0x1800ef73a  test    al, 10h
0x1800ef73c  jz      short loc_1800EF74C
0x1800ef73e  call    cs:__imp__o__errno
0x1800ef744  mov     dword ptr [rax], 15h
0x1800ef74a  jmp     short loc_1800EF758
0x1800ef74c  call    cs:__imp__o__errno
0x1800ef752  mov     dword ptr [rax], 0Dh
0x1800ef758  mov     rcx, rbx; Block
0x1800ef75b  call    cs:__imp_free
0x1800ef761  mov     eax, dword ptr [rsp+68h+var_28]
0x1800ef765  add     rsp, 50h
0x1800ef769  pop     rdi
0x1800ef76a  pop     rsi
0x1800ef76b  pop     rbx
0x1800ef76c  retn
```
