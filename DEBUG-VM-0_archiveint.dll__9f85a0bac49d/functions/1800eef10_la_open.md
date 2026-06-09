# __la_open

- ea: `0x1800eef10`
- end: `0x1800ef15b`
- name: `__la_open`
- size: `587`
- prototype: `__int64 __fastcall(LPCSTR lpFileName)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800c10b0`
- `0x1800d78d0`

## callees

- `0x1800149c0`
- `0x1800eef10`
- `0x1800ef374`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800eef7b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ef05c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ef082`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ef093`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ef0af`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ef0f5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ef12a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ef138`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800eef7b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ef05c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ef082`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ef093`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ef0af`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ef0f5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ef12a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ef138`
- `api-ms-win-crt-private-l1-1-0!_o__open_osfhandle` at `0x1800ef01c`
- `api-ms-win-crt-private-l1-1-0!_o__open_osfhandle` at `0x1800ef01c`
- `api-ms-win-crt-private-l1-1-0!_o__sopen_s` at `0x1800ef04b`
- `api-ms-win-crt-private-l1-1-0!_o__sopen_s` at `0x1800ef04b`
- `api-ms-win-crt-private-l1-1-0!_o__wsopen_s` at `0x1800ef0e9`
- `api-ms-win-crt-private-l1-1-0!_o__wsopen_s` at `0x1800ef0e9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800eefad`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800eeff9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ef147`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800eefad`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800eeff9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ef147`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800eefed`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800eefed`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x1800eef55`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x1800ef073`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x1800eef55`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x1800ef073`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800eefe2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800eefe2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800eef92`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800ef10c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800eef92`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800ef10c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eef60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eef9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef117`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eef60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eef9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef117`

## pseudocode

```c
__int64 __fastcall _la_open(LPCSTR lpFileName, unsigned int a2, __int16 a3)
{
  WCHAR *v3; // rbx
  DWORD FileAttributesA; // eax
  const WCHAR *v7; // rax
  __int64 result; // rax
  DWORD LastError; // eax
  HANDLE FileW; // rax
  HANDLE v11; // rdi
  DWORD v12; // eax
  int v13; // esi
  DWORD v14; // eax
  DWORD FileAttributesW; // eax
  DWORD v16; // eax
  unsigned int v17[4]; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v18; // [rsp+88h] [rbp+38h]

  v18 = a2;
  *(_QWORD *)v17 = 0;
  v3 = 0;
  if ( (a2 & 0xFFFF7FFF) == 0 )
  {
    FileAttributesA = GetFileAttributesA(lpFileName);
    if ( FileAttributesA == -1 )
    {
      if ( GetLastError() != 3 )
        goto LABEL_8;
      v7 = (const WCHAR *)_la_win_permissive_name(lpFileName);
      v3 = (WCHAR *)v7;
      if ( !v7 )
      {
LABEL_5:
        *(_DWORD *)_o__errno() = 22;
        return 0xFFFFFFFFLL;
      }
      FileAttributesA = GetFileAttributesW(v7);
      if ( FileAttributesA == -1 )
      {
LABEL_8:
        LastError = GetLastError();
        _la_dosmaperr(LastError);
        free(v3);
        return 0xFFFFFFFFLL;
      }
    }
    if ( (FileAttributesA & 0x10) != 0 )
    {
      if ( v3 )
        FileW = CreateFileW(v3, 0, 0, 0, 3u, 0x2000001u, 0);
      else
        FileW = CreateFileA(lpFileName, 0, 0, 0, 3u, 0x2000001u, 0);
      v11 = FileW;
      free(v3);
      if ( v11 == (HANDLE)-1LL )
      {
LABEL_14:
        v12 = GetLastError();
        _la_dosmaperr(v12);
        return 0xFFFFFFFFLL;
      }
      return _o__open_osfhandle(v11, 0);
    }
    a2 = v18;
  }
  v13 = a3 & 0x180;
  if ( v3 )
    goto LABEL_29;
  _o__sopen_s(v17, lpFileName, a2, 64, v13);
  result = v17[0];
  if ( (v17[0] & 0x80000000) != 0 )
  {
    if ( *(_DWORD *)_o__errno() == 13 && (v18 & 0x100) != 0 )
    {
      v14 = GetFileAttributesA(lpFileName);
      if ( v14 != -1 )
      {
        if ( (v14 & 0x10) != 0 )
          *(_DWORD *)_o__errno() = 21;
        else
          *(_DWORD *)_o__errno() = 13;
        return 0xFFFFFFFFLL;
      }
      goto LABEL_14;
    }
    result = v17[0];
    if ( (v17[0] & 0x80000000) != 0 )
    {
      if ( *(_DWORD *)_o__errno() != 2 )
        return v17[0];
      v3 = (WCHAR *)_la_win_permissive_name(lpFileName);
      if ( !v3 )
        goto LABEL_5;
      a2 = v18;
LABEL_29:
      _o__wsopen_s(v17, v3, a2, 64, v13);
      if ( (v17[0] & 0x80000000) != 0 && *(_DWORD *)_o__errno() == 13 && (v18 & 0x100) != 0 )
      {
        FileAttributesW = GetFileAttributesW(v3);
        if ( FileAttributesW == -1 )
        {
          v16 = GetLastError();
          _la_dosmaperr(v16);
        }
        else if ( (FileAttributesW & 0x10) != 0 )
        {
          *(_DWORD *)_o__errno() = 21;
        }
        else
        {
          *(_DWORD *)_o__errno() = 13;
        }
      }
      free(v3);
      return v17[0];
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800eef10  mov     [rsp-28h+arg_8], edx
0x1800eef14  mov     [rsp-28h+arg_10], r8
0x1800eef19  mov     [rsp-28h+arg_18], r9
0x1800eef1e  push    rbp
0x1800eef1f  push    rbx
0x1800eef20  push    rsi
0x1800eef21  push    rdi
0x1800eef22  push    r12
0x1800eef24  mov     rbp, rsp
0x1800eef27  sub     rsp, 50h
0x1800eef2b  mov     qword ptr [rbp+var_10], 0
0x1800eef33  lea     rsi, [rbp+arg_10]
0x1800eef37  xor     ebx, ebx
0x1800eef39  mov     [rbp+var_10], 0
0x1800eef40  mov     esi, [rsi]
0x1800eef42  or      r12d, 0FFFFFFFFh
0x1800eef46  mov     rdi, rcx
0x1800eef49  test    edx, 0FFFF7FFFh
0x1800eef4f  jnz     loc_1800EF02A
0x1800eef55  call    cs:__imp_GetFileAttributesA
0x1800eef5b  cmp     eax, r12d
0x1800eef5e  jnz     short loc_1800EEFB5
0x1800eef60  call    cs:__imp_GetLastError
0x1800eef66  cmp     eax, 3
0x1800eef69  jnz     short loc_1800EEF9D
0x1800eef6b  mov     rcx, rdi
0x1800eef6e  call    __la_win_permissive_name
0x1800eef73  mov     rbx, rax
0x1800eef76  test    rax, rax
0x1800eef79  jnz     short loc_1800EEF8F
0x1800eef7b  call    cs:__imp__o__errno
0x1800eef81  mov     dword ptr [rax], 16h
0x1800eef87  or      eax, 0FFFFFFFFh
0x1800eef8a  jmp     loc_1800EF150
0x1800eef8f  mov     rcx, rax; lpFileName
0x1800eef92  call    cs:__imp_GetFileAttributesW
0x1800eef98  cmp     eax, r12d
0x1800eef9b  jnz     short loc_1800EEFB5
0x1800eef9d  call    cs:__imp_GetLastError
0x1800eefa3  mov     ecx, eax
0x1800eefa5  call    __la_dosmaperr
0x1800eefaa  mov     rcx, rbx; Block
0x1800eefad  call    cs:__imp_free
0x1800eefb3  jmp     short loc_1800EEF87
0x1800eefb5  test    al, 10h
0x1800eefb7  jz      short loc_1800EF027
0x1800eefb9  mov     [rsp+50h+hTemplateFile], 0; hTemplateFile
0x1800eefc2  xor     r9d, r9d; lpSecurityAttributes
0x1800eefc5  xor     r8d, r8d; dwShareMode
0x1800eefc8  mov     [rsp+50h+dwFlagsAndAttributes], 2000001h; dwFlagsAndAttributes
0x1800eefd0  xor     edx, edx; dwDesiredAccess
0x1800eefd2  mov     [rsp+50h+dwCreationDisposition], 3; dwCreationDisposition
0x1800eefda  test    rbx, rbx
0x1800eefdd  jz      short loc_1800EEFEA
0x1800eefdf  mov     rcx, rbx; lpFileName
0x1800eefe2  call    cs:__imp_CreateFileW
0x1800eefe8  jmp     short loc_1800EEFF3
0x1800eefea  mov     rcx, rdi; lpFileName
0x1800eefed  call    cs:__imp_CreateFileA
0x1800eeff3  mov     rcx, rbx; Block
0x1800eeff6  mov     rdi, rax
0x1800eeff9  call    cs:__imp_free
0x1800eefff  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800ef003  jnz     short loc_1800EF017
0x1800ef005  call    cs:__imp_GetLastError
0x1800ef00b  mov     ecx, eax
0x1800ef00d  call    __la_dosmaperr
0x1800ef012  jmp     loc_1800EEF87
0x1800ef017  xor     edx, edx
0x1800ef019  mov     rcx, rdi
0x1800ef01c  call    cs:__imp__o__open_osfhandle
0x1800ef022  jmp     loc_1800EF150
0x1800ef027  mov     edx, [rbp+arg_8]
0x1800ef02a  and     esi, 180h
0x1800ef030  test    rbx, rbx
0x1800ef033  jnz     loc_1800EF0D5
0x1800ef039  mov     r8d, edx
0x1800ef03c  mov     [rsp+50h+dwCreationDisposition], esi
0x1800ef040  mov     rdx, rdi
0x1800ef043  lea     r9d, [rbx+40h]
0x1800ef047  lea     rcx, [rbp+var_10]
0x1800ef04b  call    cs:__imp__o__sopen_s
0x1800ef051  mov     eax, [rbp+var_10]
0x1800ef054  test    eax, eax
0x1800ef056  jns     loc_1800EF150
0x1800ef05c  call    cs:__imp__o__errno
0x1800ef062  cmp     dword ptr [rax], 0Dh
0x1800ef065  jnz     short loc_1800EF0A4
0x1800ef067  test    [rbp+arg_8], 100h
0x1800ef06e  jz      short loc_1800EF0A4
0x1800ef070  mov     rcx, rdi; lpFileName
0x1800ef073  call    cs:__imp_GetFileAttributesA
0x1800ef079  cmp     eax, r12d
0x1800ef07c  jz      short loc_1800EF005
0x1800ef07e  test    al, 10h
0x1800ef080  jz      short loc_1800EF093
0x1800ef082  call    cs:__imp__o__errno
0x1800ef088  mov     dword ptr [rax], 15h
0x1800ef08e  jmp     loc_1800EEF87
0x1800ef093  call    cs:__imp__o__errno
0x1800ef099  mov     dword ptr [rax], 0Dh
0x1800ef09f  jmp     loc_1800EEF87
0x1800ef0a4  mov     eax, [rbp+var_10]
0x1800ef0a7  test    eax, eax
0x1800ef0a9  jns     loc_1800EF150
0x1800ef0af  call    cs:__imp__o__errno
0x1800ef0b5  cmp     dword ptr [rax], 2
0x1800ef0b8  jnz     loc_1800EF14D
0x1800ef0be  mov     rcx, rdi
0x1800ef0c1  call    __la_win_permissive_name
0x1800ef0c6  mov     rbx, rax
0x1800ef0c9  test    rax, rax
0x1800ef0cc  jz      loc_1800EEF7B
0x1800ef0d2  mov     edx, [rbp+arg_8]
0x1800ef0d5  mov     r8d, edx
0x1800ef0d8  mov     [rsp+50h+dwCreationDisposition], esi
0x1800ef0dc  mov     rdx, rbx
0x1800ef0df  lea     rcx, [rbp+var_10]
0x1800ef0e3  mov     r9d, 40h ; '@'
0x1800ef0e9  call    cs:__imp__o__wsopen_s
0x1800ef0ef  cmp     [rbp+var_10], 0
0x1800ef0f3  jge     short loc_1800EF144
0x1800ef0f5  call    cs:__imp__o__errno
0x1800ef0fb  cmp     dword ptr [rax], 0Dh
0x1800ef0fe  jnz     short loc_1800EF144
0x1800ef100  test    [rbp+arg_8], 100h
0x1800ef107  jz      short loc_1800EF144
0x1800ef109  mov     rcx, rbx; lpFileName
0x1800ef10c  call    cs:__imp_GetFileAttributesW
0x1800ef112  cmp     eax, r12d
0x1800ef115  jnz     short loc_1800EF126
0x1800ef117  call    cs:__imp_GetLastError
0x1800ef11d  mov     ecx, eax
0x1800ef11f  call    __la_dosmaperr
0x1800ef124  jmp     short loc_1800EF144
0x1800ef126  test    al, 10h
0x1800ef128  jz      short loc_1800EF138
0x1800ef12a  call    cs:__imp__o__errno
0x1800ef130  mov     dword ptr [rax], 15h
0x1800ef136  jmp     short loc_1800EF144
0x1800ef138  call    cs:__imp__o__errno
0x1800ef13e  mov     dword ptr [rax], 0Dh
0x1800ef144  mov     rcx, rbx; Block
0x1800ef147  call    cs:__imp_free
0x1800ef14d  mov     eax, [rbp+var_10]
0x1800ef150  add     rsp, 50h
0x1800ef154  pop     r12
0x1800ef156  pop     rdi
0x1800ef157  pop     rsi
0x1800ef158  pop     rbx
0x1800ef159  pop     rbp
0x1800ef15a  retn
```
