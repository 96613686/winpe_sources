# StructuredQuery1::SqlGenerator::WriteFullText(wchar_t *,unsigned __int64,bool,bool,StructuredQuery1::RANKING_COERCION,ulong,bool,SQL_GENERATION_OPTIONS,bool,_tagpropertykey const &,wchar_t const *,StructuredQuery1::PHRASE_QUERY_RECORD const *,ulong,StructuredQuery1::VirtualPropertyMap *,wchar_t const *,wchar_t * *,unsigned __int64 *)

- ea: `0x1800810fc`
- end: `0x1800827f0`
- name: `?WriteFullText@SqlGenerator@StructuredQuery1@@AEAAJPEA_W_K_N2W4RANKING_COERCION@2@K2W4SQL_GENERATION_OPTIONS@@2AEBU_tagpropertykey@@PEB_WPEBUPHRASE_QUERY_RECORD@2@KPEAVVirtualPropertyMap@2@6PEAPEA_WPEA_K@Z`
- size: `5876`
- prototype: `int __high(wchar_t *, unsigned __int64, bool, bool, enum StructuredQuery1::RANKING_COERCION, unsigned int, bool, enum SQL_GENERATION_OPTIONS, bool, const struct _tagpropertykey *, const wchar_t *, const struct StructuredQuery1::PHRASE_QUERY_RECORD *, unsigned int, struct StructuredQuery1::VirtualPropertyMap *, const wchar_t *, wchar_t **, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `30`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004a374`
- `0x18004bb94`
- `0x18007eba0`

## callees

- `0x180010904`
- `0x180024040`
- `0x18002a220`
- `0x18002cc30`
- `0x18002e5c0`
- `0x18002fc34`
- `0x180034e80`
- `0x180036b7c`
- `0x18004146c`
- `0x1800576e8`
- `0x18005ac20`
- `0x18005c3d4`
- `0x18005c9d0`
- `0x18005ca18`
- `0x18005daf0`
- `0x18006749c`
- `0x180080e98`
- `0x180080f54`
- `0x1800810fc`
- `0x180082d70`
- `0x180082e9c`
- `0x180083034`
- `0x180083168`
- `0x1800833a4`
- `0x180083758`
- `0x1800837d4`
- `0x180083850`
- `0x18008388c`
- `0x180083904`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081798`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081e60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082580`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081798`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081e60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082580`

## string_xrefs

- `0x1800813b3`: `System.Comment`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StructuredQuery1::SqlGenerator::WriteFullText(
        __int64 a1,
        wchar_t *a2,
        wchar_t *a3,
        char a4,
        char a5,
        unsigned int a6,
        unsigned int a7,
        char a8,
        unsigned int a9,
        char a10,
        __int64 a11,
        wchar_t *a12,
        const wchar_t **a13,
        unsigned int a14,
        StructuredQuery1::VirtualPropertyMap *a15,
        wchar_t *a16,
        wchar_t **a17,
        wchar_t **a18)
{
  wchar_t *v18; // r10
  int ConditionPropertyNameFromKey; // ebx
  int v21; // r8d
  int v22; // r10d
  unsigned int v23; // edx
  __int64 v24; // r8
  unsigned int v25; // r9d
  char v26; // r10
  int v27; // edi
  __int64 v28; // rcx
  StructuredQuery1::VirtualPropertyMap *v29; // rcx
  unsigned int v30; // edi
  int v31; // r15d
  int v32; // eax
  int v33; // eax
  unsigned int v34; // r12d
  wchar_t **v35; // r8
  wchar_t *v36; // rcx
  bool v37; // bl
  int v38; // eax
  signed int v39; // edi
  int v40; // eax
  char IsEnabled; // al
  __int64 v42; // rcx
  __int64 v43; // r8
  int v44; // eax
  char v45; // r9
  __int64 v46; // r10
  int v47; // edx
  int v48; // eax
  int v49; // eax
  __int64 v50; // r10
  int v51; // edx
  int Alias; // eax
  int v53; // eax
  unsigned int v54; // edi
  void *v55; // r12
  int v56; // eax
  int v57; // ebx
  int v58; // eax
  int v59; // eax
  int v60; // ebx
  int v61; // eax
  int v62; // eax
  char v63; // r9
  wchar_t *v64; // r12
  int v65; // eax
  int v66; // eax
  int v67; // ebx
  bool v68; // zf
  int v69; // eax
  char v70; // al
  int v71; // r12d
  int v72; // eax
  char v73; // r9
  int v74; // eax
  int v75; // ebx
  char v76; // al
  int v77; // ebx
  bool v78; // zf
  wchar_t *v79; // r12
  int v80; // eax
  char v81; // al
  char v82; // al
  char v83; // r15
  unsigned int v84; // eax
  int v85; // r11d
  __int64 v86; // rcx
  int v87; // eax
  unsigned int v88; // eax
  wchar_t *v89; // r10
  STRSAFE_LPWSTR v90; // r11
  __int64 v91; // rbx
  __int64 v92; // rsi
  int v93; // edi
  unsigned int v95; // ebx
  __int64 v96; // rdx
  __int64 v97; // rcx
  int v98; // eax
  char v99; // r8
  int v100; // edi
  int v101; // eax
  int v102; // eax
  int v103; // [rsp+20h] [rbp-E0h]
  unsigned __int64 *v104; // [rsp+28h] [rbp-D8h]
  unsigned int v105; // [rsp+28h] [rbp-D8h]
  unsigned __int64 *v106; // [rsp+28h] [rbp-D8h]
  unsigned __int64 *v107; // [rsp+28h] [rbp-D8h]
  unsigned __int64 *v108; // [rsp+28h] [rbp-D8h]
  unsigned __int64 *v109; // [rsp+28h] [rbp-D8h]
  unsigned int v110; // [rsp+28h] [rbp-D8h]
  int v111; // [rsp+38h] [rbp-C8h]
  int v112; // [rsp+38h] [rbp-C8h]
  int v113; // [rsp+38h] [rbp-C8h]
  int v114; // [rsp+38h] [rbp-C8h]
  int v115; // [rsp+40h] [rbp-C0h]
  int v116; // [rsp+40h] [rbp-C0h]
  int v117; // [rsp+40h] [rbp-C0h]
  int v118; // [rsp+70h] [rbp-90h]
  wchar_t **v119; // [rsp+70h] [rbp-90h]
  wchar_t *v120; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *v121; // [rsp+88h] [rbp-78h] BYREF
  char v122; // [rsp+90h] [rbp-70h]
  wchar_t *v123; // [rsp+98h] [rbp-68h]
  struct StructuredQuery1::VIRTUAL_PROPERTY_INFO *v124; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t *v125; // [rsp+A8h] [rbp-58h] BYREF
  int v126; // [rsp+B0h] [rbp-50h]
  int v127; // [rsp+B4h] [rbp-4Ch]
  unsigned int v128; // [rsp+B8h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t *v130; // [rsp+C8h] [rbp-38h] BYREF
  StructuredQuery1::VirtualPropertyMap *v131; // [rsp+D0h] [rbp-30h]
  wchar_t **v132; // [rsp+D8h] [rbp-28h]
  wchar_t **v133; // [rsp+E0h] [rbp-20h]
  struct tagPROPVARIANT propkey; // [rsp+E8h] [rbp-18h] BYREF
  struct tagPROPVARIANT v135; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v122 = a4;
  v18 = a3;
  v120 = a2;
  v121 = a3;
  v125 = a12;
  v131 = a15;
  v123 = a16;
  v132 = a17;
  v133 = a18;
  LOBYTE(a3) = a10;
  ConditionPropertyNameFromKey = StructuredQuery1::WriteNot(
                                   (StructuredQuery1 *)a2,
                                   v18,
                                   (unsigned __int64)a3,
                                   (bool)&v120,
                                   &v121,
                                   v104);
  if ( ConditionPropertyNameFromKey < 0 )
    goto LABEL_213;
  LOBYTE(v22) = 0;
  v127 = v22;
  LOBYTE(v21) = 1;
  v126 = v21;
  v23 = 0;
  if ( a14 )
  {
    do
    {
      v22 = (unsigned __int8)v22;
      if ( LODWORD(a13[2 * v23 + 1]) == 13 )
        v22 = 1;
      v21 = (unsigned __int8)v21;
      if ( LODWORD(a13[2 * v23 + 1]) != 13 )
        v21 = 0;
      ++v23;
    }
    while ( v23 < a14 );
    v127 = v22;
    v126 = v21;
  }
  if ( !operator==(a11, (__int64)&PKEY_FullText) )
  {
    v27 = v25 & 2;
    goto LABEL_198;
  }
  v27 = v25 & 2;
  if ( (v25 & 2) == 0 )
  {
LABEL_198:
    LOBYTE(v24) = v26;
    v95 = StructuredQuery1::TermBehavior(v25, a7, v24);
    v128 = v95;
    v98 = StructuredQuery1::TermBehavior(v97, v96, 0);
    LODWORD(v124) = v98;
    if ( v95 == v98 || !v98 )
    {
      v122 = v99;
    }
    else
    {
      ConditionPropertyNameFromKey = StringCchCopyExW(
                                       v120,
                                       (unsigned __int64)v121,
                                       L"(",
                                       &v120,
                                       (unsigned __int64 *)&v121,
                                       v105);
      v122 = 1;
      if ( ConditionPropertyNameFromKey < 0 )
        goto LABEL_213;
      v95 = v128;
    }
    v100 = v27 != 0 ? 1000 : -1;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl'::`2'::impl) )
      v101 = StructuredQuery1::WriteOneRemoteAwareContainsWithRanking(
               v120,
               v121,
               v125,
               a13,
               a14,
               v100,
               v95,
               0,
               0,
               a6,
               a7,
               a16,
               &v120,
               &v121,
               *(_DWORD *)(a1 + 96) != 0);
    else
      v101 = StructuredQuery1::WriteOneContainsWithRanking(
               v120,
               v121,
               v125,
               a13,
               a14,
               v100,
               v95,
               0,
               0,
               a6,
               a7,
               a16,
               &v120,
               &v121);
    ConditionPropertyNameFromKey = v101;
    if ( v101 >= 0 && v122 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl'::`2'::impl) )
      {
        LOBYTE(v118) = *(_DWORD *)(a1 + 96) != 0;
        LOBYTE(v117) = 1;
        LOBYTE(v114) = 0;
        v102 = StructuredQuery1::WriteOneRemoteAwareContainsWithRanking(
                 v120,
                 v121,
                 v125,
                 a13,
                 a14,
                 v100,
                 (_DWORD)v124,
                 v114,
                 v117,
                 a6,
                 a7,
                 v123,
                 &v120,
                 &v121,
                 v118);
      }
      else
      {
        LOBYTE(v117) = 1;
        LOBYTE(v114) = 0;
        v102 = StructuredQuery1::WriteOneContainsWithRanking(
                 v120,
                 v121,
                 v125,
                 a13,
                 a14,
                 v100,
                 (_DWORD)v124,
                 v114,
                 v117,
                 a6,
                 a7,
                 v123,
                 &v120,
                 &v121);
      }
      ConditionPropertyNameFromKey = v102;
      if ( v102 >= 0 )
        ConditionPropertyNameFromKey = StringCchCopyExW(
                                         v120,
                                         (unsigned __int64)v121,
                                         L")",
                                         &v120,
                                         (unsigned __int64 *)&v121,
                                         v110);
    }
    goto LABEL_213;
  }
  if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_FI45262758>::GetImpl'::`2'::impl)
    || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl'::`2'::impl)
    && *(_DWORD *)(a1 + 96)
    || a5 )
  {
    ConditionPropertyNameFromKey = StringCchCopyExW(
                                     v120,
                                     (unsigned __int64)v121,
                                     L"(",
                                     &v120,
                                     (unsigned __int64 *)&v121,
                                     v105);
  }
  else
  {
    ConditionPropertyNameFromKey = 0;
  }
  if ( ConditionPropertyNameFromKey < 0 )
    goto LABEL_213;
  v128 = 0;
  ConditionPropertyNameFromKey = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(a1 + 8) + 24LL))(
                                   *(_QWORD *)(a1 + 8),
                                   &v128);
  if ( ConditionPropertyNameFromKey < 0 )
    goto LABEL_213;
  v130 = 0;
  ConditionPropertyNameFromKey = _AllocArray<wchar_t,CTCoAllocPolicy>(v28, 1, 0x7800u, (void **)&v130);
  if ( ConditionPropertyNameFromKey < 0 )
    goto LABEL_213;
  v125 = v130;
  v124 = (struct StructuredQuery1::VIRTUAL_PROPERTY_INFO *)30720;
  ConditionPropertyNameFromKey = StringCchCopyExW(v130, 0x7800u, *a13, &v125, (unsigned __int64 *)&v124, v105);
  v30 = 1;
  if ( ConditionPropertyNameFromKey < 0 )
    goto LABEL_196;
  while ( v30 < a14 )
  {
    ConditionPropertyNameFromKey = StringCchCopyExW(
                                     v125,
                                     (unsigned __int64)v124,
                                     L" ",
                                     &v125,
                                     (unsigned __int64 *)&v124,
                                     (unsigned int)v106);
    if ( ConditionPropertyNameFromKey >= 0 )
      ConditionPropertyNameFromKey = StringCchCopyExW(
                                       v125,
                                       (unsigned __int64)v124,
                                       a13[2 * v30],
                                       &v125,
                                       (unsigned __int64 *)&v124,
                                       (unsigned int)v106);
    ++v30;
    if ( ConditionPropertyNameFromKey < 0 )
      goto LABEL_196;
  }
  if ( a8 )
  {
    propkey.vt = 31;
    *(_QWORD *)&propkey.decVal.scale = 0;
    *(_OWORD *)&propkey.decVal.Lo32 = (unsigned __int64)v130;
    ConditionPropertyNameFromKey = StructuredQuery1::SqlGenerator::WriteValueComparison(
                                     (StructuredQuery1::SqlGenerator *)0x1F,
                                     v120,
                                     (unsigned __int64)v121,
                                     0,
                                     0,
                                     0x1Fu,
                                     0,
                                     L"System.Comment",
                                     L"=",
                                     L"<>",
                                     &propkey,
                                     &v120,
                                     (unsigned __int64 *)&v121);
    if ( ConditionPropertyNameFromKey < 0 )
      goto LABEL_196;
    v31 = a6;
    if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_FI45262758>::GetImpl'::`2'::impl)
      || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl'::`2'::impl)
      && *(_DWORD *)(a1 + 96) )
    {
      v32 = StructuredQuery1::WriteRankingAppendix(
              (StructuredQuery1 *)0x3E7,
              (int)v120,
              v121,
              (unsigned __int64)&v120,
              &v121,
              v107);
    }
    else
    {
      v108 = (unsigned __int64 *)&v120;
      v32 = StructuredQuery1::WriteRanking(100, 999, a6, v120, v121);
    }
    ConditionPropertyNameFromKey = v32;
    if ( v32 < 0 )
      goto LABEL_196;
    ConditionPropertyNameFromKey = StringCchCopyExW(
                                     v120,
                                     (unsigned __int64)v121,
                                     L" OR ",
                                     &v120,
                                     (unsigned __int64 *)&v121,
                                     (unsigned int)v108);
    if ( ConditionPropertyNameFromKey < 0 )
      goto LABEL_196;
    propkey.vt = 31;
    propkey.hVal.QuadPart = (LONGLONG)v130;
    ConditionPropertyNameFromKey = StructuredQuery1::SqlGenerator::WriteValueComparison(
                                     (StructuredQuery1::SqlGenerator *)0x1F,
                                     v120,
                                     (unsigned __int64)v121,
                                     1,
                                     0,
                                     0x1Fu,
                                     0,
                                     L"System.HighKeywords",
                                     L"=",
                                     L"<>",
                                     &propkey,
                                     &v120,
                                     (unsigned __int64 *)&v121);
    if ( ConditionPropertyNameFromKey < 0 )
      goto LABEL_196;
    if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_FI45262758>::GetImpl'::`2'::impl)
      || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl'::`2'::impl)
      && *(_DWORD *)(a1 + 96) )
    {
      v33 = StructuredQuery1::WriteRankingAppendix(
              (StructuredQuery1 *)0x3E7,
              (int)v120,
              v121,
              (unsigned __int64)&v120,
              &v121,
              v109);
    }
    else
    {
      v106 = (unsigned __int64 *)&v120;
      v33 = StructuredQuery1::WriteRanking(100, 999, a6, v120, v121);
    }
    ConditionPropertyNameFromKey = v33;
LABEL_64:
    if ( ConditionPropertyNameFromKey < 0 )
      goto LABEL_196;
    if ( a8 )
    {
      v39 = 0;
      while ( (unsigned int)v39 < 0x10 )
      {
        v40 = *((_DWORD *)&off_180097840 + 6 * v39 + 3);
        if ( v40 == 1 || v40 == 2 && (_BYTE)v126 || v40 == 3 && a14 > 1 || v40 == 4 && a14 > 1 && (_BYTE)v127 )
        {
          IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl'::`2'::impl);
          v42 = 0;
          LOBYTE(v43) = BYTE1((&off_180097840)[3 * v39 + 1]);
          if ( IsEnabled )
          {
            if ( !LOBYTE((&off_180097840)[3 * v39 + 1]) )
              v42 = a9;
            v44 = StructuredQuery1::TermBehavior(v42, a7, v43);
            LOBYTE(v118) = v45;
            LOBYTE(v115) = 1;
            LOBYTE(v111) = *(_BYTE *)(v46 + 24LL * v39 + 18);
            v48 = StructuredQuery1::WriteOneRemoteAwareContainsWithRanking(
                    v120,
                    v121,
                    *(_QWORD *)(v46 + 24LL * v39),
                    a13,
                    a14,
                    *(_DWORD *)(v46 + 24LL * v39 + 8),
                    v44,
                    v111,
                    v115,
                    v31,
                    v47,
                    v123,
                    &v120,
                    &v121,
                    v118);
          }
          else
          {
            if ( !LOBYTE((&off_180097840)[3 * v39 + 1]) )
              v42 = a9;
            v49 = StructuredQuery1::TermBehavior(v42, a7, v43);
            LOBYTE(v115) = 1;
            LOBYTE(v111) = *(_BYTE *)(v50 + 24LL * v39 + 18);
            v48 = StructuredQuery1::WriteOneContainsWithRanking(
                    v120,
                    v121,
                    *(_QWORD *)(v50 + 24LL * v39),
                    a13,
                    a14,
                    *(_DWORD *)(v50 + 24LL * v39 + 8),
                    v49,
                    v111,
                    v115,
                    v31,
                    v51,
                    v123,
                    &v120,
                    &v121);
          }
          ConditionPropertyNameFromKey = v48;
        }
        ++v39;
        if ( ConditionPropertyNameFromKey < 0 )
          goto LABEL_196;
      }
      goto LABEL_190;
    }
  }
  else
  {
    v34 = 0;
    v31 = a6;
    while ( v34 < v128 )
    {
      if ( v34 )
        ConditionPropertyNameFromKey = StringCchCopyExW(
                                         v120,
                                         (unsigned __int64)v121,
                                         L" OR ",
                                         &v120,
                                         (unsigned __int64 *)&v121,
                                         (unsigned int)v106);
      if ( ConditionPropertyNameFromKey >= 0 )
      {
        v125 = 0;
        ConditionPropertyNameFromKey = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, wchar_t **))(**(_QWORD **)(a1 + 8) + 32LL))(
                                         *(_QWORD *)(a1 + 8),
                                         v34,
                                         &GUID_6f79d558_3e96_4549_a1d1_7d75d2288814,
                                         &v125);
        if ( ConditionPropertyNameFromKey >= 0 )
        {
          memset(&propkey, 0, 20);
          ConditionPropertyNameFromKey = (*(__int64 (__fastcall **)(wchar_t *, struct tagPROPVARIANT *))(*(_QWORD *)v125 + 24LL))(
                                           v125,
                                           &propkey);
          if ( ConditionPropertyNameFromKey >= 0 )
          {
            pv = 0;
            ConditionPropertyNameFromKey = StructuredQuery1::GetConditionPropertyNameFromKey(
                                             (PROPERTYKEY *)&propkey,
                                             (const struct _tagpropertykey *)&pv,
                                             v35);
            if ( ConditionPropertyNameFromKey >= 0 )
            {
              v135.vt = 31;
              *(_QWORD *)&v135.decVal.scale = 0;
              *(_OWORD *)&v135.decVal.Lo32 = (unsigned __int64)v130;
              v36 = v125;
              v37 = 0;
              if ( v125 )
              {
                LODWORD(v124) = 0;
                if ( (*(int (__fastcall **)(wchar_t *, __int64, struct StructuredQuery1::VIRTUAL_PROPERTY_INFO **))(*(_QWORD *)v125 + 64LL))(
                       v125,
                       1,
                       &v124) >= 0 )
                  v37 = (_DWORD)v124 == 1;
              }
              ConditionPropertyNameFromKey = StructuredQuery1::SqlGenerator::WriteValueComparison(
                                               (StructuredQuery1::SqlGenerator *)v36,
                                               v120,
                                               (unsigned __int64)v121,
                                               v37,
                                               0,
                                               0x1Fu,
                                               0,
                                               (const wchar_t *)pv,
                                               L"=",
                                               L"<>",
                                               &v135,
                                               &v120,
                                               (unsigned __int64 *)&v121);
              if ( ConditionPropertyNameFromKey >= 0 )
              {
                if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_FI45262758>::GetImpl'::`2'::impl)
                  || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl'::`2'::impl)
                  && *(_DWORD *)(a1 + 96)
                  || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54310796>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54310796>::GetImpl'::`2'::impl) )
                {
                  v38 = StructuredQuery1::WriteRankingAppendix(
                          (StructuredQuery1 *)0x3E7,
                          (int)v120,
                          v121,
                          (unsigned __int64)&v120,
                          &v121,
                          v106);
                }
                else
                {
                  v106 = (unsigned __int64 *)&v120;
                  v38 = StructuredQuery1::WriteRanking(100, 999, a6, v120, v121);
                }
                ConditionPropertyNameFromKey = v38;
              }
              CoTaskMemFree(pv);
            }
          }
          (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v125 + 16LL))(v125);
        }
      }
      ++v34;
      if ( ConditionPropertyNameFromKey < 0 )
        goto LABEL_64;
    }
  }
  pv = 0;
  v124 = 0;
  if ( (a9 & 0x40) != 0 )
    Alias = StructuredQuery1::VirtualPropertyMap::LookupVirtualProperty(v131, &PKEY_MOST_RELEVANT_PROPERTIES, &v124);
  else
    Alias = StructuredQuery1::VirtualPropertyMap::GetAlias(v29, &PKEY_MOST_RELEVANT_PROPERTIES, (wchar_t **)&pv);
  ConditionPropertyNameFromKey = Alias;
  if ( Alias >= 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54310796>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54310796>::GetImpl'::`2'::impl) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl'::`2'::impl) )
      {
        v53 = 1;
        if ( *(_DWORD *)(a1 + 96) )
          v53 = v31;
        v31 = v53;
      }
      else
      {
        v31 = 1;
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl'::`2'::impl) )
    {
      if ( !*(_DWORD *)(a1 + 96) )
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_54310796>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54310796>::GetImpl'::`2'::impl);
      v54 = a7;
      v119 = &v121;
      v112 = StructuredQuery1::TermBehavior(0, a7, 0);
      LODWORD(v106) = a14;
      v55 = pv;
      v56 = StructuredQuery1::WriteOneRemoteAwareMostRelevantPropertiesContainsWithRanking(v120, v121, pv, v124, a13);
    }
    else
    {
      v54 = a7;
      v57 = StructuredQuery1::TermBehavior(0, a7, 0);
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_54310796>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54310796>::GetImpl'::`2'::impl);
      v119 = &v121;
      v112 = v57;
      LODWORD(v106) = a14;
      v55 = pv;
      v56 = StructuredQuery1::WriteOneMostRelevantPropertiesContainsWithRanking(v120, v121, pv, v124, a13);
    }
    ConditionPropertyNameFromKey = v56;
    if ( v56 >= 0 )
    {
      if ( !(_BYTE)v126 )
        goto LABEL_109;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl'::`2'::impl) )
      {
        if ( !*(_DWORD *)(a1 + 96) )
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_54310796>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54310796>::GetImpl'::`2'::impl);
        v119 = &v121;
        v112 = 1;
        LODWORD(v106) = a14;
        v58 = StructuredQuery1::WriteOneRemoteAwareMostRelevantPropertiesContainsWithRanking(v120, v121, v55, v124, a13);
      }
      else
      {
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_54310796>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54310796>::GetImpl'::`2'::impl);
        v119 = &v121;
        v112 = 1;
        LODWORD(v106) = a14;
        v58 = StructuredQuery1::WriteOneMostRelevantPropertiesContainsWithRanking(v120, v121, v55, v124, a13);
      }
      ConditionPropertyNameFromKey = v58;
      if ( v58 >= 0 )
      {
LABEL_109:
        if ( a14 > 1 )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl'::`2'::impl) )
          {
            if ( !*(_DWORD *)(a1 + 96) )
              wil::details::FeatureImpl<__WilFeatureTraits_Feature_54310796>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54310796>::GetImpl'::`2'::impl);
            v119 = &v121;
            v112 = StructuredQuery1::TermBehavior(0, v54, 0);
            LODWORD(v106) = a14;
            v59 = StructuredQuery1::WriteOneRemoteAwareMostRelevantPropertiesContainsWithRanking(
                    v120,
                    v121,
                    v55,
                    v124,
                    a13);
          }
          else
          {
            v60 = StructuredQuery1::TermBehavior(0, v54, 0);
            wil::details::FeatureImpl<__WilFeatureTraits_Feature_54310796>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54310796>::GetImpl'::`2'::impl);
            v119 = &v121;
            v112 = v60;
            LODWORD(v106) = a14;
            v59 = StructuredQuery1::WriteOneMostRelevantPropertiesContainsWithRanking(v120, v121, v55, v124, a13);
          }
          ConditionPropertyNameFromKey = v59;
          if ( v59 >= 0 && (_BYTE)v127 )
          {
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl'::`2'::impl) )
            {
              if ( !*(_DWORD *)(a1 + 96) )
                wil::details::FeatureImpl<__WilFeatureTraits_Feature_54310796>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54310796>::GetImpl'::`2'::impl);
              v119 = &v121;
              v112 = 1;
              LODWORD(v106) = a14;
              v61 = StructuredQuery1::WriteOneRemoteAwareMostRelevantPropertiesContainsWithRanking(
                      v120,
                      v121,
                      v55,
                      v124,
                      a13);
            }
            else
            {
              wil::details::FeatureImpl<__WilFeatureTraits_Feature_54310796>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54310796>::GetImpl'::`2'::impl);
              v119 = &v121;
              v112 = 1;
              LODWORD(v106) = a14;
              v61 = StructuredQuery1::WriteOneMostRelevantPropertiesContainsWithRanking(v120, v121, v55, v124, a13);
            }
            ConditionPropertyNameFromKey = v61;
          }
        }
      }
    }
    CoTaskMemFree(v55);
    if ( (*(_BYTE *)(a1 + 60) & 1) != 0 )
    {
LABEL_189:
      if ( ConditionPropertyNameFromKey >= 0 )
      {
LABEL_190:
        if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_FI45262758>::GetImpl'::`2'::impl)
          || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl'::`2'::impl)
          && *(_DWORD *)(a1 + 96)
          || a5 )
        {
          ConditionPropertyNameFromKey = StringCchCopyExW(
                                           v120,
                                           (unsigned __int64)v121,
                                           L")",
                                           &v120,
                                           (unsigned __int64 *)&v121,
                                           (unsigned int)v106);
        }
        else
        {
          ConditionPropertyNameFromKey = 0;
        }
        goto LABEL_196;
      }
      goto LABEL_196;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54310796>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54310796>::GetImpl'::`2'::impl) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl'::`2'::impl)
        && *(_DWORD *)(a1 + 96) )
      {
        if ( ConditionPropertyNameFromKey < 0 )
          goto LABEL_164;
        v62 = StructuredQuery1::TermBehavior(a9, v54, 0);
        LOBYTE(v119) = 1;
        goto LABEL_133;
      }
    }
    else if ( !v122 )
    {
      if ( ConditionPropertyNameFromKey < 0 )
        goto LABEL_164;
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl'::`2'::impl) )
      {
        v66 = StructuredQuery1::TermBehavior(a9, v54, 0);
        v64 = v123;
        LOBYTE(v115) = 1;
        LOBYTE(v112) = 1;
        v65 = StructuredQuery1::WriteOneContainsWithRanking(
                v120,
                v121,
                L"*",
                a13,
                a14,
                890,
                v66,
                v112,
                v115,
                v31,
                v54,
                v123,
                &v120,
                &v121);
        goto LABEL_134;
      }
      v62 = StructuredQuery1::TermBehavior(a9, v54, 0);
      LOBYTE(v119) = v63;
LABEL_133:
      v64 = v123;
      LOBYTE(v115) = 1;
      LOBYTE(v112) = 1;
      v65 = StructuredQuery1::WriteOneRemoteAwareContainsWithRanking(
              v120,
              v121,
              L"*",
              a13,
              a14,
              890,
              v62,
              v112,
              v115,
              v31,
              v54,
              v123,
              &v120,
              &v121,
              (_DWORD)v119);
LABEL_134:
      ConditionPropertyNameFromKey = v65;
      goto LABEL_137;
    }
    v64 = v123;
LABEL_137:
    if ( ConditionPropertyNameFromKey >= 0 )
    {
      if ( !(_BYTE)v126 )
        goto LABEL_147;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl'::`2'::impl) )
      {
        v67 = 880;
        v68 = *(_DWORD *)(a1 + 96) == 0;
        if ( !*(_DWORD *)(a1 + 96) )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54310796>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54310796>::GetImpl'::`2'::impl) )
            v67 = 8;
          v68 = *(_DWORD *)(a1 + 96) == 0;
        }
        LOBYTE(v119) = !v68;
        LOBYTE(v115) = 1;
        LOBYTE(v112) = 1;
        v69 = StructuredQuery1::WriteOneRemoteAwareContainsWithRanking(
                v120,
                v121,
                L"*",
                a13,
                a14,
                v67,
                1,
                v112,
                v115,
                v31,
                v54,
                v64,
                &v120,
                &v121,
                (_DWORD)v119);
      }
      else
      {
        v70 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_54310796>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54310796>::GetImpl'::`2'::impl);
        LOBYTE(v115) = 1;
        LOBYTE(v112) = 1;
        v69 = StructuredQuery1::WriteOneContainsWithRanking(
                v120,
                v121,
                L"*",
                a13,
                a14,
                v70 != 0 ? 8 : 880,
                1,
                v112,
                v115,
                v31,
                v54,
                v64,
                &v120,
                &v121);
      }
      ConditionPropertyNameFromKey = v69;
      if ( v69 >= 0 )
      {
LABEL_147:
        if ( a14 > 1 )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl'::`2'::impl) )
          {
            v71 = 870;
            if ( !*(_DWORD *)(a1 + 96)
              && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54310796>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54310796>::GetImpl'::`2'::impl) )
            {
              v71 = 6;
            }
            v72 = StructuredQuery1::TermBehavior(a9, v54, 0);
            LOBYTE(v119) = v73;
            LOBYTE(v115) = 1;
            LOBYTE(v112) = 0;
            v74 = StructuredQuery1::WriteOneRemoteAwareContainsWithRanking(
                    v120,
                    v121,
                    L"*",
                    a13,
                    a14,
                    v71,
                    v72,
                    v112,
                    v115,
                    v31,
                    v54,
                    v123,
                    &v120,
                    &v121,
                    (_DWORD)v119);
          }
          else
          {
            v75 = StructuredQuery1::TermBehavior(a9, v54, 0);
            v76 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_54310796>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54310796>::GetImpl'::`2'::impl);
            LOBYTE(v115) = 1;
            LOBYTE(v112) = 0;
            v74 = StructuredQuery1::WriteOneContainsWithRanking(
                    v120,
                    v121,
                    L"*",
                    a13,
                    a14,
                    v76 != 0 ? 6 : 870,
                    v75,
                    v112,
                    v115,
                    v31,
                    v54,
                    v123,
                    &v120,
                    &v121);
          }
          ConditionPropertyNameFromKey = v74;
          if ( v74 >= 0 )
          {
            if ( (_BYTE)v127 )
            {
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl'::`2'::impl) )
              {
                v77 = 860;
                v78 = *(_DWORD *)(a1 + 96) == 0;
                if ( !*(_DWORD *)(a1 + 96) )
                {
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54310796>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54310796>::GetImpl'::`2'::impl) )
                    v77 = 4;
                  v78 = *(_DWORD *)(a1 + 96) == 0;
                }
                LOBYTE(v119) = !v78;
                v79 = v123;
                LOBYTE(v116) = 1;
                LOBYTE(v113) = 0;
                v80 = StructuredQuery1::WriteOneRemoteAwareContainsWithRanking(
                        v120,
                        v121,
                        L"*",
                        a13,
                        a14,
                        v77,
                        1,
                        v113,
                        v116,
                        v31,
                        v54,
                        v123,
                        &v120,
                        &v121,
                        (_DWORD)v119);
              }
              else
              {
                v81 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_54310796>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54310796>::GetImpl'::`2'::impl);
                v79 = v123;
                LOBYTE(v116) = 1;
                LOBYTE(v113) = 0;
                v80 = StructuredQuery1::WriteOneContainsWithRanking(
                        v120,
                        v121,
                        L"*",
                        a13,
                        a14,
                        v81 != 0 ? 4 : 860,
                        1,
                        v113,
                        v116,
                        v31,
                        v54,
                        v123,
                        &v120,
                        &v121);
              }
              ConditionPropertyNameFromKey = v80;
LABEL_165:
              v82 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_54310796>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54310796>::GetImpl'::`2'::impl);
              v83 = v122;
              if ( v82 )
              {
                if ( ConditionPropertyNameFromKey >= 0 )
                {
                  if ( !v122
                    || (ConditionPropertyNameFromKey = StringCchCopyExW(
                                                         v120,
                                                         (unsigned __int64)v121,
                                                         L" OR (( ",
                                                         &v120,
                                                         (unsigned __int64 *)&v121,
                                                         (unsigned int)v106),
                        ConditionPropertyNameFromKey >= 0) )
                  {
                    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57356423>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57356423>::GetImpl'::`2'::impl)
                      || !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58124455>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58124455>::GetImpl'::`2'::impl)
                      || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl'::`2'::impl)
                      && *(_DWORD *)(a1 + 96) )
                    {
                      if ( v83 )
                      {
                        v88 = StructuredQuery1::TermBehavior(a9, v54, 0);
                        v87 = StructuredQuery1::WriteContains(
                                (unsigned __int64 *)L"*",
                                (__int64)a13,
                                a14,
                                v88,
                                1,
                                v54,
                                v79,
                                v90,
                                v89,
                                &v120,
                                &v121);
                        goto LABEL_177;
                      }
                    }
                    else if ( v83 )
                    {
                      v84 = StructuredQuery1::TermBehavior(a9, v54, 0);
                      LODWORD(v106) = v85;
                      v87 = StructuredQuery1::WriteFreeText(v86, a13, a14, v84, v54);
LABEL_177:
                      ConditionPropertyNameFromKey = v87;
                      goto LABEL_179;
                    }
                    ConditionPropertyNameFromKey = 0;
                  }
                }
              }
LABEL_179:
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl) )
              {
                if ( ConditionPropertyNameFromKey >= 0 )
                {
                  if ( !v83 && !*(_DWORD *)(a1 + 96) )
                  {
                    v91 = *(_QWORD *)(a1 + 72);
                    v92 = *(_QWORD *)(a1 + 80);
                    while ( v91 != v92 )
                    {
                      std::wstring::wstring(&v135, *a13);
                      v93 = StructuredQuery1::WriteExternalSearchContains(
                              (_DWORD)v120,
                              (_DWORD)v121,
                              (unsigned int)&v120,
                              (unsigned int)&v121,
                              (__int64)&v135,
                              v91);
                      std::wstring::_Tidy_deallocate(&v135);
                      if ( v93 < 0 )
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0xF39,
                          (unsigned int)"onecoreuap\\base\\appmodel\\search\\structuredquery\\sqlgenerator\\generatesql.cpp",
                          (const char *)(unsigned int)v93,
                          v103);
                        return (unsigned int)v93;
                      }
                      v91 += 32;
                    }
                  }
                  goto LABEL_190;
                }
                goto LABEL_196;
              }
              goto LABEL_189;
            }
          }
        }
      }
    }
LABEL_164:
    v79 = v123;
    goto LABEL_165;
  }
LABEL_196:
  CoTaskMemFree(v130);
LABEL_213:
  *v132 = v120;
  *v133 = v121;
  return (unsigned int)ConditionPropertyNameFromKey;
}

```

## disassembly

```asm
0x1800810fc  mov     [rsp-8+arg_18], rbx
0x180081101  push    rbp
0x180081102  push    rsi
0x180081103  push    rdi
0x180081104  push    r12
0x180081106  push    r13
0x180081108  push    r14
0x18008110a  push    r15
0x18008110c  lea     rbp, [rsp-30h]
0x180081111  sub     rsp, 130h
0x180081118  mov     rax, cs:__security_cookie
0x18008111f  xor     rax, rsp
0x180081122  mov     [rbp+60h+var_40], rax
0x180081126  mov     [rbp+60h+var_D0], r9b
0x18008112a  mov     r10, r8
0x18008112d  mov     rax, rdx
0x180081130  mov     r14, rcx
0x180081133  mov     [rbp+60h+var_E0], rdx
0x180081137  mov     [rbp+60h+var_D8], r8
0x18008113b  mov     rcx, [rbp+60h+arg_58]
0x180081142  mov     [rbp+60h+var_B8], rcx
0x180081146  mov     r13, [rbp+60h+arg_60]
0x18008114d  mov     rcx, [rbp+60h+arg_70]
0x180081154  mov     [rbp+60h+var_90], rcx
0x180081158  mov     r12, [rbp+60h+arg_78]
0x18008115f  mov     [rbp+60h+var_C8], r12
0x180081163  mov     rcx, [rbp+60h+arg_80]
0x18008116a  mov     [rbp+60h+var_88], rcx
0x18008116e  mov     rcx, [rbp+60h+arg_88]
0x180081175  mov     [rbp+60h+var_80], rcx
0x180081179  lea     rcx, [rbp+60h+var_D8]
0x18008117d  mov     [rsp+160h+var_140], rcx; wchar_t **
0x180081182  lea     r9, [rbp+60h+var_E0]; bool
0x180081186  mov     r8b, byte ptr [rbp+60h+arg_48]; unsigned __int64
0x18008118d  mov     rdx, r10; wchar_t *
0x180081190  mov     rcx, rax; this
0x180081193  call    ?WriteNot@StructuredQuery1@@YAJPEA_W_K_NPEAPEA_WPEA_K@Z; StructuredQuery1::WriteNot(wchar_t *,unsigned __int64,bool,wchar_t * *,unsigned __int64 *)
0x180081198  mov     ebx, eax
0x18008119a  xor     r15d, r15d
0x18008119d  test    eax, eax
0x18008119f  js      loc_1800827B1
0x1800811a5  mov     r9d, [rbp+60h+arg_40]
0x1800811ac  mov     r10b, r15b
0x1800811af  mov     [rbp+60h+var_AC], r10d
0x1800811b3  lea     r11d, [r15+1]
0x1800811b7  mov     r8b, r11b
0x1800811ba  mov     [rbp+60h+var_B0], r8d
0x1800811be  mov     edx, r15d
0x1800811c1  mov     esi, [rbp+60h+arg_68]
0x1800811c7  test    esi, esi
0x1800811c9  jz      short loc_1800811F5
0x1800811cb  mov     eax, edx
0x1800811cd  add     rax, rax
0x1800811d0  movzx   r10d, r10b
0x1800811d4  cmp     dword ptr [r13+rax*8+8], 0Dh
0x1800811da  cmovz   r10d, r11d
0x1800811de  movzx   r8d, r8b
0x1800811e2  cmovnz  r8d, r15d
0x1800811e6  add     edx, r11d
0x1800811e9  cmp     edx, esi
0x1800811eb  jb      short loc_1800811CB
0x1800811ed  mov     [rbp+60h+var_AC], r10d
0x1800811f1  mov     [rbp+60h+var_B0], r8d
0x1800811f5  lea     rdx, PKEY_FullText
0x1800811fc  mov     rcx, [rbp+60h+arg_50]
0x180081203  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x180081208  mov     edi, r9d
0x18008120b  test    eax, eax
0x18008120d  jz      loc_18008258B
0x180081213  and     edi, 2
0x180081216  jz      loc_18008258E
0x18008121c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FI45262758@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FI45262758@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758> `wil::Feature<__WilFeatureTraits_Feature_FI45262758>::GetImpl(void)'::`2'::impl
0x180081223  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FI45262758@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758>::__private_IsEnabled(void)
0x180081228  mov     bl, [rbp+60h+arg_20]
0x18008122e  test    al, al
0x180081230  jz      short loc_180081251
0x180081232  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60157349@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60157349@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349> `wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl(void)'::`2'::impl
0x180081239  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60157349@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(void)
0x18008123e  test    al, al
0x180081240  jz      short loc_180081248
0x180081242  cmp     [r14+60h], r15d
0x180081246  jnz     short loc_180081251
0x180081248  test    bl, bl
0x18008124a  jnz     short loc_180081251
0x18008124c  mov     ebx, r15d
0x18008124f  jmp     short loc_180081274
0x180081251  lea     rax, [rbp+60h+var_D8]
0x180081255  mov     [rsp+160h+var_140], rax; unsigned __int64 *
0x18008125a  lea     r9, [rbp+60h+var_E0]; wchar_t **
0x18008125e  lea     r8, asc_18009B4D0; "("
0x180081265  mov     rdx, [rbp+60h+var_D8]; unsigned __int64
0x180081269  mov     rcx, [rbp+60h+var_E0]; wchar_t *
0x18008126d  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x180081272  mov     ebx, eax
0x180081274  test    ebx, ebx
0x180081276  js      loc_1800827B1
0x18008127c  mov     [rbp+60h+var_A8], r15d
0x180081280  mov     rcx, [r14+8]
0x180081284  mov     rax, [rcx]
0x180081287  lea     rdx, [rbp+60h+var_A8]
0x18008128b  mov     rax, [rax+18h]
0x18008128f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081294  mov     ebx, eax
0x180081296  test    eax, eax
0x180081298  js      loc_1800827B1
0x18008129e  mov     [rbp+60h+var_98], r15
0x1800812a2  lea     r9, [rbp+60h+var_98]
0x1800812a6  mov     edi, 7800h
0x1800812ab  mov     r8d, edi
0x1800812ae  mov     edx, 1
0x1800812b3  call    ??$_AllocArray@_WVCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEA_W@Z; _AllocArray<wchar_t,CTCoAllocPolicy>(void *,ulong,unsigned __int64,wchar_t * *)
0x1800812b8  mov     ebx, eax
0x1800812ba  test    eax, eax
0x1800812bc  js      loc_1800827B1
0x1800812c2  mov     rax, [rbp+60h+var_98]
0x1800812c6  mov     [rbp+60h+var_B8], rax
0x1800812ca  mov     [rbp+60h+var_C0], rdi
0x1800812ce  lea     rcx, [rbp+60h+var_C0]
0x1800812d2  mov     [rsp+160h+var_140], rcx; unsigned __int64 *
0x1800812d7  lea     r9, [rbp+60h+var_B8]; wchar_t **
0x1800812db  mov     r8, [r13+0]; wchar_t *
0x1800812df  mov     edx, edi; unsigned __int64
0x1800812e1  mov     rcx, rax; wchar_t *
0x1800812e4  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x1800812e9  mov     ebx, eax
0x1800812eb  mov     edi, 1
0x1800812f0  test    eax, eax
0x1800812f2  js      loc_18008257C
0x1800812f8  cmp     edi, esi
0x1800812fa  jnb     short loc_180081355
0x1800812fc  lea     rax, [rbp+60h+var_C0]
0x180081300  mov     [rsp+160h+var_140], rax; unsigned __int64 *
0x180081305  lea     r9, [rbp+60h+var_B8]; wchar_t **
0x180081309  lea     r8, pszTrimChars; " "
0x180081310  mov     rdx, [rbp+60h+var_C0]; unsigned __int64
0x180081314  mov     rcx, [rbp+60h+var_B8]; wchar_t *
0x180081318  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18008131d  mov     ebx, eax
0x18008131f  test    eax, eax
0x180081321  js      short loc_18008134A
0x180081323  mov     r8d, edi
0x180081326  add     r8, r8
0x180081329  lea     rax, [rbp+60h+var_C0]
0x18008132d  mov     [rsp+160h+var_140], rax; unsigned __int64 *
0x180081332  lea     r9, [rbp+60h+var_B8]; wchar_t **
0x180081336  mov     r8, [r13+r8*8+0]; wchar_t *
0x18008133b  mov     rdx, [rbp+60h+var_C0]; unsigned __int64
0x18008133f  mov     rcx, [rbp+60h+var_B8]; wchar_t *
0x180081343  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x180081348  mov     ebx, eax
0x18008134a  inc     edi
0x18008134c  test    ebx, ebx
0x18008134e  jns     short loc_1800812F8
0x180081350  jmp     loc_18008257C
0x180081355  cmp     [rbp+60h+arg_38], r15b
0x18008135c  jz      loc_180081596
0x180081362  mov     ecx, 1Fh; this
0x180081367  mov     word ptr [rbp+60h+propkey], cx
0x18008136b  xorps   xmm0, xmm0
0x18008136e  xor     eax, eax
0x180081370  movups  xmmword ptr [rbp+60h+propkey+2], xmm0
0x180081374  mov     qword ptr [rbp+60h+propkey+10h], rax
0x180081378  mov     rax, [rbp+60h+var_98]
0x18008137c  mov     qword ptr [rbp+60h+propkey+8], rax
0x180081380  lea     rax, [rbp+60h+var_D8]
0x180081384  mov     [rsp+160h+var_100], rax; unsigned __int64 *
0x180081389  lea     rax, [rbp+60h+var_E0]
0x18008138d  mov     [rsp+160h+var_108], rax; wchar_t **
0x180081392  lea     rax, [rbp+60h+propkey]
0x180081396  mov     [rsp+160h+var_110], rax; struct tagPROPVARIANT *
0x18008139b  lea     rax, asc_18009AA1C; "<>"
0x1800813a2  mov     [rsp+160h+var_118], rax; wchar_t *
0x1800813a7  lea     rax, asc_18009AA0C; "="
0x1800813ae  mov     [rsp+160h+var_120], rax; wchar_t *
0x1800813b3  lea     rax, aSystemComment; "System.Comment"
0x1800813ba  mov     [rsp+160h+var_128], rax; wchar_t *
0x1800813bf  mov     [rsp+160h+var_130], r15b; bool
0x1800813c4  mov     word ptr [rsp+160h+var_138], cx; unsigned int
0x1800813c9  mov     byte ptr [rsp+160h+var_140], r15b; bool
0x1800813ce  xor     r9d, r9d; bool
0x1800813d1  mov     r8, [rbp+60h+var_D8]; unsigned __int64
0x1800813d5  mov     rdx, [rbp+60h+var_E0]; wchar_t *
0x1800813d9  call    ?WriteValueComparison@SqlGenerator@StructuredQuery1@@AEAAJPEA_W_K_N2G2PEB_W33AEBUtagPROPVARIANT@@PEAPEA_WPEA_K@Z; StructuredQuery1::SqlGenerator::WriteValueComparison(wchar_t *,unsigned __int64,bool,bool,ushort,bool,wchar_t const *,wchar_t const *,wchar_t const *,tagPROPVARIANT const &,wchar_t * *,unsigned __int64 *)
0x1800813de  mov     ebx, eax
0x1800813e0  test    eax, eax
0x1800813e2  js      loc_18008257C
0x1800813e8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FI45262758@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FI45262758@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758> `wil::Feature<__WilFeatureTraits_Feature_FI45262758>::GetImpl(void)'::`2'::impl
0x1800813ef  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FI45262758@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758>::__private_IsEnabled(void)
0x1800813f4  mov     r12d, 64h ; 'd'
0x1800813fa  mov     r15d, [rbp+60h+arg_28]
0x180081401  test    al, al
0x180081403  jz      short loc_18008144F
0x180081405  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60157349@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60157349@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349> `wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl(void)'::`2'::impl
0x18008140c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60157349@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(void)
0x180081411  mov     edi, 3E7h
0x180081416  test    al, al
0x180081418  lea     rax, [rbp+60h+var_D8]
0x18008141c  jz      short loc_180081425
0x18008141e  cmp     dword ptr [r14+60h], 0
0x180081423  jnz     short loc_180081458
0x180081425  mov     qword ptr [rsp+160h+var_130], rax
0x18008142a  lea     rax, [rbp+60h+var_E0]
0x18008142e  mov     [rsp+160h+var_138], rax
0x180081433  mov     rax, [rbp+60h+var_D8]
0x180081437  mov     [rsp+160h+var_140], rax
0x18008143c  mov     r9, [rbp+60h+var_E0]
0x180081440  mov     r8d, r15d
0x180081443  mov     edx, edi
0x180081445  mov     ecx, r12d
0x180081448  call    ?WriteRanking@StructuredQuery1@@YAJHHW4RANKING_COERCION@1@PEA_W_KPEAPEA_WPEA_K@Z; StructuredQuery1::WriteRanking(int,int,StructuredQuery1::RANKING_COERCION,wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *)
0x18008144d  jmp     short loc_180081470
0x18008144f  lea     rax, [rbp+60h+var_D8]
0x180081453  mov     edi, 3E7h
0x180081458  mov     [rsp+160h+var_140], rax; wchar_t **
0x18008145d  lea     r9, [rbp+60h+var_E0]; unsigned __int64
0x180081461  mov     r8, [rbp+60h+var_D8]; wchar_t *
0x180081465  mov     rdx, [rbp+60h+var_E0]; int
0x180081469  mov     ecx, edi; this
0x18008146b  call    ?WriteRankingAppendix@StructuredQuery1@@YAJHPEA_W_KPEAPEA_WPEA_K@Z; StructuredQuery1::WriteRankingAppendix(int,wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *)
0x180081470  mov     ebx, eax
0x180081472  test    eax, eax
0x180081474  js      loc_18008257C
0x18008147a  lea     rax, [rbp+60h+var_D8]
0x18008147e  mov     [rsp+160h+var_140], rax; unsigned __int64 *
0x180081483  lea     r9, [rbp+60h+var_E0]; wchar_t **
0x180081487  lea     r8, aOr_1; " OR "
0x18008148e  mov     rdx, [rbp+60h+var_D8]; unsigned __int64
0x180081492  mov     rcx, [rbp+60h+var_E0]; wchar_t *
0x180081496  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18008149b  mov     ebx, eax
0x18008149d  test    eax, eax
0x18008149f  js      loc_18008257C
0x1800814a5  mov     ecx, 1Fh; this
0x1800814aa  mov     word ptr [rbp+60h+propkey], cx
0x1800814ae  mov     rax, [rbp+60h+var_98]
0x1800814b2  mov     qword ptr [rbp+60h+propkey+8], rax
0x1800814b6  lea     rax, [rbp+60h+var_D8]
0x1800814ba  mov     [rsp+160h+var_100], rax; unsigned __int64 *
0x1800814bf  lea     rax, [rbp+60h+var_E0]
0x1800814c3  mov     [rsp+160h+var_108], rax; wchar_t **
0x1800814c8  lea     rax, [rbp+60h+propkey]
0x1800814cc  mov     [rsp+160h+var_110], rax; struct tagPROPVARIANT *
0x1800814d1  lea     rax, asc_18009AA1C; "<>"
0x1800814d8  mov     [rsp+160h+var_118], rax; wchar_t *
0x1800814dd  lea     rax, asc_18009AA0C; "="
0x1800814e4  mov     [rsp+160h+var_120], rax; wchar_t *
0x1800814e9  lea     rax, aSystemHighkeyw; "System.HighKeywords"
0x1800814f0  mov     [rsp+160h+var_128], rax; wchar_t *
0x1800814f5  mov     [rsp+160h+var_130], 0; bool
0x1800814fa  mov     word ptr [rsp+160h+var_138], cx; unsigned __int64 *
0x1800814ff  mov     byte ptr [rsp+160h+var_140], 0; bool
0x180081504  mov     r9b, 1; bool
0x180081507  mov     r8, [rbp+60h+var_D8]; unsigned __int64
0x18008150b  mov     rdx, [rbp+60h+var_E0]; wchar_t *
0x18008150f  call    ?WriteValueComparison@SqlGenerator@StructuredQuery1@@AEAAJPEA_W_K_N2G2PEB_W33AEBUtagPROPVARIANT@@PEAPEA_WPEA_K@Z; StructuredQuery1::SqlGenerator::WriteValueComparison(wchar_t *,unsigned __int64,bool,bool,ushort,bool,wchar_t const *,wchar_t const *,wchar_t const *,tagPROPVARIANT const &,wchar_t * *,unsigned __int64 *)
0x180081514  mov     ebx, eax
0x180081516  test    eax, eax
0x180081518  js      loc_18008257C
0x18008151e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FI45262758@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FI45262758@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758> `wil::Feature<__WilFeatureTraits_Feature_FI45262758>::GetImpl(void)'::`2'::impl
0x180081525  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FI45262758@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758>::__private_IsEnabled(void)
0x18008152a  test    al, al
0x18008152c  jz      short loc_180081573
0x18008152e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60157349@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60157349@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349> `wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl(void)'::`2'::impl
0x180081535  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60157349@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(void)
0x18008153a  test    al, al
0x18008153c  lea     rax, [rbp+60h+var_D8]
0x180081540  jz      short loc_180081549
0x180081542  cmp     dword ptr [r14+60h], 0
0x180081547  jnz     short loc_180081577
0x180081549  mov     qword ptr [rsp+160h+var_130], rax
0x18008154e  lea     rax, [rbp+60h+var_E0]
0x180081552  mov     [rsp+160h+var_138], rax
0x180081557  mov     rax, [rbp+60h+var_D8]
0x18008155b  mov     [rsp+160h+var_140], rax
0x180081560  mov     r9, [rbp+60h+var_E0]
0x180081564  mov     r8d, r15d
0x180081567  mov     edx, edi
0x180081569  mov     ecx, r12d
0x18008156c  call    ?WriteRanking@StructuredQuery1@@YAJHHW4RANKING_COERCION@1@PEA_W_KPEAPEA_WPEA_K@Z; StructuredQuery1::WriteRanking(int,int,StructuredQuery1::RANKING_COERCION,wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *)
0x180081571  jmp     short loc_18008158F
0x180081573  lea     rax, [rbp+60h+var_D8]
0x180081577  mov     [rsp+160h+var_140], rax; wchar_t **
0x18008157c  lea     r9, [rbp+60h+var_E0]; unsigned __int64
0x180081580  mov     r8, [rbp+60h+var_D8]; wchar_t *
0x180081584  mov     rdx, [rbp+60h+var_E0]; int
0x180081588  mov     ecx, edi; this
0x18008158a  call    ?WriteRankingAppendix@StructuredQuery1@@YAJHPEA_W_KPEAPEA_WPEA_K@Z; StructuredQuery1::WriteRankingAppendix(int,wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *)
0x18008158f  mov     ebx, eax
0x180081591  jmp     loc_1800817B9
0x180081596  mov     r12d, r15d
0x180081599  mov     edi, 3E7h
0x18008159e  mov     r15d, [rbp+60h+arg_28]
0x1800815a5  cmp     r12d, [rbp+60h+var_A8]
0x1800815a9  jnb     loc_180081947
0x1800815af  test    r12d, r12d
0x1800815b2  jz      short loc_1800815D7
0x1800815b4  lea     rax, [rbp+60h+var_D8]
0x1800815b8  mov     [rsp+160h+var_140], rax; unsigned __int64 *
0x1800815bd  lea     r9, [rbp+60h+var_E0]; wchar_t **
0x1800815c1  lea     r8, aOr_1; " OR "
  ... truncated ...
```
