# PathGetWindowsDirectory

- ea: `0x180050dac`
- end: `0x180050ff9`
- name: `PathGetWindowsDirectory`
- size: `589`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180047e20`

## callees

- `0x180020440`
- `0x180026c90`
- `0x180026e00`
- `0x18002d2b0`
- `0x180046650`
- `0x180046ca4`
- `0x180047c5c`
- `0x18004f580`
- `0x180050980`
- `0x180050dac`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180050e4c`
- `KERNEL32!GetLastError` at `0x180050f22`
- `KERNEL32!GetLastError` at `0x180050e4c`
- `KERNEL32!GetLastError` at `0x180050f22`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180050e36`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180050f12`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180050e36`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180050f12`

## string_xrefs

- `0x180050e6b`: `Failed to get windows directory.`
- `0x180050f41`: `Failed to get windows directory.`
- `0x180050df2`: `No path result specified`
- `0x180050eca`: `onecore\base\cbs\util\cbspath.cpp`
- `0x180050efb`: `onecore\base\cbs\util\cbspath.cpp`

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
0x180050dac  push    rbp
0x180050dae  push    rbx
0x180050daf  push    rsi
0x180050db0  push    rdi
0x180050db1  mov     rbp, rsp
0x180050db4  sub     rsp, 58h
0x180050db8  mov     rax, cs:__security_cookie
0x180050dbf  xor     rax, rsp
0x180050dc2  mov     [rbp+var_10], rax
0x180050dc6  mov     [rbp+lpBuffer], 0
0x180050dce  mov     rsi, rcx
0x180050dd1  test    rcx, rcx
0x180050dd4  jnz     short loc_180050E32
0x180050dd6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180050ddd  mov     ebx, 80004003h
0x180050de2  mov     [rbp+var_18], ebx
0x180050de5  test    rcx, rcx
0x180050de8  jz      short loc_180050E25
0x180050dea  lea     edi, [rsi+3]
0x180050ded  xor     edx, edx
0x180050def  mov     r8d, edi
0x180050df2  lea     r9, aNoPathResultSp; "No path result specified"
0x180050df9  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180050dfe  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180050e05  lea     rax, [rbp+var_18]
0x180050e09  mov     qword ptr [rbp+var_20], rax
0x180050e0d  lea     r9, asc_1800AFAD8; ": {}"
0x180050e14  lea     rax, [rbp+var_20]
0x180050e18  mov     r8d, edi
0x180050e1b  mov     qword ptr [rsp+58h+var_38], rax
0x180050e20  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180050e25  mov     r9d, ebx
0x180050e28  mov     edx, 0B4h
0x180050e2d  jmp     loc_180050EF7
0x180050e32  xor     edx, edx; uSize
0x180050e34  xor     ecx, ecx; lpBuffer
0x180050e36  call    cs:__imp_GetSystemWindowsDirectoryW
0x180050e3d  nop     dword ptr [rax+rax+00h]
0x180050e42  mov     edi, eax
0x180050e44  test    eax, eax
0x180050e46  jnz     loc_180050EDD
0x180050e4c  call    cs:__imp_GetLastError
0x180050e53  nop     dword ptr [rax+rax+00h]
0x180050e58  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180050e5f  mov     ebx, eax
0x180050e61  test    rcx, rcx
0x180050e64  jz      short loc_180050EB6
0x180050e66  mov     edi, 3
0x180050e6b  lea     r9, aFailedToGetWin_0; "Failed to get windows directory."
0x180050e72  mov     r8d, edi
0x180050e75  xor     edx, edx
0x180050e77  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180050e7c  test    ebx, ebx
0x180050e7e  jg      short loc_180050E84
0x180050e80  mov     eax, ebx
0x180050e82  jmp     short loc_180050E8C
0x180050e84  movzx   eax, bx
0x180050e87  or      eax, 80070000h
0x180050e8c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180050e93  lea     r9, a0; ": {0}"
0x180050e9a  mov     [rbp+var_18], eax
0x180050e9d  mov     r8d, edi
0x180050ea0  lea     rax, [rbp+var_18]
0x180050ea4  mov     qword ptr [rbp+var_20], rax
0x180050ea8  lea     rax, [rbp+var_20]
0x180050eac  mov     qword ptr [rsp+58h+var_38], rax; unsigned int
0x180050eb1  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180050eb6  test    ebx, ebx
0x180050eb8  jz      loc_180050FD6
0x180050ebe  mov     edx, 0B7h; void *
0x180050ec3  mov     r9d, ebx; char *
0x180050ec6  mov     rcx, [rbp+20h]; this
0x180050eca  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x180050ed1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180050ed6  mov     ebx, eax
0x180050ed8  jmp     loc_180050FD8
0x180050edd  lea     edx, [rax+1]
0x180050ee0  lea     rcx, [rbp+lpBuffer]
0x180050ee4  call    SczAlloc
0x180050ee9  mov     ebx, eax
0x180050eeb  test    eax, eax
0x180050eed  jns     short loc_180050F0C
0x180050eef  mov     r9d, eax; char *
0x180050ef2  mov     edx, 0B8h; void *
0x180050ef7  mov     rcx, [rbp+20h]; this
0x180050efb  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x180050f02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050f07  jmp     loc_180050FD8
0x180050f0c  mov     rcx, [rbp+lpBuffer]; lpBuffer
0x180050f10  mov     edx, edi; uSize
0x180050f12  call    cs:__imp_GetSystemWindowsDirectoryW
0x180050f19  nop     dword ptr [rax+rax+00h]
0x180050f1e  test    eax, eax
0x180050f20  jnz     short loc_180050F9A
0x180050f22  call    cs:__imp_GetLastError
0x180050f29  nop     dword ptr [rax+rax+00h]
0x180050f2e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180050f35  mov     ebx, eax
0x180050f37  test    rcx, rcx
0x180050f3a  jz      short loc_180050F8C
0x180050f3c  mov     edi, 3
0x180050f41  lea     r9, aFailedToGetWin_0; "Failed to get windows directory."
0x180050f48  mov     r8d, edi
0x180050f4b  xor     edx, edx
0x180050f4d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180050f52  test    ebx, ebx
0x180050f54  jg      short loc_180050F5A
0x180050f56  mov     eax, ebx
0x180050f58  jmp     short loc_180050F62
0x180050f5a  movzx   eax, bx
0x180050f5d  or      eax, 80070000h
0x180050f62  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180050f69  lea     r9, a0; ": {0}"
0x180050f70  mov     [rbp+var_18], eax
0x180050f73  mov     r8d, edi
0x180050f76  lea     rax, [rbp+var_18]
0x180050f7a  mov     qword ptr [rbp+var_20], rax
0x180050f7e  lea     rax, [rbp+var_20]
0x180050f82  mov     qword ptr [rsp+58h+var_38], rax
0x180050f87  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180050f8c  test    ebx, ebx
0x180050f8e  jz      short loc_180050FD6
0x180050f90  mov     edx, 0BCh
0x180050f95  jmp     loc_180050EC3
0x180050f9a  cmp     eax, edi
0x180050f9c  jb      short loc_180050FAD
0x180050f9e  mov     r9d, 7Ah ; 'z'
0x180050fa4  lea     edx, [r9+46h]
0x180050fa8  jmp     loc_180050EC6
0x180050fad  lea     rcx, [rbp+lpBuffer]
0x180050fb1  call    SczEnsureBackslashTerminated
0x180050fb6  mov     rcx, [rsi]
0x180050fb9  test    rcx, rcx
0x180050fbc  jz      short loc_180050FC7
0x180050fbe  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x180050fc2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180050fc7  mov     rax, [rbp+lpBuffer]
0x180050fcb  mov     [rsi], rax
0x180050fce  mov     [rbp+lpBuffer], 0
0x180050fd6  xor     ebx, ebx
0x180050fd8  lea     rcx, [rbp+lpBuffer]
0x180050fdc  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x180050fe1  mov     eax, ebx
0x180050fe3  mov     rcx, [rbp+var_10]
0x180050fe7  xor     rcx, rsp; StackCookie
0x180050fea  call    __security_check_cookie
0x180050fef  add     rsp, 58h
0x180050ff3  pop     rdi
0x180050ff4  pop     rsi
0x180050ff5  pop     rbx
0x180050ff6  pop     rbp
0x180050ff7  retn
```
