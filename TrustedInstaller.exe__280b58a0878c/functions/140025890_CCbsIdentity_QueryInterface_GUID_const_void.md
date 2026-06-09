# CCbsIdentity::QueryInterface(_GUID const &,void * *)

- ea: `0x140025890`
- end: `0x14002599a`
- name: `?QueryInterface@CCbsIdentity@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `266`
- prototype: `__int64 __fastcall(CCbsIdentity *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140016a40`
- `0x140016fb4`
- `0x140025890`
- `0x14002b010`

## string_xrefs

- `0x140025900`: `onecore\base\cbs\identityutil\cbsidentity.cpp`

## pseudocode

```c
__int64 __fastcall CCbsIdentity::QueryInterface(CCbsIdentity *this, const struct _GUID *a2, void **a3)
{
  __int64 v3; // rdx
  int v5; // [rsp+20h] [rbp-38h]
  int v6[2]; // [rsp+30h] [rbp-28h] BYREF
  int v7; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( a3 )
  {
    *a3 = 0;
    if ( *(_OWORD *)&GUID_75207396_23f2_4396_85f0_8fdb879ed0ed == *(_OWORD *)a2
      || *(_QWORD *)&GUID_09381b54_9292_11d9_a1ae_0008744f7c46.Data1 == *(_QWORD *)&a2->Data1
      && *(_QWORD *)GUID_09381b54_9292_11d9_a1ae_0008744f7c46.Data4 == *(_QWORD *)a2->Data4
      || *(_QWORD *)&IID_IUnknown.Data1 == *(_QWORD *)&a2->Data1
      && *(_QWORD *)IID_IUnknown.Data4 == *(_QWORD *)a2->Data4 )
    {
      *a3 = this;
      (*(void (__fastcall **)(CCbsIdentity *))(*(_QWORD *)this + 8LL))(this);
      return 0;
    }
    else
    {
      return 2147500034LL;
    }
  }
  else
  {
    v7 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Invalid argument ppvObject");
      *(_QWORD *)v6 = &v7;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v3,
        3,
        (__int64)": {}",
        (__int64)v6);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16,
      (unsigned int)"onecore\\base\\cbs\\identityutil\\cbsidentity.cpp",
      (const char *)0x80070057LL,
      v5);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x140025890  sub     rsp, 58h
0x140025894  mov     rax, cs:__security_cookie
0x14002589b  xor     rax, rsp
0x14002589e  mov     [rsp+58h+var_18], rax
0x1400258a3  test    r8, r8
0x1400258a6  jnz     short loc_14002591E
0x1400258a8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400258af  mov     [rsp+58h+var_20], 80070057h
0x1400258b7  test    rcx, rcx
0x1400258ba  jz      short loc_1400258FB
0x1400258bc  xor     edx, edx
0x1400258be  lea     r9, aInvalidArgumen_10; "Invalid argument ppvObject"
0x1400258c5  lea     r8d, [rdx+3]
0x1400258c9  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400258ce  lea     rcx, [rsp+58h+var_20]
0x1400258d3  mov     r8d, 3
0x1400258d9  mov     qword ptr [rsp+58h+var_28], rcx
0x1400258de  lea     r9, asc_1400353E8; ": {}"
0x1400258e5  lea     rcx, [rsp+58h+var_28]
0x1400258ea  mov     qword ptr [rsp+58h+var_38], rcx; int
0x1400258ef  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400258f6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400258fb  mov     rcx, [rsp+58h]; this
0x140025900  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\identityutil\\cbsid"...
0x140025907  mov     r9d, 80070057h; char *
0x14002590d  mov     edx, 16h; void *
0x140025912  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140025917  mov     eax, 80070057h
0x14002591c  jmp     short loc_140025988
0x14002591e  mov     qword ptr [r8], 0
0x140025925  mov     rax, qword ptr cs:_GUID_75207396_23f2_4396_85f0_8fdb879ed0ed.Data1
0x14002592c  cmp     rax, [rdx]
0x14002592f  jnz     short loc_14002593E
0x140025931  mov     rax, qword ptr cs:_GUID_75207396_23f2_4396_85f0_8fdb879ed0ed.Data4
0x140025938  cmp     rax, [rdx+8]
0x14002593c  jz      short loc_140025970
0x14002593e  mov     rax, qword ptr cs:_GUID_09381b54_9292_11d9_a1ae_0008744f7c46.Data1
0x140025945  cmp     rax, [rdx]
0x140025948  jnz     short loc_140025957
0x14002594a  mov     rax, qword ptr cs:_GUID_09381b54_9292_11d9_a1ae_0008744f7c46.Data4
0x140025951  cmp     rax, [rdx+8]
0x140025955  jz      short loc_140025970
0x140025957  mov     rax, qword ptr cs:IID_IUnknown.Data1
0x14002595e  cmp     rax, [rdx]
0x140025961  jnz     short loc_140025983
0x140025963  mov     rax, qword ptr cs:IID_IUnknown.Data4
0x14002596a  cmp     rax, [rdx+8]
0x14002596e  jnz     short loc_140025983
0x140025970  mov     [r8], rcx
0x140025973  mov     rax, [rcx]
0x140025976  mov     rax, [rax+8]
0x14002597a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002597f  xor     eax, eax
0x140025981  jmp     short loc_140025988
0x140025983  mov     eax, 80004002h
0x140025988  mov     rcx, [rsp+58h+var_18]
0x14002598d  xor     rcx, rsp; StackCookie
0x140025990  call    __security_check_cookie
0x140025995  add     rsp, 58h
0x140025999  retn
```
