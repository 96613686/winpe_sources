# GetSusBaseDirectoryW(wchar_t *,ulong,wchar_t const *,ulong *)

- ea: `0x14000e194`
- end: `0x14000e45c`
- name: `?GetSusBaseDirectoryW@@YAJPEA_WKPEB_WPEAK@Z`
- size: `712`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, __int64, const wchar_t *, unsigned int *)`
- caller_count: `5`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000d0fc`
- `0x14000f5ac`
- `0x140016c54`
- `0x14002309c`
- `0x140034af8`

## callees

- `0x1400075a0`
- `0x140008de4`
- `0x140008e08`
- `0x14000db18`
- `0x14000e194`
- `0x14000e4d0`
- `0x140017da4`
- `0x140045dc0`
- `0x14004d140`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e3a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e3a9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x14000e2b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x14000e2b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000e430`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000e430`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000e217`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000e217`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14000e29c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14000e29c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14000e39f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14000e39f`

## string_xrefs

- `0x14000e1d3`: `C:\__w\1\s\src\Client\lib\util\sdpath.cpp`
- `0x14000e2c1`: `C:\__w\1\s\src\Client\lib\util\sdpath.cpp`
- `0x14000e3f8`: `C:\__w\1\s\src\Client\lib\util\sdpath.cpp`
- `0x14000e40f`: `C:\__w\1\s\src\Client\lib\util\sdpath.cpp`
- `0x14000e292`: `%PROGRAMDATA%`
- `0x14000e23c`: `RootDirectory`
- `0x14000e210`: `SOFTWARE\Microsoft\WindowsUpdate\EditionSettings`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall GetSusBaseDirectoryW(STRSAFE_LPWSTR pszDest, __int64 a2, const wchar_t *a3, unsigned int *a4)
{
  unsigned int v6; // ebx
  unsigned int v7; // r9d
  __int64 v8; // r14
  STRSAFE_LPWSTR v9; // rdx
  __int64 v10; // r8
  const char *v11; // r9
  __int64 v12; // rdx
  int LastError; // eax
  __int64 v14; // r8
  STRSAFE_LPWSTR v15; // rax
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // r9
  __int64 v18; // rdx
  int v19; // eax
  wchar_t *v20; // rcx
  unsigned __int64 v21; // rdx
  int phkResult; // [rsp+20h] [rbp-30h]
  unsigned int phkResulta; // [rsp+20h] [rbp-30h]
  unsigned int v25; // [rsp+28h] [rbp-28h]
  wchar_t *v26; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int64 v27; // [rsp+38h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]

  v26 = 0;
  v27 = 0;
  if ( !pszDest )
  {
    v6 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdpath.cpp",
      (const char *)0x80004003LL,
      phkResult);
    return v6;
  }
  *pszDest = 0;
  hKey = 0;
  v8 = -1;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WindowsUpdate\\EditionSettings", 0, 1u, &hKey) )
  {
    RegQueryStringValueWithDefaultAndExpand(hKey, L"RootDirectory", pszDest, v7, &OutputString, v25);
    if ( *pszDest == 92 && pszDest[1] == 92 && pszDest[2] == 63 && pszDest[3] == 92 )
    {
      v9 = pszDest + 4;
      v10 = -1;
      do
        ++v10;
      while ( v9[v10] );
      memmove(pszDest, v9, 2 * v10 + 2);
    }
  }
  if ( *pszDest
    || ExpandEnvironmentStringsW(L"%PROGRAMDATA%", pszDest, 0x104u) - 1 <= 0x103
    || GetSystemWindowsDirectoryW(pszDest, 0x104u) )
  {
    v14 = 260;
    v15 = pszDest;
    do
    {
      if ( !*v15 )
        break;
      ++v15;
      --v14;
    }
    while ( v14 );
    v16 = (260 - v14) & -(__int64)(v14 != 0);
    v6 = v14 == 0 ? 0x80070057 : 0;
    if ( v14 )
    {
      if ( a3 )
      {
        do
          ++v8;
        while ( a3[v8] );
        if ( *a3 != 92 )
          ++v8;
      }
      else
      {
        v8 = 0;
      }
      if ( v16 > 0x104 || v16 + v8 + 22 > 0x104 )
      {
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x87,
                      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdpath.cpp",
                      (const char *)0x7A,
                      phkResulta);
        goto LABEL_44;
      }
      if ( pszDest[v16 - 1] == 92 )
        pszDest[--v16] = 0;
      v19 = StringCchCopyExW(&pszDest[v16], 260 - v16, L"\\SoftwareDistribution", &v26, &v27, 0);
      v6 = v19;
      if ( v19 >= 0 )
      {
        if ( !CreateDirectoryW(pszDest, 0) && GetLastError() != 183 )
        {
          v12 = 150;
          goto LABEL_15;
        }
        if ( !a3 )
          goto LABEL_42;
        v20 = v26;
        v21 = v27;
        if ( *a3 != 92 )
        {
          *v26 = 92;
          ++v20;
          --v21;
        }
        v19 = StringCchCopyW(v20, v21, a3);
        v6 = v19;
        if ( v19 >= 0 )
        {
LABEL_42:
          v6 = 0;
          goto LABEL_45;
        }
        v18 = 162;
      }
      else
      {
        v18 = 145;
      }
      v17 = (unsigned int)v19;
    }
    else
    {
      v17 = v6;
      v18 = 99;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdpath.cpp",
      (const char *)v17,
      phkResulta);
    goto LABEL_45;
  }
  v12 = 95;
LABEL_15:
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v12,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdpath.cpp",
                v11);
LABEL_44:
  v6 = LastError;
LABEL_45:
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x14000e194  mov     [rsp-38h+arg_8], rbx
0x14000e199  push    rbp
0x14000e19a  push    rsi
0x14000e19b  push    rdi
0x14000e19c  push    r12
0x14000e19e  push    r13
0x14000e1a0  push    r14
0x14000e1a2  push    r15
0x14000e1a4  mov     rbp, rsp
0x14000e1a7  sub     rsp, 50h
0x14000e1ab  mov     rax, cs:__security_cookie
0x14000e1b2  xor     rax, rsp
0x14000e1b5  mov     [rbp+var_8], rax
0x14000e1b9  xor     r12d, r12d
0x14000e1bc  mov     r15, r8
0x14000e1bf  mov     [rbp+var_20], r12
0x14000e1c3  mov     rdi, rcx
0x14000e1c6  mov     [rbp+var_18], r12
0x14000e1ca  test    rcx, rcx
0x14000e1cd  jnz     short loc_14000E1EF
0x14000e1cf  mov     rcx, [rbp+38h]; this
0x14000e1d3  lea     r8, aCW1SSrcClientL_26; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000e1da  mov     ebx, 80004003h
0x14000e1df  lea     edx, [rdi+2Dh]; void *
0x14000e1e2  mov     r9d, ebx; char *
0x14000e1e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e1ea  jmp     loc_14000E436
0x14000e1ef  mov     [rcx], r12w
0x14000e1f3  lea     rax, [rbp+hKey]
0x14000e1f7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000e1fe  mov     [rsp+50h+phkResult], rax; phkResult
0x14000e203  mov     r9d, 1; samDesired
0x14000e209  mov     [rbp+hKey], r12
0x14000e20d  xor     r8d, r8d; ulOptions
0x14000e210  lea     rdx, ?c_szEditionSettingsKey@@3QB_WB; "SOFTWARE\\Microsoft\\WindowsUpdate\\Edi"...
0x14000e217  call    cs:__imp_RegOpenKeyExW
0x14000e21d  or      r14, 0FFFFFFFFFFFFFFFFh
0x14000e221  lea     r13d, [r14+5Dh]
0x14000e225  test    eax, eax
0x14000e227  jnz     short loc_14000E284
0x14000e229  mov     rcx, [rbp+hKey]; HKEY
0x14000e22d  lea     rax, OutputString
0x14000e234  mov     r8, rdi; pszDest
0x14000e237  mov     [rsp+50h+phkResult], rax; unsigned int
0x14000e23c  lea     rdx, ?c_szRootDirectoryRegValue@@3QB_WB; "RootDirectory"
0x14000e243  call    ?RegQueryStringValueWithDefaultAndExpand@@YAJPEAUHKEY__@@PEB_WPEA_WK1H@Z; RegQueryStringValueWithDefaultAndExpand(HKEY__ *,wchar_t const *,wchar_t *,ulong,wchar_t const *,int)
0x14000e248  cmp     [rdi], r13w
0x14000e24c  jnz     short loc_14000E284
0x14000e24e  cmp     [rdi+2], r13w
0x14000e253  jnz     short loc_14000E284
0x14000e255  cmp     word ptr [rdi+4], 3Fh ; '?'
0x14000e25a  jnz     short loc_14000E284
0x14000e25c  cmp     [rdi+6], r13w
0x14000e261  jnz     short loc_14000E284
0x14000e263  lea     rdx, [rdi+8]; Src
0x14000e267  mov     r8, r14
0x14000e26a  inc     r8
0x14000e26d  cmp     [rdx+r8*2], r12w
0x14000e272  jnz     short loc_14000E26A
0x14000e274  lea     r8, ds:2[r8*2]; Size
0x14000e27c  mov     rcx, rdi; void *
0x14000e27f  call    memmove
0x14000e284  mov     esi, 104h
0x14000e289  cmp     [rdi], r12w
0x14000e28d  jnz     short loc_14000E2D2
0x14000e28f  mov     r8d, esi; nSize
0x14000e292  lea     rcx, Src; "%PROGRAMDATA%"
0x14000e299  mov     rdx, rdi; lpDst
0x14000e29c  call    cs:__imp_ExpandEnvironmentStringsW
0x14000e2a2  dec     eax
0x14000e2a4  cmp     eax, 103h
0x14000e2a9  jbe     short loc_14000E2D2
0x14000e2ab  mov     edx, esi; uSize
0x14000e2ad  mov     rcx, rdi; lpBuffer
0x14000e2b0  call    cs:__imp_GetSystemWindowsDirectoryW
0x14000e2b6  test    eax, eax
0x14000e2b8  jnz     short loc_14000E2D2
0x14000e2ba  lea     edx, [rax+5Fh]; void *
0x14000e2bd  mov     rcx, [rbp+38h]; this
0x14000e2c1  lea     r8, aCW1SSrcClientL_26; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000e2c8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000e2cd  jmp     loc_14000E425
0x14000e2d2  mov     r8, rsi
0x14000e2d5  mov     rax, rdi
0x14000e2d8  cmp     [rax], r12w
0x14000e2dc  jz      short loc_14000E2E8
0x14000e2de  add     rax, 2
0x14000e2e2  sub     r8, 1
0x14000e2e6  jnz     short loc_14000E2D8
0x14000e2e8  mov     rcx, rsi
0x14000e2eb  mov     rax, r8
0x14000e2ee  sub     rcx, r8
0x14000e2f1  neg     rax
0x14000e2f4  mov     rax, r8
0x14000e2f7  sbb     rdx, rdx
0x14000e2fa  and     rdx, rcx
0x14000e2fd  neg     rax
0x14000e300  sbb     ebx, ebx
0x14000e302  not     ebx
0x14000e304  and     ebx, 80070057h
0x14000e30a  test    r8, r8
0x14000e30d  jnz     short loc_14000E31B
0x14000e30f  mov     r9d, ebx
0x14000e312  lea     edx, [r8+63h]
0x14000e316  jmp     loc_14000E3F4
0x14000e31b  test    r15, r15
0x14000e31e  jnz     short loc_14000E325
0x14000e320  mov     r14, r12
0x14000e323  jmp     short loc_14000E338
0x14000e325  inc     r14
0x14000e328  cmp     [r15+r14*2], r12w
0x14000e32d  jnz     short loc_14000E325
0x14000e32f  cmp     [r15], r13w
0x14000e333  jz      short loc_14000E338
0x14000e335  inc     r14
0x14000e338  cmp     rdx, rsi
0x14000e33b  ja      loc_14000E40B
0x14000e341  lea     rax, [r14+16h]
0x14000e345  add     rax, rdx
0x14000e348  cmp     rax, rsi
0x14000e34b  ja      loc_14000E40B
0x14000e351  cmp     [rdi+rdx*2-2], r13w
0x14000e357  jnz     short loc_14000E365
0x14000e359  lea     rax, [rdx-1]
0x14000e35d  mov     rdx, rax
0x14000e360  mov     [rdi+rax*2], r12w
0x14000e365  sub     rsi, rdx
0x14000e368  mov     [rsp+50h+var_28], r12d; unsigned int
0x14000e36d  lea     rcx, [rdi+rdx*2]; pszDest
0x14000e371  mov     rdx, rsi; unsigned __int64
0x14000e374  lea     rax, [rbp+var_18]
0x14000e378  lea     r9, [rbp+var_20]; wchar_t **
0x14000e37c  mov     [rsp+50h+phkResult], rax; int
0x14000e381  lea     r8, aSoftwaredistri; "\\SoftwareDistribution"
0x14000e388  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x14000e38d  mov     ebx, eax
0x14000e38f  test    eax, eax
0x14000e391  jns     short loc_14000E39A
0x14000e393  mov     edx, 91h
0x14000e398  jmp     short loc_14000E3F1
0x14000e39a  xor     edx, edx; lpSecurityAttributes
0x14000e39c  mov     rcx, rdi; lpPathName
0x14000e39f  call    cs:__imp_CreateDirectoryW
0x14000e3a5  test    eax, eax
0x14000e3a7  jnz     short loc_14000E3C0
0x14000e3a9  call    cs:__imp_GetLastError
0x14000e3af  cmp     eax, 0B7h
0x14000e3b4  jz      short loc_14000E3C0
0x14000e3b6  mov     edx, 96h
0x14000e3bb  jmp     loc_14000E2BD
0x14000e3c0  test    r15, r15
0x14000e3c3  jz      short loc_14000E406
0x14000e3c5  mov     rcx, [rbp+var_20]
0x14000e3c9  mov     rdx, [rbp+var_18]
0x14000e3cd  cmp     [r15], r13w
0x14000e3d1  jz      short loc_14000E3DE
0x14000e3d3  mov     [rcx], r13w
0x14000e3d7  add     rcx, 2; wchar_t *
0x14000e3db  dec     rdx; unsigned __int64
0x14000e3de  mov     r8, r15; wchar_t *
0x14000e3e1  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x14000e3e6  mov     ebx, eax
0x14000e3e8  test    eax, eax
0x14000e3ea  jns     short loc_14000E406
0x14000e3ec  mov     edx, 0A2h; void *
0x14000e3f1  mov     r9d, eax; char *
0x14000e3f4  mov     rcx, [rbp+38h]; this
0x14000e3f8  lea     r8, aCW1SSrcClientL_26; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000e3ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e404  jmp     short loc_14000E427
0x14000e406  mov     ebx, r12d
0x14000e409  jmp     short loc_14000E427
0x14000e40b  mov     rcx, [rbp+38h]; this
0x14000e40f  lea     r8, aCW1SSrcClientL_26; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000e416  mov     r9d, 7Ah ; 'z'; char *
0x14000e41c  lea     edx, [r9+0Dh]; void *
0x14000e420  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000e425  mov     ebx, eax
0x14000e427  mov     rcx, [rbp+hKey]; hKey
0x14000e42b  test    rcx, rcx
0x14000e42e  jz      short loc_14000E436
0x14000e430  call    cs:__imp_RegCloseKey
0x14000e436  mov     eax, ebx
0x14000e438  mov     rcx, [rbp+var_8]
0x14000e43c  xor     rcx, rsp; StackCookie
0x14000e43f  call    __security_check_cookie
0x14000e444  mov     rbx, [rsp+50h+arg_8]
0x14000e44c  add     rsp, 50h
0x14000e450  pop     r15
0x14000e452  pop     r14
0x14000e454  pop     r13
0x14000e456  pop     r12
0x14000e458  pop     rdi
0x14000e459  pop     rsi
0x14000e45a  pop     rbp
0x14000e45b  retn
```
