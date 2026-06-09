# RangeSet::InitializeByMergingWithCoreFragment(RangeSet const &,SharedRefPtr<ICoreFragment> &,MergeContext &,SyncIdCache *)

- ea: `0x180013950`
- end: `0x180014ef4`
- name: `?InitializeByMergingWithCoreFragment@RangeSet@@QEAAJAEBV1@AEAV?$SharedRefPtr@UICoreFragment@@@@AEAVMergeContext@@PEAVSyncIdCache@@@Z`
- size: `5540`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `broker_com_uri`

## callers

- `0x18000d6e0`
- `0x18000efa0`

## callees

- `0x180005d80`
- `0x180005e8c`
- `0x1800068a4`
- `0x1800087fc`
- `0x18000e4e0`
- `0x18000e81c`
- `0x18000e868`
- `0x18000f810`
- `0x180010a80`
- `0x180011f60`
- `0x180011fc0`
- `0x180013930`
- `0x180013950`
- `0x180015128`
- `0x1800158d0`
- `0x1800164e4`
- `0x1800166e0`
- `0x180019ef0`
- `0x18001a038`
- `0x18001a094`
- `0x18001ae20`
- `0x18001b570`
- `0x180024994`
- `0x180024d38`
- `0x180025740`
- `0x180094010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013ce0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013e79`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013fc6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001458a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001477b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800147f0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014b45`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014d28`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013ce0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013e79`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013fc6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001458a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001477b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800147f0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014b45`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014d28`

## pseudocode

```c
__int64 __fastcall RangeSet::InitializeByMergingWithCoreFragment(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v5; // r13
  int *v9; // rbx
  __int64 v10; // rcx
  int v11; // esi
  int v12; // edx
  __int64 v13; // r12
  __int64 v14; // rcx
  int v15; // edi
  int v16; // ebx
  __int64 v17; // r9
  unsigned __int64 v18; // r11
  unsigned __int64 v19; // r8
  unsigned int v20; // r10d
  unsigned int v21; // esi
  unsigned __int64 v22; // rdx
  __int64 v23; // rax
  char v24; // cl
  unsigned int v25; // r14d
  int v26; // eax
  volatile signed __int32 *v27; // r12
  unsigned int v28; // edx
  __int64 v29; // rdx
  __int64 v30; // r14
  volatile signed __int32 *v31; // rcx
  int v32; // ecx
  unsigned __int64 v33; // r14
  __int64 v34; // rax
  bool v35; // cf
  SIZE_T v36; // rax
  _QWORD *v37; // rax
  ColumnEntry *v38; // r15
  unsigned int v40; // r12d
  __int64 v41; // rax
  __int64 v42; // rsi
  SIZE_T v43; // rax
  _QWORD *v44; // rax
  _QWORD *v45; // r14
  struct IClockVector *v46; // r14
  _QWORD *v47; // rcx
  unsigned __int64 v48; // rdx
  unsigned __int64 v49; // r8
  char v50; // cl
  __int64 v51; // rdx
  unsigned int v52; // r9d
  __int64 v53; // r9
  unsigned __int64 v54; // r8
  int v55; // eax
  unsigned int *v56; // r13
  unsigned int v57; // r12d
  __int64 v58; // r10
  unsigned __int64 v59; // rsi
  __int64 v60; // rax
  SIZE_T v61; // rax
  _QWORD *v62; // rax
  _QWORD *v63; // r12
  char *jj; // r14
  unsigned int *v65; // r12
  unsigned int v66; // r10d
  unsigned int v67; // ecx
  int v68; // r13d
  __int64 n; // rsi
  __int64 v70; // r11
  __int64 v71; // r10
  unsigned int v72; // r10d
  unsigned int v73; // r9d
  unsigned int ii; // r11d
  __int64 v75; // r8
  unsigned __int64 v76; // r13
  unsigned __int64 v77; // r8
  unsigned int nn; // r9d
  unsigned __int64 v79; // rdx
  unsigned __int64 v80; // r8
  char v81; // cl
  __int64 v82; // r10
  unsigned int v83; // r12d
  unsigned int v84; // r9d
  unsigned __int64 v85; // r8
  __int64 v86; // r11
  unsigned __int64 v87; // rax
  unsigned int i2; // r9d
  unsigned __int64 v89; // rdx
  __int64 v90; // rcx
  char v91; // al
  _QWORD *v92; // r13
  ClockVector **v93; // rsi
  unsigned int v94; // edx
  __int64 v95; // rcx
  ClockVector **v96; // r14
  unsigned int *v97; // r12
  __int64 v98; // r11
  unsigned int v99; // r13d
  unsigned __int64 v100; // r9
  unsigned __int64 v101; // r8
  __int64 v102; // r11
  unsigned __int64 v103; // rax
  unsigned int mm; // r10d
  unsigned __int64 v105; // rdx
  __int64 v106; // rcx
  char v107; // al
  __int64 v108; // rax
  __int64 v109; // rcx
  unsigned __int64 v110; // r9
  unsigned __int64 v111; // r8
  unsigned int kk; // r10d
  __int64 v113; // rax
  char v114; // cl
  unsigned int v115; // edx
  unsigned int v116; // ecx
  int v117; // esi
  __int64 i1; // rdx
  __int64 v119; // rcx
  __int64 v120; // r11
  __int64 v121; // rcx
  unsigned __int64 v122; // r14
  __int64 v123; // rax
  SIZE_T v124; // rax
  _QWORD *v125; // rax
  _QWORD *v126; // r13
  char *i3; // r12
  __int64 v128; // r11
  __int64 v129; // r10
  __int64 v130; // rcx
  unsigned int v131; // r11d
  unsigned int v132; // eax
  __int64 v133; // r11
  __int64 v134; // rcx
  __int64 v135; // r8
  unsigned __int64 v136; // r9
  unsigned __int64 v137; // r10
  unsigned int v138; // r11d
  unsigned int v139; // esi
  unsigned __int64 v140; // rdx
  char v141; // cl
  ClockVector *v142; // rax
  ClockVector *v143; // rax
  ClockVector *v144; // r14
  ClockVector *v145; // rax
  ClockVector *v146; // r15
  __int64 v147; // r13
  _DWORD *v148; // r12
  unsigned int v149; // r10d
  unsigned int v150; // r9d
  unsigned int m; // r11d
  __int64 v152; // r8
  PVOID *v153; // rcx
  unsigned int v154; // r9d
  __int64 v155; // r12
  unsigned int v156; // r10d
  __int64 v157; // r11
  unsigned __int64 v158; // rsi
  unsigned __int64 v159; // r15
  unsigned int i; // r13d
  unsigned __int64 v161; // rdx
  char v162; // cl
  __int64 v163; // r8
  unsigned int v164; // edx
  __int64 v165; // rcx
  char *v166; // r15
  struct IClockVector *v167; // r9
  __int64 v168; // r8
  _DWORD *v169; // r13
  unsigned __int64 v170; // r10
  unsigned int v171; // r15d
  __int64 v172; // rax
  __int64 v173; // rsi
  SIZE_T v174; // rax
  _QWORD *v175; // rax
  _QWORD *v176; // rax
  char *v177; // r12
  unsigned __int64 v178; // r11
  unsigned int k; // esi
  unsigned __int64 v180; // rdx
  char v181; // cl
  unsigned __int64 v182; // r10
  __int64 v183; // rsi
  unsigned __int64 v184; // rax
  unsigned int j; // r8d
  unsigned __int64 v186; // rdx
  __int64 v187; // rcx
  char v188; // al
  __int64 v189; // rcx
  __int64 v190; // rax
  unsigned int NextPrimeNumber; // eax
  unsigned __int64 v192; // r15
  __int64 v193; // rax
  SIZE_T v194; // rax
  _QWORD *v195; // rax
  _QWORD *v196; // rax
  char *v197; // r12
  unsigned int v198; // eax
  int v199; // [rsp+30h] [rbp-D0h]
  __int64 v200; // [rsp+30h] [rbp-D0h]
  __int64 v201; // [rsp+38h] [rbp-C8h]
  unsigned int v202; // [rsp+40h] [rbp-C0h]
  unsigned int v203; // [rsp+40h] [rbp-C0h]
  unsigned int *v204; // [rsp+48h] [rbp-B8h]
  int v205; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v206; // [rsp+58h] [rbp-A8h]
  int v207; // [rsp+60h] [rbp-A0h]
  ClockVector *v208; // [rsp+68h] [rbp-98h] BYREF
  int v209; // [rsp+70h] [rbp-90h] BYREF
  char v210[4]; // [rsp+78h] [rbp-88h] BYREF
  int v211; // [rsp+7Ch] [rbp-84h]
  void *v212; // [rsp+80h] [rbp-80h]
  char v213[4]; // [rsp+88h] [rbp-78h] BYREF
  int v214; // [rsp+8Ch] [rbp-74h]
  volatile signed __int32 *v215; // [rsp+90h] [rbp-70h]
  unsigned int v216; // [rsp+98h] [rbp-68h]
  struct IClockVector *v217[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v218; // [rsp+B0h] [rbp-50h]
  int v219; // [rsp+B8h] [rbp-48h] BYREF
  __int16 v220; // [rsp+BCh] [rbp-44h]
  __int64 v221; // [rsp+C0h] [rbp-40h]
  int v222; // [rsp+C8h] [rbp-38h]
  __int64 v223[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v224; // [rsp+E0h] [rbp-20h]
  struct IClockVector *v225; // [rsp+F0h] [rbp-10h]
  char v226; // [rsp+100h] [rbp+0h] BYREF
  char v227; // [rsp+108h] [rbp+8h] BYREF
  char v228; // [rsp+110h] [rbp+10h] BYREF
  int v230; // [rsp+188h] [rbp+88h]
  _QWORD *v231; // [rsp+188h] [rbp+88h]
  unsigned int v232; // [rsp+188h] [rbp+88h]
  unsigned int v233; // [rsp+188h] [rbp+88h]
  unsigned int v234; // [rsp+188h] [rbp+88h]
  struct IClockVector *v235; // [rsp+188h] [rbp+88h]
  _QWORD *v236; // [rsp+188h] [rbp+88h]
  unsigned int v237; // [rsp+190h] [rbp+90h]
  _QWORD *v238; // [rsp+190h] [rbp+90h]
  unsigned int v240; // [rsp+1A0h] [rbp+A0h]
  int v241; // [rsp+1A0h] [rbp+A0h]

  v5 = a4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      WPP_ff88f7f000e13ecf98ed337d60498caa_Traceguids,
      "RangeSet::InitializeByMergingWithCoreFragment");
  }
  v9 = (int *)(a2 + 40);
  if ( a1 + 40 != a2 + 40 )
  {
    *(_DWORD *)(a1 + 40) = *v9;
    *(_WORD *)(a1 + 44) = *(_WORD *)(a2 + 44);
  }
  v10 = *a3;
  v205 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 56LL))(v10, &v205);
  if ( !v11 )
  {
    v12 = *(_DWORD *)(a2 + 8) + v205 - 1;
    *(_DWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 32) = 0;
    if ( !v12 )
      v12 = 16;
    *(_DWORD *)(a1 + 16) = v12;
  }
  v13 = *(_QWORD *)(v5 + 48);
  v223[1] = a5;
  v209 = 0;
  v211 = 0;
  v212 = 0;
  v214 = 0;
  v215 = 0;
  *(_OWORD *)v217 = 0;
  v218 = 0;
  v219 = 0;
  v220 = 0;
  v223[0] = 0;
  v224 = 0;
  if ( &v219 != v9 )
  {
    v219 = *v9;
    v220 = *(_WORD *)(a2 + 44);
  }
  v221 = a2;
  v222 = 0;
  if ( v223 != a3 )
  {
    v14 = *a3;
    v223[0] = v14;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
  }
  v224 = v13;
  if ( !v11 )
  {
    v11 = DoubleIterator<RangeSet::IteratorWithCoreFragment,unsigned long,SharedRefPtr<IClockVector>>::Begin(&v209);
    if ( !v11 )
    {
      v15 = HIDWORD(v225);
      v16 = -1;
      while ( 1 )
      {
        if ( HIDWORD(v218) && (_DWORD)v218 )
          goto LABEL_66;
        v17 = *(_QWORD *)(v5 + 144);
        v237 = v216;
        v225 = v217[0];
        if ( v17 )
        {
          v18 = *(unsigned int *)(v5 + 136);
          v19 = (HIWORD(v216) | ((unsigned __int16)v216 << 16))
              ^ (HIWORD(HIDWORD(v217[0])) | (WORD2(v217[0]) << 16))
              ^ (HIWORD(LODWORD(v217[0])) | (LOWORD(v217[0]) << 16));
          v20 = 0;
          v21 = (((unsigned int)v19 >> 5) + 1) % ((int)v18 - 1) + 1;
          while ( v20 < (unsigned int)v18 )
          {
            v22 = v19 % v18;
            v23 = 32 * (v19 % v18);
            v24 = *(_BYTE *)(v23 + v17 + 24);
            if ( (v24 & 1) != 0 )
            {
              if ( *(_DWORD *)(v23 + v17) == v216 && *(struct IClockVector **)(v23 + v17 + 8) == v217[0] )
              {
                v25 = *(_DWORD *)(32LL * (unsigned int)v22 + v17 + 16);
                v240 = v25;
                goto LABEL_25;
              }
            }
            else if ( (v24 & 2) == 0 )
            {
              break;
            }
            v19 = v22 + v21;
            ++v20;
          }
        }
        v135 = *(_QWORD *)(v5 + 120);
        if ( v135 )
        {
          v136 = *(unsigned int *)(v5 + 112);
          v137 = (HIWORD(LODWORD(v217[0])) | (LOWORD(v217[0]) << 16))
               ^ (HIWORD(HIDWORD(v217[0])) | (WORD2(v217[0]) << 16));
          v138 = 0;
          v139 = (((unsigned int)v137 >> 5) + 1) % ((int)v136 - 1) + 1;
          while ( v138 < (unsigned int)v136 )
          {
            v140 = v137 % v136;
            v141 = *(_BYTE *)(v135 + 24 * (v137 % v136) + 16);
            if ( (v141 & 1) != 0 )
            {
              if ( *(struct IClockVector **)(v135 + 24 * (v137 % v136)) == v217[0] )
              {
                v40 = *(_DWORD *)(v135 + 24LL * (unsigned int)v140 + 8);
                goto LABEL_234;
              }
            }
            else if ( (v141 & 2) == 0 )
            {
              break;
            }
            v137 = v140 + v139;
            ++v138;
          }
        }
        v142 = (ClockVector *)HeapAlloc(hHeap, 0, 0x40u);
        if ( !v142 )
        {
          v11 = -2147024882;
          goto LABEL_79;
        }
        v241 = 0;
        v143 = ClockVector::ClockVector(v142);
        v144 = v143;
        if ( !v143 )
        {
          v11 = -2147024882;
          goto LABEL_75;
        }
        v11 = ClockVector::InitializeWithExternalInstance(v143, v217[0]);
        if ( v11 )
        {
          v40 = 0;
LABEL_77:
          (*(void (__fastcall **)(ClockVector *))(*(_QWORD *)v144 + 16LL))(v144);
          goto LABEL_78;
        }
        if ( *(_DWORD *)(v5 + 40) )
        {
          v153 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              20,
              WPP_362d7c742a68350205e0bfe72ed984ca_Traceguids,
              "ClockVector::RemapReplicaKeys");
            v153 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( *((_DWORD *)v144 + 7) )
          {
            v154 = 0;
            while ( 1 )
            {
              v155 = *((_QWORD *)v144 + 5);
              v156 = *(_DWORD *)(v155 + 16LL * v154);
              if ( *(_DWORD *)(v5 + 40) )
                break;
LABEL_261:
              v163 = 2LL * v154;
              v11 = 0;
              ++v154;
              *(_DWORD *)(v155 + 8 * v163) = v156;
              if ( v154 >= *((_DWORD *)v144 + 7) )
              {
                Algorithms::QuickSort<SyncVersion,ClockVector::CompareFunctor,ClockVector::SwapFunctor>(
                  *((char **)v144 + 5),
                  *((_DWORD *)v144 + 7),
                  v163,
                  v144);
                v153 = (PVOID *)WPP_GLOBAL_Control;
                goto LABEL_263;
              }
            }
            v157 = *(_QWORD *)(v5 + 32);
            if ( v157 )
            {
              v158 = *(unsigned int *)(v5 + 24);
              v159 = HIWORD(v156) | ((unsigned __int16)v156 << 16);
              v234 = (((unsigned int)v159 >> 5) + 1) % ((int)v158 - 1) + 1;
              for ( i = 0; i < (unsigned int)v158; ++i )
              {
                v161 = v159 % v158;
                v162 = *(_BYTE *)(v157 + 12 * (v159 % v158) + 8);
                if ( (v162 & 1) != 0 )
                {
                  if ( *(_DWORD *)(v157 + 12 * (v159 % v158)) == v156 )
                  {
                    v5 = a4;
                    v156 = *(_DWORD *)(v157 + 12LL * (unsigned int)v161 + 4);
                    goto LABEL_261;
                  }
                }
                else if ( (v162 & 2) == 0 )
                {
                  break;
                }
                v159 = v161 + v234;
              }
              v5 = a4;
            }
            ClockVector::Recycle(v144);
            v153 = (PVOID *)WPP_GLOBAL_Control;
            v11 = -2147024809;
          }
          else
          {
            v11 = 0;
          }
LABEL_263:
          if ( v153 != &WPP_GLOBAL_Control && (*((_BYTE *)v153 + 28) & 0x40) != 0 && *((_BYTE *)v153 + 25) >= 5u )
            WPP_SF_sD(
              (unsigned int)v153[2],
              21,
              (unsigned int)WPP_362d7c742a68350205e0bfe72ed984ca_Traceguids,
              (unsigned int)"ClockVector::RemapReplicaKeys",
              v11);
          if ( v11 )
            goto LABEL_75;
        }
        v11 = 0;
        if ( !*(_QWORD *)(v5 + 104) )
          break;
        v164 = *(_DWORD *)(v5 + 92);
        if ( *(_DWORD *)(v5 + 88) + 1 <= v164 )
          goto LABEL_268;
        v11 = Vector<SharedRefPtr<ClockVector>,1>::IncreaseCapacity(v5 + 88, 2 * v164);
        if ( v11 >= 0 )
          goto LABEL_268;
LABEL_273:
        if ( v11 )
          goto LABEL_75;
        v167 = v217[0];
        v168 = *(_QWORD *)(a4 + 120);
        v169 = (_DWORD *)(a4 + 112);
        v170 = *(unsigned int *)(a4 + 112);
        v241 = *(_DWORD *)(a4 + 88) - 1;
        v235 = v217[0];
        v171 = (HIWORD(LODWORD(v217[0])) | (LOWORD(v217[0]) << 16))
             ^ (HIWORD(HIDWORD(v217[0])) | (WORD2(v217[0]) << 16));
        if ( !v168 )
        {
          v172 = 24 * v170;
          v173 = (unsigned int)v170;
          if ( !is_mul_ok(v170, 0x18u) )
            v172 = -1;
          v35 = __CFADD__(v172, 8);
          v174 = v172 + 8;
          if ( v35 )
            v174 = -1;
          v175 = HeapAlloc(hHeap, 0, v174);
          if ( !v175 )
          {
            *(_QWORD *)(a4 + 120) = 0;
            goto LABEL_74;
          }
          *v175 = v173;
          v176 = v175 + 1;
          v206 = v176;
          v177 = (char *)v176;
          if ( v173 )
          {
            do
            {
              TableBucket<IUnknown *,KnowledgeCookie *,DefaultHashTableContext>::TableBucket<IUnknown *,KnowledgeCookie *,DefaultHashTableContext>(v177);
              v177 += 24;
              --v173;
            }
            while ( v173 );
            v176 = v206;
          }
          *(_QWORD *)(a4 + 120) = v176;
          if ( !v176 )
            goto LABEL_74;
LABEL_304:
          v167 = v235;
LABEL_291:
          v182 = (unsigned int)*v169;
          v183 = *(_QWORD *)(a4 + 120);
          v184 = v171;
          for ( j = 0; j < (unsigned int)v182; ++j )
          {
            v186 = v184 % v182;
            v187 = v183 + 24 * (v184 % v182);
            v188 = *(_BYTE *)(v187 + 16);
            if ( (v188 & 1) == 0 )
            {
              v40 = v241;
              v11 = 0;
              v189 = 3LL * (unsigned int)v186;
              v190 = *(_QWORD *)(a4 + 120);
              *(_BYTE *)(v190 + 8 * v189 + 16) |= 1u;
              *(_QWORD *)(v190 + 8 * v189) = v167;
              *(_DWORD *)(v190 + 8 * v189 + 8) = v241;
              ++*(_DWORD *)(a4 + 128);
              goto LABEL_76;
            }
            *(_BYTE *)(v187 + 16) = v188 | 2;
            v184 = v186 + ((v171 >> 5) + 1) % ((int)v182 - 1) + 1;
          }
          v11 = -2147418113;
          goto LABEL_75;
        }
        v178 = v171;
        for ( k = 0; k < (unsigned int)v170; ++k )
        {
          v180 = v178 % v170;
          v181 = *(_BYTE *)(v168 + 24 * (v178 % v170) + 16);
          if ( (v181 & 1) != 0 )
          {
            if ( *(struct IClockVector **)(v168 + 24 * v180) == v217[0] )
            {
              v11 = -2147024809;
              goto LABEL_75;
            }
          }
          else if ( (v181 & 2) == 0 )
          {
            break;
          }
          v178 = ((v171 >> 5) + 1) % ((int)v170 - 1) + 1 + v180;
        }
        if ( *(_DWORD *)(a4 + 128) + 1 <= 72 * *v169 / 0x64u )
          goto LABEL_291;
        NextPrimeNumber = GetNextPrimeNumber(2 * *v169);
        v11 = HashTable<void *,unsigned long,DefaultHashTableContext>::Resize(v169, NextPrimeNumber);
        if ( v11 >= 0 )
          goto LABEL_304;
LABEL_75:
        v40 = v241;
LABEL_76:
        if ( v144 )
          goto LABEL_77;
LABEL_78:
        if ( v11 )
          goto LABEL_79;
        v5 = a4;
LABEL_234:
        v145 = (ClockVector *)HeapAlloc(hHeap, 0, 0x40u);
        if ( !v145 )
        {
          v208 = 0;
          v11 = -2147024882;
          goto LABEL_79;
        }
        v25 = 0;
        v240 = 0;
        v208 = ClockVector::ClockVector(v145);
        v146 = v208;
        if ( v208 )
        {
          v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, ClockVector *))(v5 + 184))(
                  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v5 + 56) + 32LL) + 8LL * v237),
                  *(_QWORD *)(*(_QWORD *)(v5 + 104) + 8LL * v40),
                  v208);
          if ( v11 )
            goto LABEL_95;
          v147 = *(_QWORD *)(v5 + 64);
          v206 = (_QWORD *)v147;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              10,
              WPP_e65626ae806d36e8966776faf765a664_Traceguids,
              "ClockVectorManager::FindByKeyOrAdd");
          }
          v53 = *(_QWORD *)(v147 + 48);
          v148 = (_DWORD *)(v147 + 16);
          v204 = (unsigned int *)(v147 + 16);
          v207 = *(_DWORD *)(v147 + 16);
          v200 = v53;
          if ( v53 )
          {
            v54 = *((unsigned int *)v146 + 14);
            v131 = *(_DWORD *)(v147 + 40);
            v233 = v131;
            if ( (_DWORD)v54 == -1 )
            {
              v149 = *((_DWORD *)v146 + 7);
              v150 = v149 ^ (*((_DWORD *)v146 + 9) >> 1) & 1;
              if ( v149 )
              {
                for ( m = 0; m < v149; ++m )
                {
                  v152 = m;
                  v150 = *(_DWORD *)(16 * v152 + *((_QWORD *)v146 + 5))
                       ^ *(_QWORD *)(16 * v152 + *((_QWORD *)v146 + 5) + 8)
                       ^ (32 * v150)
                       ^ (v150 >> 27)
                       ^ HIDWORD(*(_QWORD *)(16 * v152 + *((_QWORD *)v146 + 5) + 8));
                }
                v131 = *(_DWORD *)(v147 + 40);
              }
              v54 = 0x7FFFFFFF;
              if ( v150 != -1 )
                v54 = v150;
              v53 = v200;
              *((_DWORD *)v146 + 14) = v54;
            }
            v202 = (((unsigned int)v54 >> 5) + 1) % (v131 - 1) + 1;
            while ( v25 < v131 )
            {
              v48 = v54 % v131;
              v49 = v48;
              v50 = *(_BYTE *)(v53 + 24 * v48 + 16);
              if ( (v50 & 1) != 0 )
              {
                v51 = *(_QWORD *)(v53 + 24 * v48);
                if ( (ClockVector *)v51 == v146 )
                  goto LABEL_146;
                v52 = *(_DWORD *)(v51 + 28);
                if ( v52 == *((_DWORD *)v146 + 7) )
                {
                  v66 = *((_DWORD *)v146 + 9);
                  v67 = *(_DWORD *)(v51 + 36);
                  v68 = (v67 >> 1) & 1;
                  if ( v68 == ((v66 >> 1) & 1)
                    && *(_DWORD *)(v51 + 32) == *((_DWORD *)v146 + 8)
                    && (((unsigned __int8)v66 ^ (unsigned __int8)v67) & 4) == 0 )
                  {
                    for ( n = 0; (unsigned int)n < v52; n = (unsigned int)(n + 1) )
                    {
                      v70 = *((_QWORD *)v146 + 5);
                      v71 = *(_QWORD *)(v51 + 40);
                      if ( *(_DWORD *)(v71 + 16LL * (unsigned int)n) == *(_DWORD *)(v70 + 16LL * (unsigned int)n)
                        && *(_QWORD *)(v71 + 16LL * (unsigned int)n + 8) == *(_QWORD *)(v70 + 16LL * (unsigned int)n + 8) )
                      {
                        if ( !v68 )
                          continue;
                        v128 = *((_QWORD *)v146 + 6);
                        v129 = *(_QWORD *)(v51 + 48);
                        v130 = 12 * n;
                        if ( *(_DWORD *)(v129 + 12 * n) == *(_DWORD *)(v128 + 12 * n)
                          && *(_DWORD *)(v129 + v130 + 4) == *(_DWORD *)(v128 + v130 + 4)
                          && *(_BYTE *)(v129 + v130 + 8) == *(_BYTE *)(v128 + v130 + 8) )
                        {
                          continue;
                        }
                      }
                      v131 = v233;
                      goto LABEL_104;
                    }
LABEL_146:
                    v92 = v206;
                    v11 = 0;
                    v25 = *(_DWORD *)(v206[6] + 24LL * (unsigned int)v49 + 8);
                    v240 = v25;
                    goto LABEL_161;
                  }
                }
LABEL_104:
                v53 = v200;
              }
              else if ( (v50 & 2) == 0 )
              {
                break;
              }
              v54 = v202 + v49;
              ++v25;
            }
          }
          v55 = *v148;
          v56 = v148 + 6;
          v57 = *((_DWORD *)v146 + 14);
          v199 = v55;
          v232 = v57;
          if ( v57 == -1 )
          {
            v72 = *((_DWORD *)v146 + 7);
            v73 = v72 ^ (*((_DWORD *)v146 + 9) >> 1) & 1;
            if ( v72 )
            {
              for ( ii = 0; ii < v72; ++ii )
              {
                v75 = ii;
                v73 = *(_DWORD *)(16 * v75 + *((_QWORD *)v146 + 5))
                    ^ *(_QWORD *)(16 * v75 + *((_QWORD *)v146 + 5) + 8)
                    ^ (32 * v73)
                    ^ (v73 >> 27)
                    ^ HIDWORD(*(_QWORD *)(16 * v75 + *((_QWORD *)v146 + 5) + 8));
              }
            }
            v57 = 0x7FFFFFFF;
            if ( v73 != -1 )
              v57 = v73;
            v232 = v57;
            *((_DWORD *)v146 + 14) = v57;
          }
          v58 = *((_QWORD *)v56 + 1);
          v201 = v58;
          if ( !v58 )
          {
            v59 = *v56;
            v60 = 24 * v59;
            if ( !is_mul_ok(v59, 0x18u) )
              v60 = -1;
            v35 = __CFADD__(v60, 8);
            v61 = v60 + 8;
            if ( v35 )
              v61 = -1;
            v62 = HeapAlloc(hHeap, 0, v61);
            if ( v62 )
            {
              *v62 = v59;
              v63 = v62 + 1;
              for ( jj = (char *)(v62 + 1); v59; --v59 )
              {
                TableBucket<SharedRefPtr<RangeSet>,unsigned long,SimpleHashTableContext>::TableBucket<SharedRefPtr<RangeSet>,unsigned long,SimpleHashTableContext>(jj);
                jj += 24;
              }
              *((_QWORD *)v56 + 1) = v63;
              if ( v63 )
              {
                v65 = v204;
                goto LABEL_142;
              }
            }
            else
            {
              *((_QWORD *)v56 + 1) = 0;
            }
            v11 = -2147024882;
LABEL_218:
            v25 = 0;
LABEL_159:
            if ( !v11 )
            {
              v92 = v206;
LABEL_161:
              if ( *((_DWORD *)v92 + 4) != v207 )
                *((_DWORD *)v92 + 2) = -1;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_sD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                11,
                (unsigned int)WPP_e65626ae806d36e8966776faf765a664_Traceguids,
                (unsigned int)"ClockVectorManager::FindByKeyOrAdd",
                v11);
            }
            if ( !v11 )
            {
              v46 = v225;
              v97 = (unsigned int *)(a4 + 136);
              v98 = *(_QWORD *)(a4 + 144);
              v99 = (HIWORD(v237) | ((unsigned __int16)v237 << 16))
                  ^ (HIWORD(HIDWORD(v225)) | (WORD2(v225) << 16))
                  ^ (((unsigned int)v225 >> 16) | ((unsigned __int16)v225 << 16));
              if ( v98 )
              {
                v110 = *v97;
                v111 = v99;
                for ( kk = 0; kk < (unsigned int)v110; ++kk )
                {
                  v113 = 32 * (v111 % v110);
                  v114 = *(_BYTE *)(v113 + v98 + 24);
                  if ( (v114 & 1) != 0 )
                  {
                    if ( *(_DWORD *)(v113 + v98) == v237 && *(struct IClockVector **)(v113 + v98 + 8) == v225 )
                    {
                      v11 = -2147024809;
                      goto LABEL_94;
                    }
                  }
                  else if ( (v114 & 2) == 0 )
                  {
                    break;
                  }
                  v111 = ((v99 >> 5) + 1) % ((int)v110 - 1) + 1 + v111 % v110;
                }
              }
              v100 = *v97;
              if ( v98 )
              {
                if ( *(_DWORD *)(a4 + 152) + 1 <= 72 * (int)v100 / 0x64u )
                  goto LABEL_169;
                v198 = GetNextPrimeNumber(2 * (int)v100);
                v11 = HashTable<Tuple<unsigned long,void *>,unsigned long,DefaultHashTableContext>::Resize(v97, v198);
              }
              else
              {
                v41 = 32LL * *v97;
                v42 = *v97;
                if ( !is_mul_ok(v100, 0x20u) )
                  v41 = -1;
                v35 = __CFADD__(v41, 8);
                v43 = v41 + 8;
                if ( v35 )
                  v43 = -1;
                v44 = HeapAlloc(hHeap, 0, v43);
                v231 = v44;
                if ( v44 )
                {
                  *v44 = v42;
                  v45 = v44 + 1;
                  if ( v42 )
                  {
                    do
                    {
                      TableBucket<Tuple<unsigned long,void *>,unsigned long,DefaultHashTableContext>::TableBucket<Tuple<unsigned long,void *>,unsigned long,DefaultHashTableContext>(v45);
                      v45 += 4;
                      --v42;
                    }
                    while ( v42 );
                    v44 = v231;
                  }
                  v46 = v225;
                  v47 = v44 + 1;
                }
                else
                {
                  v47 = 0;
                }
                *(_QWORD *)(a4 + 144) = v47;
                v11 = -2147024882;
                if ( v47 )
                  v11 = 0;
              }
              if ( v11 >= 0 )
              {
LABEL_169:
                v101 = *v97;
                v102 = *(_QWORD *)(a4 + 144);
                v103 = v99;
                for ( mm = 0; mm < (unsigned int)v101; ++mm )
                {
                  v105 = v103 % v101;
                  v106 = 32 * (v103 % v101);
                  v107 = *(_BYTE *)(v106 + v102 + 24);
                  if ( (v107 & 1) == 0 )
                  {
                    v108 = *(_QWORD *)(a4 + 144);
                    v11 = 0;
                    v109 = 32LL * (unsigned int)v105;
                    *(_BYTE *)(v109 + v108 + 24) |= 1u;
                    *(_DWORD *)(v109 + v108) = v237;
                    *(_DWORD *)(v109 + v108 + 16) = v240;
                    *(_DWORD *)(v109 + v108 + 4) = v15;
                    *(_QWORD *)(v109 + v108 + 8) = v46;
                    ++*(_DWORD *)(a4 + 152);
                    goto LABEL_94;
                  }
                  *(_BYTE *)(v106 + v102 + 24) = v107 | 2;
                  v103 = v105 + ((v99 >> 5) + 1) % ((int)v101 - 1) + 1;
                }
                v11 = -2147418113;
              }
LABEL_94:
              v25 = v240;
            }
LABEL_95:
            (*(void (__fastcall **)(ClockVector *))(*(_QWORD *)v146 + 16LL))(v146);
            goto LABEL_96;
          }
          v76 = *v56;
          v77 = v57;
          v203 = ((v57 >> 5) + 1) % ((int)v76 - 1) + 1;
          for ( nn = 0; nn < (unsigned int)v76; ++nn )
          {
            v79 = v77 % v76;
            v80 = v79;
            v81 = *(_BYTE *)(v58 + 24 * v79 + 16);
            if ( (v81 & 1) != 0 )
            {
              v82 = *(_QWORD *)(v58 + 24 * v79);
              if ( (ClockVector *)v82 == v146 )
                goto LABEL_193;
              v83 = *(_DWORD *)(v82 + 28);
              if ( v83 == *((_DWORD *)v146 + 7) )
              {
                v115 = *((_DWORD *)v146 + 9);
                v116 = *(_DWORD *)(v82 + 36);
                v117 = (v116 >> 1) & 1;
                if ( v117 == ((v115 >> 1) & 1)
                  && *(_DWORD *)(v82 + 32) == *((_DWORD *)v146 + 8)
                  && (((unsigned __int8)v115 ^ (unsigned __int8)v116) & 4) == 0 )
                {
                  for ( i1 = 0; (unsigned int)i1 < v83; i1 = (unsigned int)(i1 + 1) )
                  {
                    v119 = 16LL * (unsigned int)i1;
                    v120 = v119 + *(_QWORD *)(v82 + 40);
                    v121 = *((_QWORD *)v146 + 5) + v119;
                    if ( *(_DWORD *)v120 != *(_DWORD *)v121 )
                      goto LABEL_138;
                    if ( *(_QWORD *)(v120 + 8) != *(_QWORD *)(v121 + 8) )
                      goto LABEL_138;
                    if ( v117 )
                    {
                      v133 = 12 * i1 + *(_QWORD *)(v82 + 48);
                      v134 = *((_QWORD *)v146 + 6) + 12 * i1;
                      if ( *(_DWORD *)v133 != *(_DWORD *)v134
                        || *(_DWORD *)(v133 + 4) != *(_DWORD *)(v134 + 4)
                        || *(_BYTE *)(v133 + 8) != *(_BYTE *)(v134 + 8) )
                      {
                        goto LABEL_138;
                      }
                    }
                  }
LABEL_193:
                  v11 = -2147024809;
                  goto LABEL_218;
                }
              }
LABEL_138:
              v58 = v201;
            }
            else if ( (v81 & 2) == 0 )
            {
              break;
            }
            v77 = v203 + v80;
          }
          v65 = v204;
          v84 = v204[6];
          v56 = v204 + 6;
          if ( v204[10] + 1 > 72 * v84 / 0x64 )
          {
            v132 = GetNextPrimeNumber(2 * v84);
            v11 = HashTable<SharedRefPtr<ClockVector>,unsigned long,SimpleHashTableContext>::Resize(v56, v132);
            if ( v11 < 0 )
              goto LABEL_218;
          }
LABEL_142:
          v85 = *v56;
          v86 = *((_QWORD *)v56 + 1);
          v87 = v232;
          for ( i2 = 0; ; ++i2 )
          {
            if ( i2 >= (unsigned int)v85 )
            {
              v11 = -2147418113;
              goto LABEL_218;
            }
            v89 = v87 % v85;
            v90 = v86 + 24 * (v87 % v85);
            v91 = *(_BYTE *)(v90 + 16);
            if ( (v91 & 1) == 0 )
              break;
            *(_BYTE *)(v90 + 16) = v91 | 2;
            v87 = v89 + ((v232 >> 5) + 1) % ((int)v85 - 1) + 1;
          }
          v93 = (ClockVector **)(*((_QWORD *)v56 + 1) + 24LL * (unsigned int)v89);
          (*(void (__fastcall **)(ClockVector *))(*(_QWORD *)v146 + 8LL))(v146);
          if ( v93 != (ClockVector **)&v227 )
          {
            if ( *v93 )
              (*(void (__fastcall **)(ClockVector *))(*(_QWORD *)*v93 + 16LL))(*v93);
            *v93 = v146;
            (*(void (__fastcall **)(ClockVector *))(*(_QWORD *)v146 + 8LL))(v146);
          }
          (*(void (__fastcall **)(ClockVector *))(*(_QWORD *)v146 + 16LL))(v146);
          *((_BYTE *)v93 + 16) |= 1u;
          *((_DWORD *)v93 + 2) = v199;
          v11 = 0;
          ++v56[4];
          if ( *((_QWORD *)v65 + 2) )
          {
            v94 = v65[1];
            if ( *v65 + 1 > v94 )
            {
              v11 = Vector<SharedRefPtr<ClockVector>,1>::IncreaseCapacity(v65, 2 * v94);
              if ( v11 < 0 )
              {
LABEL_157:
                if ( !v11 )
                {
                  v25 = *v65 - 1;
                  v240 = v25;
                  goto LABEL_159;
                }
                goto LABEL_217;
              }
            }
LABEL_153:
            v95 = *v65;
            v96 = (ClockVector **)(*((_QWORD *)v65 + 2) + 8 * v95);
            *v65 = v95 + 1;
            if ( v96 != &v208 )
            {
              if ( *v96 )
                (*(void (__fastcall **)(ClockVector *))(*(_QWORD *)*v96 + 16LL))(*v96);
              *v96 = v146;
              (*(void (__fastcall **)(ClockVector *))(*(_QWORD *)v146 + 8LL))(v146);
            }
            goto LABEL_157;
          }
          v122 = v65[2];
          v123 = 8 * v122;
          if ( !is_mul_ok(v122, 8u) )
            v123 = -1;
          v35 = __CFADD__(v123, 8);
          v124 = v123 + 8;
          if ( v35 )
            v124 = -1;
          v125 = HeapAlloc(hHeap, 0, v124);
          v126 = v125;
          if ( v125 )
          {
            *v125 = v122;
            for ( i3 = (char *)(v125 + 1); v122; --v122 )
            {
              SharedRefPtr<Legacy::Override>::`default constructor closure'(i3);
              i3 += 8;
            }
            v65 = v204;
            *((_QWORD *)v204 + 2) = v126 + 1;
            if ( v126 != (_QWORD *)-8LL )
            {
              v204[1] = v204[2];
              goto LABEL_153;
            }
          }
          else
          {
            *((_QWORD *)v65 + 2) = 0;
          }
          v11 = -2147024882;
LABEL_217:
          HashTable<SharedRefPtr<ClockVector>,unsigned long,SimpleHashTableContext>::RemoveItem(v65 + 6, &v208);
          goto LABEL_218;
        }
        v11 = -2147024882;
LABEL_96:
        if ( v11 )
          goto LABEL_79;
LABEL_25:
        if ( v16 != -1 && v16 == v25 )
        {
          v16 = v25;
          goto LABEL_52;
        }
        v16 = v25;
        if ( v209 > 0 )
        {
          v26 = v214;
          v27 = v215;
        }
        else
        {
          v26 = v211;
          v27 = (volatile signed __int32 *)v212;
        }
        v230 = v26;
        if ( v27 )
          _InterlockedIncrement(v27);
        v11 = 0;
        if ( !*(_QWORD *)(a1 + 24) )
        {
          v33 = *(unsigned int *)(a1 + 16);
          v34 = 24 * v33;
          if ( !is_mul_ok(v33, 0x18u) )
            v34 = -1;
          v35 = __CFADD__(v34, 8);
          v36 = v34 + 8;
          if ( v35 )
            v36 = -1;
          v37 = HeapAlloc(hHeap, 0, v36);
          v238 = v37;
          if ( !v37 )
          {
            *(_QWORD *)(a1 + 24) = 0;
LABEL_81:
            v32 = v230;
            v11 = -2147024882;
            goto LABEL_42;
          }
          *v37 = v33;
          v38 = (ColumnEntry *)(v37 + 1);
          if ( v33 )
          {
            do
            {
              ColumnEntry::ColumnEntry(v38);
              v38 = (ColumnEntry *)((char *)v38 + 24);
              --v33;
            }
            while ( v33 );
            v37 = v238;
          }
          else
          {
            v16 = v240;
          }
          *(_QWORD *)(a1 + 24) = v37 + 1;
          if ( v37 == (_QWORD *)-8LL )
            goto LABEL_81;
          *(_DWORD *)(a1 + 12) = *(_DWORD *)(a1 + 16);
LABEL_32:
          v29 = *(unsigned int *)(a1 + 8);
          v30 = *(_QWORD *)(a1 + 24) + 24 * v29;
          *(_DWORD *)(a1 + 8) = v29 + 1;
          if ( (char *)v30 == &v228 )
          {
            v32 = v230;
          }
          else
          {
            if ( (*(_DWORD *)(v30 + 4) & 0x20000) == 0 )
            {
              v31 = *(volatile signed __int32 **)(v30 + 8);
              if ( v31 )
              {
                if ( _InterlockedExchangeAdd(v31, 0xFFFFFFFF) == 1 )
                  SeFree(*(void **)(v30 + 8));
              }
            }
            v32 = v230;
            *(_DWORD *)(v30 + 4) = v230;
            *(_QWORD *)(v30 + 8) = v27;
            if ( v27 )
              _InterlockedIncrement(v27);
          }
          *(_DWORD *)(v30 + 16) = v16;
          goto LABEL_40;
        }
        v28 = *(_DWORD *)(a1 + 12);
        if ( *(_DWORD *)(a1 + 8) + 1 <= v28 )
          goto LABEL_32;
        v11 = Vector<Range,1>::IncreaseCapacity(a1 + 8, 2 * v28);
        if ( v11 >= 0 )
          goto LABEL_32;
        v32 = v230;
LABEL_40:
        if ( !v11 )
          *(_DWORD *)(a1 + 32) += v16 == 0;
LABEL_42:
        if ( (v32 & 0x20000) == 0 && v27 && _InterlockedExchangeAdd(v27, 0xFFFFFFFF) == 1 )
          SeFree((void *)v27);
        if ( v11 )
          goto LABEL_79;
LABEL_52:
        v11 = DoubleIterator<RangeSet::IteratorWithCoreFragment,unsigned long,SharedRefPtr<IClockVector>>::MoveNext(&v209);
        if ( v11 )
          goto LABEL_79;
        v5 = a4;
      }
      v192 = *(unsigned int *)(v5 + 96);
      v193 = 8 * v192;
      if ( !is_mul_ok(v192, 8u) )
        v193 = -1;
      v35 = __CFADD__(v193, 8);
      v194 = v193 + 8;
      if ( v35 )
        v194 = -1;
      v195 = HeapAlloc(hHeap, 0, v194);
      if ( !v195 )
      {
        *(_QWORD *)(v5 + 104) = 0;
LABEL_74:
        v11 = -2147024882;
        goto LABEL_75;
      }
      *v195 = v192;
      v196 = v195 + 1;
      v236 = v196;
      v197 = (char *)v196;
      if ( v192 )
      {
        do
        {
          SharedRefPtr<Legacy::Override>::`default constructor closure'(v197);
          v197 += 8;
          --v192;
        }
        while ( v192 );
        v196 = v236;
      }
      *(_QWORD *)(v5 + 104) = v196;
      if ( !v196 )
        goto LABEL_74;
      *(_DWORD *)(v5 + 92) = *(_DWORD *)(v5 + 96);
LABEL_268:
      v165 = *(unsigned int *)(v5 + 88);
      v166 = (char *)(*(_QWORD *)(v5 + 104) + 8 * v165);
      *(_DWORD *)(v5 + 88) = v165 + 1;
      if ( v166 != &v226 )
      {
        if ( *(_QWORD *)v166 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v166 + 16LL))(*(_QWORD *)v166);
        *(_QWORD *)v166 = v144;
        if ( v144 )
          (*(void (__fastcall **)(ClockVector *))(*(_QWORD *)v144 + 8LL))(v144);
      }
      goto LABEL_273;
    }
  }
LABEL_79:
  RangeSet::Recycle((RangeSet *)a1);
LABEL_66:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      (unsigned int)WPP_ff88f7f000e13ecf98ed337d60498caa_Traceguids,
      (unsigned int)"RangeSet::InitializeByMergingWithCoreFragment",
      v11);
  }
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(v223);
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>((__int64 *)&v217[1]);
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>((__int64 *)v217);
  SyncId::~SyncId((SyncId *)v213);
  SyncId::~SyncId((SyncId *)v210);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180013950  mov     [rsp-8+arg_18], r9
0x180013955  mov     [rsp-8+arg_0], rcx
0x18001395a  push    rbp
0x18001395b  push    rbx
0x18001395c  push    rsi
0x18001395d  push    rdi
0x18001395e  push    r12
0x180013960  push    r13
0x180013962  push    r14
0x180013964  push    r15
0x180013966  lea     rbp, [rsp-38h]
0x18001396b  sub     rsp, 138h
0x180013972  mov     r13, r9
0x180013975  mov     r14, r8
0x180013978  mov     rdi, rdx
0x18001397b  mov     r12, rcx
0x18001397e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013985  lea     rax, WPP_GLOBAL_Control
0x18001398c  cmp     rcx, rax
0x18001398f  jz      short loc_18001399B
0x180013991  test    byte ptr [rcx+1Ch], 40h
0x180013995  jnz     loc_180014E36
0x18001399b  lea     rbx, [rdi+28h]
0x18001399f  lea     rcx, [r12+28h]
0x1800139a4  cmp     rcx, rbx
0x1800139a7  jz      short loc_1800139B5
0x1800139a9  mov     eax, [rbx]
0x1800139ab  mov     [rcx], eax
0x1800139ad  movzx   eax, word ptr [rbx+4]
0x1800139b1  mov     [rcx+4], ax
0x1800139b5  mov     rcx, [r14]
0x1800139b8  lea     rdx, [rsp+170h+var_120]
0x1800139bd  mov     [rsp+170h+var_120], 0
0x1800139c5  mov     rax, [rcx]
0x1800139c8  mov     rax, [rax+38h]
0x1800139cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139d1  xor     ecx, ecx
0x1800139d3  mov     esi, eax
0x1800139d5  test    eax, eax
0x1800139d7  jnz     short loc_1800139FB
0x1800139d9  mov     edx, [rsp+170h+var_120]
0x1800139dd  mov     eax, 10h
0x1800139e2  dec     edx
0x1800139e4  add     edx, [rdi+8]
0x1800139e7  test    edx, edx
0x1800139e9  mov     [r12+8], ecx
0x1800139ee  mov     [r12+20h], ecx
0x1800139f3  cmovz   edx, eax
0x1800139f6  mov     [r12+10h], edx
0x1800139fb  mov     rax, [rbp+70h+arg_20]
0x180013a02  xorps   xmm0, xmm0
0x180013a05  mov     r12, [r13+30h]
0x180013a09  mov     [rbp+70h+var_98], rax
0x180013a0d  lea     rax, [rbp+70h+var_B8]
0x180013a11  mov     [rsp+170h+var_100], ecx
0x180013a15  mov     [rsp+170h+var_F4], ecx
0x180013a19  mov     [rbp+70h+var_F0], rcx
0x180013a1d  mov     [rbp+70h+var_E4], ecx
0x180013a20  mov     [rbp+70h+var_E0], rcx
0x180013a24  movdqa  xmmword ptr [rbp+70h+var_D0], xmm0
0x180013a29  mov     [rbp+70h+var_C0], 0
0x180013a31  mov     [rbp+70h+var_B8], ecx
0x180013a34  mov     [rbp+70h+var_B4], cx
0x180013a38  mov     [rbp+70h+var_A0], rcx
0x180013a3c  mov     [rbp+70h+var_90], rcx
0x180013a40  cmp     rax, rbx
0x180013a43  jz      short loc_180013A52
0x180013a45  mov     eax, [rbx]
0x180013a47  mov     [rbp+70h+var_B8], eax
0x180013a4a  movzx   eax, word ptr [rbx+4]
0x180013a4e  mov     [rbp+70h+var_B4], ax
0x180013a52  lea     rax, [rbp+70h+var_A0]
0x180013a56  mov     [rbp+70h+var_B0], rdi
0x180013a5a  mov     [rbp+70h+var_A8], ecx
0x180013a5d  cmp     rax, r14
0x180013a60  jz      short loc_180013A7A
0x180013a62  mov     rcx, [r14]
0x180013a65  mov     [rbp+70h+var_A0], rcx
0x180013a69  test    rcx, rcx
0x180013a6c  jz      short loc_180013A7A
0x180013a6e  mov     rax, [rcx]
0x180013a71  mov     rax, [rax+8]
0x180013a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a7a  mov     [rbp+70h+var_90], r12
0x180013a7e  test    esi, esi
0x180013a80  jnz     loc_180013E2A
0x180013a86  lea     rcx, [rsp+170h+var_100]
0x180013a8b  call    ?Begin@?$DoubleIterator@VIteratorWithCoreFragment@RangeSet@@KV?$SharedRefPtr@UIClockVector@@@@@@QEAAJXZ; DoubleIterator<RangeSet::IteratorWithCoreFragment,ulong,SharedRefPtr<IClockVector>>::Begin(void)
0x180013a90  mov     esi, eax
0x180013a92  test    eax, eax
0x180013a94  jnz     loc_180013E2A
0x180013a9a  mov     edi, [rbp+70h+var_7C]
0x180013a9d  mov     ebx, 0FFFFFFFFh
0x180013aa2  cmp     dword ptr [rbp+70h+var_C0+4], 0
0x180013aa6  mov     r12d, 8007000Eh
0x180013aac  jnz     loc_180013D3A
0x180013ab2  mov     r9, [r13+90h]
0x180013ab9  mov     r14, [rbp+70h+var_D0]
0x180013abd  mov     r15d, [rbp+70h+var_D8]
0x180013ac1  mov     dword ptr [rbp+70h+arg_10], r15d
0x180013ac8  mov     [rbp-10h], r14
0x180013acc  test    r9, r9
0x180013acf  jz      loc_1800146F8
0x180013ad5  mov     r11d, [r13+88h]
0x180013adc  mov     eax, r14d
0x180013adf  shr     eax, 10h
0x180013ae2  mov     rcx, r14
0x180013ae5  shr     rcx, 20h
0x180013ae9  movzx   edx, r14w
0x180013aed  shl     edx, 10h
0x180013af0  or      edx, eax
0x180013af2  movzx   eax, cx
0x180013af5  shl     eax, 10h
0x180013af8  shr     ecx, 10h
0x180013afb  or      eax, ecx
0x180013afd  movzx   ecx, r15w
0x180013b01  xor     edx, eax
0x180013b03  shl     ecx, 10h
0x180013b06  mov     eax, r15d
0x180013b09  shr     eax, 10h
0x180013b0c  or      ecx, eax
0x180013b0e  xor     edx, ecx
0x180013b10  lea     ecx, [r11-1]
0x180013b14  mov     eax, edx
0x180013b16  mov     r8d, edx
0x180013b19  shr     eax, 5
0x180013b1c  xor     edx, edx
0x180013b1e  inc     eax
0x180013b20  div     ecx
0x180013b22  xor     r10d, r10d
0x180013b25  lea     esi, [rdx+1]
0x180013b28  cmp     r10d, r11d
0x180013b2b  jnb     loc_1800146F8
0x180013b31  xor     edx, edx
0x180013b33  mov     rax, r8
0x180013b36  div     r11
0x180013b39  mov     rax, rdx
0x180013b3c  shl     rax, 5
0x180013b40  movzx   ecx, byte ptr [rax+r9+18h]
0x180013b46  test    cl, 1
0x180013b49  jz      loc_180013C66
0x180013b4f  cmp     [rax+r9], r15d
0x180013b53  jnz     loc_180013C6F
0x180013b59  cmp     [rax+r9+8], r14
0x180013b5e  jnz     loc_180013C6F
0x180013b64  mov     eax, edx
0x180013b66  shl     rax, 5
0x180013b6a  mov     r14d, [rax+r9+10h]
0x180013b6f  mov     dword ptr [rbp+70h+arg_20], r14d
0x180013b76  cmp     ebx, 0FFFFFFFFh
0x180013b79  jnz     loc_180013C7D
0x180013b7f  cmp     [rsp+170h+var_100], 0
0x180013b84  mov     ebx, r14d
0x180013b87  mov     r13, [rbp+70h+arg_0]
0x180013b8e  jg      loc_180013CA9
0x180013b94  mov     eax, [rsp+170h+var_F4]
0x180013b98  mov     r12, [rbp+70h+var_F0]
0x180013b9c  mov     dword ptr [rbp+70h+arg_8], eax
0x180013ba2  test    r12, r12
0x180013ba5  jz      short loc_180013BAC
0x180013ba7  lock inc dword ptr [r12]
0x180013bac  xor     esi, esi
0x180013bae  cmp     [r13+18h], rsi
0x180013bb2  jz      loc_180013CB5
0x180013bb8  mov     eax, [r13+8]
0x180013bbc  mov     edx, [r13+0Ch]
0x180013bc0  inc     eax
0x180013bc2  cmp     eax, edx
0x180013bc4  ja      loc_180013DDE
0x180013bca  mov     edx, [r13+8]
0x180013bce  mov     rax, [r13+18h]
0x180013bd2  lea     rcx, [rdx+rdx*2]
0x180013bd6  lea     r14, [rax+rcx*8]
0x180013bda  lea     eax, [rdx+1]
0x180013bdd  mov     [r13+8], eax
0x180013be1  lea     rax, [rbp+70h+var_60]
0x180013be5  cmp     r14, rax
0x180013be8  jz      loc_180013DAD
0x180013bee  test    dword ptr [r14+4], 20000h
0x180013bf6  jnz     short loc_180013C13
0x180013bf8  mov     rcx, [r14+8]
0x180013bfc  test    rcx, rcx
0x180013bff  jz      short loc_180013C13
0x180013c01  mov     eax, 0FFFFFFFFh
0x180013c06  lock xadd [rcx], eax
0x180013c0a  cmp     eax, 1
0x180013c0d  jz      loc_180013DC5
0x180013c13  mov     ecx, dword ptr [rbp+70h+arg_8]
0x180013c19  mov     [r14+4], ecx
0x180013c1d  mov     [r14+8], r12
0x180013c21  test    r12, r12
0x180013c24  jz      short loc_180013C2B
0x180013c26  lock inc dword ptr [r12]
0x180013c2b  mov     [r14+10h], ebx
0x180013c2f  test    esi, esi
0x180013c31  jnz     short loc_180013C3E
0x180013c33  xor     eax, eax
0x180013c35  test    ebx, ebx
0x180013c37  setz    al
0x180013c3a  add     [r13+20h], eax
0x180013c3e  bt      ecx, 11h
0x180013c42  jb      short loc_180013C5D
0x180013c44  test    r12, r12
0x180013c47  jz      short loc_180013C5D
0x180013c49  mov     eax, 0FFFFFFFFh
0x180013c4e  lock xadd [r12], eax
0x180013c54  cmp     eax, 1
0x180013c57  jz      loc_180013DB8
0x180013c5d  test    esi, esi
0x180013c5f  jz      short loc_180013C89
0x180013c61  jmp     loc_180013E2A
0x180013c66  test    cl, 2
0x180013c69  jz      loc_1800146F8
0x180013c6f  mov     r8d, esi
0x180013c72  add     r8, rdx
0x180013c75  inc     r10d
0x180013c78  jmp     loc_180013B28
0x180013c7d  cmp     ebx, r14d
0x180013c80  jnz     loc_180013B7F
0x180013c86  mov     ebx, r14d
0x180013c89  lea     rcx, [rsp+170h+var_100]
0x180013c8e  call    ?MoveNext@?$DoubleIterator@VIteratorWithCoreFragment@RangeSet@@KV?$SharedRefPtr@UIClockVector@@@@@@QEAAJXZ; DoubleIterator<RangeSet::IteratorWithCoreFragment,ulong,SharedRefPtr<IClockVector>>::MoveNext(void)
0x180013c93  mov     esi, eax
0x180013c95  test    eax, eax
0x180013c97  jnz     loc_180013E2A
0x180013c9d  mov     r13, [rbp+70h+arg_18]
0x180013ca4  jmp     loc_180013AA2
0x180013ca9  mov     eax, [rbp+70h+var_E4]
0x180013cac  mov     r12, [rbp+70h+var_E0]
0x180013cb0  jmp     loc_180013B9C
0x180013cb5  mov     r14d, [r13+10h]
0x180013cb9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180013cc0  mov     eax, 18h
0x180013cc5  mul     r14
0x180013cc8  cmovb   rax, rcx
0x180013ccc  add     rax, 8
0x180013cd0  cmovb   rax, rcx
0x180013cd4  mov     rcx, cs:hHeap; hHeap
0x180013cdb  mov     r8, rax; dwBytes
0x180013cde  xor     edx, edx; dwFlags
0x180013ce0  call    cs:__imp_HeapAlloc
0x180013ce6  mov     [rbp+70h+arg_10], rax
0x180013ced  test    rax, rax
0x180013cf0  jz      loc_180013E3B
0x180013cf6  mov     [rax], r14
0x180013cf9  lea     r15, [rax+8]
0x180013cfd  test    r14, r14
0x180013d00  jz      loc_180013DD3
0x180013d06  mov     rcx, r15; this
0x180013d09  call    ??0ColumnEntry@@QEAA@XZ; ColumnEntry::ColumnEntry(void)
0x180013d0e  add     r15, 18h
0x180013d12  sub     r14, 1
0x180013d16  jnz     short loc_180013D06
0x180013d18  mov     rax, [rbp+70h+arg_10]
0x180013d1f  add     rax, 8
0x180013d23  mov     [r13+18h], rax
0x180013d27  jz      loc_180013E3F
0x180013d2d  mov     eax, [r13+10h]
0x180013d31  mov     [r13+0Ch], eax
0x180013d35  jmp     loc_180013BCA
0x180013d3a  cmp     dword ptr [rbp+70h+var_C0], 0
0x180013d3e  jz      loc_180013AB2
0x180013d44  test    esi, esi
0x180013d46  jnz     loc_180013E2A
0x180013d4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d53  lea     rax, WPP_GLOBAL_Control
0x180013d5a  cmp     rcx, rax
0x180013d5d  jz      short loc_180013D69
0x180013d5f  test    byte ptr [rcx+1Ch], 40h
0x180013d63  jnz     loc_180014EC5
0x180013d69  lea     rcx, [rbp+70h+var_A0]
0x180013d6d  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180013d72  lea     rcx, [rbp+70h+var_D0+8]
0x180013d76  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180013d7b  lea     rcx, [rbp+70h+var_D0]
0x180013d7f  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180013d84  lea     rcx, [rbp+70h+var_E8]; this
0x180013d88  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x180013d8d  lea     rcx, [rsp+170h+var_F8]; this
0x180013d92  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x180013d97  mov     eax, esi
0x180013d99  add     rsp, 138h
0x180013da0  pop     r15
0x180013da2  pop     r14
0x180013da4  pop     r13
0x180013da6  pop     r12
0x180013da8  pop     rdi
0x180013da9  pop     rsi
0x180013daa  pop     rbx
0x180013dab  pop     rbp
0x180013dac  retn
0x180013dad  mov     ecx, dword ptr [rbp+70h+arg_8]
0x180013db3  jmp     loc_180013C2B
0x180013db8  mov     rcx, r12; void *
0x180013dbb  call    ?SeFree@@YAXPEAX@Z; SeFree(void *)
0x180013dc0  jmp     loc_180013C5D
0x180013dc5  mov     rcx, [r14+8]; void *
0x180013dc9  call    ?SeFree@@YAXPEAX@Z; SeFree(void *)
0x180013dce  jmp     loc_180013C13
0x180013dd3  mov     ebx, dword ptr [rbp+70h+arg_20]
  ... truncated ...
```
