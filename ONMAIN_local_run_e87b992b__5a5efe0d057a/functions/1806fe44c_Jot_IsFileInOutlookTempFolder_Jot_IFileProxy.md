# Jot::IsFileInOutlookTempFolder(Jot::IFileProxy *)

- ea: `0x1806fe44c`
- end: `0x1806fea8f`
- name: `?IsFileInOutlookTempFolder@Jot@@YA_NPEAUIFileProxy@1@@Z`
- size: `1603`
- prototype: `bool __fastcall(Jot *__hidden this, struct Jot::IFileProxy *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1806fe1b0`

## callees

- `0x18005b344`
- `0x18005b408`
- `0x180067080`
- `0x18009424c`
- `0x1802919f0`
- `0x18029ced0`
- `0x1802e2190`
- `0x1802e50d0`
- `0x1802e5170`
- `0x1802e5190`
- `0x180655754`
- `0x1806fe44c`
- `0x1806fea90`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x1806fe592`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1806fe968`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1806fe9d4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1806fea38`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1806fe592`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1806fe968`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1806fe9d4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1806fea38`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1806fe988`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1806fe9cd`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1806fea31`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1806fe988`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1806fe9cd`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1806fea31`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1806fe839`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1806fe839`
- `Mso20Win32Client!__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z` at `0x1806fe6f3`
- `Mso20Win32Client!__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z` at `0x1806fe718`
- `Mso20Win32Client!__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z` at `0x1806fe6f3`
- `Mso20Win32Client!__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z` at `0x1806fe718`
- `Mso20Win32Client!__imp_?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z` at `0x1806fe514`
- `Mso20Win32Client!__imp_?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z` at `0x1806fe78b`
- `Mso20Win32Client!__imp_?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z` at `0x1806fe514`
- `Mso20Win32Client!__imp_?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z` at `0x1806fe78b`
- `Mso20Win32Client!__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z` at `0x1806fe746`
- `Mso20Win32Client!__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z` at `0x1806fe746`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1806fe84c`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1806fe889`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1806fe8c1`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1806fe904`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1806fe84c`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1806fe889`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1806fe8c1`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1806fe904`

## string_xrefs

- `0x1806fe709`: `Security`
- `0x1806fe736`: `OutlookSecureTempFolder`

## pseudocode

```c
char __fastcall Jot::IsFileInOutlookTempFolder(Jot *this, struct Jot::IFileProxy *a2)
{
  __int64 v2; // rax
  wchar_t *v3; // rax
  int Wz; // ebx
  const wchar_t *v5; // r8
  void **v6; // rdx
  Jot::Url *v7; // rcx
  void *v8; // rcx
  __m128i v9; // xmm0
  void (*v10)(void); // rax
  int i; // eax
  const wchar_t *v12; // r8
  wchar_t *v13; // rax
  int v14; // ebx
  const wchar_t *v15; // r8
  void **v16; // rdx
  Jot::Url *v17; // rcx
  __int64 v19; // rcx
  wchar_t *v20; // rcx
  void *v21; // rcx
  __m128i v22; // xmm0
  Jot::Url *v23; // rcx
  void **v24; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v26; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+50h] [rbp-B0h]
  _OWORD v28[2]; // [rsp+58h] [rbp-A8h] BYREF
  char v29; // [rsp+78h] [rbp-88h]
  __int128 v30; // [rsp+80h] [rbp-80h] BYREF
  __int64 v31; // [rsp+90h] [rbp-70h]
  _OWORD v32[2]; // [rsp+98h] [rbp-68h] BYREF
  char v33; // [rsp+B8h] [rbp-48h]
  __int128 v34; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v35; // [rsp+D0h] [rbp-30h]
  _OWORD v36[2]; // [rsp+D8h] [rbp-28h] BYREF
  char v37; // [rsp+F8h] [rbp-8h]
  __int128 v38; // [rsp+100h] [rbp+0h] BYREF
  __int64 v39; // [rsp+110h] [rbp+10h]
  _OWORD v40[2]; // [rsp+118h] [rbp+18h] BYREF
  char v41; // [rsp+138h] [rbp+38h]
  void **v42; // [rsp+140h] [rbp+40h] BYREF
  void *Block[2]; // [rsp+148h] [rbp+48h] BYREF
  __m128i si128; // [rsp+158h] [rbp+58h]
  Jot::Url *v45[2]; // [rsp+168h] [rbp+68h] BYREF
  __m128i v46; // [rsp+178h] [rbp+78h]
  wchar_t *Src[3]; // [rsp+188h] [rbp+88h] BYREF
  unsigned __int64 v48; // [rsp+1A0h] [rbp+A0h]

  (*(void (__fastcall **)(Jot *, __int64 *))(*(_QWORD *)this + 232LL))(this, &v25);
  if ( !v25 )
    return 0;
  v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 24LL))(v25);
  (*(void (__fastcall **)(__int64, Jot::Url **))(*(_QWORD *)v2 + 128LL))(v2, v45);
  *(_OWORD *)Block = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Block[0]) = 0;
  v24 = Block;
  std::wstring::resize(Block, 261);
  v3 = (wchar_t *)std::wstring::operator[](Block, 0);
  Wz = MsoFRegReadWz((const struct _msoreg *)&vmsoridOutlookSecureTempFolder, v3, 0x104u);
  Jot::basic_strbuffer<std::wstring>::~basic_strbuffer<std::wstring>(&v24);
  if ( Wz )
  {
    v6 = Block;
    if ( si128.m128i_i64[1] > 7uLL )
      v6 = (void **)Block[0];
    v7 = (Jot::Url *)v45;
    if ( v46.m128i_i64[1] > 7uLL )
      v7 = v45[0];
    if ( Jot::Url::AreEqualPathnames(v7, (const wchar_t *)v6, v5) )
    {
      if ( si128.m128i_i64[1] <= 7uLL )
        goto LABEL_12;
      v8 = Block[0];
      if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) < 0x1000
        || (v8 = (void *)*((_QWORD *)Block[0] - 1), (unsigned __int64)((char *)Block[0] - (char *)v8 - 8) <= 0x1F) )
      {
        free(v8);
LABEL_12:
        Block[0] = (void *)19937;
        v9 = _mm_load_si128((const __m128i *)&_xmm);
        si128 = v9;
        if ( v46.m128i_i64[1] > 7uLL )
        {
          std::_Deallocate<16>(v45[0], 2 * v46.m128i_i64[1] + 2);
          v9 = _mm_load_si128((const __m128i *)&_xmm);
        }
        v45[0] = (Jot::Url *)19937;
        v46 = v9;
        if ( v25 )
        {
          v10 = *(void (**)(void))(*(_QWORD *)v25 + 16LL);
          goto LABEL_34;
        }
        return 1;
      }
LABEL_56:
      _invoke_watson(0, 0, 0, 0, 0);
    }
  }
  for ( i = 15; ; i = (_DWORD)v24 - 1 )
  {
    LODWORD(v24) = i;
    if ( i < 9 )
    {
      if ( si128.m128i_i64[1] > 7uLL )
      {
        v21 = Block[0];
        if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
        {
          v21 = (void *)*((_QWORD *)Block[0] - 1);
          if ( (unsigned __int64)((char *)Block[0] - (char *)v21 - 8) > 0x1F )
            goto LABEL_56;
        }
        free(v21);
      }
      Block[0] = (void *)19937;
      v22 = _mm_load_si128((const __m128i *)&_xmm);
      si128 = v22;
      if ( v46.m128i_i64[1] > 7uLL )
      {
        v23 = v45[0];
        if ( (unsigned __int64)(2 * v46.m128i_i64[1] + 2) >= 0x1000 )
        {
          v23 = (Jot::Url *)*((_QWORD *)v45[0] - 1);
          if ( (unsigned __int64)(v45[0] - v23 - 8) > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
        }
        free(v23);
        v22 = _mm_load_si128((const __m128i *)&_xmm);
      }
      v45[0] = (Jot::Url *)19937;
      v46 = v22;
      if ( v25 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      return 0;
    }
    MsoCF::StringFromPatternWithConverter<wchar_t [5],int>(Src);
    v38 = 0;
    v39 = 0;
    v40[0] = 0;
    v41 = 0;
    v40[1] = (unsigned __int64)&v38;
    v34 = 0;
    v35 = 0;
    v36[0] = 0;
    v37 = 0;
    v36[1] = (unsigned __int64)&v34;
    v30 = 0;
    v31 = 0;
    v32[0] = 0;
    v33 = 0;
    v32[1] = (unsigned __int64)&v30;
    v26 = 0;
    v27 = 0;
    v28[0] = 0;
    v29 = 0;
    v28[1] = (unsigned __int64)&v26;
    v12 = (const wchar_t *)Src;
    if ( v48 > 7 )
      v12 = Src[0];
    if ( DynamicMsorid::FInitForKey((DynamicMsorid *)&v38, (const struct _msoreg *)&vmsoridCUOffice, v12) )
      break;
LABEL_39:
    if ( v29 )
    {
      MsoOrapiDeleteFromCache((const struct _msoreg *)v28);
      DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v26);
      DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v28);
      v29 = 0;
    }
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v28);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v26);
    if ( v33 )
    {
      MsoOrapiDeleteFromCache((const struct _msoreg *)v32);
      DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v30);
      DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v32);
      v33 = 0;
    }
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v32);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v30);
    if ( v37 )
    {
      MsoOrapiDeleteFromCache((const struct _msoreg *)v36);
      DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v34);
      DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v36);
      v37 = 0;
    }
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v36);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v34);
    if ( v41 )
    {
      MsoOrapiDeleteFromCache((const struct _msoreg *)v40);
      DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v38);
      DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v40);
      v41 = 0;
    }
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v40);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v38);
    if ( v48 > 7 )
    {
      v20 = Src[0];
      if ( 2 * v48 + 2 >= 0x1000 )
      {
        v20 = (wchar_t *)*((_QWORD *)Src[0] - 1);
        if ( (unsigned __int64)((char *)Src[0] - (char *)v20 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v20);
    }
  }
  if ( !v41 || (DynamicMsorid::InitForKey((DynamicMsorid *)&v34, (const struct _msoreg *)v40, L"Outlook", 7u), !v37) )
  {
    v19 = 508048475;
    goto LABEL_38;
  }
  DynamicMsorid::InitForKey((DynamicMsorid *)&v30, (const struct _msoreg *)v36, L"Security", 8u);
  if ( !v33 )
  {
    v19 = 508048472;
LABEL_38:
    MsoShipAssertTagProc(v19);
    goto LABEL_39;
  }
  DynamicMsorid::InitForValue(&v26, v32, L"OutlookSecureTempFolder", 23, 1);
  v42 = Block;
  if ( si128.m128i_i64[0] < 0x105uLL )
    std::wstring::resize(Block, 261);
  v13 = (wchar_t *)std::wstring::operator[](Block, 0);
  v14 = MsoFRegReadWz((const struct _msoreg *)((unsigned __int64)v28 & -(__int64)(v29 != 0)), v13, 0x104u);
  Jot::basic_strbuffer<std::wstring>::~basic_strbuffer<std::wstring>(&v42);
  if ( !v14 )
    goto LABEL_39;
  v16 = Block;
  if ( si128.m128i_i64[1] > 7uLL )
    v16 = (void **)Block[0];
  v17 = (Jot::Url *)v45;
  if ( v46.m128i_i64[1] > 7uLL )
    v17 = v45[0];
  if ( !Jot::Url::AreEqualPathnames(v17, (const wchar_t *)v16, v15) )
    goto LABEL_39;
  DynamicMsorid::~DynamicMsorid((DynamicMsorid *)&v26);
  DynamicMsorid::~DynamicMsorid((DynamicMsorid *)&v30);
  DynamicMsorid::~DynamicMsorid((DynamicMsorid *)&v34);
  DynamicMsorid::~DynamicMsorid((DynamicMsorid *)&v38);
  std::wstring::~wstring(Src);
  std::wstring::~wstring(Block);
  std::wstring::~wstring(v45);
  if ( v25 )
  {
    v10 = *(void (**)(void))(*(_QWORD *)v25 + 16LL);
LABEL_34:
    v10();
  }
  return 1;
}

```

## disassembly

```asm
0x1806fe44c  mov     [rsp-8+arg_8], rbx
0x1806fe451  mov     [rsp-8+arg_10], rsi
0x1806fe456  push    rbp
0x1806fe457  push    rdi
0x1806fe458  push    r15
0x1806fe45a  lea     rbp, [rsp-0B0h]
0x1806fe462  sub     rsp, 1B0h
0x1806fe469  mov     rax, cs:__security_cookie
0x1806fe470  xor     rax, rsp
0x1806fe473  mov     [rbp+0C0h+var_18], rax
0x1806fe47a  xor     esi, esi
0x1806fe47c  mov     rax, [rcx]
0x1806fe47f  lea     rdx, [rsp+1C0h+var_188]
0x1806fe484  mov     rax, [rax+0E8h]
0x1806fe48b  call    cs:__guard_dispatch_icall_fptr
0x1806fe491  mov     rcx, [rsp+1C0h+var_188]
0x1806fe496  test    rcx, rcx
0x1806fe499  jnz     short loc_1806FE4A0
0x1806fe49b  jmp     loc_1806FEA66
0x1806fe4a0  mov     rax, [rcx]
0x1806fe4a3  mov     rax, [rax+18h]
0x1806fe4a7  call    cs:__guard_dispatch_icall_fptr
0x1806fe4ad  mov     r8, rax
0x1806fe4b0  mov     rcx, [rax]
0x1806fe4b3  mov     rax, [rcx+80h]
0x1806fe4ba  lea     rdx, [rbp+0C0h+var_58]
0x1806fe4be  mov     rcx, r8
0x1806fe4c1  call    cs:__guard_dispatch_icall_fptr
0x1806fe4c7  nop
0x1806fe4c8  xorps   xmm0, xmm0
0x1806fe4cb  movups  xmmword ptr [rbp+0C0h+Block], xmm0
0x1806fe4cf  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1806fe4d7  movdqu  [rbp+0C0h+var_68], xmm1
0x1806fe4dc  mov     word ptr [rbp+0C0h+Block], si
0x1806fe4e0  lea     rax, [rbp+0C0h+Block]
0x1806fe4e4  mov     [rsp+1C0h+var_190], rax
0x1806fe4e9  mov     r15d, 105h
0x1806fe4ef  mov     edx, r15d
0x1806fe4f2  lea     rcx, [rbp+0C0h+Block]
0x1806fe4f6  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1806fe4fb  xor     edx, edx
0x1806fe4fd  lea     rcx, [rbp+0C0h+Block]
0x1806fe501  call    ??A?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEA_W_K@Z; std::wstring::operator[](unsigned __int64)
0x1806fe506  lea     r8d, [r15-1]
0x1806fe50a  mov     rdx, rax
0x1806fe50d  lea     rcx, ?vmsoridOutlookSecureTempFolder@@3U_msoreg@@B; _msoreg const vmsoridOutlookSecureTempFolder
0x1806fe514  call    cs:__imp_?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z; MsoFRegReadWz(_msoreg const *,wchar_t *,ulong)
0x1806fe51a  mov     ebx, eax
0x1806fe51c  lea     rcx, [rsp+1C0h+var_190]
0x1806fe521  call    ??1?$basic_strbuffer@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Jot@@QEAA@XZ; Jot::basic_strbuffer<std::wstring>::~basic_strbuffer<std::wstring>(void)
0x1806fe526  test    ebx, ebx
0x1806fe528  jz      loc_1806FE5F7
0x1806fe52e  lea     rdx, [rbp+0C0h+Block]
0x1806fe532  cmp     qword ptr [rbp+0C0h+var_68+8], 7
0x1806fe537  cmova   rdx, [rbp+0C0h+Block]; wchar_t *
0x1806fe53c  lea     rcx, [rbp+0C0h+var_58]
0x1806fe540  cmp     [rbp+0C0h+var_40], 7
0x1806fe548  cmova   rcx, [rbp+0C0h+var_58]; this
0x1806fe54d  call    ?AreEqualPathnames@Url@Jot@@YA_NPEB_W0@Z; Jot::Url::AreEqualPathnames(wchar_t const *,wchar_t const *)
0x1806fe552  test    al, al
0x1806fe554  jz      loc_1806FE5F7
0x1806fe55a  mov     rax, qword ptr [rbp+0C0h+var_68+8]
0x1806fe55e  cmp     rax, 7
0x1806fe562  jbe     short loc_1806FE598
0x1806fe564  mov     rcx, [rbp+0C0h+Block]
0x1806fe568  mov     rdx, rcx
0x1806fe56b  lea     rax, ds:2[rax*2]
0x1806fe573  mov     edi, 1000h
0x1806fe578  cmp     rax, rdi
0x1806fe57b  jb      short loc_1806FE592
0x1806fe57d  mov     rcx, [rcx-8]; Block
0x1806fe581  sub     rdx, rcx
0x1806fe584  lea     rax, [rdx-8]
0x1806fe588  cmp     rax, 1Fh
0x1806fe58c  ja      loc_1806FE9BE
0x1806fe592  call    cs:__imp_free
0x1806fe598  mov     ebx, 4DE1h
0x1806fe59d  mov     [rbp+0C0h+Block], rbx
0x1806fe5a1  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1806fe5a9  movdqu  [rbp+0C0h+var_68], xmm0
0x1806fe5ae  mov     rdx, [rbp+0C0h+var_40]
0x1806fe5b5  cmp     rdx, 7
0x1806fe5b9  jbe     short loc_1806FE5D4
0x1806fe5bb  lea     rdx, ds:2[rdx*2]
0x1806fe5c3  mov     rcx, [rbp+0C0h+var_58]
0x1806fe5c7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1806fe5cc  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1806fe5d4  mov     [rbp+0C0h+var_58], rbx
0x1806fe5d8  movdqu  xmmword ptr [rbp+78h], xmm0
0x1806fe5dd  mov     rcx, [rsp+1C0h+var_188]
0x1806fe5e2  test    rcx, rcx
0x1806fe5e5  jz      loc_1806FE826
0x1806fe5eb  mov     rax, [rcx]
0x1806fe5ee  mov     rax, [rax+10h]
0x1806fe5f2  jmp     loc_1806FE820
0x1806fe5f7  mov     eax, 0Fh
0x1806fe5fc  mov     edi, 1000h
0x1806fe601  mov     dword ptr [rsp+1C0h+var_190], eax
0x1806fe605  cmp     eax, 9
0x1806fe608  jl      loc_1806FE98F
0x1806fe60e  lea     r8, [rsp+1C0h+var_190]
0x1806fe613  lea     rcx, [rbp+0C0h+Src]; Src
0x1806fe61a  call    ??$StringFromPatternWithConverter@$$BY04_WH@MsoCF@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAY04$$CB_WAEBH@Z; MsoCF::StringFromPatternWithConverter<wchar_t [5],int>(wchar_t const (&)[5],int const &)
0x1806fe61f  nop
0x1806fe620  xorps   xmm0, xmm0
0x1806fe623  xor     eax, eax
0x1806fe625  movups  [rbp+0C0h+var_C0], xmm0
0x1806fe629  mov     [rbp+0C0h+var_B0], rax
0x1806fe62d  xorps   xmm1, xmm1
0x1806fe630  movups  [rbp+0C0h+var_A8], xmm1
0x1806fe634  movups  [rbp+0C0h+var_98], xmm1
0x1806fe638  mov     [rbp+0C0h+var_88], sil
0x1806fe63c  lea     rax, [rbp+0C0h+var_C0]
0x1806fe640  mov     qword ptr [rbp+0C0h+var_98], rax
0x1806fe644  xor     eax, eax
0x1806fe646  movups  [rbp+0C0h+var_100], xmm0
0x1806fe64a  mov     [rbp+0C0h+var_F0], rax
0x1806fe64e  movups  [rbp+0C0h+var_E8], xmm1
0x1806fe652  movups  [rbp+0C0h+var_D8], xmm1
0x1806fe656  mov     [rbp+0C0h+var_C8], sil
0x1806fe65a  lea     rax, [rbp+0C0h+var_100]
0x1806fe65e  mov     qword ptr [rbp+0C0h+var_D8], rax
0x1806fe662  xor     eax, eax
0x1806fe664  movups  [rbp+0C0h+var_140], xmm0
0x1806fe668  mov     [rbp+0C0h+var_130], rax
0x1806fe66c  movups  [rbp+0C0h+var_128], xmm1
0x1806fe670  movups  [rbp+0C0h+var_118], xmm1
0x1806fe674  mov     [rbp+0C0h+var_108], sil
0x1806fe678  lea     rax, [rbp+0C0h+var_140]
0x1806fe67c  mov     qword ptr [rbp+0C0h+var_118], rax
0x1806fe680  xor     eax, eax
0x1806fe682  movups  [rsp+1C0h+var_180], xmm0
0x1806fe687  mov     [rsp+1C0h+var_170], rax
0x1806fe68c  movups  [rsp+1C0h+var_168], xmm1
0x1806fe691  movups  [rsp+1C0h+var_158], xmm1
0x1806fe696  mov     [rsp+1C0h+var_148], sil
0x1806fe69b  lea     rax, [rsp+1C0h+var_180]
0x1806fe6a0  mov     qword ptr [rsp+1C0h+var_158], rax
0x1806fe6a5  lea     r8, [rbp+0C0h+Src]
0x1806fe6ac  cmp     [rbp+0C0h+var_20], 7
0x1806fe6b4  cmova   r8, [rbp+0C0h+Src]; wchar_t *
0x1806fe6bc  lea     rdx, ?vmsoridCUOffice@@3U_msoreg@@B; struct _msoreg *
0x1806fe6c3  lea     rcx, [rbp+0C0h+var_C0]; this
0x1806fe6c7  call    ?FInitForKey@DynamicMsorid@@QEAA_NPEBU_msoreg@@PEB_W@Z; DynamicMsorid::FInitForKey(_msoreg const *,wchar_t const *)
0x1806fe6cc  test    al, al
0x1806fe6ce  jz      loc_1806FE840
0x1806fe6d4  cmp     [rbp+0C0h+var_88], sil
0x1806fe6d8  jz      loc_1806FE834
0x1806fe6de  mov     r9d, 7
0x1806fe6e4  lea     r8, aOutlook_0; "Outlook"
0x1806fe6eb  lea     rdx, [rbp+0C0h+var_A8]
0x1806fe6ef  lea     rcx, [rbp+0C0h+var_100]
0x1806fe6f3  call    cs:__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z; DynamicMsorid::InitForKey(_msoreg const &,wchar_t const *,unsigned __int64)
0x1806fe6f9  cmp     [rbp+0C0h+var_C8], sil
0x1806fe6fd  jz      loc_1806FE834
0x1806fe703  mov     r9d, 8
0x1806fe709  lea     r8, aSecurity; "Security"
0x1806fe710  lea     rdx, [rbp+0C0h+var_E8]
0x1806fe714  lea     rcx, [rbp+0C0h+var_140]
0x1806fe718  call    cs:__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z; DynamicMsorid::InitForKey(_msoreg const &,wchar_t const *,unsigned __int64)
0x1806fe71e  cmp     [rbp+0C0h+var_108], sil
0x1806fe722  jz      loc_1806FE82D
0x1806fe728  mov     dword ptr [rsp+1C0h+Reserved], 1
0x1806fe730  mov     r9d, 17h
0x1806fe736  lea     r8, aOutlooksecuret; "OutlookSecureTempFolder"
0x1806fe73d  lea     rdx, [rbp+0C0h+var_128]
0x1806fe741  lea     rcx, [rsp+1C0h+var_180]
0x1806fe746  call    cs:__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z; DynamicMsorid::InitForValue(_msoreg const &,wchar_t const *,unsigned __int64,RegValueType)
0x1806fe74c  lea     rax, [rbp+0C0h+Block]
0x1806fe750  mov     [rbp+0C0h+var_80], rax
0x1806fe754  cmp     qword ptr [rbp+0C0h+var_68], r15
0x1806fe758  jnb     short loc_1806FE766
0x1806fe75a  mov     rdx, r15
0x1806fe75d  lea     rcx, [rbp+0C0h+Block]
0x1806fe761  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1806fe766  xor     edx, edx
0x1806fe768  lea     rcx, [rbp+0C0h+Block]
0x1806fe76c  call    ??A?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEA_W_K@Z; std::wstring::operator[](unsigned __int64)
0x1806fe771  mov     cl, [rsp+1C0h+var_148]
0x1806fe775  neg     cl
0x1806fe777  sbb     rcx, rcx
0x1806fe77a  lea     rdx, [rsp+1C0h+var_168]
0x1806fe77f  and     rcx, rdx
0x1806fe782  mov     r8d, 104h
0x1806fe788  mov     rdx, rax
0x1806fe78b  call    cs:__imp_?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z; MsoFRegReadWz(_msoreg const *,wchar_t *,ulong)
0x1806fe791  mov     ebx, eax
0x1806fe793  lea     rcx, [rbp+0C0h+var_80]
0x1806fe797  call    ??1?$basic_strbuffer@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Jot@@QEAA@XZ; Jot::basic_strbuffer<std::wstring>::~basic_strbuffer<std::wstring>(void)
0x1806fe79c  test    ebx, ebx
0x1806fe79e  jz      loc_1806FE840
0x1806fe7a4  lea     rdx, [rbp+0C0h+Block]
0x1806fe7a8  cmp     qword ptr [rbp+0C0h+var_68+8], 7
0x1806fe7ad  cmova   rdx, [rbp+0C0h+Block]; wchar_t *
0x1806fe7b2  lea     rcx, [rbp+0C0h+var_58]
0x1806fe7b6  cmp     [rbp+0C0h+var_40], 7
0x1806fe7be  cmova   rcx, [rbp+0C0h+var_58]; this
0x1806fe7c3  call    ?AreEqualPathnames@Url@Jot@@YA_NPEB_W0@Z; Jot::Url::AreEqualPathnames(wchar_t const *,wchar_t const *)
0x1806fe7c8  test    al, al
0x1806fe7ca  jz      short loc_1806FE840
0x1806fe7cc  lea     rcx, [rsp+1C0h+var_180]; this
0x1806fe7d1  call    ??1DynamicMsorid@@QEAA@XZ; DynamicMsorid::~DynamicMsorid(void)
0x1806fe7d6  lea     rcx, [rbp+0C0h+var_140]; this
0x1806fe7da  call    ??1DynamicMsorid@@QEAA@XZ; DynamicMsorid::~DynamicMsorid(void)
0x1806fe7df  lea     rcx, [rbp+0C0h+var_100]; this
0x1806fe7e3  call    ??1DynamicMsorid@@QEAA@XZ; DynamicMsorid::~DynamicMsorid(void)
0x1806fe7e8  lea     rcx, [rbp+0C0h+var_C0]; this
0x1806fe7ec  call    ??1DynamicMsorid@@QEAA@XZ; DynamicMsorid::~DynamicMsorid(void)
0x1806fe7f1  lea     rcx, [rbp+0C0h+Src]; void *
0x1806fe7f8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1806fe7fd  lea     rcx, [rbp+0C0h+Block]; void *
0x1806fe801  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1806fe806  lea     rcx, [rbp+0C0h+var_58]; void *
0x1806fe80a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1806fe80f  mov     rcx, [rsp+1C0h+var_188]
0x1806fe814  test    rcx, rcx
0x1806fe817  jz      short loc_1806FE826
0x1806fe819  mov     rdx, [rcx]
0x1806fe81c  mov     rax, [rdx+10h]
0x1806fe820  call    cs:__guard_dispatch_icall_fptr
0x1806fe826  mov     al, 1
0x1806fe828  jmp     loc_1806FEA68
0x1806fe82d  mov     ecx, 1E483458h
0x1806fe832  jmp     short loc_1806FE839
0x1806fe834  mov     ecx, 1E48345Bh
0x1806fe839  call    cs:__imp_MsoShipAssertTagProc
0x1806fe83f  nop
0x1806fe840  cmp     [rsp+1C0h+var_148], sil
0x1806fe845  jz      short loc_1806FE86B
0x1806fe847  lea     rcx, [rsp+1C0h+var_168]
0x1806fe84c  call    cs:__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z; MsoOrapiDeleteFromCache(_msoreg const *)
0x1806fe852  lea     rcx, [rsp+1C0h+var_180]; this
0x1806fe857  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1806fe85c  lea     rcx, [rsp+1C0h+var_168]; this
0x1806fe861  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1806fe866  mov     [rsp+1C0h+var_148], sil
0x1806fe86b  lea     rcx, [rsp+1C0h+var_168]; this
0x1806fe870  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1806fe875  lea     rcx, [rsp+1C0h+var_180]; this
0x1806fe87a  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1806fe87f  cmp     [rbp+0C0h+var_108], sil
0x1806fe883  jz      short loc_1806FE8A5
0x1806fe885  lea     rcx, [rbp+0C0h+var_128]
0x1806fe889  call    cs:__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z; MsoOrapiDeleteFromCache(_msoreg const *)
0x1806fe88f  lea     rcx, [rbp+0C0h+var_140]; this
0x1806fe893  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1806fe898  lea     rcx, [rbp+0C0h+var_128]; this
0x1806fe89c  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1806fe8a1  mov     [rbp+0C0h+var_108], sil
0x1806fe8a5  lea     rcx, [rbp+0C0h+var_128]; this
0x1806fe8a9  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1806fe8ae  lea     rcx, [rbp+0C0h+var_140]; this
0x1806fe8b2  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1806fe8b7  cmp     [rbp+0C0h+var_C8], sil
0x1806fe8bb  jz      short loc_1806FE8DD
0x1806fe8bd  lea     rcx, [rbp+0C0h+var_E8]
0x1806fe8c1  call    cs:__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z; MsoOrapiDeleteFromCache(_msoreg const *)
0x1806fe8c7  lea     rcx, [rbp+0C0h+var_100]; this
0x1806fe8cb  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1806fe8d0  lea     rcx, [rbp+0C0h+var_E8]; this
0x1806fe8d4  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1806fe8d9  mov     [rbp+0C0h+var_C8], sil
0x1806fe8dd  lea     rcx, [rbp+0C0h+var_E8]; this
0x1806fe8e1  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1806fe8e6  lea     rcx, [rbp+0C0h+var_100]; this
0x1806fe8ea  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1806fe8ef  cmp     [rbp+0C0h+var_88], sil
0x1806fe8f3  jz      short loc_1806FE920
0x1806fe8f5  nop     word ptr [rax+rax+00000000h]
0x1806fe900  lea     rcx, [rbp+0C0h+var_A8]
0x1806fe904  call    cs:__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z; MsoOrapiDeleteFromCache(_msoreg const *)
0x1806fe90a  lea     rcx, [rbp+0C0h+var_C0]; this
0x1806fe90e  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1806fe913  lea     rcx, [rbp+0C0h+var_A8]; this
0x1806fe917  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1806fe91c  mov     [rbp+0C0h+var_88], sil
0x1806fe920  lea     rcx, [rbp+0C0h+var_A8]; this
0x1806fe924  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1806fe929  lea     rcx, [rbp+0C0h+var_C0]; this
0x1806fe92d  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1806fe932  mov     rax, [rbp+0C0h+var_20]
0x1806fe939  cmp     rax, 7
0x1806fe93d  jbe     short loc_1806FE96E
0x1806fe93f  nop
0x1806fe940  mov     rcx, [rbp+0C0h+Src]
0x1806fe947  mov     rdx, rcx
0x1806fe94a  lea     rax, ds:2[rax*2]
0x1806fe952  cmp     rax, rdi
0x1806fe955  jb      short loc_1806FE968
0x1806fe957  mov     rcx, [rcx-8]; Block
0x1806fe95b  sub     rdx, rcx
0x1806fe95e  lea     rax, [rdx-8]
0x1806fe962  cmp     rax, 1Fh
0x1806fe966  ja      short loc_1806FE979
0x1806fe968  call    cs:__imp_free
0x1806fe96e  mov     eax, dword ptr [rsp+1C0h+var_190]
0x1806fe972  dec     eax
0x1806fe974  jmp     loc_1806FE601
0x1806fe979  mov     [rsp+1C0h+Reserved], rsi; Reserved
0x1806fe97e  xor     r9d, r9d; LineNo
  ... truncated ...
```
