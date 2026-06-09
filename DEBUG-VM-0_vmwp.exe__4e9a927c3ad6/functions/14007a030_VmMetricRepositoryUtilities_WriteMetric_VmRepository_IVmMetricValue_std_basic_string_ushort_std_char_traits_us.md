# VmMetricRepositoryUtilities::WriteMetric(VmRepository *,IVmMetricValue *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x14007a030`
- end: `0x14007a6ff`
- name: `?WriteMetric@VmMetricRepositoryUtilities@@SAXPEAVVmRepository@@PEAUIVmMetricValue@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1743`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14007b6e0`
- `0x14011a5a0`
- `0x14011a8c0`
- `0x140295008`

## callees

- `0x14002fb88`
- `0x140031c88`
- `0x14006af38`
- `0x14007a030`
- `0x14007a708`
- `0x14007a7e4`
- `0x140132940`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14007a374`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14007a374`

## string_xrefs

- `0x14007a0d9`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a109`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a139`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a169`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a199`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a1c9`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a1f9`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a229`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a259`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a28c`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a2e6`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a34e`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a3d0`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a433`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a496`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a4f9`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a55c`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a5bf`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a639`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a6a1`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a4bf`: `/lastcomputedtime`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall VmMetricRepositoryUtilities::WriteMetric(__int64 a1, __int64 a2, void *a3)
{
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  __int64 (__fastcall *v16)(__int64, _QWORD *, __int64); // r14
  __int64 v17; // rbx
  _QWORD *v18; // rax
  int v19; // eax
  __int64 (__fastcall *v20)(__int64, _QWORD *, BOOL); // r14
  BOOL v21; // ebx
  _QWORD *v22; // rax
  int v23; // eax
  __int64 (__fastcall *v24)(__int64, _QWORD *, __int64); // r14
  __int64 v25; // rbx
  _QWORD *v26; // rax
  int v27; // eax
  __int64 (__fastcall *v28)(__int64, _QWORD *, __int64); // r14
  __int64 v29; // rbx
  _QWORD *v30; // rax
  int v31; // eax
  __int64 (__fastcall *v32)(__int64, _QWORD *, __int64); // r14
  __int64 v33; // rbx
  _QWORD *v34; // rax
  int v35; // eax
  __int64 (__fastcall *v36)(__int64, _QWORD *, __int64); // r14
  __int64 v37; // rbx
  _QWORD *v38; // rax
  int v39; // eax
  __int64 (__fastcall *v40)(__int64, _QWORD *, __int64); // r14
  __int64 v41; // rbx
  _QWORD *v42; // rax
  int v43; // eax
  __int64 (__fastcall *v44)(__int64, _QWORD *, __int64); // r14
  __int64 v45; // rbx
  _QWORD *v46; // rax
  int v47; // eax
  __int64 (__fastcall *v48)(__int64, _QWORD *, unsigned __int16 *); // r14
  unsigned __int16 *v49; // rbx
  _QWORD *v50; // rax
  int v51; // eax
  __int64 (__fastcall *v52)(__int64, _QWORD *, __int64); // r14
  __int64 v53; // rbx
  _QWORD *v54; // rax
  int v55; // eax
  int v56[8]; // [rsp+20h] [rbp-69h] BYREF
  int v57; // [rsp+40h] [rbp-49h] BYREF
  unsigned int v58; // [rsp+44h] [rbp-45h] BYREF
  __int64 v59; // [rsp+48h] [rbp-41h] BYREF
  __int64 v60; // [rsp+50h] [rbp-39h] BYREF
  __int64 v61; // [rsp+58h] [rbp-31h] BYREF
  __int64 v62; // [rsp+60h] [rbp-29h] BYREF
  __int64 v63; // [rsp+68h] [rbp-21h] BYREF
  __int64 v64; // [rsp+70h] [rbp-19h] BYREF
  __int64 v65; // [rsp+78h] [rbp-11h] BYREF
  unsigned __int16 v66[8]; // [rsp+80h] [rbp-9h] BYREF
  __m128i si128; // [rsp+90h] [rbp+7h]
  struct _GUID v68; // [rsp+A0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v62 = 0;
  v57 = 0;
  v59 = 0;
  v61 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v60 = 0;
  v68 = 0;
  *(_OWORD *)v66 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v66[0] = 0;
  v58 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 32LL))(a2, &v62);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1DE,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v6,
      v56[0]);
  v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 48LL))(a2, &v57);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1DF,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v7,
      v56[0]);
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 56LL))(a2, &v59);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E0,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v8,
      v56[0]);
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 64LL))(a2, &v61);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E1,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v9,
      v56[0]);
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 72LL))(a2, &v63);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E2,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v10,
      v56[0]);
  v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 80LL))(a2, &v64);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E3,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v11,
      v56[0]);
  v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 88LL))(a2, &v65);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E4,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v12,
      v56[0]);
  v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 104LL))(a2, &v60);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E5,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v13,
      v56[0]);
  v14 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)a2 + 120LL))(a2, &v68);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E6,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v14,
      v56[0]);
  v15 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a2 + 152LL))(a2, &v58);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E7,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v15,
      v56[0]);
  v16 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)a1 + 160LL);
  v17 = v62;
  v18 = (_QWORD *)std::operator+<unsigned short>(v56, a3, (void *)L"/value");
  if ( v18[3] > 7u )
    v18 = (_QWORD *)*v18;
  v19 = v16(a1, v18, v17);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1EB,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v19,
      v56[0]);
  std::wstring::_Tidy_deallocate(v56);
  v20 = *(__int64 (__fastcall **)(__int64, _QWORD *, BOOL))(*(_QWORD *)a1 + 176LL);
  v21 = v57 == 2;
  v22 = (_QWORD *)std::operator+<unsigned short>(v56, a3, (void *)L"/enabled");
  if ( v22[3] > 7u )
    v22 = (_QWORD *)*v22;
  v23 = v20(a1, v22, v21);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1EF,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v23,
      v56[0]);
  std::wstring::_Tidy_deallocate(v56);
  if ( (unsigned int)_o__wcsicmp(v59, &qword_1402E4D20) )
  {
    v24 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)a1 + 152LL);
    v25 = v59;
    v26 = (_QWORD *)std::operator+<unsigned short>(v56, a3, (void *)L"/breakdowndimension");
    if ( v26[3] > 7u )
      v26 = (_QWORD *)*v26;
    v27 = v24(a1, v26, v25);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1F9,
        (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
        (const char *)(unsigned int)v27,
        v56[0]);
    std::wstring::_Tidy_deallocate(v56);
    v28 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)a1 + 152LL);
    v29 = v61;
    v30 = (_QWORD *)std::operator+<unsigned short>(v56, a3, (void *)L"/breakdownvalue");
    if ( v30[3] > 7u )
      v30 = (_QWORD *)*v30;
    v31 = v28(a1, v30, v29);
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1FD,
        (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
        (const char *)(unsigned int)v31,
        v56[0]);
    std::wstring::_Tidy_deallocate(v56);
  }
  v32 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)a1 + 160LL);
  v33 = v63;
  v34 = (_QWORD *)std::operator+<unsigned short>(v56, a3, (void *)L"/starttime");
  if ( v34[3] > 7u )
    v34 = (_QWORD *)*v34;
  v35 = v32(a1, v34, v33);
  if ( v35 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x202,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v35,
      v56[0]);
  std::wstring::_Tidy_deallocate(v56);
  v36 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)a1 + 160LL);
  v37 = v64;
  v38 = (_QWORD *)std::operator+<unsigned short>(v56, a3, (void *)L"/lastcomputedtime");
  if ( v38[3] > 7u )
    v38 = (_QWORD *)*v38;
  v39 = v36(a1, v38, v37);
  if ( v39 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x206,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v39,
      v56[0]);
  std::wstring::_Tidy_deallocate(v56);
  v40 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)a1 + 160LL);
  v41 = v65;
  v42 = (_QWORD *)std::operator+<unsigned short>(v56, a3, (void *)L"/peaktime");
  if ( v42[3] > 7u )
    v42 = (_QWORD *)*v42;
  v43 = v40(a1, v42, v41);
  if ( v43 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x20A,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v43,
      v56[0]);
  std::wstring::_Tidy_deallocate(v56);
  v44 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)a1 + 152LL);
  v45 = v60;
  v46 = (_QWORD *)std::operator+<unsigned short>(v56, a3, (void *)L"/poolid");
  if ( v46[3] > 7u )
    v46 = (_QWORD *)*v46;
  v47 = v44(a1, v46, v45);
  if ( v47 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x20E,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v47,
      v56[0]);
  std::wstring::_Tidy_deallocate(v56);
  Vml::VmGuid::ToString(&v68, v66);
  v48 = *(__int64 (__fastcall **)(__int64, _QWORD *, unsigned __int16 *))(*(_QWORD *)a1 + 152LL);
  v49 = v66;
  if ( si128.m128i_i64[1] > 7uLL )
    v49 = *(unsigned __int16 **)v66;
  v50 = (_QWORD *)std::operator+<unsigned short>(v56, a3, (void *)L"/resourcetypeid");
  if ( v50[3] > 7u )
    v50 = (_QWORD *)*v50;
  v51 = v48(a1, v50, v49);
  if ( v51 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x213,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v51,
      v56[0]);
  std::wstring::_Tidy_deallocate(v56);
  if ( v58 )
  {
    v52 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)a1 + 160LL);
    v53 = v58;
    v54 = (_QWORD *)std::operator+<unsigned short>(v56, a3, (void *)L"/weight");
    if ( v54[3] > 7u )
      v54 = (_QWORD *)*v54;
    v55 = v52(a1, v54, v53);
    if ( v55 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x219,
        (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
        (const char *)(unsigned int)v55,
        v56[0]);
    std::wstring::_Tidy_deallocate(v56);
  }
  std::wstring::_Tidy_deallocate(v66);
  Vml::VmBstr::~VmBstr((Vml::VmBstr *)&v60);
  Vml::VmBstr::~VmBstr((Vml::VmBstr *)&v61);
  Vml::VmBstr::~VmBstr((Vml::VmBstr *)&v59);
}

```

## disassembly

```asm
0x14007a030  push    rbp
0x14007a032  push    rbx
0x14007a033  push    rsi
0x14007a034  push    rdi
0x14007a035  push    r14
0x14007a037  lea     rbp, [rsp-37h]
0x14007a03c  sub     rsp, 0C0h
0x14007a043  mov     rax, cs:__security_cookie
0x14007a04a  xor     rax, rsp
0x14007a04d  mov     [rbp+57h+var_30], rax
0x14007a051  mov     rsi, r8
0x14007a054  mov     rbx, rdx
0x14007a057  mov     rdi, rcx
0x14007a05a  mov     [rbp+57h+var_80], 0
0x14007a062  mov     [rbp+57h+var_A0], 0
0x14007a069  mov     [rbp+57h+var_98], 0
0x14007a071  mov     [rbp+57h+var_88], 0
0x14007a079  mov     [rbp+57h+var_78], 0
0x14007a081  mov     [rbp+57h+var_70], 0
0x14007a089  mov     [rbp+57h+var_68], 0
0x14007a091  mov     [rbp+57h+var_90], 0
0x14007a099  xorps   xmm0, xmm0
0x14007a09c  movdqa  xmmword ptr [rbp+57h+var_40.Data1], xmm0
0x14007a0a1  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x14007a0a5  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14007a0ad  movdqu  [rbp+57h+var_50], xmm1
0x14007a0b2  xor     eax, eax
0x14007a0b4  mov     [rbp+57h+var_60], ax
0x14007a0b8  mov     [rbp+57h+var_9C], eax
0x14007a0bb  mov     rax, [rdx]
0x14007a0be  lea     rdx, [rbp+57h+var_80]
0x14007a0c2  mov     rcx, rbx
0x14007a0c5  mov     rax, [rax+20h]
0x14007a0c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a0ce  mov     rcx, [rbp+5Fh]; this
0x14007a0d2  test    eax, eax
0x14007a0d4  jns     short loc_14007A0EB
0x14007a0d6  mov     r9d, eax; char *
0x14007a0d9  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a0e0  mov     edx, 1DEh; void *
0x14007a0e5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a0eb  mov     rax, [rbx]
0x14007a0ee  lea     rdx, [rbp+57h+var_A0]
0x14007a0f2  mov     rcx, rbx
0x14007a0f5  mov     rax, [rax+30h]
0x14007a0f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a0fe  mov     rcx, [rbp+5Fh]; this
0x14007a102  test    eax, eax
0x14007a104  jns     short loc_14007A11B
0x14007a106  mov     r9d, eax; char *
0x14007a109  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a110  mov     edx, 1DFh; void *
0x14007a115  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a11b  mov     rax, [rbx]
0x14007a11e  lea     rdx, [rbp+57h+var_98]
0x14007a122  mov     rcx, rbx
0x14007a125  mov     rax, [rax+38h]
0x14007a129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a12e  mov     rcx, [rbp+5Fh]; this
0x14007a132  test    eax, eax
0x14007a134  jns     short loc_14007A14B
0x14007a136  mov     r9d, eax; char *
0x14007a139  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a140  mov     edx, 1E0h; void *
0x14007a145  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a14b  mov     rax, [rbx]
0x14007a14e  lea     rdx, [rbp+57h+var_88]
0x14007a152  mov     rcx, rbx
0x14007a155  mov     rax, [rax+40h]
0x14007a159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a15e  mov     rcx, [rbp+5Fh]; this
0x14007a162  test    eax, eax
0x14007a164  jns     short loc_14007A17B
0x14007a166  mov     r9d, eax; char *
0x14007a169  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a170  mov     edx, 1E1h; void *
0x14007a175  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a17b  mov     rax, [rbx]
0x14007a17e  lea     rdx, [rbp+57h+var_78]
0x14007a182  mov     rcx, rbx
0x14007a185  mov     rax, [rax+48h]
0x14007a189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a18e  mov     rcx, [rbp+5Fh]; this
0x14007a192  test    eax, eax
0x14007a194  jns     short loc_14007A1AB
0x14007a196  mov     r9d, eax; char *
0x14007a199  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a1a0  mov     edx, 1E2h; void *
0x14007a1a5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a1ab  mov     rax, [rbx]
0x14007a1ae  lea     rdx, [rbp+57h+var_70]
0x14007a1b2  mov     rcx, rbx
0x14007a1b5  mov     rax, [rax+50h]
0x14007a1b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a1be  mov     rcx, [rbp+5Fh]; this
0x14007a1c2  test    eax, eax
0x14007a1c4  jns     short loc_14007A1DB
0x14007a1c6  mov     r9d, eax; char *
0x14007a1c9  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a1d0  mov     edx, 1E3h; void *
0x14007a1d5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a1db  mov     rax, [rbx]
0x14007a1de  lea     rdx, [rbp+57h+var_68]
0x14007a1e2  mov     rcx, rbx
0x14007a1e5  mov     rax, [rax+58h]
0x14007a1e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a1ee  mov     rcx, [rbp+5Fh]; this
0x14007a1f2  test    eax, eax
0x14007a1f4  jns     short loc_14007A20B
0x14007a1f6  mov     r9d, eax; char *
0x14007a1f9  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a200  mov     edx, 1E4h; void *
0x14007a205  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a20b  mov     rax, [rbx]
0x14007a20e  lea     rdx, [rbp+57h+var_90]
0x14007a212  mov     rcx, rbx
0x14007a215  mov     rax, [rax+68h]
0x14007a219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a21e  mov     rcx, [rbp+5Fh]; this
0x14007a222  test    eax, eax
0x14007a224  jns     short loc_14007A23B
0x14007a226  mov     r9d, eax; char *
0x14007a229  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a230  mov     edx, 1E5h; void *
0x14007a235  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a23b  mov     rax, [rbx]
0x14007a23e  lea     rdx, [rbp+57h+var_40]
0x14007a242  mov     rcx, rbx
0x14007a245  mov     rax, [rax+78h]
0x14007a249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a24e  mov     rcx, [rbp+5Fh]; this
0x14007a252  test    eax, eax
0x14007a254  jns     short loc_14007A26B
0x14007a256  mov     r9d, eax; char *
0x14007a259  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a260  mov     edx, 1E6h; void *
0x14007a265  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a26b  mov     rax, [rbx]
0x14007a26e  lea     rdx, [rbp+57h+var_9C]
0x14007a272  mov     rcx, rbx
0x14007a275  mov     rax, [rax+98h]
0x14007a27c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a281  mov     rcx, [rbp+5Fh]; this
0x14007a285  test    eax, eax
0x14007a287  jns     short loc_14007A29E
0x14007a289  mov     r9d, eax; char *
0x14007a28c  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a293  mov     edx, 1E7h; void *
0x14007a298  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a29e  mov     rax, [rdi]
0x14007a2a1  mov     r14, [rax+0A0h]
0x14007a2a8  mov     rbx, [rbp+57h+var_80]
0x14007a2ac  lea     r8, ?METRIC_VALUE_RELATIVE@@3QBGB; "/value"
0x14007a2b3  mov     rdx, rsi; Src
0x14007a2b6  lea     rcx, [rbp+57h+var_C0]; void *
0x14007a2ba  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x14007a2bf  nop
0x14007a2c0  cmp     qword ptr [rax+18h], 7
0x14007a2c5  jbe     short loc_14007A2CA
0x14007a2c7  mov     rax, [rax]
0x14007a2ca  mov     r8, rbx
0x14007a2cd  mov     rdx, rax
0x14007a2d0  mov     rcx, rdi
0x14007a2d3  mov     rax, r14
0x14007a2d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a2db  mov     rcx, [rbp+5Fh]; this
0x14007a2df  test    eax, eax
0x14007a2e1  jns     short loc_14007A2F8
0x14007a2e3  mov     r9d, eax; char *
0x14007a2e6  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a2ed  mov     edx, 1EBh; void *
0x14007a2f2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a2f8  lea     rcx, [rbp+57h+var_C0]
0x14007a2fc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14007a301  mov     rax, [rdi]
0x14007a304  mov     r14, [rax+0B0h]
0x14007a30b  xor     ebx, ebx
0x14007a30d  cmp     [rbp+57h+var_A0], 2
0x14007a311  setz    bl
0x14007a314  lea     r8, ?METRIC_ENABLED_RELATIVE@@3QBGB; "/enabled"
0x14007a31b  mov     rdx, rsi; Src
0x14007a31e  lea     rcx, [rbp+57h+var_C0]; void *
0x14007a322  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x14007a327  nop
0x14007a328  cmp     qword ptr [rax+18h], 7
0x14007a32d  jbe     short loc_14007A332
0x14007a32f  mov     rax, [rax]
0x14007a332  mov     r8d, ebx
0x14007a335  mov     rdx, rax
0x14007a338  mov     rcx, rdi
0x14007a33b  mov     rax, r14
0x14007a33e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a343  mov     rcx, [rbp+5Fh]; this
0x14007a347  test    eax, eax
0x14007a349  jns     short loc_14007A360
0x14007a34b  mov     r9d, eax; char *
0x14007a34e  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a355  mov     edx, 1EFh; void *
0x14007a35a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a360  lea     rcx, [rbp+57h+var_C0]
0x14007a364  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14007a369  lea     rdx, qword_1402E4D20
0x14007a370  mov     rcx, [rbp+57h+var_98]
0x14007a374  call    cs:__imp__o__wcsicmp
0x14007a37b  nop     dword ptr [rax+rax+00h]
0x14007a380  test    eax, eax
0x14007a382  jz      loc_14007A44E
0x14007a388  mov     rax, [rdi]
0x14007a38b  mov     r14, [rax+98h]
0x14007a392  mov     rbx, [rbp+57h+var_98]
0x14007a396  lea     r8, ?METRIC_BREAKDOWNDIMENSION_RELATIVE@@3QBGB; "/breakdowndimension"
0x14007a39d  mov     rdx, rsi; Src
0x14007a3a0  lea     rcx, [rbp+57h+var_C0]; void *
0x14007a3a4  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x14007a3a9  nop
0x14007a3aa  cmp     qword ptr [rax+18h], 7
0x14007a3af  jbe     short loc_14007A3B4
0x14007a3b1  mov     rax, [rax]
0x14007a3b4  mov     r8, rbx
0x14007a3b7  mov     rdx, rax
0x14007a3ba  mov     rcx, rdi
0x14007a3bd  mov     rax, r14
0x14007a3c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a3c5  mov     rcx, [rbp+5Fh]; this
0x14007a3c9  test    eax, eax
0x14007a3cb  jns     short loc_14007A3E2
0x14007a3cd  mov     r9d, eax; char *
0x14007a3d0  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a3d7  mov     edx, 1F9h; void *
0x14007a3dc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a3e2  lea     rcx, [rbp+57h+var_C0]
0x14007a3e6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14007a3eb  mov     rax, [rdi]
0x14007a3ee  mov     r14, [rax+98h]
0x14007a3f5  mov     rbx, [rbp+57h+var_88]
0x14007a3f9  lea     r8, ?METRIC_BREAKDOWNVALUE_RELATIVE@@3QBGB; "/breakdownvalue"
0x14007a400  mov     rdx, rsi; Src
0x14007a403  lea     rcx, [rbp+57h+var_C0]; void *
0x14007a407  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x14007a40c  nop
0x14007a40d  cmp     qword ptr [rax+18h], 7
0x14007a412  jbe     short loc_14007A417
0x14007a414  mov     rax, [rax]
0x14007a417  mov     r8, rbx
0x14007a41a  mov     rdx, rax
0x14007a41d  mov     rcx, rdi
0x14007a420  mov     rax, r14
0x14007a423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a428  mov     rcx, [rbp+5Fh]; this
0x14007a42c  test    eax, eax
0x14007a42e  jns     short loc_14007A445
0x14007a430  mov     r9d, eax; char *
0x14007a433  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a43a  mov     edx, 1FDh; void *
0x14007a43f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a445  lea     rcx, [rbp+57h+var_C0]
0x14007a449  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14007a44e  mov     rax, [rdi]
0x14007a451  mov     r14, [rax+0A0h]
0x14007a458  mov     rbx, [rbp+57h+var_78]
0x14007a45c  lea     r8, ?METRIC_STARTTIME_RELATIVE@@3QBGB; "/starttime"
0x14007a463  mov     rdx, rsi; Src
0x14007a466  lea     rcx, [rbp+57h+var_C0]; void *
0x14007a46a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x14007a46f  nop
0x14007a470  cmp     qword ptr [rax+18h], 7
0x14007a475  jbe     short loc_14007A47A
0x14007a477  mov     rax, [rax]
0x14007a47a  mov     r8, rbx
0x14007a47d  mov     rdx, rax
0x14007a480  mov     rcx, rdi
0x14007a483  mov     rax, r14
0x14007a486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a48b  mov     rcx, [rbp+5Fh]; this
0x14007a48f  test    eax, eax
0x14007a491  jns     short loc_14007A4A8
0x14007a493  mov     r9d, eax; char *
0x14007a496  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a49d  mov     edx, 202h; void *
0x14007a4a2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a4a8  lea     rcx, [rbp+57h+var_C0]
0x14007a4ac  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14007a4b1  mov     rax, [rdi]
0x14007a4b4  mov     r14, [rax+0A0h]
0x14007a4bb  mov     rbx, [rbp+57h+var_70]
0x14007a4bf  lea     r8, ?METRIC_LASTCOMPUTEDTIME_RELATIVE@@3QBGB; "/lastcomputedtime"
0x14007a4c6  mov     rdx, rsi; Src
0x14007a4c9  lea     rcx, [rbp+57h+var_C0]; void *
0x14007a4cd  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x14007a4d2  nop
0x14007a4d3  cmp     qword ptr [rax+18h], 7
0x14007a4d8  jbe     short loc_14007A4DD
0x14007a4da  mov     rax, [rax]
0x14007a4dd  mov     r8, rbx
0x14007a4e0  mov     rdx, rax
0x14007a4e3  mov     rcx, rdi
0x14007a4e6  mov     rax, r14
0x14007a4e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a4ee  mov     rcx, [rbp+5Fh]; this
0x14007a4f2  test    eax, eax
  ... truncated ...
```
