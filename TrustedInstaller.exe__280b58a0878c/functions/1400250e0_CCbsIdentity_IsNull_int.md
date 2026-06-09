# CCbsIdentity::IsNull(int *)

- ea: `0x1400250e0`
- end: `0x14002518a`
- name: `?IsNull@CCbsIdentity@@UEAAJPEAH@Z`
- size: `170`
- prototype: `__int64 __fastcall(CCbsIdentity *__hidden this, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140016a40`
- `0x140016fb4`
- `0x1400250e0`

## string_xrefs

- `0x14002514e`: `onecore\base\cbs\identityutil\cbsidentity.cpp`

## pseudocode

```c
__int64 __fastcall CCbsIdentity::IsNull(CCbsIdentity *this, int *a2)
{
  __int64 v2; // rdx
  int v4; // [rsp+20h] [rbp-38h]
  int v5[2]; // [rsp+30h] [rbp-28h] BYREF
  int v6; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( a2 )
  {
    *a2 = *((_DWORD *)this + 6) == 0;
    return 0;
  }
  else
  {
    v6 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Invalid argument: pbIsNull");
      *(_QWORD *)v5 = &v6;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v2,
        3,
        (__int64)": {}",
        (__int64)v5);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecore\\base\\cbs\\identityutil\\cbsidentity.cpp",
      (const char *)0x80004003LL,
      v4);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x1400250e0  sub     rsp, 58h
0x1400250e4  mov     rax, cs:__security_cookie
0x1400250eb  xor     rax, rsp
0x1400250ee  mov     [rsp+58h+var_18], rax
0x1400250f3  test    rdx, rdx
0x1400250f6  jnz     short loc_14002516C
0x1400250f8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400250ff  mov     [rsp+58h+var_20], 80004003h
0x140025107  test    rcx, rcx
0x14002510a  jz      short loc_140025149
0x14002510c  lea     r9, aInvalidArgumen_35; "Invalid argument: pbIsNull"
0x140025113  lea     r8d, [rdx+3]
0x140025117  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14002511c  lea     rcx, [rsp+58h+var_20]
0x140025121  mov     r8d, 3
0x140025127  mov     qword ptr [rsp+58h+var_28], rcx
0x14002512c  lea     r9, asc_1400353E8; ": {}"
0x140025133  lea     rcx, [rsp+58h+var_28]
0x140025138  mov     qword ptr [rsp+58h+var_38], rcx; int
0x14002513d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140025144  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140025149  mov     rcx, [rsp+58h]; this
0x14002514e  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\identityutil\\cbsid"...
0x140025155  mov     r9d, 80004003h; char *
0x14002515b  mov     edx, 51h ; 'Q'; void *
0x140025160  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140025165  mov     eax, 80004003h
0x14002516a  jmp     short loc_140025178
0x14002516c  xor     eax, eax
0x14002516e  cmp     [rcx+18h], eax
0x140025171  setz    al
0x140025174  mov     [rdx], eax
0x140025176  xor     eax, eax
0x140025178  mov     rcx, [rsp+58h+var_18]
0x14002517d  xor     rcx, rsp; StackCookie
0x140025180  call    __security_check_cookie
0x140025185  add     rsp, 58h
0x140025189  retn
```
