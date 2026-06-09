# Microsoft::Resources::UnifiedResourceView::LoadPriFiles(bool,Microsoft::Resources::_MRMPROFILE_PHASE,Microsoft::Resources::DynamicArray<Microsoft::Resources::StringResult *> *,Microsoft::Resources::LoadPriFlags,Microsoft::Resources::DynamicArray<Microsoft::Resources::UnifiedResourceView::PriFileInfo *> * *)

- ea: `0x1800130e0`
- end: `0x18001420b`
- name: `?LoadPriFiles@UnifiedResourceView@Resources@Microsoft@@QEAAJ_NW4_MRMPROFILE_PHASE@23@PEAV?$DynamicArray@PEAVStringResult@Resources@Microsoft@@@23@W4LoadPriFlags@23@PEAPEAV?$DynamicArray@PEAVPriFileInfo@UnifiedResourceView@Resources@Microsoft@@@23@@Z`
- size: `4395`
- prototype: `__int64(_QWORD *, unsigned __int8, unsigned int, ...)`
- caller_count: `2`
- callee_count: `35`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800116bc`
- `0x180014284`

## callees

- `0x180011054`
- `0x180011b58`
- `0x180011cdc`
- `0x1800120f8`
- `0x180012c78`
- `0x180012ca0`
- `0x180012db0`
- `0x180012fc4`
- `0x1800130e0`
- `0x180016b00`
- `0x180017960`
- `0x180018014`
- `0x180018670`
- `0x18001b43c`
- `0x18001d734`
- `0x18001e088`
- `0x18001e0c0`
- `0x180024a0c`
- `0x180024f4c`
- `0x1800268c0`
- `0x180027270`
- `0x180028000`
- `0x180028510`
- `0x180028ad0`
- `0x18002c8d0`
- `0x18002cfd0`
- `0x18002ec70`
- `0x18005fdf8`
- `0x180066c48`
- `0x180074b68`
- `0x18007a904`
- `0x18007c690`
- `0x180080560`
- `0x18008fb04`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180013565`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180013565`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800135f5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800137f2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013927`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013a38`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800135f5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800137f2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013927`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013a38`

## pseudocode

```c
__int64 Microsoft::Resources::UnifiedResourceView::LoadPriFiles(_QWORD *a1, unsigned __int8 a2, unsigned int a3, ...)
{
  struct Microsoft::Resources::ManagedResourceMap *v3; // r14
  _QWORD *v4; // r15
  unsigned int v5; // edi
  int v6; // eax
  int v7; // ebx
  __int64 v8; // r12
  void *v9; // rcx
  unsigned int j; // r14d
  _DWORD *v11; // rax
  unsigned int v12; // r14d
  __int64 v13; // rsi
  Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo *v14; // r12
  int v15; // eax
  __int64 v16; // rdi
  unsigned int v17; // edx
  __int64 v18; // rcx
  __int64 v19; // rax
  _DWORD *v20; // r9
  unsigned int v21; // ebx
  __int64 v22; // rax
  Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo **v23; // rsi
  unsigned int Pri; // edi
  struct Microsoft::Resources::PriFile *v25; // rbx
  __int64 v26; // rax
  __int64 v27; // rax
  Microsoft::Resources::StringResult *v29; // rbx
  LPCWSTR v30; // r8
  int v31; // eax
  const unsigned __int16 *Ref; // rax
  const wchar_t **v33; // rdi
  __int64 v34; // rdx
  void *v35; // rcx
  unsigned int v36; // edi
  const unsigned __int16 *v37; // rax
  int v38; // eax
  int PrimaryResourceMap; // eax
  wchar_t *v40; // rax
  const WCHAR *v41; // rax
  int v42; // ecx
  const WCHAR *v43; // rdi
  const wchar_t **v44; // r8
  const WCHAR *v45; // r14
  __int64 i; // rbx
  __int64 v47; // rax
  Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo *v48; // rsi
  int v49; // eax
  const wchar_t *v50; // rax
  int v51; // ecx
  const wchar_t *v52; // r8
  __int64 v53; // r9
  int Instance; // eax
  Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo *v55; // rbx
  int v56; // eax
  const unsigned __int16 *v57; // rax
  _BOOL8 v58; // r8
  const unsigned __int16 *v59; // rdx
  int v60; // r9d
  int v61; // eax
  struct Microsoft::Resources::UnifiedResourceView::PriFileInfo *v62; // rsi
  unsigned int *v63; // rbx
  __int64 v64; // rcx
  __int64 v65; // rax
  int v66; // eax
  const unsigned __int16 *v67; // rax
  int v68; // ecx
  const unsigned __int16 *v69; // rdx
  int v70; // eax
  void *v71; // rcx
  unsigned int v72; // ebx
  __int64 v73; // rdi
  __int64 v74; // r12
  __int64 k; // rsi
  __int64 *v76; // rcx
  __int64 v77; // rcx
  _QWORD *v78; // r15
  const WCHAR *v79; // rbx
  const WCHAR *v80; // rax
  int v81; // eax
  _DWORD *v82; // r9
  unsigned int v83; // ebx
  const WCHAR *v84; // rbx
  const WCHAR *v85; // rax
  int v86; // eax
  __int64 v87; // rax
  _DWORD *v88; // r9
  unsigned int v89; // edi
  unsigned int v90; // edx
  unsigned int v91; // edx
  int OriginalPri; // eax
  struct Microsoft::Resources::PriFile *v93; // rdi
  void *v94; // rcx
  const unsigned __int16 *v95; // rax
  __int64 v96; // rax
  unsigned int v97; // edi
  const unsigned __int16 *v98; // rax
  __int64 v99; // rax
  const unsigned __int16 *v100; // rax
  __int64 v101; // rax
  unsigned int v102; // edi
  unsigned int v103; // edx
  __int64 v104; // rax
  __int16 v105; // bx
  unsigned int v106; // edx
  unsigned int v107; // ebx
  __int64 v108; // rdx
  _DWORD *v109; // r9
  unsigned int v110; // ebx
  unsigned int v111; // ebx
  unsigned int v112; // ebx
  unsigned int v113; // ebx
  const unsigned __int16 *v114; // rax
  __int64 v115; // rax
  unsigned int v116; // ebx
  unsigned int v117; // edx
  unsigned int v118; // ebx
  unsigned int v119; // edx
  unsigned int v120; // edi
  unsigned int v121; // edx
  int v122; // eax
  unsigned int v123; // ebx
  unsigned int v124; // ebx
  unsigned int v125; // edi
  unsigned int v126; // ebx
  unsigned int v127; // edx
  unsigned int v128; // edx
  unsigned int v129; // edx
  unsigned int v130; // edx
  unsigned int v131; // edx
  void *v132; // r9
  unsigned int v133; // edx
  void *v134; // r9
  unsigned int v135; // edx
  void *v136; // r9
  unsigned int v137; // edx
  void *v138; // r9
  unsigned int v139; // edx
  void *v140; // r9
  unsigned int v141; // edx
  void *v142; // r9
  unsigned int v143; // edx
  void *v144; // r9
  unsigned int v145; // edx
  void *v146; // r9
  unsigned int v147; // edx
  void *v148; // r9
  unsigned int v149; // edx
  void *v150; // r9
  Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo **v151; // [rsp+28h] [rbp-B9h]
  int v152; // [rsp+28h] [rbp-B9h]
  void *lpMem; // [rsp+38h] [rbp-A9h] BYREF
  struct Microsoft::Resources::PriFile *v154; // [rsp+40h] [rbp-A1h] BYREF
  void **v155; // [rsp+48h] [rbp-99h] BYREF
  Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo *v156; // [rsp+50h] [rbp-91h] BYREF
  const int *v157; // [rsp+58h] [rbp-89h] BYREF
  _BYTE v158[32]; // [rsp+60h] [rbp-81h] BYREF
  const wchar_t **v159; // [rsp+80h] [rbp-61h] BYREF
  _BYTE v160[24]; // [rsp+88h] [rbp-59h] BYREF
  unsigned int v161; // [rsp+A0h] [rbp-41h]
  void **v162; // [rsp+A8h] [rbp-39h] BYREF
  struct Microsoft::Resources::UnifiedResourceView::PriFileInfo *v163; // [rsp+B0h] [rbp-31h] BYREF
  void **p_lpMem; // [rsp+B8h] [rbp-29h] BYREF
  char v165; // [rsp+C0h] [rbp-21h]
  _BYTE *v166; // [rsp+C8h] [rbp-19h] BYREF
  _BYTE v167[88]; // [rsp+D0h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+130h] [rbp+4Fh]
  struct Microsoft::Resources::ManagedResourceMap *v172; // [rsp+150h] [rbp+6Fh] BYREF
  va_list va; // [rsp+150h] [rbp+6Fh]
  __int64 v174; // [rsp+158h] [rbp+77h]
  Microsoft::Resources::UnifiedResourceView::PriFileInfo *v175; // [rsp+160h] [rbp+7Fh] BYREF
  va_list va1; // [rsp+160h] [rbp+7Fh]
  va_list va2; // [rsp+168h] [rbp+87h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v172 = va_arg(va1, struct Microsoft::Resources::ManagedResourceMap *);
  v174 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v175 = va_arg(va2, Microsoft::Resources::UnifiedResourceView::PriFileInfo *);
  v3 = v172;
  v4 = a1;
  *(_QWORD *)v175 = 0;
  v5 = *((_DWORD *)v3 + 3);
  v161 = v5;
  if ( !v5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B3,
      (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\unifiedview.cpp",
      (const char *)0x80070057LL,
      (int)v151);
    return 2147942487LL;
  }
  lpMem = 0;
  v6 = Microsoft::Resources::DynamicArray<Microsoft::Resources::UnifiedResourceView::PriFileInfo *>::CreateInstance(
         v5,
         &lpMem);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B7,
      (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\unifiedview.cpp",
      (const char *)(unsigned int)v6,
      (int)v151);
    return (unsigned int)v7;
  }
  v165 = 1;
  p_lpMem = &lpMem;
  v8 = 0;
  while ( (unsigned int)v8 < v5 )
  {
    if ( (unsigned int)v8 >= *((_DWORD *)v3 + 3) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3CB,
        (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\unifiedview.cpp",
        (const char *)0x80070057LL,
        (int)v151);
      v9 = lpMem;
      if ( *((_DWORD *)lpMem + 3) )
      {
        v126 = 0;
        do
        {
          v172 = 0;
          if ( (int)Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::Get(
                      v9,
                      v126,
                      (struct Microsoft::Resources::ManagedResourceMap **)va) >= 0 )
          {
            if ( v172 )
            {
              Microsoft::Resources::UnifiedResourceView::PriFileInfo::`scalar deleting destructor'(v172, v149);
              v150 = lpMem;
            }
          }
          ++v126;
          v9 = v150;
        }
        while ( v126 < *((_DWORD *)v150 + 3) );
      }
      if ( v9 )
LABEL_24:
        Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::`scalar deleting destructor'(v9);
      return 2147942487LL;
    }
    v29 = *(Microsoft::Resources::StringResult **)(*(_QWORD *)v3 + 8 * v8);
    Microsoft::Resources::StringResult::StringResult((Microsoft::Resources::StringResult *)v158);
    v157 = &Microsoft::Resources::NormalizedFilePath::`vftable';
    Microsoft::Resources::StringResult::GetRef(v29);
    DefStringResult_InitBuf(v167);
    v166 = v167;
    v31 = Microsoft::Resources::ManagedFile::NormalizeFilePath(v30, (struct Microsoft::Resources::StringResult *)&v166);
    v7 = v31;
    if ( v31 < 0 )
    {
      v108 = 19;
    }
    else
    {
      v31 = Microsoft::Resources::StringResult::SetContentsFromOther(
              (Microsoft::Resources::StringResult *)v158,
              (struct Microsoft::Resources::StringResult *)&v166);
      v7 = v31;
      if ( v31 >= 0 )
      {
        v7 = 0;
        goto LABEL_37;
      }
      v108 = 20;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v108,
      (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\managedfiles.cpp",
      (const char *)(unsigned int)v31,
      (int)v151);
LABEL_37:
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v166);
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3CF,
        (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\unifiedview.cpp",
        (const char *)(unsigned int)v7,
        (int)v151);
      v157 = &Microsoft::Resources::NormalizedFilePath::`vftable';
      Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)v158);
      v35 = lpMem;
      if ( *((_DWORD *)lpMem + 3) )
      {
        v125 = 0;
        do
        {
          v172 = 0;
          if ( (int)Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::Get(
                      v35,
                      v125,
                      (struct Microsoft::Resources::ManagedResourceMap **)va) >= 0
            && v172 )
          {
            Microsoft::Resources::UnifiedResourceView::PriFileInfo::`scalar deleting destructor'(v172, v147);
            v148 = lpMem;
          }
          ++v125;
          v35 = v148;
        }
        while ( v125 < *((_DWORD *)v148 + 3) );
      }
      goto LABEL_147;
    }
    DefStringResult_InitBuf(v160);
    v159 = (const wchar_t **)v160;
    Ref = Microsoft::Resources::StringResult::GetRef((Microsoft::Resources::StringResult *)v158);
    v7 = DefStringResult_SetCopy(v160, Ref);
    if ( v7 < 0 )
    {
      v34 = 686;
      goto LABEL_44;
    }
    v33 = v159;
    if ( !v159 || !*v159 && *((_DWORD *)v159 + 2) || !*((_DWORD *)v159 + 2) && *v159 )
    {
      v7 = -2147024809;
LABEL_43:
      v34 = 690;
LABEL_44:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v34,
        (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\managedfiles.cpp",
        (const char *)(unsigned int)v7,
        (int)v151);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3D2,
        (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\unifiedview.cpp",
        (const char *)(unsigned int)v7,
        v152);
      Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v159);
      v157 = &Microsoft::Resources::NormalizedFilePath::`vftable';
      Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)v158);
      v35 = lpMem;
      if ( *((_DWORD *)lpMem + 3) )
      {
        v36 = 0;
        do
        {
          v172 = 0;
          if ( (int)Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::Get(
                      v35,
                      v36,
                      (struct Microsoft::Resources::ManagedResourceMap **)va) >= 0
            && v172 )
          {
            Microsoft::Resources::UnifiedResourceView::PriFileInfo::`scalar deleting destructor'(v172, v145);
            v146 = lpMem;
          }
          ++v36;
          v35 = v146;
        }
        while ( v36 < *((_DWORD *)v146 + 3) );
      }
LABEL_147:
      if ( !v35 )
        return (unsigned int)v7;
      goto LABEL_153;
    }
    v7 = DefStringResult_EnsureBuffer(v159, 0);
    if ( v7 < 0 )
      goto LABEL_43;
    v40 = wcsrchr(*v33, 0x5Cu);
    if ( v40 )
      *v40 = 0;
    if ( v159 && (*v159 || !*((_DWORD *)v159 + 2)) && (*((_DWORD *)v159 + 2) || !*v159) )
    {
      v41 = v159[2];
      v42 = 0;
    }
    else
    {
      v41 = 0;
      v42 = -2147024809;
    }
    v43 = 0;
    if ( v42 >= 0 )
      v43 = v41;
    v45 = Microsoft::Resources::StringResult::GetRef((Microsoft::Resources::StringResult *)v158);
    if ( v4[9] )
    {
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v47 = v4[9];
        if ( (unsigned int)i >= *(_DWORD *)(v47 + 12) )
        {
          v44 = v159;
          goto LABEL_69;
        }
        v48 = *(Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo **)(*(_QWORD *)v47 + 8 * i);
        if ( v48 )
        {
          v49 = CompareStringOrdinal(v45, -1, *(LPCWCH *)(*((_QWORD *)v48 + 2) + 48LL), -1, 1);
          if ( !(unsigned int)IntToComparison((unsigned int)(v49 - 2)) )
          {
            if ( !v43 )
              break;
            v66 = CompareStringOrdinal(v43, -1, *(LPCWCH *)(*((_QWORD *)v48 + 2) + 72LL), -1, 1);
            if ( !(unsigned int)IntToComparison((unsigned int)(v66 - 2)) )
              break;
          }
        }
      }
      if ( v159 && (*v159 || !*((_DWORD *)v159 + 2)) && (*((_DWORD *)v159 + 2) || !*v159) )
      {
        v67 = v159[2];
        v68 = 0;
      }
      else
      {
        v67 = 0;
        v68 = -2147024809;
      }
      v69 = 0;
      if ( v68 >= 0 )
        v69 = v67;
      v70 = Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo::GetOrAddAllResourceMaps(v48, v69);
      Pri = v70;
      if ( v70 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x40E,
          (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\unifiedview.cpp",
          (const char *)(unsigned int)v70,
          (int)v151);
        Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v159);
        v157 = &Microsoft::Resources::NormalizedFilePath::`vftable';
        Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)v158);
        v71 = lpMem;
        if ( *((_DWORD *)lpMem + 3) )
        {
          v72 = 0;
          do
          {
            v172 = 0;
            if ( (int)Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::Get(
                        v71,
                        v72,
                        (struct Microsoft::Resources::ManagedResourceMap **)va) >= 0
              && v172 )
            {
              Microsoft::Resources::UnifiedResourceView::PriFileInfo::`scalar deleting destructor'(v172, v131);
              v132 = lpMem;
            }
            ++v72;
            v71 = v132;
          }
          while ( v72 < *((_DWORD *)v132 + 3) );
        }
        goto LABEL_108;
      }
    }
    else
    {
LABEL_69:
      v154 = 0;
      if ( v44 && (*v44 || !*((_DWORD *)v44 + 2)) && (*((_DWORD *)v44 + 2) || !*v44) )
      {
        v50 = v44[2];
        v51 = 0;
      }
      else
      {
        v50 = 0;
        v51 = -2147024809;
      }
      v52 = 0;
      if ( v51 >= 0 )
        v52 = v50;
      Pri = Microsoft::Resources::PriFileManager::GetOrAddFile(v4[4], &v157, v52, (unsigned int)v174 | 4, &v154);
      if ( !v154 )
      {
        if ( (v174 & 1) == 0 )
        {
          v98 = Microsoft::Resources::StringResult::GetRef((Microsoft::Resources::StringResult *)v158);
          v99 = RemovePiiFromString(v98);
          MrtRuntimeTelemetry_GenericEventParam2(
            L"Microsoft::Resources::UnifiedResourceView::LoadPriFiles",
            L"GetOrAddFile Failed",
            v99,
            Pri);
        }
        Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v159);
        v157 = &Microsoft::Resources::NormalizedFilePath::`vftable';
        Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)v158);
        v71 = lpMem;
        if ( *((_DWORD *)lpMem + 3) )
        {
          v124 = 0;
          do
          {
            v172 = 0;
            if ( (int)Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::Get(
                        v71,
                        v124,
                        (struct Microsoft::Resources::ManagedResourceMap **)va) >= 0
              && v172 )
            {
              Microsoft::Resources::UnifiedResourceView::PriFileInfo::`scalar deleting destructor'(v172, v143);
              v144 = lpMem;
            }
            ++v124;
            v71 = v144;
          }
          while ( v124 < *((_DWORD *)v144 + 3) );
        }
LABEL_108:
        if ( v71 )
          goto LABEL_115;
        return Pri;
      }
      v53 = v4[3];
      v155 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo>::`vftable';
      v156 = 0;
      v151 = &v156;
      Instance = Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo::CreateInstance(
                   v4,
                   v154,
                   (2 * a2) | 1u,
                   v53);
      Pri = Instance;
      if ( Instance < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3EC,
          (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\unifiedview.cpp",
          (const char *)(unsigned int)Instance,
          (int)&v156);
        if ( v156 )
          Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo::`scalar deleting destructor'(v156, v106);
        DefStringResult_Clear(v160, 1);
        v157 = &Microsoft::Resources::NormalizedFilePath::`vftable';
        Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)v158);
        v71 = lpMem;
        if ( *((_DWORD *)lpMem + 3) )
        {
          v107 = 0;
          do
          {
            v172 = 0;
            if ( (int)Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::Get(
                        v71,
                        v107,
                        (struct Microsoft::Resources::ManagedResourceMap **)va) >= 0
              && v172 )
            {
              Microsoft::Resources::UnifiedResourceView::PriFileInfo::`scalar deleting destructor'(v172, v141);
              v142 = lpMem;
            }
            ++v107;
            v71 = v142;
          }
          while ( v107 < *((_DWORD *)v142 + 3) );
        }
        goto LABEL_108;
      }
      v55 = v156;
      if ( a3 == 2 )
      {
        v154 = 0;
        OriginalPri = Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo::GetOriginalPri(v156, &v154);
        Pri = OriginalPri;
        if ( OriginalPri < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3F3,
            (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\unifiedview.cpp",
            (const char *)(unsigned int)OriginalPri,
            (int)&v156);
          Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo>::~AutoDeletePtr<Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo>(&v155);
          Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v159);
          v157 = &Microsoft::Resources::NormalizedFilePath::`vftable';
          Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)v158);
          v71 = lpMem;
          if ( *((_DWORD *)lpMem + 3) )
          {
            v112 = 0;
            do
            {
              v172 = 0;
              if ( (int)Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::Get(
                          v71,
                          v112,
                          (struct Microsoft::Resources::ManagedResourceMap **)va) >= 0
                && v172 )
              {
                Microsoft::Resources::UnifiedResourceView::PriFileInfo::`scalar deleting destructor'(v172, v137);
                v138 = lpMem;
              }
              ++v112;
              v71 = v138;
            }
            while ( v112 < *((_DWORD *)v138 + 3) );
          }
          goto LABEL_108;
        }
        v93 = v154;
        if ( !v154 )
        {
          Pri = -2147023728;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3F4,
            (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\unifiedview.cpp",
            (const char *)0x80070490LL,
            (int)&v156);
          Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo>::~AutoDeletePtr<Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo>(&v155);
          Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v159);
          v157 = &Microsoft::Resources::NormalizedFilePath::`vftable';
          Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)v158);
          v71 = lpMem;
          if ( *((_DWORD *)lpMem + 3) )
          {
            v111 = 0;
            do
            {
              v172 = 0;
              if ( (int)Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::Get(
                          v71,
                          v111,
                          (struct Microsoft::Resources::ManagedResourceMap **)va) >= 0
                && v172 )
              {
                Microsoft::Resources::UnifiedResourceView::PriFileInfo::`scalar deleting destructor'(v172, v135);
                v136 = lpMem;
              }
              ++v111;
              v71 = v136;
            }
            while ( v111 < *((_DWORD *)v136 + 3) );
          }
          goto LABEL_108;
        }
        if ( ((*(unsigned __int8 (__fastcall **)(struct Microsoft::Resources::PriFile *))(*(_QWORD *)v154 + 104LL))(v154)
           || (**(_BYTE **)(*((_QWORD *)v93 + 5) + 48LL) & 4) != 0)
          && !(*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v4[3] + 56LL))(v4[3]) )
        {
          Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo>::~AutoDeletePtr<Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo>(&v155);
          Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v159);
          v157 = &Microsoft::Resources::NormalizedFilePath::`vftable';
          Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)v158);
          v94 = lpMem;
          if ( *((_DWORD *)lpMem + 3) )
          {
            v123 = 0;
            do
            {
              v172 = 0;
              if ( (int)Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::Get(
                          v94,
                          v123,
                          (struct Microsoft::Resources::ManagedResourceMap **)va) >= 0
                && v172 )
              {
                Microsoft::Resources::UnifiedResourceView::PriFileInfo::`scalar deleting destructor'(v172, v133);
                v134 = lpMem;
              }
              ++v123;
              v94 = v134;
            }
            while ( v123 < *((_DWORD *)v134 + 3) );
          }
          if ( v94 )
            Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::`scalar deleting destructor'(v94);
          return 2147957542LL;
        }
      }
      v56 = Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo::ResolveFileFileList(v55);
      Pri = v56;
      if ( v56 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3FF,
          (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\unifiedview.cpp",
          (const char *)(unsigned int)v56,
          (int)&v156);
LABEL_131:
        if ( v55 )
          Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo::`scalar deleting destructor'(v55, v91);
        DefStringResult_Clear(v160, 1);
        v157 = &Microsoft::Resources::NormalizedFilePath::`vftable';
        Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)v158);
        wil::details::lambda_call__lambda_19c997c5cd0269a6b8cc773f7d147a97___::reset(&p_lpMem);
        return Pri;
      }
      v162 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::UnifiedResourceView::PriFileInfo>::`vftable';
      v163 = 0;
      v57 = Microsoft::Resources::StringResult::GetRef((Microsoft::Resources::StringResult *)v158);
      v59 = 0;
      if ( v60 >= 0 )
        v59 = (const unsigned __int16 *)v58;
      v61 = Microsoft::Resources::UnifiedResourceView::PriFileInfo::CreateInstance(v57, v59, v58, &v163);
      Pri = v61;
      if ( v61 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x403,
          (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\unifiedview.cpp",
          (const char *)(unsigned int)v61,
          (int)&v156);
        if ( v163 )
          Microsoft::Resources::UnifiedResourceView::PriFileInfo::`scalar deleting destructor'(v163, v91);
        goto LABEL_131;
      }
      v62 = v163;
      v156 = 0;
      *(_QWORD *)v163 = v55;
      *((_DWORD *)v62 + 19) = v8;
      *((_DWORD *)v62 + 18) = -1;
      v63 = (unsigned int *)lpMem;
      if ( *((_DWORD *)lpMem + 3) >= *((_DWORD *)lpMem + 2) )
      {
        v122 = Microsoft::Resources::DynamicArray<Microsoft::Resources::UnifiedEnvironment::CompatibleEnvironmentInfo *>::Extend((int)lpMem);
        Pri = v122;
        if ( v122 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x408,
            (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\unifiedview.cpp",
            (const char *)(unsigned int)v122,
            (int)&v156);
          Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::UnifiedResourceView::PriFileInfo>::~AutoDeletePtr<Microsoft::Resources::UnifiedResourceView::PriFileInfo>(&v162);
          Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo>::~AutoDeletePtr<Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo>(&v155);
          Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v159);
          v157 = &Microsoft::Resources::NormalizedFilePath::`vftable';
          Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)v158);
          v71 = lpMem;
          if ( *((_DWORD *)lpMem + 3) )
          {
            v113 = 0;
            do
            {
              v172 = 0;
              if ( (int)Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::Get(
                          v71,
                          v113,
                          (struct Microsoft::Resources::ManagedResourceMap **)va) >= 0
                && v172 )
              {
                Microsoft::Resources::UnifiedResourceView::PriFileInfo::`scalar deleting destructor'(v172, v139);
                v140 = lpMem;
              }
              ++v113;
              v71 = v140;
            }
            while ( v113 < *((_DWORD *)v140 + 3) );
          }
          goto LABEL_108;
        }
      }
      v64 = v63[3];
      v65 = *(_QWORD *)v63;
      v163 = 0;
      v156 = 0;
      *(_QWORD *)(v65 + 8 * v64) = v62;
      ++v63[3];
      v162 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::UnifiedResourceView::PriFileInfo>::`vftable';
      v155 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo>::`vftable';
    }
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v159);
    v157 = &Microsoft::Resources::NormalizedFilePath::`vftable';
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)v158);
    v5 = v161;
    v8 = (unsigned int)(v8 + 1);
    v3 = v172;
  }
  for ( j = 0; ; ++j )
  {
    v11 = lpMem;
    if ( j >= *((_DWORD *)lpMem + 3) )
      break;
    v22 = *(_QWORD *)lpMem;
    v154 = 0;
    v23 = *(Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo ***)(v22 + 8LL * j);
    Pri = Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo::GetPri(*v23, &v154);
    if ( (Pri & 0x80000000) != 0 )
      goto LABEL_176;
    v25 = v154;
    if ( !v154 )
    {
      Pri = -2147467260;
LABEL_176:
      v114 = Microsoft::Resources::StringResult::GetRef((Microsoft::Resources::StringResult *)(v23 + 1));
      v115 = RemovePiiFromString(v114);
      MrtRuntimeTelemetry_GenericEventParam1(L"Microsoft::Resources::UnifiedResourceView::LoadPriFiles", v115, Pri);
      v82 = lpMem;
      v116 = 0;
      if ( *((_DWORD *)lpMem + 3) )
      {
        do
        {
          v175 = 0;
          if ( (int)Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::Get(
                      v82,
                      v116,
                      (Microsoft::Resources::UnifiedResourceView::PriFileInfo **)va1) >= 0
            && v175 )
          {
            Microsoft::Resources::UnifiedResourceView::PriFileInfo::`scalar deleting destructor'(v175, v117);
            v82 = lpMem;
          }
          ++v116;
        }
        while ( v116 < v82[3] );
      }
LABEL_113:
      if ( v82 )
      {
        v71 = v82;
LABEL_115:
        Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::`scalar deleting destructor'(v71);
      }
      return Pri;
    }
    if ( (*(int (__fastcall **)(char *))(*((_QWORD *)v154 + 2) + 8LL))((char *)v154 + 16) > 1 )
    {
      v100 = Microsoft::Resources::StringResult::GetRef((Microsoft::Resources::StringResult *)(v23 + 1));
      v101 = RemovePiiFromString(v100);
      v7 = -2147009761;
      MrtRuntimeTelemetry_GenericEventParam1(
        L"Microsoft::Resources::UnifiedResourceView::LoadPriFiles",
        v101,
        2147957535LL);
      v88 = lpMem;
      v102 = 0;
      if ( *((_DWORD *)lpMem + 3) )
      {
        do
        {
          v175 = 0;
          if ( (int)Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::Get(
                      v88,
                      v102,
                      (Microsoft::Resources::UnifiedResourceView::PriFileInfo **)va1) >= 0
            && v175 )
          {
            Microsoft::Resources::UnifiedResourceView::PriFileInfo::`scalar deleting destructor'(v175, v103);
            v88 = lpMem;
          }
          ++v102;
        }
        while ( v102 < v88[3] );
      }
      goto LABEL_150;
    }
    v172 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, struct Microsoft::Resources::ManagedResourceMap **))(*((_QWORD *)v25 + 2)
                                                                                                + 24LL))(
           (__int64)v25 + 16,
           (struct Microsoft::Resources::ManagedResourceMap **)va);
    if ( v7 < 0 )
      goto LABEL_149;
    if ( !v172 )
    {
      v7 = -2147009761;
LABEL_149:
      v95 = Microsoft::Resources::StringResult::GetRef((Microsoft::Resources::StringResult *)(v23 + 1));
      v96 = RemovePiiFromString(v95);
      MrtRuntimeTelemetry_GenericEventParam1(
        L"Microsoft::Resources::UnifiedResourceView::LoadPriFiles",
        v96,
        (unsigned int)v7);
      v88 = lpMem;
      v97 = 0;
      if ( *((_DWORD *)lpMem + 3) )
      {
        do
        {
          v175 = 0;
          if ( (int)Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::Get(
                      v88,
                      v97,
                      (Microsoft::Resources::UnifiedResourceView::PriFileInfo **)va1) >= 0
            && v175 )
          {
            Microsoft::Resources::UnifiedResourceView::PriFileInfo::`scalar deleting destructor'(v175, v128);
            v88 = lpMem;
          }
          ++v97;
        }
        while ( v97 < v88[3] );
      }
LABEL_150:
      if ( !v88 )
        return (unsigned int)v7;
      v35 = v88;
LABEL_153:
      Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::`scalar deleting destructor'(v35);
      return (unsigned int)v7;
    }
    v26 = (*(__int64 (__fastcall **)(struct Microsoft::Resources::ManagedResourceMap *))(*(_QWORD *)v172 + 8LL))(v172);
    v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(*(_QWORD *)v4[3] + 48LL))(
            v4[3],
            v27,
            a3,
            0) )
    {
      v109 = lpMem;
      v110 = 0;
      if ( *((_DWORD *)lpMem + 3) )
      {
        do
        {
          v175 = 0;
          if ( (int)Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::Get(
                      v109,
                      v110,
                      (Microsoft::Resources::UnifiedResourceView::PriFileInfo **)va1) >= 0
            && v175 )
          {
            Microsoft::Resources::UnifiedResourceView::PriFileInfo::`scalar deleting destructor'(v175, v127);
            v109 = lpMem;
          }
          ++v110;
        }
        while ( v110 < v109[3] );
      }
      if ( v109 )
        Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::`scalar deleting destructor'(v109);
      return 2147942405LL;
    }
    if ( v4[11] )
    {
      v73 = (*(__int64 (__fastcall **)(struct Microsoft::Resources::ManagedResourceMap *))(*(_QWORD *)v172 + 8LL))(v172);
      v74 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v73 + 80LL))(v73, 0);
      for ( k = 0; ; k = (unsigned int)(k + 1) )
      {
        v76 = (__int64 *)v4[11];
        if ( (unsigned int)k >= *((_DWORD *)v76 + 3) )
          goto LABEL_32;
        v77 = *v76;
        v78 = *(_QWORD **)(v77 + 8 * k);
        if ( v78[2] == v73 )
          goto LABEL_110;
        v79 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(*v78 + 16LL))(*(_QWORD *)(v77 + 8 * k));
        v80 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
        v81 = CompareStringOrdinal(v80, -1, v79, -1, 1);
        if ( !(unsigned int)IntToComparison((unsigned int)(v81 - 2)) )
          break;
        v4 = a1;
      }
      v84 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD *))(*v78 + 8LL))(v78);
      v85 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v73 + 8LL))(v73);
      v86 = CompareStringOrdinal(v85, -1, v84, -1, 1);
      if ( (unsigned int)IntToComparison((unsigned int)(v86 - 2))
        || (v104 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v78 + 80LL))(v78, 0),
            v105 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v104 + 8LL))(v104),
            (*(unsigned __int16 (__fastcall **)(__int64))(*(_QWORD *)v74 + 8LL))(v74) != v105) )
      {
        v87 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v73 + 8LL))(v73);
        v7 = -2147009761;
        MrtRuntimeTelemetry_GenericEventParam1(
          L"Microsoft::Resources::UnifiedResourceView::LoadPriFiles",
          v87,
          2147957535LL);
        v88 = lpMem;
        v89 = 0;
        if ( *((_DWORD *)lpMem + 3) )
        {
          do
          {
            v175 = 0;
            if ( (int)Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::Get(
                        v88,
                        v89,
                        (Microsoft::Resources::UnifiedResourceView::PriFileInfo **)va1) >= 0
              && v175 )
            {
              Microsoft::Resources::UnifiedResourceView::PriFileInfo::`scalar deleting destructor'(v175, v90);
              v88 = lpMem;
            }
            ++v89;
          }
          while ( v89 < v88[3] );
        }
        goto LABEL_150;
      }
LABEL_110:
      v4 = a1;
    }
LABEL_32:
    ;
  }
  v12 = 0;
  while ( 2 )
  {
    if ( v12 >= v11[3] )
    {
      *(_QWORD *)v175 = v11;
      return 0;
    }
    v13 = *(_QWORD *)(*(_QWORD *)v11 + 8LL * v12);
    v14 = *(Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo **)v13;
    if ( !v4[9] )
    {
      v15 = Microsoft::Resources::DynamicArray<Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo *>::CreateInstance(
              v12,
              v4 + 9);
      v7 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5B8,
          (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\unifiedview.cpp",
          (const char *)(unsigned int)v15,
          (int)v151);
LABEL_184:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x47B,
          (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\unifiedview.cpp",
          (const char *)(unsigned int)v7,
          (int)v151);
        v88 = lpMem;
        v120 = 0;
        if ( *((_DWORD *)lpMem + 3) )
        {
          do
          {
            v172 = 0;
            if ( (int)Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::Get(
                        v88,
                        v120,
                        (struct Microsoft::Resources::ManagedResourceMap **)va) >= 0
              && v172 )
            {
              Microsoft::Resources::UnifiedResourceView::PriFileInfo::`scalar deleting destructor'(v172, v121);
              v88 = lpMem;
            }
            ++v120;
          }
          while ( v120 < v88[3] );
        }
        goto LABEL_150;
      }
    }
    v16 = v4[9];
    v17 = *(_DWORD *)(v16 + 12);
    if ( v17 < *(_DWORD *)(v16 + 8)
      || (v7 = Microsoft::Resources::DynamicArray<Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo *>::Extend(
                 v4[9],
                 v17 + 1),
          v7 >= 0) )
    {
      v7 = 0;
      *(_QWORD *)(*(_QWORD *)v16 + 8LL * *(unsigned int *)(v16 + 12)) = v14;
      v18 = *(unsigned int *)(v16 + 12);
      *(_DWORD *)(v16 + 12) = v18 + 1;
    }
    else
    {
      v18 = 0;
    }
    if ( v7 < 0 )
      goto LABEL_184;
    *(_BYTE *)(v13 + 80) = 1;
    *(_DWORD *)(v13 + 72) = v18;
    if ( a3 || a1[13] )
    {
      v4 = a1;
      goto LABEL_47;
    }
    v19 = v4[9];
    v4 = a1;
    a1[13] = 0;
    if ( (unsigned int)v18 < *(_DWORD *)(v19 + 12) )
    {
      a1[13] = *(_QWORD *)(*(_QWORD *)v19 + 8 * v18);
      *(_BYTE *)(v13 + 81) = 1;
LABEL_47:
      v37 = Microsoft::Resources::StringResult::GetRef((Microsoft::Resources::StringResult *)(v13 + 40));
      v38 = Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo::GetOrAddAllResourceMaps(v14, v37);
      Pri = v38;
      if ( v38 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x485,
          (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\unifiedview.cpp",
          (const char *)(unsigned int)v38,
          (int)v151);
        v82 = lpMem;
        v83 = 0;
        if ( *((_DWORD *)lpMem + 3) )
        {
          do
          {
            v172 = 0;
            if ( (int)Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::Get(
                        v82,
                        v83,
                        (struct Microsoft::Resources::ManagedResourceMap **)va) >= 0
              && v172 )
            {
              Microsoft::Resources::UnifiedResourceView::PriFileInfo::`scalar deleting destructor'(v172, v130);
              v82 = lpMem;
            }
            ++v83;
          }
          while ( v83 < v82[3] );
        }
        goto LABEL_113;
      }
      v172 = 0;
      PrimaryResourceMap = Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo::GetPrimaryResourceMap(
                             v14,
                             (struct Microsoft::Resources::ManagedResourceMap **)va);
      Pri = PrimaryResourceMap;
      if ( PrimaryResourceMap < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x488,
          (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\unifiedview.cpp",
          (const char *)(unsigned int)PrimaryResourceMap,
          (int)v151);
        v82 = lpMem;
        v118 = 0;
        if ( *((_DWORD *)lpMem + 3) )
        {
          do
          {
            v172 = 0;
            if ( (int)Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::Get(
                        v82,
                        v118,
                        (struct Microsoft::Resources::ManagedResourceMap **)va) >= 0
              && v172 )
            {
              Microsoft::Resources::UnifiedResourceView::PriFileInfo::`scalar deleting destructor'(v172, v119);
              v82 = lpMem;
            }
            ++v118;
          }
          while ( v118 < v82[3] );
        }
        goto LABEL_113;
      }
      ++v12;
      *(_QWORD *)(v13 + 88) = v172;
      v11 = lpMem;
      continue;
    }
    break;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x481,
    (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\unifiedview.cpp",
    (const char *)0x80070057LL,
    (int)v151);
  v20 = lpMem;
  v21 = 0;
  if ( *((_DWORD *)lpMem + 3) )
  {
    do
    {
      v172 = 0;
      if ( (int)Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::Get(
                  v20,
                  v21,
                  (struct Microsoft::Resources::ManagedResourceMap **)va) >= 0
        && v172 )
      {
        Microsoft::Resources::UnifiedResourceView::PriFileInfo::`scalar deleting destructor'(v172, v129);
        v20 = lpMem;
      }
      ++v21;
    }
    while ( v21 < v20[3] );
  }
  if ( v20 )
  {
    v9 = v20;
    goto LABEL_24;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800130e0  mov     rax, rsp
0x1800130e3  mov     [rax+20h], r9
0x1800130e7  mov     [rax+18h], r8d
0x1800130eb  mov     [rax+10h], dl
0x1800130ee  mov     [rax+8], rcx
0x1800130f2  push    rbp
0x1800130f3  push    rbx
0x1800130f4  push    rsi
0x1800130f5  push    rdi
0x1800130f6  push    r12
0x1800130f8  push    r13
0x1800130fa  push    r14
0x1800130fc  push    r15
0x1800130fe  lea     rbp, [rax-4Fh]
0x180013102  sub     rsp, 0E8h
0x180013109  mov     rax, [rbp+47h+arg_28]
0x18001310d  mov     r14, r9
0x180013110  mov     r15, rcx
0x180013113  mov     qword ptr [rax], 0
0x18001311a  mov     edi, [r9+0Ch]
0x18001311e  mov     [rbp+47h+var_88], edi
0x180013121  cmp     edi, 1
0x180013124  jb      loc_180013537
0x18001312a  lea     rdx, [rsp+120h+lpMem]
0x18001312f  mov     [rsp+120h+lpMem], 0
0x180013138  mov     ecx, edi
0x18001313a  call    ?CreateInstance@?$DynamicArray@PEAVPriFileInfo@UnifiedResourceView@Resources@Microsoft@@@Resources@Microsoft@@SAJIPEAPEAV123@@Z; Microsoft::Resources::DynamicArray<Microsoft::Resources::UnifiedResourceView::PriFileInfo *>::CreateInstance(uint,Microsoft::Resources::DynamicArray<Microsoft::Resources::UnifiedResourceView::PriFileInfo *> * *)
0x18001313f  mov     ebx, eax
0x180013141  test    eax, eax
0x180013143  js      loc_180014085
0x180013149  lea     rax, [rsp+120h+lpMem]
0x18001314e  mov     [rbp+47h+var_68], 1
0x180013152  mov     [rbp+47h+var_70], rax
0x180013156  xor     r12d, r12d
0x180013159  mov     r13d, 80070057h
0x18001315f  lea     rsi, aMinkernelMrtMr_46; "minkernel\\mrt\\mrm\\mrmmin\\managedfil"...
0x180013166  cmp     r12d, edi
0x180013169  jnb     short loc_1800131AE
0x18001316b  cmp     r12d, [r14+0Ch]
0x18001316f  jb      loc_18001338C
0x180013175  mov     rcx, [rbp+4Fh]; this
0x180013179  lea     r8, aMinkernelMrtMr_7; "minkernel\\mrt\\mrm\\mrmmin\\unifiedvie"...
0x180013180  mov     r9d, r13d; char *
0x180013183  mov     edx, 3CBh; void *
0x180013188  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001318d  mov     r9, [rsp+120h+lpMem]
0x180013192  mov     rcx, r9
0x180013195  cmp     dword ptr [r9+0Ch], 0
0x18001319a  ja      loc_1800140F3
0x1800131a0  test    rcx, rcx
0x1800131a3  jnz     loc_180013292
0x1800131a9  jmp     loc_180013555
0x1800131ae  xor     r12d, r12d
0x1800131b1  mov     r14d, r12d
0x1800131b4  mov     rax, [rsp+120h+lpMem]
0x1800131b9  cmp     r14d, [rax+0Ch]
0x1800131bd  jb      loc_18001329C
0x1800131c3  mov     r14d, r12d
0x1800131c6  cmp     r14d, [rax+0Ch]
0x1800131ca  jnb     loc_18001336F
0x1800131d0  cmp     qword ptr [r15+48h], 0
0x1800131d5  mov     rax, [rax]
0x1800131d8  mov     ecx, r14d
0x1800131db  mov     rsi, [rax+rcx*8]
0x1800131df  mov     r12, [rsi]
0x1800131e2  jnz     short loc_1800131F7
0x1800131e4  lea     rdx, [r15+48h]
0x1800131e8  call    ?CreateInstance@?$DynamicArray@PEAVUnifiedViewFileInfo@UnifiedResourceView@Resources@Microsoft@@@Resources@Microsoft@@SAJIPEAPEAV123@@Z; Microsoft::Resources::DynamicArray<Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo *>::CreateInstance(uint,Microsoft::Resources::DynamicArray<Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo *> * *)
0x1800131ed  mov     ebx, eax
0x1800131ef  test    eax, eax
0x1800131f1  js      loc_18001417A
0x1800131f7  mov     rdi, [r15+48h]
0x1800131fb  mov     edx, [rdi+0Ch]
0x1800131fe  cmp     edx, [rdi+8]
0x180013201  jnb     loc_180013ABF
0x180013207  mov     ecx, [rdi+0Ch]
0x18001320a  xor     ebx, ebx
0x18001320c  mov     rax, [rdi]
0x18001320f  mov     [rax+rcx*8], r12
0x180013213  mov     ecx, [rdi+0Ch]
0x180013216  lea     eax, [rcx+1]
0x180013219  mov     [rdi+0Ch], eax
0x18001321c  test    ebx, ebx
0x18001321e  js      loc_180014022
0x180013224  cmp     [rbp+47h+arg_10], 0
0x180013228  mov     byte ptr [rsi+50h], 1
0x18001322c  mov     [rsi+48h], ecx
0x18001322f  jnz     loc_1800139D0
0x180013235  mov     rax, [rbp+47h+arg_0]
0x180013239  cmp     qword ptr [rax+68h], 0
0x18001323e  jnz     loc_1800139D0
0x180013244  mov     rax, [r15+48h]
0x180013248  mov     r15, [rbp+47h+arg_0]
0x18001324c  mov     qword ptr [r15+68h], 0
0x180013254  cmp     ecx, [rax+0Ch]
0x180013257  jb      loc_1800134D4
0x18001325d  mov     rcx, [rbp+4Fh]; this
0x180013261  lea     r8, aMinkernelMrtMr_7; "minkernel\\mrt\\mrm\\mrmmin\\unifiedvie"...
0x180013268  mov     r9d, r13d; char *
0x18001326b  mov     edx, 481h; void *
0x180013270  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013275  mov     r9, [rsp+120h+lpMem]
0x18001327a  xor     ebx, ebx
0x18001327c  cmp     [r9+0Ch], ebx
0x180013280  ja      loc_180014197
0x180013286  test    r9, r9
0x180013289  jz      loc_180013555
0x18001328f  mov     rcx, r9; lpMem
0x180013292  call    ??_G?$DynamicArray@PEAVManagedSchema@Resources@Microsoft@@@Resources@Microsoft@@QEAAPEAXI@Z; Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::`scalar deleting destructor'(uint)
0x180013297  jmp     loc_180013555
0x18001329c  mov     rax, [rax]
0x18001329f  lea     rdx, [rsp+120h+var_E8]; struct Microsoft::Resources::PriFile **
0x1800132a4  mov     ecx, r14d
0x1800132a7  mov     [rsp+120h+var_E8], r12
0x1800132ac  mov     rsi, [rax+rcx*8]
0x1800132b0  mov     rcx, [rsi]; this
0x1800132b3  call    ?GetPri@UnifiedViewFileInfo@UnifiedResourceView@Resources@Microsoft@@QEAAJPEAPEAVPriFile@34@@Z; Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo::GetPri(Microsoft::Resources::PriFile * *)
0x1800132b8  mov     edi, eax
0x1800132ba  test    eax, eax
0x1800132bc  js      loc_180013F57
0x1800132c2  mov     rbx, [rsp+120h+var_E8]
0x1800132c7  test    rbx, rbx
0x1800132ca  jz      loc_180014170
0x1800132d0  mov     rax, [rbx+10h]
0x1800132d4  lea     rcx, [rbx+10h]
0x1800132d8  mov     rax, [rax+8]
0x1800132dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132e1  cmp     eax, 1
0x1800132e4  jg      loc_180013CE4
0x1800132ea  mov     [rbp+47h+arg_18], r12
0x1800132ee  lea     rdx, [rbp+47h+arg_18]
0x1800132f2  mov     rax, [rbx+10h]
0x1800132f6  lea     rcx, [rbx+10h]
0x1800132fa  mov     rax, [rax+18h]
0x1800132fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013303  mov     ebx, eax
0x180013305  test    eax, eax
0x180013307  js      loc_180013C69
0x18001330d  mov     rcx, [rbp+47h+arg_18]
0x180013311  test    rcx, rcx
0x180013314  jz      loc_180014130
0x18001331a  mov     rax, [rcx]
0x18001331d  mov     rax, [rax+8]
0x180013321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013326  mov     rdx, rax
0x180013329  mov     rcx, [rax]
0x18001332c  mov     rax, [rcx+10h]
0x180013330  mov     rcx, rdx
0x180013333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013338  mov     rcx, [r15+18h]
0x18001333c  mov     r10, rax
0x18001333f  mov     r8d, [rbp+47h+arg_10]
0x180013343  xor     r9d, r9d
0x180013346  mov     rdx, [rcx]
0x180013349  mov     rax, [rdx+30h]
0x18001334d  mov     rdx, r10
0x180013350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013355  test    al, al
0x180013357  jz      loc_180013E0F
0x18001335d  cmp     [r15+58h], r12
0x180013361  jnz     loc_1800138A9
0x180013367  inc     r14d
0x18001336a  jmp     loc_1800131B4
0x18001336f  mov     rcx, [rbp+47h+arg_28]
0x180013373  mov     [rcx], rax
0x180013376  xor     eax, eax
0x180013378  add     rsp, 0E8h
0x18001337f  pop     r15
0x180013381  pop     r14
0x180013383  pop     r13
0x180013385  pop     r12
0x180013387  pop     rdi
0x180013388  pop     rsi
0x180013389  pop     rbx
0x18001338a  pop     rbp
0x18001338b  retn
0x18001338c  mov     rax, [r14]
0x18001338f  lea     rcx, [rsp+120h+var_C8]; this
0x180013394  mov     rbx, [rax+r12*8]
0x180013398  call    ??0StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::StringResult(void)
0x18001339d  lea     rdi, ??_7NormalizedFilePath@Resources@Microsoft@@6B@; const Microsoft::Resources::NormalizedFilePath::`vftable'
0x1800133a4  mov     rcx, rbx; this
0x1800133a7  mov     [rsp+120h+var_D0], rdi
0x1800133ac  call    ?GetRef@StringResult@Resources@Microsoft@@QEBAPEBGXZ; Microsoft::Resources::StringResult::GetRef(void)
0x1800133b1  lea     rcx, [rbp+47h+var_58]
0x1800133b5  mov     r8, rax
0x1800133b8  call    DefStringResult_InitBuf
0x1800133bd  lea     rcx, [rbp+47h+var_58]
0x1800133c1  mov     [rbp+47h+var_60], rcx
0x1800133c5  lea     rdx, [rbp+47h+var_60]; struct Microsoft::Resources::StringResult *
0x1800133c9  mov     rcx, r8; lpFileName
0x1800133cc  call    ?NormalizeFilePath@ManagedFile@Resources@Microsoft@@SAJPEBGPEAVStringResult@23@@Z; Microsoft::Resources::ManagedFile::NormalizeFilePath(ushort const *,Microsoft::Resources::StringResult *)
0x1800133d1  xor     r14d, r14d
0x1800133d4  mov     ebx, eax
0x1800133d6  test    eax, eax
0x1800133d8  js      loc_180013DF6
0x1800133de  lea     rdx, [rbp+47h+var_60]; struct Microsoft::Resources::StringResult *
0x1800133e2  lea     rcx, [rsp+120h+var_C8]; this
0x1800133e7  call    ?SetContentsFromOther@StringResult@Resources@Microsoft@@QEAAJPEAV123@@Z; Microsoft::Resources::StringResult::SetContentsFromOther(Microsoft::Resources::StringResult *)
0x1800133ec  mov     ebx, eax
0x1800133ee  test    eax, eax
0x1800133f0  js      loc_1800140A2
0x1800133f6  mov     ebx, r14d
0x1800133f9  lea     rcx, [rbp+47h+var_60]; this
0x1800133fd  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x180013402  test    ebx, ebx
0x180013404  js      loc_180013C29
0x18001340a  lea     rcx, [rbp+47h+var_A0]
0x18001340e  call    DefStringResult_InitBuf
0x180013413  lea     rcx, [rbp+47h+var_A0]
0x180013417  mov     [rbp+47h+var_A8], rcx
0x18001341b  lea     rcx, [rsp+120h+var_C8]; this
0x180013420  call    ?GetRef@StringResult@Resources@Microsoft@@QEBAPEBGXZ; Microsoft::Resources::StringResult::GetRef(void)
0x180013425  mov     rdx, rax
0x180013428  lea     rcx, [rbp+47h+var_A0]
0x18001342c  call    DefStringResult_SetCopy
0x180013431  mov     ebx, eax
0x180013433  test    eax, eax
0x180013435  js      loc_180013B44
0x18001343b  mov     rdi, [rbp+47h+var_A8]
0x18001343f  test    rdi, rdi
0x180013442  jz      loc_1800139ED
0x180013448  cmp     [rdi], r14
0x18001344b  jz      loc_1800139F5
0x180013451  cmp     [rdi+8], r14d
0x180013455  jz      loc_1800139E4
0x18001345b  xor     edx, edx
0x18001345d  mov     rcx, rdi
0x180013460  call    _DefStringResult_EnsureBuffer
0x180013465  mov     ebx, eax
0x180013467  test    eax, eax
0x180013469  jns     loc_18001355D
0x18001346f  mov     edx, 2B2h; void *
0x180013474  lea     rdi, ??_7NormalizedFilePath@Resources@Microsoft@@6B@; const Microsoft::Resources::NormalizedFilePath::`vftable'
0x18001347b  mov     rcx, [rbp+4Fh]; this
0x18001347f  mov     r9d, ebx; char *
0x180013482  mov     r8, rsi; unsigned int
0x180013485  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001348a  mov     rcx, [rbp+4Fh]; this
0x18001348e  lea     r8, aMinkernelMrtMr_7; "minkernel\\mrt\\mrm\\mrmmin\\unifiedvie"...
0x180013495  mov     r9d, ebx; char *
0x180013498  mov     edx, 3D2h; void *
0x18001349d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800134a2  lea     rcx, [rbp+47h+var_A8]; this
0x1800134a6  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x1800134ab  lea     rcx, [rsp+120h+var_C8]; this
0x1800134b0  mov     [rsp+120h+var_D0], rdi
0x1800134b5  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x1800134ba  mov     r9, [rsp+120h+lpMem]
0x1800134bf  mov     rcx, r9
0x1800134c2  cmp     [r9+0Ch], r14d
0x1800134c6  jbe     loc_180013C62
0x1800134cc  mov     edi, r14d
0x1800134cf  jmp     loc_1800C0CE8
0x1800134d4  mov     rax, [rax]
0x1800134d7  mov     rcx, [rax+rcx*8]
0x1800134db  mov     [r15+68h], rcx
0x1800134df  mov     byte ptr [rsi+51h], 1
0x1800134e3  lea     rcx, [rsi+28h]; this
0x1800134e7  call    ?GetRef@StringResult@Resources@Microsoft@@QEBAPEBGXZ; Microsoft::Resources::StringResult::GetRef(void)
0x1800134ec  mov     rdx, rax; unsigned __int16 *
0x1800134ef  mov     rcx, r12; this
0x1800134f2  call    ?GetOrAddAllResourceMaps@UnifiedViewFileInfo@UnifiedResourceView@Resources@Microsoft@@QEAAJPEBG@Z; Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo::GetOrAddAllResourceMaps(ushort const *)
0x1800134f7  mov     edi, eax
0x1800134f9  test    eax, eax
0x1800134fb  js      loc_180013998
0x180013501  lea     rdx, [rbp+47h+arg_18]; struct Microsoft::Resources::ManagedResourceMap **
0x180013505  mov     [rbp+47h+arg_18], 0
0x18001350d  mov     rcx, r12; this
0x180013510  call    ?GetPrimaryResourceMap@UnifiedViewFileInfo@UnifiedResourceView@Resources@Microsoft@@QEAAJPEAPEAVManagedResourceMap@34@@Z; Microsoft::Resources::UnifiedResourceView::UnifiedViewFileInfo::GetPrimaryResourceMap(Microsoft::Resources::ManagedResourceMap * *)
0x180013515  xor     r12d, r12d
0x180013518  mov     edi, eax
0x18001351a  test    eax, eax
0x18001351c  js      loc_180013FC2
0x180013522  mov     rax, [rbp+47h+arg_18]
0x180013526  inc     r14d
0x180013529  mov     [rsi+58h], rax
0x18001352d  mov     rax, [rsp+120h+lpMem]
0x180013532  jmp     loc_1800131C6
0x180013537  mov     rcx, [rbp+4Fh]; this
0x18001353b  lea     r8, aMinkernelMrtMr_7; "minkernel\\mrt\\mrm\\mrmmin\\unifiedvie"...
0x180013542  mov     r13d, 80070057h
0x180013548  mov     edx, 3B3h; void *
0x18001354d  mov     r9d, r13d; char *
0x180013550  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013555  mov     eax, r13d
0x180013558  jmp     loc_180013378
0x18001355d  mov     rcx, [rdi]; Str
0x180013560  mov     edx, 5Ch ; '\'; Ch
0x180013565  call    cs:__imp_wcsrchr
0x18001356b  test    rax, rax
0x18001356e  jz      short loc_180013574
0x180013570  mov     [rax], r14w
0x180013574  mov     r8, [rbp+47h+var_A8]
0x180013578  test    r8, r8
0x18001357b  jz      loc_1800139D9
0x180013581  cmp     [r8], r14
0x180013584  jnz     short loc_180013590
0x180013586  cmp     [r8+8], r14d
0x18001358a  ja      loc_1800139D9
  ... truncated ...
```
