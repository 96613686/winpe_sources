# StructuredQuery1::SqlGenerator::PrepareSqlLeaf(ICondition2 *,SQL_GENERATION_OPTIONS,bool,StructuredQuery1::VirtualPropertyMap *,IConditionFactory2 *,ICondition2 * *)

- ea: `0x180030e78`
- end: `0x1800313e9`
- name: `?PrepareSqlLeaf@SqlGenerator@StructuredQuery1@@AEAAJPEAUICondition2@@W4SQL_GENERATION_OPTIONS@@_NPEAVVirtualPropertyMap@2@PEAUIConditionFactory2@@PEAPEAU3@@Z`
- size: `1393`
- prototype: `int __high(struct ICondition2 *, enum SQL_GENERATION_OPTIONS, bool, struct StructuredQuery1::VirtualPropertyMap *, struct IConditionFactory2 *, struct ICondition2 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800326e0`

## callees

- `0x180030e78`
- `0x1800313f0`
- `0x180031580`
- `0x1800326e0`
- `0x18004146c`
- `0x18005c6a0`
- `0x18005daf0`
- `0x18005f7fd`
- `0x18007ad70`
- `0x18007d790`
- `0x18008479c`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003105a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180089a97`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180089abe`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003105a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180089a97`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180089abe`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180031206`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180031206`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031191`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003119b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031191`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003119b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180031187`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800311a5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003133e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180031187`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800311a5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003133e`
- `PROPSYS!PropVariantChangeType` at `0x1800310a8`
- `PROPSYS!PropVariantChangeType` at `0x1800310a8`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::SqlGenerator::PrepareSqlLeaf(
        void *a1,
        __int64 *a2,
        __int64 a3,
        char a4,
        __int64 a5,
        struct ICondition2 *a6,
        _QWORD *a7)
{
  LPVOID v7; // r14
  char v8; // si
  unsigned int v9; // r12d
  int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // r14
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // r9
  int v18; // ebx
  __int64 v19; // rdx
  __int64 v20; // r8
  int v21; // eax
  const struct tagPROPVARIANT *v22; // rdx
  int v23; // ebx
  __int16 Data1; // r8
  _WORD *v25; // rdx
  unsigned int v26; // ebx
  PCNZWCH v27; // rdx
  int TrueFalseCondition; // eax
  __int64 v30; // rdx
  HRESULT SortKeyDescriptionExpression; // eax
  __int64 v32; // rax
  bool v33; // zf
  unsigned __int64 v34; // rcx
  __int16 v35; // r8
  StructuredQuery1::SqlGenerator *v36; // rcx
  const struct _tagpropertykey *v37; // r8
  const struct _tagpropertykey *v38; // rdx
  __int64 v39; // r9
  BOOL v40; // eax
  bool v41; // dl
  bool v42; // dl
  struct IConditionFactory2 *cchCount2; // [rsp+28h] [rbp-D8h]
  void **v44; // [rsp+38h] [rbp-C8h]
  char v45[4]; // [rsp+70h] [rbp-90h] BYREF
  struct _tagpropertykey v46; // [rsp+74h] [rbp-8Ch] BYREF
  PCNZWCH lpString1; // [rsp+88h] [rbp-78h] BYREF
  LPVOID pv; // [rsp+90h] [rbp-70h] BYREF
  __int64 v49; // [rsp+98h] [rbp-68h] BYREF
  struct _GUID v50; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v51; // [rsp+B0h] [rbp-50h]
  PROPVARIANT propvarSrc[2]; // [rsp+B8h] [rbp-48h] BYREF
  struct SORTKEY_DESCRIPTION *v53; // [rsp+C8h] [rbp-38h]
  _QWORD *v54; // [rsp+D0h] [rbp-30h]
  struct _tagpropertykey v55; // [rsp+D8h] [rbp-28h] BYREF
  __int128 Buf1; // [rsp+F0h] [rbp-10h] BYREF
  int v57; // [rsp+100h] [rbp+0h]

  v7 = a1;
  v8 = 1;
  pv = a1;
  v9 = a3;
  v54 = a7;
  LOBYTE(v46.fmtid.Data1) = a4;
  *(_QWORD *)&v46.fmtid.Data4[4] = 0;
  v49 = 0;
  v45[0] = 1;
  if ( a4 )
  {
    v11 = StructuredQuery1::SqlGenerator::ApplyTransformation(a1, a2, a3, &v49, v45);
    if ( v11 < 0 )
      goto LABEL_42;
    v13 = v49;
    if ( v49 )
    {
      LOBYTE(v12) = v45[0];
      v11 = StructuredQuery1::SqlGenerator::PrepareSql(pv, v49, v9, v12, a5, a6, &v46.fmtid.Data4[4]);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      goto LABEL_42;
    }
    v7 = pv;
  }
  v57 = 0;
  *(_DWORD *)&v46.fmtid.Data2 = 0;
  v53 = 0;
  v14 = *a2;
  Buf1 = 0;
  *(_OWORD *)propvarSrc = 0;
  v11 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, unsigned __int16 *, PROPVARIANT *))(v14 + 128))(
          a2,
          &Buf1,
          &v46.fmtid.Data2,
          propvarSrc);
  if ( v11 >= 0 )
  {
    v15 = *a2;
    lpString1 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64 *, PCNZWCH *))(v15 + 88))(a2, &lpString1);
    if ( v11 < 0 )
    {
LABEL_41:
      PropVariantClear(propvarSrc);
      goto LABEL_42;
    }
    v16 = *a2;
    pv = 0;
    v11 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v16 + 120))(a2, &pv);
    if ( v11 < 0 )
    {
LABEL_40:
      CoTaskMemFree((LPVOID)lpString1);
      goto LABEL_41;
    }
    if ( (v9 & 0x40) != 0 || (unsigned int)(*(_DWORD *)&v46.fmtid.Data2 - 12) > 1 )
    {
      v18 = v57;
      if ( v57 == 100 && !memcmp_0(&Buf1, &PKEY_MOST_RELEVANT_PROPERTIES, 0x10u) )
      {
        v19 = a5 + 40;
LABEL_15:
        if ( v19 )
        {
          v37 = (const struct _tagpropertykey *)*(unsigned int *)(v19 + 32);
          v38 = *(const struct _tagpropertykey **)(v19 + 24);
          v49 = 0;
          v11 = StructuredQuery1::ExpandVirtualProperty(
                  (StructuredQuery1 *)&Buf1,
                  v38,
                  v37,
                  (unsigned int)a2,
                  a6,
                  cchCount2,
                  (const struct _GUID *)&v49,
                  v44);
          if ( v11 >= 0 )
          {
            LOBYTE(v39) = v46.fmtid.Data1;
            v11 = StructuredQuery1::SqlGenerator::PrepareSql(v7, v49, v9, v39, a5, a6, &v46.fmtid.Data4[4]);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
          }
          goto LABEL_39;
        }
      }
      else
      {
        v19 = 0;
        v20 = 0;
        while ( (unsigned int)v20 < *(_DWORD *)(a5 + 24) )
        {
          v17 = *(_QWORD *)(a5 + 16) + 40 * v20;
          if ( *(_DWORD *)(v17 + 16) == v18 )
          {
            v32 = *(_QWORD *)v17 - Buf1;
            if ( *(_QWORD *)v17 == (_QWORD)Buf1 )
              v32 = *(_QWORD *)(v17 + 8) - *((_QWORD *)&Buf1 + 1);
            if ( !v32 )
              v19 = *(_QWORD *)(a5 + 16) + 40 * v20;
          }
          v20 = (unsigned int)(v20 + 1);
          if ( v19 )
            goto LABEL_15;
        }
      }
    }
    LOWORD(v46.fmtid.Data1) = 0;
    memset(&v55, 0, sizeof(v55));
    v11 = StructuredQuery1::PrepareProperty((StructuredQuery1 *)&Buf1, &v55, &v46, (unsigned __int16 *)v17);
    if ( v11 < 0 )
    {
LABEL_39:
      CoTaskMemFree(pv);
      goto LABEL_40;
    }
    if ( v55.pid == 6 && !memcmp_0(&v55, &PKEY_FullText, 0x10u) && (v9 & 2) != 0 )
      *(_DWORD *)(a5 + 80) = 1;
    v21 = CompareStringW(0x7Fu, 0, lpString1, -1, L"System.StructuredQueryType.SortKeyDescription", -1);
    v50 = 0;
    v51 = 0;
    if ( LOWORD(propvarSrc[0]) == 65 )
    {
      if ( v21 != 2 )
        goto LABEL_21;
      if ( LODWORD(propvarSrc[1]) == 12 && v53 )
      {
        LOWORD(v50.Data1) = 31;
        SortKeyDescriptionExpression = GetSortKeyDescriptionExpression(v53, (unsigned __int16 **)v50.Data4);
      }
      else
      {
        SortKeyDescriptionExpression = -2147467259;
      }
    }
    else
    {
      if ( LOWORD(propvarSrc[0]) >= 2u && v21 != 2 )
      {
LABEL_21:
        v23 = *(_DWORD *)&v46.fmtid.Data2;
        if ( PropVariantChangeType((PROPVARIANT *)&v50, propvarSrc, 0, v46.fmtid.Data1) >= 0 )
        {
          if ( (unsigned int)(v23 - 1) <= 1 )
          {
            Data1 = v50.Data1;
            v25 = *(_WORD **)v50.Data4;
            if ( (LOWORD(v50.Data1) != 31 || **(_WORD **)v50.Data4) && (LOWORD(v50.Data1) != 8 || **(_WORD **)v50.Data4) )
            {
LABEL_26:
              v26 = *(_DWORD *)&v46.fmtid.Data2;
              if ( *(int *)&v46.fmtid.Data2 > 7 )
              {
                if ( *(_DWORD *)&v46.fmtid.Data2 != 8
                  && *(_DWORD *)&v46.fmtid.Data2 != 9
                  && *(_DWORD *)&v46.fmtid.Data2 != 10
                  && *(_DWORD *)&v46.fmtid.Data2 != 11 )
                {
                  v34 = (unsigned int)(*(_DWORD *)&v46.fmtid.Data2 - 12);
                  if ( *(_DWORD *)&v46.fmtid.Data2 == 12
                    || (v34 = (unsigned int)(*(_DWORD *)&v46.fmtid.Data2 - 13), *(_DWORD *)&v46.fmtid.Data2 == 13) )
                  {
                    if ( Data1 != 31 )
                    {
LABEL_100:
                      v41 = 0;
                      goto LABEL_101;
                    }
                    if ( !*v25 )
                    {
                      v41 = 1;
LABEL_101:
                      TrueFalseCondition = StructuredQuery1::SqlGenerator::MakeTrueFalseCondition(
                                             (StructuredQuery1::SqlGenerator *)v34,
                                             v41,
                                             (struct IConditionFactory2 *)a6,
                                             (struct ICondition2 **)&v46.fmtid.Data4[4]);
                      goto LABEL_37;
                    }
                  }
                  else
                  {
                    if ( *(_DWORD *)&v46.fmtid.Data2 != 14 )
                      goto LABEL_96;
                    v40 = operator==((__int64)&v55, (__int64)&PKEY_FullText);
                    v27 = lpString1;
                    if ( !v40 || !lpString1 )
                      goto LABEL_36;
                    if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"System.StructuredQueryType.AnyBitsSet", -1) == 2
                      || CompareStringW(0x7Fu, 1u, lpString1, -1, L"System.StructuredQueryType.AllBitsSet", -1) == 2 )
                    {
                      goto LABEL_100;
                    }
                    v26 = *(_DWORD *)&v46.fmtid.Data2;
                  }
LABEL_35:
                  v27 = lpString1;
LABEL_36:
                  TrueFalseCondition = ((__int64 (__fastcall *)(struct ICondition2 *, struct _tagpropertykey *, _QWORD, struct _GUID *, PCNZWCH, LPVOID, _QWORD, _QWORD, _QWORD, int, GUID *, unsigned __int8 *))a6->lpVtbl->Clone)(
                                         a6,
                                         &v55,
                                         v26,
                                         &v50,
                                         v27,
                                         pv,
                                         0,
                                         0,
                                         0,
                                         1,
                                         &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                                         &v46.fmtid.Data4[4]);
LABEL_37:
                  v11 = TrueFalseCondition;
LABEL_38:
                  PropVariantClear((PROPVARIANT *)&v50);
                  goto LABEL_39;
                }
              }
              else if ( *(_DWORD *)&v46.fmtid.Data2 != 7 )
              {
                switch ( *(_DWORD *)&v46.fmtid.Data2 )
                {
                  case 0:
                    v30 = 1;
LABEL_44:
                    TrueFalseCondition = ((__int64 (__fastcall *)(struct ICondition2 *, __int64, _QWORD, GUID *, unsigned __int8 *))a6->lpVtbl->GetSizeMax)(
                                           a6,
                                           v30,
                                           0,
                                           &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                                           &v46.fmtid.Data4[4]);
                    goto LABEL_37;
                  case 1:
                    goto LABEL_34;
                  case 2:
                    if ( Data1 == 11 )
                    {
                      v33 = *(_WORD *)v50.Data4 == 0;
                      v26 = 1;
                      *(_DWORD *)&v46.fmtid.Data2 = 1;
                      *(_WORD *)v50.Data4 = -1;
                      if ( !v33 )
                        *(_WORD *)v50.Data4 = 0;
                    }
LABEL_34:
                    if ( v55.pid == 6 && !memcmp_0(&v55, &PKEY_FullText, 0x10u) )
                    {
                      v30 = 0;
                      goto LABEL_44;
                    }
                    goto LABEL_35;
                }
                if ( *(_DWORD *)&v46.fmtid.Data2 == 3
                  || *(_DWORD *)&v46.fmtid.Data2 == 4
                  || (unsigned int)(*(_DWORD *)&v46.fmtid.Data2 - 5) <= 1 )
                {
                  goto LABEL_34;
                }
LABEL_96:
                v11 = -2147024809;
                goto LABEL_38;
              }
              if ( operator==((__int64)&v55, (__int64)&PKEY_FullText) || v35 != 31 )
                goto LABEL_100;
              goto LABEL_35;
            }
            PropVariantClear((PROPVARIANT *)&v50);
            Data1 = 1;
            LOWORD(v50.Data1) = 1;
LABEL_48:
            v25 = *(_WORD **)v50.Data4;
            goto LABEL_26;
          }
LABEL_47:
          Data1 = v50.Data1;
          goto LABEL_48;
        }
LABEL_75:
        if ( (LOWORD(v46.fmtid.Data1) == 17
           || LOWORD(v46.fmtid.Data1) == 18
           || LOWORD(v46.fmtid.Data1) == 19
           || (v36 = (StructuredQuery1::SqlGenerator *)((unsigned int)LOWORD(v46.fmtid.Data1) - 21),
               LOWORD(v46.fmtid.Data1) == 21)
           || LOWORD(v46.fmtid.Data1) == 23)
          && StructuredQuery1::IsNegativeValue((StructuredQuery1 *)propvarSrc, v22) )
        {
          v36 = (StructuredQuery1::SqlGenerator *)*(unsigned int *)&v46.fmtid.Data2;
          if ( ((*(_DWORD *)&v46.fmtid.Data2 - 2) & 0xFFFFFFF9) != 0 || *(_DWORD *)&v46.fmtid.Data2 == 8 )
            v8 = 0;
          v42 = v8;
        }
        else
        {
          v42 = 0;
        }
        v11 = StructuredQuery1::SqlGenerator::MakeTrueFalseCondition(
                v36,
                v42,
                (struct IConditionFactory2 *)a6,
                (struct ICondition2 **)&v46.fmtid.Data4[4]);
        goto LABEL_39;
      }
      SortKeyDescriptionExpression = PropVariantCopy((PROPVARIANT *)&v50, propvarSrc);
    }
    if ( SortKeyDescriptionExpression >= 0 )
      goto LABEL_47;
    goto LABEL_75;
  }
LABEL_42:
  *v54 = *(_QWORD *)&v46.fmtid.Data4[4];
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180030e78  push    rbp
0x180030e7a  push    rbx
0x180030e7b  push    rsi
0x180030e7c  push    rdi
0x180030e7d  push    r12
0x180030e7f  push    r13
0x180030e81  push    r14
0x180030e83  push    r15
0x180030e85  lea     rbp, [rsp-18h]
0x180030e8a  sub     rsp, 118h
0x180030e91  mov     rax, cs:__security_cookie
0x180030e98  xor     rax, rsp
0x180030e9b  mov     [rbp+50h+var_48], rax
0x180030e9f  mov     r13, [rbp+50h+arg_20]
0x180030ea6  mov     r14, rcx
0x180030ea9  mov     rdi, [rbp+50h+arg_28]
0x180030eb0  mov     esi, 1
0x180030eb5  mov     [rbp+50h+pv], rcx
0x180030eb9  mov     r12d, r8d
0x180030ebc  mov     rcx, [rbp+50h+arg_30]
0x180030ec3  mov     r15, rdx
0x180030ec6  mov     [rbp+50h+var_80], rcx
0x180030eca  mov     byte ptr [rsp+150h+var_DC.fmtid.Data1], r9b
0x180030ecf  mov     qword ptr [rbp+50h+var_DC.fmtid.Data4+4], 0
0x180030ed7  mov     qword ptr [rbp+50h+var_B8.Data1], 0
0x180030edf  mov     [rsp+150h+var_E0], sil
0x180030ee4  test    r9b, r9b
0x180030ee7  jz      short loc_180030F1A
0x180030ee9  lea     rax, [rsp+150h+var_E0]
0x180030eee  mov     rcx, r14
0x180030ef1  lea     r9, [rbp+50h+var_B8]
0x180030ef5  mov     [rsp+150h+lpString2], rax
0x180030efa  call    ?ApplyTransformation@SqlGenerator@StructuredQuery1@@AEAAJPEAUICondition2@@W4SQL_GENERATION_OPTIONS@@PEAPEAU3@PEA_N@Z; StructuredQuery1::SqlGenerator::ApplyTransformation(ICondition2 *,SQL_GENERATION_OPTIONS,ICondition2 * *,bool *)
0x180030eff  mov     ebx, eax
0x180030f01  test    eax, eax
0x180030f03  js      loc_1800311AB
0x180030f09  mov     r14, qword ptr [rbp+50h+var_B8.Data1]
0x180030f0d  test    r14, r14
0x180030f10  jnz     loc_180031245
0x180030f16  mov     r14, [rbp+50h+pv]
0x180030f1a  xor     eax, eax
0x180030f1c  lea     r9, [rbp+50h+propvarSrc]
0x180030f20  mov     [rbp+50h+var_50], eax
0x180030f23  lea     r8, [rsp+150h+var_DC.fmtid.Data2]
0x180030f28  mov     dword ptr [rsp+150h+var_DC.fmtid.Data2], eax
0x180030f2c  lea     rdx, [rbp+50h+Buf1]
0x180030f30  mov     [rbp+50h+var_88], rax
0x180030f34  xorps   xmm0, xmm0
0x180030f37  mov     rax, [r15]
0x180030f3a  mov     rcx, r15
0x180030f3d  movups  [rbp+50h+Buf1], xmm0
0x180030f41  movups  xmmword ptr [rbp+50h+propvarSrc], xmm0
0x180030f45  mov     rax, [rax+80h]
0x180030f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f51  mov     ebx, eax
0x180030f53  test    eax, eax
0x180030f55  js      loc_1800311AB
0x180030f5b  mov     rax, [r15]
0x180030f5e  lea     rdx, [rbp+50h+lpString1]
0x180030f62  mov     rcx, r15
0x180030f65  mov     [rbp+50h+lpString1], 0
0x180030f6d  mov     rax, [rax+58h]
0x180030f71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f76  mov     ebx, eax
0x180030f78  test    eax, eax
0x180030f7a  js      loc_1800311A1
0x180030f80  mov     rax, [r15]
0x180030f83  lea     rdx, [rbp+50h+pv]
0x180030f87  mov     rcx, r15
0x180030f8a  mov     [rbp+50h+pv], 0
0x180030f92  mov     rax, [rax+78h]
0x180030f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f9b  mov     ebx, eax
0x180030f9d  test    eax, eax
0x180030f9f  js      loc_180031197
0x180030fa5  test    r12b, 40h
0x180030fa9  jnz     short loc_180030FB6
0x180030fab  mov     eax, dword ptr [rsp+150h+var_DC.fmtid.Data2]
0x180030faf  add     eax, 0FFFFFFF4h
0x180030fb2  cmp     eax, esi
0x180030fb4  jbe     short loc_180030FFA
0x180030fb6  mov     ebx, [rbp+50h+var_50]
0x180030fb9  cmp     ebx, 64h ; 'd'
0x180030fbc  jz      loc_180031282
0x180030fc2  xor     edx, edx
0x180030fc4  xor     r8d, r8d
0x180030fc7  cmp     r8d, [r13+18h]
0x180030fcb  jnb     short loc_180030FFA
0x180030fcd  mov     rax, [r13+10h]
0x180030fd1  lea     rcx, [r8+r8*4]
0x180030fd5  lea     r9, [rax+rcx*8]
0x180030fd9  cmp     [r9+10h], ebx
0x180030fdd  jz      loc_180031228
0x180030fe3  add     r8d, esi
0x180030fe6  test    rdx, rdx
0x180030fe9  jz      short loc_180030FC7
0x180030feb  jmp     short loc_180030FF1
0x180030fed  lea     rdx, [r13+28h]
0x180030ff1  test    rdx, rdx
0x180030ff4  jnz     loc_18008999A
0x180030ffa  xorps   xmm0, xmm0
0x180030ffd  lea     r8, [rsp+150h+var_DC]; struct _tagpropertykey *
0x180031002  xor     eax, eax
0x180031004  lea     rdx, [rbp+50h+var_78]; struct _tagpropertykey *
0x180031008  xor     r14d, r14d
0x18003100b  mov     [rbp+50h+var_78.pid], eax
0x18003100e  lea     rcx, [rbp+50h+Buf1]; this
0x180031012  mov     word ptr [rsp+150h+var_DC.fmtid.Data1], r14w
0x180031018  movups  xmmword ptr [rbp+50h+var_78.fmtid.Data1], xmm0
0x18003101c  call    ?PrepareProperty@StructuredQuery1@@YAJAEBU_tagpropertykey@@PEAU2@PEAG@Z; StructuredQuery1::PrepareProperty(_tagpropertykey const &,_tagpropertykey *,ushort *)
0x180031021  mov     ebx, eax
0x180031023  test    eax, eax
0x180031025  js      loc_18003118D
0x18003102b  cmp     [rbp+50h+var_78.pid], 6
0x18003102f  lea     r15d, [r14+2]
0x180031033  jz      loc_1800312A5
0x180031039  mov     r8, [rbp+50h+lpString1]; lpString1
0x18003103d  lea     rax, aSystemStructur_10; "System.StructuredQueryType.SortKeyDescr"...
0x180031044  xor     edx, edx; dwCmpFlags
0x180031046  or      r13d, 0FFFFFFFFh
0x18003104a  mov     [rsp+150h+cchCount2], r13d; cchCount2
0x18003104f  mov     r9d, r13d; cchCount1
0x180031052  mov     [rsp+150h+lpString2], rax; lpString2
0x180031057  lea     ecx, [rdx+7Fh]; Locale
0x18003105a  call    cs:__imp_CompareStringW
0x180031060  xor     ecx, ecx
0x180031062  lea     r12d, [r13+20h]
0x180031066  cmp     word ptr [rbp+50h+propvarSrc], 41h ; 'A'
0x18003106b  xorps   xmm0, xmm0
0x18003106e  movups  xmmword ptr [rbp+50h+var_B8.Data4], xmm0
0x180031072  mov     [rbp+50h+var_A0], rcx
0x180031076  lea     ebx, [rcx+8]
0x180031079  jz      loc_1800312FD
0x18003107f  cmp     word ptr [rbp+50h+propvarSrc], r15w
0x180031084  jb      loc_1800311FE
0x18003108a  cmp     eax, r15d
0x18003108d  jz      loc_1800311FE
0x180031093  movzx   r9d, word ptr [rsp+150h+var_DC.fmtid.Data1]; vt
0x180031099  lea     rdx, [rbp+50h+propvarSrc]; propvarSrc
0x18003109d  mov     ebx, dword ptr [rsp+150h+var_DC.fmtid.Data2]
0x1800310a1  lea     rcx, [rbp+50h+var_B8.Data4]; ppropvarDest
0x1800310a5  xor     r8d, r8d; flags
0x1800310a8  call    cs:__imp_PropVariantChangeType
0x1800310ae  test    eax, eax
0x1800310b0  js      loc_1800313AF
0x1800310b6  lea     eax, [rbx-1]
0x1800310b9  cmp     eax, esi
0x1800310bb  ja      loc_180031214
0x1800310c1  movzx   r8d, word ptr [rbp+50h+var_B8.Data4]
0x1800310c6  mov     rdx, [rbp+50h+var_A8]
0x1800310ca  cmp     r8w, r12w
0x1800310ce  jnz     short loc_1800310DA
0x1800310d0  cmp     [rdx], r14w
0x1800310d4  jz      loc_18003133A
0x1800310da  mov     r9d, 8
0x1800310e0  cmp     r8w, r9w
0x1800310e4  jz      loc_180031330
0x1800310ea  mov     ebx, dword ptr [rsp+150h+var_DC.fmtid.Data2]
0x1800310ee  cmp     ebx, 7
0x1800310f1  jg      loc_180089A17
0x1800310f7  jz      loc_180031388
0x1800310fd  mov     ecx, ebx
0x1800310ff  test    ebx, ebx
0x180031101  jz      loc_1800311D8
0x180031107  sub     ecx, esi
0x180031109  jz      short loc_180031123
0x18003110b  sub     ecx, esi
0x18003110d  jz      loc_18003135D
0x180031113  sub     ecx, esi
0x180031115  jz      short loc_180031123
0x180031117  sub     ecx, esi
0x180031119  jz      short loc_180031123
0x18003111b  sub     ecx, esi
0x18003111d  jnz     loc_180031350
0x180031123  cmp     [rbp+50h+var_78.pid], 6
0x180031127  jz      loc_1800312D5
0x18003112d  mov     rdx, [rbp+50h+lpString1]
0x180031131  mov     rcx, [rbp+50h+pv]
0x180031135  lea     r8, [rbp+50h+var_DC.fmtid.Data4+4]
0x180031139  mov     rax, [rdi]
0x18003113c  lea     r9, [rbp+50h+var_B8.Data4]
0x180031140  mov     [rsp+150h+var_F8], r8
0x180031145  lea     r8, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x18003114c  mov     [rsp+150h+var_100], r8
0x180031151  mov     r8d, ebx
0x180031154  mov     [rsp+150h+var_108], esi
0x180031158  mov     rax, [rax+70h]
0x18003115c  mov     [rsp+150h+var_110], r14
0x180031161  mov     [rsp+150h+var_118], r14
0x180031166  mov     [rsp+150h+var_120], r14
0x18003116b  mov     qword ptr [rsp+150h+cchCount2], rcx
0x180031170  mov     rcx, rdi
0x180031173  mov     [rsp+150h+lpString2], rdx
0x180031178  lea     rdx, [rbp+50h+var_78]
0x18003117c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031181  mov     ebx, eax
0x180031183  lea     rcx, [rbp+50h+var_B8.Data4]; pvar
0x180031187  call    cs:__imp_PropVariantClear
0x18003118d  mov     rcx, [rbp+50h+pv]; pv
0x180031191  call    cs:__imp_CoTaskMemFree
0x180031197  mov     rcx, [rbp+50h+lpString1]; pv
0x18003119b  call    cs:__imp_CoTaskMemFree
0x1800311a1  lea     rcx, [rbp+50h+propvarSrc]; pvar
0x1800311a5  call    cs:__imp_PropVariantClear
0x1800311ab  mov     rax, qword ptr [rbp+50h+var_DC.fmtid.Data4+4]
0x1800311af  mov     rcx, [rbp+50h+var_80]
0x1800311b3  mov     [rcx], rax
0x1800311b6  mov     eax, ebx
0x1800311b8  mov     rcx, [rbp+50h+var_48]
0x1800311bc  xor     rcx, rsp; StackCookie
0x1800311bf  call    __security_check_cookie
0x1800311c4  add     rsp, 118h
0x1800311cb  pop     r15
0x1800311cd  pop     r14
0x1800311cf  pop     r13
0x1800311d1  pop     r12
0x1800311d3  pop     rdi
0x1800311d4  pop     rsi
0x1800311d5  pop     rbx
0x1800311d6  pop     rbp
0x1800311d7  retn
0x1800311d8  xor     r8d, r8d
0x1800311db  mov     edx, esi
0x1800311dd  mov     rax, [rdi]
0x1800311e0  lea     rcx, [rbp+50h+var_DC.fmtid.Data4+4]
0x1800311e4  mov     [rsp+150h+lpString2], rcx
0x1800311e9  lea     r9, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x1800311f0  mov     rcx, rdi
0x1800311f3  mov     rax, [rax+38h]
0x1800311f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800311fc  jmp     short loc_180031181
0x1800311fe  lea     rdx, [rbp+50h+propvarSrc]; pvarSrc
0x180031202  lea     rcx, [rbp+50h+var_B8.Data4]; pvarDest
0x180031206  call    cs:__imp_PropVariantCopy
0x18003120c  test    eax, eax
0x18003120e  js      loc_1800313B4
0x180031214  movzx   r8d, word ptr [rbp+50h+var_B8.Data4]
0x180031219  mov     rdx, [rbp+50h+var_A8]
0x18003121d  mov     r9d, 8
0x180031223  jmp     loc_1800310EA
0x180031228  mov     rax, [r9]
0x18003122b  sub     rax, qword ptr [rbp+50h+Buf1]
0x18003122f  jnz     short loc_180031239
0x180031231  mov     rax, [r9+8]
0x180031235  sub     rax, qword ptr [rbp+50h+Buf1+8]
0x180031239  test    rax, rax
0x18003123c  cmovz   rdx, r9
0x180031240  jmp     loc_180030FE3
0x180031245  mov     r9b, [rsp+150h+var_E0]
0x18003124a  lea     rax, [rbp+50h+var_DC.fmtid.Data4+4]
0x18003124e  mov     rcx, [rbp+50h+pv]
0x180031252  mov     r8d, r12d
0x180031255  mov     [rsp+150h+var_120], rax
0x18003125a  mov     rdx, r14
0x18003125d  mov     qword ptr [rsp+150h+cchCount2], rdi
0x180031262  mov     [rsp+150h+lpString2], r13
0x180031267  call    ?PrepareSql@SqlGenerator@StructuredQuery1@@AEAAJPEAUICondition2@@W4SQL_GENERATION_OPTIONS@@_NPEAVVirtualPropertyMap@2@PEAUIConditionFactory2@@PEAPEAU3@@Z; StructuredQuery1::SqlGenerator::PrepareSql(ICondition2 *,SQL_GENERATION_OPTIONS,bool,StructuredQuery1::VirtualPropertyMap *,IConditionFactory2 *,ICondition2 * *)
0x18003126c  mov     ebx, eax
0x18003126e  mov     rcx, r14
0x180031271  mov     rax, [r14]
0x180031274  mov     rax, [rax+10h]
0x180031278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003127d  jmp     loc_1800311AB
0x180031282  mov     r8d, 10h; Size
0x180031288  lea     rdx, PKEY_MOST_RELEVANT_PROPERTIES; Buf2
0x18003128f  lea     rcx, [rbp+50h+Buf1]; Buf1
0x180031293  call    memcmp_0
0x180031298  test    eax, eax
0x18003129a  jnz     loc_180030FC2
0x1800312a0  jmp     loc_180030FED
0x1800312a5  mov     r8d, 10h; Size
0x1800312ab  lea     rdx, PKEY_FullText; Buf2
0x1800312b2  lea     rcx, [rbp+50h+var_78]; Buf1
0x1800312b6  call    memcmp_0
0x1800312bb  test    eax, eax
0x1800312bd  jnz     loc_180031039
0x1800312c3  test    r15b, r12b
0x1800312c6  jz      loc_180031039
0x1800312cc  mov     [r13+50h], esi
0x1800312d0  jmp     loc_180031039
0x1800312d5  mov     r8d, 10h; Size
0x1800312db  lea     rdx, PKEY_FullText; Buf2
0x1800312e2  lea     rcx, [rbp+50h+var_78]; Buf1
0x1800312e6  call    memcmp_0
0x1800312eb  test    eax, eax
0x1800312ed  jnz     loc_18003112D
0x1800312f3  xor     r8d, r8d
0x1800312f6  xor     edx, edx
0x1800312f8  jmp     loc_1800311DD
0x1800312fd  cmp     eax, r15d
0x180031300  jnz     loc_180031093
0x180031306  cmp     dword ptr [rbp+50h+propvarSrc+8], 0Ch
0x18003130a  jnz     loc_180089A0D
0x180031310  mov     rcx, [rbp+50h+var_88]; struct SORTKEY_DESCRIPTION *
0x180031314  test    rcx, rcx
0x180031317  jz      loc_180089A0D
0x18003131d  lea     rdx, [rbp+50h+var_A8]; unsigned __int16 **
0x180031321  mov     word ptr [rbp+50h+var_B8.Data4], r12w
0x180031326  call    ?GetSortKeyDescriptionExpression@@YAJPEBUSORTKEY_DESCRIPTION@@PEAPEAG@Z; GetSortKeyDescriptionExpression(SORTKEY_DESCRIPTION const *,ushort * *)
0x18003132b  jmp     loc_18003120C
  ... truncated ...
```
