# PathGetWindowsDirectory

- ea: `0x18004dc74`
- end: `0x18004dec1`
- name: `PathGetWindowsDirectory`
- size: `589`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180044c90`

## callees

- `0x18001e51c`
- `0x180022d80`
- `0x180022ef0`
- `0x1800293a0`
- `0x18003d7d4`
- `0x180041a74`
- `0x180041de8`
- `0x18004c460`
- `0x18004d850`
- `0x18004dc74`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004dd14`
- `KERNEL32!GetLastError` at `0x18004ddea`
- `KERNEL32!GetLastError` at `0x18004dd14`
- `KERNEL32!GetLastError` at `0x18004ddea`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x18004dcfe`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x18004ddda`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x18004dcfe`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x18004ddda`

## string_xrefs

- `0x18004dd33`: `Failed to get windows directory.`
- `0x18004de09`: `Failed to get windows directory.`
- `0x18004dcba`: `No path result specified`
- `0x18004dd92`: `onecore\base\cbs\util\cbspath.cpp`
- `0x18004ddc3`: `onecore\base\cbs\util\cbspath.cpp`

## pseudocode

```c
__int64 __fastcall PathGetWindowsDirectory(LPWSTR *a1)
{
  unsigned int v2; // ebx
  int v3; // edx
  __int64 v4; // r9
  __int64 v5; // rdx
  UINT SystemWindowsDirectoryW; // eax
  UINT v7; // edi
  signed int LastError; // ebx
  int v9; // edx
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r9
  int v13; // eax
  UINT v14; // eax
  int v15; // edx
  unsigned int v16; // eax
  const struct std::nothrow_t *v17; // rdx
  unsigned int v19; // [rsp+20h] [rbp-38h]
  LPWSTR lpBuffer; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v21[2]; // [rsp+38h] [rbp-20h] BYREF
  int v22; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]

  lpBuffer = 0;
  if ( !a1 )
  {
    v2 = -2147467261;
    v22 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No path result specified");
      *(_QWORD *)v21 = &v22;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v3,
        3,
        (unsigned int)": {}",
        (__int64)v21);
    }
    v4 = 2147500035LL;
    v5 = 180;
    goto LABEL_17;
  }
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(0, 0);
  v7 = SystemWindowsDirectoryW;
  if ( SystemWindowsDirectoryW )
  {
    v13 = SczAlloc(&lpBuffer, SystemWindowsDirectoryW + 1);
    v2 = v13;
    if ( v13 < 0 )
    {
      v4 = (unsigned int)v13;
      v5 = 184;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v5,
        (unsigned int)"onecore\\base\\cbs\\util\\cbspath.cpp",
        (const char *)v4,
        v19);
      goto LABEL_32;
    }
    v14 = GetSystemWindowsDirectoryW(lpBuffer, v7);
    if ( v14 )
    {
      if ( v14 >= v7 )
      {
        v12 = 122;
        v11 = 192;
        goto LABEL_14;
      }
      SczEnsureBackslashTerminated(&lpBuffer);
      if ( *a1 )
        operator delete(*a1 - 4, v17);
      *a1 = lpBuffer;
      lpBuffer = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get windows directory.");
        if ( LastError > 0 )
          v16 = (unsigned __int16)LastError | 0x80070000;
        else
          v16 = LastError;
        v22 = v16;
        *(_QWORD *)v21 = &v22;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v15,
          3,
          (unsigned int)": {0}",
          (__int64)v21);
      }
      if ( LastError )
      {
        v11 = 188;
        goto LABEL_13;
      }
    }
LABEL_31:
    v2 = 0;
    goto LABEL_32;
  }
  LastError = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get windows directory.");
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    else
      v10 = LastError;
    v22 = v10;
    *(_QWORD *)v21 = &v22;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v9,
      3,
      (unsigned int)": {0}",
      (__int64)v21);
  }
  if ( !LastError )
    goto LABEL_31;
  v11 = 183;
LABEL_13:
  v12 = (unsigned int)LastError;
LABEL_14:
  v2 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)v11,
         (unsigned int)"onecore\\base\\cbs\\util\\cbspath.cpp",
         (const char *)v12,
         v19);
LABEL_32:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
  return v2;
}

```

## disassembly

```asm
0x18004dc74  push    rbp
0x18004dc76  push    rbx
0x18004dc77  push    rsi
0x18004dc78  push    rdi
0x18004dc79  mov     rbp, rsp
0x18004dc7c  sub     rsp, 58h
0x18004dc80  mov     rax, cs:__security_cookie
0x18004dc87  xor     rax, rsp
0x18004dc8a  mov     [rbp+var_10], rax
0x18004dc8e  mov     [rbp+lpBuffer], 0
0x18004dc96  mov     rsi, rcx
0x18004dc99  test    rcx, rcx
0x18004dc9c  jnz     short loc_18004DCFA
0x18004dc9e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004dca5  mov     ebx, 80004003h
0x18004dcaa  mov     [rbp+var_18], ebx
0x18004dcad  test    rcx, rcx
0x18004dcb0  jz      short loc_18004DCED
0x18004dcb2  lea     edi, [rsi+3]
0x18004dcb5  xor     edx, edx
0x18004dcb7  mov     r8d, edi
0x18004dcba  lea     r9, aNoPathResultSp; "No path result specified"
0x18004dcc1  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004dcc6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004dccd  lea     rax, [rbp+var_18]
0x18004dcd1  mov     qword ptr [rbp+var_20], rax
0x18004dcd5  lea     r9, asc_1800AFB70; ": {}"
0x18004dcdc  lea     rax, [rbp+var_20]
0x18004dce0  mov     r8d, edi
0x18004dce3  mov     qword ptr [rsp+58h+var_38], rax
0x18004dce8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004dced  mov     r9d, ebx
0x18004dcf0  mov     edx, 0B4h
0x18004dcf5  jmp     loc_18004DDBF
0x18004dcfa  xor     edx, edx; uSize
0x18004dcfc  xor     ecx, ecx; lpBuffer
0x18004dcfe  call    cs:__imp_GetSystemWindowsDirectoryW
0x18004dd05  nop     dword ptr [rax+rax+00h]
0x18004dd0a  mov     edi, eax
0x18004dd0c  test    eax, eax
0x18004dd0e  jnz     loc_18004DDA5
0x18004dd14  call    cs:__imp_GetLastError
0x18004dd1b  nop     dword ptr [rax+rax+00h]
0x18004dd20  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004dd27  mov     ebx, eax
0x18004dd29  test    rcx, rcx
0x18004dd2c  jz      short loc_18004DD7E
0x18004dd2e  mov     edi, 3
0x18004dd33  lea     r9, aFailedToGetWin_0; "Failed to get windows directory."
0x18004dd3a  mov     r8d, edi
0x18004dd3d  xor     edx, edx
0x18004dd3f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004dd44  test    ebx, ebx
0x18004dd46  jg      short loc_18004DD4C
0x18004dd48  mov     eax, ebx
0x18004dd4a  jmp     short loc_18004DD54
0x18004dd4c  movzx   eax, bx
0x18004dd4f  or      eax, 80070000h
0x18004dd54  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004dd5b  lea     r9, a0; ": {0}"
0x18004dd62  mov     [rbp+var_18], eax
0x18004dd65  mov     r8d, edi
0x18004dd68  lea     rax, [rbp+var_18]
0x18004dd6c  mov     qword ptr [rbp+var_20], rax
0x18004dd70  lea     rax, [rbp+var_20]
0x18004dd74  mov     qword ptr [rsp+58h+var_38], rax; unsigned int
0x18004dd79  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004dd7e  test    ebx, ebx
0x18004dd80  jz      loc_18004DE9E
0x18004dd86  mov     edx, 0B7h; void *
0x18004dd8b  mov     r9d, ebx; char *
0x18004dd8e  mov     rcx, [rbp+20h]; this
0x18004dd92  lea     r8, aOnecoreBaseCbs_11; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x18004dd99  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004dd9e  mov     ebx, eax
0x18004dda0  jmp     loc_18004DEA0
0x18004dda5  lea     edx, [rax+1]
0x18004dda8  lea     rcx, [rbp+lpBuffer]
0x18004ddac  call    SczAlloc
0x18004ddb1  mov     ebx, eax
0x18004ddb3  test    eax, eax
0x18004ddb5  jns     short loc_18004DDD4
0x18004ddb7  mov     r9d, eax; char *
0x18004ddba  mov     edx, 0B8h; void *
0x18004ddbf  mov     rcx, [rbp+20h]; this
0x18004ddc3  lea     r8, aOnecoreBaseCbs_11; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x18004ddca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ddcf  jmp     loc_18004DEA0
0x18004ddd4  mov     rcx, [rbp+lpBuffer]; lpBuffer
0x18004ddd8  mov     edx, edi; uSize
0x18004ddda  call    cs:__imp_GetSystemWindowsDirectoryW
0x18004dde1  nop     dword ptr [rax+rax+00h]
0x18004dde6  test    eax, eax
0x18004dde8  jnz     short loc_18004DE62
0x18004ddea  call    cs:__imp_GetLastError
0x18004ddf1  nop     dword ptr [rax+rax+00h]
0x18004ddf6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004ddfd  mov     ebx, eax
0x18004ddff  test    rcx, rcx
0x18004de02  jz      short loc_18004DE54
0x18004de04  mov     edi, 3
0x18004de09  lea     r9, aFailedToGetWin_0; "Failed to get windows directory."
0x18004de10  mov     r8d, edi
0x18004de13  xor     edx, edx
0x18004de15  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004de1a  test    ebx, ebx
0x18004de1c  jg      short loc_18004DE22
0x18004de1e  mov     eax, ebx
0x18004de20  jmp     short loc_18004DE2A
0x18004de22  movzx   eax, bx
0x18004de25  or      eax, 80070000h
0x18004de2a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004de31  lea     r9, a0; ": {0}"
0x18004de38  mov     [rbp+var_18], eax
0x18004de3b  mov     r8d, edi
0x18004de3e  lea     rax, [rbp+var_18]
0x18004de42  mov     qword ptr [rbp+var_20], rax
0x18004de46  lea     rax, [rbp+var_20]
0x18004de4a  mov     qword ptr [rsp+58h+var_38], rax
0x18004de4f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004de54  test    ebx, ebx
0x18004de56  jz      short loc_18004DE9E
0x18004de58  mov     edx, 0BCh
0x18004de5d  jmp     loc_18004DD8B
0x18004de62  cmp     eax, edi
0x18004de64  jb      short loc_18004DE75
0x18004de66  mov     r9d, 7Ah ; 'z'
0x18004de6c  lea     edx, [r9+46h]
0x18004de70  jmp     loc_18004DD8E
0x18004de75  lea     rcx, [rbp+lpBuffer]
0x18004de79  call    SczEnsureBackslashTerminated
0x18004de7e  mov     rcx, [rsi]
0x18004de81  test    rcx, rcx
0x18004de84  jz      short loc_18004DE8F
0x18004de86  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x18004de8a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004de8f  mov     rax, [rbp+lpBuffer]
0x18004de93  mov     [rsi], rax
0x18004de96  mov     [rbp+lpBuffer], 0
0x18004de9e  xor     ebx, ebx
0x18004dea0  lea     rcx, [rbp+lpBuffer]
0x18004dea4  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18004dea9  mov     eax, ebx
0x18004deab  mov     rcx, [rbp+var_10]
0x18004deaf  xor     rcx, rsp; StackCookie
0x18004deb2  call    __security_check_cookie
0x18004deb7  add     rsp, 58h
0x18004debb  pop     rdi
0x18004debc  pop     rsi
0x18004debd  pop     rbx
0x18004debe  pop     rbp
0x18004debf  retn
```
