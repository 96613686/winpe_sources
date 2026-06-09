# EnsureCallerIsAdministrator

- ea: `0x1400200b8`
- end: `0x140020273`
- name: `EnsureCallerIsAdministrator`
- size: `443`
- prototype: `__int64()`
- caller_count: `5`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000ede4`
- `0x14000f634`
- `0x1400104a4`
- `0x140012a74`
- `0x140014334`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140016a40`
- `0x140016fb4`
- `0x140017810`
- `0x140017d14`
- `0x1400200b8`
- `0x140020c84`
- `0x140022548`

## string_xrefs

- `0x140020108`: `Failed to get user token to test for admin credentials.`
- `0x14002019d`: `Failed administrator access check.`
- `0x140020208`: `Failed to determine credentials for access check.`

## pseudocode

```c
__int64 EnsureCallerIsAdministrator()
{
  __int64 InitPointer; // rax
  int ImpersonationToken; // eax
  unsigned int v2; // ebx
  int v3; // edx
  __int64 v4; // rdx
  int v5; // eax
  int v6; // edx
  int v7; // edx
  int v9; // [rsp+20h] [rbp-19h]
  int v10[2]; // [rsp+30h] [rbp-9h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-1h] BYREF
  int v12; // [rsp+40h] [rbp+7h] BYREF
  __int128 v13; // [rsp+48h] [rbp+Fh]
  __int64 v14; // [rsp+58h] [rbp+1Fh]
  __int64 v15; // [rsp+60h] [rbp+27h]
  __int128 v16; // [rsp+68h] [rbp+2Fh]
  __int64 v17; // [rsp+78h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  TokenHandle = 0;
  InitPointer = Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(&TokenHandle);
  ImpersonationToken = ComGetImpersonationToken(InitPointer);
  v2 = ImpersonationToken;
  if ( ImpersonationToken >= 0 )
  {
    v14 = 0x2050000000000LL;
    v15 = 0x22000000020LL;
    v13 = 0;
    v17 = 0;
    v16 = 0;
    v5 = AclCheckAccess(TokenHandle);
    v2 = v5;
    if ( v5 == 1 )
    {
      v2 = -2147024891;
      v12 = -2147024891;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed administrator access check.");
        *(_QWORD *)v10 = &v12;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v6,
          3,
          (unsigned int)": {}",
          (__int64)v10);
      }
      v4 = 239;
    }
    else
    {
      if ( v5 >= 0 )
      {
        v2 = 0;
        goto LABEL_15;
      }
      v12 = v5;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to determine credentials for access check.");
        *(_QWORD *)v10 = &v12;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v7,
          3,
          (unsigned int)": {}",
          (__int64)v10);
      }
      v4 = 241;
    }
  }
  else
  {
    v12 = ImpersonationToken;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Failed to get user token to test for admin credentials.");
      *(_QWORD *)v10 = &v12;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v3,
        3,
        (unsigned int)": {}",
        (__int64)v10);
    }
    v4 = 232;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecore\\base\\cbs\\util\\cbspriv.cpp",
    (const char *)v2,
    v9);
LABEL_15:
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&TokenHandle);
  return v2;
}

```

## disassembly

```asm
0x1400200b8  mov     [rsp-8+arg_0], rbx
0x1400200bd  push    rbp
0x1400200be  lea     rbp, [rsp-57h]
0x1400200c3  sub     rsp, 90h
0x1400200ca  mov     rax, cs:__security_cookie
0x1400200d1  xor     rax, rsp
0x1400200d4  mov     [rbp+57h+var_10], rax
0x1400200d8  lea     rcx, [rbp+57h+TokenHandle]
0x1400200dc  mov     [rbp+57h+TokenHandle], 0
0x1400200e4  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x1400200e9  mov     rcx, rax
0x1400200ec  call    ComGetImpersonationToken
0x1400200f1  mov     ebx, eax
0x1400200f3  test    eax, eax
0x1400200f5  jns     short loc_14002014C
0x1400200f7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400200fe  mov     [rbp+57h+var_50], eax
0x140020101  test    rcx, rcx
0x140020104  jz      short loc_140020142
0x140020106  xor     edx, edx
0x140020108  lea     r9, aFailedToGetUse; "Failed to get user token to test for ad"...
0x14002010f  lea     r8d, [rdx+3]
0x140020113  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140020118  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002011f  lea     rax, [rbp+57h+var_50]
0x140020123  mov     qword ptr [rbp+57h+var_60], rax
0x140020127  lea     r9, asc_1400353E8; ": {}"
0x14002012e  lea     rax, [rbp+57h+var_60]
0x140020132  mov     r8d, 3
0x140020138  mov     qword ptr [rsp+90h+var_70], rax
0x14002013d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140020142  mov     edx, 0E8h
0x140020147  jmp     loc_1400201DE
0x14002014c  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x140020150  lea     rdx, [rbp+57h+var_48]
0x140020154  xorps   xmm0, xmm0
0x140020157  xor     eax, eax
0x140020159  movups  [rbp+57h+var_38], xmm0
0x14002015d  mov     word ptr [rbp+57h+var_38+5], 205h
0x140020163  mov     dword ptr [rbp+57h+var_38+8], 20h ; ' '
0x14002016a  mov     dword ptr [rbp+57h+var_38+0Ch], 220h
0x140020171  movups  [rbp+57h+var_48], xmm0
0x140020175  mov     [rbp+57h+var_18], rax
0x140020179  movups  [rbp+57h+var_28], xmm0
0x14002017d  call    AclCheckAccess
0x140020182  mov     ebx, eax
0x140020184  cmp     eax, 1
0x140020187  jnz     short loc_1400201F3
0x140020189  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140020190  mov     ebx, 80070005h
0x140020195  mov     [rbp+57h+var_50], ebx
0x140020198  test    rcx, rcx
0x14002019b  jz      short loc_1400201D9
0x14002019d  lea     r9, aFailedAdminist; "Failed administrator access check."
0x1400201a4  xor     edx, edx
0x1400201a6  lea     r8d, [rax+2]
0x1400201aa  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400201af  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400201b6  lea     rax, [rbp+57h+var_50]
0x1400201ba  mov     qword ptr [rbp+57h+var_60], rax
0x1400201be  lea     r9, asc_1400353E8; ": {}"
0x1400201c5  lea     rax, [rbp+57h+var_60]
0x1400201c9  mov     r8d, 3
0x1400201cf  mov     qword ptr [rsp+90h+var_70], rax; int
0x1400201d4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400201d9  mov     edx, 0EFh; void *
0x1400201de  mov     rcx, [rbp+5Fh]; this
0x1400201e2  lea     r8, aOnecoreBaseCbs_11; "onecore\\base\\cbs\\util\\cbspriv.cpp"
0x1400201e9  mov     r9d, ebx; char *
0x1400201ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400201f1  jmp     short loc_14002024B
0x1400201f3  test    ebx, ebx
0x1400201f5  jns     short loc_140020249
0x1400201f7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400201fe  mov     [rbp+57h+var_50], ebx
0x140020201  test    rcx, rcx
0x140020204  jz      short loc_140020242
0x140020206  xor     edx, edx
0x140020208  lea     r9, aFailedToDeterm; "Failed to determine credentials for acc"...
0x14002020f  lea     r8d, [rdx+3]
0x140020213  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140020218  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002021f  lea     rax, [rbp+57h+var_50]
0x140020223  mov     qword ptr [rbp+57h+var_60], rax
0x140020227  lea     r9, asc_1400353E8; ": {}"
0x14002022e  lea     rax, [rbp+57h+var_60]
0x140020232  mov     r8d, 3
0x140020238  mov     qword ptr [rsp+90h+var_70], rax
0x14002023d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140020242  mov     edx, 0F1h
0x140020247  jmp     short loc_1400201DE
0x140020249  xor     ebx, ebx
0x14002024b  lea     rcx, [rbp+57h+TokenHandle]
0x14002024f  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x140020254  mov     eax, ebx
0x140020256  mov     rcx, [rbp+57h+var_10]
0x14002025a  xor     rcx, rsp; StackCookie
0x14002025d  call    __security_check_cookie
0x140020262  mov     rbx, [rsp+90h+arg_0]
0x14002026a  add     rsp, 90h
0x140020271  pop     rbp
0x140020272  retn
```
