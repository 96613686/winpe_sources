# CCbsIdentity::IsEqual(ICbsIdentity *,int *)

- ea: `0x140024e40`
- end: `0x1400250c2`
- name: `?IsEqual@CCbsIdentity@@UEAAJPEAUICbsIdentity@@PEAH@Z`
- size: `642`
- prototype: `__int64 __fastcall(CCbsIdentity *this, __int64 (__fastcall ***)(struct ICbsIdentity *, GUID *, int *), int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140016a40`
- `0x140016fb4`
- `0x140024e40`
- `0x14002b010`

## string_xrefs

- `0x140024ec1`: `onecore\base\cbs\identityutil\cbsidentity.cpp`
- `0x140024fbe`: `onecore\base\cbs\identityutil\cbsidentity.cpp`
- `0x140024f7d`: `Unknown interface to compare against.`

## pseudocode

```c
__int64 __fastcall CCbsIdentity::IsEqual(
        CCbsIdentity *this,
        __int64 (__fastcall ***a2)(struct ICbsIdentity *, GUID *, int *),
        int *a3)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v8; // rdx
  __int64 (__fastcall **v9)(struct ICbsIdentity *, GUID *, int *); // rax
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // rdx
  int v15; // [rsp+20h] [rbp-40h]
  int v16[2]; // [rsp+40h] [rbp-20h] BYREF
  int v17; // [rsp+48h] [rbp-18h] BYREF
  int v18[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  if ( !a2 )
  {
    v4 = -2147467261;
    v17 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Invalid argument: pIdentity");
      *(_QWORD *)v18 = &v17;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v5,
        3,
        (__int64)": {}",
        (__int64)v18);
    }
    v6 = 89;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\cbs\\identityutil\\cbsidentity.cpp",
      (const char *)0x80004003LL,
      v15);
    return v4;
  }
  if ( !a3 )
  {
    v4 = -2147467261;
    v17 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Invalid argument: pbIsEqual");
      *(_QWORD *)v18 = &v17;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v8,
        3,
        (__int64)": {}",
        (__int64)v18);
    }
    v6 = 90;
    goto LABEL_5;
  }
  if ( *((_DWORD *)this + 6) )
  {
    v9 = *a2;
    *(_QWORD *)v18 = 0;
    v10 = (*v9)((struct ICbsIdentity *)a2, &GUID_09381b54_9292_11d9_a1ae_0008744f7c46, v18);
    v4 = v10;
    if ( v10 < 0 )
    {
      v17 = v10;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Unknown interface to compare against.");
        *(_QWORD *)v16 = &v17;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v11,
          3,
          (__int64)": {}",
          (__int64)v16);
      }
      v12 = 98;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\base\\cbs\\identityutil\\cbsidentity.cpp",
        (const char *)v4,
        v15);
      if ( *(_QWORD *)v18 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v18 + 16LL))(*(_QWORD *)v18);
      return v4;
    }
    v15 = (_DWORD)this + 584;
    v13 = (*(__int64 (__fastcall **)(_QWORD, char *, char *, char *))(**(_QWORD **)v18 + 80LL))(
            *(_QWORD *)v18,
            (char *)this + 30,
            (char *)this + 550,
            (char *)this + 648);
    v4 = v13;
    if ( v13 < 0 )
    {
      v17 = v13;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to test InternalIsEqualbyAttribute");
        *(_QWORD *)v16 = &v17;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v14,
          3,
          (__int64)": {}",
          (__int64)v16);
      }
      v12 = 103;
      goto LABEL_16;
    }
    if ( *(_QWORD *)v18 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v18 + 16LL))(*(_QWORD *)v18);
  }
  else
  {
    *a3 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x140024e40  mov     [rsp-18h+arg_18], rbx
0x140024e45  push    rbp
0x140024e46  push    rsi
0x140024e47  push    rdi
0x140024e48  mov     rbp, rsp
0x140024e4b  sub     rsp, 60h
0x140024e4f  mov     rax, cs:__security_cookie
0x140024e56  xor     rax, rsp
0x140024e59  mov     [rbp+var_8], rax
0x140024e5d  mov     rdi, r8
0x140024e60  mov     r9, rdx
0x140024e63  mov     rsi, rcx
0x140024e66  test    rdx, rdx
0x140024e69  jnz     short loc_140024ED7
0x140024e6b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140024e72  mov     ebx, 80004003h
0x140024e77  mov     [rbp+var_18], ebx
0x140024e7a  test    rcx, rcx
0x140024e7d  jz      short loc_140024EB8
0x140024e7f  lea     edi, [rdx+3]
0x140024e82  mov     r8d, edi
0x140024e85  lea     r9, aInvalidArgumen_27; "Invalid argument: pIdentity"
0x140024e8c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140024e91  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140024e98  lea     rax, [rbp+var_18]
0x140024e9c  mov     qword ptr [rbp+var_10], rax
0x140024ea0  lea     r9, asc_1400353E8; ": {}"
0x140024ea7  lea     rax, [rbp+var_10]
0x140024eab  mov     r8d, edi
0x140024eae  mov     qword ptr [rsp+60h+var_40], rax; int
0x140024eb3  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140024eb8  mov     edx, 59h ; 'Y'; void *
0x140024ebd  mov     rcx, [rbp+18h]; this
0x140024ec1  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\identityutil\\cbsid"...
0x140024ec8  mov     r9d, ebx; char *
0x140024ecb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140024ed0  mov     eax, ebx
0x140024ed2  jmp     loc_1400250A6
0x140024ed7  test    rdi, rdi
0x140024eda  jnz     short loc_140024F34
0x140024edc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140024ee3  mov     ebx, 80004003h
0x140024ee8  mov     [rbp+var_18], ebx
0x140024eeb  test    rcx, rcx
0x140024eee  jz      short loc_140024F2D
0x140024ef0  mov     edi, 3
0x140024ef5  lea     r9, aInvalidArgumen_37; "Invalid argument: pbIsEqual"
0x140024efc  mov     r8d, edi
0x140024eff  xor     edx, edx
0x140024f01  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140024f06  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140024f0d  lea     rax, [rbp+var_18]
0x140024f11  mov     qword ptr [rbp+var_10], rax
0x140024f15  lea     r9, asc_1400353E8; ": {}"
0x140024f1c  lea     rax, [rbp+var_10]
0x140024f20  mov     r8d, edi
0x140024f23  mov     qword ptr [rsp+60h+var_40], rax
0x140024f28  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140024f2d  mov     edx, 5Ah ; 'Z'
0x140024f32  jmp     short loc_140024EBD
0x140024f34  cmp     dword ptr [rcx+18h], 0
0x140024f38  jz      loc_14002509D
0x140024f3e  mov     rax, [rdx]
0x140024f41  lea     r8, [rbp+var_10]
0x140024f45  lea     rdx, _GUID_09381b54_9292_11d9_a1ae_0008744f7c46
0x140024f4c  mov     qword ptr [rbp+var_10], 0
0x140024f54  mov     rcx, r9
0x140024f57  mov     rax, [rax]
0x140024f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024f5f  mov     ebx, eax
0x140024f61  test    eax, eax
0x140024f63  jns     loc_140024FEB
0x140024f69  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140024f70  mov     [rbp+var_18], eax
0x140024f73  test    rcx, rcx
0x140024f76  jz      short loc_140024FB5
0x140024f78  mov     edi, 3
0x140024f7d  lea     r9, aUnknownInterfa; "Unknown interface to compare against."
0x140024f84  mov     r8d, edi
0x140024f87  xor     edx, edx
0x140024f89  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140024f8e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140024f95  lea     rax, [rbp+var_18]
0x140024f99  mov     qword ptr [rbp+var_20], rax
0x140024f9d  lea     r9, asc_1400353E8; ": {}"
0x140024fa4  lea     rax, [rbp+var_20]
0x140024fa8  mov     r8d, edi
0x140024fab  mov     qword ptr [rsp+60h+var_40], rax; int
0x140024fb0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140024fb5  mov     edx, 62h ; 'b'; void *
0x140024fba  mov     rcx, [rbp+18h]; this
0x140024fbe  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\identityutil\\cbsid"...
0x140024fc5  mov     r9d, ebx; char *
0x140024fc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140024fcd  mov     rcx, qword ptr [rbp+var_10]
0x140024fd1  test    rcx, rcx
0x140024fd4  jz      loc_140024ED0
0x140024fda  mov     rax, [rcx]
0x140024fdd  mov     rax, [rax+10h]
0x140024fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024fe6  jmp     loc_140024ED0
0x140024feb  mov     rcx, qword ptr [rbp+var_10]
0x140024fef  lea     r10, [rsi+2C8h]
0x140024ff6  lea     r11, [rsi+248h]
0x140024ffd  mov     [rsp+60h+var_30], rdi
0x140025002  mov     [rsp+60h+var_38], r10
0x140025007  lea     r9, [rsi+288h]
0x14002500e  lea     r8, [rsi+226h]
0x140025015  mov     qword ptr [rsp+60h+var_40], r11
0x14002501a  mov     rax, [rcx]
0x14002501d  lea     rdx, [rsi+1Eh]
0x140025021  mov     rax, [rax+50h]
0x140025025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002502a  mov     ebx, eax
0x14002502c  test    eax, eax
0x14002502e  jns     short loc_140025086
0x140025030  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140025037  mov     [rbp+var_18], eax
0x14002503a  test    rcx, rcx
0x14002503d  jz      short loc_14002507C
0x14002503f  mov     edi, 3
0x140025044  lea     r9, aFailedToTestIn; "Failed to test InternalIsEqualbyAttribu"...
0x14002504b  mov     r8d, edi
0x14002504e  xor     edx, edx
0x140025050  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140025055  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002505c  lea     rax, [rbp+var_18]
0x140025060  mov     qword ptr [rbp+var_20], rax
0x140025064  lea     r9, asc_1400353E8; ": {}"
0x14002506b  lea     rax, [rbp+var_20]
0x14002506f  mov     r8d, edi
0x140025072  mov     qword ptr [rsp+60h+var_40], rax
0x140025077  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14002507c  mov     edx, 67h ; 'g'
0x140025081  jmp     loc_140024FBA
0x140025086  mov     rcx, qword ptr [rbp+var_10]
0x14002508a  test    rcx, rcx
0x14002508d  jz      short loc_1400250A4
0x14002508f  mov     rax, [rcx]
0x140025092  mov     rax, [rax+10h]
0x140025096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002509b  jmp     short loc_1400250A4
0x14002509d  mov     dword ptr [r8], 0
0x1400250a4  xor     eax, eax
0x1400250a6  mov     rcx, [rbp+var_8]
0x1400250aa  xor     rcx, rsp; StackCookie
0x1400250ad  call    __security_check_cookie
0x1400250b2  mov     rbx, [rsp+60h+arg_18]
0x1400250ba  add     rsp, 60h
0x1400250be  pop     rdi
0x1400250bf  pop     rsi
0x1400250c0  pop     rbp
0x1400250c1  retn
```
