# GetSusBaseDirectoryW(wchar_t *,ulong,wchar_t const *,ulong *)

- ea: `0x18004bd90`
- end: `0x18004c045`
- name: `?GetSusBaseDirectoryW@@YAJPEA_WKPEB_WPEAK@Z`
- size: `693`
- prototype: `__int64 __fastcall(wchar_t *, unsigned int, const wchar_t *, unsigned int *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180040814`
- `0x180049984`
- `0x18004a89c`

## callees

- `0x180002214`
- `0x180003180`
- `0x180003b7c`
- `0x180009438`
- `0x18000970c`
- `0x18001217c`
- `0x18004bd90`
- `0x180061960`
- `0x1800692e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bf92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bf92`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18004be99`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18004be99`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004be13`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004be13`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c019`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c019`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18004be85`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18004be85`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004bf88`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004bf88`

## string_xrefs

- `0x18004be0c`: `SOFTWARE\Microsoft\WindowsUpdate\EditionSettings`
- `0x18004bdcf`: `C:\__w\1\s\src\Client\lib\util\sdpath.cpp`
- `0x18004beaa`: `C:\__w\1\s\src\Client\lib\util\sdpath.cpp`
- `0x18004bfe1`: `C:\__w\1\s\src\Client\lib\util\sdpath.cpp`
- `0x18004bff8`: `C:\__w\1\s\src\Client\lib\util\sdpath.cpp`
- `0x18004be7b`: `%PROGRAMDATA%`

## pseudocode

```c
__int64 __fastcall GetSusBaseDirectoryW(wchar_t *a1, __int64 a2, const wchar_t *a3, unsigned int *a4)
{
  unsigned int v6; // ebx
  const wchar_t *v7; // rdx
  unsigned int v8; // r9d
  __int64 v9; // r14
  wchar_t *v10; // rdx
  __int64 v11; // r8
  const char *v12; // r9
  __int64 v13; // rdx
  int LastError; // eax
  __int64 v15; // r8
  wchar_t *v16; // rax
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // r9
  __int64 v19; // rdx
  int v20; // eax
  wchar_t *v21; // rcx
  unsigned __int64 v22; // rdx
  int phkResult; // [rsp+20h] [rbp-30h]
  const wchar_t *phkResulta; // [rsp+20h] [rbp-30h]
  unsigned int v26; // [rsp+28h] [rbp-28h]
  wchar_t *v27; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int64 v28; // [rsp+38h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]

  v27 = 0;
  v28 = 0;
  if ( !a1 )
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
  *a1 = 0;
  hKey = 0;
  v9 = -1;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WindowsUpdate\\EditionSettings", 0, 1u, &hKey) )
  {
    RegQueryStringValueWithDefaultAndExpand(hKey, v7, a1, v8, phkResulta, v26);
    if ( *a1 == 92 && a1[1] == 92 && a1[2] == 63 && a1[3] == 92 )
    {
      v10 = a1 + 4;
      v11 = -1;
      do
        ++v11;
      while ( v10[v11] );
      memmove(a1, v10, 2 * v11 + 2);
    }
  }
  if ( *a1
    || ExpandEnvironmentStringsW(L"%PROGRAMDATA%", a1, 0x104u) - 1 <= 0x103
    || GetSystemWindowsDirectoryW(a1, 0x104u) )
  {
    v15 = 260;
    v16 = a1;
    do
    {
      if ( !*v16 )
        break;
      ++v16;
      --v15;
    }
    while ( v15 );
    v17 = (260 - v15) & -(__int64)(v15 != 0);
    v6 = v15 == 0 ? 0x80070057 : 0;
    if ( v15 )
    {
      if ( a3 )
      {
        do
          ++v9;
        while ( a3[v9] );
        if ( *a3 != 92 )
          ++v9;
      }
      else
      {
        v9 = 0;
      }
      if ( v17 > 0x104 || v17 + v9 + 22 > 0x104 )
      {
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x87,
                      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdpath.cpp",
                      (const char *)0x7A,
                      (unsigned int)phkResulta);
        goto LABEL_44;
      }
      if ( a1[v17 - 1] == 92 )
        a1[--v17] = 0;
      v20 = StringCchCopyExW(&a1[v17], 260 - v17, L"\\SoftwareDistribution", &v27, &v28, 0);
      v6 = v20;
      if ( v20 >= 0 )
      {
        if ( !CreateDirectoryW(a1, 0) && GetLastError() != 183 )
        {
          v13 = 150;
          goto LABEL_15;
        }
        if ( !a3 )
          goto LABEL_42;
        v21 = v27;
        v22 = v28;
        if ( *a3 != 92 )
        {
          *v27 = 92;
          ++v21;
          --v22;
        }
        v20 = StringCchCopyW(v21, v22, a3);
        v6 = v20;
        if ( v20 >= 0 )
        {
LABEL_42:
          v6 = 0;
          goto LABEL_45;
        }
        v19 = 162;
      }
      else
      {
        v19 = 145;
      }
      v18 = (unsigned int)v20;
    }
    else
    {
      v18 = v6;
      v19 = 99;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdpath.cpp",
      (const char *)v18,
      (int)phkResulta);
    goto LABEL_45;
  }
  v13 = 95;
LABEL_15:
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v13,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdpath.cpp",
                v12);
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
0x18004bd90  mov     [rsp-38h+arg_8], rbx
0x18004bd95  push    rbp
0x18004bd96  push    rsi
0x18004bd97  push    rdi
0x18004bd98  push    r12
0x18004bd9a  push    r13
0x18004bd9c  push    r14
0x18004bd9e  push    r15
0x18004bda0  mov     rbp, rsp
0x18004bda3  sub     rsp, 50h
0x18004bda7  mov     rax, cs:__security_cookie
0x18004bdae  xor     rax, rsp
0x18004bdb1  mov     [rbp+var_8], rax
0x18004bdb5  xor     r12d, r12d
0x18004bdb8  mov     r15, r8
0x18004bdbb  mov     [rbp+var_20], r12
0x18004bdbf  mov     rdi, rcx
0x18004bdc2  mov     [rbp+var_18], r12
0x18004bdc6  test    rcx, rcx
0x18004bdc9  jnz     short loc_18004BDEB
0x18004bdcb  mov     rcx, [rbp+38h]; this
0x18004bdcf  lea     r8, aCW1SSrcClientL_19; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18004bdd6  mov     ebx, 80004003h
0x18004bddb  lea     edx, [rdi+2Dh]; void *
0x18004bdde  mov     r9d, ebx; char *
0x18004bde1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bde6  jmp     loc_18004C01F
0x18004bdeb  mov     [rcx], r12w
0x18004bdef  lea     rax, [rbp+hKey]
0x18004bdf3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004bdfa  mov     [rsp+50h+phkResult], rax; unsigned int
0x18004bdff  mov     r9d, 1; samDesired
0x18004be05  mov     [rbp+hKey], r12
0x18004be09  xor     r8d, r8d; ulOptions
0x18004be0c  lea     rdx, ?c_szEditionSettingsKey@@3QB_WB; "SOFTWARE\\Microsoft\\WindowsUpdate\\Edi"...
0x18004be13  call    cs:__imp_RegOpenKeyExW
0x18004be19  or      r14, 0FFFFFFFFFFFFFFFFh
0x18004be1d  lea     r13d, [r14+5Dh]
0x18004be21  test    eax, eax
0x18004be23  jnz     short loc_18004BE6D
0x18004be25  mov     rcx, [rbp+hKey]; HKEY
0x18004be29  mov     r8, rdi; wchar_t *
0x18004be2c  call    ?RegQueryStringValueWithDefaultAndExpand@@YAJPEAUHKEY__@@PEB_WPEA_WK1H@Z; RegQueryStringValueWithDefaultAndExpand(HKEY__ *,wchar_t const *,wchar_t *,ulong,wchar_t const *,int)
0x18004be31  cmp     [rdi], r13w
0x18004be35  jnz     short loc_18004BE6D
0x18004be37  cmp     [rdi+2], r13w
0x18004be3c  jnz     short loc_18004BE6D
0x18004be3e  cmp     word ptr [rdi+4], 3Fh ; '?'
0x18004be43  jnz     short loc_18004BE6D
0x18004be45  cmp     [rdi+6], r13w
0x18004be4a  jnz     short loc_18004BE6D
0x18004be4c  lea     rdx, [rdi+8]; Src
0x18004be50  mov     r8, r14
0x18004be53  inc     r8
0x18004be56  cmp     [rdx+r8*2], r12w
0x18004be5b  jnz     short loc_18004BE53
0x18004be5d  lea     r8, ds:2[r8*2]; Size
0x18004be65  mov     rcx, rdi; void *
0x18004be68  call    memmove
0x18004be6d  mov     esi, 104h
0x18004be72  cmp     [rdi], r12w
0x18004be76  jnz     short loc_18004BEBB
0x18004be78  mov     r8d, esi; nSize
0x18004be7b  lea     rcx, Src; "%PROGRAMDATA%"
0x18004be82  mov     rdx, rdi; lpDst
0x18004be85  call    cs:__imp_ExpandEnvironmentStringsW
0x18004be8b  dec     eax
0x18004be8d  cmp     eax, 103h
0x18004be92  jbe     short loc_18004BEBB
0x18004be94  mov     edx, esi; uSize
0x18004be96  mov     rcx, rdi; lpBuffer
0x18004be99  call    cs:__imp_GetSystemWindowsDirectoryW
0x18004be9f  test    eax, eax
0x18004bea1  jnz     short loc_18004BEBB
0x18004bea3  lea     edx, [rax+5Fh]; void *
0x18004bea6  mov     rcx, [rbp+38h]; this
0x18004beaa  lea     r8, aCW1SSrcClientL_19; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18004beb1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004beb6  jmp     loc_18004C00E
0x18004bebb  mov     r8, rsi
0x18004bebe  mov     rax, rdi
0x18004bec1  cmp     [rax], r12w
0x18004bec5  jz      short loc_18004BED1
0x18004bec7  add     rax, 2
0x18004becb  sub     r8, 1
0x18004becf  jnz     short loc_18004BEC1
0x18004bed1  mov     rcx, rsi
0x18004bed4  mov     rax, r8
0x18004bed7  sub     rcx, r8
0x18004beda  neg     rax
0x18004bedd  mov     rax, r8
0x18004bee0  sbb     rdx, rdx
0x18004bee3  and     rdx, rcx
0x18004bee6  neg     rax
0x18004bee9  sbb     ebx, ebx
0x18004beeb  not     ebx
0x18004beed  and     ebx, 80070057h
0x18004bef3  test    r8, r8
0x18004bef6  jnz     short loc_18004BF04
0x18004bef8  mov     r9d, ebx
0x18004befb  lea     edx, [r8+63h]
0x18004beff  jmp     loc_18004BFDD
0x18004bf04  test    r15, r15
0x18004bf07  jnz     short loc_18004BF0E
0x18004bf09  mov     r14, r12
0x18004bf0c  jmp     short loc_18004BF21
0x18004bf0e  inc     r14
0x18004bf11  cmp     [r15+r14*2], r12w
0x18004bf16  jnz     short loc_18004BF0E
0x18004bf18  cmp     [r15], r13w
0x18004bf1c  jz      short loc_18004BF21
0x18004bf1e  inc     r14
0x18004bf21  cmp     rdx, rsi
0x18004bf24  ja      loc_18004BFF4
0x18004bf2a  lea     rax, [r14+16h]
0x18004bf2e  add     rax, rdx
0x18004bf31  cmp     rax, rsi
0x18004bf34  ja      loc_18004BFF4
0x18004bf3a  cmp     [rdi+rdx*2-2], r13w
0x18004bf40  jnz     short loc_18004BF4E
0x18004bf42  lea     rax, [rdx-1]
0x18004bf46  mov     rdx, rax
0x18004bf49  mov     [rdi+rax*2], r12w
0x18004bf4e  sub     rsi, rdx
0x18004bf51  mov     [rsp+50h+var_28], r12d; unsigned int
0x18004bf56  lea     rcx, [rdi+rdx*2]; pszDest
0x18004bf5a  mov     rdx, rsi; unsigned __int64
0x18004bf5d  lea     rax, [rbp+var_18]
0x18004bf61  lea     r9, [rbp+var_20]; wchar_t **
0x18004bf65  mov     [rsp+50h+phkResult], rax; int
0x18004bf6a  lea     r8, aSoftwaredistri; "\\SoftwareDistribution"
0x18004bf71  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18004bf76  mov     ebx, eax
0x18004bf78  test    eax, eax
0x18004bf7a  jns     short loc_18004BF83
0x18004bf7c  mov     edx, 91h
0x18004bf81  jmp     short loc_18004BFDA
0x18004bf83  xor     edx, edx; lpSecurityAttributes
0x18004bf85  mov     rcx, rdi; lpPathName
0x18004bf88  call    cs:__imp_CreateDirectoryW
0x18004bf8e  test    eax, eax
0x18004bf90  jnz     short loc_18004BFA9
0x18004bf92  call    cs:__imp_GetLastError
0x18004bf98  cmp     eax, 0B7h
0x18004bf9d  jz      short loc_18004BFA9
0x18004bf9f  mov     edx, 96h
0x18004bfa4  jmp     loc_18004BEA6
0x18004bfa9  test    r15, r15
0x18004bfac  jz      short loc_18004BFEF
0x18004bfae  mov     rcx, [rbp+var_20]
0x18004bfb2  mov     rdx, [rbp+var_18]
0x18004bfb6  cmp     [r15], r13w
0x18004bfba  jz      short loc_18004BFC7
0x18004bfbc  mov     [rcx], r13w
0x18004bfc0  add     rcx, 2; wchar_t *
0x18004bfc4  dec     rdx; unsigned __int64
0x18004bfc7  mov     r8, r15; wchar_t *
0x18004bfca  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18004bfcf  mov     ebx, eax
0x18004bfd1  test    eax, eax
0x18004bfd3  jns     short loc_18004BFEF
0x18004bfd5  mov     edx, 0A2h; void *
0x18004bfda  mov     r9d, eax; char *
0x18004bfdd  mov     rcx, [rbp+38h]; this
0x18004bfe1  lea     r8, aCW1SSrcClientL_19; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18004bfe8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bfed  jmp     short loc_18004C010
0x18004bfef  mov     ebx, r12d
0x18004bff2  jmp     short loc_18004C010
0x18004bff4  mov     rcx, [rbp+38h]; this
0x18004bff8  lea     r8, aCW1SSrcClientL_19; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18004bfff  mov     r9d, 7Ah ; 'z'; char *
0x18004c005  lea     edx, [r9+0Dh]; void *
0x18004c009  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004c00e  mov     ebx, eax
0x18004c010  mov     rcx, [rbp+hKey]; hKey
0x18004c014  test    rcx, rcx
0x18004c017  jz      short loc_18004C01F
0x18004c019  call    cs:__imp_RegCloseKey
0x18004c01f  mov     eax, ebx
0x18004c021  mov     rcx, [rbp+var_8]
0x18004c025  xor     rcx, rsp; StackCookie
0x18004c028  call    __security_check_cookie
0x18004c02d  mov     rbx, [rsp+50h+arg_8]
0x18004c035  add     rsp, 50h
0x18004c039  pop     r15
0x18004c03b  pop     r14
0x18004c03d  pop     r13
0x18004c03f  pop     r12
0x18004c041  pop     rdi
0x18004c042  pop     rsi
0x18004c043  pop     rbp
0x18004c044  retn
```
