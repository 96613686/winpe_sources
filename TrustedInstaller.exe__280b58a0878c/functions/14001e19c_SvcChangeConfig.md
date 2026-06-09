# SvcChangeConfig

- ea: `0x14001e19c`
- end: `0x14001e324`
- name: `SvcChangeConfig`
- size: `392`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x14000d12c`
- `0x14000d420`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140016a40`
- `0x140016fb4`
- `0x1400184fc`
- `0x14001e19c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e283`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001e283`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x14001e275`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x14001e275`

## string_xrefs

- `0x14001e1d0`: `No service handle specified`
- `0x14001e299`: `Failed change service configuration.`

## pseudocode

```c
int __fastcall SvcChangeConfig(SC_HANDLE a1, __int64 a2, DWORD a3)
{
  __int64 v3; // rdx
  signed int LastError; // ebx
  __int64 v6; // rdx
  unsigned int v7; // eax
  int lpBinaryPathName; // [rsp+20h] [rbp-68h]
  unsigned int lpBinaryPathNamea; // [rsp+20h] [rbp-68h]
  unsigned int v10[2]; // [rsp+60h] [rbp-28h] BYREF
  int v11; // [rsp+68h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( a1 )
  {
    if ( ChangeServiceConfigW(a1, 0xFFFFFFFF, a3, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
      return 0;
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed change service configuration.");
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      else
        v7 = LastError;
      v11 = v7;
      *(_QWORD *)v10 = &v11;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v6,
        3,
        (__int64)": {0}",
        (__int64)v10);
    }
    if ( !LastError )
      return 0;
    else
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x52,
               (unsigned int)"onecore\\base\\cbs\\util\\cbssvc.cpp",
               (const char *)(unsigned int)LastError,
               lpBinaryPathNamea);
  }
  else
  {
    v11 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No service handle specified");
      *(_QWORD *)v10 = &v11;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v3,
        3,
        (__int64)": {}",
        (__int64)v10);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecore\\base\\cbs\\util\\cbssvc.cpp",
      (const char *)0x80070057LL,
      lpBinaryPathName);
    return -2147024809;
  }
}

```

## disassembly

```asm
0x14001e19c  push    rbx
0x14001e19e  sub     rsp, 80h
0x14001e1a5  mov     rax, cs:__security_cookie
0x14001e1ac  xor     rax, rsp
0x14001e1af  mov     [rsp+88h+var_18], rax
0x14001e1b4  test    rcx, rcx
0x14001e1b7  jnz     short loc_14001E230
0x14001e1b9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001e1c0  mov     ebx, 80070057h
0x14001e1c5  mov     [rsp+88h+var_20], ebx
0x14001e1c9  test    rcx, rcx
0x14001e1cc  jz      short loc_14001E20D
0x14001e1ce  xor     edx, edx
0x14001e1d0  lea     r9, aNoServiceHandl_0; "No service handle specified"
0x14001e1d7  lea     r8d, [rdx+3]
0x14001e1db  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001e1e0  lea     rcx, [rsp+88h+var_28]
0x14001e1e5  mov     r8d, 3
0x14001e1eb  mov     [rsp+88h+lpBinaryPathName], rcx; int
0x14001e1f0  lea     rax, [rsp+88h+var_20]
0x14001e1f5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001e1fc  lea     r9, asc_1400353E8; ": {}"
0x14001e203  mov     qword ptr [rsp+88h+var_28], rax
0x14001e208  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001e20d  mov     rcx, [rsp+88h]; this
0x14001e215  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\util\\cbssvc.cpp"
0x14001e21c  mov     r9d, ebx; char *
0x14001e21f  mov     edx, 43h ; 'C'; void *
0x14001e224  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001e229  mov     eax, ebx
0x14001e22b  jmp     loc_14001E30E
0x14001e230  mov     [rsp+88h+lpDisplayName], 0; lpDisplayName
0x14001e239  or      edx, 0FFFFFFFFh; dwServiceType
0x14001e23c  mov     [rsp+88h+lpPassword], 0; lpPassword
0x14001e245  mov     r9d, edx; dwErrorControl
0x14001e248  mov     [rsp+88h+lpServiceStartName], 0; lpServiceStartName
0x14001e251  mov     [rsp+88h+lpDependencies], 0; lpDependencies
0x14001e25a  mov     [rsp+88h+lpdwTagId], 0; lpdwTagId
0x14001e263  mov     [rsp+88h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x14001e26c  mov     [rsp+88h+lpBinaryPathName], 0; lpBinaryPathName
0x14001e275  call    cs:__imp_ChangeServiceConfigW
0x14001e27b  test    eax, eax
0x14001e27d  jnz     loc_14001E30C
0x14001e283  call    cs:__imp_GetLastError
0x14001e289  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001e290  mov     ebx, eax
0x14001e292  test    rcx, rcx
0x14001e295  jz      short loc_14001E2EA
0x14001e297  xor     edx, edx
0x14001e299  lea     r9, aFailedChangeSe; "Failed change service configuration."
0x14001e2a0  lea     r8d, [rdx+3]
0x14001e2a4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001e2a9  test    ebx, ebx
0x14001e2ab  jg      short loc_14001E2B1
0x14001e2ad  mov     eax, ebx
0x14001e2af  jmp     short loc_14001E2B9
0x14001e2b1  movzx   eax, bx
0x14001e2b4  or      eax, 80070000h
0x14001e2b9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001e2c0  lea     r9, a0; ": {0}"
0x14001e2c7  mov     [rsp+88h+var_20], eax
0x14001e2cb  mov     r8d, 3
0x14001e2d1  lea     rax, [rsp+88h+var_20]
0x14001e2d6  mov     qword ptr [rsp+88h+var_28], rax
0x14001e2db  lea     rax, [rsp+88h+var_28]
0x14001e2e0  mov     [rsp+88h+lpBinaryPathName], rax; unsigned int
0x14001e2e5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001e2ea  test    ebx, ebx
0x14001e2ec  jz      short loc_14001E30C
0x14001e2ee  mov     rcx, [rsp+88h]; this
0x14001e2f6  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\util\\cbssvc.cpp"
0x14001e2fd  mov     r9d, ebx; char *
0x14001e300  mov     edx, 52h ; 'R'; void *
0x14001e305  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14001e30a  jmp     short loc_14001E30E
0x14001e30c  xor     eax, eax
0x14001e30e  mov     rcx, [rsp+88h+var_18]
0x14001e313  xor     rcx, rsp; StackCookie
0x14001e316  call    __security_check_cookie
0x14001e31b  add     rsp, 80h
0x14001e322  pop     rbx
0x14001e323  retn
```
