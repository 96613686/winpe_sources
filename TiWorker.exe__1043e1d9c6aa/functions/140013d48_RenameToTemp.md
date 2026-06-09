# RenameToTemp

- ea: `0x140013d48`
- end: `0x1400140fe`
- name: `RenameToTemp`
- size: `950`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x14001344c`

## callees

- `0x140002310`
- `0x1400025a4`
- `0x1400053c0`
- `0x140006514`
- `0x140008d38`
- `0x140008ef4`
- `0x14000d910`
- `0x14000dbc8`
- `0x14000f36c`
- `0x140013d48`
- `0x1400177d8`
- `0x140017ec8`
- `0x140018298`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014039`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014039`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14001402b`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14001402b`

## string_xrefs

- `0x140013d9f`: `No directory specified`
- `0x140014006`: `Moving directory from {} to {}`
- `0x140013e26`: `Failed duplicating directory path: {}`
- `0x140013e95`: `Invalid directory path for deletion: {}`
- `0x140013f11`: `Invalid directory path for deletion: {}`
- `0x14001405a`: `Failed to move {} to temp directory {}`

## pseudocode

```c
__int64 __fastcall RenameToTemp(const WCHAR *a1, const struct std::nothrow_t *a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // rdx
  int v6; // eax
  __int64 v7; // rdx
  unsigned __int64 v8; // rdx
  __int64 v9; // rdx
  unsigned __int64 v10; // rdx
  __int64 v11; // rdx
  unsigned __int64 v12; // r9
  const struct std::nothrow_t *v13; // rdx
  const struct std::nothrow_t *v14; // rdx
  int v16; // eax
  int v17; // eax
  int v18; // edx
  const WCHAR *v19; // rdi
  const struct std::nothrow_t *v20; // rdx
  signed int LastError; // ebx
  __int64 v22; // rdx
  unsigned int v23; // eax
  const struct std::nothrow_t *v24; // rdx
  LPCWSTR lpNewFileName; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v26[2]; // [rsp+38h] [rbp-38h] BYREF
  LPCWSTR v27; // [rsp+40h] [rbp-30h] BYREF
  __int64 v28; // [rsp+48h] [rbp-28h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+50h] [rbp-20h] BYREF
  int v30; // [rsp+58h] [rbp-18h] BYREF
  int *v31; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  lpExistingFileName = a1;
  lpNewFileName = 0;
  v28 = 0;
  if ( !a1 )
  {
    v3 = -2147024809;
    v30 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No directory specified");
      v31 = &v30;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v4,
        3,
        (__int64)": {}",
        (__int64)&v31);
    }
    v5 = 716;
LABEL_23:
    v12 = v3;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)v12);
LABEL_25:
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v28, v13);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close((__int64 *)&lpNewFileName, v14);
    return v3;
  }
  if ( *(_QWORD *)a2 )
  {
    operator delete((void *)(*(_QWORD *)a2 - 8LL), a2);
    a1 = lpExistingFileName;
    *(_QWORD *)a2 = 0;
  }
  v6 = SczAllocFromSz(&lpNewFileName, a1);
  v3 = v6;
  if ( v6 < 0 )
  {
    v30 = v6;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed duplicating directory path: {}",
        (__int64)&lpExistingFileName);
      *(_QWORD *)v26 = &v30;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v7,
        3,
        (__int64)": {}",
        (__int64)v26);
    }
    v5 = 719;
    goto LABEL_23;
  }
  v8 = -1;
  do
    ++v8;
  while ( lpNewFileName[v8] );
  if ( v8 <= 2 )
  {
    v3 = -2147024809;
    LODWORD(v31) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      v27 = lpNewFileName;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Invalid directory path for deletion: {}",
        (__int64)&v27);
      *(_QWORD *)v26 = &v31;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v9,
        3,
        (__int64)": {}",
        (__int64)v26);
    }
    v5 = 726;
    goto LABEL_23;
  }
  v10 = v8 - 2;
  if ( !v10 )
  {
LABEL_20:
    v3 = -2147024809;
    LODWORD(v31) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      v27 = lpNewFileName;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Invalid directory path for deletion: {}",
        (__int64)&v27);
      *(_QWORD *)v26 = &v31;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v11,
        3,
        (__int64)": {}",
        (__int64)v26);
    }
    v5 = 738;
    goto LABEL_23;
  }
  while ( lpNewFileName[v10] != 92 )
  {
    if ( !--v10 )
      goto LABEL_20;
  }
  lpNewFileName[v10 + 1] = 0;
  v16 = SczAllocGuid(&v28);
  v3 = v16;
  if ( v16 < 0 )
  {
    v12 = (unsigned int)v16;
    v5 = 743;
    goto LABEL_24;
  }
  v17 = SczAllocConcatSz(&lpNewFileName, v28);
  v3 = v17;
  if ( v17 < 0 )
  {
    v12 = (unsigned int)v17;
    v5 = 744;
    goto LABEL_24;
  }
  v19 = lpNewFileName;
  v27 = lpNewFileName;
  if ( LogAdapter::g_Logger )
  {
    LOBYTE(v18) = 1;
    LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
      (_DWORD)LogAdapter::g_Logger,
      v18,
      1,
      (unsigned int)"Moving directory from {} to {}",
      (__int64)&lpExistingFileName,
      (__int64)&v27);
  }
  if ( !MoveFileExW(lpExistingFileName, v19, 1u) )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      v27 = v19;
      LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to move {} to temp directory {}",
        (__int64)&lpExistingFileName,
        (__int64)&v27);
      if ( LastError > 0 )
        v23 = (unsigned __int16)LastError | 0x80070000;
      else
        v23 = LastError;
      LODWORD(v31) = v23;
      *(_QWORD *)v26 = &v31;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v22,
        3,
        (__int64)": {0}",
        (__int64)v26);
    }
    if ( LastError )
      v3 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x2EE,
             (int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
             (const char *)(unsigned int)LastError);
    else
      v3 = 0;
    goto LABEL_25;
  }
  lpNewFileName = 0;
  *(_QWORD *)a2 = v19;
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v28, v20);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close((__int64 *)&lpNewFileName, v24);
  return 0;
}

```

## disassembly

```asm
0x140013d48  mov     [rsp-18h+arg_10], rbx
0x140013d4d  mov     [rsp-18h+arg_18], rsi
0x140013d52  push    rbp
0x140013d53  push    rdi
0x140013d54  push    r14
0x140013d56  mov     rbp, rsp
0x140013d59  sub     rsp, 70h
0x140013d5d  mov     rax, cs:__security_cookie
0x140013d64  xor     rax, rsp
0x140013d67  mov     [rbp+var_8], rax
0x140013d6b  xor     r14d, r14d
0x140013d6e  mov     [rbp+lpExistingFileName], rcx
0x140013d72  mov     [rbp+lpNewFileName], r14
0x140013d76  mov     rsi, rdx
0x140013d79  mov     [rbp+var_28], r14
0x140013d7d  test    rcx, rcx
0x140013d80  jnz     short loc_140013DDC
0x140013d82  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140013d89  mov     ebx, 80070057h
0x140013d8e  mov     [rbp+var_18], ebx
0x140013d91  test    rcx, rcx
0x140013d94  jz      short loc_140013DD2
0x140013d96  lea     edi, [r14+3]
0x140013d9a  xor     edx, edx
0x140013d9c  mov     r8d, edi
0x140013d9f  lea     r9, aNoDirectorySpe; "No directory specified"
0x140013da6  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140013dab  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140013db2  lea     rax, [rbp+var_18]
0x140013db6  mov     [rbp+var_10], rax
0x140013dba  lea     r9, asc_140030534; ": {}"
0x140013dc1  lea     rax, [rbp+var_10]
0x140013dc5  mov     r8d, edi
0x140013dc8  mov     qword ptr [rsp+70h+var_50], rax
0x140013dcd  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140013dd2  mov     edx, 2CCh; struct std::nothrow_t *
0x140013dd7  jmp     loc_140013F5C
0x140013ddc  mov     rax, [rdx]
0x140013ddf  test    rax, rax
0x140013de2  jz      short loc_140013DF4
0x140013de4  lea     rcx, [rax-8]; void *
0x140013de8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140013ded  mov     rcx, [rbp+lpExistingFileName]
0x140013df1  mov     [rsi], r14
0x140013df4  mov     rdx, rcx
0x140013df7  lea     rcx, [rbp+lpNewFileName]
0x140013dfb  call    SczAllocFromSz
0x140013e00  mov     ebx, eax
0x140013e02  test    eax, eax
0x140013e04  jns     short loc_140013E65
0x140013e06  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140013e0d  mov     [rbp+var_18], eax
0x140013e10  test    rcx, rcx
0x140013e13  jz      short loc_140013E5B
0x140013e15  lea     rax, [rbp+lpExistingFileName]
0x140013e19  mov     edi, 3
0x140013e1e  mov     r8d, edi
0x140013e21  mov     qword ptr [rsp+70h+var_50], rax
0x140013e26  lea     r9, aFailedDuplicat; "Failed duplicating directory path: {}"
0x140013e2d  xor     edx, edx
0x140013e2f  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140013e34  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140013e3b  lea     rax, [rbp+var_18]
0x140013e3f  mov     qword ptr [rbp+var_38], rax
0x140013e43  lea     r9, asc_140030534; ": {}"
0x140013e4a  lea     rax, [rbp+var_38]
0x140013e4e  mov     r8d, edi
0x140013e51  mov     qword ptr [rsp+70h+var_50], rax
0x140013e56  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140013e5b  mov     edx, 2CFh
0x140013e60  jmp     loc_140013F5C
0x140013e65  mov     rax, [rbp+lpNewFileName]
0x140013e69  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140013e6d  inc     rdx
0x140013e70  cmp     [rax+rdx*2], r14w
0x140013e75  jnz     short loc_140013E6D
0x140013e77  cmp     rdx, 2
0x140013e7b  ja      short loc_140013EE2
0x140013e7d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140013e84  mov     ebx, 80070057h
0x140013e89  mov     dword ptr [rbp+var_10], ebx
0x140013e8c  test    rcx, rcx
0x140013e8f  jz      short loc_140013EDB
0x140013e91  mov     [rbp+var_30], rax
0x140013e95  lea     r9, aInvalidDirecto; "Invalid directory path for deletion: {}"
0x140013e9c  lea     rax, [rbp+var_30]
0x140013ea0  mov     edi, 3
0x140013ea5  mov     r8d, edi
0x140013ea8  mov     qword ptr [rsp+70h+var_50], rax
0x140013ead  xor     edx, edx
0x140013eaf  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140013eb4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140013ebb  lea     rax, [rbp+var_10]
0x140013ebf  mov     qword ptr [rbp+var_38], rax
0x140013ec3  lea     r9, asc_140030534; ": {}"
0x140013eca  lea     rax, [rbp+var_38]
0x140013ece  mov     r8d, edi
0x140013ed1  mov     qword ptr [rsp+70h+var_50], rax
0x140013ed6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140013edb  mov     edx, 2D6h
0x140013ee0  jmp     short loc_140013F5C
0x140013ee2  add     rdx, 0FFFFFFFFFFFFFFFEh
0x140013ee6  jz      short loc_140013EF9
0x140013ee8  cmp     word ptr [rax+rdx*2], 5Ch ; '\'
0x140013eed  jz      loc_140013FA4
0x140013ef3  sub     rdx, 1
0x140013ef7  jnz     short loc_140013EE8
0x140013ef9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140013f00  mov     ebx, 80070057h
0x140013f05  mov     dword ptr [rbp+var_10], ebx
0x140013f08  test    rcx, rcx
0x140013f0b  jz      short loc_140013F57
0x140013f0d  mov     [rbp+var_30], rax
0x140013f11  lea     r9, aInvalidDirecto; "Invalid directory path for deletion: {}"
0x140013f18  lea     rax, [rbp+var_30]
0x140013f1c  mov     edi, 3
0x140013f21  mov     r8d, edi
0x140013f24  mov     qword ptr [rsp+70h+var_50], rax
0x140013f29  xor     edx, edx
0x140013f2b  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140013f30  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140013f37  lea     rax, [rbp+var_10]
0x140013f3b  mov     qword ptr [rbp+var_38], rax
0x140013f3f  lea     r9, asc_140030534; ": {}"
0x140013f46  lea     rax, [rbp+var_38]
0x140013f4a  mov     r8d, edi
0x140013f4d  mov     qword ptr [rsp+70h+var_50], rax; int
0x140013f52  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140013f57  mov     edx, 2E2h; void *
0x140013f5c  mov     r9d, ebx; char *
0x140013f5f  mov     rcx, [rbp+18h]; this
0x140013f63  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x140013f6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013f6f  lea     rcx, [rbp+var_28]
0x140013f73  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140013f78  lea     rcx, [rbp+lpNewFileName]
0x140013f7c  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140013f81  mov     eax, ebx
0x140013f83  mov     rcx, [rbp+var_8]
0x140013f87  xor     rcx, rsp; StackCookie
0x140013f8a  call    __security_check_cookie
0x140013f8f  lea     r11, [rsp+70h+var_s0]
0x140013f94  mov     rbx, [r11+30h]
0x140013f98  mov     rsi, [r11+38h]
0x140013f9c  mov     rsp, r11
0x140013f9f  pop     r14
0x140013fa1  pop     rdi
0x140013fa2  pop     rbp
0x140013fa3  retn
0x140013fa4  lea     rcx, [rbp+var_28]
0x140013fa8  mov     [rax+rdx*2+2], r14w
0x140013fae  call    SczAllocGuid
0x140013fb3  mov     ebx, eax
0x140013fb5  test    eax, eax
0x140013fb7  jns     short loc_140013FC3
0x140013fb9  mov     r9d, eax
0x140013fbc  mov     edx, 2E7h
0x140013fc1  jmp     short loc_140013F5F
0x140013fc3  mov     rdx, [rbp+var_28]
0x140013fc7  lea     rcx, [rbp+lpNewFileName]
0x140013fcb  call    SczAllocConcatSz
0x140013fd0  mov     ebx, eax
0x140013fd2  test    eax, eax
0x140013fd4  jns     short loc_140013FE3
0x140013fd6  mov     r9d, eax
0x140013fd9  mov     edx, 2E8h
0x140013fde  jmp     loc_140013F5F
0x140013fe3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140013fea  mov     rdi, [rbp+lpNewFileName]
0x140013fee  mov     [rbp+var_30], rdi
0x140013ff2  test    rcx, rcx
0x140013ff5  jz      short loc_14001401E
0x140013ff7  lea     rax, [rbp+var_30]
0x140013ffb  mov     r8d, 1
0x140014001  mov     [rsp+70h+var_48], rax
0x140014006  lea     r9, aMovingDirector; "Moving directory from {} to {}"
0x14001400d  lea     rax, [rbp+lpExistingFileName]
0x140014011  mov     dl, r8b
0x140014014  mov     qword ptr [rsp+70h+var_50], rax
0x140014019  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x14001401e  mov     rcx, [rbp+lpExistingFileName]; lpExistingFileName
0x140014022  mov     r8d, 1; dwFlags
0x140014028  mov     rdx, rdi; lpNewFileName
0x14001402b  call    cs:__imp_MoveFileExW
0x140014031  test    eax, eax
0x140014033  jnz     loc_1400140DE
0x140014039  call    cs:__imp_GetLastError
0x14001403f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140014046  mov     ebx, eax
0x140014048  test    rcx, rcx
0x14001404b  jz      short loc_1400140B3
0x14001404d  lea     rax, [rbp+var_30]
0x140014051  mov     [rbp+var_30], rdi
0x140014055  mov     [rsp+70h+var_48], rax
0x14001405a  lea     r9, aFailedToMoveTo; "Failed to move {} to temp directory {}"
0x140014061  lea     rax, [rbp+lpExistingFileName]
0x140014065  mov     edi, 3
0x14001406a  mov     r8d, edi
0x14001406d  mov     qword ptr [rsp+70h+var_50], rax
0x140014072  xor     edx, edx
0x140014074  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x140014079  test    ebx, ebx
0x14001407b  jg      short loc_140014081
0x14001407d  mov     eax, ebx
0x14001407f  jmp     short loc_140014089
0x140014081  movzx   eax, bx
0x140014084  or      eax, 80070000h
0x140014089  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140014090  lea     r9, a0; ": {0}"
0x140014097  mov     dword ptr [rbp+var_10], eax
0x14001409a  mov     r8d, edi
0x14001409d  lea     rax, [rbp+var_10]
0x1400140a1  mov     qword ptr [rbp+var_38], rax
0x1400140a5  lea     rax, [rbp+var_38]
0x1400140a9  mov     qword ptr [rsp+70h+var_50], rax; unsigned int
0x1400140ae  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400140b3  test    ebx, ebx
0x1400140b5  jz      short loc_1400140D6
0x1400140b7  mov     rcx, [rbp+18h]; this
0x1400140bb  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x1400140c2  mov     r9d, ebx; char *
0x1400140c5  mov     edx, 2EEh; void *
0x1400140ca  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400140cf  mov     ebx, eax
0x1400140d1  jmp     loc_140013F6F
0x1400140d6  mov     ebx, r14d
0x1400140d9  jmp     loc_140013F6F
0x1400140de  lea     rcx, [rbp+var_28]
0x1400140e2  mov     [rbp+lpNewFileName], r14
0x1400140e6  mov     [rsi], rdi
0x1400140e9  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1400140ee  lea     rcx, [rbp+lpNewFileName]
0x1400140f2  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1400140f7  xor     eax, eax
0x1400140f9  jmp     loc_140013F83
```
