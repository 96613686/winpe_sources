# RangeSet::InitializeByRemappingCoreFragment(SharedRefPtr<ICoreFragment> &,RemapContext &,SyncIdCache *)

- ea: `0x180012260`
- end: `0x1800137b6`
- name: `?InitializeByRemappingCoreFragment@RangeSet@@QEAAJAEAV?$SharedRefPtr@UICoreFragment@@@@AEAVRemapContext@@PEAVSyncIdCache@@@Z`
- size: `5462`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `broker_com_uri`

## callers

- `0x18000ced0`

## callees

- `0x180005d80`
- `0x180005e8c`
- `0x1800068a4`
- `0x180007114`
- `0x180007584`
- `0x18000e4e0`
- `0x18000e81c`
- `0x18000e868`
- `0x18000f810`
- `0x180010a80`
- `0x180011f60`
- `0x180011fc0`
- `0x180012260`
- `0x180013930`
- `0x1800158d0`
- `0x1800164e4`
- `0x1800166e0`
- `0x180019ef0`
- `0x18001a038`
- `0x18001ae20`
- `0x18001b4c8`
- `0x180024994`
- `0x180024d38`
- `0x180025740`
- `0x180093232`
- `0x180094010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001236f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800124a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012934`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012ba3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012fe9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013244`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800132c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001236f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800124a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012934`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012ba3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012fe9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013244`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800132c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001238e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001238e`

## pseudocode

```c
__int64 __fastcall RangeSet::InitializeByRemappingCoreFragment(__int64 a1, _QWORD *a2, __int64 a3, SyncIdCache *a4)
{
  SyncIdCache *v4; // r12
  __int64 v5; // r14
  __int64 v6; // rdi
  __int64 v7; // r13
  void *v8; // r15
  int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // rdx
  int v12; // eax
  int v13; // esi
  unsigned __int8 *v14; // r15
  __int64 v15; // rdx
  size_t v16; // rdi
  _DWORD *v17; // r12
  void *v18; // rcx
  unsigned int v19; // edx
  __int64 v20; // r8
  unsigned __int64 v21; // r9
  unsigned __int64 v22; // r10
  unsigned int v23; // r11d
  unsigned int v24; // esi
  unsigned __int64 v25; // rdx
  char v26; // cl
  ClockVector *v27; // rax
  ClockVector *v28; // rdi
  unsigned __int64 v29; // r8
  int v30; // r13d
  unsigned int v31; // edi
  volatile signed __int32 *v32; // r12
  char *v33; // rcx
  char *v34; // r9
  char *v35; // r11
  unsigned int v36; // edx
  unsigned int v37; // r8d
  char *v38; // rdx
  unsigned int v39; // edx
  __int64 v40; // rdx
  __int64 v41; // rbx
  unsigned int v42; // edx
  __int64 v43; // rdx
  __int64 v44; // rbx
  volatile signed __int32 *v45; // rcx
  int v46; // ecx
  void *v47; // rcx
  unsigned int v48; // edx
  unsigned int v49; // r8d
  unsigned int v50; // edi
  unsigned __int64 v52; // rbx
  __int64 v53; // rax
  bool v54; // cf
  SIZE_T v55; // rax
  _QWORD *v56; // rax
  _QWORD *v57; // r15
  ColumnEntry *i4; // rdi
  unsigned int v59; // r10d
  unsigned int *v60; // r13
  unsigned int v61; // r9d
  __int64 v62; // r11
  unsigned __int64 v63; // r14
  unsigned int v64; // esi
  unsigned int v65; // r12d
  unsigned __int64 v66; // rdx
  char v67; // cl
  PVOID *v68; // rax
  __int64 v69; // rsi
  int v70; // eax
  unsigned int *v71; // r14
  __int64 v72; // r9
  unsigned int *v73; // r15
  unsigned __int64 v74; // r8
  unsigned __int64 v75; // r13
  unsigned int v76; // r11d
  unsigned int v77; // r12d
  unsigned __int64 v78; // rdx
  unsigned __int64 v79; // r8
  char v80; // cl
  __int64 v81; // rdx
  unsigned int v82; // r9d
  unsigned int v83; // r12d
  unsigned int *v84; // r15
  int v85; // r13d
  __int64 v86; // r10
  unsigned __int64 v87; // rsi
  __int64 v88; // rax
  SIZE_T v89; // rax
  _QWORD *v90; // rax
  _QWORD *v91; // r15
  char *m; // r14
  unsigned int *v93; // r14
  unsigned int v94; // ecx
  unsigned int v95; // r10d
  int v96; // r14d
  __int64 kk; // r10
  __int64 v98; // rcx
  __int64 v99; // rsi
  __int64 v100; // rcx
  unsigned int v101; // r10d
  unsigned int v102; // r9d
  unsigned int jj; // r11d
  __int64 v104; // r8
  unsigned int v105; // r10d
  unsigned int v106; // r9d
  unsigned int i; // r11d
  __int64 v108; // r8
  unsigned __int64 v109; // r13
  unsigned __int64 v110; // r8
  unsigned int j; // r9d
  unsigned __int64 v112; // rdx
  unsigned __int64 v113; // r8
  char v114; // cl
  __int64 v115; // rdx
  unsigned int v116; // r12d
  unsigned int v117; // ecx
  unsigned int v118; // r10d
  int v119; // r14d
  __int64 k; // rsi
  __int64 v121; // r11
  __int64 v122; // r10
  ClockVector **v123; // rsi
  unsigned int v124; // edx
  __int64 v125; // rcx
  ClockVector **v126; // r14
  unsigned int v127; // eax
  unsigned int *v128; // rcx
  struct IClockVector *v129; // r14
  __int64 v130; // rsi
  unsigned __int64 v131; // r10
  unsigned int v132; // r15d
  __int64 v133; // rax
  __int64 v134; // rsi
  SIZE_T v135; // rax
  _QWORD *v136; // rax
  _QWORD *v137; // r13
  char *i1; // r14
  unsigned __int64 v139; // r8
  unsigned int mm; // r9d
  unsigned __int64 v141; // rdx
  char v142; // cl
  int v143; // r9d
  unsigned __int64 v144; // r8
  __int64 v145; // r11
  unsigned __int64 v146; // rax
  unsigned int nn; // r9d
  unsigned __int64 v148; // rdx
  __int64 v149; // rcx
  char v150; // al
  __int64 v151; // rcx
  __int64 v152; // rax
  unsigned __int64 v153; // r8
  __int64 v154; // r11
  unsigned __int64 v155; // rax
  unsigned int n; // r9d
  unsigned __int64 v157; // rdx
  __int64 v158; // rcx
  char v159; // al
  unsigned __int64 v160; // r14
  __int64 v161; // rax
  SIZE_T v162; // rax
  _QWORD *v163; // rax
  _QWORD *v164; // r12
  char *ii; // r15
  unsigned __int64 v166; // rbx
  __int64 v167; // rax
  SIZE_T v168; // rax
  _QWORD *v169; // rax
  _QWORD *v170; // r15
  ColumnEntry *i2; // rdi
  unsigned int v172; // eax
  int v173; // eax
  __int64 v174; // rsi
  __int64 v175; // rcx
  unsigned int NextPrimeNumber; // eax
  unsigned __int16 *v177; // rax
  unsigned __int8 *v178; // r10
  unsigned __int16 v179; // ax
  unsigned __int8 *v180; // r8
  unsigned __int8 *v181; // r11
  unsigned __int8 *i3; // r9
  int v183; // edx
  int v184; // ecx
  __int64 v185; // r11
  __int64 v186; // r10
  __int64 v187; // rcx
  unsigned __int16 *v188; // rax
  int v189; // [rsp+30h] [rbp-D0h]
  unsigned int v190; // [rsp+34h] [rbp-CCh]
  int v191; // [rsp+38h] [rbp-C8h]
  struct IClockVector *v192; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v193; // [rsp+48h] [rbp-B8h]
  unsigned int *v194; // [rsp+50h] [rbp-B0h]
  _BYTE v195[4]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v196; // [rsp+5Ch] [rbp-A4h]
  void *v197; // [rsp+60h] [rbp-A0h]
  int v198; // [rsp+68h] [rbp-98h]
  void *v199; // [rsp+70h] [rbp-90h]
  __int64 v200; // [rsp+78h] [rbp-88h]
  unsigned int v201; // [rsp+80h] [rbp-80h]
  void *v202; // [rsp+88h] [rbp-78h]
  int v203; // [rsp+90h] [rbp-70h]
  int v204; // [rsp+94h] [rbp-6Ch] BYREF
  LPVOID lpMem; // [rsp+98h] [rbp-68h]
  ClockVector *v206; // [rsp+A0h] [rbp-60h] BYREF
  struct IClockVector *v207; // [rsp+A8h] [rbp-58h]
  unsigned int *v208; // [rsp+B0h] [rbp-50h]
  __int64 v209; // [rsp+B8h] [rbp-48h]
  __int64 v210; // [rsp+C0h] [rbp-40h]
  char v211; // [rsp+C8h] [rbp-38h] BYREF
  char v212; // [rsp+D0h] [rbp-30h] BYREF
  char v213; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD *v215; // [rsp+158h] [rbp+58h]

  v215 = a2;
  v4 = a4;
  v5 = a3;
  v6 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      WPP_ff88f7f000e13ecf98ed337d60498caa_Traceguids,
      "RangeSet::InitializeByRemappingCoreFragment");
    a2 = v215;
  }
  v7 = v6 + 40;
  v210 = v6 + 40;
  if ( v6 + 40 != v5 + 8 )
  {
    *(_DWORD *)v7 = *(_DWORD *)(v5 + 8);
    *(_WORD *)(v6 + 44) = *(_WORD *)(v5 + 12);
  }
  *(_DWORD *)(v6 + 16) = 4;
  *(_DWORD *)(v6 + 8) = 0;
  v8 = 0;
  *(_DWORD *)(v6 + 32) = 0;
  v9 = -1;
  v190 = 0;
  v199 = 0;
  while ( 2 )
  {
    v10 = *a2;
    v11 = *(_QWORD *)(v5 + 48);
    v192 = 0;
    v204 = *(unsigned __int16 *)(v6 + 44);
    v12 = (*(__int64 (__fastcall **)(__int64, __int64, int *, struct IClockVector **))(*(_QWORD *)v10 + 32LL))(
            v10,
            v11,
            &v204,
            &v192);
    v13 = v12;
    if ( v12 == 1 )
    {
      if ( v192 )
        ((void (__fastcall *)(struct IClockVector *))v192->lpVtbl->Release)(v192);
      if ( v9 == -1 )
      {
        v13 = -2147217398;
        goto LABEL_112;
      }
      v50 = v190;
      v13 = 0;
      goto LABEL_113;
    }
    if ( v12 )
      goto LABEL_111;
    v14 = *(unsigned __int8 **)(v5 + 48);
    v196 = 0;
    v197 = 0;
    if ( v4 )
    {
      v173 = SyncIdCache::FindOrAddSyncId(v4, v14, (struct SyncId *)v195);
      v19 = v196;
      v13 = v173;
      v18 = v197;
      v198 = (unsigned __int16)v196;
      v202 = v197;
    }
    else
    {
      ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
      v16 = (unsigned int)v15;
      v17 = HeapAlloc(hHeap, 0, v15 + 7);
      v202 = v17;
      if ( lpMem )
        HeapFree(hHeap, 0, lpMem);
      lpMem = v17;
      if ( v17 )
      {
        v13 = 0;
        v197 = v17;
        lpMem = 0;
        *v17 = 1;
        memcpy_0(v17 + 1, v14, v16);
        v18 = v17;
        v196 = (*(_DWORD *)v7 & 1) << 16;
        LOWORD(v196) = *(_WORD *)(v7 + 4);
        v19 = v196;
        v198 = (unsigned __int16)v196;
      }
      else
      {
        v13 = -2147024882;
        SyncId::~SyncId((SyncId *)v195);
        v19 = 0;
        v18 = 0;
        v196 = 0;
        v202 = 0;
        v197 = 0;
        v198 = 0;
      }
      v5 = a3;
    }
    if ( v13 )
    {
      if ( (v19 & 0x20000) == 0 && v18 && _InterlockedExchangeAdd((volatile signed __int32 *)v18, 0xFFFFFFFF) == 1 )
        SeFree(v18);
      if ( v192 )
      {
        ((void (__fastcall *)(struct IClockVector *))v192->lpVtbl->Release)(v192);
        v8 = v199;
        goto LABEL_112;
      }
      goto LABEL_293;
    }
    v20 = *(_QWORD *)(v5 + 64);
    if ( v20 )
    {
      v21 = *(unsigned int *)(v5 + 56);
      v22 = (HIWORD(HIDWORD(v192)) | (WORD2(v192) << 16))
          ^ (((unsigned int)v192 >> 16) | ((unsigned __int16)v192 << 16));
      v23 = 0;
      v24 = (((unsigned int)v22 >> 5) + 1) % ((int)v21 - 1) + 1;
      while ( v23 < (unsigned int)v21 )
      {
        v25 = v22 % v21;
        v26 = *(_BYTE *)(v20 + 24 * (v22 % v21) + 16);
        if ( (v26 & 1) != 0 )
        {
          if ( *(struct IClockVector **)(v20 + 24 * (v22 % v21)) == v192 )
          {
            v30 = *(_DWORD *)(v20 + 24LL * (unsigned int)v25 + 8);
            v189 = v30;
            goto LABEL_31;
          }
        }
        else if ( (v26 & 2) == 0 )
        {
          break;
        }
        v22 = v25 + v24;
        ++v23;
      }
    }
    v27 = (ClockVector *)HeapAlloc(hHeap, 0, 0x40u);
    if ( !v27 )
    {
      v206 = 0;
      v13 = -2147024882;
LABEL_355:
      SyncId::~SyncId((SyncId *)v195);
      SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>((__int64 *)&v192);
      v8 = v199;
      goto LABEL_112;
    }
    v189 = 0;
    v206 = ClockVector::ClockVector(v27);
    v28 = v206;
    if ( !v206 )
    {
      v13 = -2147024882;
      goto LABEL_27;
    }
    v13 = ClockVector::InitializeWithExternalInstance(v206, v192);
    if ( v13 )
    {
      v30 = 0;
      goto LABEL_29;
    }
    if ( *(_DWORD *)(v5 + 40) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          WPP_362d7c742a68350205e0bfe72ed984ca_Traceguids,
          "ClockVector::RemapReplicaKeys");
      }
      if ( *((_DWORD *)v28 + 7) )
      {
        v59 = 0;
        while ( 1 )
        {
          v60 = (unsigned int *)(*((_QWORD *)v28 + 5) + 16LL * v59);
          v61 = *v60;
          if ( *(_DWORD *)(v5 + 40) )
            break;
LABEL_140:
          v13 = 0;
          *v60 = v61;
          if ( ++v59 >= *((_DWORD *)v28 + 7) )
          {
            Algorithms::QuickSort<SyncVersion,ClockVector::CompareFunctor,ClockVector::SwapFunctor>(
              *((char **)v28 + 5),
              *((_DWORD *)v28 + 7),
              v29,
              v28);
            goto LABEL_142;
          }
        }
        v62 = *(_QWORD *)(v5 + 32);
        if ( v62 )
        {
          v63 = *(unsigned int *)(v5 + 24);
          v29 = HIWORD(v61) | ((unsigned __int16)v61 << 16);
          v64 = 0;
          v65 = (((unsigned int)v29 >> 5) + 1) % ((int)v63 - 1) + 1;
          while ( v64 < (unsigned int)v63 )
          {
            v66 = v29 % v63;
            v67 = *(_BYTE *)(v62 + 12 * (v29 % v63) + 8);
            if ( (v67 & 1) != 0 )
            {
              if ( *(_DWORD *)(v62 + 12 * (v29 % v63)) == v61 )
              {
                v5 = a3;
                v61 = *(_DWORD *)(v62 + 12LL * (unsigned int)v66 + 4);
                goto LABEL_140;
              }
            }
            else if ( (v67 & 2) == 0 )
            {
              break;
            }
            v29 = v66 + v65;
            ++v64;
          }
          v5 = a3;
        }
        ClockVector::Recycle(v28);
        v13 = -2147024809;
      }
      else
      {
        v13 = 0;
      }
LABEL_142:
      v68 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          (unsigned int)WPP_362d7c742a68350205e0bfe72ed984ca_Traceguids,
          (unsigned int)"ClockVector::RemapReplicaKeys",
          v13);
        v68 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v13 )
        goto LABEL_27;
    }
    else
    {
      v68 = (PVOID *)WPP_GLOBAL_Control;
    }
    v69 = *(_QWORD *)(v5 + 80);
    v207 = (struct IClockVector *)v69;
    if ( v68 != &WPP_GLOBAL_Control && (*((_BYTE *)v68 + 28) & 1) != 0 && *((_BYTE *)v68 + 25) >= 5u )
      WPP_SF_s(v68[2], 10, WPP_e65626ae806d36e8966776faf765a664_Traceguids, "ClockVectorManager::FindByKeyOrAdd");
    v70 = *(_DWORD *)(v69 + 16);
    v71 = (unsigned int *)(v69 + 16);
    v72 = *(_QWORD *)(v69 + 48);
    v73 = (unsigned int *)(v69 + 40);
    v194 = (unsigned int *)(v69 + 16);
    v191 = v70;
    v209 = v69 + 40;
    v193 = v72;
    if ( !v72 )
    {
LABEL_158:
      v83 = *((_DWORD *)v28 + 14);
      v84 = v71 + 6;
      v85 = *v71;
      v208 = v71 + 6;
      v203 = v85;
      v201 = v83;
      if ( v83 == -1 )
      {
        v105 = *((_DWORD *)v28 + 7);
        v106 = v105 ^ (*((_DWORD *)v28 + 9) >> 1) & 1;
        if ( v105 )
        {
          for ( i = 0; i < v105; ++i )
          {
            v108 = i;
            v106 = *(_DWORD *)(16 * v108 + *((_QWORD *)v28 + 5))
                 ^ *(_QWORD *)(16 * v108 + *((_QWORD *)v28 + 5) + 8)
                 ^ (32 * v106)
                 ^ (v106 >> 27)
                 ^ HIDWORD(*(_QWORD *)(16 * v108 + *((_QWORD *)v28 + 5) + 8));
          }
        }
        v83 = 0x7FFFFFFF;
        if ( v106 != -1 )
          v83 = v106;
        v201 = v83;
        *((_DWORD *)v28 + 14) = v83;
      }
      v86 = *((_QWORD *)v71 + 4);
      v200 = v86;
      if ( v86 )
      {
        v109 = *v84;
        v110 = v83;
        LODWORD(v193) = ((v83 >> 5) + 1) % ((int)v109 - 1) + 1;
        for ( j = 0; j < (unsigned int)v109; ++j )
        {
          v112 = v110 % v109;
          v113 = v112;
          v114 = *(_BYTE *)(v86 + 24 * v112 + 16);
          if ( (v114 & 1) != 0 )
          {
            v115 = *(_QWORD *)(v86 + 24 * v112);
            if ( (ClockVector *)v115 == v28 )
              goto LABEL_261;
            v116 = *(_DWORD *)(v115 + 28);
            if ( v116 == *((_DWORD *)v28 + 7) )
            {
              v117 = *((_DWORD *)v28 + 9);
              v118 = *(_DWORD *)(v115 + 36);
              v119 = (v118 >> 1) & 1;
              if ( v119 == ((v117 >> 1) & 1)
                && *(_DWORD *)(v115 + 32) == *((_DWORD *)v28 + 8)
                && (((unsigned __int8)v118 ^ (unsigned __int8)v117) & 4) == 0 )
              {
                for ( k = 0; (unsigned int)k < v116; k = (unsigned int)(k + 1) )
                {
                  v121 = *((_QWORD *)v28 + 5);
                  v122 = *(_QWORD *)(v115 + 40);
                  if ( *(_DWORD *)(v122 + 16LL * (unsigned int)k) != *(_DWORD *)(v121 + 16LL * (unsigned int)k) )
                    goto LABEL_334;
                  if ( *(_QWORD *)(v122 + 16LL * (unsigned int)k + 8) != *(_QWORD *)(v121 + 16LL * (unsigned int)k + 8) )
                    goto LABEL_334;
                  if ( v119 )
                  {
                    v185 = *((_QWORD *)v28 + 6);
                    v186 = *(_QWORD *)(v115 + 48);
                    v187 = 12 * k;
                    if ( *(_DWORD *)(v186 + 12 * k) != *(_DWORD *)(v185 + 12 * k)
                      || *(_DWORD *)(v186 + v187 + 4) != *(_DWORD *)(v185 + v187 + 4)
                      || *(_BYTE *)(v186 + v187 + 8) != *(_BYTE *)(v185 + v187 + 8) )
                    {
                      goto LABEL_334;
                    }
                  }
                }
LABEL_261:
                v13 = -2147024809;
                goto LABEL_222;
              }
LABEL_334:
              v86 = v200;
            }
          }
          else if ( (v114 & 2) == 0 )
          {
            break;
          }
          v110 = (unsigned int)v193 + v113;
        }
        if ( v84[4] + 1 <= 72 * *v84 / 0x64
          || (NextPrimeNumber = GetNextPrimeNumber(2 * *v84),
              v13 = HashTable<SharedRefPtr<ClockVector>,unsigned long,SimpleHashTableContext>::Resize(
                      v84,
                      NextPrimeNumber),
              v13 >= 0) )
        {
          v83 = v201;
          v85 = v203;
          v93 = v194;
          goto LABEL_255;
        }
        goto LABEL_222;
      }
      v87 = *v84;
      v88 = 24 * v87;
      if ( !is_mul_ok(v87, 0x18u) )
        v88 = -1;
      v54 = __CFADD__(v88, 8);
      v89 = v88 + 8;
      if ( v54 )
        v89 = -1;
      v90 = HeapAlloc(hHeap, 0, v89);
      if ( v90 )
      {
        *v90 = v87;
        v91 = v90 + 1;
        for ( m = (char *)(v90 + 1); v87; --v87 )
        {
          TableBucket<SharedRefPtr<RangeSet>,unsigned long,SimpleHashTableContext>::TableBucket<SharedRefPtr<RangeSet>,unsigned long,SimpleHashTableContext>(m);
          m += 24;
        }
        v93 = v194;
        *((_QWORD *)v194 + 4) = v91;
        if ( v91 )
        {
          v84 = v208;
LABEL_255:
          v153 = *v84;
          v154 = *((_QWORD *)v84 + 1);
          v155 = v83;
          for ( n = 0; ; ++n )
          {
            if ( n >= (unsigned int)v153 )
            {
              v13 = -2147418113;
              goto LABEL_222;
            }
            v157 = v155 % v153;
            v158 = v154 + 24 * (v155 % v153);
            v159 = *(_BYTE *)(v158 + 16);
            if ( (v159 & 1) == 0 )
              break;
            *(_BYTE *)(v158 + 16) = v159 | 2;
            v155 = v157 + ((v83 >> 5) + 1) % ((int)v153 - 1) + 1;
          }
          v123 = (ClockVector **)(*((_QWORD *)v84 + 1) + 24LL * (unsigned int)v157);
          (*(void (__fastcall **)(ClockVector *))(*(_QWORD *)v28 + 8LL))(v28);
          if ( v123 != (ClockVector **)&v211 )
          {
            if ( *v123 )
              (*(void (__fastcall **)(ClockVector *))(*(_QWORD *)*v123 + 16LL))(*v123);
            *v123 = v28;
            (*(void (__fastcall **)(ClockVector *))(*(_QWORD *)v28 + 8LL))(v28);
          }
          (*(void (__fastcall **)(ClockVector *))(*(_QWORD *)v28 + 16LL))(v28);
          *((_BYTE *)v123 + 16) |= 1u;
          *((_DWORD *)v123 + 2) = v85;
          v13 = 0;
          ++v84[4];
          if ( *((_QWORD *)v93 + 2) )
          {
            v124 = v93[1];
            if ( *v93 + 1 > v124 )
            {
              v13 = Vector<SharedRefPtr<ClockVector>,1>::IncreaseCapacity(v93, 2 * v124);
              if ( v13 < 0 )
                goto LABEL_217;
            }
            goto LABEL_213;
          }
          v160 = v93[2];
          v161 = 8 * v160;
          if ( !is_mul_ok(v160, 8u) )
            v161 = -1;
          v54 = __CFADD__(v161, 8);
          v162 = v161 + 8;
          if ( v54 )
            v162 = -1;
          v163 = HeapAlloc(hHeap, 0, v162);
          v164 = v163;
          if ( v163 )
          {
            *v163 = v160;
            for ( ii = (char *)(v163 + 1); v160; --v160 )
            {
              SharedRefPtr<Legacy::Override>::`default constructor closure'(ii);
              ii += 8;
            }
            v93 = v194;
            *((_QWORD *)v194 + 2) = v164 + 1;
            if ( v164 != (_QWORD *)-8LL )
            {
              v93[1] = v93[2];
LABEL_213:
              v125 = *v93;
              v126 = (ClockVector **)(*((_QWORD *)v93 + 2) + 8 * v125);
              v127 = v125 + 1;
              v128 = v194;
              *v194 = v127;
              if ( v126 == &v206 )
              {
                v93 = v128;
              }
              else
              {
                if ( *v126 )
                  (*(void (__fastcall **)(ClockVector *))(*(_QWORD *)*v126 + 16LL))(*v126);
                *v126 = v28;
                (*(void (__fastcall **)(ClockVector *))(*(_QWORD *)v28 + 8LL))(v28);
                v93 = v194;
              }
LABEL_217:
              if ( !v13 )
              {
                v189 = *v93 - 1;
                goto LABEL_219;
              }
LABEL_337:
              HashTable<SharedRefPtr<ClockVector>,unsigned long,SimpleHashTableContext>::RemoveItem(v209, &v206);
LABEL_219:
              if ( v13 )
                goto LABEL_222;
              goto LABEL_220;
            }
          }
          else
          {
            *((_QWORD *)v194 + 2) = 0;
          }
          v13 = -2147024882;
          goto LABEL_337;
        }
      }
      else
      {
        *((_QWORD *)v71 + 4) = 0;
      }
      v13 = -2147024882;
      goto LABEL_222;
    }
    v74 = *((unsigned int *)v28 + 14);
    v75 = *v73;
    if ( (_DWORD)v74 == -1 )
    {
      v101 = *((_DWORD *)v28 + 7);
      v102 = v101 ^ (*((_DWORD *)v28 + 9) >> 1) & 1;
      if ( v101 )
      {
        for ( jj = 0; jj < v101; ++jj )
        {
          v104 = jj;
          v102 = *(_DWORD *)(16 * v104 + *((_QWORD *)v28 + 5))
               ^ *(_QWORD *)(16 * v104 + *((_QWORD *)v28 + 5) + 8)
               ^ (32 * v102)
               ^ (v102 >> 27)
               ^ HIDWORD(*(_QWORD *)(16 * v104 + *((_QWORD *)v28 + 5) + 8));
        }
      }
      v74 = 0x7FFFFFFF;
      if ( v102 != -1 )
        v74 = v102;
      v72 = v193;
      *((_DWORD *)v28 + 14) = v74;
    }
    v76 = 0;
    v77 = (((unsigned int)v74 >> 5) + 1) % ((int)v75 - 1) + 1;
    while ( 1 )
    {
      if ( v76 >= (unsigned int)v75 )
      {
LABEL_157:
        v71 = v194;
        goto LABEL_158;
      }
      v78 = v74 % v75;
      v79 = v78;
      v80 = *(_BYTE *)(v72 + 24 * v78 + 16);
      if ( (v80 & 1) != 0 )
        break;
      if ( (v80 & 2) == 0 )
        goto LABEL_157;
LABEL_155:
      v74 = v77 + v79;
      ++v76;
    }
    v81 = *(_QWORD *)(v72 + 24 * v78);
    if ( (ClockVector *)v81 == v28 )
      goto LABEL_206;
    v82 = *(_DWORD *)(v81 + 28);
    if ( v82 != *((_DWORD *)v28 + 7)
      || (v94 = *((_DWORD *)v28 + 9), v95 = *(_DWORD *)(v81 + 36), v96 = (v95 >> 1) & 1, v96 != ((v94 >> 1) & 1))
      || *(_DWORD *)(v81 + 32) != *((_DWORD *)v28 + 8)
      || (((unsigned __int8)v95 ^ (unsigned __int8)v94) & 4) != 0 )
    {
LABEL_154:
      v72 = v193;
      goto LABEL_155;
    }
    for ( kk = 0; (unsigned int)kk < v82; kk = (unsigned int)(kk + 1) )
    {
      v98 = 16LL * (unsigned int)kk;
      v99 = v98 + *(_QWORD *)(v81 + 40);
      v100 = *((_QWORD *)v28 + 5) + v98;
      if ( *(_DWORD *)v99 != *(_DWORD *)v100 )
        goto LABEL_154;
      if ( *(_QWORD *)(v99 + 8) != *(_QWORD *)(v100 + 8) )
        goto LABEL_154;
      if ( v96 )
      {
        v174 = 12 * kk + *(_QWORD *)(v81 + 48);
        v175 = *((_QWORD *)v28 + 6) + 12 * kk;
        if ( *(_DWORD *)v174 != *(_DWORD *)v175
          || *(_DWORD *)(v174 + 4) != *(_DWORD *)(v175 + 4)
          || *(_BYTE *)(v174 + 8) != *(_BYTE *)(v175 + 8) )
        {
          goto LABEL_154;
        }
      }
    }
LABEL_206:
    v13 = 0;
    v189 = *(_DWORD *)(*((_QWORD *)v73 + 1) + 24LL * (unsigned int)v79 + 8);
LABEL_220:
    if ( LODWORD(v207[2].lpVtbl) != v191 )
      LODWORD(v207[1].lpVtbl) = -1;
LABEL_222:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_e65626ae806d36e8966776faf765a664_Traceguids,
        (unsigned int)"ClockVectorManager::FindByKeyOrAdd",
        v13);
    }
    if ( v13 )
      goto LABEL_27;
    v129 = v192;
    v130 = *(_QWORD *)(a3 + 64);
    v131 = *(unsigned int *)(a3 + 56);
    v207 = v192;
    v132 = (HIWORD(HIDWORD(v192)) | (WORD2(v192) << 16)) ^ (((unsigned int)v192 >> 16) | ((unsigned __int16)v192 << 16));
    if ( v130 )
    {
      v139 = v132;
      for ( mm = 0; mm < (unsigned int)v131; ++mm )
      {
        v141 = v139 % v131;
        v142 = *(_BYTE *)(v130 + 24 * (v139 % v131) + 16);
        if ( (v142 & 1) != 0 )
        {
          if ( *(struct IClockVector **)(v130 + 24 * v141) == v192 )
          {
            v13 = -2147024809;
            goto LABEL_27;
          }
        }
        else if ( (v142 & 2) == 0 )
        {
          break;
        }
        v139 = ((v132 >> 5) + 1) % ((int)v131 - 1) + 1 + v141;
      }
      v143 = *(_DWORD *)(a3 + 56);
      if ( *(_DWORD *)(a3 + 72) + 1 > 72 * v143 / 0x64u )
      {
        v172 = GetNextPrimeNumber(2 * v143);
        v13 = HashTable<void *,unsigned long,DefaultHashTableContext>::Resize(a3 + 56, v172);
        if ( v13 < 0 )
          goto LABEL_27;
      }
LABEL_242:
      v144 = *(unsigned int *)(a3 + 56);
      v145 = *(_QWORD *)(a3 + 64);
      v146 = v132;
      for ( nn = 0; ; ++nn )
      {
        if ( nn >= (unsigned int)v144 )
        {
          v13 = -2147418113;
          goto LABEL_27;
        }
        v148 = v146 % v144;
        v149 = v145 + 24 * (v146 % v144);
        v150 = *(_BYTE *)(v149 + 16);
        if ( (v150 & 1) == 0 )
          break;
        *(_BYTE *)(v149 + 16) = v150 | 2;
        v146 = v148 + ((v132 >> 5) + 1) % ((int)v144 - 1) + 1;
      }
      v30 = v189;
      v13 = 0;
      v151 = 3LL * (unsigned int)v148;
      v152 = *(_QWORD *)(a3 + 64);
      *(_BYTE *)(v152 + 8 * v151 + 16) |= 1u;
      *(_QWORD *)(v152 + 8 * v151) = v129;
      *(_DWORD *)(v152 + 8 * v151 + 8) = v189;
      ++*(_DWORD *)(a3 + 72);
    }
    else
    {
      v133 = 24 * v131;
      v134 = (unsigned int)v131;
      if ( !is_mul_ok(v131, 0x18u) )
        v133 = -1;
      v54 = __CFADD__(v133, 8);
      v135 = v133 + 8;
      if ( v54 )
        v135 = -1;
      v136 = HeapAlloc(hHeap, 0, v135);
      if ( v136 )
      {
        *v136 = v134;
        v137 = v136 + 1;
        for ( i1 = (char *)(v136 + 1); v134; --v134 )
        {
          TableBucket<IUnknown *,KnowledgeCookie *,DefaultHashTableContext>::TableBucket<IUnknown *,KnowledgeCookie *,DefaultHashTableContext>(i1);
          i1 += 24;
        }
        *(_QWORD *)(a3 + 64) = v137;
        if ( v137 )
        {
          v129 = v207;
          goto LABEL_242;
        }
      }
      else
      {
        *(_QWORD *)(a3 + 64) = 0;
      }
      v13 = -2147024882;
LABEL_27:
      v30 = v189;
    }
    if ( v28 )
LABEL_29:
      (*(void (__fastcall **)(ClockVector *))(*(_QWORD *)v28 + 16LL))(v28);
    if ( v13 )
      goto LABEL_355;
LABEL_31:
    if ( v9 == -1 )
    {
      if ( !(unsigned int)SyncId::IsZeroId((SyncId *)v195) )
      {
        v13 = -2147217398;
LABEL_291:
        SyncId::~SyncId((SyncId *)v195);
        if ( v192 )
          ((void (__fastcall *)(struct IClockVector *))v192->lpVtbl->Release)(v192);
LABEL_293:
        v8 = v199;
        goto LABEL_112;
      }
      v32 = (volatile signed __int32 *)v202;
      if ( v202 )
        _InterlockedIncrement((volatile signed __int32 *)v202);
      v13 = 0;
      if ( !*(_QWORD *)(a1 + 24) )
      {
        v166 = *(unsigned int *)(a1 + 16);
        v167 = 24 * v166;
        if ( !is_mul_ok(v166, 0x18u) )
          v167 = -1;
        v54 = __CFADD__(v167, 8);
        v168 = v167 + 8;
        if ( v54 )
          v168 = -1;
        v169 = HeapAlloc(hHeap, 0, v168);
        v170 = v169;
        if ( !v169 )
        {
          *(_QWORD *)(a1 + 24) = 0;
LABEL_345:
          v13 = -2147024882;
          goto LABEL_61;
        }
        *v169 = v166;
        for ( i2 = (ColumnEntry *)(v169 + 1); v166; --v166 )
        {
          ColumnEntry::ColumnEntry(i2);
          i2 = (ColumnEntry *)((char *)i2 + 24);
        }
        *(_QWORD *)(a1 + 24) = v170 + 1;
        if ( v170 == (_QWORD *)-8LL )
          goto LABEL_345;
        *(_DWORD *)(a1 + 12) = *(_DWORD *)(a1 + 16);
LABEL_55:
        v40 = *(unsigned int *)(a1 + 8);
        v41 = *(_QWORD *)(a1 + 24) + 24 * v40;
        *(_DWORD *)(a1 + 8) = v40 + 1;
        if ( (char *)v41 != &v212 )
        {
          SyncId::~SyncId((SyncId *)v41);
          *(_DWORD *)(v41 + 4) = v196;
          *(_QWORD *)(v41 + 8) = v32;
          if ( v32 )
            _InterlockedIncrement(v32);
        }
        *(_DWORD *)(v41 + 16) = v30;
        goto LABEL_59;
      }
      v39 = *(_DWORD *)(a1 + 12);
      if ( *(_DWORD *)(a1 + 8) + 1 <= v39 )
        goto LABEL_55;
      v13 = Vector<Range,1>::IncreaseCapacity(a1 + 8, 2 * v39);
      if ( v13 >= 0 )
        goto LABEL_55;
LABEL_59:
      if ( !v13 )
        *(_DWORD *)(a1 + 32) += v30 == 0;
LABEL_61:
      v31 = v196;
      if ( (v196 & 0x20000) == 0 && v32 && _InterlockedExchangeAdd(v32, 0xFFFFFFFF) == 1 )
        SeFree((void *)v32);
      if ( v13 )
        goto LABEL_291;
LABEL_88:
      v9 = v30;
      if ( (v190 & 0x20000) == 0 )
      {
        v47 = v199;
        if ( v199 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v199, 0xFFFFFFFF) == 1 )
            SeFree(v47);
        }
      }
      v190 = v31;
      v8 = (void *)v32;
      v199 = (void *)v32;
      if ( v32 )
        _InterlockedIncrement(v32);
      if ( (v31 & 0x20000) == 0 && v32 && _InterlockedExchangeAdd(v32, 0xFFFFFFFF) == 1 )
      {
        SeFree((void *)v32);
        v197 = 0;
      }
      v5 = a3;
      v7 = v210;
      v6 = a1;
      v4 = a4;
      a2 = v215;
      if ( v192 )
      {
        ((void (__fastcall *)(struct IClockVector *, _QWORD *))v192->lpVtbl->Release)(v192, v215);
        a2 = v215;
      }
      continue;
    }
    break;
  }
  v31 = v196;
  v32 = (volatile signed __int32 *)v202;
  v33 = (char *)v202;
  if ( ((v196 >> 17) & 1) == 0 )
    v33 = (char *)v202 + 4;
  v8 = v199;
  v34 = (char *)v199;
  if ( (v190 & 0x20000) == 0 )
    v34 = (char *)v199 + 4;
  if ( v33 == v34 )
    goto LABEL_110;
  if ( (v196 & 0x10000) != 0 )
  {
    v177 = (unsigned __int16 *)v202;
    if ( ((v196 >> 17) & 1) == 0 )
      v177 = (unsigned __int16 *)((char *)v202 + 4);
    v178 = (unsigned __int8 *)&v33[*v177];
    if ( (v190 & 0x10000) != 0 )
    {
      v188 = (unsigned __int16 *)v199;
      if ( (v190 & 0x20000) == 0 )
        v188 = (unsigned __int16 *)((char *)v199 + 4);
      v179 = *v188;
    }
    else
    {
      v179 = v190;
    }
    v180 = (unsigned __int8 *)(v33 + 2);
    v181 = (unsigned __int8 *)&v34[v179];
    v189 = v30;
    for ( i3 = (unsigned __int8 *)(v34 + 2); ; ++i3 )
    {
      if ( v180 >= v178 )
        goto LABEL_110;
      if ( i3 >= v181 )
        goto LABEL_68;
      v183 = *i3;
      v184 = *v180;
      if ( v184 != v183 )
        break;
      ++v180;
    }
    if ( (unsigned __int8)v184 <= (unsigned __int8)v183 )
      goto LABEL_110;
LABEL_68:
    if ( v30 == v9 )
      goto LABEL_88;
    if ( v202 )
      _InterlockedIncrement((volatile signed __int32 *)v202);
    v13 = 0;
    if ( *(_QWORD *)(a1 + 24) )
    {
      v42 = *(_DWORD *)(a1 + 12);
      if ( *(_DWORD *)(a1 + 8) + 1 > v42 )
      {
        v13 = Vector<Range,1>::IncreaseCapacity(a1 + 8, 2 * v42);
        if ( v13 < 0 )
        {
          v46 = v189;
LABEL_81:
          v30 = v189;
          if ( !v13 )
            *(_DWORD *)(a1 + 32) += v46 == 0;
LABEL_83:
          if ( (v31 & 0x20000) == 0 && v32 && _InterlockedExchangeAdd(v32, 0xFFFFFFFF) == 1 )
            SeFree((void *)v32);
          if ( v13 )
            goto LABEL_355;
          goto LABEL_88;
        }
      }
LABEL_73:
      v43 = *(unsigned int *)(a1 + 8);
      v44 = *(_QWORD *)(a1 + 24) + 24 * v43;
      *(_DWORD *)(a1 + 8) = v43 + 1;
      if ( (char *)v44 != &v213 )
      {
        if ( (*(_DWORD *)(v44 + 4) & 0x20000) == 0 )
        {
          v45 = *(volatile signed __int32 **)(v44 + 8);
          if ( v45 )
          {
            if ( _InterlockedExchangeAdd(v45, 0xFFFFFFFF) == 1 )
              SeFree(*(void **)(v44 + 8));
          }
        }
        *(_DWORD *)(v44 + 4) = v31;
        *(_QWORD *)(v44 + 8) = v32;
        if ( v32 )
          _InterlockedIncrement(v32);
      }
      v46 = v189;
      *(_DWORD *)(v44 + 16) = v189;
      goto LABEL_81;
    }
    v52 = *(unsigned int *)(a1 + 16);
    v53 = 24 * v52;
    if ( !is_mul_ok(v52, 0x18u) )
      v53 = -1;
    v54 = __CFADD__(v53, 8);
    v55 = v53 + 8;
    if ( v54 )
      v55 = -1;
    v56 = HeapAlloc(hHeap, 0, v55);
    v57 = v56;
    if ( v56 )
    {
      *v56 = v52;
      for ( i4 = (ColumnEntry *)(v56 + 1); v52; --v52 )
      {
        ColumnEntry::ColumnEntry(i4);
        i4 = (ColumnEntry *)((char *)i4 + 24);
      }
      v31 = v196;
      *(_QWORD *)(a1 + 24) = v57 + 1;
      if ( v57 != (_QWORD *)-8LL )
      {
        *(_DWORD *)(a1 + 12) = *(_DWORD *)(a1 + 16);
        goto LABEL_73;
      }
    }
    else
    {
      *(_QWORD *)(a1 + 24) = 0;
    }
    v13 = -2147024882;
    goto LABEL_83;
  }
  v35 = &v33[4 * ((unsigned __int64)(unsigned __int16)v198 >> 2)];
  while ( v33 < v35 )
  {
    v36 = *(_DWORD *)v34;
    v37 = *(_DWORD *)v33;
    if ( *(_DWORD *)v33 != *(_DWORD *)v34 )
    {
      if ( (unsigned __int8)v37 > (unsigned __int8)v36 )
        goto LABEL_47;
      if ( (unsigned __int8)v37 < (unsigned __int8)v36 || BYTE1(v37) < BYTE1(v36) )
        goto LABEL_110;
      if ( BYTE1(v37) > BYTE1(v36) || BYTE2(v37) > BYTE2(v36) )
        goto LABEL_47;
      if ( BYTE2(v37) < BYTE2(v36) )
        goto LABEL_110;
      v48 = HIBYTE(v36);
      v49 = HIBYTE(v37);
      if ( (unsigned __int8)v49 > (unsigned __int8)v48 )
      {
LABEL_47:
        v30 = v189;
        goto LABEL_68;
      }
      if ( (unsigned __int8)v49 < (unsigned __int8)v48 )
        goto LABEL_110;
    }
    v33 += 4;
    v34 += 4;
  }
  if ( (v198 & 3) != 0 )
  {
    v38 = (char *)v202;
    if ( (v196 & 0x20000) == 0 )
      v38 = (char *)v202 + 4;
    while ( v33 < &v38[(unsigned __int16)v198] )
    {
      if ( (unsigned __int8)*v33 > (unsigned __int8)*v34 )
        goto LABEL_47;
      if ( (unsigned __int8)*v33 < (unsigned __int8)*v34 )
        break;
      ++v33;
      ++v34;
    }
  }
LABEL_110:
  v13 = -2147217398;
  SyncId::~SyncId((SyncId *)v195);
LABEL_111:
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>((__int64 *)&v192);
LABEL_112:
  v50 = v190;
  RangeSet::Recycle((RangeSet *)a1);
LABEL_113:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      31,
      (unsigned int)WPP_ff88f7f000e13ecf98ed337d60498caa_Traceguids,
      (unsigned int)"RangeSet::InitializeByRemappingCoreFragment",
      v13);
  }
  if ( (v50 & 0x20000) == 0 && v8 && _InterlockedExchangeAdd((volatile signed __int32 *)v8, 0xFFFFFFFF) == 1 )
    SeFree(v8);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180012260  mov     [rsp-8+arg_18], r9
0x180012265  mov     [rsp-8+arg_10], r8
0x18001226a  mov     [rsp-8+arg_8], rdx
0x18001226f  mov     [rsp-8+arg_0], rcx
0x180012274  push    rbp
0x180012275  push    rbx
0x180012276  push    rsi
0x180012277  push    rdi
0x180012278  push    r12
0x18001227a  push    r13
0x18001227c  push    r14
0x18001227e  push    r15
0x180012280  lea     rbp, [rsp-8]
0x180012285  sub     rsp, 108h
0x18001228c  mov     r12, r9
0x18001228f  mov     r14, r8
0x180012292  mov     rdi, rcx
0x180012295  mov     rcx, cs:WPP_GLOBAL_Control
0x18001229c  lea     rax, WPP_GLOBAL_Control
0x1800122a3  cmp     rcx, rax
0x1800122a6  jnz     loc_18001342C
0x1800122ac  lea     r13, [rdi+28h]
0x1800122b0  lea     rcx, [r14+8]
0x1800122b4  mov     [rbp+40h+var_80], r13
0x1800122b8  cmp     r13, rcx
0x1800122bb  jz      short loc_1800122CC
0x1800122bd  mov     eax, [rcx]
0x1800122bf  mov     [r13+0], eax
0x1800122c3  movzx   eax, word ptr [rcx+4]
0x1800122c7  mov     [r13+4], ax
0x1800122cc  xor     eax, eax
0x1800122ce  mov     dword ptr [rdi+10h], 4
0x1800122d5  mov     [rdi+8], eax
0x1800122d8  mov     r15d, eax
0x1800122db  mov     [rdi+20h], eax
0x1800122de  mov     ebx, 0FFFFFFFFh
0x1800122e3  mov     [rsp+140h+var_10C], eax
0x1800122e7  mov     [rsp+140h+var_D0], rax
0x1800122ec  nop     dword ptr [rax+00h]
0x1800122f0  mov     rcx, [rdx]
0x1800122f3  lea     r9, [rsp+140h+var_100]
0x1800122f8  mov     rdx, [r14+30h]
0x1800122fc  lea     r8, [rbp+40h+var_AC]
0x180012300  mov     [rsp+140h+var_100], rax
0x180012305  movzx   eax, word ptr [rdi+2Ch]
0x180012309  mov     [rbp+40h+var_AC], eax
0x18001230c  mov     rax, [rcx]
0x18001230f  mov     rax, [rax+20h]
0x180012313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012318  mov     esi, eax
0x18001231a  cmp     eax, 1
0x18001231d  jz      loc_180013483
0x180012323  test    eax, eax
0x180012325  jnz     loc_18001289C
0x18001232b  mov     r15, [r14+30h]
0x18001232f  xor     edi, edi
0x180012331  mov     [rsp+140h+var_E4], edi
0x180012335  mov     [rsp+140h+var_E0], rdi
0x18001233a  test    r12, r12
0x18001233d  jnz     loc_1800134B8
0x180012343  cmp     [r13+0], edi
0x180012347  jnz     loc_1800136A2
0x18001234d  lea     rdx, [r13+4]
0x180012351  mov     r14, rdx
0x180012354  movzx   edx, word ptr [rdx]
0x180012357  lea     rcx, [rbp+40h+lpMem]
0x18001235b  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x180012360  mov     rcx, cs:hHeap; hHeap
0x180012367  lea     r8, [rdx+7]; dwBytes
0x18001236b  mov     edi, edx
0x18001236d  xor     edx, edx; dwFlags
0x18001236f  call    cs:__imp_HeapAlloc
0x180012375  mov     r8, [rbp+40h+lpMem]; lpMem
0x180012379  mov     r12, rax
0x18001237c  mov     [rbp+40h+var_B8], rax
0x180012380  test    r8, r8
0x180012383  jz      short loc_180012394
0x180012385  mov     rcx, cs:hHeap; hHeap
0x18001238c  xor     edx, edx; dwFlags
0x18001238e  call    cs:__imp_HeapFree
0x180012394  mov     [rbp+40h+lpMem], r12
0x180012398  test    r12, r12
0x18001239b  jz      loc_180012471
0x1800123a1  xor     esi, esi
0x1800123a3  mov     [rsp+140h+var_E0], r12
0x1800123a8  lea     rcx, [r12+4]; void *
0x1800123ad  mov     [rbp+40h+lpMem], rsi
0x1800123b1  mov     r8, rdi; Size
0x1800123b4  mov     dword ptr [r12], 1
0x1800123bc  mov     rdx, r15; Src
0x1800123bf  call    memcpy_0
0x1800123c4  mov     eax, [r13+0]
0x1800123c8  mov     rcx, r12; void *
0x1800123cb  and     eax, 1
0x1800123ce  shl     eax, 10h
0x1800123d1  mov     [rsp+140h+var_E4], eax
0x1800123d5  movzx   eax, word ptr [r14]
0x1800123d9  mov     word ptr [rsp+140h+var_E4], ax
0x1800123de  mov     edx, [rsp+140h+var_E4]
0x1800123e2  mov     [rsp+140h+var_D8], eax
0x1800123e6  mov     r14, [rbp+40h+arg_10]
0x1800123ea  test    esi, esi
0x1800123ec  jnz     loc_18001332A
0x1800123f2  mov     r8, [r14+40h]
0x1800123f6  test    r8, r8
0x1800123f9  jz      loc_18001249A
0x1800123ff  mov     rdi, [rsp+140h+var_100]
0x180012404  mov     r9d, [r14+38h]
0x180012408  mov     eax, edi
0x18001240a  shr     eax, 10h
0x18001240d  mov     rcx, rdi
0x180012410  shr     rcx, 20h
0x180012414  movzx   edx, di
0x180012417  shl     edx, 10h
0x18001241a  or      edx, eax
0x18001241c  movzx   eax, cx
0x18001241f  shl     eax, 10h
0x180012422  shr     ecx, 10h
0x180012425  or      eax, ecx
0x180012427  lea     ecx, [r9-1]
0x18001242b  xor     edx, eax
0x18001242d  mov     eax, edx
0x18001242f  mov     r10d, edx
0x180012432  shr     eax, 5
0x180012435  xor     edx, edx
0x180012437  inc     eax
0x180012439  div     ecx
0x18001243b  xor     r11d, r11d
0x18001243e  lea     esi, [rdx+1]
0x180012441  cmp     r11d, r9d
0x180012444  jnb     short loc_18001249A
0x180012446  xor     edx, edx
0x180012448  mov     rax, r10
0x18001244b  div     r9
0x18001244e  lea     rax, [rdx+rdx*2]
0x180012452  movzx   ecx, byte ptr [r8+rax*8+10h]
0x180012458  test    cl, 1
0x18001245b  jnz     loc_1800125E5
0x180012461  test    cl, 2
0x180012464  jz      short loc_18001249A
0x180012466  mov     r10d, esi
0x180012469  add     r10, rdx
0x18001246c  inc     r11d
0x18001246f  jmp     short loc_180012441
0x180012471  lea     rcx, [rsp+140h+var_E8]; this
0x180012476  mov     esi, 8007000Eh
0x18001247b  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x180012480  xor     edx, edx
0x180012482  xor     ecx, ecx
0x180012484  mov     [rsp+140h+var_E4], edx
0x180012488  mov     [rbp+40h+var_B8], rcx
0x18001248c  mov     [rsp+140h+var_E0], rcx
0x180012491  mov     [rsp+140h+var_D8], edx
0x180012495  jmp     loc_1800123E6
0x18001249a  mov     rcx, cs:hHeap; hHeap
0x1800124a1  xor     edx, edx; dwFlags
0x1800124a3  mov     r8d, 40h ; '@'; dwBytes
0x1800124a9  call    cs:__imp_HeapAlloc
0x1800124af  test    rax, rax
0x1800124b2  jz      loc_18001377A
0x1800124b8  mov     rcx, rax; this
0x1800124bb  mov     [rsp+140h+var_110], 0
0x1800124c3  call    ??0ClockVector@@QEAA@XZ; ClockVector::ClockVector(void)
0x1800124c8  xor     esi, esi
0x1800124ca  mov     [rbp+40h+var_A0], rax
0x1800124ce  test    rax, rax
0x1800124d1  mov     rdi, rax
0x1800124d4  mov     eax, 8007000Eh
0x1800124d9  cmovz   esi, eax
0x1800124dc  test    rdi, rdi
0x1800124df  jz      short loc_180012504
0x1800124e1  mov     rdx, [rsp+140h+var_100]; struct IClockVector *
0x1800124e6  mov     rcx, rdi; this
0x1800124e9  call    ?InitializeWithExternalInstance@ClockVector@@QEAAJPEAUIClockVector@@@Z; ClockVector::InitializeWithExternalInstance(IClockVector *)
0x1800124ee  mov     esi, eax
0x1800124f0  test    eax, eax
0x1800124f2  jz      loc_180012986
0x1800124f8  mov     r13d, [rsp+140h+var_110]
0x1800124fd  jmp     short loc_18001250E
0x1800124ff  mov     esi, 8000FFFFh
0x180012504  mov     r13d, [rsp+140h+var_110]
0x180012509  test    rdi, rdi
0x18001250c  jz      short loc_18001251D
0x18001250e  mov     rax, [rdi]
0x180012511  mov     rcx, rdi
0x180012514  mov     rax, [rax+10h]
0x180012518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001251d  test    esi, esi
0x18001251f  jnz     loc_180013787
0x180012525  cmp     ebx, 0FFFFFFFFh
0x180012528  jz      loc_180012606
0x18001252e  mov     edi, [rsp+140h+var_E4]
0x180012532  mov     eax, edi
0x180012534  mov     r12, [rbp+40h+var_B8]
0x180012538  shr     eax, 11h
0x18001253b  mov     rcx, r12
0x18001253e  and     eax, 1
0x180012541  jnz     short loc_180012548
0x180012543  lea     rcx, [r12+4]
0x180012548  mov     r8d, [rsp+140h+var_10C]
0x18001254d  mov     r15, [rsp+140h+var_D0]
0x180012552  mov     r9, r15
0x180012555  bt      r8d, 11h
0x18001255a  jnb     loc_180012900
0x180012560  cmp     rcx, r9
0x180012563  jz      loc_18001288D
0x180012569  bt      edi, 10h
0x18001256d  jb      loc_180013571
0x180012573  movzx   eax, word ptr [rsp+140h+var_D8]
0x180012578  shr     rax, 2
0x18001257c  lea     r11, [rcx+rax*4]
0x180012580  mov     eax, [rsp+140h+var_110]
0x180012584  mov     [rsp+140h+var_110], eax
0x180012588  cmp     rcx, r11
0x18001258b  jnb     short loc_1800125A6
0x18001258d  mov     edx, [r9]
0x180012590  mov     r8d, [rcx]
0x180012593  cmp     r8d, edx
0x180012596  jnz     loc_180012836
0x18001259c  add     rcx, 4
0x1800125a0  add     r9, 4
0x1800125a4  jmp     short loc_180012588
0x1800125a6  mov     eax, [rsp+140h+var_D8]
0x1800125aa  movzx   eax, ax
0x1800125ad  test    al, 3
0x1800125af  jz      loc_18001288D
0x1800125b5  mov     rdx, r12
0x1800125b8  bt      edi, 11h
0x1800125bc  jb      short loc_1800125C3
0x1800125be  lea     rdx, [r12+4]
0x1800125c3  add     rax, rdx
0x1800125c6  cmp     rcx, rax
0x1800125c9  jnb     loc_18001288D
0x1800125cf  movzx   edx, byte ptr [r9]
0x1800125d3  cmp     [rcx], dl
0x1800125d5  jbe     loc_180012887
0x1800125db  mov     r13d, [rsp+140h+var_110]
0x1800125e0  jmp     loc_1800126D1
0x1800125e5  cmp     [r8+rax*8], rdi
0x1800125e9  jnz     loc_180012466
0x1800125ef  mov     eax, edx
0x1800125f1  lea     rcx, [rax+rax*2]
0x1800125f5  mov     eax, [r8+rcx*8+8]
0x1800125fa  mov     r13d, eax
0x1800125fd  mov     [rsp+140h+var_110], eax
0x180012601  jmp     loc_180012525
0x180012606  lea     rcx, [rsp+140h+var_E8]; this
0x18001260b  call    ?IsZeroId@SyncId@@QEBAHXZ; SyncId::IsZeroId(void)
0x180012610  test    eax, eax
0x180012612  jz      loc_1800133A9
0x180012618  mov     r12, [rbp+40h+var_B8]
0x18001261c  mov     r14, [rbp+40h+arg_0]
0x180012620  test    r12, r12
0x180012623  jz      short loc_18001262A
0x180012625  lock inc dword ptr [r12]
0x18001262a  xor     esi, esi
0x18001262c  cmp     [r14+18h], rsi
0x180012630  jz      loc_180013298
0x180012636  mov     eax, [r14+8]
0x18001263a  mov     edx, [r14+0Ch]
0x18001263e  inc     eax
0x180012640  cmp     eax, edx
0x180012642  ja      loc_180013535
0x180012648  mov     edx, [r14+8]
0x18001264c  mov     rax, [r14+18h]
0x180012650  lea     rcx, [rdx+rdx*2]
0x180012654  lea     rbx, [rax+rcx*8]
0x180012658  lea     eax, [rdx+1]
0x18001265b  mov     [r14+8], eax
0x18001265f  lea     rax, [rbp+40h+var_70]
0x180012663  cmp     rbx, rax
0x180012666  jz      short loc_180012685
0x180012668  mov     rcx, rbx; this
0x18001266b  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x180012670  mov     eax, [rsp+140h+var_E4]
0x180012674  mov     [rbx+4], eax
0x180012677  mov     [rbx+8], r12
0x18001267b  test    r12, r12
0x18001267e  jz      short loc_180012685
0x180012680  lock inc dword ptr [r12]
0x180012685  mov     [rbx+10h], r13d
0x180012689  test    esi, esi
0x18001268b  jnz     short loc_180012699
0x18001268d  xor     eax, eax
0x18001268f  test    r13d, r13d
0x180012692  setz    al
0x180012695  add     [r14+20h], eax
0x180012699  mov     edi, [rsp+140h+var_E4]
0x18001269d  bt      edi, 11h
0x1800126a1  jb      short loc_1800126BC
0x1800126a3  test    r12, r12
0x1800126a6  jz      short loc_1800126BC
0x1800126a8  mov     eax, 0FFFFFFFFh
0x1800126ad  lock xadd [r12], eax
0x1800126b3  cmp     eax, 1
0x1800126b6  jz      loc_1800134AB
0x1800126bc  test    esi, esi
0x1800126be  jnz     loc_1800133AE
0x1800126c4  jmp     loc_18001279D
0x1800126c9  cmp     cl, dl
  ... truncated ...
```
