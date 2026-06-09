# StructuredQuery1::Solution::TranslateValueCondition(SemanticsUM::IValueCondition const *,SemanticsUM::IEntityCondition const *,wchar_t const *,unsigned __int64,SemanticsUM::TokenCollectionUM const &,int &,ICondition2 * *)

- ea: `0x18000e4ec`
- end: `0x18000e9d6`
- name: `?TranslateValueCondition@Solution@StructuredQuery1@@AEAAJPEBVIValueCondition@SemanticsUM@@PEBVIEntityCondition@4@PEB_W_KAEBVTokenCollectionUM@4@AEAHPEAPEAUICondition2@@@Z`
- size: `1258`
- prototype: `__int64 __usercall@<rax>(StructuredQuery1::Solution *__hidden this@<rcx>, const struct SemanticsUM::IValueCondition *@<rdx>, const struct SemanticsUM::IEntityCondition *@<r8>, const wchar_t *@<r9>, unsigned __int64, const struct SemanticsUM::TokenCollectionUM *, int *, struct ICondition2 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000ddc8`

## callees

- `0x1800094f8`
- `0x180009a40`
- `0x18000e4ec`
- `0x18000e9dc`
- `0x18000ea6c`
- `0x18005daf0`
- `0x18005db64`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180087aca`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180087aca`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000e6e0`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000e6e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StructuredQuery1::Solution::TranslateValueCondition(
        wchar_t *this,
        const struct SemanticsUM::IValueCondition *a2,
        const struct SemanticsUM::IEntityCondition *a3,
        const wchar_t *a4,
        unsigned __int64 a5,
        const struct SemanticsUM::TokenCollectionUM *a6,
        int *a7,
        struct ICondition2 **a8)
{
  __int64 v11; // r8
  PCNZWCH *v12; // rax
  __int64 v13; // r8
  int KeyFromConditionPropertyName; // edi
  __int64 v15; // r12
  char *v16; // rcx
  int v17; // eax
  int v18; // ecx
  char *v19; // rcx
  int v20; // r15d
  __int64 v21; // r8
  struct IRichChunk *v22; // r14
  _QWORD *v23; // rax
  _QWORD *v24; // rbx
  int v25; // eax
  struct ICondition2 *v26; // r15
  struct IRichChunk *v28; // rbx
  enum tagCONDITION_OPERATION v29; // r15d
  char *v30; // rcx
  int v31; // ebx
  char *v32; // rcx
  __int64 v33; // rax
  char *v34; // rcx
  int v35; // eax
  struct _tagpropertykey *v36; // r8
  struct IRichChunk *v37; // rsi
  const wchar_t *v38; // r9
  char *v39; // rcx
  __int64 v40; // rax
  char *v41; // rcx
  __int64 v42; // rax
  PCNZWCH *v43; // rax
  int v44; // eax
  char *v45; // rcx
  __int64 v46; // rax
  _QWORD *v47; // rbx
  __int64 v48; // r8
  const struct _GUID *lpString2; // [rsp+20h] [rbp-E0h]
  void *v50; // [rsp+70h] [rbp-90h] BYREF
  int v51; // [rsp+78h] [rbp-88h]
  struct ICondition2 *v52; // [rsp+80h] [rbp-80h]
  __int64 v53; // [rsp+88h] [rbp-78h]
  int v54; // [rsp+90h] [rbp-70h]
  enum tagCONDITION_OPERATION v55; // [rsp+94h] [rbp-6Ch]
  struct ICondition2 *v56; // [rsp+98h] [rbp-68h] BYREF
  __int128 v57; // [rsp+A0h] [rbp-60h] BYREF
  struct tagPROPVARIANT pvarSrc; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v59; // [rsp+C8h] [rbp-38h] BYREF
  __int128 *v60; // [rsp+D8h] [rbp-28h]
  wchar_t *Buffer; // [rsp+E0h] [rbp-20h]
  __int64 (__fastcall ***v62)(_QWORD); // [rsp+E8h] [rbp-18h]
  struct ICondition2 **v63; // [rsp+F0h] [rbp-10h]
  PROPERTYKEY v64; // [rsp+F8h] [rbp-8h] BYREF

  v63 = a8;
  v52 = 0;
  v56 = 0;
  Buffer = (wchar_t *)(*(__int64 (__fastcall **)(const struct SemanticsUM::IEntityCondition *))(*(_QWORD *)a3 + 16LL))(a3);
  v11 = *(int *)(*((_QWORD *)a2 + 1) + 4LL);
  v12 = (PCNZWCH *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)((char *)a2 + v11 + 8) + 16LL))((char *)a2 + v11 + 8);
  v55 = (unsigned int)StructuredQuery1::OperationFromModifier(*v12);
  v62 = (__int64 (__fastcall ***)(_QWORD))(**(__int64 (__fastcall ***)(const struct SemanticsUM::IValueCondition *))a2)(a2);
  v53 = (*(__int64 (__fastcall **)(const struct SemanticsUM::IValueCondition *))(*(_QWORD *)a2 + 16LL))(a2);
  v13 = *(int *)(*((_QWORD *)a2 + 1) + 4LL);
  KeyFromConditionPropertyName = 1;
  if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)((char *)a2 + v13 + 8) + 40LL))((char *)a2 + v13 + 8)
    && (v39 = (char *)a2 + *(int *)(*((_QWORD *)a2 + 1) + 4LL) + 8,
        v40 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v39 + 40LL))(v39),
        *(_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40))
    && (v41 = (char *)a2 + *(int *)(*((_QWORD *)a2 + 1) + 4LL) + 8,
        v42 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v41 + 40LL))(v41),
        v43 = (PCNZWCH *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42),
        v44 = CompareStringW(0x7Fu, 0, *v43, -1, L"dotdot", -1),
        v44 == 2) )
  {
    v45 = (char *)a2 + *(int *)(*((_QWORD *)a2 + 1) + 4LL) + 8;
    v46 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v45 + 40LL))(v45);
    v47 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v46 + 72LL))(v46);
    v15 = (*(__int64 (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
    v48 = *(int *)(v47[1] + 4LL);
    v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)((char *)v47 + v48 + 8) + 32LL))((__int64)v47 + v48 + 8);
    v18 = 2;
  }
  else
  {
    v15 = 0;
    v16 = (char *)a2 + *(int *)(*((_QWORD *)a2 + 1) + 4LL) + 8;
    v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v16 + 32LL))(v16);
    v18 = 1;
  }
  v51 = v17;
  *a7 = v18;
  pvarSrc.vt = 3;
  memset(&pvarSrc.decVal.scale, 0, 22);
  pvarSrc.lVal = (*(__int64 (__fastcall **)(const struct SemanticsUM::IEntityCondition *))(*(_QWORD *)a3 + 24LL))(a3);
  v19 = (char *)a3 + *(int *)(*((_QWORD *)a3 + 1) + 4LL) + 8;
  v20 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v19 + 32LL))(v19);
  v21 = *(int *)(*((_QWORD *)a3 + 1) + 4LL);
  v54 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)((char *)a3 + v21 + 8) + 24LL))((char *)a3 + v21 + 8);
  v22 = 0;
  v50 = 0;
  if ( v54 >= 0 && v20 >= 0 )
  {
    v23 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
    v24 = v23;
    *(_QWORD *)&v57 = v23;
    if ( v23 )
    {
      *v23 = &StructuredQuery1::TokenInformation::`vftable';
      v25 = v54;
      *((_DWORD *)v24 + 2) = v54;
      *((_DWORD *)v24 + 3) = v20 - v25;
      v24[5] = this;
      *((_DWORD *)v24 + 12) = 1;
      _InterlockedAdd(&dword_1800B134C, 1u);
      *((_OWORD *)v24 + 1) = 0;
      v24[4] = 0;
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v24[5] + 8LL))(v24[5]);
    }
    else
    {
      v24 = 0;
    }
    if ( !v24 )
    {
      KeyFromConditionPropertyName = -2147024882;
      goto LABEL_12;
    }
    KeyFromConditionPropertyName = PropVariantCopy((PROPVARIANT *)v24 + 2, (const PROPVARIANT *)&pvarSrc);
    if ( KeyFromConditionPropertyName >= 0 )
      KeyFromConditionPropertyName = (*(__int64 (__fastcall **)(_QWORD *, GUID *, void **))*v24)(
                                       v24,
                                       &GUID_4fdef69c_dbc9_454e_9910_b34f3c64b510,
                                       &v50);
    (*(void (__fastcall **)(_QWORD *))(*v24 + 16LL))(v24);
    v22 = (struct IRichChunk *)v50;
  }
  if ( KeyFromConditionPropertyName < 0 )
  {
LABEL_12:
    v26 = v52;
    goto LABEL_13;
  }
  v28 = 0;
  v50 = 0;
  v29 = v55;
  if ( v55 == COP_IMPLICIT )
    goto LABEL_17;
  pvarSrc.lVal = 0;
  v30 = (char *)a2 + *(int *)(*((_QWORD *)a2 + 1) + 4LL) + 8;
  v31 = *(_DWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v30 + 16LL))(v30) + 12);
  v32 = (char *)a2 + *(int *)(*((_QWORD *)a2 + 1) + 4LL) + 8;
  v33 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v32 + 16LL))(v32);
  KeyFromConditionPropertyName = StructuredQuery1::TokenInformation::CreateInstance(
                                   *(_DWORD *)(v33 + 8),
                                   v31,
                                   (struct StructuredQuery1::Solution *)this,
                                   &pvarSrc,
                                   lpString2,
                                   &v50);
  if ( KeyFromConditionPropertyName >= 0 )
  {
    v28 = (struct IRichChunk *)v50;
LABEL_17:
    pvarSrc.lVal = (*(__int64 (__fastcall **)(const struct SemanticsUM::IValueCondition *))(*(_QWORD *)a2 + 24LL))(a2)
                 | 0x40;
    v50 = 0;
    v34 = (char *)a2 + *(int *)(*((_QWORD *)a2 + 1) + 4LL) + 8;
    v35 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v34 + 24LL))(v34);
    KeyFromConditionPropertyName = StructuredQuery1::TokenInformation::CreateInstance(
                                     v35,
                                     v51,
                                     (struct StructuredQuery1::Solution *)this,
                                     &pvarSrc,
                                     lpString2,
                                     &v50);
    if ( KeyFromConditionPropertyName < 0 )
    {
      v26 = v52;
    }
    else
    {
      v57 = 0;
      v59 = 0;
      v60 = 0;
      if ( v15 )
      {
        *(_QWORD *)&v57 = v53;
        *((_QWORD *)&v57 + 1) = v15;
        LOWORD(v59) = 4127;
        DWORD2(v59) = 2;
        v60 = &v57;
      }
      else
      {
        LOWORD(v59) = 31;
        *((_QWORD *)&v59 + 1) = v53;
      }
      memset(&v64, 0, sizeof(v64));
      KeyFromConditionPropertyName = StructuredQuery1::GetKeyFromConditionPropertyName(Buffer, &v64, v36);
      v37 = (struct IRichChunk *)v50;
      if ( KeyFromConditionPropertyName < 0 )
      {
        v26 = v52;
      }
      else
      {
        if ( v62 )
          v38 = (const wchar_t *)(**v62)(v62);
        else
          v38 = 0;
        KeyFromConditionPropertyName = StructuredQuery1::Solution::MakePredicate(
                                         (__int64)this,
                                         &v64,
                                         v29,
                                         v38,
                                         (PROPVARIANT *)&v59,
                                         this + 44,
                                         0,
                                         v22,
                                         v28,
                                         v37,
                                         0,
                                         0,
                                         &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                                         (void **)&v56);
        v26 = v56;
      }
      if ( v37 )
        ((void (__fastcall *)(struct IRichChunk *))v37->lpVtbl->Release)(v37);
    }
    if ( v28 )
      ((void (__fastcall *)(struct IRichChunk *))v28->lpVtbl->Release)(v28);
    goto LABEL_28;
  }
  v26 = v52;
LABEL_28:
  if ( v22 )
    ((void (__fastcall *)(struct IRichChunk *))v22->lpVtbl->Release)(v22);
LABEL_13:
  *v63 = v26;
  return (unsigned int)KeyFromConditionPropertyName;
}

```

## disassembly

```asm
0x18000e4ec  mov     [rsp-8+arg_18], rbx
0x18000e4f1  push    rbp
0x18000e4f2  push    rsi
0x18000e4f3  push    rdi
0x18000e4f4  push    r12
0x18000e4f6  push    r13
0x18000e4f8  push    r14
0x18000e4fa  push    r15
0x18000e4fc  lea     rbp, [rsp-20h]
0x18000e501  sub     rsp, 120h
0x18000e508  mov     rax, cs:__security_cookie
0x18000e50f  xor     rax, rsp
0x18000e512  mov     [rbp+50h+var_40], rax
0x18000e516  mov     r14, r8
0x18000e519  mov     rsi, rdx
0x18000e51c  mov     r13, rcx
0x18000e51f  mov     r15, [rbp+50h+arg_30]
0x18000e526  mov     rax, [rbp+50h+arg_38]
0x18000e52d  mov     [rbp+50h+var_60], rax
0x18000e531  xor     eax, eax
0x18000e533  mov     [rbp+50h+var_D0], rax
0x18000e537  mov     [rbp+50h+var_B8], rax
0x18000e53b  mov     rax, [r8]
0x18000e53e  mov     rcx, r8
0x18000e541  mov     rax, [rax+10h]
0x18000e545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e54a  mov     [rbp+50h+Buffer], rax
0x18000e54e  mov     rcx, [rsi+8]
0x18000e552  movsxd  r8, dword ptr [rcx+4]
0x18000e556  mov     rcx, [r8+rsi+8]
0x18000e55b  mov     rax, [rcx+10h]
0x18000e55f  lea     rcx, [rsi+8]
0x18000e563  add     rcx, r8
0x18000e566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e56b  mov     rcx, [rax]; lpString1
0x18000e56e  call    StructuredQuery1__OperationFromModifier
0x18000e573  mov     [rbp+50h+var_BC], eax
0x18000e576  mov     rcx, [rsi]
0x18000e579  mov     rax, [rcx]
0x18000e57c  mov     rcx, rsi
0x18000e57f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e584  mov     [rbp+50h+var_68], rax
0x18000e588  mov     rcx, [rsi]
0x18000e58b  mov     rax, [rcx+10h]
0x18000e58f  mov     rcx, rsi
0x18000e592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e597  mov     [rbp+50h+var_C8], rax
0x18000e59b  mov     rcx, [rsi+8]
0x18000e59f  movsxd  r8, dword ptr [rcx+4]
0x18000e5a3  mov     rcx, [r8+rsi+8]
0x18000e5a8  mov     rax, [rcx+28h]
0x18000e5ac  lea     rcx, [rsi+8]
0x18000e5b0  add     rcx, r8
0x18000e5b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5b8  mov     edi, 1
0x18000e5bd  test    rax, rax
0x18000e5c0  jnz     loc_18000E991
0x18000e5c6  xor     r12d, r12d
0x18000e5c9  mov     rax, [rsi+8]
0x18000e5cd  movsxd  rcx, dword ptr [rax+4]
0x18000e5d1  add     rcx, 8
0x18000e5d5  add     rcx, rsi
0x18000e5d8  mov     rax, [rcx]
0x18000e5db  mov     rax, [rax+20h]
0x18000e5df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5e4  mov     ecx, edi
0x18000e5e6  mov     [rsp+150h+var_D8], eax
0x18000e5ea  mov     [r15], ecx
0x18000e5ed  mov     eax, 3
0x18000e5f2  mov     word ptr [rbp+50h+pvarSrc], ax
0x18000e5f6  xorps   xmm0, xmm0
0x18000e5f9  xor     eax, eax
0x18000e5fb  movups  xmmword ptr [rbp+50h+pvarSrc+2], xmm0
0x18000e5ff  mov     qword ptr [rbp+50h+pvarSrc+10h], rax
0x18000e603  mov     rax, [r14]
0x18000e606  mov     rcx, r14
0x18000e609  mov     rax, [rax+18h]
0x18000e60d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e612  mov     dword ptr [rbp+50h+pvarSrc+8], eax
0x18000e615  mov     rax, [r14+8]
0x18000e619  movsxd  rcx, dword ptr [rax+4]
0x18000e61d  add     rcx, 8
0x18000e621  add     rcx, r14
0x18000e624  mov     rax, [rcx]
0x18000e627  mov     rax, [rax+20h]
0x18000e62b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e630  mov     r15d, eax
0x18000e633  mov     rcx, [r14+8]
0x18000e637  movsxd  r8, dword ptr [rcx+4]
0x18000e63b  mov     rcx, [r8+r14+8]
0x18000e640  mov     rax, [rcx+18h]
0x18000e644  lea     rcx, [r14+8]
0x18000e648  add     rcx, r8
0x18000e64b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e650  mov     [rbp+50h+var_C0], eax
0x18000e653  xor     r14d, r14d
0x18000e656  mov     [rsp+150h+var_E0], r14
0x18000e65b  test    eax, eax
0x18000e65d  js      loc_18000E71C
0x18000e663  test    r15d, r15d
0x18000e666  js      loc_18000E71C
0x18000e66c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e673  lea     ecx, [r14+38h]; unsigned __int64
0x18000e677  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e67c  mov     rbx, rax
0x18000e67f  mov     qword ptr [rbp+50h+var_B0], rax
0x18000e683  test    rax, rax
0x18000e686  jz      loc_18000E982
0x18000e68c  lea     rax, ??_7TokenInformation@StructuredQuery1@@6B@; const StructuredQuery1::TokenInformation::`vftable'
0x18000e693  mov     [rbx], rax
0x18000e696  mov     eax, [rbp+50h+var_C0]
0x18000e699  mov     [rbx+8], eax
0x18000e69c  sub     r15d, eax
0x18000e69f  mov     [rbx+0Ch], r15d
0x18000e6a3  mov     [rbx+28h], r13
0x18000e6a7  mov     [rbx+30h], edi
0x18000e6aa  lock add cs:dword_1800B134C, edi
0x18000e6b1  xorps   xmm0, xmm0
0x18000e6b4  xor     eax, eax
0x18000e6b6  movups  xmmword ptr [rbx+10h], xmm0
0x18000e6ba  mov     [rbx+20h], rax
0x18000e6be  mov     rcx, [rbx+28h]
0x18000e6c2  mov     rax, [rcx]
0x18000e6c5  mov     rax, [rax+8]
0x18000e6c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6ce  nop
0x18000e6cf  test    rbx, rbx
0x18000e6d2  jz      loc_18000E93E
0x18000e6d8  lea     rcx, [rbx+10h]; pvarDest
0x18000e6dc  lea     rdx, [rbp+50h+pvarSrc]; pvarSrc
0x18000e6e0  call    cs:__imp_PropVariantCopy
0x18000e6e6  mov     edi, eax
0x18000e6e8  test    eax, eax
0x18000e6ea  js      short loc_18000E708
0x18000e6ec  mov     rax, [rbx]
0x18000e6ef  lea     r8, [rsp+150h+var_E0]
0x18000e6f4  lea     rdx, _GUID_4fdef69c_dbc9_454e_9910_b34f3c64b510
0x18000e6fb  mov     rcx, rbx
0x18000e6fe  mov     rax, [rax]
0x18000e701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e706  mov     edi, eax
0x18000e708  mov     rax, [rbx]
0x18000e70b  mov     rcx, rbx
0x18000e70e  mov     rax, [rax+10h]
0x18000e712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e717  mov     r14, [rsp+150h+var_E0]
0x18000e71c  test    edi, edi
0x18000e71e  jns     short loc_18000E754
0x18000e720  mov     r15, [rbp+50h+var_D0]
0x18000e724  mov     rax, [rbp+50h+var_60]
0x18000e728  mov     [rax], r15
0x18000e72b  mov     eax, edi
0x18000e72d  mov     rcx, [rbp+50h+var_40]
0x18000e731  xor     rcx, rsp; StackCookie
0x18000e734  call    __security_check_cookie
0x18000e739  mov     rbx, [rsp+150h+arg_18]
0x18000e741  add     rsp, 120h
0x18000e748  pop     r15
0x18000e74a  pop     r14
0x18000e74c  pop     r13
0x18000e74e  pop     r12
0x18000e750  pop     rdi
0x18000e751  pop     rsi
0x18000e752  pop     rbp
0x18000e753  retn
0x18000e754  xor     ebx, ebx
0x18000e756  mov     [rsp+150h+var_E0], rbx
0x18000e75b  mov     r15d, [rbp+50h+var_BC]
0x18000e75f  test    r15d, r15d
0x18000e762  jz      short loc_18000E7CA
0x18000e764  mov     dword ptr [rbp+50h+pvarSrc+8], ebx
0x18000e767  mov     rax, [rsi+8]
0x18000e76b  movsxd  rcx, dword ptr [rax+4]
0x18000e76f  add     rcx, 8
0x18000e773  add     rcx, rsi
0x18000e776  mov     rax, [rcx]
0x18000e779  mov     rax, [rax+10h]
0x18000e77d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e782  mov     ebx, [rax+0Ch]
0x18000e785  mov     rax, [rsi+8]
0x18000e789  movsxd  rcx, dword ptr [rax+4]
0x18000e78d  add     rcx, 8
0x18000e791  add     rcx, rsi
0x18000e794  mov     rax, [rcx]
0x18000e797  mov     rax, [rax+10h]
0x18000e79b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7a0  lea     rcx, [rsp+150h+var_E0]
0x18000e7a5  mov     qword ptr [rsp+150h+cchCount2], rcx; void **
0x18000e7aa  lea     r9, [rbp+50h+pvarSrc]; struct tagPROPVARIANT *
0x18000e7ae  mov     r8, r13; struct StructuredQuery1::Solution *
0x18000e7b1  mov     edx, ebx; int
0x18000e7b3  mov     ecx, [rax+8]; int
0x18000e7b6  call    ?CreateInstance@TokenInformation@StructuredQuery1@@SAJJJPEAVSolution@2@PEAUtagPROPVARIANT@@AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::TokenInformation::CreateInstance(long,long,StructuredQuery1::Solution *,tagPROPVARIANT *,_GUID const &,void * *)
0x18000e7bb  mov     edi, eax
0x18000e7bd  test    eax, eax
0x18000e7bf  js      loc_18000E94E
0x18000e7c5  mov     rbx, [rsp+150h+var_E0]
0x18000e7ca  mov     rax, [rsi]
0x18000e7cd  mov     rcx, rsi
0x18000e7d0  mov     rax, [rax+18h]
0x18000e7d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7d9  or      eax, 40h
0x18000e7dc  mov     dword ptr [rbp+50h+pvarSrc+8], eax
0x18000e7df  mov     [rsp+150h+var_E0], 0
0x18000e7e8  mov     rax, [rsi+8]
0x18000e7ec  movsxd  rcx, dword ptr [rax+4]
0x18000e7f0  add     rcx, 8
0x18000e7f4  add     rcx, rsi
0x18000e7f7  mov     rax, [rcx]
0x18000e7fa  mov     rax, [rax+18h]
0x18000e7fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e803  lea     rcx, [rsp+150h+var_E0]
0x18000e808  mov     qword ptr [rsp+150h+cchCount2], rcx; void **
0x18000e80d  lea     r9, [rbp+50h+pvarSrc]; struct tagPROPVARIANT *
0x18000e811  mov     r8, r13; struct StructuredQuery1::Solution *
0x18000e814  mov     edx, [rsp+150h+var_D8]; int
0x18000e818  mov     ecx, eax; int
0x18000e81a  call    ?CreateInstance@TokenInformation@StructuredQuery1@@SAJJJPEAVSolution@2@PEAUtagPROPVARIANT@@AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::TokenInformation::CreateInstance(long,long,StructuredQuery1::Solution *,tagPROPVARIANT *,_GUID const &,void * *)
0x18000e81f  mov     edi, eax
0x18000e821  test    eax, eax
0x18000e823  js      loc_18000E9CD
0x18000e829  xorps   xmm0, xmm0
0x18000e82c  movups  [rbp+50h+var_B0], xmm0
0x18000e830  xorps   xmm1, xmm1
0x18000e833  xor     eax, eax
0x18000e835  movups  [rbp+50h+var_88], xmm1
0x18000e839  mov     [rbp+50h+var_78], rax
0x18000e83d  test    r12, r12
0x18000e840  jnz     loc_18000E954
0x18000e846  lea     eax, [r12+1Fh]
0x18000e84b  mov     word ptr [rbp+50h+var_88], ax
0x18000e84f  mov     rax, [rbp+50h+var_C8]
0x18000e853  mov     dword ptr [rbp+50h+var_88+8], eax
0x18000e856  mov     eax, dword ptr [rbp+50h+var_C8+4]
0x18000e859  mov     dword ptr [rbp+50h+var_88+0Ch], eax
0x18000e85c  xor     eax, eax
0x18000e85e  movups  xmmword ptr [rbp+50h+var_58], xmm0
0x18000e862  mov     [rbp+50h+var_48], eax
0x18000e865  lea     rdx, [rbp+50h+var_58]; wchar_t *
0x18000e869  mov     rcx, [rbp+50h+Buffer]; Buffer
0x18000e86d  call    ?GetKeyFromConditionPropertyName@StructuredQuery1@@YAJPEB_WPEAU_tagpropertykey@@@Z; StructuredQuery1::GetKeyFromConditionPropertyName(wchar_t const *,_tagpropertykey *)
0x18000e872  mov     edi, eax
0x18000e874  mov     rsi, [rsp+150h+var_E0]
0x18000e879  test    eax, eax
0x18000e87b  js      loc_18000E948
0x18000e881  mov     rcx, [rbp+50h+var_68]
0x18000e885  test    rcx, rcx
0x18000e888  jz      loc_18000E989
0x18000e88e  mov     rax, [rcx]
0x18000e891  mov     rax, [rax]
0x18000e894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e899  mov     r9, rax
0x18000e89c  lea     rax, [r13+58h]
0x18000e8a0  lea     rcx, [rbp+50h+var_B8]
0x18000e8a4  mov     [rsp+150h+var_E8], rcx
0x18000e8a9  lea     rcx, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x18000e8b0  mov     [rsp+150h+var_F0], rcx
0x18000e8b5  mov     [rsp+150h+var_F8], 0
0x18000e8ba  mov     [rsp+150h+var_100], 0
0x18000e8bf  mov     [rsp+150h+var_108], rsi
0x18000e8c4  mov     [rsp+150h+var_110], rbx
0x18000e8c9  mov     [rsp+150h+var_118], r14
0x18000e8ce  mov     [rsp+150h+var_120], 0
0x18000e8d6  mov     qword ptr [rsp+150h+cchCount2], rax
0x18000e8db  lea     rax, [rbp+50h+var_88]
0x18000e8df  mov     [rsp+150h+lpString2], rax
0x18000e8e4  mov     r8d, r15d
0x18000e8e7  lea     rdx, [rbp+50h+var_58]
0x18000e8eb  mov     rcx, r13
0x18000e8ee  call    ?MakePredicate@Solution@StructuredQuery1@@QEAAJAEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@PEB_WAEBUtagPROPVARIANT@@2W4LANGUAGE_OVERRIDE_CHECK@2@PEAUIRichChunk@@55_N6AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::Solution::MakePredicate(_tagpropertykey const &,tagCONDITION_OPERATION,wchar_t const *,tagPROPVARIANT const &,wchar_t const *,StructuredQuery1::LANGUAGE_OVERRIDE_CHECK,IRichChunk *,IRichChunk *,IRichChunk *,bool,bool,_GUID const &,void * *)
0x18000e8f3  mov     edi, eax
0x18000e8f5  mov     r15, [rbp+50h+var_B8]
0x18000e8f9  test    rsi, rsi
0x18000e8fc  jz      short loc_18000E90D
0x18000e8fe  mov     rax, [rsi]
0x18000e901  mov     rcx, rsi
0x18000e904  mov     rax, [rax+10h]
0x18000e908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e90d  test    rbx, rbx
0x18000e910  jz      short loc_18000E921
0x18000e912  mov     rax, [rbx]
0x18000e915  mov     rcx, rbx
0x18000e918  mov     rax, [rax+10h]
0x18000e91c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e921  test    r14, r14
0x18000e924  jz      loc_18000E724
0x18000e92a  mov     rax, [r14]
0x18000e92d  mov     rcx, r14
0x18000e930  mov     rax, [rax+10h]
0x18000e934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e939  jmp     loc_18000E724
0x18000e93e  mov     edi, 8007000Eh
0x18000e943  jmp     loc_18000E720
0x18000e948  mov     r15, [rbp+50h+var_D0]
0x18000e94c  jmp     short loc_18000E8F9
0x18000e94e  mov     r15, [rbp+50h+var_D0]
0x18000e952  jmp     short loc_18000E921
0x18000e954  mov     rax, [rbp+50h+var_C8]
0x18000e958  mov     dword ptr [rbp+50h+var_B0], eax
0x18000e95b  mov     eax, dword ptr [rbp+50h+var_C8+4]
  ... truncated ...
```
