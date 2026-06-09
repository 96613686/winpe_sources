# PathGetWindowsDirectory

- ea: `0x180046050`
- end: `0x18004633f`
- name: `PathGetWindowsDirectory`
- size: `751`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x1800375fc`
- `0x18003f8a4`
- `0x18011352c`
- `0x180182df0`
- `0x1801acf20`

## callees

- `0x1800031d0`
- `0x1800062b8`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x1800296a4`
- `0x18003cbbc`
- `0x18003cd78`
- `0x18003e9cc`
- `0x180046050`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800460fa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800461ef`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800460fa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800461ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046110`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046203`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046110`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046203`

## string_xrefs

- `0x1800460a2`: `No path result specified`
- `0x18004612f`: `Failed to get windows directory.`
- `0x180046222`: `Failed to get windows directory.`
- `0x1800460db`: `onecore\base\cbs\util\cbspath.cpp`
- `0x180046188`: `onecore\base\cbs\util\cbspath.cpp`
- `0x1800461b7`: `onecore\base\cbs\util\cbspath.cpp`
- `0x180046283`: `onecore\base\cbs\util\cbspath.cpp`
- `0x1800462dd`: `onecore\base\cbs\util\cbspath.cpp`

## pseudocode

```c
int __fastcall PathGetWindowsDirectory(LPWSTR *a1, __int64 a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  UINT SystemWindowsDirectoryW; // eax
  UINT v8; // esi
  signed int LastError; // ebx
  __int64 v10; // rdx
  unsigned int v11; // eax
  int v12; // eax
  LPWSTR v13; // rbx
  UINT v14; // eax
  signed int v15; // edi
  __int64 v16; // rdx
  unsigned int v17; // eax
  __int64 v18; // r9
  __int64 v19; // rdx
  int v20; // edi
  int v21; // eax
  unsigned int *v22; // [rsp+20h] [rbp-30h]
  unsigned int v23[2]; // [rsp+30h] [rbp-20h] BYREF
  LPWSTR lpBuffer; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  lpBuffer = 0;
  if ( !a1 )
  {
    v4 = -2147467261;
    LODWORD(lpBuffer) = -2147467261;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "No path result specified");
      *(_QWORD *)v23 = &lpBuffer;
      LOBYTE(v5) = 1;
      v22 = v23;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v5,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB4,
      (unsigned int)"onecore\\base\\cbs\\util\\cbspath.cpp",
      (const char *)0x80004003LL,
      (int)v22);
    return v4;
  }
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(0, 0);
  v8 = SystemWindowsDirectoryW;
  if ( !SystemWindowsDirectoryW )
  {
    LastError = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get windows directory.");
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      else
        v11 = LastError;
      LODWORD(lpBuffer) = v11;
      LOBYTE(v10) = 1;
      *(_QWORD *)v23 = &lpBuffer;
      v22 = v23;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v10,
        3,
        ": {0}");
    }
    if ( LastError )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xB7,
               (unsigned int)"onecore\\base\\cbs\\util\\cbspath.cpp",
               (const char *)(unsigned int)LastError,
               (unsigned int)v22);
    return 0;
  }
  v12 = SczAlloc(&lpBuffer, SystemWindowsDirectoryW + 1);
  v4 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecore\\base\\cbs\\util\\cbspath.cpp",
      (const char *)(unsigned int)v12,
      (int)v22);
    if ( lpBuffer )
      operator delete(lpBuffer - 4);
    return v4;
  }
  v13 = lpBuffer;
  v14 = GetSystemWindowsDirectoryW(lpBuffer, v8);
  if ( v14 )
  {
    if ( v14 >= v8 )
    {
      v18 = 122;
      v19 = 192;
      goto LABEL_25;
    }
    SczEnsureBackslashTerminated(&lpBuffer);
    if ( a2 )
    {
      v13 = lpBuffer;
      v21 = SczAllocConcat2Sz(a1, lpBuffer, a2);
      v20 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC6,
          (unsigned int)"onecore\\base\\cbs\\util\\cbspath.cpp",
          (const char *)(unsigned int)v21,
          (int)v22);
        goto LABEL_26;
      }
    }
    else
    {
      if ( *a1 )
        operator delete(*a1 - 4);
      v13 = 0;
      *a1 = lpBuffer;
    }
LABEL_37:
    if ( v13 )
      operator delete(v13 - 4);
    return 0;
  }
  v15 = GetLastError();
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get windows directory.");
    if ( v15 > 0 )
      v17 = (unsigned __int16)v15 | 0x80070000;
    else
      v17 = v15;
    LODWORD(lpBuffer) = v17;
    LOBYTE(v16) = 1;
    *(_QWORD *)v23 = &lpBuffer;
    v22 = v23;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v16,
      3,
      ": {0}");
  }
  if ( !v15 )
    goto LABEL_37;
  v18 = (unsigned int)v15;
  v19 = 188;
LABEL_25:
  v20 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)v19,
          (unsigned int)"onecore\\base\\cbs\\util\\cbspath.cpp",
          (const char *)v18,
          (unsigned int)v22);
LABEL_26:
  if ( v13 )
    operator delete(v13 - 4);
  return v20;
}

```

## disassembly

```asm
0x180046050  mov     [rsp-18h+arg_10], rbx
0x180046055  mov     [rsp-18h+arg_18], rsi
0x18004605a  push    rbp
0x18004605b  push    rdi
0x18004605c  push    r14
0x18004605e  mov     rbp, rsp
0x180046061  sub     rsp, 50h
0x180046065  mov     rax, cs:__security_cookie
0x18004606c  xor     rax, rsp
0x18004606f  mov     [rbp+var_10], rax
0x180046073  mov     [rbp+lpBuffer], 0
0x18004607b  mov     r14, rdx
0x18004607e  mov     rdi, rcx
0x180046081  test    rcx, rcx
0x180046084  jnz     short loc_1800460F6
0x180046086  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004608d  mov     ebx, 80004003h
0x180046092  mov     dword ptr [rbp+lpBuffer], ebx
0x180046095  test    rcx, rcx
0x180046098  jz      short loc_1800460D7
0x18004609a  lea     esi, [rdi+3]
0x18004609d  xor     edx, edx
0x18004609f  mov     r8d, esi
0x1800460a2  lea     r9, aNoPathResultSp; "No path result specified"
0x1800460a9  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800460ae  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800460b5  lea     rax, [rbp+lpBuffer]
0x1800460b9  mov     qword ptr [rbp+var_20], rax
0x1800460bd  lea     r9, asc_1801CAFB4; ": {}"
0x1800460c4  lea     rax, [rbp+var_20]
0x1800460c8  mov     r8d, esi
0x1800460cb  mov     dl, 1
0x1800460cd  mov     qword ptr [rsp+50h+var_30], rax; int
0x1800460d2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800460d7  mov     rcx, [rbp+18h]; this
0x1800460db  lea     r8, aOnecoreBaseCbs_15; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x1800460e2  mov     r9d, ebx; char *
0x1800460e5  mov     edx, 0B4h; void *
0x1800460ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800460ef  mov     eax, ebx
0x1800460f1  jmp     loc_18004631D
0x1800460f6  xor     edx, edx; uSize
0x1800460f8  xor     ecx, ecx; lpBuffer
0x1800460fa  call    cs:__imp_GetSystemWindowsDirectoryW
0x180046101  nop     dword ptr [rax+rax+00h]
0x180046106  mov     esi, eax
0x180046108  test    eax, eax
0x18004610a  jnz     loc_1800461A1
0x180046110  call    cs:__imp_GetLastError
0x180046117  nop     dword ptr [rax+rax+00h]
0x18004611c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180046123  mov     ebx, eax
0x180046125  test    rcx, rcx
0x180046128  jz      short loc_18004617C
0x18004612a  mov     esi, 3
0x18004612f  lea     r9, aFailedToGetWin_0; "Failed to get windows directory."
0x180046136  mov     r8d, esi
0x180046139  xor     edx, edx
0x18004613b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180046140  test    ebx, ebx
0x180046142  jg      short loc_180046148
0x180046144  mov     eax, ebx
0x180046146  jmp     short loc_180046150
0x180046148  movzx   eax, bx
0x18004614b  or      eax, 80070000h
0x180046150  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180046157  lea     r9, a0; ": {0}"
0x18004615e  mov     dword ptr [rbp+lpBuffer], eax
0x180046161  mov     r8d, esi
0x180046164  lea     rax, [rbp+lpBuffer]
0x180046168  mov     dl, 1
0x18004616a  mov     qword ptr [rbp+var_20], rax
0x18004616e  lea     rax, [rbp+var_20]
0x180046172  mov     qword ptr [rsp+50h+var_30], rax; unsigned int
0x180046177  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004617c  test    ebx, ebx
0x18004617e  jz      loc_18004631B
0x180046184  mov     rcx, [rbp+18h]; this
0x180046188  lea     r8, aOnecoreBaseCbs_15; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x18004618f  mov     r9d, ebx; char *
0x180046192  mov     edx, 0B7h; void *
0x180046197  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004619c  jmp     loc_18004631D
0x1800461a1  lea     edx, [rax+1]
0x1800461a4  lea     rcx, [rbp+lpBuffer]
0x1800461a8  call    SczAlloc
0x1800461ad  mov     ebx, eax
0x1800461af  test    eax, eax
0x1800461b1  jns     short loc_1800461E6
0x1800461b3  mov     rcx, [rbp+18h]; this
0x1800461b7  lea     r8, aOnecoreBaseCbs_15; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x1800461be  mov     r9d, eax; char *
0x1800461c1  mov     edx, 0B8h; void *
0x1800461c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800461cb  mov     rcx, [rbp+lpBuffer]
0x1800461cf  test    rcx, rcx
0x1800461d2  jz      loc_1800460EF
0x1800461d8  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1800461dc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800461e1  jmp     loc_1800460EF
0x1800461e6  mov     rbx, [rbp+lpBuffer]
0x1800461ea  mov     edx, esi; uSize
0x1800461ec  mov     rcx, rbx; lpBuffer
0x1800461ef  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800461f6  nop     dword ptr [rax+rax+00h]
0x1800461fb  test    eax, eax
0x1800461fd  jnz     loc_1800462A3
0x180046203  call    cs:__imp_GetLastError
0x18004620a  nop     dword ptr [rax+rax+00h]
0x18004620f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180046216  mov     edi, eax
0x180046218  test    rcx, rcx
0x18004621b  jz      short loc_18004626F
0x18004621d  mov     esi, 3
0x180046222  lea     r9, aFailedToGetWin_0; "Failed to get windows directory."
0x180046229  mov     r8d, esi
0x18004622c  xor     edx, edx
0x18004622e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180046233  test    edi, edi
0x180046235  jg      short loc_18004623B
0x180046237  mov     eax, edi
0x180046239  jmp     short loc_180046243
0x18004623b  movzx   eax, di
0x18004623e  or      eax, 80070000h
0x180046243  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004624a  lea     r9, a0; ": {0}"
0x180046251  mov     dword ptr [rbp+lpBuffer], eax
0x180046254  mov     r8d, esi
0x180046257  lea     rax, [rbp+lpBuffer]
0x18004625b  mov     dl, 1
0x18004625d  mov     qword ptr [rbp+var_20], rax
0x180046261  lea     rax, [rbp+var_20]
0x180046265  mov     qword ptr [rsp+50h+var_30], rax; unsigned int
0x18004626a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004626f  test    edi, edi
0x180046271  jz      loc_18004630D
0x180046277  mov     r9d, edi; char *
0x18004627a  mov     edx, 0BCh; void *
0x18004627f  mov     rcx, [rbp+18h]; this
0x180046283  lea     r8, aOnecoreBaseCbs_15; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x18004628a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004628f  mov     edi, eax
0x180046291  test    rbx, rbx
0x180046294  jz      short loc_18004629F
0x180046296  lea     rcx, [rbx-8]; Block
0x18004629a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004629f  mov     eax, edi
0x1800462a1  jmp     short loc_18004631D
0x1800462a3  cmp     eax, esi
0x1800462a5  jb      short loc_1800462B3
0x1800462a7  mov     r9d, 7Ah ; 'z'
0x1800462ad  lea     edx, [r9+46h]
0x1800462b1  jmp     short loc_18004627F
0x1800462b3  lea     rcx, [rbp+lpBuffer]
0x1800462b7  call    SczEnsureBackslashTerminated
0x1800462bc  test    r14, r14
0x1800462bf  jz      short loc_1800462F3
0x1800462c1  mov     rbx, [rbp+lpBuffer]
0x1800462c5  mov     r8, r14
0x1800462c8  mov     rdx, rbx
0x1800462cb  mov     rcx, rdi
0x1800462ce  call    SczAllocConcat2Sz
0x1800462d3  mov     edi, eax
0x1800462d5  test    eax, eax
0x1800462d7  jns     short loc_18004630D
0x1800462d9  mov     rcx, [rbp+18h]; this
0x1800462dd  lea     r8, aOnecoreBaseCbs_15; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x1800462e4  mov     r9d, eax; char *
0x1800462e7  mov     edx, 0C6h; void *
0x1800462ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800462f1  jmp     short loc_180046291
0x1800462f3  mov     rcx, [rdi]
0x1800462f6  test    rcx, rcx
0x1800462f9  jz      short loc_180046304
0x1800462fb  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1800462ff  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180046304  mov     rax, [rbp+lpBuffer]
0x180046308  xor     ebx, ebx
0x18004630a  mov     [rdi], rax
0x18004630d  test    rbx, rbx
0x180046310  jz      short loc_18004631B
0x180046312  lea     rcx, [rbx-8]; Block
0x180046316  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004631b  xor     eax, eax
0x18004631d  mov     rcx, [rbp+var_10]
0x180046321  xor     rcx, rsp; StackCookie
0x180046324  call    __security_check_cookie
0x180046329  lea     r11, [rsp+50h+var_s0]
0x18004632e  mov     rbx, [r11+30h]
0x180046332  mov     rsi, [r11+38h]
0x180046336  mov     rsp, r11
0x180046339  pop     r14
0x18004633b  pop     rdi
0x18004633c  pop     rbp
0x18004633d  retn
```
