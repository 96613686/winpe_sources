# PathGetWindowsDirectory

- ea: `0x140016328`
- end: `0x1400165ef`
- name: `PathGetWindowsDirectory`
- size: `711`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x140013288`

## callees

- `0x140001fcc`
- `0x140002360`
- `0x1400056ac`
- `0x1400067bc`
- `0x140006c50`
- `0x14000726c`
- `0x14000952c`
- `0x140010b3c`
- `0x140011d50`
- `0x140016328`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400163e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400164d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400163e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400164d9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1400163d9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1400164cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1400163d9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1400164cb`

## string_xrefs

- `0x14001636e`: `No path result specified`
- `0x1400163b2`: `onecore\base\cbs\util\cbspath.cpp`
- `0x140016458`: `onecore\base\cbs\util\cbspath.cpp`
- `0x1400164a2`: `onecore\base\cbs\util\cbspath.cpp`
- `0x140016548`: `onecore\base\cbs\util\cbspath.cpp`
- `0x140016584`: `onecore\base\cbs\util\cbspath.cpp`
- `0x1400163fd`: `Failed to get windows directory.`
- `0x1400164ed`: `Failed to get windows directory.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PathGetWindowsDirectory(LPWSTR *a1)
{
  unsigned int v2; // ebx
  int v3; // edx
  UINT SystemWindowsDirectoryW; // eax
  UINT v6; // ebx
  signed int v7; // ebx
  int v8; // edx
  unsigned int v9; // eax
  int v10; // eax
  unsigned int v11; // esi
  UINT v12; // eax
  signed int LastError; // ebx
  int v14; // edx
  unsigned int v15; // eax
  LPWSTR v16; // rax
  unsigned int v17; // [rsp+20h] [rbp-48h]
  LPWSTR lpBuffer; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v19[2]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v20; // [rsp+40h] [rbp-28h]
  int v21; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]

  v20 = -2;
  lpBuffer = 0;
  if ( !a1 )
  {
    v2 = -2147467261;
    v21 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No path result specified");
      *(_QWORD *)v19 = &v21;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v3,
        3,
        (unsigned int)": {}",
        (__int64)v19);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB4,
      (unsigned int)"onecore\\base\\cbs\\util\\cbspath.cpp",
      (const char *)0x80004003LL,
      v17);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
    return v2;
  }
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(0, 0);
  v6 = SystemWindowsDirectoryW;
  if ( SystemWindowsDirectoryW )
  {
    v10 = SczAlloc(&lpBuffer, SystemWindowsDirectoryW + 1);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB8,
        (unsigned int)"onecore\\base\\cbs\\util\\cbspath.cpp",
        (const char *)(unsigned int)v10,
        v17);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
      return v11;
    }
    v12 = GetSystemWindowsDirectoryW(lpBuffer, v6);
    if ( v12 )
    {
      if ( v12 >= v6 )
      {
        v2 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xC0,
               (unsigned int)"onecore\\base\\cbs\\util\\cbspath.cpp",
               (const char *)0x7A,
               v17);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
        return v2;
      }
      SczEnsureBackslashTerminated(&lpBuffer);
      if ( *a1 )
        operator delete(*a1 - 4);
      v16 = lpBuffer;
      lpBuffer = 0;
      *a1 = v16;
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
      return 0;
    }
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get windows directory.");
      if ( LastError > 0 )
        v15 = (unsigned __int16)LastError | 0x80070000;
      else
        v15 = LastError;
      v21 = v15;
      *(_QWORD *)v19 = &v21;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v14,
        3,
        (unsigned int)": {0}",
        (__int64)v19);
    }
    if ( LastError )
    {
      v2 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xBC,
             (unsigned int)"onecore\\base\\cbs\\util\\cbspath.cpp",
             (const char *)(unsigned int)LastError,
             v17);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
      return v2;
    }
  }
  else
  {
    v7 = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get windows directory.");
      if ( v7 > 0 )
        v9 = (unsigned __int16)v7 | 0x80070000;
      else
        v9 = v7;
      v21 = v9;
      *(_QWORD *)v19 = &v21;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v8,
        3,
        (unsigned int)": {0}",
        (__int64)v19);
    }
    if ( v7 )
    {
      v2 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xB7,
             (unsigned int)"onecore\\base\\cbs\\util\\cbspath.cpp",
             (const char *)(unsigned int)v7,
             v17);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
      return v2;
    }
  }
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
  return 0;
}

```

## disassembly

```asm
0x140016328  push    rbp
0x14001632a  push    rbx
0x14001632b  push    rsi
0x14001632c  push    rdi
0x14001632d  mov     rbp, rsp
0x140016330  sub     rsp, 68h
0x140016334  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFEh
0x14001633c  mov     rax, cs:__security_cookie
0x140016343  xor     rax, rsp
0x140016346  mov     [rbp+var_18], rax
0x14001634a  mov     rdi, rcx
0x14001634d  mov     [rbp+lpBuffer], 0
0x140016355  test    rcx, rcx
0x140016358  jnz     short loc_1400163D5
0x14001635a  mov     ebx, 80004003h
0x14001635f  mov     [rbp+var_20], ebx
0x140016362  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016369  test    rcx, rcx
0x14001636c  jz      short loc_1400163AB
0x14001636e  lea     r9, aNoPathResultSp; "No path result specified"
0x140016375  mov     edi, 3
0x14001637a  mov     r8d, edi
0x14001637d  xor     edx, edx
0x14001637f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140016384  lea     rax, [rbp+var_20]
0x140016388  mov     qword ptr [rbp+var_30], rax
0x14001638c  lea     rax, [rbp+var_30]
0x140016390  mov     qword ptr [rsp+68h+var_48], rax; int
0x140016395  lea     r9, asc_14002D4FC; ": {}"
0x14001639c  mov     r8d, edi
0x14001639f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400163a6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400163ab  mov     rcx, [rbp+20h]; this
0x1400163af  mov     r9d, ebx; char *
0x1400163b2  lea     r8, aOnecoreBaseCbs_11; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x1400163b9  mov     edx, 0B4h; void *
0x1400163be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400163c3  nop
0x1400163c4  lea     rcx, [rbp+lpBuffer]
0x1400163c8  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1400163cd  nop
0x1400163ce  mov     eax, ebx
0x1400163d0  jmp     loc_1400165DA
0x1400163d5  xor     edx, edx; uSize
0x1400163d7  xor     ecx, ecx; lpBuffer
0x1400163d9  call    cs:__imp_GetSystemWindowsDirectoryW
0x1400163df  mov     ebx, eax
0x1400163e1  test    eax, eax
0x1400163e3  jnz     loc_140016489
0x1400163e9  call    cs:__imp_GetLastError
0x1400163ef  mov     ebx, eax
0x1400163f1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400163f8  test    rcx, rcx
0x1400163fb  jz      short loc_14001644D
0x1400163fd  lea     r9, aFailedToGetWin_0; "Failed to get windows directory."
0x140016404  mov     edi, 3
0x140016409  mov     r8d, edi
0x14001640c  xor     edx, edx
0x14001640e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140016413  test    ebx, ebx
0x140016415  jg      short loc_14001641B
0x140016417  mov     eax, ebx
0x140016419  jmp     short loc_140016423
0x14001641b  movzx   eax, bx
0x14001641e  or      eax, 80070000h
0x140016423  mov     [rbp+var_20], eax
0x140016426  lea     rax, [rbp+var_20]
0x14001642a  mov     qword ptr [rbp+var_30], rax
0x14001642e  lea     rax, [rbp+var_30]
0x140016432  mov     qword ptr [rsp+68h+var_48], rax; unsigned int
0x140016437  lea     r9, a0; ": {0}"
0x14001643e  mov     r8d, edi
0x140016441  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016448  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001644d  test    ebx, ebx
0x14001644f  jz      short loc_14001647A
0x140016451  mov     rcx, [rbp+20h]; this
0x140016455  mov     r9d, ebx; char *
0x140016458  lea     r8, aOnecoreBaseCbs_11; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x14001645f  mov     edx, 0B7h; void *
0x140016464  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140016469  mov     ebx, eax
0x14001646b  lea     rcx, [rbp+lpBuffer]
0x14001646f  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140016474  nop
0x140016475  jmp     loc_1400163CE
0x14001647a  lea     rcx, [rbp+lpBuffer]
0x14001647e  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140016483  nop
0x140016484  jmp     loc_1400165D8
0x140016489  lea     edx, [rax+1]
0x14001648c  lea     rcx, [rbp+lpBuffer]
0x140016490  call    SczAlloc
0x140016495  mov     esi, eax
0x140016497  test    eax, eax
0x140016499  jns     short loc_1400164C5
0x14001649b  mov     rcx, [rbp+20h]; this
0x14001649f  mov     r9d, eax; char *
0x1400164a2  lea     r8, aOnecoreBaseCbs_11; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x1400164a9  mov     edx, 0B8h; void *
0x1400164ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400164b3  nop
0x1400164b4  lea     rcx, [rbp+lpBuffer]
0x1400164b8  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1400164bd  nop
0x1400164be  mov     eax, esi
0x1400164c0  jmp     loc_1400165DA
0x1400164c5  mov     edx, ebx; uSize
0x1400164c7  mov     rcx, [rbp+lpBuffer]; lpBuffer
0x1400164cb  call    cs:__imp_GetSystemWindowsDirectoryW
0x1400164d1  test    eax, eax
0x1400164d3  jnz     loc_140016576
0x1400164d9  call    cs:__imp_GetLastError
0x1400164df  mov     ebx, eax
0x1400164e1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400164e8  test    rcx, rcx
0x1400164eb  jz      short loc_14001653D
0x1400164ed  lea     r9, aFailedToGetWin_0; "Failed to get windows directory."
0x1400164f4  mov     edi, 3
0x1400164f9  mov     r8d, edi
0x1400164fc  xor     edx, edx
0x1400164fe  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140016503  test    ebx, ebx
0x140016505  jg      short loc_14001650B
0x140016507  mov     eax, ebx
0x140016509  jmp     short loc_140016513
0x14001650b  movzx   eax, bx
0x14001650e  or      eax, 80070000h
0x140016513  mov     [rbp+var_20], eax
0x140016516  lea     rax, [rbp+var_20]
0x14001651a  mov     qword ptr [rbp+var_30], rax
0x14001651e  lea     rax, [rbp+var_30]
0x140016522  mov     qword ptr [rsp+68h+var_48], rax; unsigned int
0x140016527  lea     r9, a0; ": {0}"
0x14001652e  mov     r8d, edi
0x140016531  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016538  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001653d  test    ebx, ebx
0x14001653f  jz      short loc_14001656A
0x140016541  mov     rcx, [rbp+20h]; this
0x140016545  mov     r9d, ebx; char *
0x140016548  lea     r8, aOnecoreBaseCbs_11; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x14001654f  mov     edx, 0BCh; void *
0x140016554  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140016559  mov     ebx, eax
0x14001655b  lea     rcx, [rbp+lpBuffer]
0x14001655f  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140016564  nop
0x140016565  jmp     loc_1400163CE
0x14001656a  lea     rcx, [rbp+lpBuffer]
0x14001656e  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140016573  nop
0x140016574  jmp     short loc_1400165D8
0x140016576  cmp     eax, ebx
0x140016578  jb      short loc_1400165A5
0x14001657a  mov     rcx, [rbp+20h]; this
0x14001657e  mov     r9d, 7Ah ; 'z'; char *
0x140016584  lea     r8, aOnecoreBaseCbs_11; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x14001658b  lea     edx, [r9+46h]; void *
0x14001658f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140016594  mov     ebx, eax
0x140016596  lea     rcx, [rbp+lpBuffer]
0x14001659a  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14001659f  nop
0x1400165a0  jmp     loc_1400163CE
0x1400165a5  lea     rcx, [rbp+lpBuffer]
0x1400165a9  call    SczEnsureBackslashTerminated
0x1400165ae  mov     rcx, [rdi]
0x1400165b1  test    rcx, rcx
0x1400165b4  jz      short loc_1400165BF
0x1400165b6  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1400165ba  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400165bf  mov     rax, [rbp+lpBuffer]
0x1400165c3  mov     [rbp+lpBuffer], 0
0x1400165cb  mov     [rdi], rax
0x1400165ce  lea     rcx, [rbp+lpBuffer]
0x1400165d2  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1400165d7  nop
0x1400165d8  xor     eax, eax
0x1400165da  mov     rcx, [rbp+var_18]
0x1400165de  xor     rcx, rsp; StackCookie
0x1400165e1  call    __security_check_cookie
0x1400165e6  add     rsp, 68h
0x1400165ea  pop     rdi
0x1400165eb  pop     rsi
0x1400165ec  pop     rbx
0x1400165ed  pop     rbp
0x1400165ee  retn
```
