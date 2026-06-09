# FileSize

- ea: `0x140014d18`
- end: `0x140014eea`
- name: `FileSize`
- size: `466`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x14000f5b0`

## callees

- `0x140002310`
- `0x1400053c0`
- `0x140008d38`
- `0x140008ef4`
- `0x14000d910`
- `0x14000f36c`
- `0x140014d18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014e31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014e31`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x140014e23`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x140014e23`

## string_xrefs

- `0x140014d66`: `No file path specified`

## pseudocode

```c
__int64 __fastcall FileSize(const WCHAR *a1, unsigned __int64 *a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // rdx
  __int64 v7; // rdx
  signed int LastError; // ebx
  __int64 v9; // rdx
  unsigned int v10; // eax
  unsigned int v11[2]; // [rsp+30h] [rbp-50h] BYREF
  const WCHAR *v12; // [rsp+38h] [rbp-48h] BYREF
  int v13; // [rsp+40h] [rbp-40h] BYREF
  __int128 FileInformation; // [rsp+48h] [rbp-38h] BYREF
  __int128 v15; // [rsp+58h] [rbp-28h]
  unsigned int v16; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v12 = a1;
  v16 = 0;
  FileInformation = 0;
  v15 = 0;
  if ( !a1 )
  {
    v3 = -2147024809;
    v13 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No file path specified");
      *(_QWORD *)v11 = &v13;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v4,
        3,
        (__int64)": {}",
        (__int64)v11);
    }
    v5 = 230;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)v3);
    return v3;
  }
  if ( !a2 )
  {
    v3 = -2147467261;
    v13 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No file size result specified");
      *(_QWORD *)v11 = &v13;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v7,
        3,
        (__int64)": {}",
        (__int64)v11);
    }
    v5 = 231;
    goto LABEL_5;
  }
  if ( GetFileAttributesExW(a1, GetFileExInfoStandard, &FileInformation) )
  {
    *a2 = v16 | ((unsigned __int64)HIDWORD(v15) << 32);
  }
  else
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed to get attributes for file: {}",
        (__int64)&v12);
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      else
        v10 = LastError;
      v13 = v10;
      *(_QWORD *)v11 = &v13;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v9,
        3,
        (__int64)": {0}",
        (__int64)v11);
    }
    if ( LastError )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xEA,
               (int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
               (const char *)(unsigned int)LastError);
  }
  return 0;
}

```

## disassembly

```asm
0x140014d18  mov     [rsp-8+arg_10], rbx
0x140014d1d  push    rbp
0x140014d1e  mov     rbp, rsp
0x140014d21  sub     rsp, 80h
0x140014d28  mov     rax, cs:__security_cookie
0x140014d2f  xor     rax, rsp
0x140014d32  mov     [rbp+var_10], rax
0x140014d36  xor     eax, eax
0x140014d38  mov     [rbp+var_48], rcx
0x140014d3c  mov     [rbp+var_18], eax
0x140014d3f  xorps   xmm0, xmm0
0x140014d42  mov     rbx, rdx
0x140014d45  movups  [rbp+FileInformation], xmm0
0x140014d49  movups  [rbp+var_28], xmm0
0x140014d4d  test    rcx, rcx
0x140014d50  jnz     short loc_140014DC1
0x140014d52  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140014d59  mov     ebx, 80070057h
0x140014d5e  mov     [rbp+var_40], ebx
0x140014d61  test    rcx, rcx
0x140014d64  jz      short loc_140014DA2
0x140014d66  lea     r9, aNoFilePathSpec; "No file path specified"
0x140014d6d  xor     edx, edx
0x140014d6f  lea     r8d, [rax+3]
0x140014d73  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140014d78  lea     rcx, [rbp+var_50]
0x140014d7c  mov     r8d, 3
0x140014d82  mov     qword ptr [rsp+80h+var_60], rcx; int
0x140014d87  lea     rax, [rbp+var_40]
0x140014d8b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140014d92  lea     r9, asc_140030534; ": {}"
0x140014d99  mov     qword ptr [rbp+var_50], rax
0x140014d9d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140014da2  mov     edx, 0E6h; void *
0x140014da7  mov     rcx, [rbp+8]; this
0x140014dab  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x140014db2  mov     r9d, ebx; char *
0x140014db5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014dba  mov     eax, ebx
0x140014dbc  jmp     loc_140014ECD
0x140014dc1  test    rbx, rbx
0x140014dc4  jnz     short loc_140014E1D
0x140014dc6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140014dcd  mov     ebx, 80004003h
0x140014dd2  mov     [rbp+var_40], ebx
0x140014dd5  test    rcx, rcx
0x140014dd8  jz      short loc_140014E16
0x140014dda  xor     edx, edx
0x140014ddc  lea     r9, aNoFileSizeResu; "No file size result specified"
0x140014de3  lea     r8d, [rdx+3]
0x140014de7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140014dec  lea     rcx, [rbp+var_50]
0x140014df0  mov     r8d, 3
0x140014df6  mov     qword ptr [rsp+80h+var_60], rcx
0x140014dfb  lea     rax, [rbp+var_40]
0x140014dff  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140014e06  lea     r9, asc_140030534; ": {}"
0x140014e0d  mov     qword ptr [rbp+var_50], rax
0x140014e11  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140014e16  mov     edx, 0E7h
0x140014e1b  jmp     short loc_140014DA7
0x140014e1d  lea     r8, [rbp+FileInformation]; lpFileInformation
0x140014e21  xor     edx, edx; fInfoLevelId
0x140014e23  call    cs:__imp_GetFileAttributesExW
0x140014e29  test    eax, eax
0x140014e2b  jnz     loc_140014EBB
0x140014e31  call    cs:__imp_GetLastError
0x140014e37  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140014e3e  mov     ebx, eax
0x140014e40  test    rcx, rcx
0x140014e43  jz      short loc_140014E9D
0x140014e45  xor     edx, edx
0x140014e47  lea     rax, [rbp+var_48]
0x140014e4b  lea     r9, aFailedToGetAtt; "Failed to get attributes for file: {}"
0x140014e52  mov     qword ptr [rsp+80h+var_60], rax
0x140014e57  lea     r8d, [rdx+3]
0x140014e5b  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140014e60  test    ebx, ebx
0x140014e62  jg      short loc_140014E68
0x140014e64  mov     eax, ebx
0x140014e66  jmp     short loc_140014E70
0x140014e68  movzx   eax, bx
0x140014e6b  or      eax, 80070000h
0x140014e70  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140014e77  lea     r9, a0; ": {0}"
0x140014e7e  mov     [rbp+var_40], eax
0x140014e81  mov     r8d, 3
0x140014e87  lea     rax, [rbp+var_40]
0x140014e8b  mov     qword ptr [rbp+var_50], rax
0x140014e8f  lea     rax, [rbp+var_50]
0x140014e93  mov     qword ptr [rsp+80h+var_60], rax; unsigned int
0x140014e98  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140014e9d  test    ebx, ebx
0x140014e9f  jz      short loc_140014ECB
0x140014ea1  mov     rcx, [rbp+8]; this
0x140014ea5  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x140014eac  mov     r9d, ebx; char *
0x140014eaf  mov     edx, 0EAh; void *
0x140014eb4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140014eb9  jmp     short loc_140014ECD
0x140014ebb  mov     ecx, dword ptr [rbp+var_28+0Ch]
0x140014ebe  mov     eax, [rbp+var_18]
0x140014ec1  shl     rcx, 20h
0x140014ec5  or      rcx, rax
0x140014ec8  mov     [rbx], rcx
0x140014ecb  xor     eax, eax
0x140014ecd  mov     rcx, [rbp+var_10]
0x140014ed1  xor     rcx, rsp; StackCookie
0x140014ed4  call    __security_check_cookie
0x140014ed9  mov     rbx, [rsp+80h+arg_10]
0x140014ee1  add     rsp, 80h
0x140014ee8  pop     rbp
0x140014ee9  retn
```
