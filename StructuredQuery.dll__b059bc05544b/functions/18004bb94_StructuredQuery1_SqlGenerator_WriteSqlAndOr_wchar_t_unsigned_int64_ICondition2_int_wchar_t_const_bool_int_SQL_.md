# StructuredQuery1::SqlGenerator::WriteSqlAndOr(wchar_t *,unsigned __int64,ICondition2 *,int,wchar_t const *,bool,int,SQL_GENERATION_OPTIONS,bool,StructuredQuery1::VirtualPropertyMap *,bool,wchar_t * *,unsigned __int64 *)

- ea: `0x18004bb94`
- end: `0x18004d939`
- name: `?WriteSqlAndOr@SqlGenerator@StructuredQuery1@@AEAAJPEA_W_KPEAUICondition2@@HPEB_W_NHW4SQL_GENERATION_OPTIONS@@4PEAVVirtualPropertyMap@2@4PEAPEA_WPEA_K@Z`
- size: `7589`
- prototype: ``
- caller_count: `1`
- callee_count: `34`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004a18c`

## callees

- `0x180020250`
- `0x18002a220`
- `0x18002e5c0`
- `0x18002fc34`
- `0x180033f74`
- `0x180034064`
- `0x180036910`
- `0x180036b7c`
- `0x18003bed0`
- `0x18004146c`
- `0x18004a18c`
- `0x18004bb94`
- `0x180052e5c`
- `0x1800535d0`
- `0x180053678`
- `0x1800587b4`
- `0x18005ac20`
- `0x18005c3d4`
- `0x18005ca18`
- `0x18005daf0`
- `0x18006749c`
- `0x18007e6a0`
- `0x18007f798`
- `0x180080038`
- `0x180080e98`
- `0x1800810fc`
- `0x1800827f8`
- `0x180082c64`
- `0x1800833a4`
- `0x180083444`
- `0x180083758`
- `0x18008388c`
- `0x180083904`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c3f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c5c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d72f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d743`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c3f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c5c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d72f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d743`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall StructuredQuery1::SqlGenerator::WriteSqlAndOr(
        __int64 a1,
        wchar_t *a2,
        wchar_t *a3,
        __int64 a4,
        int a5,
        wchar_t *a6,
        char a7,
        int a8,
        unsigned int a9,
        char a10,
        StructuredQuery1::VirtualPropertyMap *a11,
        char a12,
        wchar_t **a13,
        wchar_t **a14)
{
  __int64 v14; // r15
  wchar_t **v15; // rbx
  wchar_t **v16; // rsi
  signed int ConditionFullTextInfo; // edi
  unsigned int v18; // r8d
  unsigned int v19; // ecx
  unsigned int v20; // r13d
  unsigned int RankableSubConditionCount; // eax
  unsigned __int64 v22; // r8
  unsigned int *v23; // r9
  unsigned int v24; // ebx
  int v25; // ebx
  StructuredQuery1 *v26; // r12
  unsigned int v27; // esi
  __int64 v28; // r8
  unsigned int v29; // r14d
  int v30; // edx
  __int64 v31; // rax
  const PROPERTYKEY *v32; // r9
  __int64 v33; // rsi
  int v34; // ecx
  int v35; // ecx
  unsigned int v36; // ebx
  int v37; // eax
  int v38; // ebx
  StructuredQuery1::SqlGenerator *v39; // rcx
  void *v40; // r8
  StructuredQuery1::VirtualPropertyMap *v41; // rcx
  wchar_t *v42; // r14
  LPVOID v43; // rbx
  int Alias; // eax
  unsigned int v45; // eax
  LPVOID v46; // r8
  unsigned int v47; // ebx
  unsigned int v48; // eax
  unsigned int v49; // ebx
  unsigned int lpVtbl; // ecx
  int v51; // r15d
  unsigned int v52; // edx
  wchar_t *v53; // r14
  wchar_t *v54; // r13
  IMalloc *v55; // rcx
  unsigned int v56; // ebx
  __int64 v57; // rcx
  int v58; // r14d
  int v59; // r12d
  bool v60; // r15
  __int64 v61; // rcx
  int v62; // ebx
  char IsPCSettingsQuery; // al
  _BOOL8 v64; // r9
  int FullPhrase; // eax
  __int64 v66; // rcx
  __int64 v67; // r9
  unsigned int v68; // ebx
  LPVOID v69; // rbx
  __int64 v70; // rdi
  __int64 v71; // rsi
  int v72; // eax
  void **p_pv; // rcx
  int v74; // ebx
  char v75; // al
  int v76; // r14d
  int v77; // r12d
  bool v78; // r15
  __int64 v79; // rcx
  int v80; // ebx
  char v81; // al
  _BOOL8 v82; // r9
  int v83; // eax
  __int64 v84; // rcx
  __int64 v85; // r9
  __int64 v86; // rbx
  __int64 v87; // r13
  __int64 v88; // rdi
  __int64 v89; // rsi
  int v90; // eax
  unsigned int v91; // ebx
  char v92; // al
  int v93; // r14d
  int v94; // r13d
  bool v95; // r15
  __int64 v96; // rcx
  char v97; // al
  __int64 v98; // rcx
  wchar_t *v99; // rbx
  __int64 v100; // r9
  int v101; // eax
  __int64 v102; // rcx
  __int64 v103; // r9
  LPVOID v104; // rbx
  __int64 v105; // rdi
  __int64 v106; // r14
  int v107; // eax
  int v108; // r14d
  int v109; // r13d
  bool v110; // r15
  __int64 v111; // rcx
  char v112; // al
  __int64 v113; // rcx
  wchar_t *v114; // rbx
  __int64 v115; // r9
  int v116; // eax
  __int64 v117; // rcx
  __int64 v118; // r9
  LPVOID v119; // rbx
  bool v120; // zf
  __int64 v121; // r14
  __int64 v122; // rdi
  __int64 v123; // r14
  int v124; // eax
  unsigned int v125; // ebx
  wchar_t *v126; // rdi
  void **v127; // rcx
  unsigned int *v129; // [rsp+20h] [rbp-F0h]
  int v130; // [rsp+20h] [rbp-F0h]
  int v131; // [rsp+20h] [rbp-F0h]
  int v132; // [rsp+20h] [rbp-F0h]
  int v133; // [rsp+20h] [rbp-F0h]
  unsigned __int64 *v134; // [rsp+28h] [rbp-E8h]
  __int64 v135; // [rsp+38h] [rbp-D8h]
  wchar_t **v136; // [rsp+48h] [rbp-C8h]
  wchar_t *v137; // [rsp+60h] [rbp-B0h]
  wchar_t *v138; // [rsp+60h] [rbp-B0h]
  wchar_t *v139; // [rsp+78h] [rbp-98h]
  wchar_t *v140; // [rsp+90h] [rbp-80h] BYREF
  wchar_t *v141; // [rsp+98h] [rbp-78h] BYREF
  signed int v142; // [rsp+A0h] [rbp-70h]
  bool v143[4]; // [rsp+A4h] [rbp-6Ch] BYREF
  IObjectArray v144; // [rsp+A8h] [rbp-68h] BYREF
  LPVOID pv; // [rsp+B0h] [rbp-60h] BYREF
  wchar_t *v146; // [rsp+B8h] [rbp-58h]
  unsigned int v147; // [rsp+C0h] [rbp-50h]
  StructuredQuery1 *v148; // [rsp+C8h] [rbp-48h]
  wchar_t *v149; // [rsp+D0h] [rbp-40h] BYREF
  __int64 v150; // [rsp+D8h] [rbp-38h] BYREF
  StructuredQuery1::VirtualPropertyMap *v151; // [rsp+E0h] [rbp-30h]
  __int64 v152; // [rsp+E8h] [rbp-28h]
  int v153; // [rsp+F0h] [rbp-20h]
  unsigned int v154; // [rsp+F4h] [rbp-1Ch] BYREF
  __int64 v155; // [rsp+F8h] [rbp-18h]
  unsigned int v156; // [rsp+100h] [rbp-10h] BYREF
  int v157; // [rsp+104h] [rbp-Ch]
  wchar_t **v158; // [rsp+108h] [rbp-8h]
  wchar_t **v159; // [rsp+110h] [rbp+0h]
  int v160; // [rsp+118h] [rbp+8h]
  StructuredQuery1 *v161; // [rsp+120h] [rbp+10h] BYREF
  unsigned int v162; // [rsp+128h] [rbp+18h]
  StructuredQuery1 *v163; // [rsp+130h] [rbp+20h] BYREF
  struct StructuredQuery1::CONDITION_GROUP *v164; // [rsp+138h] [rbp+28h]
  bool v165; // [rsp+140h] [rbp+30h]
  __int128 v166; // [rsp+148h] [rbp+38h] BYREF
  __int64 v167; // [rsp+158h] [rbp+48h]
  int v168[8]; // [rsp+160h] [rbp+50h] BYREF
  int v169[8]; // [rsp+180h] [rbp+70h] BYREF
  int v170[8]; // [rsp+1A0h] [rbp+90h] BYREF
  int v171[8]; // [rsp+1C0h] [rbp+B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+128h]

  v155 = a4;
  v14 = a1;
  v152 = a1;
  v140 = a2;
  v141 = a3;
  v146 = a6;
  v151 = a11;
  v15 = a13;
  v158 = a13;
  v16 = a14;
  v159 = a14;
  v161 = 0;
  ConditionFullTextInfo = (*(__int64 (__fastcall **)(__int64, GUID *, StructuredQuery1 **))(*(_QWORD *)a4 + 72LL))(
                            a4,
                            &GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9,
                            &v161);
  if ( ConditionFullTextInfo < 0 )
    goto LABEL_277;
  v156 = 0;
  ConditionFullTextInfo = (*(__int64 (__fastcall **)(StructuredQuery1 *, unsigned int *))(*(_QWORD *)v161 + 24LL))(
                            v161,
                            &v156);
  if ( ConditionFullTextInfo < 0 )
    goto LABEL_276;
  v19 = v156;
  v20 = a9;
  v160 = a9 & 2;
  if ( (a9 & 2) != 0 )
  {
    RankableSubConditionCount = StructuredQuery1::GetRankableSubConditionCount(v161, (struct IObjectArray *)v156, v18);
    v19 = -1;
    if ( RankableSubConditionCount + v156 >= RankableSubConditionCount )
      v19 = RankableSubConditionCount + v156;
    ConditionFullTextInfo = RankableSubConditionCount + v156 < RankableSubConditionCount ? 0x80070216 : 0;
  }
  if ( ConditionFullTextInfo < 0 )
  {
LABEL_276:
    (*(void (__fastcall **)(StructuredQuery1 *))(*(_QWORD *)v161 + 16LL))(v161);
LABEL_277:
    *v15 = v140;
    *v16 = v141;
    return (unsigned int)ConditionFullTextInfo;
  }
  v163 = 0;
  v164 = 0;
  v165 = 0;
  ConditionFullTextInfo = StructuredQuery1::ConditionGroupManager::Initialize((void **)&v163, v19);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl'::`2'::impl) )
  {
    v165 = *(_DWORD *)(v14 + 96) != 0;
  }
  else if ( ConditionFullTextInfo < 0 )
  {
LABEL_275:
    StructuredQuery1::ConditionGroupManager::~ConditionGroupManager((StructuredQuery1::ConditionGroupManager *)&v163);
    goto LABEL_276;
  }
  v24 = 0;
  while ( v24 < v156 )
  {
    pv = 0;
    ConditionFullTextInfo = (*(__int64 (__fastcall **)(StructuredQuery1 *, _QWORD, GUID *, LPVOID *))(*(_QWORD *)v161 + 32LL))(
                              v161,
                              v24,
                              &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                              &pv);
    if ( ConditionFullTextInfo >= 0 )
    {
      ConditionFullTextInfo = StructuredQuery1::ConditionGroupManager::AddConjunct(&v163, a9, pv);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
    }
    ++v24;
    if ( ConditionFullTextInfo < 0 )
      goto LABEL_274;
  }
  if ( a10 )
  {
    LOBYTE(v22) = 1;
    ConditionFullTextInfo = StructuredQuery1::WriteNot((StructuredQuery1 *)v140, v141, v22, (bool)&v140, &v141, v134);
    v25 = 2;
    v157 = 2;
    if ( ConditionFullTextInfo < 0 )
      goto LABEL_274;
  }
  else
  {
    v25 = a8;
    v157 = a8;
  }
  v26 = v163;
  v148 = v163;
  v27 = HIDWORD(v164);
  v162 = HIDWORD(v164);
  v154 = 0;
  ConditionFullTextInfo = StructuredQuery1::TotalSubsToWrite(
                            v163,
                            (struct StructuredQuery1::CONDITION_GROUP *)HIDWORD(v164),
                            (unsigned int)&v154,
                            v23);
  if ( ConditionFullTextInfo < 0 )
    goto LABEL_273;
  if ( v154 == 1 )
  {
    v29 = v25;
    v147 = v25;
    v30 = 0;
    v153 = 0;
    v31 = 0;
    v154 = 0;
    goto LABEL_28;
  }
  v29 = a5;
  v147 = a5;
  if ( a5 >= v25 )
    v147 = a5;
  else
    ConditionFullTextInfo = StringCchCopyExW(
                              v140,
                              (unsigned __int64)v141,
                              L"(",
                              &v140,
                              (unsigned __int64 *)&v141,
                              (unsigned int)v134);
  v30 = 0;
  v153 = 0;
  v31 = 0;
  v154 = 0;
  if ( ConditionFullTextInfo < 0 )
    goto LABEL_273;
  while ( 1 )
  {
LABEL_28:
    v32 = &PKEY_FullText;
    if ( (unsigned int)v31 >= v27 )
    {
      if ( (int)v29 < v157 )
        ConditionFullTextInfo = StringCchCopyExW(
                                  v140,
                                  (unsigned __int64)v141,
                                  L")",
                                  &v140,
                                  (unsigned __int64 *)&v141,
                                  (unsigned int)v134);
      goto LABEL_273;
    }
    v33 = 48 * v31;
    v34 = *((_DWORD *)v26 + 12 * v31);
    if ( !v34 )
      break;
    v35 = v34 - 1;
    if ( v35 )
    {
      if ( v35 == 1 )
      {
        LODWORD(v150) = 0;
        ConditionFullTextInfo = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64, const PROPERTYKEY *))(**(_QWORD **)((char *)v26 + v33 + 40) + 24LL))(
                                  *(_QWORD *)((char *)v26 + v33 + 40),
                                  &v150,
                                  v28,
                                  &PKEY_FullText);
        if ( ConditionFullTextInfo >= 0 )
        {
          v36 = 0;
          while ( v36 < (unsigned int)v150 )
          {
            pv = 0;
            ConditionFullTextInfo = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, LPVOID *))(**(_QWORD **)((char *)v26 + v33 + 40)
                                                                                                + 32LL))(
                                      *(_QWORD *)((char *)v26 + v33 + 40),
                                      v36,
                                      &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                                      &pv);
            if ( ConditionFullTextInfo >= 0 )
            {
              v37 = v153++;
              if ( !v37
                || (ConditionFullTextInfo = StringCchCopyExW(
                                              v140,
                                              (unsigned __int64)v141,
                                              v146,
                                              &v140,
                                              (unsigned __int64 *)&v141,
                                              (unsigned int)v134),
                    ConditionFullTextInfo >= 0) )
              {
                v136 = &v140;
                LODWORD(v135) = (_DWORD)v151;
                LODWORD(v134) = v20;
                LODWORD(v129) = v29;
                ConditionFullTextInfo = StructuredQuery1::SqlGenerator::WriteSql(v14, v140, v141, pv);
              }
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
            }
            ++v36;
            if ( ConditionFullTextInfo < 0 )
              goto LABEL_273;
          }
        }
        goto LABEL_257;
      }
      ConditionFullTextInfo = -2147418113;
LABEL_273:
      v16 = v159;
LABEL_274:
      v15 = v158;
      goto LABEL_275;
    }
    v153 = v30 + 1;
    v38 = (int)v146;
    if ( v30 )
      ConditionFullTextInfo = StringCchCopyExW(
                                v140,
                                (unsigned __int64)v141,
                                v146,
                                &v140,
                                (unsigned __int64 *)&v141,
                                (unsigned int)v134);
    v28 = 0;
    if ( ConditionFullTextInfo < 0 )
      goto LABEL_257;
    if ( !operator==((__int64)v26 + v33 + 4, (__int64)&PKEY_FullText) || v160 == (_DWORD)v40 )
    {
      v143[0] = (char)v40;
      pv = v40;
      ConditionFullTextInfo = StructuredQuery1::SqlGenerator::DetermineProperty(
                                v39,
                                (const struct _tagpropertykey *)v39,
                                v151,
                                v143,
                                (wchar_t **)&pv);
      if ( ConditionFullTextInfo >= 0 )
      {
        LODWORD(v136) = v38;
        v135 = *(_QWORD *)((char *)v26 + v33 + 40);
        LODWORD(v134) = 0;
        LODWORD(v129) = v20;
        ConditionFullTextInfo = StructuredQuery1::WriteFullTextDeep(
                                  v29,
                                  pv,
                                  0,
                                  *(unsigned int *)((char *)v26 + v33 + 24));
        CoTaskMemFree(pv);
      }
      goto LABEL_257;
    }
    BYTE4(v144.lpVtbl) = (_BYTE)v40;
    v143[0] = (char)v40;
    LODWORD(v144.lpVtbl) = (_DWORD)v40;
    ConditionFullTextInfo = StructuredQuery1::GetConditionFullTextInfo(
                              *(StructuredQuery1 **)((char *)v26 + v33 + 40),
                              (struct IObjectArray *)((char *)&v144.lpVtbl + 4),
                              v143,
                              (bool *)&v144,
                              v129);
    if ( ConditionFullTextInfo < 0 )
      goto LABEL_257;
    ConditionFullTextInfo = StringCchCopyExW(
                              v140,
                              (unsigned __int64)v141,
                              L"(",
                              &v140,
                              (unsigned __int64 *)&v141,
                              (unsigned int)v134);
    if ( ConditionFullTextInfo < 0 )
      goto LABEL_257;
    if ( a12 )
    {
      v49 = 0;
      lpVtbl = (unsigned int)v144.lpVtbl;
      v51 = (int)v146;
      while ( 1 )
      {
        if ( v49 >= 0x10 )
        {
LABEL_93:
          v14 = v152;
          goto LABEL_94;
        }
        v28 = *((unsigned int *)&off_180097840 + 6 * (int)v49 + 3);
        if ( (_DWORD)v28 == 1 )
          break;
        if ( (_DWORD)v28 == 2 )
        {
          if ( BYTE4(v144.lpVtbl) )
            break;
        }
        else if ( (_DWORD)v28 == 3 )
        {
          if ( lpVtbl > 1 )
            break;
        }
        else if ( (_DWORD)v28 == 4 && lpVtbl > 1 && v143[0] )
        {
          break;
        }
LABEL_92:
        ++v49;
        if ( ConditionFullTextInfo < 0 )
          goto LABEL_93;
      }
      v52 = 0;
      if ( !LOBYTE((&off_180097840)[3 * (int)v49 + 1]) )
        v52 = v20;
      LODWORD(v136) = v51;
      v135 = *(_QWORD *)((char *)v26 + v33 + 40);
      LODWORD(v134) = *((_DWORD *)&off_180097840 + 6 * (int)v49 + 3);
      LODWORD(v129) = v52;
      ConditionFullTextInfo = StructuredQuery1::WriteFullTextDeep(
                                v29,
                                (&off_180097840)[3 * (int)v49],
                                0,
                                *(unsigned int *)((char *)v26 + v33 + 24));
      lpVtbl = (unsigned int)v144.lpVtbl;
      goto LABEL_92;
    }
    v42 = 0;
    v149 = 0;
    v43 = 0;
    pv = 0;
    if ( (v20 & 0x40) != 0 )
    {
      Alias = StructuredQuery1::VirtualPropertyMap::LookupVirtualProperty(
                v151,
                &PKEY_MOST_RELEVANT_PROPERTIES,
                (const struct StructuredQuery1::VIRTUAL_PROPERTY_INFO **)&pv);
      v43 = pv;
    }
    else
    {
      Alias = StructuredQuery1::VirtualPropertyMap::GetAlias(v41, &PKEY_MOST_RELEVANT_PROPERTIES, &v149);
      v42 = v149;
    }
    ConditionFullTextInfo = Alias;
    if ( Alias >= 0 )
    {
      LODWORD(v136) = (_DWORD)v146;
      v135 = *(_QWORD *)((char *)v26 + v33 + 40);
      LODWORD(v134) = 1;
      LODWORD(v129) = v20;
      ConditionFullTextInfo = StructuredQuery1::WriteFullTextDeep(
                                v147,
                                v42,
                                v43,
                                *(unsigned int *)((char *)v26 + v33 + 24));
      if ( ConditionFullTextInfo >= 0 )
      {
        if ( BYTE4(v144.lpVtbl) )
        {
          LODWORD(v136) = (_DWORD)v146;
          v135 = *(_QWORD *)((char *)v26 + v33 + 40);
          LODWORD(v134) = 2;
          LODWORD(v129) = v20;
          ConditionFullTextInfo = StructuredQuery1::WriteFullTextDeep(
                                    v147,
                                    v42,
                                    v43,
                                    *(unsigned int *)((char *)v26 + v33 + 24));
        }
        if ( ConditionFullTextInfo >= 0 )
        {
          v45 = (unsigned int)v144.lpVtbl;
          if ( LODWORD(v144.lpVtbl) > 1 )
          {
            LODWORD(v136) = (_DWORD)v146;
            v135 = *(_QWORD *)((char *)v26 + v33 + 40);
            LODWORD(v134) = 3;
            LODWORD(v129) = v20;
            ConditionFullTextInfo = StructuredQuery1::WriteFullTextDeep(
                                      v147,
                                      v42,
                                      v43,
                                      *(unsigned int *)((char *)v26 + v33 + 24));
            v45 = (unsigned int)v144.lpVtbl;
          }
          if ( ConditionFullTextInfo >= 0 )
          {
            if ( v45 > 1 && v143[0] )
            {
              LODWORD(v136) = (_DWORD)v146;
              v135 = *(_QWORD *)((char *)v26 + v33 + 40);
              LODWORD(v134) = 4;
              LODWORD(v129) = v20;
              v46 = v43;
              v47 = v147;
              ConditionFullTextInfo = StructuredQuery1::WriteFullTextDeep(
                                        v147,
                                        v42,
                                        v46,
                                        *(unsigned int *)((char *)v26 + v33 + 24));
            }
            else
            {
              v47 = v147;
            }
            if ( ConditionFullTextInfo >= 0 )
            {
              LODWORD(v136) = (_DWORD)v146;
              v135 = *(_QWORD *)((char *)v26 + v33 + 40);
              LODWORD(v134) = 1;
              LODWORD(v129) = v20;
              ConditionFullTextInfo = StructuredQuery1::WriteFullTextDeep(
                                        v47,
                                        L"*",
                                        0,
                                        *(unsigned int *)((char *)v26 + v33 + 24));
              if ( ConditionFullTextInfo >= 0 )
              {
                if ( BYTE4(v144.lpVtbl) )
                {
                  LODWORD(v136) = (_DWORD)v146;
                  v135 = *(_QWORD *)((char *)v26 + v33 + 40);
                  LODWORD(v134) = 2;
                  LODWORD(v129) = v20;
                  ConditionFullTextInfo = StructuredQuery1::WriteFullTextDeep(
                                            v47,
                                            L"*",
                                            0,
                                            *(unsigned int *)((char *)v26 + v33 + 24));
                }
                if ( ConditionFullTextInfo >= 0 )
                {
                  v48 = (unsigned int)v144.lpVtbl;
                  if ( LODWORD(v144.lpVtbl) > 1 )
                  {
                    LODWORD(v136) = (_DWORD)v146;
                    v135 = *(_QWORD *)((char *)v26 + v33 + 40);
                    LODWORD(v134) = 3;
                    LODWORD(v129) = v20;
                    ConditionFullTextInfo = StructuredQuery1::WriteFullTextDeep(
                                              v47,
                                              L"*",
                                              0,
                                              *(unsigned int *)((char *)v26 + v33 + 24));
                    v48 = (unsigned int)v144.lpVtbl;
                  }
                  if ( ConditionFullTextInfo >= 0 && v48 > 1 && v143[0] )
                  {
                    LODWORD(v136) = (_DWORD)v146;
                    v135 = *(_QWORD *)((char *)v26 + v33 + 40);
                    LODWORD(v134) = 4;
                    LODWORD(v129) = v20;
                    ConditionFullTextInfo = StructuredQuery1::WriteFullTextDeep(
                                              v47,
                                              L"*",
                                              0,
                                              *(unsigned int *)((char *)v26 + v33 + 24));
                  }
                }
              }
            }
          }
        }
      }
      CoTaskMemFree(v42);
LABEL_94:
      if ( ConditionFullTextInfo >= 0 )
        ConditionFullTextInfo = StringCchCopyExW(
                                  v140,
                                  (unsigned __int64)v141,
                                  L")",
                                  &v140,
                                  (unsigned __int64 *)&v141,
                                  (unsigned int)v134);
    }
LABEL_257:
    v31 = ++v154;
    if ( ConditionFullTextInfo < 0 )
      goto LABEL_273;
    v29 = v147;
    v30 = v153;
    v27 = v162;
  }
  v153 = v30 + 1;
  v53 = v146;
  if ( v30 )
    ConditionFullTextInfo = StringCchCopyExW(
                              v140,
                              (unsigned __int64)v141,
                              v146,
                              &v140,
                              (unsigned __int64 *)&v141,
                              (unsigned int)v134);
  if ( ConditionFullTextInfo < 0 )
    goto LABEL_257;
  LODWORD(v144.lpVtbl) = 0;
  ConditionFullTextInfo = (*(__int64 (__fastcall **)(_QWORD, IObjectArray *, __int64, const PROPERTYKEY *))(**(_QWORD **)((char *)v26 + v33 + 40) + 24LL))(
                            *(_QWORD *)((char *)v26 + v33 + 40),
                            &v144,
                            v28,
                            v32);
  if ( ConditionFullTextInfo < 0 )
    goto LABEL_257;
  v54 = 0;
  v149 = 0;
  pv = 0;
  ConditionFullTextInfo = ULongLongMult(LODWORD(v144.lpVtbl), 0x10u, (unsigned __int64 *)&pv);
  if ( ConditionFullTextInfo >= 0 )
  {
    ConditionFullTextInfo = CTCoAllocPolicy::Alloc(v55, 1, (SIZE_T)pv, (void **)&v149);
    v54 = v149;
  }
  if ( ConditionFullTextInfo < 0 )
  {
    v20 = a9;
    goto LABEL_257;
  }
  v56 = 0;
  while ( v56 < LODWORD(v144.lpVtbl) )
  {
    pv = 0;
    ConditionFullTextInfo = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, LPVOID *))(**(_QWORD **)((char *)v26 + v33 + 40)
                                                                                        + 32LL))(
                              *(_QWORD *)((char *)v26 + v33 + 40),
                              v56,
                              &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                              &pv);
    v142 = ConditionFullTextInfo;
    if ( ConditionFullTextInfo >= 0 )
    {
      LODWORD(v150) = 0;
      v166 = 0;
      v167 = 0;
      ConditionFullTextInfo = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *, __int128 *))(*(_QWORD *)pv + 128LL))(
                                pv,
                                0,
                                &v150,
                                &v166);
      v142 = ConditionFullTextInfo;
      if ( ConditionFullTextInfo >= 0 )
      {
        v57 = 2LL * v56;
        *(_QWORD *)&v54[4 * v57] = *((_QWORD *)&v166 + 1);
        *(_DWORD *)&v54[4 * v57 + 4] = v150;
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
    }
    ++v56;
    if ( ConditionFullTextInfo < 0 )
      goto LABEL_250;
  }
  if ( a7 )
  {
    if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_FI45262758>::GetImpl'::`2'::impl) )
      goto LABEL_173;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl'::`2'::impl) )
    {
      if ( !*(_DWORD *)(v14 + 96) )
      {
        v58 = *(_DWORD *)((char *)v26 + v33 + 28);
        if ( v58 )
        {
          v59 = *(_DWORD *)((char *)v26 + v33 + 32);
          v60 = 0;
          ConditionFullTextInfo = StringCchCopyExW(
                                    v140,
                                    (unsigned __int64)v141,
                                    L"(",
                                    &v140,
                                    (unsigned __int64 *)&v141,
                                    (unsigned int)v134);
          v142 = ConditionFullTextInfo;
          if ( ConditionFullTextInfo >= 0 && (v58 & 1) != 0 )
          {
            v62 = (int)v144.lpVtbl;
            IsPCSettingsQuery = PCSetting::s_IsPCSettingsQuery(v155);
            v64 = v59 <= 1;
            LOBYTE(v136) = 0;
            LOBYTE(v135) = IsPCSettingsQuery;
            LOBYTE(v129) = v59 <= 1;
            LOBYTE(v64) = 1;
            ConditionFullTextInfo = StructuredQuery1::SqlGenerator::WriteFullText(
                                      v152,
                                      v140,
                                      v141,
                                      v64,
                                      (_DWORD)v129,
                                      v59 <= 1,
                                      *(_DWORD *)((char *)v148 + v33 + 24),
                                      v135,
                                      a9,
                                      (_DWORD)v136,
                                      &PKEY_FullText,
                                      L"*",
                                      v54,
                                      v62,
                                      v151,
                                      v146,
                                      &v140,
                                      &v141);
            v142 = ConditionFullTextInfo;
            v60 = ConditionFullTextInfo >= 0;
          }
          pv = 0;
          FullPhrase = StructuredQuery1::SqlGenerator::GetFullPhrase(v61, v149, LODWORD(v144.lpVtbl), &pv);
          v68 = FullPhrase;
          if ( FullPhrase < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1729,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\structuredquery\\sqlgenerator\\generatesql.cpp",
              (const char *)(unsigned int)FullPhrase,
              (int)v129);
            goto LABEL_269;
          }
          if ( ConditionFullTextInfo < 0 )
            goto LABEL_141;
          v69 = pv;
          if ( (v58 & 2) != 0 )
          {
            v136 = &v141;
            LODWORD(v135) = v59;
            LOBYTE(v134) = 1;
            LOBYTE(v67) = v60;
            ConditionFullTextInfo = StructuredQuery1::SqlGenerator::WriteSemanticSearchContains(
                                      v66,
                                      v140,
                                      v141,
                                      v67,
                                      pv);
            v142 = ConditionFullTextInfo;
            if ( ConditionFullTextInfo < 0 )
            {
LABEL_141:
              p_pv = &pv;
LABEL_142:
              wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(p_pv);
LABEL_250:
              v20 = a9;
              goto LABEL_251;
            }
            v60 = 1;
          }
          if ( (v58 & 4) == 0
            || (v136 = &v141,
                LODWORD(v135) = v59,
                LOBYTE(v134) = 0,
                LOBYTE(v67) = v60,
                ConditionFullTextInfo = StructuredQuery1::SqlGenerator::WriteSemanticSearchContains(
                                          v66,
                                          v140,
                                          v141,
                                          v67,
                                          v69),
                v142 = ConditionFullTextInfo,
                ConditionFullTextInfo >= 0) )
          {
            ConditionFullTextInfo = StringCchCopyExW(
                                      v140,
                                      (unsigned __int64)v141,
                                      L")",
                                      &v140,
                                      (unsigned __int64 *)&v141,
                                      (unsigned int)v134);
            v142 = ConditionFullTextInfo;
            if ( ConditionFullTextInfo >= 0 )
            {
              ConditionFullTextInfo = StructuredQuery1::WriteMergeStrategy(v140, v141, (unsigned int)v59, &v140, &v141);
              v142 = ConditionFullTextInfo;
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54310796>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54310796>::GetImpl'::`2'::impl) )
            {
              if ( ConditionFullTextInfo >= 0 )
              {
                ConditionFullTextInfo = StringCchCopyExW(
                                          v140,
                                          (unsigned __int64)v141,
                                          L")",
                                          &v140,
                                          (unsigned __int64 *)&v141,
                                          (unsigned int)v134);
                v142 = ConditionFullTextInfo;
                if ( ConditionFullTextInfo >= 0 )
                {
                  v134 = (unsigned __int64 *)&v140;
                  ConditionFullTextInfo = StructuredQuery1::WriteRanking(980, 990, 2, v140, v141);
                  v142 = ConditionFullTextInfo;
                  if ( ConditionFullTextInfo >= 0 )
                  {
                    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl) )
                    {
                      std::wstring::wstring(v168, v69);
                      v70 = *(_QWORD *)(v152 + 72);
                      v71 = *(_QWORD *)(v152 + 80);
                      while ( v70 != v71 )
                      {
                        v72 = StructuredQuery1::WriteExternalSearchContains(
                                (_DWORD)v140,
                                (_DWORD)v141,
                                (unsigned int)&v140,
                                (unsigned int)&v141,
                                (__int64)v168,
                                v70);
                        v68 = v72;
                        if ( v72 < 0 )
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x176C,
                            (unsigned int)"onecoreuap\\base\\appmodel\\search\\structuredquery\\sqlgenerator\\generatesql.cpp",
                            (const char *)(unsigned int)v72,
                            v130);
                          std::wstring::_Tidy_deallocate(v168);
                          goto LABEL_269;
                        }
                        v70 += 32;
                      }
                      std::wstring::_Tidy_deallocate(v168);
                    }
                    ConditionFullTextInfo = StringCchCopyExW(
                                              v140,
                                              (unsigned __int64)v141,
                                              L")",
                                              &v140,
                                              (unsigned __int64 *)&v141,
                                              (unsigned int)v134);
                    v142 = ConditionFullTextInfo;
                  }
                }
              }
            }
          }
          goto LABEL_141;
        }
        goto LABEL_143;
      }
LABEL_173:
      v74 = (int)v144.lpVtbl;
      v75 = PCSetting::s_IsPCSettingsQuery(v155);
      v139 = v53;
      goto LABEL_174;
    }
    v76 = *(_DWORD *)((char *)v26 + v33 + 28);
    if ( !v76 )
    {
LABEL_143:
      v74 = (int)v144.lpVtbl;
      v75 = PCSetting::s_IsPCSettingsQuery(v155);
      v139 = v146;
LABEL_174:
      v137 = v54;
      LOBYTE(v136) = 0;
      v20 = a9;
      LOBYTE(v135) = v75;
      LOBYTE(v129) = 1;
      ConditionFullTextInfo = StructuredQuery1::SqlGenerator::WriteFullText(
                                v14,
                                v140,
                                v141,
                                0,
                                (_DWORD)v129,
                                1,
                                *(_DWORD *)((char *)v26 + v33 + 24),
                                v135,
                                a9,
                                (_DWORD)v136,
                                &PKEY_FullText,
                                L"*",
                                v137,
                                v74,
                                v151,
                                v139,
                                &v140,
                                &v141);
      v142 = ConditionFullTextInfo;
LABEL_251:
      v125 = 0;
      if ( LODWORD(v144.lpVtbl) )
      {
        v126 = v149;
        do
          CoTaskMemFree(*(LPVOID *)&v126[8 * v125++]);
        while ( v125 < LODWORD(v144.lpVtbl) );
        ConditionFullTextInfo = v142;
      }
      CoTaskMemFree(v149);
      v26 = v148;
      v14 = v152;
      goto LABEL_257;
    }
    v77 = *(_DWORD *)((char *)v26 + v33 + 32);
    v78 = 0;
    ConditionFullTextInfo = StringCchCopyExW(
                              v140,
                              (unsigned __int64)v141,
                              L"(",
                              &v140,
                              (unsigned __int64 *)&v141,
                              (unsigned int)v134);
    v142 = ConditionFullTextInfo;
    if ( ConditionFullTextInfo >= 0 && (v76 & 1) != 0 )
    {
      v80 = (int)v144.lpVtbl;
      v81 = PCSetting::s_IsPCSettingsQuery(v155);
      v82 = v77 <= 1;
      LOBYTE(v136) = 0;
      LOBYTE(v135) = v81;
      LOBYTE(v129) = v77 <= 1;
      LOBYTE(v82) = 1;
      ConditionFullTextInfo = StructuredQuery1::SqlGenerator::WriteFullText(
                                v152,
                                v140,
                                v141,
                                v82,
                                (_DWORD)v129,
                                v77 <= 1,
                                *(_DWORD *)((char *)v148 + v33 + 24),
                                v135,
                                a9,
                                (_DWORD)v136,
                                &PKEY_FullText,
                                L"*",
                                v54,
                                v80,
                                v151,
                                v146,
                                &v140,
                                &v141);
      v142 = ConditionFullTextInfo;
      v78 = ConditionFullTextInfo >= 0;
    }
    v150 = 0;
    v83 = StructuredQuery1::SqlGenerator::GetFullPhrase(v79, v149, LODWORD(v144.lpVtbl), &v150);
    v68 = v83;
    if ( v83 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17C9,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\structuredquery\\sqlgenerator\\generatesql.cpp",
        (const char *)(unsigned int)v83,
        (int)v129);
LABEL_263:
      v127 = (void **)&v150;
      goto LABEL_270;
    }
    if ( ConditionFullTextInfo >= 0 )
    {
      v86 = v150;
      v87 = v152;
      if ( (v76 & 2) == 0 || *(_DWORD *)(v152 + 96) )
      {
LABEL_154:
        if ( (v76 & 4) != 0 && !*(_DWORD *)(v87 + 96) )
        {
          v136 = &v141;
          LODWORD(v135) = v77;
          LOBYTE(v134) = 0;
          LOBYTE(v85) = v78;
          ConditionFullTextInfo = StructuredQuery1::SqlGenerator::WriteSemanticSearchContains(v84, v140, v141, v85, v86);
          v142 = ConditionFullTextInfo;
        }
        if ( ConditionFullTextInfo >= 0 )
        {
          ConditionFullTextInfo = StringCchCopyExW(
                                    v140,
                                    (unsigned __int64)v141,
                                    L")",
                                    &v140,
                                    (unsigned __int64 *)&v141,
                                    (unsigned int)v134);
          v142 = ConditionFullTextInfo;
          if ( ConditionFullTextInfo >= 0 )
          {
            ConditionFullTextInfo = StructuredQuery1::WriteMergeStrategy(v140, v141, (unsigned int)v77, &v140, &v141);
            v142 = ConditionFullTextInfo;
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54310796>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54310796>::GetImpl'::`2'::impl) )
          {
            if ( ConditionFullTextInfo >= 0 )
            {
              ConditionFullTextInfo = StringCchCopyExW(
                                        v140,
                                        (unsigned __int64)v141,
                                        L")",
                                        &v140,
                                        (unsigned __int64 *)&v141,
                                        (unsigned int)v134);
              v142 = ConditionFullTextInfo;
              if ( ConditionFullTextInfo >= 0 )
              {
                v134 = (unsigned __int64 *)&v140;
                ConditionFullTextInfo = StructuredQuery1::WriteRanking(980, 990, 2, v140, v141);
                v142 = ConditionFullTextInfo;
                if ( ConditionFullTextInfo >= 0 )
                {
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl)
                    && !*(_DWORD *)(v87 + 96) )
                  {
                    std::wstring::wstring(v169, v86);
                    v88 = *(_QWORD *)(v87 + 72);
                    v89 = *(_QWORD *)(v87 + 80);
                    while ( v88 != v89 )
                    {
                      v90 = StructuredQuery1::WriteExternalSearchContains(
                              (_DWORD)v140,
                              (_DWORD)v141,
                              (unsigned int)&v140,
                              (unsigned int)&v141,
                              (__int64)v169,
                              v88);
                      v68 = v90;
                      if ( v90 < 0 )
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x1810,
                          (unsigned int)"onecoreuap\\base\\appmodel\\search\\structuredquery\\sqlgenerator\\generatesql.cpp",
                          (const char *)(unsigned int)v90,
                          v131);
                        std::wstring::_Tidy_deallocate(v169);
                        goto LABEL_263;
                      }
                      v88 += 32;
                    }
                    std::wstring::_Tidy_deallocate(v169);
                  }
                  ConditionFullTextInfo = StringCchCopyExW(
                                            v140,
                                            (unsigned __int64)v141,
                                            L")",
                                            &v140,
                                            (unsigned __int64 *)&v141,
                                            (unsigned int)v134);
                  v142 = ConditionFullTextInfo;
                }
              }
            }
          }
        }
        goto LABEL_172;
      }
      v136 = &v141;
      LODWORD(v135) = v77;
      LOBYTE(v134) = 1;
      LOBYTE(v85) = v78;
      ConditionFullTextInfo = StructuredQuery1::SqlGenerator::WriteSemanticSearchContains(v84, v140, v141, v85, v150);
      v142 = ConditionFullTextInfo;
      if ( ConditionFullTextInfo >= 0 )
      {
        v78 = 1;
        goto LABEL_154;
      }
    }
LABEL_172:
    p_pv = (void **)&v150;
    goto LABEL_142;
  }
  ConditionFullTextInfo = StringCchCopyExW(
                            v140,
                            (unsigned __int64)v141,
                            L"(",
                            &v140,
                            (unsigned __int64 *)&v141,
                            (unsigned int)v134);
  v142 = ConditionFullTextInfo;
  v91 = 0;
  LODWORD(v150) = 0;
  if ( ConditionFullTextInfo < 0 )
    goto LABEL_250;
  while ( 1 )
  {
    if ( v91 >= LODWORD(v144.lpVtbl) )
    {
      ConditionFullTextInfo = StringCchCopyExW(
                                v140,
                                (unsigned __int64)v141,
                                L")",
                                &v140,
                                (unsigned __int64 *)&v141,
                                (unsigned int)v134);
      v142 = ConditionFullTextInfo;
      goto LABEL_250;
    }
    if ( v91 )
    {
      ConditionFullTextInfo = StringCchCopyExW(
                                v140,
                                (unsigned __int64)v141,
                                L" OR ",
                                &v140,
                                (unsigned __int64 *)&v141,
                                (unsigned int)v134);
      v142 = ConditionFullTextInfo;
    }
    if ( ConditionFullTextInfo < 0 )
      goto LABEL_213;
    if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_FI45262758>::GetImpl'::`2'::impl) )
      goto LABEL_185;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl'::`2'::impl) )
      break;
    if ( !*(_DWORD *)(v14 + 96) )
    {
      v93 = *(_DWORD *)((char *)v26 + v33 + 28);
      if ( v93 )
      {
        v94 = *(_DWORD *)((char *)v26 + v33 + 32);
        v95 = 0;
        ConditionFullTextInfo = StringCchCopyExW(
                                  v140,
                                  (unsigned __int64)v141,
                                  L"(",
                                  &v140,
                                  (unsigned __int64 *)&v141,
                                  (unsigned int)v134);
        v142 = ConditionFullTextInfo;
        if ( ConditionFullTextInfo >= 0 && (v93 & 1) != 0 )
        {
          v97 = PCSetting::s_IsPCSettingsQuery(v155);
          v98 = 8LL * v91;
          v99 = v149;
          LOBYTE(v136) = 0;
          LOBYTE(v135) = v97;
          LOBYTE(v129) = v94 <= 1;
          LOBYTE(v100) = 1;
          ConditionFullTextInfo = StructuredQuery1::SqlGenerator::WriteFullText(
                                    v152,
                                    v140,
                                    v141,
                                    v100,
                                    (_DWORD)v129,
                                    v94 <= 1,
                                    *(_DWORD *)((char *)v26 + v33 + 24),
                                    v135,
                                    a9,
                                    (_DWORD)v136,
                                    &PKEY_FullText,
                                    L"*",
                                    &v149[v98],
                                    1,
                                    v151,
                                    v146,
                                    &v140,
                                    &v141);
          v142 = ConditionFullTextInfo;
          v95 = ConditionFullTextInfo >= 0;
        }
        else
        {
          v99 = v149;
        }
        pv = 0;
        v101 = StructuredQuery1::SqlGenerator::GetFullPhrase(v96, v99, LODWORD(v144.lpVtbl), &pv);
        v68 = v101;
        if ( v101 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x18AF,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\structuredquery\\sqlgenerator\\generatesql.cpp",
            (const char *)(unsigned int)v101,
            (int)v129);
          goto LABEL_269;
        }
        if ( ConditionFullTextInfo < 0 )
          goto LABEL_212;
        v104 = pv;
        if ( (v93 & 2) != 0 )
        {
          v136 = &v141;
          LODWORD(v135) = v94;
          LOBYTE(v134) = 1;
          LOBYTE(v103) = v95;
          ConditionFullTextInfo = StructuredQuery1::SqlGenerator::WriteSemanticSearchContains(
                                    v102,
                                    v140,
                                    v141,
                                    v103,
                                    pv);
          v142 = ConditionFullTextInfo;
          if ( ConditionFullTextInfo >= 0 )
          {
            v95 = 1;
            goto LABEL_196;
          }
        }
        else
        {
LABEL_196:
          if ( (v93 & 4) == 0
            || (v136 = &v141,
                LODWORD(v135) = v94,
                LOBYTE(v134) = 0,
                LOBYTE(v103) = v95,
                ConditionFullTextInfo = StructuredQuery1::SqlGenerator::WriteSemanticSearchContains(
                                          v102,
                                          v140,
                                          v141,
                                          v103,
                                          v104),
                v142 = ConditionFullTextInfo,
                ConditionFullTextInfo >= 0) )
          {
            ConditionFullTextInfo = StringCchCopyExW(
                                      v140,
                                      (unsigned __int64)v141,
                                      L")",
                                      &v140,
                                      (unsigned __int64 *)&v141,
                                      (unsigned int)v134);
            v142 = ConditionFullTextInfo;
            if ( ConditionFullTextInfo >= 0 )
            {
              ConditionFullTextInfo = StructuredQuery1::WriteMergeStrategy(v140, v141, (unsigned int)v94, &v140, &v141);
              v142 = ConditionFullTextInfo;
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54310796>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54310796>::GetImpl'::`2'::impl) )
            {
              if ( ConditionFullTextInfo >= 0 )
              {
                ConditionFullTextInfo = StringCchCopyExW(
                                          v140,
                                          (unsigned __int64)v141,
                                          L")",
                                          &v140,
                                          (unsigned __int64 *)&v141,
                                          (unsigned int)v134);
                v142 = ConditionFullTextInfo;
                if ( ConditionFullTextInfo >= 0 )
                {
                  v134 = (unsigned __int64 *)&v140;
                  ConditionFullTextInfo = StructuredQuery1::WriteRanking(980, 990, 2, v140, v141);
                  v142 = ConditionFullTextInfo;
                  if ( ConditionFullTextInfo >= 0 )
                  {
                    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl) )
                    {
                      std::wstring::wstring(v170, v104);
                      v105 = *(_QWORD *)(v152 + 72);
                      v106 = *(_QWORD *)(v152 + 80);
                      while ( v105 != v106 )
                      {
                        v107 = StructuredQuery1::WriteExternalSearchContains(
                                 (_DWORD)v140,
                                 (_DWORD)v141,
                                 (unsigned int)&v140,
                                 (unsigned int)&v141,
                                 (__int64)v170,
                                 v105);
                        v68 = v107;
                        if ( v107 < 0 )
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x18F3,
                            (unsigned int)"onecoreuap\\base\\appmodel\\search\\structuredquery\\sqlgenerator\\generatesql.cpp",
                            (const char *)(unsigned int)v107,
                            v132);
                          std::wstring::_Tidy_deallocate(v170);
                          goto LABEL_269;
                        }
                        v105 += 32;
                      }
                      std::wstring::_Tidy_deallocate(v170);
                    }
                    ConditionFullTextInfo = StringCchCopyExW(
                                              v140,
                                              (unsigned __int64)v141,
                                              L")",
                                              &v140,
                                              (unsigned __int64 *)&v141,
                                              (unsigned int)v134);
                    v142 = ConditionFullTextInfo;
                  }
                }
              }
            }
          }
        }
        v26 = v148;
        goto LABEL_212;
      }
LABEL_247:
      v92 = PCSetting::s_IsPCSettingsQuery(v155);
      v53 = v146;
      goto LABEL_248;
    }
LABEL_185:
    v92 = PCSetting::s_IsPCSettingsQuery(v155);
LABEL_248:
    v138 = &v54[8 * v91];
    LOBYTE(v136) = 0;
    v20 = a9;
    LOBYTE(v135) = v92;
    LOBYTE(v129) = 1;
    ConditionFullTextInfo = StructuredQuery1::SqlGenerator::WriteFullText(
                              v14,
                              v140,
                              v141,
                              0,
                              (_DWORD)v129,
                              1,
                              *(_DWORD *)((char *)v26 + v33 + 24),
                              v135,
                              a9,
                              (_DWORD)v136,
                              &PKEY_FullText,
                              L"*",
                              v138,
                              1,
                              v151,
                              v53,
                              &v140,
                              &v141);
    v142 = ConditionFullTextInfo;
LABEL_214:
    LODWORD(v150) = ++v91;
    if ( ConditionFullTextInfo < 0 )
      goto LABEL_251;
    v54 = v149;
  }
  v108 = *(_DWORD *)((char *)v26 + v33 + 28);
  if ( !v108 )
    goto LABEL_247;
  v109 = *(_DWORD *)((char *)v26 + v33 + 32);
  v110 = 0;
  ConditionFullTextInfo = StringCchCopyExW(
                            v140,
                            (unsigned __int64)v141,
                            L"(",
                            &v140,
                            (unsigned __int64 *)&v141,
                            (unsigned int)v134);
  v142 = ConditionFullTextInfo;
  if ( ConditionFullTextInfo >= 0 && (v108 & 1) != 0 )
  {
    v112 = PCSetting::s_IsPCSettingsQuery(v155);
    v113 = 8LL * v91;
    v114 = v149;
    LOBYTE(v136) = 0;
    LOBYTE(v135) = v112;
    LOBYTE(v129) = v109 <= 1;
    LOBYTE(v115) = 1;
    ConditionFullTextInfo = StructuredQuery1::SqlGenerator::WriteFullText(
                              v152,
                              v140,
                              v141,
                              v115,
                              (_DWORD)v129,
                              v109 <= 1,
                              *(_DWORD *)((char *)v26 + v33 + 24),
                              v135,
                              a9,
                              (_DWORD)v136,
                              &PKEY_FullText,
                              L"*",
                              &v149[v113],
                              1,
                              v151,
                              v146,
                              &v140,
                              &v141);
    v142 = ConditionFullTextInfo;
    v110 = ConditionFullTextInfo >= 0;
  }
  else
  {
    v114 = v149;
  }
  pv = 0;
  v116 = StructuredQuery1::SqlGenerator::GetFullPhrase(v111, v114, LODWORD(v144.lpVtbl), &pv);
  v68 = v116;
  if ( v116 >= 0 )
  {
    if ( ConditionFullTextInfo >= 0 )
    {
      v119 = pv;
      if ( (v108 & 2) == 0 || *(_DWORD *)(v152 + 96) )
        goto LABEL_227;
      v136 = &v141;
      LODWORD(v135) = v109;
      LOBYTE(v134) = 1;
      LOBYTE(v118) = v110;
      ConditionFullTextInfo = StructuredQuery1::SqlGenerator::WriteSemanticSearchContains(v117, v140, v141, v118, pv);
      v142 = ConditionFullTextInfo;
      if ( ConditionFullTextInfo >= 0 )
      {
        v110 = 1;
LABEL_227:
        v120 = (v108 & 4) == 0;
        v121 = v152;
        if ( !v120 && !*(_DWORD *)(v152 + 96) )
        {
          v136 = &v141;
          LODWORD(v135) = v109;
          LOBYTE(v134) = 0;
          LOBYTE(v118) = v110;
          ConditionFullTextInfo = StructuredQuery1::SqlGenerator::WriteSemanticSearchContains(
                                    v117,
                                    v140,
                                    v141,
                                    v118,
                                    v119);
          v142 = ConditionFullTextInfo;
        }
        if ( ConditionFullTextInfo >= 0 )
        {
          ConditionFullTextInfo = StringCchCopyExW(
                                    v140,
                                    (unsigned __int64)v141,
                                    L")",
                                    &v140,
                                    (unsigned __int64 *)&v141,
                                    (unsigned int)v134);
          v142 = ConditionFullTextInfo;
          if ( ConditionFullTextInfo >= 0 )
          {
            ConditionFullTextInfo = StructuredQuery1::WriteMergeStrategy(v140, v141, (unsigned int)v109, &v140, &v141);
            v142 = ConditionFullTextInfo;
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54310796>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54310796>::GetImpl'::`2'::impl) )
          {
            if ( ConditionFullTextInfo >= 0 )
            {
              ConditionFullTextInfo = StringCchCopyExW(
                                        v140,
                                        (unsigned __int64)v141,
                                        L")",
                                        &v140,
                                        (unsigned __int64 *)&v141,
                                        (unsigned int)v134);
              v142 = ConditionFullTextInfo;
              if ( ConditionFullTextInfo >= 0 )
              {
                v134 = (unsigned __int64 *)&v140;
                ConditionFullTextInfo = StructuredQuery1::WriteRanking(980, 990, 2, v140, v141);
                v142 = ConditionFullTextInfo;
                if ( ConditionFullTextInfo >= 0 )
                {
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl)
                    && !*(_DWORD *)(v121 + 96) )
                  {
                    std::wstring::wstring(v171, v119);
                    v122 = *(_QWORD *)(v121 + 72);
                    v123 = *(_QWORD *)(v121 + 80);
                    while ( v122 != v123 )
                    {
                      v124 = StructuredQuery1::WriteExternalSearchContains(
                               (_DWORD)v140,
                               (_DWORD)v141,
                               (unsigned int)&v140,
                               (unsigned int)&v141,
                               (__int64)v171,
                               v122);
                      v68 = v124;
                      if ( v124 < 0 )
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x1997,
                          (unsigned int)"onecoreuap\\base\\appmodel\\search\\structuredquery\\sqlgenerator\\generatesql.cpp",
                          (const char *)(unsigned int)v124,
                          v133);
                        std::wstring::_Tidy_deallocate(v171);
                        goto LABEL_269;
                      }
                      v122 += 32;
                    }
                    std::wstring::_Tidy_deallocate(v171);
                  }
                  ConditionFullTextInfo = StringCchCopyExW(
                                            v140,
                                            (unsigned __int64)v141,
                                            L")",
                                            &v140,
                                            (unsigned __int64 *)&v141,
                                            (unsigned int)v134);
                  v142 = ConditionFullTextInfo;
                }
              }
            }
          }
        }
      }
      v26 = v148;
    }
LABEL_212:
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&pv);
    v91 = v150;
    v14 = v152;
    v53 = v146;
LABEL_213:
    v20 = a9;
    goto LABEL_214;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x194F,
    (unsigned int)"onecoreuap\\base\\appmodel\\search\\structuredquery\\sqlgenerator\\generatesql.cpp",
    (const char *)(unsigned int)v116,
    (int)v129);
LABEL_269:
  v127 = &pv;
LABEL_270:
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(v127);
  StructuredQuery1::ConditionGroupManager::~ConditionGroupManager((StructuredQuery1::ConditionGroupManager *)&v163);
  return v68;
}

```

## disassembly

```asm
0x18004bb94  push    rbp
0x18004bb96  push    rbx
0x18004bb97  push    rsi
0x18004bb98  push    rdi
0x18004bb99  push    r12
0x18004bb9b  push    r13
0x18004bb9d  push    r14
0x18004bb9f  push    r15
0x18004bba1  lea     rbp, [rsp-0E8h]
0x18004bba9  sub     rsp, 1F8h
0x18004bbb0  mov     rax, cs:__security_cookie
0x18004bbb7  xor     rax, rsp
0x18004bbba  mov     [rbp+120h+var_50], rax
0x18004bbc1  mov     [rbp+120h+var_138], r9
0x18004bbc5  mov     r15, rcx
0x18004bbc8  mov     [rbp+120h+var_148], rcx
0x18004bbcc  mov     [rbp+120h+var_1A0], rdx
0x18004bbd0  mov     [rbp+120h+var_198], r8
0x18004bbd4  mov     rax, [rbp+120h+arg_28]
0x18004bbdb  mov     [rbp+120h+var_178], rax
0x18004bbdf  mov     rax, [rbp+120h+arg_50]
0x18004bbe6  mov     [rbp+120h+var_150], rax
0x18004bbea  mov     rbx, [rbp+120h+arg_60]
0x18004bbf1  mov     [rbp+120h+var_128], rbx
0x18004bbf5  mov     rsi, [rbp+120h+arg_68]
0x18004bbfc  mov     [rbp+120h+var_120], rsi
0x18004bc00  xor     r14d, r14d
0x18004bc03  mov     [rbp+120h+var_110], r14
0x18004bc07  mov     rax, [r9]
0x18004bc0a  lea     r8, [rbp+120h+var_110]
0x18004bc0e  lea     rdx, _GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9
0x18004bc15  mov     rcx, r9
0x18004bc18  mov     rax, [rax+48h]
0x18004bc1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bc21  mov     edi, eax
0x18004bc23  test    eax, eax
0x18004bc25  js      loc_18004D906
0x18004bc2b  mov     dword ptr [rbp+120h+var_130], r14d
0x18004bc2f  mov     rcx, [rbp+120h+var_110]
0x18004bc33  mov     rax, [rcx]
0x18004bc36  lea     rdx, [rbp+120h+var_130]
0x18004bc3a  mov     rax, [rax+18h]
0x18004bc3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bc43  mov     edi, eax
0x18004bc45  test    eax, eax
0x18004bc47  js      loc_18004D8F6
0x18004bc4d  mov     ecx, dword ptr [rbp+120h+var_130]
0x18004bc50  mov     r13d, [rbp+120h+arg_40]
0x18004bc57  mov     eax, r13d
0x18004bc5a  and     eax, 2
0x18004bc5d  mov     [rbp+120h+var_118], eax
0x18004bc60  jz      short loc_18004BC82
0x18004bc62  mov     edx, ecx; struct IObjectArray *
0x18004bc64  mov     rcx, [rbp+120h+var_110]; this
0x18004bc68  call    ?GetRankableSubConditionCount@StructuredQuery1@@YAIPEAUIObjectArray@@I@Z; StructuredQuery1::GetRankableSubConditionCount(IObjectArray *,uint)
0x18004bc6d  mov     edx, dword ptr [rbp+120h+var_130]
0x18004bc70  add     edx, eax
0x18004bc72  or      ecx, 0FFFFFFFFh
0x18004bc75  cmp     edx, eax
0x18004bc77  cmovnb  ecx, edx
0x18004bc7a  sbb     edi, edi
0x18004bc7c  and     edi, 80070216h
0x18004bc82  test    edi, edi
0x18004bc84  js      loc_18004D8F6
0x18004bc8a  mov     [rbp+120h+var_100], r14
0x18004bc8e  mov     [rbp+120h+var_F8], r14
0x18004bc92  mov     [rbp+120h+var_F0], r14b
0x18004bc96  mov     edx, ecx; unsigned int
0x18004bc98  lea     rcx, [rbp+120h+var_100]; this
0x18004bc9c  call    ?Initialize@ConditionGroupManager@StructuredQuery1@@QEAAJK@Z; StructuredQuery1::ConditionGroupManager::Initialize(ulong)
0x18004bca1  mov     edi, eax
0x18004bca3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60157349@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60157349@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349> `wil::Feature<__WilFeatureTraits_Feature_60157349>::GetImpl(void)'::`2'::impl
0x18004bcaa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60157349@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60157349>::__private_IsEnabled(void)
0x18004bcaf  test    al, al
0x18004bcb1  jz      short loc_18004BCBD
0x18004bcb3  cmp     [r15+60h], r14d
0x18004bcb7  setnz   [rbp+120h+var_F0]
0x18004bcbb  jmp     short loc_18004BCC5
0x18004bcbd  test    edi, edi
0x18004bcbf  js      loc_18004D8ED
0x18004bcc5  mov     ebx, r14d
0x18004bcc8  mov     r12d, 1
0x18004bcce  cmp     ebx, dword ptr [rbp+120h+var_130]
0x18004bcd1  jnb     short loc_18004BD28
0x18004bcd3  mov     [rbp+120h+pv], r14
0x18004bcd7  mov     rcx, [rbp+120h+var_110]
0x18004bcdb  mov     rax, [rcx]
0x18004bcde  lea     r9, [rbp+120h+pv]
0x18004bce2  lea     r8, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x18004bce9  mov     edx, ebx
0x18004bceb  mov     rax, [rax+20h]
0x18004bcef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bcf4  mov     edi, eax
0x18004bcf6  test    eax, eax
0x18004bcf8  js      short loc_18004BD1C
0x18004bcfa  mov     r8, [rbp+120h+pv]
0x18004bcfe  mov     edx, r13d
0x18004bd01  lea     rcx, [rbp+120h+var_100]
0x18004bd05  call    ?AddConjunct@ConditionGroupManager@StructuredQuery1@@QEAAJW4SQL_GENERATION_OPTIONS@@PEAUICondition2@@@Z; StructuredQuery1::ConditionGroupManager::AddConjunct(SQL_GENERATION_OPTIONS,ICondition2 *)
0x18004bd0a  mov     edi, eax
0x18004bd0c  mov     rcx, [rbp+120h+pv]
0x18004bd10  mov     rax, [rcx]
0x18004bd13  mov     rax, [rax+10h]
0x18004bd17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd1c  add     ebx, r12d
0x18004bd1f  test    edi, edi
0x18004bd21  jns     short loc_18004BCCE
0x18004bd23  jmp     loc_18004D8E9
0x18004bd28  cmp     [rbp+120h+arg_48], r14b
0x18004bd2f  jz      short loc_18004BD61
0x18004bd31  lea     rax, [rbp+120h+var_198]
0x18004bd35  mov     [rsp+230h+var_210], rax; wchar_t **
0x18004bd3a  lea     r9, [rbp+120h+var_1A0]; bool
0x18004bd3e  mov     r8b, r12b; unsigned __int64
0x18004bd41  mov     rdx, [rbp+120h+var_198]; wchar_t *
0x18004bd45  mov     rcx, [rbp+120h+var_1A0]; this
0x18004bd49  call    ?WriteNot@StructuredQuery1@@YAJPEA_W_K_NPEAPEA_WPEA_K@Z; StructuredQuery1::WriteNot(wchar_t *,unsigned __int64,bool,wchar_t * *,unsigned __int64 *)
0x18004bd4e  mov     edi, eax
0x18004bd50  mov     ebx, 2
0x18004bd55  mov     dword ptr [rbp+120h+var_130+4], ebx
0x18004bd58  test    eax, eax
0x18004bd5a  jns     short loc_18004BD6A
0x18004bd5c  jmp     loc_18004D8E9
0x18004bd61  mov     ebx, [rbp+120h+arg_38]
0x18004bd67  mov     dword ptr [rbp+120h+var_130+4], ebx
0x18004bd6a  mov     r12, [rbp+120h+var_100]
0x18004bd6e  mov     [rbp+120h+var_168], r12
0x18004bd72  mov     esi, dword ptr [rbp+120h+var_F8+4]
0x18004bd75  mov     [rbp+120h+var_108], esi
0x18004bd78  mov     [rbp+120h+var_13C], r14d
0x18004bd7c  lea     r8, [rbp+120h+var_13C]; unsigned int
0x18004bd80  mov     edx, esi; struct StructuredQuery1::CONDITION_GROUP *
0x18004bd82  mov     rcx, r12; this
0x18004bd85  call    ?TotalSubsToWrite@StructuredQuery1@@YAJPEAUCONDITION_GROUP@1@KPEAK@Z; StructuredQuery1::TotalSubsToWrite(StructuredQuery1::CONDITION_GROUP *,ulong,ulong *)
0x18004bd8a  mov     edi, eax
0x18004bd8c  test    eax, eax
0x18004bd8e  js      loc_18004D8E5
0x18004bd94  cmp     [rbp+120h+var_13C], 1
0x18004bd98  jnz     short loc_18004BDAC
0x18004bd9a  mov     r14d, ebx
0x18004bd9d  mov     [rbp+120h+var_170], ebx
0x18004bda0  xor     edx, edx
0x18004bda2  mov     [rbp+120h+var_140], edx
0x18004bda5  xor     eax, eax
0x18004bda7  mov     [rbp+120h+var_13C], eax
0x18004bdaa  jmp     short loc_18004BDF7
0x18004bdac  mov     r14d, [rbp+120h+arg_20]
0x18004bdb3  mov     [rbp+120h+var_170], r14d
0x18004bdb7  cmp     r14d, ebx
0x18004bdba  jge     short loc_18004BDE1
0x18004bdbc  lea     rax, [rbp+120h+var_198]
0x18004bdc0  mov     [rsp+230h+var_210], rax; unsigned __int64 *
0x18004bdc5  lea     r9, [rbp+120h+var_1A0]; wchar_t **
0x18004bdc9  lea     r8, asc_18009B4D0; "("
0x18004bdd0  mov     rdx, [rbp+120h+var_198]; unsigned __int64
0x18004bdd4  mov     rcx, [rbp+120h+var_1A0]; wchar_t *
0x18004bdd8  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18004bddd  mov     edi, eax
0x18004bddf  jmp     short loc_18004BDE5
0x18004bde1  mov     [rbp+120h+var_170], r14d
0x18004bde5  xor     edx, edx
0x18004bde7  mov     [rbp+120h+var_140], edx
0x18004bdea  xor     eax, eax
0x18004bdec  mov     [rbp+120h+var_13C], eax
0x18004bdef  test    edi, edi
0x18004bdf1  js      loc_18004D8E5
0x18004bdf7  lea     r9, PKEY_FullText
0x18004bdfe  cmp     eax, esi
0x18004be00  jnb     loc_18004D8BC
0x18004be06  lea     rsi, [rax+rax*2]
0x18004be0a  shl     rsi, 4
0x18004be0e  mov     ecx, [rsi+r12]
0x18004be12  test    ecx, ecx
0x18004be14  jz      loc_18004C5CD
0x18004be1a  sub     ecx, 1
0x18004be1d  jz      loc_18004BF28
0x18004be23  cmp     ecx, 1
0x18004be26  jnz     loc_18004D779
0x18004be2c  mov     dword ptr [rbp+120h+var_158], 0
0x18004be33  mov     rcx, [rsi+r12+28h]
0x18004be38  mov     rax, [rcx]
0x18004be3b  lea     rdx, [rbp+120h+var_158]
0x18004be3f  mov     rax, [rax+18h]
0x18004be43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be48  mov     edi, eax
0x18004be4a  test    eax, eax
0x18004be4c  js      loc_18004D75A
0x18004be52  xor     ebx, ebx
0x18004be54  cmp     ebx, dword ptr [rbp+120h+var_158]
0x18004be57  jnb     loc_18004D75A
0x18004be5d  mov     [rbp+120h+pv], 0
0x18004be65  mov     rcx, [rsi+r12+28h]
0x18004be6a  mov     rax, [rcx]
0x18004be6d  lea     r9, [rbp+120h+pv]
0x18004be71  lea     r8, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x18004be78  mov     edx, ebx
0x18004be7a  mov     rax, [rax+20h]
0x18004be7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be83  mov     edi, eax
0x18004be85  test    eax, eax
0x18004be87  js      loc_18004BF19
0x18004be8d  mov     ecx, [rbp+120h+var_140]
0x18004be90  mov     eax, ecx
0x18004be92  inc     ecx
0x18004be94  mov     [rbp+120h+var_140], ecx
0x18004be97  test    eax, eax
0x18004be99  jz      short loc_18004BEBF
0x18004be9b  lea     rax, [rbp+120h+var_198]
0x18004be9f  mov     [rsp+230h+var_210], rax; unsigned __int64 *
0x18004bea4  lea     r9, [rbp+120h+var_1A0]; wchar_t **
0x18004bea8  mov     r8, [rbp+120h+var_178]; wchar_t *
0x18004beac  mov     rdx, [rbp+120h+var_198]; unsigned __int64
0x18004beb0  mov     rcx, [rbp+120h+var_1A0]; wchar_t *
0x18004beb4  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18004beb9  mov     edi, eax
0x18004bebb  test    eax, eax
0x18004bebd  js      short loc_18004BF09
0x18004bebf  lea     rax, [rbp+120h+var_198]
0x18004bec3  mov     [rsp+230h+var_1E0], rax
0x18004bec8  lea     rax, [rbp+120h+var_1A0]
0x18004becc  mov     [rsp+230h+var_1E8], rax
0x18004bed1  mov     al, [rbp+120h+arg_58]
0x18004bed7  mov     byte ptr [rsp+230h+var_1F0], al
0x18004bedb  mov     rax, [rbp+120h+var_150]
0x18004bedf  mov     [rsp+230h+var_1F8], rax
0x18004bee4  mov     byte ptr [rsp+230h+var_200], 0
0x18004bee9  mov     [rsp+230h+var_208], r13d
0x18004beee  mov     dword ptr [rsp+230h+var_210], r14d
0x18004bef3  mov     r9, [rbp+120h+pv]
0x18004bef7  mov     r8, [rbp+120h+var_198]
0x18004befb  mov     rdx, [rbp+120h+var_1A0]
0x18004beff  mov     rcx, r15
0x18004bf02  call    ?WriteSql@SqlGenerator@StructuredQuery1@@AEAAJPEA_W_KPEAUICondition2@@HW4SQL_GENERATION_OPTIONS@@_NPEAVVirtualPropertyMap@2@4PEAPEA_WPEA_K@Z; StructuredQuery1::SqlGenerator::WriteSql(wchar_t *,unsigned __int64,ICondition2 *,int,SQL_GENERATION_OPTIONS,bool,StructuredQuery1::VirtualPropertyMap *,bool,wchar_t * *,unsigned __int64 *)
0x18004bf07  mov     edi, eax
0x18004bf09  mov     rcx, [rbp+120h+pv]
0x18004bf0d  mov     rax, [rcx]
0x18004bf10  mov     rax, [rax+10h]
0x18004bf14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf19  inc     ebx
0x18004bf1b  test    edi, edi
0x18004bf1d  jns     loc_18004BE54
0x18004bf23  jmp     loc_18004D8E5
0x18004bf28  mov     eax, edx
0x18004bf2a  inc     edx
0x18004bf2c  mov     [rbp+120h+var_140], edx
0x18004bf2f  mov     rbx, [rbp+120h+var_178]
0x18004bf33  test    eax, eax
0x18004bf35  jz      short loc_18004BF5D
0x18004bf37  lea     rax, [rbp+120h+var_198]
0x18004bf3b  mov     [rsp+230h+var_210], rax; unsigned int *
0x18004bf40  lea     r9, [rbp+120h+var_1A0]; wchar_t **
0x18004bf44  mov     r8, rbx; wchar_t *
0x18004bf47  mov     rdx, [rbp+120h+var_198]; unsigned __int64
0x18004bf4b  mov     rcx, [rbp+120h+var_1A0]; wchar_t *
0x18004bf4f  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18004bf54  mov     edi, eax
0x18004bf56  lea     r9, PKEY_FullText
0x18004bf5d  xor     r8d, r8d
0x18004bf60  test    edi, edi
0x18004bf62  js      loc_18004D75A
0x18004bf68  lea     rcx, [r12+4]
0x18004bf6d  add     rcx, rsi
0x18004bf70  mov     rdx, r9
0x18004bf73  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18004bf78  test    eax, eax
0x18004bf7a  jz      loc_18004C521
0x18004bf80  cmp     [rbp+120h+var_118], r8d
0x18004bf84  jz      loc_18004C521
0x18004bf8a  mov     byte ptr [rbp+120h+var_188.lpVtbl+4], r8b
0x18004bf8e  mov     [rbp+120h+var_18C], r8b
0x18004bf92  mov     dword ptr [rbp+120h+var_188.lpVtbl], r8d
0x18004bf96  lea     r9, [rbp+120h+var_188]; bool *
0x18004bf9a  lea     r8, [rbp+120h+var_18C]; bool *
0x18004bf9e  lea     rdx, [rbp+120h+var_188.lpVtbl+4]; struct IObjectArray *
0x18004bfa2  mov     rcx, [rsi+r12+28h]; this
0x18004bfa7  call    ?GetConditionFullTextInfo@StructuredQuery1@@YAJPEAUIObjectArray@@PEA_N1PEAI@Z; StructuredQuery1::GetConditionFullTextInfo(IObjectArray *,bool *,bool *,uint *)
0x18004bfac  mov     edi, eax
0x18004bfae  test    eax, eax
0x18004bfb0  js      loc_18004D75A
0x18004bfb6  lea     rax, [rbp+120h+var_198]
0x18004bfba  mov     [rsp+230h+var_210], rax; unsigned __int64 *
0x18004bfbf  lea     r9, [rbp+120h+var_1A0]; wchar_t **
0x18004bfc3  lea     r8, asc_18009B4D0; "("
0x18004bfca  mov     rdx, [rbp+120h+var_198]; unsigned __int64
0x18004bfce  mov     rcx, [rbp+120h+var_1A0]; wchar_t *
0x18004bfd2  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18004bfd7  mov     edi, eax
0x18004bfd9  test    eax, eax
0x18004bfdb  js      loc_18004D75A
0x18004bfe1  cmp     [rbp+120h+arg_58], 0
0x18004bfe8  jnz     loc_18004C3FB
0x18004bfee  xor     r14d, r14d
0x18004bff1  mov     [rbp+120h+var_160], r14
0x18004bff5  xor     ebx, ebx
0x18004bff7  mov     [rbp+120h+pv], rbx
0x18004bffb  lea     rdx, PKEY_MOST_RELEVANT_PROPERTIES; struct _tagpropertykey *
0x18004c002  test    r13b, 40h
0x18004c006  jz      short loc_18004C01B
0x18004c008  lea     r8, [rbp+120h+pv]; struct StructuredQuery1::VIRTUAL_PROPERTY_INFO **
0x18004c00c  mov     rcx, [rbp+120h+var_150]; this
  ... truncated ...
```
