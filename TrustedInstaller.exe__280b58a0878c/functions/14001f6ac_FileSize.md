# FileSize

- ea: `0x14001f6ac`
- end: `0x14001f878`
- name: `FileSize`
- size: `460`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x140018630`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140016a40`
- `0x140016bfc`
- `0x140016fb4`
- `0x1400184fc`
- `0x14001f6ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f7c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f7c5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x14001f7b7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x14001f7b7`

## string_xrefs

- `0x14001f6fa`: `No file path specified`

## pseudocode

```c
int __fastcall FileSize(const WCHAR *a1, unsigned __int64 *a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // rdx
  __int64 v7; // rdx
  __int64 v8; // rdx
  signed int LastError; // ebx
  __int64 v10; // r8
  __int64 v11; // rdx
  unsigned int v12; // eax
  unsigned int v13; // [rsp+20h] [rbp-60h]
  unsigned int v14[2]; // [rsp+30h] [rbp-50h] BYREF
  const WCHAR *v15; // [rsp+38h] [rbp-48h] BYREF
  int v16; // [rsp+40h] [rbp-40h] BYREF
  __int128 FileInformation; // [rsp+48h] [rbp-38h] BYREF
  __int128 v18; // [rsp+58h] [rbp-28h]
  unsigned int v19; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v15 = a1;
  v19 = 0;
  FileInformation = 0;
  v18 = 0;
  if ( !a1 )
  {
    v3 = -2147024809;
    v16 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No file path specified");
      *(_QWORD *)v14 = &v16;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v4,
        3,
        (__int64)": {}",
        (__int64)v14);
    }
    v5 = 230;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)v3,
      v13);
    return v3;
  }
  if ( !a2 )
  {
    v3 = -2147467261;
    v16 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No file size result specified");
      *(_QWORD *)v14 = &v16;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v7,
        3,
        (__int64)": {}",
        (__int64)v14);
    }
    v5 = 231;
    goto LABEL_5;
  }
  if ( GetFileAttributesExW(a1, GetFileExInfoStandard, &FileInformation) )
  {
    *a2 = v19 | ((unsigned __int64)HIDWORD(v18) << 32);
  }
  else
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        v8,
        v10,
        (__int64)"Failed to get attributes for file: {}",
        (__int64)&v15);
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      else
        v12 = LastError;
      v16 = v12;
      *(_QWORD *)v14 = &v16;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v11,
        3,
        (__int64)": {0}",
        (__int64)v14);
    }
    if ( LastError )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xEA,
               (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
               (const char *)(unsigned int)LastError,
               v13);
  }
  return 0;
}

```

## disassembly

```asm
0x14001f6ac  mov     [rsp-8+arg_10], rbx
0x14001f6b1  push    rbp
0x14001f6b2  mov     rbp, rsp
0x14001f6b5  sub     rsp, 80h
0x14001f6bc  mov     rax, cs:__security_cookie
0x14001f6c3  xor     rax, rsp
0x14001f6c6  mov     [rbp+var_10], rax
0x14001f6ca  xor     eax, eax
0x14001f6cc  mov     [rbp+var_48], rcx
0x14001f6d0  mov     [rbp+var_18], eax
0x14001f6d3  xorps   xmm0, xmm0
0x14001f6d6  mov     rbx, rdx
0x14001f6d9  movups  [rbp+FileInformation], xmm0
0x14001f6dd  movups  [rbp+var_28], xmm0
0x14001f6e1  test    rcx, rcx
0x14001f6e4  jnz     short loc_14001F755
0x14001f6e6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001f6ed  mov     ebx, 80070057h
0x14001f6f2  mov     [rbp+var_40], ebx
0x14001f6f5  test    rcx, rcx
0x14001f6f8  jz      short loc_14001F736
0x14001f6fa  lea     r9, aNoFilePathSpec; "No file path specified"
0x14001f701  xor     edx, edx
0x14001f703  lea     r8d, [rax+3]
0x14001f707  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001f70c  lea     rcx, [rbp+var_50]
0x14001f710  mov     r8d, 3
0x14001f716  mov     qword ptr [rsp+80h+var_60], rcx; int
0x14001f71b  lea     rax, [rbp+var_40]
0x14001f71f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001f726  lea     r9, asc_1400353E8; ": {}"
0x14001f72d  mov     qword ptr [rbp+var_50], rax
0x14001f731  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001f736  mov     edx, 0E6h; void *
0x14001f73b  mov     rcx, [rbp+8]; this
0x14001f73f  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x14001f746  mov     r9d, ebx; char *
0x14001f749  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001f74e  mov     eax, ebx
0x14001f750  jmp     loc_14001F85B
0x14001f755  test    rbx, rbx
0x14001f758  jnz     short loc_14001F7B1
0x14001f75a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001f761  mov     ebx, 80004003h
0x14001f766  mov     [rbp+var_40], ebx
0x14001f769  test    rcx, rcx
0x14001f76c  jz      short loc_14001F7AA
0x14001f76e  xor     edx, edx
0x14001f770  lea     r9, aNoFileSizeResu; "No file size result specified"
0x14001f777  lea     r8d, [rdx+3]
0x14001f77b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001f780  lea     rcx, [rbp+var_50]
0x14001f784  mov     r8d, 3
0x14001f78a  mov     qword ptr [rsp+80h+var_60], rcx
0x14001f78f  lea     rax, [rbp+var_40]
0x14001f793  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001f79a  lea     r9, asc_1400353E8; ": {}"
0x14001f7a1  mov     qword ptr [rbp+var_50], rax
0x14001f7a5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001f7aa  mov     edx, 0E7h
0x14001f7af  jmp     short loc_14001F73B
0x14001f7b1  lea     r8, [rbp+FileInformation]; lpFileInformation
0x14001f7b5  xor     edx, edx; fInfoLevelId
0x14001f7b7  call    cs:__imp_GetFileAttributesExW
0x14001f7bd  test    eax, eax
0x14001f7bf  jnz     loc_14001F849
0x14001f7c5  call    cs:__imp_GetLastError
0x14001f7cb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001f7d2  mov     ebx, eax
0x14001f7d4  test    rcx, rcx
0x14001f7d7  jz      short loc_14001F82B
0x14001f7d9  lea     rax, [rbp+var_48]
0x14001f7dd  lea     r9, aFailedToGetAtt; "Failed to get attributes for file: {}"
0x14001f7e4  mov     qword ptr [rsp+80h+var_60], rax
0x14001f7e9  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001f7ee  test    ebx, ebx
0x14001f7f0  jg      short loc_14001F7F6
0x14001f7f2  mov     eax, ebx
0x14001f7f4  jmp     short loc_14001F7FE
0x14001f7f6  movzx   eax, bx
0x14001f7f9  or      eax, 80070000h
0x14001f7fe  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001f805  lea     r9, a0; ": {0}"
0x14001f80c  mov     [rbp+var_40], eax
0x14001f80f  mov     r8d, 3
0x14001f815  lea     rax, [rbp+var_40]
0x14001f819  mov     qword ptr [rbp+var_50], rax
0x14001f81d  lea     rax, [rbp+var_50]
0x14001f821  mov     qword ptr [rsp+80h+var_60], rax; unsigned int
0x14001f826  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001f82b  test    ebx, ebx
0x14001f82d  jz      short loc_14001F859
0x14001f82f  mov     rcx, [rbp+8]; this
0x14001f833  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x14001f83a  mov     r9d, ebx; char *
0x14001f83d  mov     edx, 0EAh; void *
0x14001f842  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14001f847  jmp     short loc_14001F85B
0x14001f849  mov     ecx, dword ptr [rbp+var_28+0Ch]
0x14001f84c  mov     eax, [rbp+var_18]
0x14001f84f  shl     rcx, 20h
0x14001f853  or      rcx, rax
0x14001f856  mov     [rbx], rcx
0x14001f859  xor     eax, eax
0x14001f85b  mov     rcx, [rbp+var_10]
0x14001f85f  xor     rcx, rsp; StackCookie
0x14001f862  call    __security_check_cookie
0x14001f867  mov     rbx, [rsp+80h+arg_10]
0x14001f86f  add     rsp, 80h
0x14001f876  pop     rbp
0x14001f877  retn
```
