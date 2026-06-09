# StructuredQuery1::SqlGenerator::WriteSqlLeaf(wchar_t *,unsigned __int64,ICondition2 *,int,SQL_GENERATION_OPTIONS,bool,StructuredQuery1::VirtualPropertyMap *,bool,wchar_t * *,unsigned __int64 *)

- ea: `0x18004a374`
- end: `0x18004bb8c`
- name: `?WriteSqlLeaf@SqlGenerator@StructuredQuery1@@AEAAJPEA_W_KPEAUICondition2@@HW4SQL_GENERATION_OPTIONS@@_NPEAVVirtualPropertyMap@2@4PEAPEA_WPEA_K@Z`
- size: `6168`
- prototype: `int __high(wchar_t *, unsigned __int64, struct ICondition2 *, int, enum SQL_GENERATION_OPTIONS, bool, struct StructuredQuery1::VirtualPropertyMap *, bool, wchar_t **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004a18c`

## callees

- `0x180024040`
- `0x18002a220`
- `0x18002e5c0`
- `0x180032148`
- `0x180036910`
- `0x18004146c`
- `0x18004a374`
- `0x18005ac20`
- `0x18005ca18`
- `0x18005daf0`
- `0x18006749c`
- `0x18006dc14`
- `0x18006f740`
- `0x180080238`
- `0x18008094c`
- `0x180080e98`
- `0x1800810fc`
- `0x180082b64`
- `0x180082c64`
- `0x1800833a4`
- `0x180083444`
- `0x180083758`
- `0x18008388c`
- `0x1800838c8`
- `0x180083904`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004a470`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004a6e0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004a73e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004a470`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004a6e0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004a73e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004bb3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004bb4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004bb3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004bb4b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004bb55`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004bb55`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall StructuredQuery1::SqlGenerator::WriteSqlLeaf(
        __int64 a1,
        wchar_t *a2,
        unsigned __int64 a3,
        struct ICondition2 *a4,
        __int64 a5,
        int a6,
        bool a7,
        struct StructuredQuery1::VirtualPropertyMap *a8,
        char a9,
        wchar_t **a10,
        unsigned __int64 *a11)
{
  unsigned __int64 *v13; // r14
  int v14; // ebx
  StructuredQuery1::SqlGenerator *v15; // rcx
  bool v16; // bl
  StructuredQuery1::SqlGenerator *v17; // rcx
  void *v18; // r14
  StructuredQuery1::SqlGenerator *v19; // rcx
  int v20; // eax
  StructuredQuery1::ConditionGroupManager *v21; // rcx
  unsigned int LCID; // eax
  struct ISemanticSearchParameters **v23; // r8
  StructuredQuery1::ConditionGroupManager *v24; // rcx
  int v25; // eax
  __int64 v26; // rdx
  StructuredQuery1::ConditionGroupManager *v27; // rcx
  unsigned int v28; // eax
  int v29; // r15d
  __int64 v30; // rcx
  __int64 v31; // r9
  char v32; // al
  __int64 v33; // rbx
  __int64 v34; // r15
  int v35; // eax
  int v36; // esi
  int v37; // eax
  unsigned int v38; // eax
  int v39; // eax
  StructuredQuery1::ConditionGroupManager *v40; // rcx
  StructuredQuery1::ConditionGroupManager *v41; // rcx
  unsigned int v42; // eax
  int v43; // r15d
  __int64 v44; // rcx
  __int64 v45; // r9
  char v46; // al
  __int64 v47; // rbx
  __int64 v48; // r15
  int v49; // eax
  int v50; // esi
  int v51; // eax
  unsigned int v52; // eax
  int v53; // eax
  struct ISemanticSearchParameters **v54; // r8
  StructuredQuery1::ConditionGroupManager *v55; // rcx
  StructuredQuery1::ConditionGroupManager *v56; // rcx
  unsigned int v57; // eax
  int v58; // r15d
  __int64 v59; // rcx
  __int64 v60; // r9
  char v61; // al
  __int64 v62; // rbx
  __int64 v63; // r15
  int v64; // eax
  int v65; // esi
  int v66; // eax
  unsigned int v67; // eax
  int v68; // eax
  StructuredQuery1::ConditionGroupManager *v69; // rcx
  StructuredQuery1::ConditionGroupManager *v70; // rcx
  unsigned int v71; // eax
  int v72; // r15d
  __int64 v73; // rcx
  __int64 v74; // r9
  char v75; // al
  __int64 v76; // rbx
  __int64 v77; // r15
  int v78; // eax
  int v79; // esi
  int v80; // eax
  unsigned int v81; // eax
  int v82; // eax
  int lpString2; // [rsp+20h] [rbp-F0h]
  int lpString2a; // [rsp+20h] [rbp-F0h]
  int lpString2b; // [rsp+20h] [rbp-F0h]
  int lpString2c; // [rsp+20h] [rbp-F0h]
  int lpString2d; // [rsp+20h] [rbp-F0h]
  int lpString2e; // [rsp+20h] [rbp-F0h]
  int lpString2f; // [rsp+20h] [rbp-F0h]
  int lpString2g; // [rsp+20h] [rbp-F0h]
  int lpString2h; // [rsp+20h] [rbp-F0h]
  unsigned int cchCount2; // [rsp+28h] [rbp-E8h]
  unsigned int cchCount2a; // [rsp+28h] [rbp-E8h]
  unsigned int cchCount2b; // [rsp+28h] [rbp-E8h]
  wchar_t **cchCount2c; // [rsp+28h] [rbp-E8h]
  unsigned int cchCount2d; // [rsp+28h] [rbp-E8h]
  unsigned int cchCount2e; // [rsp+28h] [rbp-E8h]
  wchar_t **cchCount2f; // [rsp+28h] [rbp-E8h]
  unsigned int cchCount2g; // [rsp+28h] [rbp-E8h]
  unsigned int cchCount2h; // [rsp+28h] [rbp-E8h]
  wchar_t **cchCount2i; // [rsp+28h] [rbp-E8h]
  unsigned int cchCount2j; // [rsp+28h] [rbp-E8h]
  unsigned int cchCount2k; // [rsp+28h] [rbp-E8h]
  wchar_t **cchCount2l; // [rsp+28h] [rbp-E8h]
  int v106; // [rsp+30h] [rbp-E0h]
  wchar_t *v107; // [rsp+90h] [rbp-80h] BYREF
  unsigned __int64 v108; // [rsp+98h] [rbp-78h] BYREF
  bool v109; // [rsp+A0h] [rbp-70h] BYREF
  int v110; // [rsp+A4h] [rbp-6Ch] BYREF
  int v111; // [rsp+A8h] [rbp-68h] BYREF
  LPVOID pv; // [rsp+B0h] [rbp-60h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+B8h] [rbp-58h] BYREF
  LARGE_INTEGER hVal; // [rsp+D0h] [rbp-40h] BYREF
  int v115; // [rsp+D8h] [rbp-38h]
  StructuredQuery1::SqlGenerator *v116; // [rsp+E0h] [rbp-30h] BYREF
  PCNZWCH lpString1; // [rsp+E8h] [rbp-28h] BYREF
  unsigned __int64 *v118; // [rsp+F0h] [rbp-20h]
  struct _tagpropertykey v119; // [rsp+F8h] [rbp-18h] BYREF
  int v120[8]; // [rsp+110h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+78h]

  v107 = a2;
  v108 = a3;
  v13 = a11;
  v118 = a11;
  memset(&v119, 0, sizeof(v119));
  LODWORD(v116) = 0;
  memset(&pvar, 0, sizeof(pvar));
  v14 = ((__int64 (__fastcall *)(struct ICondition2 *, struct _tagpropertykey *, StructuredQuery1::SqlGenerator **, struct tagPROPVARIANT *))a4->lpVtbl->GetLeafConditionInfo)(
          a4,
          &v119,
          &v116,
          &pvar);
  if ( v14 < 0 )
    goto LABEL_195;
  lpString1 = 0;
  v14 = ((__int64 (__fastcall *)(struct ICondition2 *, PCNZWCH *))a4->lpVtbl->GetValueType)(a4, &lpString1);
  if ( v14 < 0 )
  {
LABEL_194:
    PropVariantClear((PROPVARIANT *)&pvar);
LABEL_195:
    *a10 = v107;
    *v13 = v108;
    return (unsigned int)v14;
  }
  v109 = 0;
  pv = 0;
  v14 = StructuredQuery1::SqlGenerator::DetermineProperty(v15, &v119, a8, &v109, (wchar_t **)&pv);
  if ( v14 < 0 )
  {
LABEL_193:
    CoTaskMemFree((LPVOID)lpString1);
    goto LABEL_194;
  }
  v16 = CompareStringW(0x7Fu, 0, lpString1, -1, L"System.StructuredQueryType.SortKeyDescription", -1) == 2;
  v17 = (StructuredQuery1::SqlGenerator *)(unsigned int)v116;
  v18 = pv;
  if ( (int)v116 <= 7 )
  {
    switch ( (_DWORD)v116 )
    {
      case 7:
        v20 = StructuredQuery1::SqlGenerator::WriteLike(
                (StructuredQuery1::SqlGenerator *)L"%",
                v107,
                v108,
                0,
                a7,
                (const wchar_t *)pv,
                (const wchar_t *)&cchOriginalDestLength,
                L"%",
                &pvar,
                &v107,
                &v108);
        goto LABEL_191;
      case 0:
        v14 = -2147418113;
LABEL_192:
        CoTaskMemFree(v18);
        v13 = v118;
        goto LABEL_193;
      case 1:
        v20 = StructuredQuery1::SqlGenerator::WriteValueComparison(
                0,
                v107,
                v108,
                v109,
                v16,
                pvar.vt,
                a7,
                (const wchar_t *)pv,
                L"=",
                L"<>",
                &pvar,
                &v107,
                &v108);
        goto LABEL_191;
      case 2:
        v20 = StructuredQuery1::SqlGenerator::WriteValueComparison(
                (StructuredQuery1::SqlGenerator *)(unsigned int)((_DWORD)v116 - 2),
                v107,
                v108,
                v109,
                v16,
                pvar.vt,
                a7,
                (const wchar_t *)pv,
                L"<>",
                L"=",
                &pvar,
                &v107,
                &v108);
        goto LABEL_191;
      case 3:
        v20 = StructuredQuery1::SqlGenerator::WriteValueComparison(
                (StructuredQuery1::SqlGenerator *)(unsigned int)((_DWORD)v116 - 3),
                v107,
                v108,
                v109,
                v16,
                pvar.vt,
                a7,
                (const wchar_t *)pv,
                L"<",
                L">=",
                &pvar,
                &v107,
                &v108);
        goto LABEL_191;
      case 4:
        v20 = StructuredQuery1::SqlGenerator::WriteValueComparison(
                (StructuredQuery1::SqlGenerator *)(unsigned int)((_DWORD)v116 - 4),
                v107,
                v108,
                v109,
                v16,
                pvar.vt,
                a7,
                (const wchar_t *)pv,
                L">",
                L"<=",
                &pvar,
                &v107,
                &v108);
        goto LABEL_191;
    }
    v19 = (StructuredQuery1::SqlGenerator *)(unsigned int)((_DWORD)v116 - 5);
    if ( (_DWORD)v116 == 5 )
    {
      v20 = StructuredQuery1::SqlGenerator::WriteValueComparison(
              v19,
              v107,
              v108,
              v109,
              v16,
              pvar.vt,
              a7,
              (const wchar_t *)pv,
              L"<=",
              L">",
              &pvar,
              &v107,
              &v108);
      goto LABEL_191;
    }
    if ( (_DWORD)v116 == 6 )
    {
      v20 = StructuredQuery1::SqlGenerator::WriteValueComparison(
              v19,
              v107,
              v108,
              v109,
              v16,
              pvar.vt,
              a7,
              (const wchar_t *)pv,
              L">=",
              L"<",
              &pvar,
              &v107,
              &v108);
LABEL_191:
      v14 = v20;
      goto LABEL_192;
    }
LABEL_28:
    v14 = -2147024809;
    goto LABEL_192;
  }
  switch ( (_DWORD)v116 )
  {
    case 8:
      v20 = StructuredQuery1::SqlGenerator::WriteLike(
              (StructuredQuery1::SqlGenerator *)L"%",
              v107,
              v108,
              0,
              a7,
              (const wchar_t *)pv,
              L"%",
              (const wchar_t *)&cchOriginalDestLength,
              &pvar,
              &v107,
              &v108);
      goto LABEL_191;
    case 9:
      v20 = StructuredQuery1::SqlGenerator::WriteLike(
              (StructuredQuery1::SqlGenerator *)L"%",
              v107,
              v108,
              0,
              a7,
              (const wchar_t *)pv,
              L"%",
              L"%",
              &pvar,
              &v107,
              &v108);
      goto LABEL_191;
    case 0xA:
      v20 = StructuredQuery1::SqlGenerator::WriteLike(
              (StructuredQuery1::SqlGenerator *)L"%",
              v107,
              v108,
              0,
              !a7,
              (const wchar_t *)pv,
              L"%",
              L"%",
              &pvar,
              &v107,
              &v108);
      goto LABEL_191;
    case 0xB:
      v20 = StructuredQuery1::SqlGenerator::WriteLike(
              (StructuredQuery1::SqlGenerator *)0xB,
              v107,
              v108,
              1,
              a7,
              (const wchar_t *)pv,
              (const wchar_t *)&cchOriginalDestLength,
              (const wchar_t *)&cchOriginalDestLength,
              &pvar,
              &v107,
              &v108);
      goto LABEL_191;
  }
  if ( (_DWORD)v116 != 12 && (_DWORD)v116 != 13 )
  {
    if ( (_DWORD)v116 == 14 )
    {
      if ( lpString1 )
      {
        if ( CompareStringW(0x7Fu, 0, lpString1, -1, L"System.StructuredQueryType.AnyBitsSet", -1) == 2 )
        {
          v20 = StructuredQuery1::SqlGenerator::WriteValueComparison(
                  v17,
                  v107,
                  v108,
                  v109,
                  v16,
                  pvar.vt,
                  a7,
                  (const wchar_t *)v18,
                  L"= ANY BITWISE",
                  L"<> ANY BITWISE",
                  &pvar,
                  &v107,
                  &v108);
          goto LABEL_191;
        }
        if ( lpString1 && CompareStringW(0x7Fu, 0, lpString1, -1, L"System.StructuredQueryType.AllBitsSet", -1) == 2 )
        {
          v20 = StructuredQuery1::SqlGenerator::WriteValueComparison(
                  v17,
                  v107,
                  v108,
                  v109,
                  v16,
                  pvar.vt,
                  a7,
                  (const wchar_t *)v18,
                  L"= ALL BITWISE",
                  L"<> ALL BITWISE",
                  &pvar,
                  &v107,
                  &v108);
          goto LABEL_191;
        }
      }
      v20 = StructuredQuery1::SqlGenerator::WriteApplicationSpecific(v17, v107, v108, a7, &pvar, &v107, &v108);
      goto LABEL_191;
    }
    goto LABEL_28;
  }
  hVal = pvar.hVal;
  v115 = (int)v116;
  if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_FI45262758>::GetImpl'::`2'::impl) )
  {
LABEL_39:
    LCID = StructuredQuery1::ConditionGroupManager::GetLCID(v21, a4);
    v106 = StructuredQuery1::LocaleForProperty(&v119, LCID);
    LOBYTE(lpString2) = 1;
    v20 = StructuredQuery1::SqlGenerator::WriteFullText(
            a1,
            v107,
            v108,
            0,
            lpString2,
            1,
            v106,
            a9,
            a6,
            a7,
            &v119,
            v18,
            &hVal,
            1,
            a8,
            L" AND ",
            &v107,
            &v108);
    goto LABEL_191;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60428908>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60428908>::GetImpl'::`2'::impl) )
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl'::`2'::impl) )
    {
      pv = 0;
      if ( (int)StructuredQuery1::TryGetSemanticSearchParameters((StructuredQuery1 *)a4, (struct ICondition *)&pv, v54) < 0 )
        goto LABEL_184;
      v69 = (StructuredQuery1::ConditionGroupManager *)pv;
      if ( !pv )
        goto LABEL_184;
      v111 = 0;
      v25 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)pv + 32LL))(pv, &v111);
      v14 = v25;
      if ( v25 < 0 )
      {
        v26 = 5441;
        goto LABEL_155;
      }
      v110 = 0;
      v25 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)pv + 40LL))(pv, &v110);
      v14 = v25;
      if ( v25 < 0 )
      {
        v26 = 5443;
        goto LABEL_155;
      }
      v71 = StructuredQuery1::ConditionGroupManager::GetLCID(v70, a4);
      v72 = StructuredQuery1::LocaleForProperty(&v119, v71);
      if ( v111 )
      {
        v14 = StringCchCopyExW(v107, v108, L"(", &v107, &v108, cchCount2);
        if ( v14 < 0 )
          goto LABEL_113;
        LOBYTE(v74) = 0;
        v75 = v111;
        if ( (v111 & 1) != 0 )
        {
          LOBYTE(lpString2g) = v110 <= 1;
          LOBYTE(v74) = 1;
          v14 = StructuredQuery1::SqlGenerator::WriteFullText(
                  a1,
                  v107,
                  v108,
                  v74,
                  lpString2g,
                  v110 <= 1,
                  v72,
                  a9,
                  a6,
                  a7,
                  &v119,
                  v18,
                  &hVal,
                  1,
                  a8,
                  L" AND ",
                  &v107,
                  &v108);
          if ( v14 < 0 )
            goto LABEL_113;
          LOBYTE(v74) = 1;
          v75 = v111;
        }
        if ( (v75 & 2) != 0 && !*(_DWORD *)(a1 + 96) )
        {
          LOBYTE(cchCount2j) = 1;
          v14 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))StructuredQuery1::SqlGenerator::WriteSemanticSearchContains)(
                  v73,
                  v107,
                  v108,
                  v74,
                  (LARGE_INTEGER)pvar.hVal.QuadPart);
          if ( v14 < 0 )
            goto LABEL_113;
          LOBYTE(v74) = 1;
          v75 = v111;
        }
        if ( (v75 & 4) != 0 && !*(_DWORD *)(a1 + 96) )
        {
          LOBYTE(cchCount2j) = 0;
          v14 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))StructuredQuery1::SqlGenerator::WriteSemanticSearchContains)(
                  v73,
                  v107,
                  v108,
                  v74,
                  (LARGE_INTEGER)pvar.hVal.QuadPart);
        }
        if ( v14 < 0 )
          goto LABEL_113;
        v14 = StringCchCopyExW(v107, v108, L")", &v107, &v108, cchCount2j);
        if ( v14 >= 0 )
          v14 = StructuredQuery1::WriteMergeStrategy(v107, v108, (unsigned int)v110, &v107, &v108);
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54310796>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54310796>::GetImpl'::`2'::impl) )
          goto LABEL_113;
        if ( v14 < 0 )
          goto LABEL_113;
        v14 = StringCchCopyExW(v107, v108, L")", &v107, &v108, cchCount2k);
        if ( v14 < 0 )
          goto LABEL_113;
        cchCount2l = &v107;
        v14 = StructuredQuery1::WriteRanking(980, 990, 2, v107, v108);
        if ( v14 < 0 )
          goto LABEL_113;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl)
          && !*(_DWORD *)(a1 + 96) )
        {
          ((void (__fastcall *)(_QWORD, _QWORD))std::wstring::wstring)(v120, (LARGE_INTEGER)pvar.hVal.QuadPart);
          v76 = *(_QWORD *)(a1 + 72);
          v77 = *(_QWORD *)(a1 + 80);
          while ( 1 )
          {
            if ( v76 == v77 )
            {
              std::wstring::_Tidy_deallocate(v120);
              goto LABEL_182;
            }
            v78 = StructuredQuery1::WriteExternalSearchContains(
                    (_DWORD)v107,
                    v108,
                    (unsigned int)&v107,
                    (unsigned int)&v108,
                    (__int64)v120,
                    v76);
            v79 = v78;
            if ( v78 < 0 )
              break;
            v76 += 32;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x15AA,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\structuredquery\\sqlgenerator\\generatesql.cpp",
            (const char *)(unsigned int)v78,
            lpString2h);
          std::wstring::_Tidy_deallocate(v120);
          v14 = v79;
          goto LABEL_73;
        }
LABEL_182:
        v80 = StringCchCopyExW(v107, v108, L")", &v107, &v108, (unsigned int)cchCount2l);
      }
      else
      {
LABEL_184:
        v81 = StructuredQuery1::ConditionGroupManager::GetLCID(v69, a4);
        v82 = StructuredQuery1::LocaleForProperty(&v119, v81);
        LOBYTE(lpString2) = 1;
        v80 = StructuredQuery1::SqlGenerator::WriteFullText(
                a1,
                v107,
                v108,
                0,
                lpString2,
                1,
                v82,
                a9,
                a6,
                a7,
                &v119,
                v18,
                &hVal,
                1,
                a8,
                L" AND ",
                &v107,
                &v108);
      }
      v14 = v80;
      goto LABEL_113;
    }
    if ( *(_DWORD *)(a1 + 96) )
      goto LABEL_39;
    pv = 0;
    if ( (int)StructuredQuery1::TryGetSemanticSearchParameters((StructuredQuery1 *)a4, (struct ICondition *)&pv, v54) < 0 )
      goto LABEL_146;
    v55 = (StructuredQuery1::ConditionGroupManager *)pv;
    if ( !pv )
      goto LABEL_146;
    v111 = 0;
    v25 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)pv + 32LL))(pv, &v111);
    v14 = v25;
    if ( v25 < 0 )
    {
      v26 = 5274;
      goto LABEL_155;
    }
    v110 = 0;
    v25 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)pv + 40LL))(pv, &v110);
    v14 = v25;
    if ( v25 < 0 )
    {
      v26 = 5276;
      goto LABEL_155;
    }
    v57 = StructuredQuery1::ConditionGroupManager::GetLCID(v56, a4);
    v58 = StructuredQuery1::LocaleForProperty(&v119, v57);
    if ( v111 )
    {
      v14 = StringCchCopyExW(v107, v108, L"(", &v107, &v108, cchCount2);
      if ( v14 < 0 )
        goto LABEL_113;
      LOBYTE(v60) = 0;
      v61 = v111;
      if ( (v111 & 1) != 0 )
      {
        LOBYTE(lpString2e) = v110 <= 1;
        LOBYTE(v60) = 1;
        v14 = StructuredQuery1::SqlGenerator::WriteFullText(
                a1,
                v107,
                v108,
                v60,
                lpString2e,
                v110 <= 1,
                v58,
                a9,
                a6,
                a7,
                &v119,
                v18,
                &hVal,
                1,
                a8,
                L" AND ",
                &v107,
                &v108);
        if ( v14 < 0 )
          goto LABEL_113;
        LOBYTE(v60) = 1;
        v61 = v111;
      }
      if ( (v61 & 2) != 0 )
      {
        LOBYTE(cchCount2g) = 1;
        v14 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))StructuredQuery1::SqlGenerator::WriteSemanticSearchContains)(
                v59,
                v107,
                v108,
                v60,
                (LARGE_INTEGER)pvar.hVal.QuadPart);
        if ( v14 < 0 )
          goto LABEL_113;
        LOBYTE(v60) = 1;
        v61 = v111;
      }
      if ( (v61 & 4) != 0 )
      {
        LOBYTE(cchCount2g) = 0;
        v14 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))StructuredQuery1::SqlGenerator::WriteSemanticSearchContains)(
                v59,
                v107,
                v108,
                v60,
                (LARGE_INTEGER)pvar.hVal.QuadPart);
        if ( v14 < 0 )
          goto LABEL_113;
      }
      v14 = StringCchCopyExW(v107, v108, L")", &v107, &v108, cchCount2g);
      if ( v14 >= 0 )
        v14 = StructuredQuery1::WriteMergeStrategy(v107, v108, (unsigned int)v110, &v107, &v108);
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54310796>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54310796>::GetImpl'::`2'::impl) )
        goto LABEL_113;
      if ( v14 < 0 )
        goto LABEL_113;
      v14 = StringCchCopyExW(v107, v108, L")", &v107, &v108, cchCount2h);
      if ( v14 < 0 )
        goto LABEL_113;
      cchCount2i = &v107;
      v14 = StructuredQuery1::WriteRanking(980, 990, 2, v107, v108);
      if ( v14 < 0 )
        goto LABEL_113;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl) )
      {
        ((void (__fastcall *)(_QWORD, _QWORD))std::wstring::wstring)(v120, (LARGE_INTEGER)pvar.hVal.QuadPart);
        v62 = *(_QWORD *)(a1 + 72);
        v63 = *(_QWORD *)(a1 + 80);
        while ( 1 )
        {
          if ( v62 == v63 )
          {
            std::wstring::_Tidy_deallocate(v120);
            goto LABEL_144;
          }
          v64 = StructuredQuery1::WriteExternalSearchContains(
                  (_DWORD)v107,
                  v108,
                  (unsigned int)&v107,
                  (unsigned int)&v108,
                  (__int64)v120,
                  v62);
          v65 = v64;
          if ( v64 < 0 )
            break;
          v62 += 32;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1501,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\structuredquery\\sqlgenerator\\generatesql.cpp",
          (const char *)(unsigned int)v64,
          lpString2f);
        std::wstring::_Tidy_deallocate(v120);
        v14 = v65;
        goto LABEL_73;
      }
LABEL_144:
      v66 = StringCchCopyExW(v107, v108, L")", &v107, &v108, (unsigned int)cchCount2i);
    }
    else
    {
LABEL_146:
      v67 = StructuredQuery1::ConditionGroupManager::GetLCID(v55, a4);
      v68 = StructuredQuery1::LocaleForProperty(&v119, v67);
      LOBYTE(lpString2) = 1;
      v66 = StructuredQuery1::SqlGenerator::WriteFullText(
              a1,
              v107,
              v108,
              0,
              lpString2,
              1,
              v68,
              a9,
              a6,
              a7,
              &v119,
              v18,
              &hVal,
              1,
              a8,
              L" AND ",
              &v107,
              &v108);
    }
    v14 = v66;
    goto LABEL_113;
  }
  if ( !operator==((__int64)&v119, (__int64)&PKEY_FullText) )
    goto LABEL_39;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl'::`2'::impl) )
  {
    pv = 0;
    if ( (int)StructuredQuery1::TryGetSemanticSearchParameters((StructuredQuery1 *)a4, (struct ICondition *)&pv, v23) < 0 )
      goto LABEL_111;
    v40 = (StructuredQuery1::ConditionGroupManager *)pv;
    if ( !pv )
      goto LABEL_111;
    v111 = 0;
    v25 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)pv + 32LL))(pv, &v111);
    v14 = v25;
    if ( v25 < 0 )
    {
      v26 = 5078;
      goto LABEL_155;
    }
    v110 = 0;
    v25 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)pv + 40LL))(pv, &v110);
    v14 = v25;
    if ( v25 < 0 )
    {
      v26 = 5080;
      goto LABEL_155;
    }
    v42 = StructuredQuery1::ConditionGroupManager::GetLCID(v41, a4);
    v43 = StructuredQuery1::LocaleForProperty(&v119, v42);
    if ( v111 )
    {
      v14 = StringCchCopyExW(v107, v108, L"(", &v107, &v108, cchCount2);
      if ( v14 < 0 )
        goto LABEL_113;
      LOBYTE(v45) = 0;
      v46 = v111;
      if ( (v111 & 1) != 0 )
      {
        LOBYTE(lpString2c) = v110 <= 1;
        LOBYTE(v45) = 1;
        v14 = StructuredQuery1::SqlGenerator::WriteFullText(
                a1,
                v107,
                v108,
                v45,
                lpString2c,
                v110 <= 1,
                v43,
                a9,
                a6,
                a7,
                &v119,
                v18,
                &hVal,
                1,
                a8,
                L" AND ",
                &v107,
                &v108);
        if ( v14 < 0 )
          goto LABEL_113;
        LOBYTE(v45) = 1;
        v46 = v111;
      }
      if ( (v46 & 2) != 0 && !*(_DWORD *)(a1 + 96) )
      {
        LOBYTE(cchCount2d) = 1;
        v14 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))StructuredQuery1::SqlGenerator::WriteSemanticSearchContains)(
                v44,
                v107,
                v108,
                v45,
                (LARGE_INTEGER)pvar.hVal.QuadPart);
        if ( v14 < 0 )
          goto LABEL_113;
        LOBYTE(v45) = 1;
        v46 = v111;
      }
      if ( (v46 & 4) != 0 && !*(_DWORD *)(a1 + 96) )
      {
        LOBYTE(cchCount2d) = 0;
        v14 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))StructuredQuery1::SqlGenerator::WriteSemanticSearchContains)(
                v44,
                v107,
                v108,
                v45,
                (LARGE_INTEGER)pvar.hVal.QuadPart);
      }
      if ( v14 < 0 )
        goto LABEL_113;
      v14 = StringCchCopyExW(v107, v108, L")", &v107, &v108, cchCount2d);
      if ( v14 >= 0 )
        v14 = StructuredQuery1::WriteMergeStrategy(v107, v108, (unsigned int)v110, &v107, &v108);
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54310796>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54310796>::GetImpl'::`2'::impl) )
        goto LABEL_113;
      if ( v14 < 0 )
        goto LABEL_113;
      v14 = StringCchCopyExW(v107, v108, L")", &v107, &v108, cchCount2e);
      if ( v14 < 0 )
        goto LABEL_113;
      cchCount2f = &v107;
      v14 = StructuredQuery1::WriteRanking(980, 990, 2, v107, v108);
      if ( v14 < 0 )
        goto LABEL_113;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl)
        && !*(_DWORD *)(a1 + 96) )
      {
        ((void (__fastcall *)(_QWORD, _QWORD))std::wstring::wstring)(v120, (LARGE_INTEGER)pvar.hVal.QuadPart);
        v47 = *(_QWORD *)(a1 + 72);
        v48 = *(_QWORD *)(a1 + 80);
        while ( 1 )
        {
          if ( v47 == v48 )
          {
            std::wstring::_Tidy_deallocate(v120);
            goto LABEL_109;
          }
          v49 = StructuredQuery1::WriteExternalSearchContains(
                  (_DWORD)v107,
                  v108,
                  (unsigned int)&v107,
                  (unsigned int)&v108,
                  (__int64)v120,
                  v47);
          v50 = v49;
          if ( v49 < 0 )
            break;
          v47 += 32;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x143F,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\structuredquery\\sqlgenerator\\generatesql.cpp",
          (const char *)(unsigned int)v49,
          lpString2d);
        std::wstring::_Tidy_deallocate(v120);
        v14 = v50;
        goto LABEL_73;
      }
LABEL_109:
      v51 = StringCchCopyExW(v107, v108, L")", &v107, &v108, (unsigned int)cchCount2f);
    }
    else
    {
LABEL_111:
      v52 = StructuredQuery1::ConditionGroupManager::GetLCID(v40, a4);
      v53 = StructuredQuery1::LocaleForProperty(&v119, v52);
      LOBYTE(lpString2) = 1;
      v51 = StructuredQuery1::SqlGenerator::WriteFullText(
              a1,
              v107,
              v108,
              0,
              lpString2,
              1,
              v53,
              a9,
              a6,
              a7,
              &v119,
              v18,
              &hVal,
              1,
              a8,
              L" AND ",
              &v107,
              &v108);
    }
    v14 = v51;
    goto LABEL_113;
  }
  if ( *(_DWORD *)(a1 + 96) )
    goto LABEL_39;
  pv = 0;
  if ( (int)StructuredQuery1::TryGetSemanticSearchParameters((StructuredQuery1 *)a4, (struct ICondition *)&pv, v23) < 0
    || (v24 = (StructuredQuery1::ConditionGroupManager *)pv) == 0 )
  {
LABEL_74:
    v38 = StructuredQuery1::ConditionGroupManager::GetLCID(v24, a4);
    v39 = StructuredQuery1::LocaleForProperty(&v119, v38);
    LOBYTE(lpString2) = 1;
    v37 = StructuredQuery1::SqlGenerator::WriteFullText(
            a1,
            v107,
            v108,
            0,
            lpString2,
            1,
            v39,
            a9,
            a6,
            a7,
            &v119,
            v18,
            &hVal,
            1,
            a8,
            L" AND ",
            &v107,
            &v108);
LABEL_75:
    v14 = v37;
    goto LABEL_113;
  }
  v111 = 0;
  v25 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)pv + 32LL))(pv, &v111);
  v14 = v25;
  if ( v25 >= 0 )
  {
    v110 = 0;
    v25 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)pv + 40LL))(pv, &v110);
    v14 = v25;
    if ( v25 < 0 )
    {
      v26 = 4913;
      goto LABEL_155;
    }
    v28 = StructuredQuery1::ConditionGroupManager::GetLCID(v27, a4);
    v29 = StructuredQuery1::LocaleForProperty(&v119, v28);
    if ( v111 )
    {
      v14 = StringCchCopyExW(v107, v108, L"(", &v107, &v108, cchCount2);
      if ( v14 >= 0 )
      {
        LOBYTE(v31) = 0;
        v32 = v111;
        if ( (v111 & 1) != 0 )
        {
          LOBYTE(lpString2a) = v110 <= 1;
          LOBYTE(v31) = 1;
          v14 = StructuredQuery1::SqlGenerator::WriteFullText(
                  a1,
                  v107,
                  v108,
                  v31,
                  lpString2a,
                  v110 <= 1,
                  v29,
                  a9,
                  a6,
                  a7,
                  &v119,
                  v18,
                  &hVal,
                  1,
                  a8,
                  L" AND ",
                  &v107,
                  &v108);
          if ( v14 < 0 )
            goto LABEL_113;
          LOBYTE(v31) = 1;
          v32 = v111;
        }
        if ( (v32 & 2) == 0 )
        {
LABEL_57:
          if ( (v32 & 4) != 0 )
          {
            LOBYTE(cchCount2a) = 0;
            v14 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))StructuredQuery1::SqlGenerator::WriteSemanticSearchContains)(
                    v30,
                    v107,
                    v108,
                    v31,
                    (LARGE_INTEGER)pvar.hVal.QuadPart);
            if ( v14 < 0 )
              goto LABEL_113;
          }
          v14 = StringCchCopyExW(v107, v108, L")", &v107, &v108, cchCount2a);
          if ( v14 >= 0 )
            v14 = StructuredQuery1::WriteMergeStrategy(v107, v108, (unsigned int)v110, &v107, &v108);
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54310796>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54310796>::GetImpl'::`2'::impl) )
            goto LABEL_113;
          if ( v14 < 0 )
            goto LABEL_113;
          v14 = StringCchCopyExW(v107, v108, L")", &v107, &v108, cchCount2b);
          if ( v14 < 0 )
            goto LABEL_113;
          cchCount2c = &v107;
          v14 = StructuredQuery1::WriteRanking(980, 990, 2, v107, v108);
          if ( v14 < 0 )
            goto LABEL_113;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl) )
          {
            ((void (__fastcall *)(_QWORD, _QWORD))std::wstring::wstring)(v120, (LARGE_INTEGER)pvar.hVal.QuadPart);
            v33 = *(_QWORD *)(a1 + 72);
            v34 = *(_QWORD *)(a1 + 80);
            while ( 1 )
            {
              if ( v33 == v34 )
              {
                std::wstring::_Tidy_deallocate(v120);
                goto LABEL_71;
              }
              v35 = StructuredQuery1::WriteExternalSearchContains(
                      (_DWORD)v107,
                      v108,
                      (unsigned int)&v107,
                      (unsigned int)&v108,
                      (__int64)v120,
                      v33);
              v36 = v35;
              if ( v35 < 0 )
                break;
              v33 += 32;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1396,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\structuredquery\\sqlgenerator\\generatesql.cpp",
              (const char *)(unsigned int)v35,
              lpString2b);
            std::wstring::_Tidy_deallocate(v120);
            v14 = v36;
            goto LABEL_73;
          }
LABEL_71:
          v37 = StringCchCopyExW(v107, v108, L")", &v107, &v108, (unsigned int)cchCount2c);
          goto LABEL_75;
        }
        LOBYTE(cchCount2a) = 1;
        v14 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))StructuredQuery1::SqlGenerator::WriteSemanticSearchContains)(
                v30,
                v107,
                v108,
                v31,
                (LARGE_INTEGER)pvar.hVal.QuadPart);
        if ( v14 >= 0 )
        {
          LOBYTE(v31) = 1;
          v32 = v111;
          goto LABEL_57;
        }
      }
LABEL_113:
      wil::com_ptr_t<IXMLDOMNamedNodeMap,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNamedNodeMap,wil::err_exception_policy>((__int64 *)&pv);
      goto LABEL_192;
    }
    goto LABEL_74;
  }
  v26 = 4911;
LABEL_155:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v26,
    (unsigned int)"onecoreuap\\base\\appmodel\\search\\structuredquery\\sqlgenerator\\generatesql.cpp",
    (const char *)(unsigned int)v25,
    lpString2);
LABEL_73:
  wil::com_ptr_t<IXMLDOMNamedNodeMap,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNamedNodeMap,wil::err_exception_policy>((__int64 *)&pv);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18004a374  push    rbp
0x18004a376  push    rbx
0x18004a377  push    rsi
0x18004a378  push    rdi
0x18004a379  push    r12
0x18004a37b  push    r13
0x18004a37d  push    r14
0x18004a37f  push    r15
0x18004a381  lea     rbp, [rsp-38h]
0x18004a386  sub     rsp, 148h
0x18004a38d  mov     rax, cs:__security_cookie
0x18004a394  xor     rax, rsp
0x18004a397  mov     [rbp+70h+var_50], rax
0x18004a39b  mov     rdi, r9
0x18004a39e  mov     rsi, rcx
0x18004a3a1  mov     [rbp+70h+var_F0], rdx
0x18004a3a5  mov     [rbp+70h+var_E8], r8
0x18004a3a9  mov     r12, [rbp+70h+arg_38]
0x18004a3b0  mov     r13, [rbp+70h+arg_48]
0x18004a3b7  mov     r14, [rbp+70h+arg_50]
0x18004a3be  mov     [rbp+70h+var_90], r14
0x18004a3c2  xorps   xmm0, xmm0
0x18004a3c5  xor     eax, eax
0x18004a3c7  movups  xmmword ptr [rbp+70h+var_88.fmtid.Data1], xmm0
0x18004a3cb  mov     [rbp+70h+var_88.pid], eax
0x18004a3ce  xor     r15d, r15d
0x18004a3d1  mov     dword ptr [rbp+70h+var_A0], r15d
0x18004a3d5  movups  xmmword ptr [rbp+70h+pvar], xmm0
0x18004a3d9  mov     [rbp+70h+var_B8], rax
0x18004a3dd  mov     rax, [r9]
0x18004a3e0  lea     r9, [rbp+70h+pvar]
0x18004a3e4  lea     r8, [rbp+70h+var_A0]
0x18004a3e8  lea     rdx, [rbp+70h+var_88]
0x18004a3ec  mov     rcx, rdi
0x18004a3ef  mov     rax, [rax+80h]
0x18004a3f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a3fb  mov     ebx, eax
0x18004a3fd  test    eax, eax
0x18004a3ff  js      loc_18004BB5B
0x18004a405  mov     [rbp+70h+lpString1], r15
0x18004a409  mov     rax, [rdi]
0x18004a40c  lea     rdx, [rbp+70h+lpString1]
0x18004a410  mov     rcx, rdi
0x18004a413  mov     rax, [rax+58h]
0x18004a417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a41c  mov     ebx, eax
0x18004a41e  test    eax, eax
0x18004a420  js      loc_18004BB51
0x18004a426  mov     [rbp+70h+var_E0], r15b
0x18004a42a  mov     [rbp+70h+pv], r15
0x18004a42e  lea     rax, [rbp+70h+pv]
0x18004a432  mov     [rsp+180h+lpString2], rax; wchar_t **
0x18004a437  lea     r9, [rbp+70h+var_E0]; bool *
0x18004a43b  mov     r8, r12; struct StructuredQuery1::VirtualPropertyMap *
0x18004a43e  lea     rdx, [rbp+70h+var_88]; struct _tagpropertykey *
0x18004a442  call    ?DetermineProperty@SqlGenerator@StructuredQuery1@@AEAAJAEBU_tagpropertykey@@PEAVVirtualPropertyMap@2@PEA_NPEAPEA_W@Z; StructuredQuery1::SqlGenerator::DetermineProperty(_tagpropertykey const &,StructuredQuery1::VirtualPropertyMap *,bool *,wchar_t * *)
0x18004a447  mov     ebx, eax
0x18004a449  test    eax, eax
0x18004a44b  js      loc_18004BB47
0x18004a451  or      ecx, 0FFFFFFFFh
0x18004a454  mov     [rsp+180h+cchCount2], ecx; unsigned int
0x18004a458  lea     rax, aSystemStructur_10; "System.StructuredQueryType.SortKeyDescr"...
0x18004a45f  mov     [rsp+180h+lpString2], rax; int
0x18004a464  mov     r9d, ecx; cchCount1
0x18004a467  mov     r8, [rbp+70h+lpString1]; lpString1
0x18004a46b  xor     edx, edx; dwCmpFlags
0x18004a46d  lea     ecx, [rdx+7Fh]; Locale
0x18004a470  call    cs:__imp_CompareStringW
0x18004a476  cmp     eax, 2
0x18004a479  setz    bl
0x18004a47c  mov     ecx, dword ptr [rbp+70h+var_A0]; this
0x18004a47f  mov     r14, [rbp+70h+pv]
0x18004a483  cmp     ecx, 7
0x18004a486  jg      loc_18004A66F
0x18004a48c  jz      loc_18004A637
0x18004a492  test    ecx, ecx
0x18004a494  jz      loc_18004A62D
0x18004a49a  sub     ecx, 1
0x18004a49d  jz      loc_18004A5FA
0x18004a4a3  sub     ecx, 1
0x18004a4a6  jz      loc_18004A5C7
0x18004a4ac  sub     ecx, 1
0x18004a4af  jz      loc_18004A594
0x18004a4b5  sub     ecx, 1
0x18004a4b8  jz      loc_18004A561
0x18004a4be  sub     ecx, 1; this
0x18004a4c1  jz      short loc_18004A531
0x18004a4c3  cmp     ecx, 1
0x18004a4c6  jnz     loc_18004A6AC
0x18004a4cc  lea     rax, [rbp+70h+var_E8]
0x18004a4d0  mov     [rsp+180h+var_120], rax; unsigned __int64 *
0x18004a4d5  lea     rax, [rbp+70h+var_F0]
0x18004a4d9  mov     [rsp+180h+var_128], rax; wchar_t **
0x18004a4de  lea     rax, [rbp+70h+pvar]
0x18004a4e2  mov     [rsp+180h+var_130], rax; struct tagPROPVARIANT *
0x18004a4e7  lea     rax, asc_1800A0758; "<"
0x18004a4ee  mov     [rsp+180h+var_138], rax; wchar_t *
0x18004a4f3  lea     rax, asc_1800A0768; ">="
0x18004a4fa  mov     [rsp+180h+var_140], rax; wchar_t *
0x18004a4ff  mov     [rsp+180h+var_148], r14; wchar_t *
0x18004a504  mov     al, [rbp+70h+arg_30]
0x18004a50a  mov     byte ptr [rsp+180h+var_150], al; bool
0x18004a50e  movzx   eax, word ptr [rbp+70h+pvar]
0x18004a512  mov     word ptr [rsp+180h+cchCount2], ax; unsigned __int16
0x18004a517  mov     byte ptr [rsp+180h+lpString2], bl; bool
0x18004a51b  mov     r9b, [rbp+70h+var_E0]; bool
0x18004a51f  mov     r8, [rbp+70h+var_E8]; unsigned __int64
0x18004a523  mov     rdx, [rbp+70h+var_F0]; wchar_t *
0x18004a527  call    ?WriteValueComparison@SqlGenerator@StructuredQuery1@@AEAAJPEA_W_K_N2G2PEB_W33AEBUtagPROPVARIANT@@PEAPEA_WPEA_K@Z; StructuredQuery1::SqlGenerator::WriteValueComparison(wchar_t *,unsigned __int64,bool,bool,ushort,bool,wchar_t const *,wchar_t const *,wchar_t const *,tagPROPVARIANT const &,wchar_t * *,unsigned __int64 *)
0x18004a52c  jmp     loc_18004BB38
0x18004a531  lea     rax, [rbp+70h+var_E8]
0x18004a535  mov     [rsp+180h+var_120], rax
0x18004a53a  lea     rax, [rbp+70h+var_F0]
0x18004a53e  mov     [rsp+180h+var_128], rax
0x18004a543  lea     rax, [rbp+70h+pvar]
0x18004a547  mov     [rsp+180h+var_130], rax
0x18004a54c  lea     rax, asc_1800A0764; ">"
0x18004a553  mov     [rsp+180h+var_138], rax
0x18004a558  lea     rax, asc_1800A075C; "<="
0x18004a55f  jmp     short loc_18004A4FA
0x18004a561  lea     rax, [rbp+70h+var_E8]
0x18004a565  mov     [rsp+180h+var_120], rax
0x18004a56a  lea     rax, [rbp+70h+var_F0]
0x18004a56e  mov     [rsp+180h+var_128], rax
0x18004a573  lea     rax, [rbp+70h+pvar]
0x18004a577  mov     [rsp+180h+var_130], rax
0x18004a57c  lea     rax, asc_1800A075C; "<="
0x18004a583  mov     [rsp+180h+var_138], rax
0x18004a588  lea     rax, asc_1800A0764; ">"
0x18004a58f  jmp     loc_18004A4FA
0x18004a594  lea     rax, [rbp+70h+var_E8]
0x18004a598  mov     [rsp+180h+var_120], rax
0x18004a59d  lea     rax, [rbp+70h+var_F0]
0x18004a5a1  mov     [rsp+180h+var_128], rax
0x18004a5a6  lea     rax, [rbp+70h+pvar]
0x18004a5aa  mov     [rsp+180h+var_130], rax
0x18004a5af  lea     rax, asc_1800A0768; ">="
0x18004a5b6  mov     [rsp+180h+var_138], rax
0x18004a5bb  lea     rax, asc_1800A0758; "<"
0x18004a5c2  jmp     loc_18004A4FA
0x18004a5c7  lea     rax, [rbp+70h+var_E8]
0x18004a5cb  mov     [rsp+180h+var_120], rax
0x18004a5d0  lea     rax, [rbp+70h+var_F0]
0x18004a5d4  mov     [rsp+180h+var_128], rax
0x18004a5d9  lea     rax, [rbp+70h+pvar]
0x18004a5dd  mov     [rsp+180h+var_130], rax
0x18004a5e2  lea     rax, asc_18009AA0C; "="
0x18004a5e9  mov     [rsp+180h+var_138], rax
0x18004a5ee  lea     rax, asc_18009AA1C; "<>"
0x18004a5f5  jmp     loc_18004A4FA
0x18004a5fa  lea     rax, [rbp+70h+var_E8]
0x18004a5fe  mov     [rsp+180h+var_120], rax
0x18004a603  lea     rax, [rbp+70h+var_F0]
0x18004a607  mov     [rsp+180h+var_128], rax
0x18004a60c  lea     rax, [rbp+70h+pvar]
0x18004a610  mov     [rsp+180h+var_130], rax
0x18004a615  lea     rax, asc_18009AA1C; "<>"
0x18004a61c  mov     [rsp+180h+var_138], rax
0x18004a621  lea     rax, asc_18009AA0C; "="
0x18004a628  jmp     loc_18004A4FA
0x18004a62d  mov     ebx, 8000FFFFh
0x18004a632  jmp     loc_18004BB3A
0x18004a637  lea     rax, [rbp+70h+var_E8]
0x18004a63b  mov     [rsp+180h+var_130], rax
0x18004a640  lea     rax, [rbp+70h+var_F0]
0x18004a644  mov     [rsp+180h+var_138], rax
0x18004a649  lea     rax, [rbp+70h+pvar]
0x18004a64d  mov     [rsp+180h+var_140], rax
0x18004a652  lea     rcx, asc_1800A2D08; "%"
0x18004a659  mov     [rsp+180h+var_148], rcx
0x18004a65e  lea     rax, cchOriginalDestLength
0x18004a665  mov     [rsp+180h+var_150], rax
0x18004a66a  jmp     loc_18004BB19
0x18004a66f  mov     edx, ecx
0x18004a671  sub     edx, 8
0x18004a674  jz      loc_18004BAE6
0x18004a67a  sub     edx, 1
0x18004a67d  jz      loc_18004BABD
0x18004a683  sub     edx, 1
0x18004a686  jz      loc_18004BA84
0x18004a68c  sub     edx, 1
0x18004a68f  jz      loc_18004BA4D
0x18004a695  sub     edx, 1
0x18004a698  jz      loc_18004A7B0
0x18004a69e  sub     edx, 1
0x18004a6a1  jz      loc_18004A7B0
0x18004a6a7  cmp     edx, 1
0x18004a6aa  jz      short loc_18004A6B6
0x18004a6ac  mov     ebx, 80070057h
0x18004a6b1  jmp     loc_18004BB3A
0x18004a6b6  mov     r8, [rbp+70h+lpString1]; lpString1
0x18004a6ba  test    r8, r8
0x18004a6bd  jz      loc_18004A77C
0x18004a6c3  or      edi, 0FFFFFFFFh
0x18004a6c6  mov     [rsp+180h+cchCount2], edi; cchCount2
0x18004a6ca  lea     rax, aSystemStructur_4; "System.StructuredQueryType.AnyBitsSet"
0x18004a6d1  mov     [rsp+180h+lpString2], rax; lpString2
0x18004a6d6  mov     r9d, edi; cchCount1
0x18004a6d9  xor     edx, edx; dwCmpFlags
0x18004a6db  lea     esi, [rdx+7Fh]
0x18004a6de  mov     ecx, esi; Locale
0x18004a6e0  call    cs:__imp_CompareStringW
0x18004a6e6  cmp     eax, 2
0x18004a6e9  jnz     short loc_18004A71E
0x18004a6eb  lea     rax, [rbp+70h+var_E8]
0x18004a6ef  mov     [rsp+180h+var_120], rax
0x18004a6f4  lea     rax, [rbp+70h+var_F0]
0x18004a6f8  mov     [rsp+180h+var_128], rax
0x18004a6fd  lea     rax, [rbp+70h+pvar]
0x18004a701  mov     [rsp+180h+var_130], rax
0x18004a706  lea     rax, aAnyBitwise_0; "<> ANY BITWISE"
0x18004a70d  mov     [rsp+180h+var_138], rax
0x18004a712  lea     rax, aAnyBitwise; "= ANY BITWISE"
0x18004a719  jmp     loc_18004A4FA
0x18004a71e  mov     r8, [rbp+70h+lpString1]; lpString1
0x18004a722  test    r8, r8
0x18004a725  jz      short loc_18004A77C
0x18004a727  mov     [rsp+180h+cchCount2], edi; cchCount2
0x18004a72b  lea     rax, aSystemStructur_9; "System.StructuredQueryType.AllBitsSet"
0x18004a732  mov     [rsp+180h+lpString2], rax; lpString2
0x18004a737  mov     r9d, edi; cchCount1
0x18004a73a  xor     edx, edx; dwCmpFlags
0x18004a73c  mov     ecx, esi; Locale
0x18004a73e  call    cs:__imp_CompareStringW
0x18004a744  cmp     eax, 2
0x18004a747  jnz     short loc_18004A77C
0x18004a749  lea     rax, [rbp+70h+var_E8]
0x18004a74d  mov     [rsp+180h+var_120], rax
0x18004a752  lea     rax, [rbp+70h+var_F0]
0x18004a756  mov     [rsp+180h+var_128], rax
0x18004a75b  lea     rax, [rbp+70h+pvar]
0x18004a75f  mov     [rsp+180h+var_130], rax
0x18004a764  lea     rax, aAllBitwise; "<> ALL BITWISE"
0x18004a76b  mov     [rsp+180h+var_138], rax
0x18004a770  lea     rax, aAllBitwise_0; "= ALL BITWISE"
0x18004a777  jmp     loc_18004A4FA
0x18004a77c  lea     rax, [rbp+70h+var_E8]
0x18004a780  mov     [rsp+180h+var_150], rax; unsigned __int64 *
0x18004a785  lea     rax, [rbp+70h+var_F0]
0x18004a789  mov     qword ptr [rsp+180h+cchCount2], rax; wchar_t **
0x18004a78e  lea     rax, [rbp+70h+pvar]
0x18004a792  mov     [rsp+180h+lpString2], rax; struct tagPROPVARIANT *
0x18004a797  mov     r9b, [rbp+70h+arg_30]; bool
0x18004a79e  mov     r8, [rbp+70h+var_E8]; unsigned __int64
0x18004a7a2  mov     rdx, [rbp+70h+var_F0]; wchar_t *
0x18004a7a6  call    ?WriteApplicationSpecific@SqlGenerator@StructuredQuery1@@AEAAJPEA_W_K_NAEBUtagPROPVARIANT@@PEAPEA_WPEA_K@Z; StructuredQuery1::SqlGenerator::WriteApplicationSpecific(wchar_t *,unsigned __int64,bool,tagPROPVARIANT const &,wchar_t * *,unsigned __int64 *)
0x18004a7ab  jmp     loc_18004BB38
0x18004a7b0  mov     rax, [rbp+70h+pvar+8]
0x18004a7b4  mov     [rbp+70h+var_B0], rax
0x18004a7b8  mov     [rbp+70h+var_A8], ecx
0x18004a7bb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FI45262758@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FI45262758@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758> `wil::Feature<__WilFeatureTraits_Feature_FI45262758>::GetImpl(void)'::`2'::impl
0x18004a7c2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FI45262758@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758>::__private_IsEnabled(void)
0x18004a7c7  test    al, al
0x18004a7c9  jz      loc_18004A8BC
0x18004a7cf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60428908@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60428908@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60428908> `wil::Feature<__WilFeatureTraits_Feature_60428908>::GetImpl(void)'::`2'::impl
0x18004a7d6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60428908@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60428908>::__private_IsEnabled(void)
0x18004a7db  test    al, al
0x18004a7dd  jz      loc_18004B1C1
0x18004a7e3  lea     rdx, PKEY_FullText
0x18004a7ea  lea     rcx, [rbp+70h+var_88]
0x18004a7ee  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18004a7f3  test    eax, eax
0x18004a7f5  jnz     loc_18004A89E
0x18004a7fb  mov     rdx, rdi; struct ICondition2 *
0x18004a7fe  call    ?GetLCID@ConditionGroupManager@StructuredQuery1@@AEAAKPEAUICondition2@@@Z; StructuredQuery1::ConditionGroupManager::GetLCID(ICondition2 *)
0x18004a803  mov     edx, eax
0x18004a805  lea     rcx, [rbp+70h+var_88]
0x18004a809  call    StructuredQuery1__LocaleForProperty
0x18004a80e  mov     r10d, eax
0x18004a811  lea     rax, [rbp+70h+var_E8]
0x18004a815  mov     [rsp+180h+var_F8], rax
0x18004a81d  lea     rax, [rbp+70h+var_F0]
0x18004a821  mov     [rsp+180h+var_100], rax
0x18004a829  lea     rax, aAnd; " AND "
0x18004a830  mov     [rsp+180h+var_108], rax
0x18004a835  mov     [rsp+180h+var_110], r12
0x18004a83a  mov     edi, 1
0x18004a83f  mov     [rsp+180h+var_118], edi
0x18004a843  lea     rax, [rbp+70h+var_B0]
0x18004a847  mov     [rsp+180h+var_120], rax
0x18004a84c  mov     [rsp+180h+var_128], r14
0x18004a851  lea     rax, [rbp+70h+var_88]
0x18004a855  mov     [rsp+180h+var_130], rax
0x18004a85a  mov     al, [rbp+70h+arg_30]
0x18004a860  mov     byte ptr [rsp+180h+var_138], al
0x18004a864  mov     eax, [rbp+70h+arg_28]
0x18004a86a  mov     dword ptr [rsp+180h+var_140], eax
0x18004a86e  mov     al, [rbp+70h+arg_40]
0x18004a874  mov     byte ptr [rsp+180h+var_148], al
0x18004a878  mov     dword ptr [rsp+180h+var_150], r10d
0x18004a87d  mov     [rsp+180h+cchCount2], edi
0x18004a881  mov     byte ptr [rsp+180h+lpString2], dil
0x18004a886  xor     r9d, r9d
0x18004a889  mov     r8, [rbp+70h+var_E8]
0x18004a88d  mov     rdx, [rbp+70h+var_F0]
0x18004a891  mov     rcx, rsi
0x18004a894  call    ?WriteFullText@SqlGenerator@StructuredQuery1@@AEAAJPEA_W_K_N2W4RANKING_COERCION@2@K2W4SQL_GENERATION_OPTIONS@@2AEBU_tagpropertykey@@PEB_WPEBUPHRASE_QUERY_RECORD@2@KPEAVVirtualPropertyMap@2@6PEAPEA_WPEA_K@Z; StructuredQuery1::SqlGenerator::WriteFullText(wchar_t *,unsigned __int64,bool,bool,StructuredQuery1::RANKING_COERCION,ulong,bool,SQL_GENERATION_OPTIONS,bool,_tagpropertykey const &,wchar_t const *,StructuredQuery1::PHRASE_QUERY_RECORD const *,ulong,StructuredQuery1::VirtualPropertyMap *,wchar_t const *,wchar_t * *,unsigned __int64 *)
0x18004a899  jmp     loc_18004BB38
0x18004a89e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60157349@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60157349@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349> `wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl(void)'::`2'::impl
0x18004a8a5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60157349@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(void)
  ... truncated ...
```
