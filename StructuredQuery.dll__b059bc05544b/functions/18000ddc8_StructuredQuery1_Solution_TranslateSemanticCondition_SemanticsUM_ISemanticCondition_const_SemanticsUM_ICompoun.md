# StructuredQuery1::Solution::TranslateSemanticCondition(SemanticsUM::ISemanticCondition const *,SemanticsUM::ICompoundCondition const *,wchar_t const *,unsigned __int64,SemanticsUM::TokenCollectionUM const &,int &,StructuredQuery1::ConnectedQuery *)

- ea: `0x18000ddc8`
- end: `0x18000e23e`
- name: `?TranslateSemanticCondition@Solution@StructuredQuery1@@AEAAJPEBVISemanticCondition@SemanticsUM@@PEBVICompoundCondition@4@PEB_W_KAEBVTokenCollectionUM@4@AEAHPEAUConnectedQuery@2@@Z`
- size: `1142`
- prototype: `__int64 __fastcall(StructuredQuery1::Solution *__hidden this, const struct SemanticsUM::ISemanticCondition *, const struct SemanticsUM::ICompoundCondition *, const wchar_t *, struct _GUID *, const struct SemanticsUM::TokenCollectionUM *, int *, struct StructuredQuery1::ConnectedQuery *)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000ddc8`
- `0x18003cecc`

## callees

- `0x1800090c0`
- `0x1800094f8`
- `0x18000b180`
- `0x18000c3a0`
- `0x18000c9c4`
- `0x18000ddc8`
- `0x18000e4ec`
- `0x18000ea6c`
- `0x18003f7a0`
- `0x18005daf0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000dee9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000df65`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e194`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000dee9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000df65`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e194`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::Solution::TranslateSemanticCondition(
        StructuredQuery1::Solution *this,
        const struct SemanticsUM::ISemanticCondition *a2,
        const struct SemanticsUM::ICompoundCondition *a3,
        const wchar_t *a4,
        struct _GUID *a5,
        const struct SemanticsUM::TokenCollectionUM *a6,
        int *a7,
        struct StructuredQuery1::ConnectedQuery *a8)
{
  struct ICondition *v9; // r14
  const wchar_t *v10; // r12
  __int64 v13; // rax
  int v14; // ecx
  __int64 v15; // rax
  const struct SemanticsUM::IValueCondition *v16; // r15
  __int64 v17; // r8
  const struct SemanticsUM::IEntityCondition *v18; // rax
  const wchar_t *v19; // r9
  int v20; // eax
  int Compound; // edi
  PCNZWCH *v22; // rax
  PCNZWCH *v23; // rax
  const struct SemanticsUM::ICompoundCondition *v25; // rbx
  const struct SemanticsUM::ISemanticCondition *v26; // r15
  __int64 v27; // r8
  LARGE_INTEGER hVal; // r12
  int i; // ebx
  __int64 v30; // rax
  struct ICondition *v31; // rbx
  StructuredQuery1::Solution *v32; // rcx
  struct IObjectArray *v33; // rbx
  struct IConditionVtbl *lpVtbl; // rax
  __int64 *v35; // rax
  __int64 *v36; // r15
  PCNZWCH *v37; // rax
  int v38; // eax
  int v39; // ecx
  __int64 v40; // rcx
  __int64 v41; // rax
  char *v42; // rcx
  int v43; // ebx
  __int64 v44; // r8
  int v45; // eax
  __int64 v46; // rax
  wchar_t *v47; // rax
  struct _tagpropertykey *v48; // r8
  const struct _GUID *lpString2; // [rsp+20h] [rbp-E0h]
  const struct SemanticsUM::TokenCollectionUM *cchCount2; // [rsp+28h] [rbp-D8h]
  int v51[4]; // [rsp+70h] [rbp-90h] BYREF
  struct ICondition *v52[2]; // [rsp+80h] [rbp-80h] BYREF
  enum tagCONDITION_TYPE v53[2]; // [rsp+90h] [rbp-70h] BYREF
  struct tagPROPVARIANT v54; // [rsp+A0h] [rbp-60h] BYREF
  struct IObjectArray *v55; // [rsp+C0h] [rbp-40h] BYREF
  void *v56; // [rsp+C8h] [rbp-38h] BYREF
  struct SemanticsUM::TokenCollectionUM *v57; // [rsp+D0h] [rbp-30h]
  const struct SemanticsUM::ICompoundCondition *v58; // [rsp+D8h] [rbp-28h]
  const wchar_t *v59; // [rsp+E0h] [rbp-20h]
  struct StructuredQuery1::ConnectedQuery *v60; // [rsp+E8h] [rbp-18h]
  PROPERTYKEY v61; // [rsp+F0h] [rbp-10h] BYREF

  v9 = 0;
  v57 = a6;
  v10 = a4;
  v60 = a8;
  v13 = *((_QWORD *)this + 4);
  v59 = a4;
  v52[1] = 0;
  v14 = *(_DWORD *)(v13 + 64);
  HIDWORD(v52[0]) = 0;
  *a7 = 1;
  v15 = *(_QWORD *)a2;
  LODWORD(v52[0]) = v14;
  v16 = (const struct SemanticsUM::IValueCondition *)(*(__int64 (__fastcall **)(const struct SemanticsUM::ISemanticCondition *))(v15 + 72))(a2);
  if ( v16 )
  {
    v17 = *(int *)(*((_QWORD *)a3 + 1) + 4LL);
    v18 = (const struct SemanticsUM::IEntityCondition *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)((char *)a3 + v17 + 8)
                                                                                          + 64LL))((char *)a3 + v17 + 8);
    v20 = StructuredQuery1::Solution::TranslateValueCondition(
            this,
            v16,
            v18,
            v19,
            (unsigned __int64)lpString2,
            cchCount2,
            a7,
            (struct ICondition2 **)&v52[1]);
    v9 = v52[1];
    Compound = v20;
    goto LABEL_3;
  }
  v25 = (const struct SemanticsUM::ICompoundCondition *)(*(__int64 (__fastcall **)(const struct SemanticsUM::ISemanticCondition *))(*(_QWORD *)a2 + 56LL))(a2);
  v58 = v25;
  v26 = (const struct SemanticsUM::ISemanticCondition *)(**(__int64 (__fastcall ***)(const struct SemanticsUM::ICompoundCondition *))v25)(v25);
  if ( v26 )
  {
    Compound = 0;
    while ( v26 )
    {
      v51[0] = 0;
      *(_OWORD *)&v54.vt = 0;
      Compound = StructuredQuery1::Solution::TranslateSemanticCondition(
                   this,
                   v26,
                   v25,
                   v10,
                   a5,
                   v57,
                   v51,
                   (struct StructuredQuery1::ConnectedQuery *)&v54);
      if ( Compound >= 0 )
      {
        hVal = v54.hVal;
        if ( v54.hVal.QuadPart )
        {
          if ( v9 )
          {
            v30 = *((_QWORD *)this + 4);
            v31 = v9;
            *(_QWORD *)v61.fmtid.Data4 = v54.hVal.QuadPart;
            v9 = 0;
            *(_QWORD *)&v61.fmtid.Data1 = v31;
            v56 = 0;
            LODWORD(v52[0]) = *(_DWORD *)(v30 + 64);
            v53[0] = *(enum tagCONDITION_TYPE *)&v54.vt;
            v55 = 0;
            Compound = FixedCapacityObjectCollection::CreateInstance<ICondition>(2u, (__int64)&v61, v27, &v55);
            if ( Compound >= 0 )
            {
              v33 = v55;
              Compound = StructuredQuery1::Solution::MakeCompound(
                           v32,
                           v53[0],
                           v55,
                           1,
                           1,
                           &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                           &v56);
              ((void (__fastcall *)(struct IObjectArray *))v33->lpVtbl->Release)(v33);
              v9 = (struct ICondition *)v56;
              v31 = *(struct ICondition **)&v61.fmtid.Data1;
            }
            lpVtbl = v31->lpVtbl;
            v52[1] = v9;
            ((void (__fastcall *)(struct ICondition *))lpVtbl->Release)(v31);
            (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)hVal.QuadPart + 16LL))(hVal);
          }
          else
          {
            *(_OWORD *)v52 = *(_OWORD *)&v54.vt;
            v9 = (struct ICondition *)_mm_srli_si128(*(__m128i *)&v54.vt, 8).m128i_u64[0];
            LODWORD(v52[0]) = *(_DWORD *)&v54.vt;
          }
        }
        for ( i = 0;
              i < v51[0];
              v26 = (const struct SemanticsUM::ISemanticCondition *)(*(__int64 (__fastcall **)(const struct SemanticsUM::ISemanticCondition *))(*(_QWORD *)v26 + 40LL))(v26) )
        {
          ++i;
        }
        v25 = v58;
        v10 = v59;
        if ( Compound >= 0 )
          continue;
      }
      goto LABEL_11;
    }
  }
  else
  {
    v35 = (__int64 *)(*(__int64 (__fastcall **)(const struct SemanticsUM::ISemanticCondition *))(*(_QWORD *)a2 + 64LL))(a2);
    v36 = v35;
    if ( v35 )
    {
      v40 = *v35;
      v54.vt = 3;
      memset(&v54.decVal.scale, 0, 22);
      v54.lVal = (*(__int64 (__fastcall **)(__int64 *))(v40 + 24))(v35);
      v41 = v36[1];
      *(_QWORD *)v53 = 0;
      v42 = (char *)v36 + *(int *)(v41 + 4) + 8;
      v43 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v42 + 32LL))(v42);
      v44 = *(int *)(v36[1] + 4);
      v45 = (*(__int64 (__fastcall **)(__int64))(*(__int64 *)((char *)v36 + v44 + 8) + 24))((__int64)v36 + v44 + 8);
      Compound = StructuredQuery1::TokenInformation::CreateInstance(v45, v43, this, &v54, lpString2, (void **)v53);
      if ( Compound < 0 )
        goto LABEL_11;
      v46 = *v36;
      memset(&v61, 0, sizeof(v61));
      v47 = (wchar_t *)(*(__int64 (__fastcall **)(__int64 *))(v46 + 16))(v36);
      Compound = StructuredQuery1::GetKeyFromConditionPropertyName(v47, &v61, v48);
      if ( Compound >= 0 )
      {
        v9 = v52[1];
        Compound = StructuredQuery1::Solution::MakePredicate(
                     this,
                     &v61,
                     0,
                     L"System.StructuredQueryType.Value",
                     &cchOriginalDestLength,
                     &cchOriginalDestLength);
      }
      IUnknown_SafeReleaseAndNullPtr<IRichChunk>(v53);
LABEL_3:
      if ( Compound < 0 )
        goto LABEL_11;
      goto LABEL_4;
    }
    Compound = 0;
  }
LABEL_4:
  if ( !v9
    || !*(_QWORD *)(*(__int64 (__fastcall **)(const struct SemanticsUM::ISemanticCondition *))(*(_QWORD *)a2 + 16LL))(a2)
    || (v22 = (PCNZWCH *)(*(__int64 (__fastcall **)(const struct SemanticsUM::ISemanticCondition *))(*(_QWORD *)a2 + 16LL))(a2),
        CompareStringW(0x7Fu, 0, *v22, -1, L"not", -1) != 2)
    || (Compound = StructuredQuery1::Solution::MakeNegation(
                     this,
                     v9,
                     1,
                     &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                     (void **)&v52[1]),
        ((void (__fastcall *)(struct ICondition *))v9->lpVtbl->Release)(v9),
        Compound >= 0) )
  {
    if ( *(_QWORD *)(*(__int64 (__fastcall **)(const struct SemanticsUM::ISemanticCondition *))(*(_QWORD *)a2 + 8LL))(a2) )
    {
      v23 = (PCNZWCH *)(*(__int64 (__fastcall **)(const struct SemanticsUM::ISemanticCondition *))(*(_QWORD *)a2 + 8LL))(a2);
      if ( CompareStringW(0x7Fu, 0, *v23, -1, L"and", -1) == 2 )
      {
        LODWORD(v52[0]) = 0;
      }
      else
      {
        v37 = (PCNZWCH *)(*(__int64 (__fastcall **)(const struct SemanticsUM::ISemanticCondition *))(*(_QWORD *)a2 + 8LL))(a2);
        v38 = CompareStringW(0x7Fu, 0, *v37, -1, L"or", -1);
        v39 = (int)v52[0];
        if ( v38 == 2 )
          v39 = 1;
        LODWORD(v52[0]) = v39;
      }
    }
  }
LABEL_11:
  *(_OWORD *)v60 = *(_OWORD *)v52;
  return (unsigned int)Compound;
}

```

## disassembly

```asm
0x18000ddc8  push    rbp
0x18000ddca  push    rbx
0x18000ddcb  push    rsi
0x18000ddcc  push    rdi
0x18000ddcd  push    r12
0x18000ddcf  push    r13
0x18000ddd1  push    r14
0x18000ddd3  push    r15
0x18000ddd5  lea     rbp, [rsp-18h]
0x18000ddda  sub     rsp, 118h
0x18000dde1  mov     rax, cs:__security_cookie
0x18000dde8  xor     rax, rsp
0x18000ddeb  mov     [rbp+50h+var_48], rax
0x18000ddef  mov     rax, [rbp+50h+arg_28]
0x18000ddf6  mov     r13, rcx
0x18000ddf9  mov     rdi, [rbp+50h+arg_30]
0x18000de00  xor     r14d, r14d
0x18000de03  mov     [rbp+50h+var_80], rax
0x18000de07  mov     r12, r9
0x18000de0a  mov     rax, [rbp+50h+arg_38]
0x18000de11  mov     rbx, r8
0x18000de14  mov     [rbp+50h+var_68], rax
0x18000de18  mov     rsi, rdx
0x18000de1b  mov     rax, [rcx+20h]
0x18000de1f  mov     [rbp+50h+var_70], r9
0x18000de23  mov     [rbp+50h+var_D0+8], r14
0x18000de27  mov     ecx, [rax+40h]
0x18000de2a  xor     eax, eax
0x18000de2c  mov     dword ptr [rbp+50h+var_D0+4], eax
0x18000de2f  mov     dword ptr [rdi], 1
0x18000de35  mov     rax, [rdx]
0x18000de38  mov     dword ptr [rbp+50h+var_D0], ecx
0x18000de3b  mov     rcx, rdx
0x18000de3e  mov     rax, [rax+48h]
0x18000de42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de47  mov     r15, rax
0x18000de4a  test    rax, rax
0x18000de4d  jz      loc_18000DFA6
0x18000de53  mov     rcx, [rbx+8]
0x18000de57  movsxd  r8, dword ptr [rcx+4]
0x18000de5b  mov     rcx, [r8+rbx+8]
0x18000de60  mov     rax, [rcx+40h]
0x18000de64  lea     rcx, [rbx+8]
0x18000de68  add     rcx, r8
0x18000de6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de70  lea     rcx, [rbp+50h+var_D0+8]
0x18000de74  mov     r8, rax; struct SemanticsUM::IEntityCondition *
0x18000de77  mov     [rsp+150h+var_118], rcx; struct ICondition2 **
0x18000de7c  mov     rdx, r15; struct SemanticsUM::IValueCondition *
0x18000de7f  mov     rcx, r13; this
0x18000de82  mov     [rsp+150h+var_120], rdi; int *
0x18000de87  call    ?TranslateValueCondition@Solution@StructuredQuery1@@AEAAJPEBVIValueCondition@SemanticsUM@@PEBVIEntityCondition@4@PEB_W_KAEBVTokenCollectionUM@4@AEAHPEAPEAUICondition2@@@Z; StructuredQuery1::Solution::TranslateValueCondition(SemanticsUM::IValueCondition const *,SemanticsUM::IEntityCondition const *,wchar_t const *,unsigned __int64,SemanticsUM::TokenCollectionUM const &,int &,ICondition2 * *)
0x18000de8c  mov     r14, [rbp+50h+var_D0+8]
0x18000de90  mov     edi, eax
0x18000de92  xor     r12d, r12d
0x18000de95  test    edi, edi
0x18000de97  js      loc_18000DF78
0x18000de9d  or      ebx, 0FFFFFFFFh
0x18000dea0  mov     r15d, 7Fh
0x18000dea6  test    r14, r14
0x18000dea9  jz      short loc_18000DF27
0x18000deab  mov     rax, [rsi]
0x18000deae  mov     rcx, rsi
0x18000deb1  mov     rax, [rax+10h]
0x18000deb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000deba  cmp     [rax], r12
0x18000debd  jz      short loc_18000DF27
0x18000debf  mov     rax, [rsi]
0x18000dec2  mov     rcx, rsi
0x18000dec5  mov     rax, [rax+10h]
0x18000dec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dece  lea     rcx, aNot_0; "not"
0x18000ded5  mov     [rsp+150h+cchCount2], ebx; cchCount2
0x18000ded9  mov     [rsp+150h+lpString2], rcx; lpString2
0x18000dede  mov     r9d, ebx; cchCount1
0x18000dee1  mov     ecx, r15d; Locale
0x18000dee4  xor     edx, edx; dwCmpFlags
0x18000dee6  mov     r8, [rax]; lpString1
0x18000dee9  call    cs:__imp_CompareStringW
0x18000deef  cmp     eax, 2
0x18000def2  jnz     short loc_18000DF27
0x18000def4  lea     rax, [rbp+50h+var_D0+8]
0x18000def8  mov     r8b, 1; bool
0x18000defb  lea     r9, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7; struct _GUID *
0x18000df02  mov     [rsp+150h+lpString2], rax; void **
0x18000df07  mov     rdx, r14; struct ICondition *
0x18000df0a  mov     rcx, r13; this
0x18000df0d  call    ?MakeNegation@Solution@StructuredQuery1@@QEAAJPEAUICondition@@_NAEBU_GUID@@PEAPEAX@Z; StructuredQuery1::Solution::MakeNegation(ICondition *,bool,_GUID const &,void * *)
0x18000df12  mov     edi, eax
0x18000df14  mov     rcx, r14
0x18000df17  mov     rax, [r14]
0x18000df1a  mov     rax, [rax+10h]
0x18000df1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df23  test    edi, edi
0x18000df25  js      short loc_18000DF78
0x18000df27  mov     rax, [rsi]
0x18000df2a  mov     rcx, rsi
0x18000df2d  mov     rax, [rax+8]
0x18000df31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df36  cmp     [rax], r12
0x18000df39  jz      short loc_18000DF78
0x18000df3b  mov     rax, [rsi]
0x18000df3e  mov     rcx, rsi
0x18000df41  mov     rax, [rax+8]
0x18000df45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df4a  lea     rcx, aAnd_1; "and"
0x18000df51  mov     [rsp+150h+cchCount2], ebx; cchCount2
0x18000df55  mov     [rsp+150h+lpString2], rcx; lpString2
0x18000df5a  mov     r9d, ebx; cchCount1
0x18000df5d  mov     ecx, r15d; Locale
0x18000df60  xor     edx, edx; dwCmpFlags
0x18000df62  mov     r8, [rax]; lpString1
0x18000df65  call    cs:__imp_CompareStringW
0x18000df6b  cmp     eax, 2
0x18000df6e  jnz     loc_18000E16A
0x18000df74  mov     dword ptr [rbp+50h+var_D0], r12d
0x18000df78  mov     rax, [rbp+50h+var_68]
0x18000df7c  movaps  xmm0, xmmword ptr [rbp+50h+var_D0]
0x18000df80  movdqu  xmmword ptr [rax], xmm0
0x18000df84  mov     eax, edi
0x18000df86  mov     rcx, [rbp+50h+var_48]
0x18000df8a  xor     rcx, rsp; StackCookie
0x18000df8d  call    __security_check_cookie
0x18000df92  add     rsp, 118h
0x18000df99  pop     r15
0x18000df9b  pop     r14
0x18000df9d  pop     r13
0x18000df9f  pop     r12
0x18000dfa1  pop     rdi
0x18000dfa2  pop     rsi
0x18000dfa3  pop     rbx
0x18000dfa4  pop     rbp
0x18000dfa5  retn
0x18000dfa6  mov     rax, [rsi]
0x18000dfa9  mov     rcx, rsi
0x18000dfac  mov     rax, [rax+38h]
0x18000dfb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfb5  mov     rbx, rax
0x18000dfb8  mov     [rbp+50h+var_78], rax
0x18000dfbc  mov     rcx, [rax]
0x18000dfbf  mov     rax, [rcx]
0x18000dfc2  mov     rcx, rbx
0x18000dfc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfca  mov     r15, rax
0x18000dfcd  test    rax, rax
0x18000dfd0  jz      loc_18000E148
0x18000dfd6  xor     edi, edi
0x18000dfd8  test    r15, r15
0x18000dfdb  jz      loc_18000E093
0x18000dfe1  lea     rax, [rbp+50h+var_B0]
0x18000dfe5  mov     [rsp+150h+var_E0], 0
0x18000dfed  mov     [rsp+150h+var_118], rax; struct StructuredQuery1::ConnectedQuery *
0x18000dff2  xorps   xmm0, xmm0
0x18000dff5  lea     rax, [rsp+150h+var_E0]
0x18000dffa  mov     r9, r12; wchar_t *
0x18000dffd  mov     [rsp+150h+var_120], rax; int *
0x18000e002  mov     r8, rbx; struct SemanticsUM::ICompoundCondition *
0x18000e005  mov     rax, [rbp+50h+var_80]
0x18000e009  mov     rdx, r15; struct SemanticsUM::ISemanticCondition *
0x18000e00c  mov     qword ptr [rsp+150h+cchCount2], rax; struct SemanticsUM::TokenCollectionUM *
0x18000e011  mov     rcx, r13; this
0x18000e014  mov     rax, [rbp+50h+arg_20]
0x18000e01b  mov     [rsp+150h+lpString2], rax; struct _GUID *
0x18000e020  movups  xmmword ptr [rbp+50h+var_B0], xmm0
0x18000e024  call    ?TranslateSemanticCondition@Solution@StructuredQuery1@@AEAAJPEBVISemanticCondition@SemanticsUM@@PEBVICompoundCondition@4@PEB_W_KAEBVTokenCollectionUM@4@AEAHPEAUConnectedQuery@2@@Z; StructuredQuery1::Solution::TranslateSemanticCondition(SemanticsUM::ISemanticCondition const *,SemanticsUM::ICompoundCondition const *,wchar_t const *,unsigned __int64,SemanticsUM::TokenCollectionUM const &,int &,StructuredQuery1::ConnectedQuery *)
0x18000e029  mov     edi, eax
0x18000e02b  test    eax, eax
0x18000e02d  js      loc_18000DF78
0x18000e033  mov     r12, qword ptr [rbp+50h+var_B0+8]
0x18000e037  test    r12, r12
0x18000e03a  jz      short loc_18000E05C
0x18000e03c  test    r14, r14
0x18000e03f  jnz     short loc_18000E09B
0x18000e041  movaps  xmm1, xmmword ptr [rbp+50h+var_B0]
0x18000e045  movdqa  xmm0, xmm1
0x18000e049  movaps  xmmword ptr [rbp+50h+var_D0], xmm1
0x18000e04d  psrldq  xmm0, 8
0x18000e052  movq    r14, xmm0
0x18000e057  movss   dword ptr [rbp+50h+var_D0], xmm1
0x18000e05c  xor     ebx, ebx
0x18000e05e  cmp     [rsp+150h+var_E0], ebx
0x18000e062  jle     short loc_18000E07E
0x18000e064  mov     rax, [r15]
0x18000e067  mov     rcx, r15
0x18000e06a  mov     rax, [rax+28h]
0x18000e06e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e073  inc     ebx
0x18000e075  mov     r15, rax
0x18000e078  cmp     ebx, [rsp+150h+var_E0]
0x18000e07c  jl      short loc_18000E064
0x18000e07e  mov     rbx, [rbp+50h+var_78]
0x18000e082  mov     r12, [rbp+50h+var_70]
0x18000e086  test    edi, edi
0x18000e088  jns     loc_18000DFD8
0x18000e08e  jmp     loc_18000DF78
0x18000e093  xor     r12d, r12d
0x18000e096  jmp     loc_18000DE9D
0x18000e09b  mov     rax, [r13+20h]
0x18000e09f  lea     r9, [rbp+50h+var_90]
0x18000e0a3  mov     rbx, r14
0x18000e0a6  mov     qword ptr [rbp+50h+var_60+8], r12
0x18000e0aa  xor     r14d, r14d
0x18000e0ad  mov     qword ptr [rbp+50h+var_60], rbx
0x18000e0b1  lea     rdx, [rbp+50h+var_60]
0x18000e0b5  mov     [rbp+50h+var_88], r14
0x18000e0b9  mov     ecx, [rax+40h]
0x18000e0bc  mov     eax, dword ptr [rbp+50h+var_B0]
0x18000e0bf  mov     dword ptr [rbp+50h+var_D0], ecx
0x18000e0c2  lea     ecx, [r14+2]
0x18000e0c6  mov     [rbp+50h+var_C0], eax
0x18000e0c9  mov     [rbp+50h+var_90], r14
0x18000e0cd  call    ??$CreateInstance@UICondition@@@FixedCapacityObjectCollection@@SAJIPEAPEAUICondition@@AEBU_GUID@@PEAPEAX@Z; FixedCapacityObjectCollection::CreateInstance<ICondition>(uint,ICondition * *,_GUID const &,void * *)
0x18000e0d2  mov     edi, eax
0x18000e0d4  test    eax, eax
0x18000e0d6  js      short loc_18000E120
0x18000e0d8  mov     rbx, [rbp+50h+var_90]
0x18000e0dc  lea     rax, [rbp+50h+var_88]
0x18000e0e0  mov     edx, [rbp+50h+var_C0]; enum tagCONDITION_TYPE
0x18000e0e3  mov     r8, rbx; struct IObjectArray *
0x18000e0e6  mov     [rsp+150h+var_120], rax; void **
0x18000e0eb  lea     rax, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x18000e0f2  mov     qword ptr [rsp+150h+cchCount2], rax; struct _GUID *
0x18000e0f7  lea     eax, [r14+1]
0x18000e0fb  mov     r9b, al; bool
0x18000e0fe  mov     byte ptr [rsp+150h+lpString2], al; bool
0x18000e102  call    ?MakeCompound@Solution@StructuredQuery1@@QEAAJW4tagCONDITION_TYPE@@PEAUIObjectArray@@_N2AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::Solution::MakeCompound(tagCONDITION_TYPE,IObjectArray *,bool,bool,_GUID const &,void * *)
0x18000e107  mov     edi, eax
0x18000e109  mov     rcx, rbx
0x18000e10c  mov     rax, [rbx]
0x18000e10f  mov     rax, [rax+10h]
0x18000e113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e118  mov     r14, [rbp+50h+var_88]
0x18000e11c  mov     rbx, qword ptr [rbp+50h+var_60]
0x18000e120  mov     rax, [rbx]
0x18000e123  mov     rcx, rbx
0x18000e126  mov     [rbp+50h+var_D0+8], r14
0x18000e12a  mov     rax, [rax+10h]
0x18000e12e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e133  mov     rax, [r12]
0x18000e137  mov     rcx, r12
0x18000e13a  mov     rax, [rax+10h]
0x18000e13e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e143  jmp     loc_18000E05C
0x18000e148  mov     rax, [rsi]
0x18000e14b  mov     rcx, rsi
0x18000e14e  mov     rax, [rax+40h]
0x18000e152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e157  xor     r12d, r12d
0x18000e15a  mov     r15, rax
0x18000e15d  test    rax, rax
0x18000e160  jnz     short loc_18000E1B0
0x18000e162  mov     edi, r12d
0x18000e165  jmp     loc_18000DE9D
0x18000e16a  mov     rax, [rsi]
0x18000e16d  mov     rcx, rsi
0x18000e170  mov     rax, [rax+8]
0x18000e174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e179  lea     rdx, aOr; "or"
0x18000e180  mov     [rsp+150h+cchCount2], ebx; cchCount2
0x18000e184  mov     [rsp+150h+lpString2], rdx; lpString2
0x18000e189  mov     r9d, ebx; cchCount1
0x18000e18c  xor     edx, edx; dwCmpFlags
0x18000e18e  mov     ecx, r15d; Locale
0x18000e191  mov     r8, [rax]; lpString1
0x18000e194  call    cs:__imp_CompareStringW
0x18000e19a  mov     ecx, dword ptr [rbp+50h+var_D0]
0x18000e19d  cmp     eax, 2
0x18000e1a0  mov     eax, 1
0x18000e1a5  cmovz   ecx, eax
0x18000e1a8  mov     dword ptr [rbp+50h+var_D0], ecx
0x18000e1ab  jmp     loc_18000DF78
0x18000e1b0  mov     rcx, [r15]
0x18000e1b3  mov     eax, 3
0x18000e1b8  mov     word ptr [rbp+50h+var_B0], ax
0x18000e1bc  xorps   xmm0, xmm0
0x18000e1bf  xor     eax, eax
0x18000e1c1  movups  xmmword ptr [rbp+50h+var_B0+2], xmm0
0x18000e1c5  mov     qword ptr [rbp+50h+var_B0+10h], rax
0x18000e1c9  mov     rax, [rcx+18h]
0x18000e1cd  mov     rcx, r15
0x18000e1d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1d5  mov     dword ptr [rbp+50h+var_B0+8], eax
0x18000e1d8  mov     rax, [r15+8]
0x18000e1dc  mov     qword ptr [rbp+50h+var_C0], r12
0x18000e1e0  movsxd  rcx, dword ptr [rax+4]
0x18000e1e4  add     rcx, 8
0x18000e1e8  add     rcx, r15
0x18000e1eb  mov     rax, [rcx]
0x18000e1ee  mov     rax, [rax+20h]
0x18000e1f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1f7  mov     rcx, [r15+8]
0x18000e1fb  mov     ebx, eax
0x18000e1fd  movsxd  r8, dword ptr [rcx+4]
0x18000e201  mov     rcx, [r8+r15+8]
0x18000e206  mov     rax, [rcx+18h]
0x18000e20a  lea     rcx, [r8+8]
0x18000e20e  add     rcx, r15
0x18000e211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e216  lea     rcx, [rbp+50h+var_C0]
0x18000e21a  mov     r8, r13; struct StructuredQuery1::Solution *
  ... truncated ...
```
