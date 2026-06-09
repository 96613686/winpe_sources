# CGatherer::GetTransferStatus(wchar_t const *,ulong *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,long *,tagPROPVARIANT *)

- ea: `0x180040320`
- end: `0x1800407f7`
- name: `?GetTransferStatus@CGatherer@@UEAAJPEB_WPEAKPEA_K22PEAJPEAUtagPROPVARIANT@@@Z`
- size: `1239`
- prototype: `int(CGatherer *__hidden this, const wchar_t *, unsigned int *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, int *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x18000bf8c`
- `0x180012120`
- `0x1800121a8`
- `0x18002dc6c`
- `0x1800320b4`
- `0x1800401c8`
- `0x180040320`
- `0x180040f48`
- `0x180048630`
- `0x1800e2374`
- `0x18010873c`
- `0x1801244c0`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040670`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040670`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800403f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800403f4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004057d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800406c3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180040755`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004057d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800406c3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180040755`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180040605`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180040605`

## string_xrefs

- `0x1800407c4`: `GetTransferStatus being called for path: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CGatherer::GetTransferStatus(
        CGatherer *this,
        const wchar_t *a2,
        unsigned int *a3,
        unsigned __int64 *a4,
        unsigned __int64 *a5,
        unsigned __int64 *a6,
        int *a7,
        struct tagPROPVARIANT *a8)
{
  int v12; // eax
  struct _RTL_CRITICAL_SECTION *v13; // rsi
  int ScopeManager; // eax
  int v15; // eax
  void *v16; // rcx
  __int64 v17; // r8
  __int64 v18; // rcx
  int *v19; // rdi
  __int64 *v20; // rbx
  const WCHAR *v21; // rcx
  const WCHAR *v22; // r8
  int *v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rbx
  __int64 v26; // rax
  __int64 *v27; // rdi
  const WCHAR *v28; // rcx
  const WCHAR *v29; // r8
  LPCWCH *v30; // rcx
  int *v31; // rdi
  __int64 *v32; // r14
  const WCHAR *v33; // rcx
  const WCHAR *v34; // r8
  __int64 v35; // rax
  __int64 v36; // rax
  int bIgnoreCase; // [rsp+20h] [rbp-E8h]
  int bIgnoreCasea; // [rsp+20h] [rbp-E8h]
  unsigned int v40; // [rsp+54h] [rbp-B4h] BYREF
  void *v41; // [rsp+58h] [rbp-B0h] BYREF
  int *v42; // [rsp+60h] [rbp-A8h] BYREF
  int v43[2]; // [rsp+68h] [rbp-A0h]
  unsigned __int64 *v44; // [rsp+70h] [rbp-98h]
  unsigned __int64 *v45; // [rsp+78h] [rbp-90h]
  const wchar_t *v46; // [rsp+80h] [rbp-88h]
  char *v47; // [rsp+88h] [rbp-80h]
  int v48; // [rsp+9Ch] [rbp-6Ch]
  LPCWCH lpString2[2]; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v50; // [rsp+B8h] [rbp-50h]
  unsigned __int64 v51; // [rsp+C0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v45 = a4;
  v46 = a2;
  *(_QWORD *)v43 = a5;
  v44 = a6;
  v42 = a7;
  *a3 = 0;
  *a4 = -1;
  *a5 = -1;
  *a6 = -1;
  *a7 = 0;
  if ( a8 )
  {
    *(_OWORD *)&a8->vt = 0;
    a8->bstrblobVal.pData = 0;
  }
  v12 = CGatherer::WaitForRecoveryEvent((CGatherer *)((char *)this - 120));
  try
  {
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x39E2,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\server\\gatherobj.cxx",
        (const char *)(unsigned int)v12,
        bIgnoreCase);
    v13 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1232);
    v47 = (char *)this + 1232;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1232));
    v40 = 0;
    if ( (int)CGatherer::_URLToWID((CGatherer *)((char *)this - 120), a2, &v40) < 0 )
    {
      *a3 |= 0x200u;
    }
    else
    {
      v41 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
      ScopeManager = CGatherer::_GetScopeManager(
                       (CGatherer *)((char *)this - 120),
                       &GUID_4b42e340_cba6_40eb_b2b4_bb1c0553eae1,
                       &v41);
      if ( ScopeManager < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x39EA,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\server\\gatherobj.cxx",
          (const char *)(unsigned int)ScopeManager,
          bIgnoreCase);
      bIgnoreCasea = v43[0];
      v15 = (*(__int64 (__fastcall **)(void *, _QWORD, unsigned int *, unsigned __int64 *))(*(_QWORD *)v41 + 120LL))(
              v41,
              v40,
              a3,
              a4);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x39F2,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\server\\gatherobj.cxx",
          (const char *)(unsigned int)v15,
          bIgnoreCasea);
      v16 = v41;
      if ( v41 )
      {
        v41 = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 16LL))(v16);
      }
    }
    *(_OWORD *)lpString2 = 0;
    v50 = 0;
    v51 = 0;
    v17 = -1;
    do
      ++v17;
    while ( a2[v17] );
    std::wstring::_Construct<1,wchar_t *>(lpString2);
    if ( !v50 )
      goto LABEL_41;
    v19 = (int *)*((_QWORD *)this + 13);
    v20 = (__int64 *)*((_QWORD *)v19 + 1);
    v48 = 0;
    while ( !*((_BYTE *)v20 + 25) )
    {
      v21 = (const WCHAR *)(v20 + 4);
      v22 = (const WCHAR *)lpString2;
      if ( v51 > 7 )
        v22 = lpString2[0];
      if ( (unsigned __int64)v20[7] > 7 )
        v21 = *(const WCHAR **)v21;
      if ( CompareStringOrdinal(v21, -1, v22, -1, 1) == 1 )
        v20 += 2;
      else
        v19 = (int *)v20;
      v20 = (__int64 *)*v20;
    }
    if ( *((_BYTE *)v19 + 25) || (unsigned __int8)wstring_filename_compare::operator()(v18, lpString2, v19 + 8) )
    {
      v23 = (int *)*((_QWORD *)this + 13);
    }
    else
    {
      v23 = (int *)*((_QWORD *)this + 13);
      if ( v19 != v23 )
      {
        v24 = *((_QWORD *)v19 + 8);
        if ( (*(_BYTE *)v24 & 1) != 0 )
        {
          *a3 |= *(_DWORD *)(v24 + 40);
          *v45 = *(_QWORD *)(*((_QWORD *)v19 + 8) + 48LL);
        }
        v25 = *((_QWORD *)v19 + 8);
        if ( (*(_BYTE *)v25 & 2) != 0
          && *(_QWORD *)(v25 + 56) != -1
          && (unsigned __int64)(*(_QWORD *)(v25 + 64) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL
          && *(_DWORD *)(v25 + 80) > GetTickCount() - 30000 )
        {
          *a3 |= 4u;
          **(_QWORD **)v43 = *(_QWORD *)(*((_QWORD *)v19 + 8) + 56LL);
          *v44 = *(_QWORD *)(*((_QWORD *)v19 + 8) + 64LL);
        }
        v26 = *((_QWORD *)v19 + 8);
        if ( (*(_BYTE *)v26 & 4) != 0 && *(int *)(v26 + 72) < 0 )
        {
          *a3 |= 0x10u;
          *v42 = *(_DWORD *)(*((_QWORD *)v19 + 8) + 72LL);
        }
LABEL_41:
        ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)lpString2);
        if ( v13 )
          LeaveCriticalSection(v13);
        goto LABEL_78;
      }
    }
    v27 = (__int64 *)*((_QWORD *)v23 + 1);
    v48 = 0;
    while ( !*((_BYTE *)v27 + 25) )
    {
      v28 = (const WCHAR *)(v27 + 4);
      v29 = (const WCHAR *)lpString2;
      if ( v51 > 7 )
        v29 = lpString2[0];
      if ( (unsigned __int64)v27[7] > 7 )
        v28 = *(const WCHAR **)v28;
      if ( CompareStringOrdinal(v28, -1, v29, -1, 1) == 1 )
        v27 += 2;
      else
        v23 = (int *)v27;
      v27 = (__int64 *)*v27;
    }
    v42 = v23;
    v30 = lpString2;
    if ( v51 > 7 )
      v30 = (LPCWCH *)lpString2[0];
    ++*((_WORD *)v30 + v50 - 1);
    v31 = (int *)*((_QWORD *)this + 13);
    v32 = (__int64 *)*((_QWORD *)v31 + 1);
    v48 = 0;
    while ( !*((_BYTE *)v32 + 25) )
    {
      v33 = (const WCHAR *)(v32 + 4);
      v34 = (const WCHAR *)lpString2;
      if ( v51 > 7 )
        v34 = lpString2[0];
      if ( (unsigned __int64)v32[7] > 7 )
        v33 = *(const WCHAR **)v33;
      if ( CompareStringOrdinal(v33, -1, v34, -1, 1) == 1 )
        v32 += 2;
      else
        v31 = (int *)v32;
      v32 = (__int64 *)*v32;
    }
    while ( v23 != v31 )
    {
      v35 = *((_QWORD *)v23 + 8);
      if ( (*(_BYTE *)v35 & 1) != 0 )
        *a3 |= *(_DWORD *)(v35 + 40);
      v36 = *((_QWORD *)v23 + 8);
      if ( (*(_BYTE *)v36 & 4) != 0 && *(int *)(v36 + 72) < 0 )
        *a3 |= 0x10u;
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<FATNotificationSource::SNotification>>,std::_Iterator_base0>::operator++(
        &v42,
        0);
      v23 = v42;
    }
    goto LABEL_41;
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      14886,
      "onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\server\\gatherobj.cxx");
  }
LABEL_78:
  ETWLog::Log(L"GetTransferStatus being called for path: %s", a2);
  return 0;
}

```

## disassembly

```asm
0x180040320  push    rbx
0x180040322  push    rsi
0x180040323  push    rdi
0x180040324  push    r12
0x180040326  push    r13
0x180040328  push    r14
0x18004032a  push    r15
0x18004032c  sub     rsp, 0D0h
0x180040333  mov     rax, cs:__security_cookie
0x18004033a  xor     rax, rsp
0x18004033d  mov     [rsp+108h+var_40], rax
0x180040345  mov     r12, r9
0x180040348  mov     [rsp+108h+var_90], r9
0x18004034d  mov     r15, r8
0x180040350  mov     r13, rdx
0x180040353  mov     r14, rcx
0x180040356  mov     [rsp+108h+var_88], rdx
0x18004035e  mov     rax, [rsp+108h+arg_20]
0x180040366  mov     qword ptr [rsp+108h+var_A0], rax
0x18004036b  mov     rcx, [rsp+108h+arg_28]
0x180040373  mov     [rsp+108h+var_98], rcx
0x180040378  mov     rdx, [rsp+108h+arg_30]
0x180040380  mov     [rsp+108h+var_A8], rdx
0x180040385  mov     rbx, [rsp+108h+arg_38]
0x18004038d  xor     esi, esi
0x18004038f  mov     [r8], esi
0x180040392  or      r8, 0FFFFFFFFFFFFFFFFh
0x180040396  mov     [r9], r8
0x180040399  mov     [rax], r8
0x18004039c  mov     [rcx], r8
0x18004039f  mov     [rdx], esi
0x1800403a1  test    rbx, rbx
0x1800403a4  jz      short loc_1800403B2
0x1800403a6  xorps   xmm0, xmm0
0x1800403a9  xor     eax, eax
0x1800403ab  movups  xmmword ptr [rbx], xmm0
0x1800403ae  mov     [rbx+10h], rax
0x1800403b2  mov     [rsp+108h+var_B8], esi
0x1800403b6  lea     rdi, [r14-78h]
0x1800403ba  mov     rcx, rdi; this
0x1800403bd  call    ?WaitForRecoveryEvent@CGatherer@@QEAAJXZ; CGatherer::WaitForRecoveryEvent(void)
0x1800403c2  mov     rcx, [rsp+108h]; this
0x1800403ca  test    eax, eax
0x1800403cc  jns     short loc_1800403E2
0x1800403ce  mov     r9d, eax; char *
0x1800403d1  lea     r8, aOnecoreuapBase_105; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800403d8  mov     edx, 39E2h; void *
0x1800403dd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800403e2  lea     rsi, [r14+4D0h]
0x1800403e9  mov     [rsp+108h+var_80], rsi
0x1800403f1  mov     rcx, rsi; lpCriticalSection
0x1800403f4  call    cs:__imp_EnterCriticalSection
0x1800403fa  nop
0x1800403fb  mov     [rsp+108h+var_B4], 0
0x180040403  lea     r8, [rsp+108h+var_B4]; unsigned int *
0x180040408  mov     rdx, r13; wchar_t *
0x18004040b  mov     rcx, rdi; this
0x18004040e  call    ?_URLToWID@CGatherer@@AEAAJPEB_WPEAK@Z; CGatherer::_URLToWID(wchar_t const *,ulong *)
0x180040413  xor     edx, edx
0x180040415  test    eax, eax
0x180040417  js      loc_1800404E0
0x18004041d  mov     [rsp+108h+var_B0], rdx
0x180040422  lea     rcx, [rsp+108h+var_B0]
0x180040427  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004042c  lea     r8, [rsp+108h+var_B0]; void **
0x180040431  lea     rdx, _GUID_4b42e340_cba6_40eb_b2b4_bb1c0553eae1; struct _GUID *
0x180040438  mov     rcx, rdi; this
0x18004043b  call    ?_GetScopeManager@CGatherer@@AEAAJAEBU_GUID@@PEAPEAX@Z; CGatherer::_GetScopeManager(_GUID const &,void * *)
0x180040440  mov     rcx, [rsp+108h]; this
0x180040448  test    eax, eax
0x18004044a  jns     short loc_180040460
0x18004044c  mov     r9d, eax; char *
0x18004044f  lea     r8, aOnecoreuapBase_105; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180040456  mov     edx, 39EAh; void *
0x18004045b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180040460  mov     rcx, [rsp+108h+var_B0]
0x180040465  mov     rax, [rcx]
0x180040468  mov     [rsp+108h+var_D0], rbx
0x18004046d  mov     rdx, [rsp+108h+var_A8]
0x180040472  mov     [rsp+108h+var_D8], rdx
0x180040477  mov     rdx, [rsp+108h+var_98]
0x18004047c  mov     [rsp+108h+var_E0], rdx
0x180040481  mov     rdx, qword ptr [rsp+108h+var_A0]
0x180040486  mov     qword ptr [rsp+108h+bIgnoreCase], rdx; int
0x18004048b  mov     r9, r12
0x18004048e  mov     r8, r15
0x180040491  mov     edx, [rsp+108h+var_B4]
0x180040495  mov     rax, [rax+78h]
0x180040499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004049e  mov     rcx, [rsp+108h]; this
0x1800404a6  xor     edx, edx
0x1800404a8  test    eax, eax
0x1800404aa  jns     short loc_1800404C1
0x1800404ac  mov     r9d, eax; char *
0x1800404af  lea     r8, aOnecoreuapBase_105; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800404b6  mov     edx, 39F2h; void *
0x1800404bb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800404c1  mov     rcx, [rsp+108h+var_B0]
0x1800404c6  test    rcx, rcx
0x1800404c9  jz      short loc_1800404DE
0x1800404cb  mov     [rsp+108h+var_B0], rdx
0x1800404d0  mov     rax, [rcx]
0x1800404d3  mov     rax, [rax+10h]
0x1800404d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800404dc  xor     edx, edx
0x1800404de  jmp     short loc_1800404E5
0x1800404e0  bts     dword ptr [r15], 9
0x1800404e5  xorps   xmm0, xmm0
0x1800404e8  movups  xmmword ptr [rsp+108h+lpString2], xmm0
0x1800404f0  mov     [rsp+108h+var_50], rdx
0x1800404f8  mov     [rsp+108h+var_48], rdx
0x180040500  or      r8, 0FFFFFFFFFFFFFFFFh
0x180040504  inc     r8
0x180040507  cmp     [r13+r8*2+0], dx
0x18004050d  jnz     short loc_180040504
0x18004050f  mov     rdx, r13
0x180040512  lea     rcx, [rsp+108h+lpString2]
0x18004051a  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x18004051f  xor     edx, edx
0x180040521  cmp     [rsp+108h+var_50], rdx
0x180040529  jz      loc_18004065A
0x18004052f  mov     rdi, [r14+68h]
0x180040533  mov     rbx, [rdi+8]
0x180040537  xor     eax, eax
0x180040539  mov     [rsp+108h+var_6C], eax
0x180040540  lea     r12d, [rdx+1]
0x180040544  cmp     [rbx+19h], dl
0x180040547  jnz     short loc_180040598
0x180040549  lea     rcx, [rbx+20h]
0x18004054d  lea     r8, [rsp+108h+lpString2]
0x180040555  cmp     [rsp+108h+var_48], 7
0x18004055e  cmova   r8, [rsp+108h+lpString2]; lpString2
0x180040567  cmp     qword ptr [rcx+18h], 7
0x18004056c  jbe     short loc_180040571
0x18004056e  mov     rcx, [rcx]; lpString1
0x180040571  mov     [rsp+108h+bIgnoreCase], r12d; bIgnoreCase
0x180040576  or      r9d, 0FFFFFFFFh; cchCount2
0x18004057a  or      edx, r9d; cchCount1
0x18004057d  call    cs:__imp_CompareStringOrdinal
0x180040583  cmp     eax, r12d
0x180040586  jnz     short loc_18004058E
0x180040588  add     rbx, 10h
0x18004058c  jmp     short loc_180040591
0x18004058e  mov     rdi, rbx
0x180040591  mov     rbx, [rbx]
0x180040594  xor     edx, edx
0x180040596  jmp     short loc_180040544
0x180040598  cmp     [rdi+19h], dl
0x18004059b  jnz     loc_18004067C
0x1800405a1  lea     r8, [rdi+20h]
0x1800405a5  lea     rdx, [rsp+108h+lpString2]
0x1800405ad  call    ??Rwstring_filename_compare@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z; wstring_filename_compare::operator()(std::wstring const &,std::wstring const &)
0x1800405b2  xor     edx, edx
0x1800405b4  test    al, al
0x1800405b6  jnz     loc_18004067C
0x1800405bc  mov     rbx, [r14+68h]
0x1800405c0  cmp     rdi, rbx
0x1800405c3  jz      loc_180040680
0x1800405c9  mov     rax, [rdi+40h]
0x1800405cd  test    [rax], r12b
0x1800405d0  jz      short loc_1800405E8
0x1800405d2  mov     eax, [rax+28h]
0x1800405d5  or      [r15], eax
0x1800405d8  mov     rax, [rdi+40h]
0x1800405dc  mov     rcx, [rax+30h]
0x1800405e0  mov     rax, [rsp+108h+var_90]
0x1800405e5  mov     [rax], rcx
0x1800405e8  mov     rbx, [rdi+40h]
0x1800405ec  test    byte ptr [rbx], 2
0x1800405ef  jz      short loc_180040639
0x1800405f1  cmp     qword ptr [rbx+38h], 0FFFFFFFFFFFFFFFFh
0x1800405f6  jz      short loc_180040639
0x1800405f8  mov     rax, [rbx+40h]
0x1800405fc  sub     rax, r12
0x1800405ff  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180040603  ja      short loc_180040639
0x180040605  call    cs:__imp_GetTickCount
0x18004060b  add     eax, 0FFFF8AD0h
0x180040610  cmp     [rbx+50h], eax
0x180040613  jbe     short loc_180040639
0x180040615  or      dword ptr [r15], 4
0x180040619  mov     rax, [rdi+40h]
0x18004061d  mov     rcx, [rax+38h]
0x180040621  mov     rax, qword ptr [rsp+108h+var_A0]
0x180040626  mov     [rax], rcx
0x180040629  mov     rax, [rdi+40h]
0x18004062d  mov     rcx, [rax+40h]
0x180040631  mov     rax, [rsp+108h+var_98]
0x180040636  mov     [rax], rcx
0x180040639  mov     rax, [rdi+40h]
0x18004063d  test    byte ptr [rax], 4
0x180040640  jz      short loc_18004065A
0x180040642  cmp     dword ptr [rax+48h], 0
0x180040646  jge     short loc_18004065A
0x180040648  or      dword ptr [r15], 10h
0x18004064c  mov     rax, [rdi+40h]
0x180040650  mov     ecx, [rax+48h]
0x180040653  mov     rax, [rsp+108h+var_A8]
0x180040658  mov     [rax], ecx
0x18004065a  lea     rcx, [rsp+108h+lpString2]; this
0x180040662  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x180040667  nop
0x180040668  test    rsi, rsi
0x18004066b  jz      short loc_180040677
0x18004066d  mov     rcx, rsi; lpCriticalSection
0x180040670  call    cs:__imp_LeaveCriticalSection
0x180040676  nop
0x180040677  jmp     loc_1800407C1
0x18004067c  mov     rbx, [r14+68h]
0x180040680  mov     rdi, [rbx+8]
0x180040684  xor     eax, eax
0x180040686  mov     [rsp+108h+var_6C], eax
0x18004068d  jmp     short loc_1800406DC
0x18004068f  lea     rcx, [rdi+20h]
0x180040693  lea     r8, [rsp+108h+lpString2]
0x18004069b  cmp     [rsp+108h+var_48], 7
0x1800406a4  cmova   r8, [rsp+108h+lpString2]; lpString2
0x1800406ad  cmp     qword ptr [rcx+18h], 7
0x1800406b2  jbe     short loc_1800406B7
0x1800406b4  mov     rcx, [rcx]; lpString1
0x1800406b7  mov     [rsp+108h+bIgnoreCase], r12d; bIgnoreCase
0x1800406bc  or      r9d, 0FFFFFFFFh; cchCount2
0x1800406c0  or      edx, r9d; cchCount1
0x1800406c3  call    cs:__imp_CompareStringOrdinal
0x1800406c9  cmp     eax, r12d
0x1800406cc  jnz     short loc_1800406D4
0x1800406ce  add     rdi, 10h
0x1800406d2  jmp     short loc_1800406D7
0x1800406d4  mov     rbx, rdi
0x1800406d7  mov     rdi, [rdi]
0x1800406da  xor     edx, edx
0x1800406dc  cmp     [rdi+19h], dl
0x1800406df  jz      short loc_18004068F
0x1800406e1  mov     [rsp+108h+var_A8], rbx
0x1800406e6  lea     rcx, [rsp+108h+lpString2]
0x1800406ee  cmp     [rsp+108h+var_48], 7
0x1800406f7  cmova   rcx, [rsp+108h+lpString2]
0x180040700  mov     rax, [rsp+108h+var_50]
0x180040708  add     [rcx+rax*2-2], r12w
0x18004070e  mov     rdi, [r14+68h]
0x180040712  mov     r14, [rdi+8]
0x180040716  xor     eax, eax
0x180040718  mov     [rsp+108h+var_6C], eax
0x18004071f  jmp     short loc_18004076E
0x180040721  lea     rcx, [r14+20h]
0x180040725  lea     r8, [rsp+108h+lpString2]
0x18004072d  cmp     [rsp+108h+var_48], 7
0x180040736  cmova   r8, [rsp+108h+lpString2]; lpString2
0x18004073f  cmp     qword ptr [rcx+18h], 7
0x180040744  jbe     short loc_180040749
0x180040746  mov     rcx, [rcx]; lpString1
0x180040749  mov     [rsp+108h+bIgnoreCase], r12d; bIgnoreCase
0x18004074e  or      r9d, 0FFFFFFFFh; cchCount2
0x180040752  or      edx, r9d; cchCount1
0x180040755  call    cs:__imp_CompareStringOrdinal
0x18004075b  cmp     eax, r12d
0x18004075e  jnz     short loc_180040766
0x180040760  add     r14, 10h
0x180040764  jmp     short loc_180040769
0x180040766  mov     rdi, r14
0x180040769  mov     r14, [r14]
0x18004076c  xor     edx, edx
0x18004076e  cmp     [r14+19h], dl
0x180040772  jz      short loc_180040721
0x180040774  cmp     rbx, rdi
0x180040777  jz      loc_18004065A
0x18004077d  mov     rax, [rbx+40h]
0x180040781  test    [rax], r12b
0x180040784  jz      short loc_18004078C
0x180040786  mov     eax, [rax+28h]
0x180040789  or      [r15], eax
0x18004078c  mov     rax, [rbx+40h]
0x180040790  test    byte ptr [rax], 4
0x180040793  jz      short loc_18004079E
0x180040795  cmp     [rax+48h], edx
0x180040798  jge     short loc_18004079E
0x18004079a  or      dword ptr [r15], 10h
0x18004079e  lea     rcx, [rsp+108h+var_A8]
0x1800407a3  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@USNotification@FATNotificationSource@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<FATNotificationSource::SNotification>>,std::_Iterator_base0>::operator++(void)
0x1800407a8  mov     rbx, [rsp+108h+var_A8]
0x1800407ad  xor     edx, edx
0x1800407af  jmp     short loc_180040774
0x1800407b1  mov     eax, [rsp+108h+var_B8]
0x1800407b5  mov     [rsp+108h+var_B8], eax
0x1800407b9  mov     r13, [rsp+108h+var_88]
0x1800407c1  mov     rdx, r13
0x1800407c4  lea     rcx, aGettransfersta; "GetTransferStatus being called for path"...
0x1800407cb  call    ?Log@ETWLog@@SAXPEB_WZZ; ETWLog::Log(wchar_t const *,...)
0x1800407d0  mov     eax, [rsp+108h+var_B8]
0x1800407d4  mov     rcx, [rsp+108h+var_40]
0x1800407dc  xor     rcx, rsp; StackCookie
0x1800407df  call    __security_check_cookie
0x1800407e4  add     rsp, 0D0h
0x1800407eb  pop     r15
0x1800407ed  pop     r14
0x1800407ef  pop     r13
0x1800407f1  pop     r12
0x1800407f3  pop     rdi
0x1800407f4  pop     rsi
0x1800407f5  pop     rbx
  ... truncated ...
```
