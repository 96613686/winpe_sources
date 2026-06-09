# SetPrivilegesById

- ea: `0x1400206cc`
- end: `0x1400207e0`
- name: `SetPrivilegesById`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x14002027c`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140016a40`
- `0x140016fb4`
- `0x140019bb8`
- `0x14001b210`
- `0x1400203b8`
- `0x1400206cc`

## string_xrefs

- `0x140020767`: `Failed to set privileges.`

## pseudocode

```c
__int64 __fastcall SetPrivilegesById(__int64 a1, __int64 a2, __int64 a3, __int64 a4, struct _TOKEN_PRIVILEGES **a5)
{
  __int64 v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rdx
  char *v8; // rdx
  int v9; // eax
  __int64 v10; // rdx
  int v12; // [rsp+20h] [rbp-38h]
  char *v13; // [rsp+30h] [rbp-28h] BYREF
  int v14[2]; // [rsp+38h] [rbp-20h] BYREF
  __int64 v15; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v13 = 0;
  if ( Windows::AutoNewArrayPtr<unsigned char>::AllocateArray(&v13, 0x10u) )
  {
    v8 = v13;
    *(_OWORD *)v13 = 0;
    *(_DWORD *)v8 = 1;
    v15 = PRIVILEGES_SHUTDOWN;
    *(_QWORD *)(v8 + 4) = PRIVILEGES_SHUTDOWN;
    *((_DWORD *)v8 + 3) = 2;
    v9 = SetPrivileges(v5, (struct _TOKEN_PRIVILEGES *)v8, a5);
    v6 = v9;
    if ( v9 >= 0 )
    {
      v6 = 0;
      goto LABEL_9;
    }
    LODWORD(v15) = v9;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to set privileges.");
      *(_QWORD *)v14 = &v15;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v10,
        3,
        (__int64)": {}",
        (__int64)v14);
    }
    v7 = 135;
  }
  else
  {
    v6 = -2147024882;
    v7 = 121;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecore\\base\\cbs\\util\\cbspriv.cpp",
    (const char *)v6,
    v12);
LABEL_9:
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close((void **)&v13);
  return v6;
}

```

## disassembly

```asm
0x1400206cc  push    rbx
0x1400206ce  sub     rsp, 50h
0x1400206d2  mov     rax, cs:__security_cookie
0x1400206d9  xor     rax, rsp
0x1400206dc  mov     [rsp+58h+var_10], rax
0x1400206e1  mov     rbx, [rsp+58h+arg_20]
0x1400206e9  lea     rcx, [rsp+58h+var_28]
0x1400206ee  mov     edx, 10h
0x1400206f3  mov     [rsp+58h+var_28], 0
0x1400206fc  call    ?AllocateArray@?$AutoNewArrayPtr@E@Windows@@QEAAPEAE_K@Z; Windows::AutoNewArrayPtr<uchar>::AllocateArray(unsigned __int64)
0x140020701  test    rax, rax
0x140020704  jnz     short loc_140020713
0x140020706  mov     ebx, 8007000Eh
0x14002070b  lea     edx, [rax+79h]
0x14002070e  jmp     loc_1400207A9
0x140020713  mov     rdx, [rsp+58h+var_28]
0x140020718  xorps   xmm0, xmm0
0x14002071b  mov     r8, rbx
0x14002071e  movups  xmmword ptr [rdx], xmm0
0x140020721  mov     dword ptr [rdx], 1
0x140020727  movsxd  rax, cs:PRIVILEGES_SHUTDOWN
0x14002072e  mov     dword ptr [rsp+58h+var_18], eax
0x140020732  shr     rax, 20h
0x140020736  mov     dword ptr [rsp+58h+var_18+4], eax
0x14002073a  mov     rax, [rsp+58h+var_18]
0x14002073f  mov     [rdx+4], rax
0x140020743  mov     dword ptr [rdx+0Ch], 2
0x14002074a  call    SetPrivileges
0x14002074f  mov     ebx, eax
0x140020751  test    eax, eax
0x140020753  jns     short loc_1400207BF
0x140020755  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002075c  mov     dword ptr [rsp+58h+var_18], eax
0x140020760  test    rcx, rcx
0x140020763  jz      short loc_1400207A4
0x140020765  xor     edx, edx
0x140020767  lea     r9, aFailedToSetPri; "Failed to set privileges."
0x14002076e  lea     r8d, [rdx+3]
0x140020772  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140020777  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002077e  lea     rax, [rsp+58h+var_18]
0x140020783  mov     qword ptr [rsp+58h+var_20], rax
0x140020788  lea     r9, asc_1400353E8; ": {}"
0x14002078f  lea     rax, [rsp+58h+var_20]
0x140020794  mov     r8d, 3
0x14002079a  mov     qword ptr [rsp+58h+var_38], rax; int
0x14002079f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400207a4  mov     edx, 87h; void *
0x1400207a9  mov     rcx, [rsp+58h]; this
0x1400207ae  lea     r8, aOnecoreBaseCbs_11; "onecore\\base\\cbs\\util\\cbspriv.cpp"
0x1400207b5  mov     r9d, ebx; char *
0x1400207b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400207bd  jmp     short loc_1400207C1
0x1400207bf  xor     ebx, ebx
0x1400207c1  lea     rcx, [rsp+58h+var_28]
0x1400207c6  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x1400207cb  mov     eax, ebx
0x1400207cd  mov     rcx, [rsp+58h+var_10]
0x1400207d2  xor     rcx, rsp; StackCookie
0x1400207d5  call    __security_check_cookie
0x1400207da  add     rsp, 50h
0x1400207de  pop     rbx
0x1400207df  retn
```
