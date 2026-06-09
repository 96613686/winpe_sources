# PathGetWindowsDirectory

- ea: `0x18005ec58`
- end: `0x18005eee7`
- name: `PathGetWindowsDirectory`
- size: `655`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `22`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1800310d8`
- `0x18005b7e4`
- `0x180094320`
- `0x1800948fc`
- `0x1800beb18`
- `0x1800c03f0`
- `0x1800c7b40`
- `0x1800dc9c0`
- `0x1800f7290`
- `0x1800f7ba4`
- `0x1800f8048`
- `0x1801027b4`
- `0x1801519f0`
- `0x18015e4b8`
- `0x18015e9c0`
- `0x18018df84`
- `0x180191210`
- `0x1801c16b8`
- `0x1801c1794`
- `0x1801de2b8`
- `0x1801e80f4`
- `0x18029bc90`

## callees

- `0x180013250`
- `0x180016d40`
- `0x180033d50`
- `0x18005aa38`
- `0x18005ec58`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb500`
- `0x1800eb920`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ed08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005edde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ed08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005edde`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18005ecf2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18005edce`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18005ecf2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18005edce`

## string_xrefs

- `0x18005ed2a`: `Failed to get windows directory.`
- `0x18005edfd`: `Failed to get windows directory.`
- `0x18005eca7`: `No path result specified`
- `0x18005ed86`: `onecore\base\cbs\util\cbspath.cpp`
- `0x18005edb7`: `onecore\base\cbs\util\cbspath.cpp`

## pseudocode

```c
__int64 __fastcall PathGetWindowsDirectory(LPWSTR *a1, __int64 a2)
{
  unsigned int v4; // ebx
  __int64 v5; // r9
  __int64 v6; // rdx
  UINT SystemWindowsDirectoryW; // eax
  UINT v8; // esi
  signed int LastError; // ebx
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r9
  int v13; // eax
  UINT v14; // eax
  unsigned int v15; // eax
  const struct std::nothrow_t *v16; // rdx
  unsigned int v18; // [rsp+20h] [rbp-30h]
  LPWSTR lpBuffer; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v20[2]; // [rsp+38h] [rbp-18h] BYREF
  int v21; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  lpBuffer = 0;
  if ( !a1 )
  {
    v4 = -2147467261;
    v21 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No path result specified");
      *(_QWORD *)v20 = &v21;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v20);
    }
    v5 = 2147500035LL;
    v6 = 180;
    goto LABEL_18;
  }
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(0, 0);
  v8 = SystemWindowsDirectoryW;
  if ( SystemWindowsDirectoryW )
  {
    v13 = SczAlloc(&lpBuffer, SystemWindowsDirectoryW + 1);
    v4 = v13;
    if ( v13 < 0 )
    {
      v6 = 184;
LABEL_17:
      v5 = (unsigned int)v13;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v6,
        (unsigned int)"onecore\\base\\cbs\\util\\cbspath.cpp",
        (const char *)v5,
        v18);
      goto LABEL_36;
    }
    v14 = GetSystemWindowsDirectoryW(lpBuffer, v8);
    if ( v14 )
    {
      if ( v14 >= v8 )
      {
        v12 = 122;
        v11 = 192;
        goto LABEL_14;
      }
      SczEnsureBackslashTerminated(&lpBuffer);
      if ( !a2 )
      {
        if ( *a1 )
          operator delete(*a1 - 4, v16);
        *a1 = lpBuffer;
        lpBuffer = 0;
        goto LABEL_35;
      }
      v13 = SczAllocConcat2Sz(a1, lpBuffer, a2);
      v4 = v13;
      if ( v13 < 0 )
      {
        v6 = 198;
        goto LABEL_17;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get windows directory.");
        if ( LastError > 0 )
          v15 = (unsigned __int16)LastError | 0x80070000;
        else
          v15 = LastError;
        v21 = v15;
        *(_QWORD *)v20 = &v21;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v20);
      }
      if ( LastError )
      {
        v11 = 188;
        goto LABEL_13;
      }
    }
LABEL_35:
    v4 = 0;
    goto LABEL_36;
  }
  LastError = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get windows directory.");
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    else
      v10 = LastError;
    v21 = v10;
    *(_QWORD *)v20 = &v21;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {0}",
      (__int64)v20);
  }
  if ( !LastError )
    goto LABEL_35;
  v11 = 183;
LABEL_13:
  v12 = (unsigned int)LastError;
LABEL_14:
  v4 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)v11,
         (unsigned int)"onecore\\base\\cbs\\util\\cbspath.cpp",
         (const char *)v12,
         v18);
LABEL_36:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
  return v4;
}

```

## disassembly

```asm
0x18005ec58  mov     [rsp-18h+arg_10], rbx
0x18005ec5d  mov     [rsp-18h+arg_18], rsi
0x18005ec62  push    rbp
0x18005ec63  push    rdi
0x18005ec64  push    r14
0x18005ec66  mov     rbp, rsp
0x18005ec69  sub     rsp, 50h
0x18005ec6d  mov     rax, cs:__security_cookie
0x18005ec74  xor     rax, rsp
0x18005ec77  mov     [rbp+var_8], rax
0x18005ec7b  mov     [rbp+lpBuffer], 0
0x18005ec83  mov     r14, rdx
0x18005ec86  mov     rdi, rcx
0x18005ec89  test    rcx, rcx
0x18005ec8c  jnz     short loc_18005ECEE
0x18005ec8e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005ec95  mov     ebx, 80004003h
0x18005ec9a  mov     [rbp+var_10], ebx
0x18005ec9d  test    rcx, rcx
0x18005eca0  jz      short loc_18005ECE1
0x18005eca2  mov     edi, 3
0x18005eca7  lea     r9, aNoPathResultSp; "No path result specified"
0x18005ecae  mov     r8d, edi
0x18005ecb1  xor     edx, edx
0x18005ecb3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18005ecb8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005ecbf  lea     rax, [rbp+var_10]
0x18005ecc3  mov     qword ptr [rbp+var_18], rax
0x18005ecc7  lea     r9, asc_1802EE7AC; ": {}"
0x18005ecce  lea     rax, [rbp+var_18]
0x18005ecd2  mov     r8d, edi
0x18005ecd5  mov     dl, 1
0x18005ecd7  mov     qword ptr [rsp+50h+var_30], rax
0x18005ecdc  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005ece1  mov     r9d, ebx
0x18005ece4  mov     edx, 0B4h
0x18005ece9  jmp     loc_18005EDB3
0x18005ecee  xor     edx, edx; uSize
0x18005ecf0  xor     ecx, ecx; lpBuffer
0x18005ecf2  call    cs:__imp_GetSystemWindowsDirectoryW
0x18005ecf9  nop     dword ptr [rax+rax+00h]
0x18005ecfe  mov     esi, eax
0x18005ed00  test    eax, eax
0x18005ed02  jnz     loc_18005ED99
0x18005ed08  call    cs:__imp_GetLastError
0x18005ed0f  nop     dword ptr [rax+rax+00h]
0x18005ed14  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005ed1b  mov     ebx, eax
0x18005ed1d  test    rcx, rcx
0x18005ed20  jz      short loc_18005ED72
0x18005ed22  lea     edi, [rsi+3]
0x18005ed25  xor     edx, edx
0x18005ed27  mov     r8d, edi
0x18005ed2a  lea     r9, aFailedToGetWin_4; "Failed to get windows directory."
0x18005ed31  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18005ed36  test    ebx, ebx
0x18005ed38  jg      short loc_18005ED3E
0x18005ed3a  mov     eax, ebx
0x18005ed3c  jmp     short loc_18005ED46
0x18005ed3e  movzx   eax, bx
0x18005ed41  or      eax, 80070000h
0x18005ed46  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005ed4d  lea     r9, a0; ": {0}"
0x18005ed54  mov     [rbp+var_10], eax
0x18005ed57  mov     r8d, edi
0x18005ed5a  lea     rax, [rbp+var_10]
0x18005ed5e  mov     dl, 1
0x18005ed60  mov     qword ptr [rbp+var_18], rax
0x18005ed64  lea     rax, [rbp+var_18]
0x18005ed68  mov     qword ptr [rsp+50h+var_30], rax; unsigned int
0x18005ed6d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005ed72  test    ebx, ebx
0x18005ed74  jz      loc_18005EEB8
0x18005ed7a  mov     edx, 0B7h; void *
0x18005ed7f  mov     r9d, ebx; char *
0x18005ed82  mov     rcx, [rbp+18h]; this
0x18005ed86  lea     r8, aOnecoreBaseCbs_120; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x18005ed8d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005ed92  mov     ebx, eax
0x18005ed94  jmp     loc_18005EEBA
0x18005ed99  lea     edx, [rax+1]
0x18005ed9c  lea     rcx, [rbp+lpBuffer]
0x18005eda0  call    SczAlloc
0x18005eda5  mov     ebx, eax
0x18005eda7  test    eax, eax
0x18005eda9  jns     short loc_18005EDC8
0x18005edab  mov     edx, 0B8h; void *
0x18005edb0  mov     r9d, eax; char *
0x18005edb3  mov     rcx, [rbp+18h]; this
0x18005edb7  lea     r8, aOnecoreBaseCbs_120; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x18005edbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005edc3  jmp     loc_18005EEBA
0x18005edc8  mov     rcx, [rbp+lpBuffer]; lpBuffer
0x18005edcc  mov     edx, esi; uSize
0x18005edce  call    cs:__imp_GetSystemWindowsDirectoryW
0x18005edd5  nop     dword ptr [rax+rax+00h]
0x18005edda  test    eax, eax
0x18005eddc  jnz     short loc_18005EE58
0x18005edde  call    cs:__imp_GetLastError
0x18005ede5  nop     dword ptr [rax+rax+00h]
0x18005edea  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005edf1  mov     ebx, eax
0x18005edf3  test    rcx, rcx
0x18005edf6  jz      short loc_18005EE4A
0x18005edf8  mov     edi, 3
0x18005edfd  lea     r9, aFailedToGetWin_4; "Failed to get windows directory."
0x18005ee04  mov     r8d, edi
0x18005ee07  xor     edx, edx
0x18005ee09  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18005ee0e  test    ebx, ebx
0x18005ee10  jg      short loc_18005EE16
0x18005ee12  mov     eax, ebx
0x18005ee14  jmp     short loc_18005EE1E
0x18005ee16  movzx   eax, bx
0x18005ee19  or      eax, 80070000h
0x18005ee1e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005ee25  lea     r9, a0; ": {0}"
0x18005ee2c  mov     [rbp+var_10], eax
0x18005ee2f  mov     r8d, edi
0x18005ee32  lea     rax, [rbp+var_10]
0x18005ee36  mov     dl, 1
0x18005ee38  mov     qword ptr [rbp+var_18], rax
0x18005ee3c  lea     rax, [rbp+var_18]
0x18005ee40  mov     qword ptr [rsp+50h+var_30], rax
0x18005ee45  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005ee4a  test    ebx, ebx
0x18005ee4c  jz      short loc_18005EEB8
0x18005ee4e  mov     edx, 0BCh
0x18005ee53  jmp     loc_18005ED7F
0x18005ee58  cmp     eax, esi
0x18005ee5a  jb      short loc_18005EE6B
0x18005ee5c  mov     r9d, 7Ah ; 'z'
0x18005ee62  lea     edx, [r9+46h]
0x18005ee66  jmp     loc_18005ED82
0x18005ee6b  lea     rcx, [rbp+lpBuffer]
0x18005ee6f  call    SczEnsureBackslashTerminated
0x18005ee74  test    r14, r14
0x18005ee77  jz      short loc_18005EE98
0x18005ee79  mov     rdx, [rbp+lpBuffer]
0x18005ee7d  mov     r8, r14
0x18005ee80  mov     rcx, rdi
0x18005ee83  call    SczAllocConcat2Sz
0x18005ee88  mov     ebx, eax
0x18005ee8a  test    eax, eax
0x18005ee8c  jns     short loc_18005EEB8
0x18005ee8e  mov     edx, 0C6h
0x18005ee93  jmp     loc_18005EDB0
0x18005ee98  mov     rcx, [rdi]
0x18005ee9b  test    rcx, rcx
0x18005ee9e  jz      short loc_18005EEA9
0x18005eea0  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x18005eea4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005eea9  mov     rax, [rbp+lpBuffer]
0x18005eead  mov     [rdi], rax
0x18005eeb0  mov     [rbp+lpBuffer], 0
0x18005eeb8  xor     ebx, ebx
0x18005eeba  lea     rcx, [rbp+lpBuffer]
0x18005eebe  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18005eec3  mov     eax, ebx
0x18005eec5  mov     rcx, [rbp+var_8]
0x18005eec9  xor     rcx, rsp; StackCookie
0x18005eecc  call    __security_check_cookie
0x18005eed1  lea     r11, [rsp+50h+var_s0]
0x18005eed6  mov     rbx, [r11+30h]
0x18005eeda  mov     rsi, [r11+38h]
0x18005eede  mov     rsp, r11
0x18005eee1  pop     r14
0x18005eee3  pop     rdi
0x18005eee4  pop     rbp
0x18005eee5  retn
```
