# ShredStringIdIntoAttributes(wchar_t *,wchar_t,wchar_t const * *,wchar_t const * *,wchar_t const * *,wchar_t const * *,wchar_t const * *)

- ea: `0x140024324`
- end: `0x140024561`
- name: `?ShredStringIdIntoAttributes@@YAJPEA_W_WPEAPEB_W2222@Z`
- size: `573`
- prototype: `__int64 __fastcall(wchar_t *, wchar_t, const wchar_t **, const wchar_t **, const wchar_t **, const wchar_t **, const wchar_t **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x140025540`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140016a40`
- `0x140016fb4`
- `0x14001e95c`
- `0x140023f60`
- `0x140023f90`
- `0x140024324`
- `0x140025c08`

## string_xrefs

- `0x140024434`: `onecore\base\cbs\identityutil\cbsidentityutil.cpp`
- `0x14002445c`: `onecore\base\cbs\identityutil\cbsidentityutil.cpp`

## pseudocode

```c
int __fastcall ShredStringIdIntoAttributes(
        wchar_t *a1,
        wchar_t a2,
        const wchar_t **a3,
        const wchar_t **a4,
        const wchar_t **a5,
        const wchar_t **a6,
        const wchar_t **a7)
{
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // rdx
  int inited; // eax
  int v15; // eax
  __int64 v16; // rdx
  int v17; // [rsp+20h] [rbp-C1h]
  int v18[2]; // [rsp+40h] [rbp-A1h] BYREF
  __int128 v19; // [rsp+48h] [rbp-99h] BYREF
  __int64 v20; // [rsp+58h] [rbp-89h]
  __int128 v21; // [rsp+60h] [rbp-81h] BYREF
  __int64 v22; // [rsp+70h] [rbp-71h]
  __int128 v23; // [rsp+78h] [rbp-69h] BYREF
  __int64 v24; // [rsp+88h] [rbp-59h]
  __int128 v25; // [rsp+90h] [rbp-51h] BYREF
  __int64 v26; // [rsp+A0h] [rbp-41h]
  __int128 v27; // [rsp+A8h] [rbp-39h] BYREF
  __int64 v28; // [rsp+B8h] [rbp-29h]
  __int128 v29; // [rsp+C0h] [rbp-21h] BYREF
  __int64 v30; // [rsp+D0h] [rbp-11h]
  int v31; // [rsp+D8h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+47h]

  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = 0;
  if ( a7 )
    *a7 = 0;
  v20 = 0;
  v22 = 0;
  v24 = 0;
  v26 = 0;
  v28 = 0;
  v30 = 0;
  v19 = 0;
  v21 = 0;
  v23 = 0;
  v25 = 0;
  v27 = 0;
  v29 = 0;
  if ( !a1 )
  {
    v10 = -2147024809;
    v31 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No identity specified");
      *(_QWORD *)v18 = &v31;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v11,
        3,
        (__int64)": {}",
        (__int64)v18);
    }
    v12 = 372;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\cbs\\identityutil\\cbsidentityutil.cpp",
      (const char *)v10,
      v17);
    return v10;
  }
  inited = RtlInitLUnicodeStringFromNullTerminatedString(a1, &v19);
  if ( inited < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x176,
             (unsigned int)"onecore\\base\\cbs\\identityutil\\cbsidentityutil.cpp",
             (const char *)(unsigned int)inited,
             v17);
  v15 = ShredStringIdIntoAttributes(
          (const struct _LUNICODE_STRING *)&v19,
          a2,
          (struct _LUNICODE_STRING *)&v21,
          (struct _LUNICODE_STRING *)&v23,
          (struct _LUNICODE_STRING *)&v25,
          (struct _LUNICODE_STRING *)&v27,
          (struct _LUNICODE_STRING *)&v29);
  v10 = v15;
  if ( v15 < 0 )
  {
    v31 = v15;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to shred identity.");
      *(_QWORD *)v18 = &v31;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v16,
        3,
        (__int64)": {}",
        (__int64)v18);
    }
    v12 = 378;
    goto LABEL_15;
  }
  SetCStringAttribute(&v21, a3);
  SetCStringAttribute(&v23, a4);
  SetCStringAttribute(&v25, a5);
  SetCStringAttribute(&v27, a6);
  SetCStringAttribute(&v29, a7);
  return 0;
}

```

## disassembly

```asm
0x140024324  push    rbp
0x140024326  push    rbx
0x140024327  push    rsi
0x140024328  push    rdi
0x140024329  push    r12
0x14002432b  push    r14
0x14002432d  push    r15
0x14002432f  lea     rbp, [rsp-0Fh]
0x140024334  sub     rsp, 0F0h
0x14002433b  mov     rax, cs:__security_cookie
0x140024342  xor     rax, rsp
0x140024345  mov     [rbp+3Fh+var_40], rax
0x140024349  mov     rsi, [rbp+3Fh+arg_20]
0x14002434d  mov     rdi, r9
0x140024350  mov     r14, [rbp+3Fh+arg_28]
0x140024354  mov     r12, r8
0x140024357  mov     r15, [rbp+3Fh+arg_30]
0x14002435b  movzx   ebx, dx
0x14002435e  test    r8, r8
0x140024361  jz      short loc_14002436A
0x140024363  mov     qword ptr [r8], 0
0x14002436a  test    rdi, rdi
0x14002436d  jz      short loc_140024376
0x14002436f  mov     qword ptr [r9], 0
0x140024376  test    rsi, rsi
0x140024379  jz      short loc_140024382
0x14002437b  mov     qword ptr [rsi], 0
0x140024382  test    r14, r14
0x140024385  jz      short loc_14002438E
0x140024387  mov     qword ptr [r14], 0
0x14002438e  test    r15, r15
0x140024391  jz      short loc_14002439A
0x140024393  mov     qword ptr [r15], 0
0x14002439a  xor     eax, eax
0x14002439c  xorps   xmm0, xmm0
0x14002439f  mov     [rsp+120h+var_C8], rax
0x1400243a4  xorps   xmm1, xmm1
0x1400243a7  mov     [rbp+3Fh+var_B0], rax
0x1400243ab  mov     [rbp+3Fh+var_98], rax
0x1400243af  mov     [rbp+3Fh+var_80], rax
0x1400243b3  mov     [rbp+3Fh+var_68], rax
0x1400243b7  mov     [rbp+3Fh+var_50], rax
0x1400243bb  movups  [rsp+120h+var_D8], xmm0
0x1400243c0  movups  [rsp+120h+var_C0], xmm1
0x1400243c5  movups  [rbp+3Fh+var_A8], xmm0
0x1400243c9  movups  [rbp+3Fh+var_90], xmm1
0x1400243cd  movups  [rbp+3Fh+var_78], xmm0
0x1400243d1  movups  [rbp+3Fh+var_60], xmm1
0x1400243d5  test    rcx, rcx
0x1400243d8  jnz     short loc_14002444A
0x1400243da  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400243e1  mov     ebx, 80070057h
0x1400243e6  mov     [rbp+3Fh+var_48], ebx
0x1400243e9  test    rcx, rcx
0x1400243ec  jz      short loc_14002442B
0x1400243ee  lea     edi, [rax+3]
0x1400243f1  xor     edx, edx
0x1400243f3  mov     r8d, edi
0x1400243f6  lea     r9, aNoIdentitySpec; "No identity specified"
0x1400243fd  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140024402  lea     rcx, [rsp+120h+var_E0]
0x140024407  mov     r8d, edi
0x14002440a  mov     [rsp+120h+var_100], rcx; int
0x14002440f  lea     rax, [rbp+3Fh+var_48]
0x140024413  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002441a  lea     r9, asc_1400353E8; ": {}"
0x140024421  mov     qword ptr [rsp+120h+var_E0], rax
0x140024426  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14002442b  mov     edx, 174h; void *
0x140024430  mov     rcx, [rbp+47h]; this
0x140024434  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\identityutil\\cbsid"...
0x14002443b  mov     r9d, ebx; char *
0x14002443e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140024443  mov     eax, ebx
0x140024445  jmp     loc_140024543
0x14002444a  lea     rdx, [rsp+120h+var_D8]
0x14002444f  call    RtlInitLUnicodeStringFromNullTerminatedString
0x140024454  test    eax, eax
0x140024456  jns     short loc_140024475
0x140024458  mov     rcx, [rbp+47h]; this
0x14002445c  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\identityutil\\cbsid"...
0x140024463  mov     r9d, eax; char *
0x140024466  mov     edx, 176h; void *
0x14002446b  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x140024470  jmp     loc_140024543
0x140024475  lea     rax, [rbp+3Fh+var_60]
0x140024479  movzx   edx, bx; wchar_t
0x14002447c  mov     [rsp+120h+var_F0], rax; struct _LUNICODE_STRING *
0x140024481  lea     r9, [rbp+3Fh+var_A8]; struct _LUNICODE_STRING *
0x140024485  lea     rax, [rbp+3Fh+var_78]
0x140024489  mov     [rsp+120h+var_F8], rax; struct _LUNICODE_STRING *
0x14002448e  lea     r8, [rsp+120h+var_C0]; struct _LUNICODE_STRING *
0x140024493  lea     rax, [rbp+3Fh+var_90]
0x140024497  lea     rcx, [rsp+120h+var_D8]; struct _LUNICODE_STRING *
0x14002449c  mov     [rsp+120h+var_100], rax; struct _LUNICODE_STRING *
0x1400244a1  call    ?ShredStringIdIntoAttributes@@YAJAEBU_LUNICODE_STRING@@_WPEAU1@2222@Z; ShredStringIdIntoAttributes(_LUNICODE_STRING const &,wchar_t,_LUNICODE_STRING *,_LUNICODE_STRING *,_LUNICODE_STRING *,_LUNICODE_STRING *,_LUNICODE_STRING *)
0x1400244a6  mov     ebx, eax
0x1400244a8  test    eax, eax
0x1400244aa  jns     short loc_140024504
0x1400244ac  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400244b3  mov     [rbp+3Fh+var_48], eax
0x1400244b6  test    rcx, rcx
0x1400244b9  jz      short loc_1400244FA
0x1400244bb  mov     edi, 3
0x1400244c0  lea     r9, aFailedToShredI; "Failed to shred identity."
0x1400244c7  mov     r8d, edi
0x1400244ca  xor     edx, edx
0x1400244cc  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400244d1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400244d8  lea     rax, [rbp+3Fh+var_48]
0x1400244dc  mov     qword ptr [rsp+120h+var_E0], rax
0x1400244e1  lea     r9, asc_1400353E8; ": {}"
0x1400244e8  lea     rax, [rsp+120h+var_E0]
0x1400244ed  mov     r8d, edi
0x1400244f0  mov     [rsp+120h+var_100], rax
0x1400244f5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400244fa  mov     edx, 17Ah
0x1400244ff  jmp     loc_140024430
0x140024504  mov     rdx, r12
0x140024507  lea     rcx, [rsp+120h+var_C0]
0x14002450c  call    SetCStringAttribute
0x140024511  lea     rcx, [rbp+3Fh+var_A8]
0x140024515  mov     rdx, rdi
0x140024518  call    SetCStringAttribute
0x14002451d  lea     rcx, [rbp+3Fh+var_90]
0x140024521  mov     rdx, rsi
0x140024524  call    SetCStringAttribute
0x140024529  lea     rcx, [rbp+3Fh+var_78]
0x14002452d  mov     rdx, r14
0x140024530  call    SetCStringAttribute
0x140024535  lea     rcx, [rbp+3Fh+var_60]
0x140024539  mov     rdx, r15
0x14002453c  call    SetCStringAttribute
0x140024541  xor     eax, eax
0x140024543  mov     rcx, [rbp+3Fh+var_40]
0x140024547  xor     rcx, rsp; StackCookie
0x14002454a  call    __security_check_cookie
0x14002454f  add     rsp, 0F0h
0x140024556  pop     r15
0x140024558  pop     r14
0x14002455a  pop     r12
0x14002455c  pop     rdi
0x14002455d  pop     rsi
0x14002455e  pop     rbx
0x14002455f  pop     rbp
0x140024560  retn
```
