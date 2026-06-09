# StructuredQuery1::Solution::ResolveLeafOneStep(ICondition2 *,STRUCTURED_QUERY_RESOLVE_OPTION,_SYSTEMTIME const *,bool,StructuredQuery1::LANGUAGE_OVERRIDE_CHECK,bool *,StructuredQuery1::LANGUAGE_OVERRIDE_CHECK *,bool *,ICondition2 * *)

- ea: `0x18000ef3c`
- end: `0x18000f5b0`
- name: `?ResolveLeafOneStep@Solution@StructuredQuery1@@AEAAJPEAUICondition2@@W4STRUCTURED_QUERY_RESOLVE_OPTION@@PEBU_SYSTEMTIME@@_NW4LANGUAGE_OVERRIDE_CHECK@2@PEA_NPEAW462@5PEAPEAU3@@Z`
- size: `1652`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003378c`

## callees

- `0x180006790`
- `0x180008a50`
- `0x18000928c`
- `0x180009a40`
- `0x18000ef3c`
- `0x18000f5b8`
- `0x18000f61c`
- `0x18000f7cc`
- `0x180011030`
- `0x18001b2b4`
- `0x18005546c`
- `0x180055ef4`
- `0x180056a7c`
- `0x18005daf0`
- `0x18006e830`
- `0x18006f300`
- `0x18006f930`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000f0fc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000f0fc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000f320`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000f349`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000f4c9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000f320`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000f349`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000f4c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f209`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f213`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f209`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f213`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f21d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f21d`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::Solution::ResolveLeafOneStep(
        StructuredQuery1::Solution *a1,
        struct ICondition2 *a2,
        enum STRUCTURED_QUERY_RESOLVE_OPTION a3,
        struct _SYSTEMTIME *a4,
        __int64 a5,
        int a6,
        char *a7,
        _DWORD *a8,
        __int64 a9,
        struct ICondition2 **a10)
{
  char *v11; // r15
  _DWORD *v12; // r12
  struct ICondition2Vtbl *lpVtbl; // rax
  char v16; // r14
  HRESULT (__stdcall *GetLeafConditionInfo)(ICondition2 *, PROPERTYKEY *, CONDITION_OPERATION *, PROPVARIANT *); // rax
  int Compound; // ebx
  struct IRichChunk *v19; // rdx
  bool v20; // r12
  bool v21; // r14
  unsigned int QuotePrefixStatus; // r15d
  const WCHAR *v23; // r9
  const WCHAR *v24; // rbx
  __int64 i; // r8
  __int64 v26; // rdx
  enum tagCONDITION_OPERATION v27; // r10d
  struct _SYSTEMTIME *v28; // r15
  struct IInterval *v29; // r15
  __int64 v30; // r9
  int v31; // r11d
  int v32; // edi
  int v33; // eax
  struct IRichChunk *v34; // rcx
  struct IRichChunk *v35; // rcx
  struct IRichChunk *v36; // rcx
  struct ICondition2 *v37; // rax
  struct ICondition2 **v38; // rcx
  __int64 v40; // rax
  int v41; // eax
  const wchar_t *v42; // r9
  StructuredQuery1::Solution *v43; // rcx
  int Predicate; // eax
  WCHAR *v45; // rbx
  int NonSpacedOverrideLocaleName; // eax
  enum tagCONDITION_TYPE v47; // edx
  const wchar_t *v48; // r9
  StructuredQuery1::Solution *v49; // rcx
  WCHAR *v50; // rsi
  struct IRichChunk *v51; // rbx
  wchar_t *v52; // rax
  struct IRichChunk *v53; // r10
  struct IRichChunk *v54; // r11
  unsigned int v55; // esi
  struct IRichChunk *v56; // rbx
  wchar_t *v57; // rax
  struct IRichChunk *v58; // r10
  struct IRichChunk *v59; // r11
  int v60; // edi
  unsigned int lpString2; // [rsp+20h] [rbp-E0h]
  struct ICondition2 **v62; // [rsp+50h] [rbp-B0h]
  enum tagCONDITION_OPERATION v63; // [rsp+74h] [rbp-8Ch] BYREF
  bool v64; // [rsp+78h] [rbp-88h]
  LPCWSTR lpString1; // [rsp+80h] [rbp-80h] BYREF
  char *v66; // [rsp+88h] [rbp-78h]
  struct ICondition2 *v67; // [rsp+90h] [rbp-70h] BYREF
  struct IRichChunk *v68; // [rsp+98h] [rbp-68h] BYREF
  struct IRichChunk *v69; // [rsp+A0h] [rbp-60h] BYREF
  struct IRichChunk *v70; // [rsp+A8h] [rbp-58h] BYREF
  struct _SYSTEMTIME *v71; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp-48h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+C0h] [rbp-40h] BYREF
  _DWORD *v74; // [rsp+D8h] [rbp-28h]
  struct ICondition2 **v75; // [rsp+E0h] [rbp-20h]
  struct _tagpropertykey v76; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v77[4]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR Name[88]; // [rsp+120h] [rbp+20h] BYREF

  v11 = a7;
  v12 = a8;
  v75 = a10;
  v71 = a4;
  lpVtbl = a2->lpVtbl;
  v16 = 0;
  v67 = 0;
  v63 = COP_IMPLICIT;
  GetLeafConditionInfo = lpVtbl->GetLeafConditionInfo;
  v66 = a7;
  v74 = a8;
  memset(&v76, 0, sizeof(v76));
  memset(&pvar, 0, sizeof(pvar));
  Compound = ((__int64 (__fastcall *)(struct ICondition2 *, struct _tagpropertykey *, enum tagCONDITION_OPERATION *, struct tagPROPVARIANT *))GetLeafConditionInfo)(
               a2,
               &v76,
               &v63,
               &pvar);
  if ( Compound < 0 )
  {
    v32 = a6;
    goto LABEL_41;
  }
  pv = 0;
  Compound = ((__int64 (__fastcall *)(struct ICondition2 *, LPVOID *))a2->lpVtbl->GetLocale)(a2, &pv);
  if ( Compound < 0 )
  {
    v32 = a6;
    goto LABEL_40;
  }
  lpString1 = 0;
  Compound = ((__int64 (__fastcall *)(struct ICondition2 *, LPCWSTR *))a2->lpVtbl->GetValueType)(a2, &lpString1);
  if ( Compound < 0 )
  {
    v32 = a6;
    goto LABEL_39;
  }
  v68 = 0;
  v70 = 0;
  v69 = 0;
  Compound = ((__int64 (__fastcall *)(struct ICondition2 *, struct IRichChunk **, struct IRichChunk **, struct IRichChunk **))a2->lpVtbl->GetInputTerms)(
               a2,
               &v68,
               &v70,
               &v69);
  if ( Compound >= 0 )
  {
    v20 = (a3 & 8) == 0;
    v21 = (a3 & 4) == 0;
    if ( v63 == COP_IMPLICIT
      && pvar.vt == 31
      && !*pvar.bstrVal
      && CompareStringW(0x7Fu, 0, lpString1, -1, L"System.StructuredQueryType.Value", -1) == 2 )
    {
      if ( (a3 & 0x20) != 0 )
      {
        memset(v77, 0, 24);
        Predicate = StructuredQuery1::Solution::MakePredicate(
                      a1,
                      &v76,
                      2,
                      0,
                      v77,
                      &cchOriginalDestLength,
                      0,
                      v68,
                      0,
                      0,
                      (a3 & 8) == 0,
                      (a3 & 4) == 0,
                      &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                      &v67);
      }
      else
      {
        Predicate = StructuredQuery1::Solution::MakeTruthValue(
                      v43,
                      1,
                      &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                      (void **)&v67);
      }
      v32 = a6;
      Compound = Predicate;
      v16 = 0;
      goto LABEL_31;
    }
    QuotePrefixStatus = StructuredQuery1::GetQuotePrefixStatus((StructuredQuery1 *)v69, v19);
    if ( (QuotePrefixStatus & 0x40) == 0 )
    {
      v23 = L"System.StructuredQueryType.DateTime";
      v24 = lpString1;
      i = 31;
      v26 = 0;
      if ( ((pvar.vt - 31) & 0xEFFF) != 0 || !lpString1 )
      {
LABEL_8:
        v27 = v63;
        if ( (QuotePrefixStatus & 0x80u) == 0 && (unsigned int)(v63 - 12) <= 1 && (a3 & 0xC0) != 0x40 && pvar.vt == 31 )
        {
          v45 = (WCHAR *)pv;
          LODWORD(v71) = 0;
          v64 = (a3 & 0x80u) == 0 && (QuotePrefixStatus & 1) != 0;
          NonSpacedOverrideLocaleName = CScriptAutoDetection::GetNonSpacedOverrideLocaleName(
                                          (CScriptAutoDetection *)g_scriptAutoDetection,
                                          pvar.bstrVal,
                                          (const wchar_t *)pv,
                                          Name,
                                          lpString2,
                                          (enum AMBIGUOUS_CJK_TEXT *)&v71);
          v49 = 0;
          v50 = Name;
          if ( NonSpacedOverrideLocaleName < 0 )
            v50 = v45;
          if ( (_DWORD)v71 == 3 )
          {
            memset(v77, 0, 24);
            v55 = 0;
            while ( v55 < 3 )
            {
              v56 = v68;
              v57 = (wchar_t *)StructuredQuery1::_SemanticTypeFromVarType(
                                 (StructuredQuery1 *)(unsigned int)a3,
                                 SQRO_DONT_RESOLVE_RANGES|SQRO_DONT_MAP_RELATIONS|SQRO_DONT_SIMPLIFY_CONDITION_TREES|SQRO_ALWAYS_ONE_INTERVAL|SQRO_DONT_RESOLVE_DATETIME,
                                 (unsigned __int16)lpString1,
                                 v48);
              LOBYTE(v62) = 0;
              Compound = StructuredQuery1::Solution::BreakAndMakePredicate(
                           a1,
                           &v76,
                           v63,
                           v57,
                           (struct IObjectArray *)pvar.hVal.QuadPart,
                           (PCWSTR)(&StructuredQuery1::g_rgpszAmbiguousHanCaseLocaleNames)[v55],
                           v56,
                           v59,
                           v58,
                           QuotePrefixStatus,
                           (struct StructuredQuery1::OneWord *)v62,
                           (a3 & 4) == 0,
                           v64,
                           (struct ICondition2 **)&v77[v55]);
              if ( Compound >= 0 && (a3 & 0x80u) != 0 && v63 == COP_WORD_EQUAL )
                Compound = StructuredQuery1::Solution::ResolveGrepPhraseHack(
                             a1,
                             &v76,
                             &pvar,
                             lpString1,
                             (const wchar_t *)(&StructuredQuery1::g_rgpszAmbiguousHanCaseLocaleNames)[v55],
                             v68,
                             v70,
                             v69,
                             (a3 & 4) == 0,
                             QuotePrefixStatus,
                             (struct ICondition2 **)&v77[v55]);
              ++v55;
              if ( Compound < 0 )
                goto LABEL_82;
            }
            Compound = StructuredQuery1::Solution::MakeCompound(
                         v49,
                         v47,
                         (struct ICondition2 **)v77,
                         (unsigned int)v48,
                         (a3 & 4) == 0,
                         &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                         (void **)&v67);
            v60 = 0;
            if ( Compound >= 0 )
            {
              while ( (unsigned __int64)v60 < 3 )
                IUnknown_SafeReleaseAndNullPtr<GrowableBuffer<tagHITRANGE>>(&v77[v60++]);
            }
          }
          else
          {
            v51 = v68;
            v52 = (wchar_t *)StructuredQuery1::_SemanticTypeFromVarType(
                               (StructuredQuery1 *)(unsigned int)a3,
                               SQRO_DONT_RESOLVE_RANGES|SQRO_DONT_MAP_RELATIONS|SQRO_DONT_SIMPLIFY_CONDITION_TREES|SQRO_ALWAYS_ONE_INTERVAL|SQRO_DONT_RESOLVE_DATETIME,
                               (unsigned __int16)lpString1,
                               v48);
            LOBYTE(v62) = 0;
            Compound = StructuredQuery1::Solution::BreakAndMakePredicate(
                         a1,
                         &v76,
                         v63,
                         v52,
                         (struct IObjectArray *)pvar.hVal.QuadPart,
                         v50,
                         v51,
                         v54,
                         v53,
                         QuotePrefixStatus,
                         (struct StructuredQuery1::OneWord *)v62,
                         (a3 & 4) == 0,
                         (a3 & 0x80u) == 0 && (QuotePrefixStatus & 1) != 0,
                         &v67);
            if ( Compound >= 0 && (a3 & 0x80u) != 0 && v63 == COP_WORD_EQUAL )
              Compound = StructuredQuery1::Solution::ResolveGrepPhraseHack(
                           a1,
                           &v76,
                           &pvar,
                           lpString1,
                           v50,
                           v68,
                           v70,
                           v69,
                           (a3 & 4) == 0,
                           QuotePrefixStatus,
                           &v67);
          }
LABEL_82:
          v32 = 0;
          v16 = 0;
          goto LABEL_30;
        }
        if ( (a3 & 1) == 0 )
        {
          v28 = v71;
          if ( v71 )
          {
            if ( v24 )
            {
              if ( !lstrcmpW(v24, L"System.StructuredQueryType.DateTime")
                && (unsigned __int16)StructuredQuery1::ValueVt(a2) == 31 )
              {
                v16 = 1;
                v41 = StructuredQuery1::Solution::ResolveDateTimeLeaf(a1, a2, a3, v28, &v76, v63, &pvar, &v67);
                goto LABEL_47;
              }
              v27 = v63;
              v24 = lpString1;
            }
          }
        }
        v71 = 0;
        v29 = 0;
        if ( (a3 & 0x10) == 0 && pvar.vt == 13 )
        {
          (**(void (__fastcall ***)(LARGE_INTEGER, GUID *, struct _SYSTEMTIME **, const WCHAR *))pvar.hVal.QuadPart)(
            pvar.hVal,
            &GUID_6bf0a714_3c18_430b_8b5d_83b1c234d3db,
            &v71,
            v23);
          v27 = v63;
          v24 = lpString1;
          v29 = (struct IInterval *)v71;
        }
        if ( v29 )
        {
          v42 = (const wchar_t *)pv;
          if ( !v24 && (a3 & 0x100) != 0 )
            v24 = StructuredQuery1::_SemanticTypeFromVarType((StructuredQuery1 *)0x1F, v26);
          Compound = StructuredQuery1::Solution::ResolveRange(a1, v29, a2, a3, &v76, v27, v24, v42, &v67);
          ((void (__fastcall *)(struct IInterval *))v29->lpVtbl->Release)(v29);
          v32 = a6;
          v16 = 0;
        }
        else
        {
          v30 = *((_QWORD *)a1 + 4);
          if ( !v30 )
            goto LABEL_26;
          v31 = 0;
          for ( i = 0; (unsigned int)i < *(_DWORD *)(v30 + 44); i = (unsigned int)(i + 1) )
          {
            v26 = *(_QWORD *)(v30 + 32);
            if ( v76.pid == *(_DWORD *)(v26 + 40LL * (unsigned int)i + 16) )
            {
              v40 = *(_QWORD *)&v76.fmtid.Data1 - *(_QWORD *)(v26 + 40LL * (unsigned int)i);
              if ( *(_QWORD *)&v76.fmtid.Data1 == *(_QWORD *)(v26 + 40LL * (unsigned int)i) )
                v40 = *(_QWORD *)v76.fmtid.Data4 - *(_QWORD *)(v26 + 40LL * (unsigned int)i + 8);
              if ( !v40 )
              {
                v31 = *(_DWORD *)(v26 + 40LL * (unsigned int)i + 32);
                break;
              }
            }
          }
          if ( v31 )
          {
            v32 = a6;
            v33 = StructuredQuery1::Solution::MakePredicate(
                    a1,
                    &v76,
                    (unsigned int)v27,
                    v24,
                    &pvar,
                    pv,
                    a6,
                    v68,
                    v70,
                    v69,
                    v20,
                    v21,
                    &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                    &v67);
          }
          else
          {
LABEL_26:
            v32 = a6;
            if ( a6 == 1 && (unsigned __int8)StructuredQuery1::IsNonEmptyPropVarString(&pvar, v26, i, v30) )
              v33 = StructuredQuery1::Solution::MakePredicate(
                      a1,
                      &v76,
                      (unsigned int)v63,
                      lpString1,
                      &pvar,
                      pv,
                      1,
                      v68,
                      v70,
                      v69,
                      v20,
                      v21,
                      &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                      &v67);
            else
              v33 = ((__int64 (__fastcall *)(struct ICondition2 *, GUID *, struct ICondition2 **))a2->lpVtbl->QueryInterface)(
                      a2,
                      &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                      &v67);
          }
          Compound = v33;
          v16 = 0;
        }
        goto LABEL_30;
      }
      if ( CompareStringW(0x7Fu, 0, lpString1, -1, L"System.StructuredQueryType.String", -1) == 2
        || CompareStringW(0x7Fu, 0, v24, -1, L"System.StructuredQueryType.DateTime", -1) == 2 )
      {
        v24 = lpString1;
        v23 = L"System.StructuredQueryType.DateTime";
        i = 31;
        v26 = 0;
        goto LABEL_8;
      }
    }
    *(struct _tagpropertykey *)v77 = v76;
    v16 = 1;
    v41 = StructuredQuery1::Solution::ResolveBasic(
            a1,
            QuotePrefixStatus,
            a2,
            a3,
            (struct _tagpropertykey *)v77,
            v63,
            lpString1,
            &pvar,
            (const wchar_t *)pv,
            v68,
            v70,
            v69,
            &v67);
LABEL_47:
    v32 = a6;
    Compound = v41;
LABEL_30:
    v11 = v66;
LABEL_31:
    v34 = v68;
    if ( v68 )
    {
      v68 = 0;
      ((void (__fastcall *)(struct IRichChunk *))v34->lpVtbl->Release)(v34);
    }
    v35 = v70;
    if ( v70 )
    {
      v70 = 0;
      ((void (__fastcall *)(struct IRichChunk *))v35->lpVtbl->Release)(v35);
    }
    v36 = v69;
    if ( v69 )
    {
      v69 = 0;
      ((void (__fastcall *)(struct IRichChunk *))v36->lpVtbl->Release)(v36);
    }
    v12 = v74;
    goto LABEL_38;
  }
  v32 = a6;
LABEL_38:
  CoTaskMemFree((LPVOID)lpString1);
LABEL_39:
  CoTaskMemFree(pv);
LABEL_40:
  PropVariantClear((PROPVARIANT *)&pvar);
LABEL_41:
  v37 = v67;
  v38 = v75;
  *v11 = v16;
  *v12 = v32;
  *v38 = v37;
  return (unsigned int)Compound;
}

```

## disassembly

```asm
0x18000ef3c  push    rbp
0x18000ef3e  push    rbx
0x18000ef3f  push    rsi
0x18000ef40  push    rdi
0x18000ef41  push    r12
0x18000ef43  push    r13
0x18000ef45  push    r14
0x18000ef47  push    r15
0x18000ef49  lea     rbp, [rsp-0E8h]
0x18000ef51  sub     rsp, 1E8h
0x18000ef58  mov     rax, cs:__security_cookie
0x18000ef5f  xor     rax, rsp
0x18000ef62  mov     [rbp+120h+var_50], rax
0x18000ef69  mov     rax, [rbp+120h+arg_48]
0x18000ef70  mov     r13, rcx
0x18000ef73  mov     r15, [rbp+120h+arg_30]
0x18000ef7a  xor     ecx, ecx
0x18000ef7c  mov     r12, [rbp+120h+arg_38]
0x18000ef83  mov     rsi, rdx
0x18000ef86  mov     [rbp+120h+var_140], rax
0x18000ef8a  xorps   xmm0, xmm0
0x18000ef8d  xor     eax, eax
0x18000ef8f  mov     [rbp+120h+var_170], r9
0x18000ef93  mov     [rbp+120h+var_138.pid], eax
0x18000ef96  lea     r9, [rbp+120h+pvar]
0x18000ef9a  mov     [rbp+120h+var_150], rax
0x18000ef9e  mov     edi, r8d
0x18000efa1  mov     rax, [rdx]
0x18000efa4  lea     r8, [rsp+220h+var_1AC]
0x18000efa9  mov     r14b, cl
0x18000efac  mov     [rsp+220h+var_1B0], cl
0x18000efb0  mov     [rbp+120h+var_190], rcx
0x18000efb4  lea     rdx, [rbp+120h+var_138]
0x18000efb8  mov     [rsp+220h+var_1AC], ecx
0x18000efbc  mov     rcx, rsi
0x18000efbf  mov     rax, [rax+80h]
0x18000efc6  mov     [rbp+120h+var_198], r15
0x18000efca  mov     [rbp+120h+var_148], r12
0x18000efce  movups  xmmword ptr [rbp+120h+var_138.fmtid.Data1], xmm0
0x18000efd2  movups  xmmword ptr [rbp+120h+pvar], xmm0
0x18000efd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efdb  mov     ebx, eax
0x18000efdd  xor     eax, eax
0x18000efdf  test    ebx, ebx
0x18000efe1  js      loc_18000F5A5
0x18000efe7  mov     [rbp+120h+pv], rax
0x18000efeb  lea     rdx, [rbp+120h+pv]
0x18000efef  mov     rax, [rsi]
0x18000eff2  mov     rcx, rsi
0x18000eff5  mov     rax, [rax+78h]
0x18000eff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000effe  mov     ebx, eax
0x18000f000  xor     eax, eax
0x18000f002  test    ebx, ebx
0x18000f004  js      loc_18000F59A
0x18000f00a  mov     [rbp+120h+lpString1], rax
0x18000f00e  lea     rdx, [rbp+120h+lpString1]
0x18000f012  mov     rax, [rsi]
0x18000f015  mov     rcx, rsi
0x18000f018  mov     rax, [rax+58h]
0x18000f01c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f021  mov     ebx, eax
0x18000f023  xor     eax, eax
0x18000f025  test    ebx, ebx
0x18000f027  js      loc_18000F58F
0x18000f02d  mov     [rbp+120h+var_188], rax
0x18000f031  lea     r9, [rbp+120h+var_180]
0x18000f035  mov     [rbp+120h+var_178], rax
0x18000f039  lea     r8, [rbp+120h+var_178]
0x18000f03d  mov     [rbp+120h+var_180], rax
0x18000f041  lea     rdx, [rbp+120h+var_188]
0x18000f045  mov     rax, [rsi]
0x18000f048  mov     rcx, rsi
0x18000f04b  mov     rax, [rax+68h]
0x18000f04f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f054  mov     ebx, eax
0x18000f056  test    eax, eax
0x18000f058  js      loc_18000F584
0x18000f05e  mov     r12d, edi
0x18000f061  mov     r14d, edi
0x18000f064  shr     r12d, 3
0x18000f068  or      ecx, 0FFFFFFFFh
0x18000f06b  shr     r14d, 2
0x18000f06f  not     r12b
0x18000f072  not     r14b
0x18000f075  and     r12b, 1
0x18000f079  and     r14b, 1
0x18000f07d  xor     ebx, ebx
0x18000f07f  mov     eax, 1Fh
0x18000f084  cmp     [rsp+220h+var_1AC], ebx
0x18000f088  jz      loc_18000F496
0x18000f08e  mov     rcx, [rbp+120h+var_180]; this
0x18000f092  call    ?GetQuotePrefixStatus@StructuredQuery1@@YAHPEAUIRichChunk@@@Z; StructuredQuery1::GetQuotePrefixStatus(IRichChunk *)
0x18000f097  mov     r15d, eax
0x18000f09a  test    al, 40h
0x18000f09c  jnz     loc_18000F27B
0x18000f0a2  movzx   ecx, word ptr [rbp+120h+pvar]
0x18000f0a6  lea     r9, aSystemStructur_17; "System.StructuredQueryType.DateTime"
0x18000f0ad  mov     rbx, [rbp+120h+lpString1]
0x18000f0b1  mov     r8d, 1Fh
0x18000f0b7  sub     cx, r8w
0x18000f0bb  mov     eax, 0EFFFh
0x18000f0c0  xor     edx, edx; dwCmpFlags
0x18000f0c2  test    ax, cx
0x18000f0c5  jz      loc_18000F2FA
0x18000f0cb  mov     r10d, [rsp+220h+var_1AC]
0x18000f0d0  test    r15b, r15b
0x18000f0d3  js      short loc_18000F0E2
0x18000f0d5  lea     eax, [r10-0Ch]
0x18000f0d9  cmp     eax, 1
0x18000f0dc  jbe     loc_18000F561
0x18000f0e2  test    dil, 1
0x18000f0e6  jnz     short loc_18000F113
0x18000f0e8  mov     r15, [rbp+120h+var_170]
0x18000f0ec  test    r15, r15
0x18000f0ef  jz      short loc_18000F113
0x18000f0f1  test    rbx, rbx
0x18000f0f4  jz      short loc_18000F113
0x18000f0f6  mov     rdx, r9; lpString2
0x18000f0f9  mov     rcx, rbx; lpString1
0x18000f0fc  call    cs:__imp_lstrcmpW
0x18000f102  test    eax, eax
0x18000f104  jz      loc_18000F3DE
0x18000f10a  mov     r10d, [rsp+220h+var_1AC]
0x18000f10f  mov     rbx, [rbp+120h+lpString1]
0x18000f113  xor     eax, eax
0x18000f115  mov     [rbp+120h+var_170], rax
0x18000f119  mov     r15d, eax
0x18000f11c  test    dil, 10h
0x18000f120  jnz     short loc_18000F12D
0x18000f122  cmp     word ptr [rbp+120h+pvar], 0Dh
0x18000f127  jz      loc_18000F4DD
0x18000f12d  test    r15, r15
0x18000f130  jnz     loc_18000F430
0x18000f136  mov     r9, [r13+20h]
0x18000f13a  test    r9, r9
0x18000f13d  jz      short loc_18000F176
0x18000f13f  mov     edi, [rbp+120h+var_138.pid]
0x18000f142  mov     r11d, r15d
0x18000f145  mov     r8d, r15d
0x18000f148  cmp     r8d, [r9+2Ch]
0x18000f14c  jnb     short loc_18000F16D
0x18000f14e  mov     rdx, [r9+20h]
0x18000f152  mov     eax, r8d
0x18000f155  lea     rcx, [rax+rax*4]
0x18000f159  cmp     edi, [rdx+rcx*8+10h]
0x18000f15d  jz      loc_18000F25A
0x18000f163  inc     r8d
0x18000f166  jmp     short loc_18000F148
0x18000f168  mov     r11d, [rdx+rcx*8+20h]
0x18000f16d  test    r11d, r11d
0x18000f170  jnz     loc_18000F509
0x18000f176  mov     edi, [rbp+120h+arg_28]
0x18000f17c  cmp     edi, 1
0x18000f17f  jnz     short loc_18000F192
0x18000f181  lea     rcx, [rbp+120h+pvar]
0x18000f185  call    StructuredQuery1__IsNonEmptyPropVarString
0x18000f18a  test    al, al
0x18000f18c  jnz     loc_18000F370
0x18000f192  mov     rax, [rsi]
0x18000f195  lea     r8, [rbp+120h+var_190]
0x18000f199  lea     rdx, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x18000f1a0  mov     rcx, rsi
0x18000f1a3  mov     rax, [rax]
0x18000f1a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1ab  mov     ebx, eax
0x18000f1ad  mov     r14b, r15b
0x18000f1b0  mov     r15, [rbp+120h+var_198]
0x18000f1b4  mov     rcx, [rbp+120h+var_188]
0x18000f1b8  xor     esi, esi
0x18000f1ba  test    rcx, rcx
0x18000f1bd  jz      short loc_18000F1CF
0x18000f1bf  mov     [rbp+120h+var_188], rsi
0x18000f1c3  mov     rax, [rcx]
0x18000f1c6  mov     rax, [rax+10h]
0x18000f1ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1cf  mov     rcx, [rbp+120h+var_178]
0x18000f1d3  test    rcx, rcx
0x18000f1d6  jz      short loc_18000F1E8
0x18000f1d8  mov     [rbp+120h+var_178], rsi
0x18000f1dc  mov     rax, [rcx]
0x18000f1df  mov     rax, [rax+10h]
0x18000f1e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1e8  mov     rcx, [rbp+120h+var_180]
0x18000f1ec  test    rcx, rcx
0x18000f1ef  jz      short loc_18000F201
0x18000f1f1  mov     [rbp+120h+var_180], rsi
0x18000f1f5  mov     rax, [rcx]
0x18000f1f8  mov     rax, [rax+10h]
0x18000f1fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f201  mov     r12, [rbp+120h+var_148]
0x18000f205  mov     rcx, [rbp+120h+lpString1]; pv
0x18000f209  call    cs:__imp_CoTaskMemFree
0x18000f20f  mov     rcx, [rbp+120h+pv]; pv
0x18000f213  call    cs:__imp_CoTaskMemFree
0x18000f219  lea     rcx, [rbp+120h+pvar]; pvar
0x18000f21d  call    cs:__imp_PropVariantClear
0x18000f223  mov     rax, [rbp+120h+var_190]
0x18000f227  mov     rcx, [rbp+120h+var_140]
0x18000f22b  mov     [r15], r14b
0x18000f22e  mov     [r12], edi
0x18000f232  mov     [rcx], rax
0x18000f235  mov     eax, ebx
0x18000f237  mov     rcx, [rbp+120h+var_50]
0x18000f23e  xor     rcx, rsp; StackCookie
0x18000f241  call    __security_check_cookie
0x18000f246  add     rsp, 1E8h
0x18000f24d  pop     r15
0x18000f24f  pop     r14
0x18000f251  pop     r13
0x18000f253  pop     r12
0x18000f255  pop     rdi
0x18000f256  pop     rsi
0x18000f257  pop     rbx
0x18000f258  pop     rbp
0x18000f259  retn
0x18000f25a  mov     rax, qword ptr [rbp+120h+var_138.fmtid.Data1]
0x18000f25e  sub     rax, [rdx+rcx*8]
0x18000f262  jnz     short loc_18000F26D
0x18000f264  mov     rax, qword ptr [rbp+120h+var_138.fmtid.Data4]
0x18000f268  sub     rax, [rdx+rcx*8+8]
0x18000f26d  test    rax, rax
0x18000f270  jz      loc_18000F168
0x18000f276  jmp     loc_18000F163
0x18000f27b  mov     eax, [rbp+120h+var_138.pid]
0x18000f27e  mov     r9d, edi; enum STRUCTURED_QUERY_RESOLVE_OPTION
0x18000f281  movups  xmm0, xmmword ptr [rbp+120h+var_138.fmtid.Data1]
0x18000f285  mov     [rbp+120h+var_120.pid], eax
0x18000f288  mov     r8, rsi; struct ICondition2 *
0x18000f28b  lea     rax, [rbp+120h+var_190]
0x18000f28f  mov     edx, r15d; int
0x18000f292  mov     [rsp+220h+var_1C0], rax; struct ICondition2 **
0x18000f297  mov     rcx, r13; this
0x18000f29a  mov     rax, [rbp+120h+var_180]
0x18000f29e  mov     r14b, 1
0x18000f2a1  mov     [rsp+220h+var_1C8], rax; struct IRichChunk *
0x18000f2a6  mov     rax, [rbp+120h+var_178]
0x18000f2aa  mov     [rsp+220h+var_1D0], rax; struct IRichChunk *
0x18000f2af  mov     rax, [rbp+120h+var_188]
0x18000f2b3  mov     [rsp+220h+var_1D8], rax; struct IRichChunk *
0x18000f2b8  mov     rax, [rbp+120h+pv]
0x18000f2bc  mov     [rsp+220h+var_1E0], rax; wchar_t *
0x18000f2c1  lea     rax, [rbp+120h+pvar]
0x18000f2c5  mov     [rsp+220h+var_1E8], rax; struct tagPROPVARIANT *
0x18000f2ca  mov     rax, [rbp+120h+lpString1]
0x18000f2ce  mov     [rsp+220h+var_1F0], rax; lpString1
0x18000f2d3  mov     eax, [rsp+220h+var_1AC]
0x18000f2d7  mov     [rsp+220h+cchCount2], eax; tagCONDITION_OPERATION
0x18000f2db  lea     rax, [rbp+120h+var_120]
0x18000f2df  mov     [rsp+220h+lpString2], rax; struct _tagpropertykey *
0x18000f2e4  movaps  xmmword ptr [rbp+120h+var_120.fmtid.Data1], xmm0
0x18000f2e8  call    ?ResolveBasic@Solution@StructuredQuery1@@AEAAJHPEAUICondition2@@W4STRUCTURED_QUERY_RESOLVE_OPTION@@U_tagpropertykey@@W4tagCONDITION_OPERATION@@PEB_WAEBUtagPROPVARIANT@@4PEAUIRichChunk@@66PEAPEAU3@@Z; StructuredQuery1::Solution::ResolveBasic(int,ICondition2 *,STRUCTURED_QUERY_RESOLVE_OPTION,_tagpropertykey,tagCONDITION_OPERATION,wchar_t const *,tagPROPVARIANT const &,wchar_t const *,IRichChunk *,IRichChunk *,IRichChunk *,ICondition2 * *)
0x18000f2ed  mov     edi, [rbp+120h+arg_28]
0x18000f2f3  mov     ebx, eax
0x18000f2f5  jmp     loc_18000F1B0
0x18000f2fa  test    rbx, rbx
0x18000f2fd  jz      loc_18000F0CB
0x18000f303  or      r9d, 0FFFFFFFFh; cchCount1
0x18000f307  lea     rax, aSystemStructur_24; "System.StructuredQueryType.String"
0x18000f30e  mov     [rsp+220h+cchCount2], r9d; cchCount2
0x18000f313  mov     r8, rbx; lpString1
0x18000f316  mov     ecx, 7Fh; Locale
0x18000f31b  mov     [rsp+220h+lpString2], rax; lpString2
0x18000f320  call    cs:__imp_CompareStringW
0x18000f326  cmp     eax, 2
0x18000f329  jz      short loc_18000F358
0x18000f32b  or      eax, 0FFFFFFFFh
0x18000f32e  lea     rcx, aSystemStructur_17; "System.StructuredQueryType.DateTime"
0x18000f335  xor     edx, edx; dwCmpFlags
0x18000f337  mov     [rsp+220h+cchCount2], eax; cchCount2
0x18000f33b  mov     [rsp+220h+lpString2], rcx; lpString2
0x18000f340  mov     r9d, eax; cchCount1
0x18000f343  mov     r8, rbx; lpString1
0x18000f346  lea     ecx, [rdx+7Fh]; Locale
0x18000f349  call    cs:__imp_CompareStringW
0x18000f34f  cmp     eax, 2
0x18000f352  jnz     loc_18000F27B
0x18000f358  mov     rbx, [rbp+120h+lpString1]
0x18000f35c  lea     r9, aSystemStructur_17; "System.StructuredQueryType.DateTime"
0x18000f363  mov     r8d, 1Fh
0x18000f369  xor     edx, edx
0x18000f36b  jmp     loc_18000F0CB
0x18000f370  mov     rax, [rbp+120h+var_180]
0x18000f374  lea     r8, [rbp+120h+var_190]
0x18000f378  mov     rcx, [rbp+120h+var_178]
0x18000f37c  lea     r11, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x18000f383  mov     rdx, [rbp+120h+var_188]
0x18000f387  mov     r10, [rbp+120h+pv]
0x18000f38b  mov     r9, [rbp+120h+lpString1]
0x18000f38f  mov     [rsp+220h+var_1B8], r8
0x18000f394  mov     r8d, [rsp+220h+var_1AC]
0x18000f399  mov     [rsp+220h+var_1C0], r11
0x18000f39e  mov     byte ptr [rsp+220h+var_1C8], r14b
0x18000f3a3  mov     byte ptr [rsp+220h+var_1D0], r12b
0x18000f3a8  mov     [rsp+220h+var_1D8], rax
0x18000f3ad  mov     [rsp+220h+var_1E0], rcx
0x18000f3b2  mov     [rsp+220h+var_1E8], rdx
0x18000f3b7  mov     dword ptr [rsp+220h+var_1F0], 1
0x18000f3bf  mov     qword ptr [rsp+220h+cchCount2], r10
0x18000f3c4  lea     rax, [rbp+120h+pvar]
  ... truncated ...
```
