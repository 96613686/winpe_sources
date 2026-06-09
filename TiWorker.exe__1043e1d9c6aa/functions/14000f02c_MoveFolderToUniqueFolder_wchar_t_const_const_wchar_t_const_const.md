# MoveFolderToUniqueFolder(wchar_t const * const,wchar_t const * const)

- ea: `0x14000f02c`
- end: `0x14000f266`
- name: `?MoveFolderToUniqueFolder@@YAJQEB_W0@Z`
- size: `570`
- prototype: `__int64 __fastcall(const WCHAR *, const wchar_t *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x14000ed6c`

## callees

- `0x140002310`
- `0x1400053c0`
- `0x140006514`
- `0x140008d38`
- `0x140008ef4`
- `0x14000dbc8`
- `0x14000e1f0`
- `0x14000f02c`
- `0x14000f36c`
- `0x140015228`
- `0x140017ec8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f1a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f1a2`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14000f194`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14000f194`

## string_xrefs

- `0x14000f07c`: `Failed to create destination folder`
- `0x14000f10f`: `Failed to append guid to path`
- `0x14000f1c5`: `Failed to move {} to {}.`

## pseudocode

```c
__int64 __fastcall MoveFolderToUniqueFolder(const WCHAR *a1, const wchar_t *a2)
{
  int Directory; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  unsigned __int64 v6; // r9
  __int64 v7; // rdx
  int v8; // eax
  const struct std::nothrow_t *v9; // rdx
  int appended; // eax
  int v11; // edx
  __int64 v12; // rdx
  const WCHAR *v13; // rbx
  signed int LastError; // edi
  __int64 v15; // rdx
  unsigned int v16; // eax
  unsigned int v18; // [rsp+20h] [rbp-40h]
  unsigned int v19[2]; // [rsp+30h] [rbp-30h] BYREF
  LPCWSTR lpNewFileName; // [rsp+38h] [rbp-28h] BYREF
  LPCWSTR v21; // [rsp+40h] [rbp-20h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+48h] [rbp-18h] BYREF
  unsigned int v23; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  lpExistingFileName = a1;
  lpNewFileName = 0;
  Directory = RecursivelyCreateDirectory(a2, 0);
  v4 = Directory;
  if ( Directory < 0 )
  {
    v23 = Directory;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create destination folder");
      *(_QWORD *)v19 = &v23;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v5,
        3,
        (__int64)": {}",
        (__int64)v19);
    }
    v6 = v4;
    v7 = 499;
    goto LABEL_7;
  }
  v8 = SczAllocFromSz(&lpNewFileName, a2);
  v4 = v8;
  if ( v8 < 0 )
  {
    v6 = (unsigned int)v8;
    v7 = 501;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
      (const char *)v6,
      v18);
    goto LABEL_23;
  }
  appended = AppendGuidToPath((struct AutoScz *)&lpNewFileName);
  v4 = appended;
  if ( appended < 0 )
  {
    v23 = appended;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to append guid to path");
      *(_QWORD *)v19 = &v23;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v12,
        3,
        (__int64)": {}",
        (__int64)v19);
    }
    v6 = v4;
    v7 = 504;
    goto LABEL_7;
  }
  v13 = lpNewFileName;
  v21 = lpNewFileName;
  if ( LogAdapter::g_Logger )
  {
    LOBYTE(v11) = 1;
    LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
      (_DWORD)LogAdapter::g_Logger,
      v11,
      1,
      (unsigned int)"Moving '{}' to '{}'",
      (__int64)&lpExistingFileName,
      (__int64)&v21);
  }
  if ( MoveFileExW(lpExistingFileName, v13, 8u) )
    goto LABEL_22;
  LastError = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    v21 = v13;
    LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
      (_DWORD)LogAdapter::g_Logger,
      0,
      3,
      (unsigned int)"Failed to move {} to {}.",
      (__int64)&lpExistingFileName,
      (__int64)&v21);
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    else
      v16 = LastError;
    v23 = v16;
    *(_QWORD *)v19 = &v23;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      v15,
      3,
      (__int64)": {0}",
      (__int64)v19);
  }
  if ( !LastError )
LABEL_22:
    v4 = 0;
  else
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1FC,
           (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
           (const char *)(unsigned int)LastError,
           v18);
LABEL_23:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close((__int64 *)&lpNewFileName, v9);
  return v4;
}

```

## disassembly

```asm
0x14000f02c  mov     [rsp-8+arg_10], rbx
0x14000f031  mov     [rsp-8+arg_18], rdi
0x14000f036  push    rbp
0x14000f037  mov     rbp, rsp
0x14000f03a  sub     rsp, 60h
0x14000f03e  mov     rax, cs:__security_cookie
0x14000f045  xor     rax, rsp
0x14000f048  mov     [rbp+var_8], rax
0x14000f04c  mov     rdi, rdx
0x14000f04f  mov     [rbp+lpExistingFileName], rcx
0x14000f053  mov     rcx, rdi
0x14000f056  mov     [rbp+lpNewFileName], 0
0x14000f05e  xor     edx, edx
0x14000f060  call    RecursivelyCreateDirectory
0x14000f065  mov     ebx, eax
0x14000f067  test    eax, eax
0x14000f069  jns     short loc_14000F0C0
0x14000f06b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000f072  mov     [rbp+var_10], eax
0x14000f075  test    rcx, rcx
0x14000f078  jz      short loc_14000F0B6
0x14000f07a  xor     edx, edx
0x14000f07c  lea     r9, aFailedToCreate_1; "Failed to create destination folder"
0x14000f083  lea     r8d, [rdx+3]
0x14000f087  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000f08c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000f093  lea     rax, [rbp+var_10]
0x14000f097  mov     qword ptr [rbp+var_30], rax
0x14000f09b  lea     r9, asc_140030534; ": {}"
0x14000f0a2  lea     rax, [rbp+var_30]
0x14000f0a6  mov     r8d, 3
0x14000f0ac  mov     qword ptr [rsp+60h+var_40], rax
0x14000f0b1  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000f0b6  mov     r9d, ebx
0x14000f0b9  mov     edx, 1F3h
0x14000f0be  jmp     short loc_14000F0DA
0x14000f0c0  mov     rdx, rdi
0x14000f0c3  lea     rcx, [rbp+lpNewFileName]
0x14000f0c7  call    SczAllocFromSz
0x14000f0cc  mov     ebx, eax
0x14000f0ce  test    eax, eax
0x14000f0d0  jns     short loc_14000F0EF
0x14000f0d2  mov     r9d, eax; char *
0x14000f0d5  mov     edx, 1F5h; void *
0x14000f0da  mov     rcx, [rbp+8]; this
0x14000f0de  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x14000f0e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000f0ea  jmp     loc_14000F23D
0x14000f0ef  lea     rcx, [rbp+lpNewFileName]; struct AutoScz *
0x14000f0f3  call    ?AppendGuidToPath@@YAJAEAVAutoScz@@@Z; AppendGuidToPath(AutoScz &)
0x14000f0f8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000f0ff  mov     ebx, eax
0x14000f101  test    eax, eax
0x14000f103  jns     short loc_14000F153
0x14000f105  mov     [rbp+var_10], eax
0x14000f108  test    rcx, rcx
0x14000f10b  jz      short loc_14000F149
0x14000f10d  xor     edx, edx
0x14000f10f  lea     r9, aFailedToAppend_0; "Failed to append guid to path"
0x14000f116  lea     r8d, [rdx+3]
0x14000f11a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000f11f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000f126  lea     rax, [rbp+var_10]
0x14000f12a  mov     qword ptr [rbp+var_30], rax
0x14000f12e  lea     r9, asc_140030534; ": {}"
0x14000f135  lea     rax, [rbp+var_30]
0x14000f139  mov     r8d, 3
0x14000f13f  mov     qword ptr [rsp+60h+var_40], rax
0x14000f144  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000f149  mov     r9d, ebx
0x14000f14c  mov     edx, 1F8h
0x14000f151  jmp     short loc_14000F0DA
0x14000f153  mov     rbx, [rbp+lpNewFileName]
0x14000f157  mov     [rbp+var_20], rbx
0x14000f15b  test    rcx, rcx
0x14000f15e  jz      short loc_14000F187
0x14000f160  lea     rax, [rbp+var_20]
0x14000f164  mov     r8d, 1
0x14000f16a  mov     [rsp+60h+var_38], rax
0x14000f16f  lea     r9, aMovingTo; "Moving '{}' to '{}'"
0x14000f176  lea     rax, [rbp+lpExistingFileName]
0x14000f17a  mov     dl, r8b
0x14000f17d  mov     qword ptr [rsp+60h+var_40], rax
0x14000f182  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x14000f187  mov     rcx, [rbp+lpExistingFileName]; lpExistingFileName
0x14000f18b  mov     r8d, 8; dwFlags
0x14000f191  mov     rdx, rbx; lpNewFileName
0x14000f194  call    cs:__imp_MoveFileExW
0x14000f19a  test    eax, eax
0x14000f19c  jnz     loc_14000F23B
0x14000f1a2  call    cs:__imp_GetLastError
0x14000f1a8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000f1af  mov     edi, eax
0x14000f1b1  test    rcx, rcx
0x14000f1b4  jz      short loc_14000F21B
0x14000f1b6  xor     edx, edx
0x14000f1b8  mov     [rbp+var_20], rbx
0x14000f1bc  lea     rax, [rbp+var_20]
0x14000f1c0  mov     [rsp+60h+var_38], rax
0x14000f1c5  lea     r9, aFailedToMoveTo_1; "Failed to move {} to {}."
0x14000f1cc  lea     rax, [rbp+lpExistingFileName]
0x14000f1d0  lea     r8d, [rdx+3]
0x14000f1d4  mov     qword ptr [rsp+60h+var_40], rax
0x14000f1d9  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x14000f1de  test    edi, edi
0x14000f1e0  jg      short loc_14000F1E6
0x14000f1e2  mov     eax, edi
0x14000f1e4  jmp     short loc_14000F1EE
0x14000f1e6  movzx   eax, di
0x14000f1e9  or      eax, 80070000h
0x14000f1ee  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000f1f5  lea     r9, a0; ": {0}"
0x14000f1fc  mov     [rbp+var_10], eax
0x14000f1ff  mov     r8d, 3
0x14000f205  lea     rax, [rbp+var_10]
0x14000f209  mov     qword ptr [rbp+var_30], rax
0x14000f20d  lea     rax, [rbp+var_30]
0x14000f211  mov     qword ptr [rsp+60h+var_40], rax; unsigned int
0x14000f216  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000f21b  test    edi, edi
0x14000f21d  jz      short loc_14000F23B
0x14000f21f  mov     rcx, [rbp+8]; this
0x14000f223  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x14000f22a  mov     r9d, edi; char *
0x14000f22d  mov     edx, 1FCh; void *
0x14000f232  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000f237  mov     ebx, eax
0x14000f239  jmp     short loc_14000F23D
0x14000f23b  xor     ebx, ebx
0x14000f23d  lea     rcx, [rbp+lpNewFileName]
0x14000f241  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14000f246  mov     eax, ebx
0x14000f248  mov     rcx, [rbp+var_8]
0x14000f24c  xor     rcx, rsp; StackCookie
0x14000f24f  call    __security_check_cookie
0x14000f254  lea     r11, [rsp+60h+var_s0]
0x14000f259  mov     rbx, [r11+20h]
0x14000f25d  mov     rdi, [r11+28h]
0x14000f261  mov     rsp, r11
0x14000f264  pop     rbp
0x14000f265  retn
```
