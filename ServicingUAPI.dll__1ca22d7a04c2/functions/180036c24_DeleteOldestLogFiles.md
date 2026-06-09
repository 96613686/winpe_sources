# DeleteOldestLogFiles

- ea: `0x180036c24`
- end: `0x180037008`
- name: `DeleteOldestLogFiles`
- size: `996`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800375fc`

## callees

- `0x1800031d0`
- `0x180003c64`
- `0x1800062b8`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x1800296a4`
- `0x180036c24`
- `0x18003d278`
- `0x18003d670`
- `0x18003ddc8`
- `0x1800465b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036ea0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036fc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036ea0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036fc5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180036d62`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180036d62`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180036e05`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180036e05`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180036d23`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180036d23`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180036e7c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180036e7c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180036e1c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180036fb5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180036e1c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180036fb5`

## string_xrefs

- `0x180036eba`: `Failed to delete oldest backup log.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DeleteOldestLogFiles(__int64 a1)
{
  int Property; // eax
  unsigned int v3; // r14d
  int v4; // ebx
  __int64 v5; // rdx
  const WCHAR *v7; // rbx
  char *FirstFileW; // rax
  char *v9; // rdi
  unsigned int v10; // esi
  _OWORD *v11; // rax
  struct _WIN32_FIND_DATAW *p_FindFileData; // rcx
  __int64 v13; // rdx
  int v14; // eax
  unsigned int v15; // edi
  LPCWSTR v16; // rdi
  signed int LastError; // esi
  __int64 v18; // rdx
  unsigned int v19; // eax
  unsigned int v20; // esi
  LPCWSTR *p_lpFileName; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpFileName; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v23; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v24; // [rsp+40h] [rbp-C0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v26[20]; // [rsp+2A0h] [rbp+1A0h] BYREF
  FILETIME FileTime1; // [rsp+2B4h] [rbp+1B4h] BYREF
  char v28[548]; // [rsp+2CCh] [rbp+1CCh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+538h] [rbp+438h]

  v24 = -2;
  lpFileName = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  memset_0(v26, 0, 0x250u);
  v23 = 0;
  Property = OnlineConfigGetProperty(L"NumCBSPersistLogs", &v23);
  v3 = v23;
  if ( Property < 0 )
    v3 = 5;
  v4 = SczAllocFromSz(&lpFileName);
  if ( v4 < 0 )
  {
    v5 = 421;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
      (const char *)(unsigned int)v4,
      (int)p_lpFileName);
    if ( lpFileName )
      operator delete((void *)(lpFileName - 4));
    return (unsigned int)v4;
  }
  v4 = SczAllocConcatSz(&lpFileName, L"\\CbsPersist_*.*");
  if ( v4 < 0 )
  {
    v5 = 422;
    goto LABEL_5;
  }
  v7 = lpFileName;
  while ( 1 )
  {
    FirstFileW = (char *)FindFirstFileW(v7, &FindFileData);
    v9 = FirstFileW;
    if ( !FirstFileW )
      goto LABEL_56;
    v10 = 0;
    if ( FirstFileW == (char *)-1LL )
      goto LABEL_56;
    do
    {
      if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      {
        if ( !v10 || CompareFileTime(&FileTime1, &FindFileData.ftLastWriteTime) > 0 )
        {
          v11 = v26;
          p_FindFileData = &FindFileData;
          v13 = 4;
          do
          {
            *v11 = *(_OWORD *)&p_FindFileData->dwFileAttributes;
            v11[1] = *(_OWORD *)&p_FindFileData->ftLastAccessTime.dwHighDateTime;
            v11[2] = *(_OWORD *)&p_FindFileData->nFileSizeLow;
            v11[3] = *(_OWORD *)&p_FindFileData->cFileName[2];
            v11[4] = *(_OWORD *)&p_FindFileData->cFileName[10];
            v11[5] = *(_OWORD *)&p_FindFileData->cFileName[18];
            v11[6] = *(_OWORD *)&p_FindFileData->cFileName[26];
            v11[7] = *(_OWORD *)&p_FindFileData->cFileName[34];
            v11 += 8;
            p_FindFileData = (struct _WIN32_FIND_DATAW *)((char *)p_FindFileData + 128);
            --v13;
          }
          while ( v13 );
          *v11 = *(_OWORD *)&p_FindFileData->dwFileAttributes;
          v11[1] = *(_OWORD *)&p_FindFileData->ftLastAccessTime.dwHighDateTime;
          v11[2] = *(_OWORD *)&p_FindFileData->nFileSizeLow;
          v11[3] = *(_OWORD *)&p_FindFileData->cFileName[2];
          v11[4] = *(_OWORD *)&p_FindFileData->cFileName[10];
        }
        ++v10;
      }
    }
    while ( FindNextFileW(v9, &FindFileData) );
    if ( !FindClose(v9) )
    {
      GetLastError();
      __fastfail(7u);
    }
    v9 = 0;
    if ( v10 <= v3 )
    {
LABEL_56:
      if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && !FindClose(v9) )
      {
        GetLastError();
        __fastfail(7u);
      }
LABEL_51:
      if ( v7 )
        operator delete((void *)(v7 - 4));
      return 0;
    }
    lpFileName = 0;
    v14 = SczAllocFormatted(&lpFileName, L"%ws\\%ws", a1, v28);
    v15 = v14;
    if ( v14 < 0 )
      break;
    v16 = lpFileName;
    if ( !DeleteFileW(lpFileName) )
    {
      LastError = GetLastError();
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to delete oldest backup log.");
        if ( LastError > 0 )
          v19 = (unsigned __int16)LastError | 0x80070000;
        else
          v19 = LastError;
        v23 = v19;
        lpFileName = (LPCWSTR)&v23;
        p_lpFileName = &lpFileName;
        LOBYTE(v18) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v18,
          3,
          ": {0}");
      }
      if ( LastError )
      {
        v20 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x1CF,
                (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
                (const char *)(unsigned int)LastError,
                (unsigned int)p_lpFileName);
        if ( v16 )
          operator delete((void *)(v16 - 4));
        if ( v7 )
          operator delete((void *)(v7 - 4));
        return v20;
      }
      if ( v16 )
        operator delete((void *)(v16 - 4));
      goto LABEL_51;
    }
    if ( v16 )
      operator delete((void *)(v16 - 4));
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1CD,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
    (const char *)(unsigned int)v14,
    (int)p_lpFileName);
  if ( lpFileName )
    operator delete((void *)(lpFileName - 4));
  if ( v7 )
    operator delete((void *)(v7 - 4));
  return v15;
}

```

## disassembly

```asm
0x180036c24  push    rbp
0x180036c26  push    rbx
0x180036c27  push    rsi
0x180036c28  push    rdi
0x180036c29  push    r14
0x180036c2b  push    r15
0x180036c2d  lea     rbp, [rsp-408h]
0x180036c35  sub     rsp, 508h
0x180036c3c  mov     [rsp+530h+var_4F0], 0FFFFFFFFFFFFFFFEh
0x180036c45  mov     rax, cs:__security_cookie
0x180036c4c  xor     rax, rsp
0x180036c4f  mov     [rbp+430h+var_40], rax
0x180036c56  mov     r15, rcx
0x180036c59  mov     [rsp+530h+lpFileName], 0
0x180036c62  mov     ebx, 250h
0x180036c67  mov     r8d, ebx; Size
0x180036c6a  xor     edx, edx; Val
0x180036c6c  lea     rcx, [rsp+530h+FindFileData]; void *
0x180036c71  call    memset_0
0x180036c76  mov     r8d, ebx; Size
0x180036c79  xor     edx, edx; Val
0x180036c7b  lea     rcx, [rbp+430h+var_290]; void *
0x180036c82  call    memset_0
0x180036c87  mov     [rsp+530h+var_4F8], 0
0x180036c8f  lea     rdx, [rsp+530h+var_4F8]; unsigned int *
0x180036c94  lea     rcx, aNumcbspersistl; "NumCBSPersistLogs"
0x180036c9b  call    ?OnlineConfigGetProperty@@YAJPEB_WPEAK@Z; OnlineConfigGetProperty(wchar_t const *,ulong *)
0x180036ca0  mov     r14d, [rsp+530h+var_4F8]
0x180036ca5  mov     ecx, 5
0x180036caa  test    eax, eax
0x180036cac  cmovs   r14d, ecx
0x180036cb0  mov     rdx, r15
0x180036cb3  lea     rcx, [rsp+530h+lpFileName]
0x180036cb8  call    SczAllocFromSz
0x180036cbd  mov     ebx, eax
0x180036cbf  test    eax, eax
0x180036cc1  jns     short loc_180036CF8
0x180036cc3  mov     edx, 1A5h; void *
0x180036cc8  lea     r8, aOnecoreBaseCbs_8; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x180036ccf  mov     r9d, ebx; char *
0x180036cd2  mov     rcx, [rbp+438h]; this
0x180036cd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036cde  mov     rcx, [rsp+530h+lpFileName]
0x180036ce3  test    rcx, rcx
0x180036ce6  jz      short loc_180036CF1
0x180036ce8  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x180036cec  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180036cf1  mov     eax, ebx
0x180036cf3  jmp     loc_180036FE8
0x180036cf8  lea     rdx, aCbspersist; "\\CbsPersist_*.*"
0x180036cff  lea     rcx, [rsp+530h+lpFileName]
0x180036d04  call    SczAllocConcatSz
0x180036d09  mov     ebx, eax
0x180036d0b  test    eax, eax
0x180036d0d  jns     short loc_180036D16
0x180036d0f  mov     edx, 1A6h
0x180036d14  jmp     short loc_180036CC8
0x180036d16  mov     rbx, [rsp+530h+lpFileName]
0x180036d1b  lea     rdx, [rsp+530h+FindFileData]; lpFindFileData
0x180036d20  mov     rcx, rbx; lpFileName
0x180036d23  call    cs:__imp_FindFirstFileW
0x180036d2a  nop     dword ptr [rax+rax+00h]
0x180036d2f  mov     rdi, rax
0x180036d32  test    rax, rax
0x180036d35  jz      loc_180036FA8
0x180036d3b  xor     esi, esi
0x180036d3d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180036d41  jz      loc_180036FA8
0x180036d47  test    byte ptr [rsp+530h+FindFileData.dwFileAttributes], 10h
0x180036d4c  jnz     loc_180036DFD
0x180036d52  test    esi, esi
0x180036d54  jz      short loc_180036D76
0x180036d56  lea     rdx, [rsp+530h+FindFileData.ftLastWriteTime]; lpFileTime2
0x180036d5b  lea     rcx, [rbp+430h+FileTime1]; lpFileTime1
0x180036d62  call    cs:__imp_CompareFileTime
0x180036d69  nop     dword ptr [rax+rax+00h]
0x180036d6e  test    eax, eax
0x180036d70  jle     loc_180036DFB
0x180036d76  lea     rax, [rbp+430h+var_290]
0x180036d7d  lea     rcx, [rsp+530h+FindFileData]
0x180036d82  mov     edx, 4
0x180036d87  lea     r8d, [rdx+7Ch]
0x180036d8b  movups  xmm0, xmmword ptr [rcx]
0x180036d8e  movups  xmmword ptr [rax], xmm0
0x180036d91  movups  xmm1, xmmword ptr [rcx+10h]
0x180036d95  movups  xmmword ptr [rax+10h], xmm1
0x180036d99  movups  xmm0, xmmword ptr [rcx+20h]
0x180036d9d  movups  xmmword ptr [rax+20h], xmm0
0x180036da1  movups  xmm1, xmmword ptr [rcx+30h]
0x180036da5  movups  xmmword ptr [rax+30h], xmm1
0x180036da9  movups  xmm0, xmmword ptr [rcx+40h]
0x180036dad  movups  xmmword ptr [rax+40h], xmm0
0x180036db1  movups  xmm1, xmmword ptr [rcx+50h]
0x180036db5  movups  xmmword ptr [rax+50h], xmm1
0x180036db9  movups  xmm0, xmmword ptr [rcx+60h]
0x180036dbd  movups  xmmword ptr [rax+60h], xmm0
0x180036dc1  movups  xmm1, xmmword ptr [rcx+70h]
0x180036dc5  movups  xmmword ptr [rax+70h], xmm1
0x180036dc9  add     rax, r8
0x180036dcc  add     rcx, r8
0x180036dcf  sub     rdx, 1
0x180036dd3  jnz     short loc_180036D8B
0x180036dd5  movups  xmm0, xmmword ptr [rcx]
0x180036dd8  movups  xmmword ptr [rax], xmm0
0x180036ddb  movups  xmm1, xmmword ptr [rcx+10h]
0x180036ddf  movups  xmmword ptr [rax+10h], xmm1
0x180036de3  movups  xmm0, xmmword ptr [rcx+20h]
0x180036de7  movups  xmmword ptr [rax+20h], xmm0
0x180036deb  movups  xmm1, xmmword ptr [rcx+30h]
0x180036def  movups  xmmword ptr [rax+30h], xmm1
0x180036df3  movups  xmm0, xmmword ptr [rcx+40h]
0x180036df7  movups  xmmword ptr [rax+40h], xmm0
0x180036dfb  inc     esi
0x180036dfd  lea     rdx, [rsp+530h+FindFileData]; lpFindFileData
0x180036e02  mov     rcx, rdi; hFindFile
0x180036e05  call    cs:__imp_FindNextFileW
0x180036e0c  nop     dword ptr [rax+rax+00h]
0x180036e11  test    eax, eax
0x180036e13  jnz     loc_180036D47
0x180036e19  mov     rcx, rdi; hFindFile
0x180036e1c  call    cs:__imp_FindClose
0x180036e23  nop     dword ptr [rax+rax+00h]
0x180036e28  test    eax, eax
0x180036e2a  jnz     short loc_180036E3F
0x180036e2c  call    cs:__imp_GetLastError
0x180036e33  nop     dword ptr [rax+rax+00h]
0x180036e38  mov     ecx, 7
0x180036e3d  int     29h; Win8: RtlFailFast(ecx)
0x180036e3f  xor     edi, edi
0x180036e41  cmp     esi, r14d
0x180036e44  jbe     loc_180036FA8
0x180036e4a  mov     [rsp+530h+lpFileName], rdi
0x180036e4f  lea     r9, [rbp+430h+var_264]
0x180036e56  mov     r8, r15
0x180036e59  lea     rdx, aWsWs_1; "%ws\\%ws"
0x180036e60  lea     rcx, [rsp+530h+lpFileName]
0x180036e65  call    SczAllocFormatted
0x180036e6a  mov     edi, eax
0x180036e6c  test    eax, eax
0x180036e6e  js      loc_180036F67
0x180036e74  mov     rdi, [rsp+530h+lpFileName]
0x180036e79  mov     rcx, rdi; lpFileName
0x180036e7c  call    cs:__imp_DeleteFileW
0x180036e83  nop     dword ptr [rax+rax+00h]
0x180036e88  test    eax, eax
0x180036e8a  jz      short loc_180036EA0
0x180036e8c  test    rdi, rdi
0x180036e8f  jz      short loc_180036E9B
0x180036e91  lea     rcx, [rdi-8]; Block
0x180036e95  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180036e9a  nop
0x180036e9b  jmp     loc_180036D1B
0x180036ea0  call    cs:__imp_GetLastError
0x180036ea7  nop     dword ptr [rax+rax+00h]
0x180036eac  mov     esi, eax
0x180036eae  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180036eb5  test    rcx, rcx
0x180036eb8  jz      short loc_180036F11
0x180036eba  lea     r9, aFailedToDelete_3; "Failed to delete oldest backup log."
0x180036ec1  mov     r14d, 3
0x180036ec7  mov     r8d, r14d
0x180036eca  xor     edx, edx
0x180036ecc  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180036ed1  test    esi, esi
0x180036ed3  jg      short loc_180036ED9
0x180036ed5  mov     eax, esi
0x180036ed7  jmp     short loc_180036EE1
0x180036ed9  movzx   eax, si
0x180036edc  or      eax, 80070000h
0x180036ee1  mov     [rsp+530h+var_4F8], eax
0x180036ee5  lea     rax, [rsp+530h+var_4F8]
0x180036eea  mov     [rsp+530h+lpFileName], rax
0x180036eef  lea     rax, [rsp+530h+lpFileName]
0x180036ef4  mov     qword ptr [rsp+530h+var_510], rax; unsigned int
0x180036ef9  lea     r9, a0; ": {0}"
0x180036f00  mov     r8d, r14d
0x180036f03  mov     dl, 1
0x180036f05  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180036f0c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180036f11  test    esi, esi
0x180036f13  jz      short loc_180036F56
0x180036f15  mov     rcx, [rbp+438h]; this
0x180036f1c  mov     r9d, esi; char *
0x180036f1f  lea     r8, aOnecoreBaseCbs_8; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x180036f26  mov     edx, 1CFh; void *
0x180036f2b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180036f30  mov     esi, eax
0x180036f32  test    rdi, rdi
0x180036f35  jz      short loc_180036F41
0x180036f37  lea     rcx, [rdi-8]; Block
0x180036f3b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180036f40  nop
0x180036f41  test    rbx, rbx
0x180036f44  jz      short loc_180036F4F
0x180036f46  lea     rcx, [rbx-8]; Block
0x180036f4a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180036f4f  mov     eax, esi
0x180036f51  jmp     loc_180036FE8
0x180036f56  test    rdi, rdi
0x180036f59  jz      short loc_180036F65
0x180036f5b  lea     rcx, [rdi-8]; Block
0x180036f5f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180036f64  nop
0x180036f65  jmp     short loc_180036FD8
0x180036f67  mov     rcx, [rbp+438h]; this
0x180036f6e  mov     r9d, edi; char *
0x180036f71  lea     r8, aOnecoreBaseCbs_8; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x180036f78  mov     edx, 1CDh; void *
0x180036f7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036f82  mov     rcx, [rsp+530h+lpFileName]
0x180036f87  test    rcx, rcx
0x180036f8a  jz      short loc_180036F96
0x180036f8c  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x180036f90  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180036f95  nop
0x180036f96  test    rbx, rbx
0x180036f99  jz      short loc_180036FA4
0x180036f9b  lea     rcx, [rbx-8]; Block
0x180036f9f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180036fa4  mov     eax, edi
0x180036fa6  jmp     short loc_180036FE8
0x180036fa8  lea     rax, [rdi-1]
0x180036fac  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180036fb0  ja      short loc_180036FD8
0x180036fb2  mov     rcx, rdi; hFindFile
0x180036fb5  call    cs:__imp_FindClose
0x180036fbc  nop     dword ptr [rax+rax+00h]
0x180036fc1  test    eax, eax
0x180036fc3  jnz     short loc_180036FD8
0x180036fc5  call    cs:__imp_GetLastError
0x180036fcc  nop     dword ptr [rax+rax+00h]
0x180036fd1  mov     ecx, 7
0x180036fd6  int     29h; Win8: RtlFailFast(ecx)
0x180036fd8  test    rbx, rbx
0x180036fdb  jz      short loc_180036FE6
0x180036fdd  lea     rcx, [rbx-8]; Block
0x180036fe1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180036fe6  xor     eax, eax
0x180036fe8  mov     rcx, [rbp+430h+var_40]
0x180036fef  xor     rcx, rsp; StackCookie
0x180036ff2  call    __security_check_cookie
0x180036ff7  add     rsp, 508h
0x180036ffe  pop     r15
0x180037000  pop     r14
0x180037002  pop     rdi
0x180037003  pop     rsi
0x180037004  pop     rbx
0x180037005  pop     rbp
0x180037006  retn
```
