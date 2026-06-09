# PathGetWindowsDirectory

- ea: `0x140016d8c`
- end: `0x140016ffc`
- name: `PathGetWindowsDirectory`
- size: `624`
- prototype: `__int64 __fastcall(LPWSTR *, __int64)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x14000ed6c`
- `0x14000f5b0`
- `0x140012678`

## callees

- `0x140002310`
- `0x1400025a4`
- `0x1400053c0`
- `0x140006514`
- `0x140008d38`
- `0x140008ef4`
- `0x14000f36c`
- `0x140016d8c`
- `0x14001726c`
- `0x140017464`
- `0x140018740`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016e34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016efc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016e34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016efc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x140016e24`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x140016ef2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x140016e24`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x140016ef2`

## string_xrefs

- `0x140016e50`: `Failed to get windows directory.`
- `0x140016f15`: `Failed to get windows directory.`
- `0x140016eaa`: `onecore\base\cbs\util\cbspath.cpp`
- `0x140016edb`: `onecore\base\cbs\util\cbspath.cpp`
- `0x140016ddb`: `No path result specified`

## pseudocode

```c
__int64 __fastcall PathGetWindowsDirectory(LPWSTR *a1, __int64 a2)
{
  unsigned int v4; // ebx
  int v5; // edx
  __int64 v6; // r9
  __int64 v7; // rdx
  UINT SystemWindowsDirectoryW; // eax
  UINT v9; // esi
  signed int LastError; // ebx
  int v11; // edx
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r9
  int v15; // eax
  UINT v16; // eax
  int v17; // edx
  unsigned int v18; // eax
  const struct std::nothrow_t *v19; // rdx
  unsigned int v21; // [rsp+20h] [rbp-30h]
  LPWSTR lpBuffer; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v23[2]; // [rsp+38h] [rbp-18h] BYREF
  int v24; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  lpBuffer = 0;
  if ( !a1 )
  {
    v4 = -2147467261;
    v24 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No path result specified");
      *(_QWORD *)v23 = &v24;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v5,
        3,
        (unsigned int)": {}",
        (__int64)v23);
    }
    v6 = 2147500035LL;
    v7 = 180;
    goto LABEL_18;
  }
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(0, 0);
  v9 = SystemWindowsDirectoryW;
  if ( SystemWindowsDirectoryW )
  {
    v15 = SczAlloc(&lpBuffer, SystemWindowsDirectoryW + 1);
    v4 = v15;
    if ( v15 < 0 )
    {
      v7 = 184;
LABEL_17:
      v6 = (unsigned int)v15;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecore\\base\\cbs\\util\\cbspath.cpp",
        (const char *)v6,
        v21);
      goto LABEL_36;
    }
    v16 = GetSystemWindowsDirectoryW(lpBuffer, v9);
    if ( v16 )
    {
      if ( v16 >= v9 )
      {
        v14 = 122;
        v13 = 192;
        goto LABEL_14;
      }
      SczEnsureBackslashTerminated(&lpBuffer);
      if ( !a2 )
      {
        if ( *a1 )
          operator delete(*a1 - 4, v19);
        *a1 = lpBuffer;
        lpBuffer = 0;
        goto LABEL_35;
      }
      v15 = SczAllocConcat2Sz(a1, lpBuffer, a2);
      v4 = v15;
      if ( v15 < 0 )
      {
        v7 = 198;
        goto LABEL_17;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get windows directory.");
        if ( LastError > 0 )
          v18 = (unsigned __int16)LastError | 0x80070000;
        else
          v18 = LastError;
        v24 = v18;
        *(_QWORD *)v23 = &v24;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v17,
          3,
          (unsigned int)": {0}",
          (__int64)v23);
      }
      if ( LastError )
      {
        v13 = 188;
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
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, v9 + 3, "Failed to get windows directory.");
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    else
      v12 = LastError;
    v24 = v12;
    *(_QWORD *)v23 = &v24;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v11,
      v9 + 3,
      (unsigned int)": {0}",
      (__int64)v23);
  }
  if ( !LastError )
    goto LABEL_35;
  v13 = 183;
LABEL_13:
  v14 = (unsigned int)LastError;
LABEL_14:
  v4 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)v13,
         (unsigned int)"onecore\\base\\cbs\\util\\cbspath.cpp",
         (const char *)v14,
         v21);
LABEL_36:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
  return v4;
}

```

## disassembly

```asm
0x140016d8c  mov     [rsp-18h+arg_10], rbx
0x140016d91  mov     [rsp-18h+arg_18], rsi
0x140016d96  push    rbp
0x140016d97  push    rdi
0x140016d98  push    r14
0x140016d9a  mov     rbp, rsp
0x140016d9d  sub     rsp, 50h
0x140016da1  mov     rax, cs:__security_cookie
0x140016da8  xor     rax, rsp
0x140016dab  mov     [rbp+var_8], rax
0x140016daf  mov     [rbp+lpBuffer], 0
0x140016db7  mov     r14, rdx
0x140016dba  mov     rdi, rcx
0x140016dbd  test    rcx, rcx
0x140016dc0  jnz     short loc_140016E20
0x140016dc2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016dc9  mov     ebx, 80004003h
0x140016dce  mov     [rbp+var_10], ebx
0x140016dd1  test    rcx, rcx
0x140016dd4  jz      short loc_140016E13
0x140016dd6  mov     edi, 3
0x140016ddb  lea     r9, aNoPathResultSp; "No path result specified"
0x140016de2  mov     r8d, edi
0x140016de5  xor     edx, edx
0x140016de7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140016dec  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016df3  lea     rax, [rbp+var_10]
0x140016df7  mov     qword ptr [rbp+var_18], rax
0x140016dfb  lea     r9, asc_140030534; ": {}"
0x140016e02  lea     rax, [rbp+var_18]
0x140016e06  mov     r8d, edi
0x140016e09  mov     qword ptr [rsp+50h+var_30], rax
0x140016e0e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140016e13  mov     r9d, ebx
0x140016e16  mov     edx, 0B4h
0x140016e1b  jmp     loc_140016ED7
0x140016e20  xor     edx, edx; uSize
0x140016e22  xor     ecx, ecx; lpBuffer
0x140016e24  call    cs:__imp_GetSystemWindowsDirectoryW
0x140016e2a  mov     esi, eax
0x140016e2c  test    eax, eax
0x140016e2e  jnz     loc_140016EBD
0x140016e34  call    cs:__imp_GetLastError
0x140016e3a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016e41  mov     ebx, eax
0x140016e43  test    rcx, rcx
0x140016e46  jz      short loc_140016E96
0x140016e48  lea     edi, [rsi+3]
0x140016e4b  xor     edx, edx
0x140016e4d  mov     r8d, edi
0x140016e50  lea     r9, aFailedToGetWin_0; "Failed to get windows directory."
0x140016e57  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140016e5c  test    ebx, ebx
0x140016e5e  jg      short loc_140016E64
0x140016e60  mov     eax, ebx
0x140016e62  jmp     short loc_140016E6C
0x140016e64  movzx   eax, bx
0x140016e67  or      eax, 80070000h
0x140016e6c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016e73  lea     r9, a0; ": {0}"
0x140016e7a  mov     [rbp+var_10], eax
0x140016e7d  mov     r8d, edi
0x140016e80  lea     rax, [rbp+var_10]
0x140016e84  mov     qword ptr [rbp+var_18], rax
0x140016e88  lea     rax, [rbp+var_18]
0x140016e8c  mov     qword ptr [rsp+50h+var_30], rax; unsigned int
0x140016e91  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140016e96  test    ebx, ebx
0x140016e98  jz      loc_140016FCE
0x140016e9e  mov     edx, 0B7h; void *
0x140016ea3  mov     r9d, ebx; char *
0x140016ea6  mov     rcx, [rbp+18h]; this
0x140016eaa  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x140016eb1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140016eb6  mov     ebx, eax
0x140016eb8  jmp     loc_140016FD0
0x140016ebd  lea     edx, [rax+1]
0x140016ec0  lea     rcx, [rbp+lpBuffer]
0x140016ec4  call    SczAlloc
0x140016ec9  mov     ebx, eax
0x140016ecb  test    eax, eax
0x140016ecd  jns     short loc_140016EEC
0x140016ecf  mov     edx, 0B8h; void *
0x140016ed4  mov     r9d, eax; char *
0x140016ed7  mov     rcx, [rbp+18h]; this
0x140016edb  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x140016ee2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016ee7  jmp     loc_140016FD0
0x140016eec  mov     rcx, [rbp+lpBuffer]; lpBuffer
0x140016ef0  mov     edx, esi; uSize
0x140016ef2  call    cs:__imp_GetSystemWindowsDirectoryW
0x140016ef8  test    eax, eax
0x140016efa  jnz     short loc_140016F6E
0x140016efc  call    cs:__imp_GetLastError
0x140016f02  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016f09  mov     ebx, eax
0x140016f0b  test    rcx, rcx
0x140016f0e  jz      short loc_140016F60
0x140016f10  mov     edi, 3
0x140016f15  lea     r9, aFailedToGetWin_0; "Failed to get windows directory."
0x140016f1c  mov     r8d, edi
0x140016f1f  xor     edx, edx
0x140016f21  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140016f26  test    ebx, ebx
0x140016f28  jg      short loc_140016F2E
0x140016f2a  mov     eax, ebx
0x140016f2c  jmp     short loc_140016F36
0x140016f2e  movzx   eax, bx
0x140016f31  or      eax, 80070000h
0x140016f36  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016f3d  lea     r9, a0; ": {0}"
0x140016f44  mov     [rbp+var_10], eax
0x140016f47  mov     r8d, edi
0x140016f4a  lea     rax, [rbp+var_10]
0x140016f4e  mov     qword ptr [rbp+var_18], rax
0x140016f52  lea     rax, [rbp+var_18]
0x140016f56  mov     qword ptr [rsp+50h+var_30], rax
0x140016f5b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140016f60  test    ebx, ebx
0x140016f62  jz      short loc_140016FCE
0x140016f64  mov     edx, 0BCh
0x140016f69  jmp     loc_140016EA3
0x140016f6e  cmp     eax, esi
0x140016f70  jb      short loc_140016F81
0x140016f72  mov     r9d, 7Ah ; 'z'
0x140016f78  lea     edx, [r9+46h]
0x140016f7c  jmp     loc_140016EA6
0x140016f81  lea     rcx, [rbp+lpBuffer]
0x140016f85  call    SczEnsureBackslashTerminated
0x140016f8a  test    r14, r14
0x140016f8d  jz      short loc_140016FAE
0x140016f8f  mov     rdx, [rbp+lpBuffer]
0x140016f93  mov     r8, r14
0x140016f96  mov     rcx, rdi
0x140016f99  call    SczAllocConcat2Sz
0x140016f9e  mov     ebx, eax
0x140016fa0  test    eax, eax
0x140016fa2  jns     short loc_140016FCE
0x140016fa4  mov     edx, 0C6h
0x140016fa9  jmp     loc_140016ED4
0x140016fae  mov     rcx, [rdi]
0x140016fb1  test    rcx, rcx
0x140016fb4  jz      short loc_140016FBF
0x140016fb6  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x140016fba  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140016fbf  mov     rax, [rbp+lpBuffer]
0x140016fc3  mov     [rdi], rax
0x140016fc6  mov     [rbp+lpBuffer], 0
0x140016fce  xor     ebx, ebx
0x140016fd0  lea     rcx, [rbp+lpBuffer]
0x140016fd4  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140016fd9  mov     eax, ebx
0x140016fdb  mov     rcx, [rbp+var_8]
0x140016fdf  xor     rcx, rsp; StackCookie
0x140016fe2  call    __security_check_cookie
0x140016fe7  lea     r11, [rsp+50h+var_s0]
0x140016fec  mov     rbx, [r11+30h]
0x140016ff0  mov     rsi, [r11+38h]
0x140016ff4  mov     rsp, r11
0x140016ff7  pop     r14
0x140016ff9  pop     rdi
0x140016ffa  pop     rbp
0x140016ffb  retn
```
