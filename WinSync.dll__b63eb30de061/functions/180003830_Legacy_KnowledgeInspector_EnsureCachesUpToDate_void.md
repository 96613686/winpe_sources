# Legacy::KnowledgeInspector::EnsureCachesUpToDate(void)

- ea: `0x180003830`
- end: `0x180005bd4`
- name: `?EnsureCachesUpToDate@KnowledgeInspector@Legacy@@AEAAJXZ`
- size: `9124`
- prototype: `__int64 __fastcall(Legacy::KnowledgeInspector *__hidden this)`
- caller_count: `2`
- callee_count: `38`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003254`
- `0x18008edb0`

## callees

- `0x1800028e0`
- `0x180003830`
- `0x180005d80`
- `0x180005d90`
- `0x180005e14`
- `0x180005e38`
- `0x180005e8c`
- `0x180005eb0`
- `0x180005f20`
- `0x180006400`
- `0x1800064a4`
- `0x180006554`
- `0x1800068a4`
- `0x1800069c0`
- `0x1800069f4`
- `0x180007584`
- `0x180009d7c`
- `0x18000c270`
- `0x18000c3e4`
- `0x18000c920`
- `0x18000c958`
- `0x18000e4e0`
- `0x18000e81c`
- `0x18000ebb0`
- `0x18000f810`
- `0x1800110f8`
- `0x180011f60`
- `0x1800158d0`
- `0x180017d50`
- `0x18001a038`
- `0x18001ac40`
- `0x18001ae20`
- `0x180024d38`
- `0x180082c20`
- `0x18008393c`
- `0x180092878`
- `0x180093232`
- `0x180094010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003ab6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003d54`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000489d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004f41`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004fc1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000519c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005316`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000573e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003ab6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003d54`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000489d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004f41`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004fc1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000519c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005316`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000573e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ad1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ad1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b5b`

## string_xrefs

- `0x180005494`: `Legacy::Override::InitializeAsItemOverride`
- `0x1800054f6`: `Legacy::Override::InitializeAsItemOverride`
- `0x18000594e`: `Legacy::KnowledgeInspector::EnsureCachesUpToDate`
- `0x180005bb2`: `Legacy::KnowledgeInspector::EnsureCachesUpToDate`

## pseudocode

```c
__int64 __fastcall Legacy::KnowledgeInspector::EnsureCachesUpToDate(Legacy::KnowledgeInspector *this)
{
  PVOID *v2; // rcx
  int v3; // r13d
  int v4; // eax
  unsigned int v5; // r12d
  __int64 v6; // rcx
  _QWORD *v7; // r14
  RangeSet *v8; // rdi
  unsigned int v9; // r10d
  unsigned int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rax
  void *v14; // r9
  __int64 v15; // rax
  int v16; // r15d
  __int64 v17; // rsi
  int v18; // r8d
  unsigned __int16 i; // dx
  unsigned __int16 *v20; // r10
  int v21; // r9d
  unsigned __int16 *v22; // rcx
  int v23; // r12d
  _DWORD *v24; // rbx
  char *v25; // rdx
  _WORD *v26; // r14
  _BYTE *v27; // rcx
  unsigned int v28; // r10d
  char *v29; // rsi
  char *v30; // rcx
  int v31; // edi
  char *v32; // r9
  char *v33; // r11
  unsigned int v34; // edx
  unsigned int v35; // r8d
  char *v36; // rax
  int v37; // r15d
  int v38; // r12d
  __int64 v39; // rbx
  __int64 v40; // rdi
  __int64 v41; // rsi
  __int64 v42; // r14
  __int64 v43; // rbx
  char *v44; // rdi
  __int64 v45; // rax
  Legacy::KnowledgeInspector *v46; // rbx
  __int64 v47; // rdx
  Legacy::Override *v48; // rax
  __int64 v49; // r13
  struct RangeSet *v50; // rbx
  unsigned int v51; // edx
  unsigned int v52; // r8d
  int v53; // eax
  __int64 v54; // rdi
  __int64 i5; // rsi
  int v56; // r15d
  int v57; // eax
  int v58; // eax
  int v59; // eax
  int v60; // ecx
  int v61; // eax
  int v62; // eax
  int v63; // eax
  int v64; // eax
  int v65; // ecx
  int v66; // eax
  int v67; // eax
  int v68; // eax
  int v69; // eax
  int v70; // ecx
  int v71; // eax
  unsigned int v73; // r9d
  unsigned int v74; // ecx
  int v75; // r8d
  __int64 v76; // r9
  unsigned int v77; // ebx
  __int64 v78; // r11
  __int64 v79; // r10
  int v80; // eax
  _QWORD *v81; // r15
  int v82; // eax
  bool v83; // zf
  __int64 *v84; // rbx
  unsigned int *v85; // r15
  struct SyncId *v86; // r12
  _WORD *v87; // rcx
  unsigned int v88; // r10d
  unsigned __int8 *v89; // rdx
  unsigned int v90; // ebx
  unsigned __int8 *i1; // r8
  __int64 v92; // r13
  unsigned __int64 v93; // r14
  unsigned __int64 v94; // r12
  unsigned int i2; // esi
  unsigned __int64 v96; // r12
  __int64 v97; // rcx
  char v98; // al
  unsigned __int64 v99; // r8
  unsigned __int64 v100; // r8
  __int64 v101; // r11
  unsigned __int64 v102; // rax
  unsigned int i4; // r9d
  unsigned __int64 v104; // rdx
  __int64 v105; // rcx
  char v106; // al
  volatile signed __int32 *v107; // rbx
  int v108; // r14d
  __int64 v109; // rsi
  volatile signed __int32 *v110; // rcx
  volatile signed __int32 *v111; // rcx
  void **v112; // rbx
  __int64 v113; // rsi
  void *v114; // rcx
  _BYTE *v115; // r15
  _BYTE *v116; // r8
  _BYTE *v117; // rdx
  int v118; // r9d
  _BYTE *v119; // rcx
  _BYTE *v120; // r9
  __int64 v121; // rcx
  struct SyncId *v122; // rdx
  __int64 v123; // r10
  int v124; // r8d
  unsigned int v125; // r11d
  int v126; // r9d
  __int64 v127; // r10
  __int64 v128; // r11
  int v129; // r8d
  __int64 v130; // rcx
  unsigned __int16 j; // dx
  __int64 v132; // rcx
  unsigned __int16 *v133; // rcx
  __int64 v134; // rsi
  __int64 v135; // rax
  bool v136; // cf
  SIZE_T v137; // rax
  _QWORD *v138; // rax
  _QWORD *v139; // r15
  _QWORD *i3; // r14
  unsigned __int16 *v141; // rax
  char *v142; // r8
  unsigned __int16 v143; // ax
  char *v144; // rdx
  char *v145; // r10
  char *v146; // r9
  __int64 v147; // r11
  __int64 v148; // r10
  __int64 v149; // rcx
  unsigned __int16 v150; // ax
  unsigned int v151; // eax
  _WORD *v152; // rcx
  unsigned __int16 *v153; // rax
  unsigned __int16 *v154; // rcx
  unsigned __int16 *v155; // rcx
  char *v156; // rsi
  __int64 v157; // rbx
  unsigned int v158; // r9d
  unsigned int v159; // r12d
  unsigned __int64 v160; // rdx
  unsigned __int64 v161; // r8
  char v162; // cl
  __int64 v163; // rdx
  unsigned int v164; // r15d
  unsigned int v165; // r10d
  unsigned int v166; // ecx
  int v167; // r11d
  __int64 n; // r10
  __int64 v169; // rcx
  __int64 v170; // rbx
  __int64 v171; // rcx
  unsigned __int64 v172; // r8
  Legacy::KnowledgeInspector *v173; // rbx
  __int64 *v174; // rbx
  unsigned int v175; // edx
  __int64 v176; // rcx
  __int64 *v177; // rbx
  PVOID *v178; // rcx
  __int64 v179; // r12
  __int64 v180; // rsi
  __int64 v181; // r14
  volatile signed __int32 *v182; // rcx
  volatile signed __int32 *v183; // rax
  __int64 *v184; // rbx
  _QWORD *v185; // rax
  _DWORD *v186; // r10
  unsigned int v187; // r14d
  unsigned int *v188; // r15
  int v189; // r12d
  struct SyncId *v190; // r8
  unsigned __int64 v191; // rbx
  __int64 v192; // rax
  SIZE_T v193; // rax
  _QWORD *v194; // rax
  _QWORD *v195; // r14
  char *jj; // rsi
  unsigned int *v197; // rsi
  __int64 v198; // r14
  unsigned int v199; // r11d
  unsigned int v200; // r9d
  unsigned int ii; // r10d
  __int64 v202; // r8
  unsigned __int64 v203; // r13
  unsigned __int64 v204; // rsi
  unsigned int v205; // r15d
  unsigned int v206; // r12d
  unsigned __int64 v207; // rdx
  unsigned __int64 v208; // rsi
  char v209; // cl
  __int64 v210; // rdx
  unsigned int v211; // r11d
  int v212; // r14d
  int v213; // ecx
  __int64 nn; // r10
  __int64 v215; // r9
  __int64 v216; // r8
  unsigned int v217; // r15d
  unsigned __int64 v218; // rbx
  __int64 v219; // rax
  SIZE_T v220; // rax
  _QWORD *v221; // rax
  _QWORD *v222; // r14
  char *v223; // rsi
  _QWORD *v224; // rsi
  __int64 v225; // rbx
  unsigned int v226; // r8d
  unsigned __int64 v227; // r8
  __int64 v228; // r11
  unsigned __int64 v229; // rax
  unsigned int kk; // r9d
  unsigned __int64 v231; // rdx
  __int64 v232; // rcx
  char v233; // al
  unsigned __int64 v234; // rbx
  __int64 v235; // rax
  SIZE_T v236; // rax
  _QWORD *v237; // rax
  _QWORD *v238; // r14
  char *mm; // rsi
  __int64 v240; // rbx
  __int64 v241; // rcx
  unsigned int NextPrimeNumber; // eax
  __int64 v243; // r9
  __int64 v244; // r8
  __int64 v245; // rcx
  __int64 v246; // r13
  unsigned __int64 v247; // r14
  unsigned int v248; // r11d
  unsigned int v249; // r9d
  unsigned int m; // r10d
  __int64 v251; // r8
  int v252; // r12d
  volatile signed __int32 *v253; // r14
  unsigned int v254; // esi
  __int64 v255; // rbx
  __int64 v256; // rsi
  volatile signed __int32 *v257; // rax
  __int64 *v258; // rbx
  _QWORD *v259; // rcx
  __int64 v260; // rax
  __int64 v261; // rbx
  SIZE_T v262; // rax
  _QWORD *v263; // rax
  _QWORD *v264; // r15
  unsigned int v265; // edx
  int v266; // r15d
  bool v267; // zf
  __int64 *v268; // rbx
  char *k; // rsi
  int v270; // eax
  unsigned int Size; // edx
  unsigned __int64 v272; // r15
  int v273; // eax
  __int64 v274; // rdx
  __int64 v275; // [rsp+38h] [rbp-D0h]
  unsigned int v276; // [rsp+40h] [rbp-C8h]
  unsigned int v277; // [rsp+44h] [rbp-C4h]
  unsigned int v278; // [rsp+48h] [rbp-C0h]
  __int64 v279; // [rsp+50h] [rbp-B8h]
  unsigned int *v280; // [rsp+50h] [rbp-B8h]
  struct SyncId *v281; // [rsp+58h] [rbp-B0h]
  struct SyncId *v282; // [rsp+58h] [rbp-B0h]
  struct SyncId *v283; // [rsp+58h] [rbp-B0h]
  __int64 v284; // [rsp+60h] [rbp-A8h] BYREF
  RangeSet *v285; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v286; // [rsp+70h] [rbp-98h]
  unsigned int v287; // [rsp+78h] [rbp-90h]
  _BYTE v288[4]; // [rsp+80h] [rbp-88h] BYREF
  int v289; // [rsp+84h] [rbp-84h]
  void *v290; // [rsp+88h] [rbp-80h]
  _QWORD *v291; // [rsp+90h] [rbp-78h]
  unsigned int v292; // [rsp+98h] [rbp-70h]
  __int64 v293; // [rsp+A0h] [rbp-68h]
  LPVOID lpMem; // [rsp+A8h] [rbp-60h]
  __int64 v295; // [rsp+B0h] [rbp-58h] BYREF
  int v296; // [rsp+B8h] [rbp-50h]
  __int64 v297; // [rsp+BCh] [rbp-4Ch]
  _QWORD *v298; // [rsp+C8h] [rbp-40h]
  _BYTE v299[4]; // [rsp+D0h] [rbp-38h] BYREF
  int v300; // [rsp+D4h] [rbp-34h]
  volatile signed __int32 *v301; // [rsp+D8h] [rbp-30h]
  __int64 v302; // [rsp+E0h] [rbp-28h] BYREF
  int v303; // [rsp+E8h] [rbp-20h]
  _QWORD *v304; // [rsp+F0h] [rbp-18h]
  __int64 v305; // [rsp+F8h] [rbp-10h] BYREF
  int v306; // [rsp+100h] [rbp-8h]
  _QWORD *v307; // [rsp+108h] [rbp+0h]
  _QWORD v308[2]; // [rsp+110h] [rbp+8h] BYREF
  __int64 v309; // [rsp+120h] [rbp+18h]
  int v310; // [rsp+128h] [rbp+20h] BYREF
  __int16 v311; // [rsp+12Ch] [rbp+24h]
  __int64 v312; // [rsp+130h] [rbp+28h]
  _BYTE v313[48]; // [rsp+138h] [rbp+30h] BYREF
  __int64 v314; // [rsp+168h] [rbp+60h] BYREF
  int v315; // [rsp+170h] [rbp+68h]
  _QWORD *v316; // [rsp+178h] [rbp+70h]
  _DWORD v317[2]; // [rsp+180h] [rbp+78h] BYREF
  _BYTE v318[48]; // [rsp+188h] [rbp+80h] BYREF
  __int64 v319; // [rsp+1B8h] [rbp+B0h] BYREF
  int v320; // [rsp+1C0h] [rbp+B8h]
  _QWORD *v321; // [rsp+1C8h] [rbp+C0h]
  _DWORD v322[2]; // [rsp+1D0h] [rbp+C8h] BYREF
  _BYTE v323[48]; // [rsp+1D8h] [rbp+D0h] BYREF
  __int64 v324; // [rsp+208h] [rbp+100h] BYREF
  int v325; // [rsp+210h] [rbp+108h]
  __int64 v326; // [rsp+218h] [rbp+110h]
  _DWORD v327[2]; // [rsp+220h] [rbp+118h] BYREF
  char v328[4]; // [rsp+228h] [rbp+120h] BYREF
  _BYTE v329[12]; // [rsp+22Ch] [rbp+124h]
  _BYTE v330[4]; // [rsp+238h] [rbp+130h] BYREF
  int v331; // [rsp+23Ch] [rbp+134h]
  __int128 v332; // [rsp+240h] [rbp+138h]
  int v333; // [rsp+250h] [rbp+148h]
  __int64 v334; // [rsp+258h] [rbp+150h]
  int v335; // [rsp+260h] [rbp+158h]
  __int64 v336; // [rsp+268h] [rbp+160h]
  char v337; // [rsp+270h] [rbp+168h] BYREF
  char v338; // [rsp+278h] [rbp+170h] BYREF
  char v339; // [rsp+280h] [rbp+178h] BYREF
  char v340; // [rsp+288h] [rbp+180h] BYREF
  char v341; // [rsp+290h] [rbp+188h] BYREF
  struct RangeSet *v343; // [rsp+300h] [rbp+1F8h] BYREF
  unsigned int v344; // [rsp+308h] [rbp+200h]
  unsigned int v345; // [rsp+310h] [rbp+208h]

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_48b71e9a06de38317ed143d1f750f029_Traceguids,
      "Legacy::KnowledgeInspector::EnsureCachesUpToDate");
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v3 = 0;
  if ( !*((_QWORD *)this + 1) )
  {
    v4 = Legacy::KnowledgeInspector::EnsureCachedScopeVector(this);
    v2 = (PVOID *)WPP_GLOBAL_Control;
    v3 = v4;
    if ( v4 )
      goto LABEL_119;
  }
  if ( *((_DWORD *)this + 22) != -1 )
    goto LABEL_119;
  v306 = 16;
  v292 = 16;
  v303 = 16;
  v5 = 0;
  LODWORD(v308[1]) = 16;
  v6 = *(_QWORD *)this;
  v7 = 0;
  v277 = 0;
  v305 = 0;
  v276 = 0;
  v291 = 0;
  v307 = 0;
  v286 = 0;
  v302 = 0;
  v298 = 0;
  v304 = 0;
  v296 = 0;
  v308[0] = 0;
  v297 = 0x1000000000LL;
  v312 = 0;
  v309 = 0;
  v285 = 0;
  v3 = RangeSetManager::FindByIndex(v6 + 184, 0, &v285);
  if ( v3 )
  {
LABEL_80:
    v50 = 0;
    goto LABEL_81;
  }
  v8 = v285;
  if ( !*((_DWORD *)v285 + 2) )
  {
    v3 = -2147217379;
    goto LABEL_80;
  }
  v3 = ClockVectorManager::Initialize((Legacy::KnowledgeInspector *)((char *)this + 256), 4u);
  if ( v3 )
    goto LABEL_95;
  v9 = 0;
  v345 = 0;
  while ( 2 )
  {
    v10 = *((_DWORD *)v8 + 2);
    if ( v9 >= v10 )
      goto LABEL_94;
    v11 = v9 + 1;
    v289 = 0;
    v290 = 0;
    if ( (unsigned int)v11 >= v10 )
    {
      v38 = 0;
      v121 = v9;
      v122 = (RangeSet *)((char *)v8 + 24);
LABEL_233:
      v37 = 0;
      goto LABEL_210;
    }
    v12 = *((_QWORD *)v8 + 3);
    v281 = (RangeSet *)((char *)v8 + 24);
    v13 = v12 + 24 * v11;
    if ( v288 != (_BYTE *)v13 )
    {
      v14 = *(void **)(v13 + 8);
      v289 = *(_DWORD *)(v13 + 4);
      v290 = v14;
      if ( v14 )
      {
        _InterlockedIncrement((volatile signed __int32 *)v14);
        v12 = *((_QWORD *)v8 + 3);
      }
    }
    v279 = v9;
    v15 = 24LL * v9;
    v16 = *(_DWORD *)(v12 + v15 + 4);
    v17 = v12 + v15;
    v293 = v15;
    v18 = v16 & 0x10000;
    if ( (v16 & 0x10000) == 0 )
      goto LABEL_16;
    v20 = *(unsigned __int16 **)(v17 + 8);
    v21 = v16 & 0x20000;
    v133 = v20;
    if ( (v16 & 0x20000) == 0 )
      v133 = v20 + 2;
    if ( *v133 >= (unsigned int)(unsigned __int16)v16 )
    {
LABEL_16:
      for ( i = v18 != 0 ? 2 : 0; i < (unsigned int)(unsigned __int16)v16; ++i )
      {
        v20 = *(unsigned __int16 **)(v17 + 8);
        v21 = v16 & 0x20000;
        v22 = v20;
        if ( (v16 & 0x20000) == 0 )
          v22 = v20 + 2;
        if ( *((_BYTE *)v22 + i) != 0xFF )
          goto LABEL_21;
      }
      v122 = (RangeSet *)((char *)v8 + 24);
      v121 = v279;
      v38 = 1;
      goto LABEL_233;
    }
LABEL_21:
    v287 = 0;
    *(_DWORD *)&v329[8] = 0;
    v344 = v16 & 0xFFFDFFFF;
    *(_QWORD *)v329 = v16 & 0xFFFDFFFF;
    v23 = v16 & 0x10000;
    if ( (v16 & 0x10000) != 0 )
    {
      if ( v18 )
      {
        v154 = v20;
        if ( (v16 & 0x20000) == 0 )
          v154 = v20 + 2;
        v150 = *v154;
      }
      else
      {
        v150 = v16;
      }
      if ( v150 >= (unsigned __int16)v16 )
      {
        if ( v18 )
        {
          v155 = v20;
          if ( (v16 & 0x20000) == 0 )
            v155 = v20 + 2;
          LOWORD(v16) = *v155;
        }
        if ( (unsigned __int16)v16 <= 2u )
        {
LABEL_277:
          v3 = -2147024809;
          ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
          v24 = lpMem;
          goto LABEL_230;
        }
        if ( !v21 )
          v20 += 2;
        while ( *((_BYTE *)v20 + (unsigned __int16)v16 - 1) == 0xFF )
        {
          LOWORD(v16) = v16 - 1;
          if ( (unsigned __int16)v16 <= 2u )
            goto LABEL_277;
        }
      }
      else
      {
        if ( v18 )
        {
          if ( (v16 & 0x20000) == 0 )
            v20 += 2;
          LOWORD(v16) = *v20;
        }
        LOWORD(v16) = v16 + 1;
      }
    }
    else if ( v18 )
    {
      if ( !v21 )
        v20 += 2;
      LOWORD(v16) = *v20;
    }
    ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
    v24 = HeapAlloc(hHeap, 0, (unsigned __int16)v16 + 7LL);
    if ( lpMem )
      HeapFree(hHeap, 0, lpMem);
    v3 = 0;
    lpMem = v24;
    if ( !v24 )
    {
      v3 = -2147024882;
LABEL_230:
      SyncId::~SyncId((SyncId *)v328);
      v28 = 0;
      v344 = 0;
      v29 = 0;
      goto LABEL_36;
    }
    v25 = *(char **)(v17 + 8);
    v26 = v24 + 1;
    if ( (*(_DWORD *)(v17 + 4) & 0x20000) == 0 )
      v25 += 4;
    memcpy_0(v24 + 1, v25, (unsigned __int16)v16);
    if ( v23 )
    {
      v80 = *(_DWORD *)(v17 + 4);
      if ( (v80 & 0x10000) != 0 )
      {
        v152 = *(_WORD **)(v17 + 8);
        if ( (v80 & 0x20000) == 0 )
          v152 += 2;
        LOWORD(v80) = *v152;
      }
      v28 = v344;
      if ( (unsigned __int16)v80 >= (unsigned __int16)v344 )
        ++*((_BYTE *)v24 + (unsigned __int16)v16 + 3);
      else
        *((_BYTE *)v24 + (unsigned __int16)v16 + 3) = 0;
    }
    else
    {
      v27 = (char *)v24 + (unsigned __int16)v16 + 3;
      if ( v27 >= (_BYTE *)v26 )
      {
        while ( 1 )
        {
          v83 = (*v27)++ == 0xFF;
          if ( !v83 )
            break;
          if ( --v27 < (_BYTE *)v26 )
          {
            v3 = -2147024809;
            goto LABEL_230;
          }
        }
      }
      v28 = v344;
    }
    *v24 = 1;
    if ( v23 )
      *v26 = v16;
    v29 = (char *)v24;
    v24 = 0;
    lpMem = 0;
LABEL_36:
    if ( v24 )
    {
      HeapFree(hHeap, 0, v24);
      v28 = v344;
    }
    if ( v3 )
    {
      v37 = v287;
    }
    else
    {
      v30 = (char *)v290;
      v31 = v289 & 0x20000;
      if ( (v289 & 0x20000) == 0 )
        v30 = (char *)v290 + 4;
      v32 = v29;
      if ( (v28 & 0x20000) == 0 )
        v32 = v29 + 4;
      if ( v30 != v32 )
      {
        if ( (v289 & 0x10000) != 0 )
        {
          v141 = (unsigned __int16 *)v290;
          if ( !v31 )
            v141 = (unsigned __int16 *)((char *)v290 + 4);
          v142 = &v30[*v141];
          if ( (v28 & 0x10000) != 0 )
          {
            v153 = (unsigned __int16 *)v29;
            if ( (v28 & 0x20000) == 0 )
              v153 = (unsigned __int16 *)(v29 + 4);
            v143 = *v153;
          }
          else
          {
            v143 = v28;
          }
          v144 = v30 + 2;
          v145 = &v32[v143];
          v146 = v32 + 2;
          while ( v144 < v142 )
          {
            if ( v146 >= v145 || *v144 != *v146 )
              goto LABEL_54;
            ++v144;
            ++v146;
          }
          if ( v146 < v145 )
          {
LABEL_54:
            v28 = v344;
            v37 = 0;
            goto LABEL_55;
          }
          v28 = v344;
          v37 = 1;
          goto LABEL_55;
        }
        v33 = &v30[4 * ((unsigned __int64)(unsigned __int16)v289 >> 2)];
        while ( v30 < v33 )
        {
          v34 = *(_DWORD *)v32;
          v35 = *(_DWORD *)v30;
          if ( *(_DWORD *)v30 != *(_DWORD *)v32 )
          {
            if ( (unsigned __int8)v35 > (unsigned __int8)v34 )
              goto LABEL_54;
            if ( (unsigned __int8)v35 < (unsigned __int8)v34 )
              goto LABEL_54;
            if ( BYTE1(v35) < BYTE1(v34) )
              goto LABEL_54;
            if ( BYTE1(v35) > BYTE1(v34) )
              goto LABEL_54;
            if ( BYTE2(v35) > BYTE2(v34) )
              goto LABEL_54;
            if ( BYTE2(v35) < BYTE2(v34) )
              goto LABEL_54;
            v51 = HIBYTE(v34);
            v52 = HIBYTE(v35);
            if ( (unsigned __int8)v52 > (unsigned __int8)v51 || (unsigned __int8)v52 < (unsigned __int8)v51 )
              goto LABEL_54;
          }
          v30 += 4;
          v32 += 4;
        }
        if ( (v289 & 3) != 0 )
        {
          v36 = (char *)v290;
          if ( !v31 )
            v36 = (char *)v290 + 4;
          while ( v30 < &v36[(unsigned __int16)v289] )
          {
            if ( (unsigned __int8)*v30 > (unsigned __int8)*v32 || (unsigned __int8)*v30 < (unsigned __int8)*v32 )
              goto LABEL_54;
            ++v30;
            ++v32;
          }
        }
        v28 = v344;
      }
      v37 = 1;
    }
LABEL_55:
    if ( (v28 & 0x20000) == 0 && v29 && _InterlockedExchangeAdd((volatile signed __int32 *)v29, 0xFFFFFFFF) == 1 )
    {
      SeFree(v29);
      *(_QWORD *)&v329[4] = 0;
    }
    if ( v3 )
      goto LABEL_79;
    v38 = 1;
    if ( v37 )
    {
      v39 = v293;
      goto LABEL_62;
    }
    v121 = v279;
    v122 = v281;
LABEL_210:
    v39 = 24 * v121;
    v123 = 24 * v121 + *(_QWORD *)v122;
    v293 = 24 * v121;
    v124 = *(_DWORD *)(v123 + 4);
    v125 = (unsigned __int16)v124;
    v126 = v124 & 0x10000;
    if ( (v124 & 0x10000) == 0 || (Size = SyncId::GetSize((SyncId *)v123), Size >= v125) )
    {
      v127 = *(_QWORD *)(v123 + 8);
      v128 = v125 - 1;
      v129 = v124 & 0x20000;
      v293 = v39;
      v130 = v127;
      if ( !v129 )
        v130 = v127 + 4;
      if ( *(_BYTE *)(v130 + v128) == 0xFE )
      {
        for ( j = v126 != 0 ? 2 : 0; j < (unsigned int)v128; ++j )
        {
          v132 = v127;
          if ( !v129 )
            v132 = v127 + 4;
          if ( *(_BYTE *)(v132 + j) != 0xFF )
            goto LABEL_62;
        }
        v37 = 1;
        v293 = v39;
      }
    }
LABEL_62:
    v40 = 0;
    v284 = 0;
    v41 = *(_QWORD *)this;
    v42 = *(unsigned int *)(*((_QWORD *)v285 + 3) + v39 + 16);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_e65626ae806d36e8966776faf765a664_Traceguids,
        "ClockVectorManager::FindByIndex");
    }
    v43 = 0;
    if ( (unsigned int)v42 >= *(_DWORD *)(v41 + 120) )
    {
      v3 = -2147024809;
      goto LABEL_68;
    }
    v3 = 0;
    v44 = (char *)(*(_QWORD *)(v41 + 136) + 8 * v42);
    if ( &v337 == v44 )
      goto LABEL_237;
    v40 = *(_QWORD *)v44;
    if ( !v40 )
    {
      v43 = 0;
LABEL_237:
      v40 = 0;
      v284 = 0;
      goto LABEL_68;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 8LL))(v40);
    v45 = *(_QWORD *)v40;
    v284 = v40;
    (*(void (__fastcall **)(__int64))(v45 + 8))(v40);
    v43 = v40;
LABEL_68:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_e65626ae806d36e8966776faf765a664_Traceguids,
        (unsigned int)"ClockVectorManager::FindByIndex",
        v3);
    }
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    if ( v3 )
      goto LABEL_556;
    v46 = this;
    v47 = *((_QWORD *)this + 1);
    if ( v47 == v40 )
      goto LABEL_185;
    if ( *(_DWORD *)(v47 + 28) == *(_DWORD *)(v40 + 28) )
    {
      v73 = *(_DWORD *)(v40 + 36);
      v74 = *(_DWORD *)(v47 + 36);
      v75 = (v74 >> 1) & 1;
      if ( v75 == ((v73 >> 1) & 1)
        && *(_DWORD *)(v47 + 32) == *(_DWORD *)(v40 + 32)
        && (((unsigned __int8)v73 ^ (unsigned __int8)v74) & 4) == 0 )
      {
        v76 = 0;
        v77 = *(_DWORD *)(v47 + 28);
        while ( 1 )
        {
          if ( (unsigned int)v76 >= v77 )
            goto LABEL_185;
          v78 = *(_QWORD *)(v40 + 40);
          v79 = *(_QWORD *)(v47 + 40);
          if ( *(_DWORD *)(v79 + 16LL * (unsigned int)v76) != *(_DWORD *)(v78 + 16LL * (unsigned int)v76)
            || *(_QWORD *)(v79 + 16LL * (unsigned int)v76 + 8) != *(_QWORD *)(v78 + 16LL * (unsigned int)v76 + 8) )
          {
            break;
          }
          if ( v75 )
          {
            v147 = *(_QWORD *)(v40 + 48);
            v148 = *(_QWORD *)(v47 + 48);
            v149 = 12 * v76;
            if ( *(_DWORD *)(v148 + 12 * v76) != *(_DWORD *)(v147 + 12 * v76)
              || *(_DWORD *)(v148 + v149 + 4) != *(_DWORD *)(v147 + v149 + 4)
              || *(_BYTE *)(v148 + v149 + 8) != *(_BYTE *)(v147 + v149 + 8) )
            {
              break;
            }
            v77 = *(_DWORD *)(v47 + 28);
          }
          v76 = (unsigned int)(v76 + 1);
        }
        v46 = this;
      }
    }
    v48 = (Legacy::Override *)HeapAlloc(hHeap, 0, 0x58u);
    if ( !v48 || (v275 = Legacy::Override::Override(v48), v49 = v275, (v295 = v275) == 0) )
    {
      v3 = -2147024882;
      if ( v40 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
LABEL_79:
      SyncId::~SyncId((SyncId *)v288);
      goto LABEL_80;
    }
    if ( !v37 )
    {
      v300 = 0;
      v301 = 0;
      if ( v38 )
      {
        SyncId::~SyncId((SyncId *)v299);
        v252 = v289;
        v253 = (volatile signed __int32 *)v290;
        v254 = v345;
        v300 = v289;
        v301 = (volatile signed __int32 *)v290;
        if ( v290 )
          _InterlockedIncrement((volatile signed __int32 *)v290);
      }
      else
      {
        v254 = v345;
        v273 = HIWORD(*(_DWORD *)(*((_QWORD *)v285 + 3) + 24LL * v345 + 4)) & 1;
        v311 = *(_DWORD *)(*((_QWORD *)v285 + 3) + 24LL * v345 + 4);
        v310 = v273;
        v3 = SyncId::InitializeWithMaxId((SyncId *)v299, (const struct IdFormat *)&v310);
        if ( v3 )
        {
          SyncId::~SyncId((SyncId *)v299);
          SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v295);
          SharedRefPtr<ClockVector>::~SharedRefPtr<ClockVector>(&v284);
          SyncId::~SyncId((SyncId *)v288);
          v50 = 0;
          goto LABEL_81;
        }
        v253 = v301;
        v252 = v300;
        v49 = v275;
      }
      v255 = *((_QWORD *)v285 + 3);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_e65626ae806d36e8966776faf765a664_Traceguids,
          "Legacy::Override::InitializeAsRangeOverride");
      }
      *(_DWORD *)(v49 + 44) = 3;
      v256 = v255 + 24LL * v254;
      if ( v49 + 48 != v256 )
      {
        SyncId::~SyncId((SyncId *)(v49 + 48));
        *(_DWORD *)(v49 + 52) = *(_DWORD *)(v256 + 4);
        v257 = *(volatile signed __int32 **)(v256 + 8);
        *(_QWORD *)(v49 + 56) = v257;
        if ( v257 )
          _InterlockedIncrement(v257);
      }
      if ( (_BYTE *)(v49 + 64) != v299 )
      {
        SyncId::~SyncId((SyncId *)(v49 + 64));
        *(_DWORD *)(v49 + 68) = v252;
        *(_QWORD *)(v49 + 72) = v253;
        if ( v253 )
          _InterlockedIncrement(v253);
      }
      v258 = (__int64 *)(v49 + 80);
      if ( (__int64 *)(v49 + 80) != &v284 )
      {
        if ( *v258 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)*v258 + 16LL))(*v258);
        *v258 = v40;
        if ( v40 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 8LL))(v40);
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)WPP_e65626ae806d36e8966776faf765a664_Traceguids,
          (unsigned int)"Legacy::Override::InitializeAsRangeOverride",
          0);
      }
      v259 = v298;
      if ( v298 )
      {
        v266 = v286;
        if ( (unsigned int)(v286 + 1) <= HIDWORD(v286) )
        {
          v113 = v275;
          v3 = 0;
LABEL_507:
          v268 = &v259[v266];
          LODWORD(v286) = v266 + 1;
          LODWORD(v302) = v266 + 1;
          if ( v268 != &v295 )
          {
            if ( *v268 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)*v268 + 16LL))(*v268);
            *v268 = v113;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v113 + 8LL))(v113);
          }
          v267 = v3 == 0;
LABEL_512:
          if ( v267 )
          {
            if ( (v252 & 0x20000) == 0 && v253 && _InterlockedExchangeAdd(v253, 0xFFFFFFFF) == 1 )
            {
              SeFree((void *)v253);
              v301 = 0;
            }
            goto LABEL_184;
          }
          SyncId::~SyncId((SyncId *)v299);
LABEL_555:
          SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v295);
LABEL_556:
          SharedRefPtr<ClockVector>::~SharedRefPtr<ClockVector>(&v284);
          goto LABEL_79;
        }
        v270 = Vector<SharedRefPtr<Legacy::Override>,1>::IncreaseCapacity(&v302, (unsigned int)(2 * HIDWORD(v286)));
        v266 = v302;
        v3 = v270;
        v259 = v304;
        v292 = v303;
        v286 = v302;
      }
      else
      {
        v260 = 8LL * v292;
        v261 = v292;
        if ( !is_mul_ok(v292, 8u) )
          v260 = -1;
        v136 = __CFADD__(v260, 8);
        v262 = v260 + 8;
        if ( v136 )
          v262 = -1;
        v263 = HeapAlloc(hHeap, 0, v262);
        v275 = v49;
        v264 = v263;
        if ( v263 )
        {
          *v263 = v261;
          for ( k = (char *)(v263 + 1); v261; --v261 )
          {
            SharedRefPtr<Legacy::Override>::`default constructor closure'(k);
            k += 8;
          }
          v259 = v264 + 1;
        }
        else
        {
          v259 = 0;
        }
        v265 = HIDWORD(v286);
        v266 = v286;
        v3 = -2147024882;
        if ( v259 )
          v265 = v292;
        v304 = v259;
        HIDWORD(v286) = v265;
        if ( v259 )
          v3 = 0;
        HIDWORD(v302) = v265;
      }
      v113 = v275;
      v298 = v259;
      v267 = v3 == 0;
      if ( v3 < 0 )
        goto LABEL_512;
      goto LABEL_507;
    }
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
    v246 = *((_QWORD *)v46 + 38);
    v186 = (_DWORD *)((char *)v46 + 272);
    v287 = *((_DWORD *)v46 + 68);
    v280 = (unsigned int *)((char *)v46 + 272);
    if ( v246 )
    {
      v172 = *(unsigned int *)(v40 + 56);
      v247 = *((unsigned int *)v46 + 74);
      if ( (_DWORD)v172 == -1 )
      {
        v248 = *(_DWORD *)(v40 + 28);
        v249 = v248 ^ (*(_DWORD *)(v40 + 36) >> 1) & 1;
        if ( v248 )
        {
          for ( m = 0; m < v248; ++m )
          {
            v251 = m;
            v249 = *(_DWORD *)(16 * v251 + *(_QWORD *)(v40 + 40))
                 ^ *(_QWORD *)(16 * v251 + *(_QWORD *)(v40 + 40) + 8)
                 ^ (32 * v249)
                 ^ (v249 >> 27)
                 ^ HIDWORD(*(_QWORD *)(16 * v251 + *(_QWORD *)(v40 + 40) + 8));
          }
        }
        v172 = 0x7FFFFFFF;
        if ( v249 != -1 )
          v172 = v249;
        *(_DWORD *)(v40 + 56) = v172;
      }
      v158 = 0;
      v159 = (((unsigned int)v172 >> 5) + 1) % ((int)v247 - 1) + 1;
      while ( v158 < (unsigned int)v247 )
      {
        v160 = v172 % v247;
        v161 = v160;
        v162 = *(_BYTE *)(v246 + 24 * v160 + 16);
        if ( (v162 & 1) != 0 )
        {
          v163 = *(_QWORD *)(v246 + 24 * v160);
          if ( v163 == v40 )
            goto LABEL_330;
          v164 = *(_DWORD *)(v163 + 28);
          if ( v164 == *(_DWORD *)(v40 + 28) )
          {
            v165 = *(_DWORD *)(v40 + 36);
            v166 = *(_DWORD *)(v163 + 36);
            v167 = (v166 >> 1) & 1;
            if ( v167 == ((v165 >> 1) & 1)
              && *(_DWORD *)(v163 + 32) == *(_DWORD *)(v40 + 32)
              && (((unsigned __int8)v165 ^ (unsigned __int8)v166) & 4) == 0 )
            {
              for ( n = 0; (unsigned int)n < v164; n = (unsigned int)(n + 1) )
              {
                v169 = 16LL * (unsigned int)n;
                v170 = v169 + *(_QWORD *)(v163 + 40);
                v171 = *(_QWORD *)(v40 + 40) + v169;
                if ( *(_DWORD *)v170 != *(_DWORD *)v171 )
                  goto LABEL_329;
                if ( *(_QWORD *)(v170 + 8) != *(_QWORD *)(v171 + 8) )
                  goto LABEL_329;
                if ( v167 )
                {
                  v240 = 12 * n + *(_QWORD *)(v163 + 48);
                  v241 = *(_QWORD *)(v40 + 48) + 12 * n;
                  if ( *(_DWORD *)v240 != *(_DWORD *)v241
                    || *(_DWORD *)(v240 + 4) != *(_DWORD *)(v241 + 4)
                    || *(_BYTE *)(v240 + 8) != *(_BYTE *)(v241 + 8) )
                  {
                    goto LABEL_329;
                  }
                }
              }
LABEL_330:
              v173 = this;
              v3 = 0;
              v344 = *(_DWORD *)(*((_QWORD *)this + 38) + 24LL * (unsigned int)v161 + 8);
LABEL_351:
              if ( *((_DWORD *)v173 + 68) != v287 )
                *((_DWORD *)v173 + 66) = -1;
              goto LABEL_353;
            }
          }
        }
        else if ( (v162 & 2) == 0 )
        {
          break;
        }
LABEL_329:
        v172 = v159 + v161;
        ++v158;
      }
      v186 = v280;
    }
    v187 = *(_DWORD *)(v40 + 56);
    v188 = v186 + 6;
    v189 = *v186;
    v344 = 0;
    LODWORD(v343) = v189;
    v278 = v187;
    if ( v187 == -1 )
    {
      v199 = *(_DWORD *)(v40 + 28);
      v200 = v199 ^ (*(_DWORD *)(v40 + 36) >> 1) & 1;
      if ( v199 )
      {
        for ( ii = 0; ii < v199; ++ii )
        {
          v202 = ii;
          v200 = *(_DWORD *)(16 * v202 + *(_QWORD *)(v40 + 40))
               ^ *(_QWORD *)(16 * v202 + *(_QWORD *)(v40 + 40) + 8)
               ^ (32 * v200)
               ^ (v200 >> 27)
               ^ HIDWORD(*(_QWORD *)(16 * v202 + *(_QWORD *)(v40 + 40) + 8));
        }
      }
      v187 = 0x7FFFFFFF;
      if ( v200 != -1 )
        v187 = v200;
      v278 = v187;
      *(_DWORD *)(v40 + 56) = v187;
    }
    v190 = (struct SyncId *)*((_QWORD *)v188 + 1);
    v283 = v190;
    if ( !v190 )
    {
      v191 = *v188;
      v192 = 24 * v191;
      if ( !is_mul_ok(v191, 0x18u) )
        v192 = -1;
      v136 = __CFADD__(v192, 8);
      v193 = v192 + 8;
      if ( v136 )
        v193 = -1;
      v194 = HeapAlloc(hHeap, 0, v193);
      if ( v194 )
      {
        *v194 = v191;
        v195 = v194 + 1;
        for ( jj = (char *)(v194 + 1); v191; --v191 )
        {
          TableBucket<SharedRefPtr<RangeSet>,unsigned long,SimpleHashTableContext>::TableBucket<SharedRefPtr<RangeSet>,unsigned long,SimpleHashTableContext>(jj);
          jj += 24;
        }
        *((_QWORD *)v188 + 1) = v195;
        if ( v195 )
        {
          v197 = v280;
          v198 = v275;
LABEL_428:
          v227 = *v188;
          v228 = *((_QWORD *)v188 + 1);
          v229 = v278;
          for ( kk = 0; ; ++kk )
          {
            if ( kk >= (unsigned int)v227 )
            {
              v3 = -2147418113;
              goto LABEL_353;
            }
            v231 = v229 % v227;
            v232 = v228 + 24 * (v229 % v227);
            v233 = *(_BYTE *)(v232 + 16);
            if ( (v233 & 1) == 0 )
              break;
            *(_BYTE *)(v232 + 16) = v233 | 2;
            v229 = v231 + ((v278 >> 5) + 1) % ((int)v227 - 1) + 1;
          }
          v174 = (__int64 *)(*((_QWORD *)v188 + 1) + 24LL * (unsigned int)v231);
          if ( v40 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 8LL))(v40);
          if ( v174 == (__int64 *)&v338 )
          {
            if ( v40 )
              goto LABEL_338;
          }
          else
          {
            if ( *v174 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)*v174 + 16LL))(*v174);
            *v174 = v40;
            if ( v40 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 8LL))(v40);
LABEL_338:
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
            }
          }
          *((_BYTE *)v174 + 16) |= 1u;
          v3 = 0;
          *((_DWORD *)v174 + 2) = v189;
          ++v188[4];
          if ( *((_QWORD *)v197 + 2) )
          {
            v175 = v197[1];
            if ( *v197 + 1 > v175 )
            {
              v275 = v198;
              v3 = Vector<SharedRefPtr<ClockVector>,1>::IncreaseCapacity(v197, 2 * v175);
              if ( v3 < 0 )
                goto LABEL_347;
            }
            else
            {
              v275 = v198;
            }
LABEL_342:
            v176 = *v197;
            v177 = (__int64 *)(*((_QWORD *)v197 + 2) + 8 * v176);
            *v197 = v176 + 1;
            if ( v177 != &v284 )
            {
              if ( *v177 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)*v177 + 16LL))(*v177);
              *v177 = v40;
              if ( v40 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 8LL))(v40);
            }
LABEL_347:
            if ( !v3 )
            {
              v344 = *v197 - 1;
LABEL_349:
              if ( v3 )
                goto LABEL_353;
              v173 = this;
              goto LABEL_351;
            }
LABEL_458:
            HashTable<SharedRefPtr<ClockVector>,unsigned long,SimpleHashTableContext>::RemoveItem(v188, &v284);
            goto LABEL_349;
          }
          v234 = v197[2];
          v235 = 8 * v234;
          if ( !is_mul_ok(v234, 8u) )
            v235 = -1;
          v136 = __CFADD__(v235, 8);
          v236 = v235 + 8;
          if ( v136 )
            v236 = -1;
          v237 = HeapAlloc(hHeap, 0, v236);
          if ( v237 )
          {
            *v237 = v234;
            v238 = v237 + 1;
            for ( mm = (char *)(v237 + 1); v234; --v234 )
            {
              SharedRefPtr<Legacy::Override>::`default constructor closure'(mm);
              mm += 8;
            }
            v197 = v280;
            *((_QWORD *)v280 + 2) = v238;
            if ( v238 )
            {
              v280[1] = v280[2];
              goto LABEL_342;
            }
          }
          else
          {
            *((_QWORD *)v197 + 2) = 0;
            v275 = v198;
          }
          v3 = -2147024882;
          goto LABEL_458;
        }
      }
      else
      {
        *((_QWORD *)v188 + 1) = 0;
      }
      v3 = -2147024882;
      goto LABEL_353;
    }
    v203 = *v188;
    v204 = v187;
    v205 = 0;
    v206 = ((v187 >> 5) + 1) % ((int)v203 - 1) + 1;
    while ( 1 )
    {
      if ( v205 >= (unsigned int)v203 )
      {
LABEL_425:
        v197 = v280;
        v226 = v280[6];
        v188 = v280 + 6;
        if ( v280[10] + 1 > 72 * v226 / 0x64 )
        {
          NextPrimeNumber = GetNextPrimeNumber(2 * v226);
          v3 = HashTable<SharedRefPtr<ClockVector>,unsigned long,SimpleHashTableContext>::Resize(v188, NextPrimeNumber);
          v198 = v275;
          if ( v3 < 0 )
            goto LABEL_353;
        }
        else
        {
          v198 = v275;
        }
        v189 = (int)v343;
        goto LABEL_428;
      }
      v207 = v204 % v203;
      v208 = v207;
      v209 = *((_BYTE *)v190 + 24 * v207 + 16);
      if ( (v209 & 1) != 0 )
        break;
      if ( (v209 & 2) == 0 )
        goto LABEL_425;
LABEL_408:
      v204 = v206 + v208;
      ++v205;
    }
    v210 = *((_QWORD *)v190 + 3 * v207);
    if ( v210 == v40 )
      goto LABEL_433;
    v211 = *(_DWORD *)(v210 + 28);
    if ( v211 != *(_DWORD *)(v40 + 28) )
      goto LABEL_408;
    v212 = *(_DWORD *)(v210 + 36);
    v213 = *(_DWORD *)(v40 + 36);
    if ( (((unsigned __int8)v213 ^ *(_BYTE *)(v210 + 36)) & 2) != 0
      || *(_DWORD *)(v210 + 32) != *(_DWORD *)(v40 + 32)
      || (((unsigned __int8)v213 ^ (unsigned __int8)v212) & 4) != 0 )
    {
      goto LABEL_408;
    }
    for ( nn = 0; (unsigned int)nn < v211; nn = (unsigned int)(nn + 1) )
    {
      v215 = *(_QWORD *)(v40 + 40);
      v216 = *(_QWORD *)(v210 + 40);
      if ( *(_DWORD *)(v216 + 16LL * (unsigned int)nn) == *(_DWORD *)(v215 + 16LL * (unsigned int)nn)
        && *(_QWORD *)(v216 + 16LL * (unsigned int)nn + 8) == *(_QWORD *)(v215 + 16LL * (unsigned int)nn + 8) )
      {
        if ( (v212 & 2) == 0 )
          continue;
        v243 = *(_QWORD *)(v40 + 48);
        v244 = *(_QWORD *)(v210 + 48);
        v245 = 12 * nn;
        if ( *(_DWORD *)(v244 + 12 * nn) == *(_DWORD *)(v243 + 12 * nn)
          && *(_DWORD *)(v244 + v245 + 4) == *(_DWORD *)(v243 + v245 + 4)
          && *(_BYTE *)(v244 + v245 + 8) == *(_BYTE *)(v243 + v245 + 8) )
        {
          continue;
        }
      }
      v190 = v283;
      goto LABEL_408;
    }
LABEL_433:
    v3 = -2147024809;
LABEL_353:
    v178 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_e65626ae806d36e8966776faf765a664_Traceguids,
        (unsigned int)"ClockVectorManager::FindByKeyOrAdd",
        v3);
      v178 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v3 )
      goto LABEL_555;
    v179 = v293;
    v180 = v293 + *((_QWORD *)v285 + 3);
    if ( v178 != &WPP_GLOBAL_Control && (*((_BYTE *)v178 + 28) & 1) != 0 && *((_BYTE *)v178 + 25) >= 5u )
      WPP_SF_s(
        v178[2],
        10,
        WPP_e65626ae806d36e8966776faf765a664_Traceguids,
        "Legacy::Override::InitializeAsItemOverride");
    v181 = v275;
    *(_DWORD *)(v275 + 44) = 1;
    if ( v275 + 48 != v180 )
    {
      if ( (*(_DWORD *)(v275 + 52) & 0x20000) == 0 )
      {
        v182 = *(volatile signed __int32 **)(v275 + 56);
        if ( v182 )
        {
          if ( _InterlockedExchangeAdd(v182, 0xFFFFFFFF) == 1 )
          {
            SeFree(*(void **)(v275 + 56));
            *(_QWORD *)(v275 + 56) = 0;
          }
        }
      }
      *(_DWORD *)(v275 + 52) = *(_DWORD *)(v180 + 4);
      v183 = *(volatile signed __int32 **)(v180 + 8);
      *(_QWORD *)(v275 + 56) = v183;
      if ( v183 )
        _InterlockedIncrement(v183);
    }
    v184 = (__int64 *)(v275 + 80);
    if ( (__int64 *)(v275 + 80) != &v284 )
    {
      if ( *v184 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)*v184 + 16LL))(*v184);
      *v184 = v40;
      if ( v40 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 8LL))(v40);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_e65626ae806d36e8966776faf765a664_Traceguids,
        (unsigned int)"Legacy::Override::InitializeAsItemOverride",
        0);
    }
    v81 = v291;
    if ( !v291 )
    {
      v185 = HeapAlloc(hHeap, 0, 0x88u);
      if ( v185 )
      {
        v81 = v185 + 1;
        *v185 = 16;
        v157 = 16;
        v291 = v185 + 1;
        v156 = (char *)(v185 + 1);
        do
        {
          SharedRefPtr<Legacy::Override>::`default constructor closure'(v156);
          v156 += 8;
          --v157;
        }
        while ( v157 );
      }
      else
      {
        v81 = 0;
        v291 = 0;
      }
      v82 = v276;
      v307 = v81;
      if ( v81 )
        v82 = 16;
      v3 = -2147024882;
      v276 = v82;
      HIDWORD(v305) = v82;
      if ( v81 )
        v3 = 0;
      goto LABEL_140;
    }
    v3 = 0;
    if ( v277 + 1 <= v276 )
      goto LABEL_141;
    v217 = 2 * v276;
    v218 = 2 * v276;
    v219 = 8 * v218;
    if ( !is_mul_ok(v218, 8u) )
      v219 = -1;
    v136 = __CFADD__(v219, 8);
    v220 = v219 + 8;
    if ( v136 )
      v220 = -1;
    v221 = HeapAlloc(hHeap, 0, v220);
    if ( !v221 )
      goto LABEL_434;
    *v221 = v217;
    v222 = v221 + 1;
    v223 = (char *)(v221 + 1);
    if ( v217 )
    {
      do
      {
        SharedRefPtr<Legacy::Override>::`default constructor closure'(v223);
        v223 += 8;
        --v218;
      }
      while ( v218 );
    }
    if ( v222 )
    {
      v224 = v291;
      v225 = 0;
      v276 *= 2;
      if ( v277 )
      {
        do
        {
          SharedRefPtr<IClockVector>::operator=(&v222[v225], &v224[v225]);
          v225 = (unsigned int)(v225 + 1);
        }
        while ( (unsigned int)v225 < v277 );
        v179 = v293;
      }
      HIDWORD(v305) = v217;
      if ( v224 )
        SharedRefPtr<ChangeUnitChangeWrapper>::`vector deleting destructor'(v224);
      v81 = v222;
      v291 = v222;
      v307 = v222;
    }
    else
    {
LABEL_434:
      v81 = v291;
      v3 = -2147024882;
    }
    v181 = v275;
LABEL_140:
    v83 = v3 == 0;
    if ( v3 >= 0 )
    {
LABEL_141:
      v84 = &v81[v277++];
      LODWORD(v305) = v277;
      if ( v84 != &v295 )
      {
        if ( *v84 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)*v84 + 16LL))(*v84);
        *v84 = v181;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v181 + 8LL))(v181);
      }
      v83 = v3 == 0;
    }
    if ( !v83 )
      goto LABEL_555;
    v85 = (unsigned int *)((char *)this + 336);
    v86 = (struct SyncId *)(*((_QWORD *)v285 + 3) + v179);
    v282 = v86;
    LODWORD(v87) = *((_DWORD *)v86 + 1);
    v88 = (unsigned int)v87 & 0x20000;
    LODWORD(v343) = (unsigned int)v87 & 0x20000;
    if ( ((unsigned int)v87 & 0x10000) != 0 )
    {
      v87 = (_WORD *)*((_QWORD *)v86 + 1);
      if ( !v88 )
        v87 += 2;
      LOWORD(v87) = *v87;
    }
    v89 = (unsigned __int8 *)*((_QWORD *)v86 + 1);
    v293 = (__int64)v89;
    v90 = (unsigned __int16)v87;
    if ( !v88 )
      v89 += 4;
    for ( i1 = &v89[(unsigned __int16)v87]; v89 < i1; ++v89 )
      v90 = *v89 ^ (v90 << 8) ^ HIBYTE(v90);
    v92 = *((_QWORD *)this + 43);
    if ( v92 )
    {
      v93 = *v85;
      v94 = v90;
      v287 = ((v90 >> 5) + 1) % ((int)v93 - 1) + 1;
      for ( i2 = 0; ; ++i2 )
      {
        if ( i2 >= (unsigned int)v93 )
        {
LABEL_157:
          v86 = v282;
          v85 = (unsigned int *)((char *)this + 336);
          break;
        }
        v96 = v94 % v93;
        v97 = v92 + 40 * v96;
        v98 = *(_BYTE *)(v97 + 32);
        if ( (v98 & 1) != 0 )
        {
          v115 = *(_BYTE **)(v97 + 8);
          v116 = (_BYTE *)v293;
          v117 = v115;
          v118 = *(_DWORD *)(v97 + 4);
          if ( (v118 & 0x20000) == 0 )
            v117 = v115 + 4;
          if ( !v88 )
            v116 = (_BYTE *)(v293 + 4);
          if ( v117 == v116 )
            goto LABEL_235;
          if ( (v118 & 0x10000) == 0 )
          {
            if ( (((unsigned __int8)v116 | (unsigned __int8)v117) & 3) != 0 )
            {
              v120 = &v117[(unsigned __int16)v118];
              while ( v117 < v120 )
              {
                if ( *v117 != *v116 )
                  goto LABEL_205;
                ++v117;
                ++v116;
              }
            }
            else
            {
              v119 = &v117[4 * ((unsigned __int64)(unsigned __int16)v118 >> 2)];
              while ( v117 < v119 )
              {
                if ( *(_DWORD *)v117 != *(_DWORD *)v116 )
                  goto LABEL_205;
                v117 += 4;
                v116 += 4;
              }
              if ( (v118 & 3) != 0 )
              {
                if ( (v118 & 0x20000) == 0 )
                  v115 += 4;
                v272 = (unsigned __int64)&v115[(unsigned __int16)v118];
                while ( (unsigned __int64)v117 < v272 )
                {
                  if ( *v117 != *v116 )
                    goto LABEL_205;
                  ++v117;
                  ++v116;
                }
              }
            }
LABEL_235:
            v3 = -2147024809;
            goto LABEL_93;
          }
          if ( !(unsigned int)SyncId::Compare((const struct SyncId *)v97, v282) )
          {
            v3 = -2147024809;
            goto LABEL_93;
          }
LABEL_205:
          v88 = (unsigned int)v343;
        }
        else if ( (v98 & 2) == 0 )
        {
          goto LABEL_157;
        }
        v94 = v287 + v96;
      }
    }
    v99 = *v85;
    if ( !v92 )
    {
      v134 = *v85;
      v135 = 40 * v134;
      if ( !is_mul_ok(v99, 0x28u) )
        v135 = -1;
      v136 = __CFADD__(v135, 8);
      v137 = v135 + 8;
      if ( v136 )
        v137 = -1;
      v138 = HeapAlloc(hHeap, 0, v137);
      if ( v138 )
      {
        *v138 = v134;
        v139 = v138 + 1;
        for ( i3 = v138 + 1; v134; --v134 )
        {
          TableBucket<SyncId,Legacy::KnowledgeInspector::ItemData,SimpleHashTableContext>::TableBucket<SyncId,Legacy::KnowledgeInspector::ItemData,SimpleHashTableContext>(i3);
          i3 += 5;
        }
      }
      else
      {
        v139 = 0;
      }
      v3 = -2147024882;
      *((_QWORD *)this + 43) = v139;
      v83 = v139 == 0;
      v85 = (unsigned int *)((char *)this + 336);
      if ( !v83 )
        v3 = 0;
      goto LABEL_247;
    }
    if ( v85[4] + 1 <= 72 * (int)v99 / 0x64u )
    {
LABEL_160:
      v100 = *v85;
      v101 = *((_QWORD *)v85 + 1);
      v102 = v90;
      for ( i4 = 0; ; ++i4 )
      {
        if ( i4 >= (unsigned int)v100 )
        {
          v3 = -2147418113;
          goto LABEL_93;
        }
        v104 = v102 % v100;
        v105 = v101 + 40 * (v102 % v100);
        v106 = *(_BYTE *)(v105 + 32);
        if ( (v106 & 1) == 0 )
          break;
        *(_BYTE *)(v105 + 32) = v106 | 2;
        v102 = v104 + ((v90 >> 5) + 1) % ((int)v100 - 1) + 1;
      }
      v107 = (volatile signed __int32 *)*((_QWORD *)v86 + 1);
      v108 = *((_DWORD *)v86 + 1);
      v109 = *((_QWORD *)v85 + 1) + 40LL * (unsigned int)v104;
      if ( v107 )
        _InterlockedIncrement(v107);
      if ( (char *)v109 == &v341 )
      {
LABEL_172:
        v111 = v107;
      }
      else
      {
        if ( (*(_DWORD *)(v109 + 4) & 0x20000) == 0 )
        {
          v110 = *(volatile signed __int32 **)(v109 + 8);
          if ( v110 )
          {
            if ( _InterlockedExchangeAdd(v110, 0xFFFFFFFF) == 1 )
              SeFree(*(void **)(v109 + 8));
          }
        }
        *(_DWORD *)(v109 + 4) = v108;
        *(_QWORD *)(v109 + 8) = v107;
        if ( v107 )
        {
          _InterlockedIncrement(v107);
          goto LABEL_172;
        }
        v111 = 0;
      }
      if ( (v108 & 0x20000) == 0 && v111 && _InterlockedExchangeAdd(v111, 0xFFFFFFFF) == 1 )
        SeFree((void *)v107);
      if ( &v339 != (char *)(v109 + 16) )
        *(_DWORD *)(v109 + 16) = v344;
      v112 = (void **)(v109 + 24);
      if ( (char *)(v109 + 24) != &v340 )
      {
        if ( *v112 )
          RefCountedHashTable<SyncId,unsigned long>::Release(*v112);
        *v112 = 0;
      }
      *(_BYTE *)(v109 + 32) |= 1u;
      ++v85[4];
      v113 = v275;
      v3 = 0;
LABEL_184:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v113 + 16LL))(v113);
LABEL_185:
      v9 = ++v345;
      if ( v40 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
        v9 = v345;
      }
      v8 = v285;
      if ( (v289 & 0x20000) == 0 )
      {
        v114 = v290;
        if ( v290 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v290, 0xFFFFFFFF) == 1 )
          {
            SeFree(v114);
            v9 = v345;
            v290 = 0;
          }
        }
      }
      continue;
    }
    break;
  }
  v151 = GetNextPrimeNumber(2 * v99);
  v3 = HashTable<SyncId,Legacy::KnowledgeInspector::ItemData,SimpleHashTableContext>::Resize(v85, v151);
LABEL_247:
  if ( v3 >= 0 )
    goto LABEL_160;
LABEL_93:
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v295);
  SharedRefPtr<ClockVector>::~SharedRefPtr<ClockVector>(&v284);
  SyncId::~SyncId((SyncId *)v288);
LABEL_94:
  v5 = v276;
  v7 = v291;
LABEL_95:
  v50 = 0;
  v343 = 0;
  if ( v3 || (v53 = RangeSetManager::FindByIndex(*(_QWORD *)this + 184LL, 0, &v343), v50 = v343, (v3 = v53) != 0) )
  {
    v56 = v296;
LABEL_100:
    Legacy::OverrideEnumerator::OverrideEnumerator((Legacy::OverrideEnumerator *)v313);
    if ( v3 )
      goto LABEL_82;
    TraceKnowledgeFunctionEnter("Legacy::OverrideEnumerator::InitializeByConsumingOverrideVector");
    v305 = v314;
    v306 = v315;
    v307 = v316;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_e65626ae806d36e8966776faf765a664_Traceguids,
        (unsigned int)"Legacy::OverrideEnumerator::InitializeByConsumingOverrideVector",
        0);
    }
    Legacy::OverrideEnumerator::OverrideEnumerator((Legacy::OverrideEnumerator *)v323);
    TraceKnowledgeFunctionEnter("Legacy::OverrideEnumerator::InitializeByConsumingOverrideVector");
    v308[0] = v324;
    LODWORD(v308[1]) = v325;
    v309 = v326;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_e65626ae806d36e8966776faf765a664_Traceguids,
        (unsigned int)"Legacy::OverrideEnumerator::InitializeByConsumingOverrideVector",
        0);
    }
    Legacy::OverrideEnumerator::OverrideEnumerator((Legacy::OverrideEnumerator *)v318);
    TraceKnowledgeFunctionEnter("Legacy::OverrideEnumerator::InitializeByConsumingOverrideVector");
    v302 = v319;
    v303 = v320;
    v304 = v321;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_e65626ae806d36e8966776faf765a664_Traceguids,
        (unsigned int)"Legacy::OverrideEnumerator::InitializeByConsumingOverrideVector",
        0);
    }
    v3 = 0;
    v57 = *((_DWORD *)this + 16);
    *((_DWORD *)this + 16) = v277;
    LODWORD(v314) = v57;
    v58 = *((_DWORD *)this + 17);
    *((_DWORD *)this + 17) = v5;
    HIDWORD(v314) = v58;
    v59 = *((_DWORD *)this + 18);
    *((_DWORD *)this + 18) = 16;
    v315 = v59;
    v316 = (_QWORD *)*((_QWORD *)this + 10);
    *((_QWORD *)this + 10) = v7;
    v60 = *((_DWORD *)this + 22);
    if ( v317 != (_DWORD *)((char *)this + 88) )
      *((_DWORD *)this + 22) = 0;
    v61 = *((_DWORD *)this + 23);
    *((_DWORD *)this + 23) = 1;
    v317[1] = v61;
    v62 = *((_DWORD *)this + 36);
    *((_DWORD *)this + 36) = v56;
    LODWORD(v324) = v62;
    v63 = *((_DWORD *)this + 37);
    v317[0] = v60;
    *((_DWORD *)this + 37) = v297;
    HIDWORD(v324) = v63;
    v64 = *((_DWORD *)this + 38);
    *((_DWORD *)this + 38) = HIDWORD(v297);
    v325 = v64;
    v326 = *((_QWORD *)this + 20);
    *((_QWORD *)this + 20) = v312;
    v65 = *((_DWORD *)this + 42);
    if ( v327 != (_DWORD *)((char *)this + 168) )
      *((_DWORD *)this + 42) = 0;
    v66 = *((_DWORD *)this + 43);
    *((_DWORD *)this + 43) = 2;
    v327[1] = v66;
    v67 = *((_DWORD *)this + 56);
    v327[0] = v65;
    *((_DWORD *)this + 56) = v286;
    LODWORD(v319) = v67;
    v68 = *((_DWORD *)this + 57);
    *((_DWORD *)this + 57) = HIDWORD(v286);
    HIDWORD(v319) = v68;
    v69 = *((_DWORD *)this + 58);
    *((_DWORD *)this + 58) = v292;
    v320 = v69;
    v321 = (_QWORD *)*((_QWORD *)this + 30);
    *((_QWORD *)this + 30) = v298;
    v70 = *((_DWORD *)this + 62);
    if ( v322 != (_DWORD *)((char *)this + 248) )
      *((_DWORD *)this + 62) = 0;
    v71 = *((_DWORD *)this + 63);
    *((_DWORD *)this + 63) = 3;
    v322[1] = v71;
    v322[0] = v70;
  }
  else
  {
    v54 = *(_QWORD *)this;
    for ( i5 = 0; ; i5 = (unsigned int)(i5 + 1) )
    {
      if ( (unsigned int)i5 >= *(_DWORD *)(v54 + 80) )
      {
        v56 = v308[0];
        v7 = v291;
        v312 = v309;
        v297 = *(_QWORD *)((char *)v308 + 4);
        goto LABEL_100;
      }
      v274 = *(_QWORD *)(v54 + 96);
      v343 = 0;
      v3 = RangeSetManager::FindByIndex(*(_QWORD *)this + 184LL, *(unsigned int *)(24 * i5 + v274 + 16), &v343);
      if ( v3 )
        break;
      v331 = 0;
      v332 = 0;
      v333 = 0;
      v334 = 0;
      v335 = 0;
      v336 = 0;
      RangeSetDoubleIterator::StartFromBeginning((RangeSetDoubleIterator *)v330, v343, v50);
      v3 = Legacy::KnowledgeInspector::CaptureChangeUnitOverridesForSingleColumn(
             this,
             v330,
             24 * i5 + *(_QWORD *)(v54 + 96),
             v308);
      if ( v3 )
      {
        SyncId::~SyncId((SyncId *)v330);
        break;
      }
      SyncId::~SyncId((SyncId *)v330);
      TableBucket<SharedRefPtr<RangeSet>,unsigned long,SimpleHashTableContext>::~TableBucket<SharedRefPtr<RangeSet>,unsigned long,SimpleHashTableContext>((_DWORD **)&v343);
    }
    TableBucket<SharedRefPtr<RangeSet>,unsigned long,SimpleHashTableContext>::~TableBucket<SharedRefPtr<RangeSet>,unsigned long,SimpleHashTableContext>((_DWORD **)&v343);
LABEL_81:
    Legacy::OverrideEnumerator::OverrideEnumerator((Legacy::OverrideEnumerator *)v313);
LABEL_82:
    Legacy::OverrideEnumerator::OverrideEnumerator((Legacy::OverrideEnumerator *)v323);
    Legacy::OverrideEnumerator::OverrideEnumerator((Legacy::OverrideEnumerator *)v318);
    ClockVectorManager::Recycle((Legacy::KnowledgeInspector *)((char *)this + 256));
    HashTable<SyncId,Legacy::KnowledgeInspector::ItemData,SimpleHashTableContext>::FreeHashTable((char *)this + 336);
    *((_DWORD *)this + 84) = GetNextPrimeNumber(0xBu);
  }
  Vector<SharedRefPtr<Legacy::Override>,1>::~Vector<SharedRefPtr<Legacy::Override>,1>(&v319);
  _InterlockedDecrement(&g_cRefThisDll);
  Vector<SharedRefPtr<Legacy::Override>,1>::~Vector<SharedRefPtr<Legacy::Override>,1>(&v324);
  _InterlockedDecrement(&g_cRefThisDll);
  Vector<SharedRefPtr<Legacy::Override>,1>::~Vector<SharedRefPtr<Legacy::Override>,1>(&v314);
  _InterlockedDecrement(&g_cRefThisDll);
  if ( v50 )
    RangeSet::Release(v50);
  if ( v285 )
    RangeSet::Release(v285);
  Vector<SharedRefPtr<Legacy::Override>,1>::~Vector<SharedRefPtr<Legacy::Override>,1>(v308);
  Vector<SharedRefPtr<Legacy::Override>,1>::~Vector<SharedRefPtr<Legacy::Override>,1>(&v302);
  Vector<SharedRefPtr<Legacy::Override>,1>::~Vector<SharedRefPtr<Legacy::Override>,1>(&v305);
  v2 = (PVOID *)WPP_GLOBAL_Control;
LABEL_119:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x40) != 0 && *((_BYTE *)v2 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v2[2],
      13,
      (unsigned int)WPP_48b71e9a06de38317ed143d1f750f029_Traceguids,
      (unsigned int)"Legacy::KnowledgeInspector::EnsureCachesUpToDate",
      v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180003830  mov     rax, rsp
0x180003833  mov     [rax+8], rcx
0x180003837  push    rbp
0x180003838  push    r13
0x18000383a  lea     rbp, [rax-1E8h]
0x180003841  sub     rsp, 2D8h
0x180003848  mov     [rax-18h], rbx
0x18000384c  mov     rbx, rcx
0x18000384f  mov     [rax-40h], r15
0x180003853  mov     rcx, cs:WPP_GLOBAL_Control
0x18000385a  lea     r15, WPP_GLOBAL_Control
0x180003861  cmp     rcx, r15
0x180003864  jz      short loc_180003870
0x180003866  test    byte ptr [rcx+1Ch], 40h
0x18000386a  jnz     loc_180005940
0x180003870  xor     r13d, r13d
0x180003873  cmp     [rbx+8], r13
0x180003877  jnz     short loc_180003893
0x180003879  mov     rcx, rbx; this
0x18000387c  call    ?EnsureCachedScopeVector@KnowledgeInspector@Legacy@@AEAAJXZ; Legacy::KnowledgeInspector::EnsureCachedScopeVector(void)
0x180003881  mov     rcx, cs:WPP_GLOBAL_Control
0x180003888  mov     r13d, eax
0x18000388b  test    eax, eax
0x18000388d  jnz     loc_180004200
0x180003893  cmp     dword ptr [rbx+58h], 0FFFFFFFFh
0x180003897  jnz     loc_180004200
0x18000389d  xor     eax, eax
0x18000389f  mov     [rsp+2E0h+var_18], rsi
0x1800038a7  mov     ecx, 10h
0x1800038ac  mov     [rsp+2E0h+var_28], r12
0x1800038b4  mov     [rbp+1E0h+var_1E8], ecx
0x1800038b7  lea     r8, [rsp+2E0h+var_280]
0x1800038bc  mov     [rbp+1E0h+var_250], ecx
0x1800038bf  xor     esi, esi
0x1800038c1  mov     [rbp+1E0h+var_200], ecx
0x1800038c4  xor     r12d, r12d
0x1800038c7  mov     dword ptr [rbp+1E0h+var_22C+4], ecx
0x1800038ca  xor     edx, edx
0x1800038cc  mov     dword ptr [rbp+1E0h+var_1D8+8], ecx
0x1800038cf  mov     rcx, [rbx]
0x1800038d2  mov     [rsp+2E0h+var_30], r14
0x1800038da  add     rcx, 0B8h
0x1800038e1  xor     r14d, r14d
0x1800038e4  mov     [rsp+2E0h+var_20], rdi
0x1800038ec  mov     [rsp+3Ch], eax
0x1800038f0  mov     [rbp+1E0h+var_1F0], rax
0x1800038f4  mov     [rsp+2E0h+var_2A8], r12d
0x1800038f9  mov     [rbp+1E0h+var_258], r14
0x1800038fd  mov     [rbp+1E0h+var_1E0], r14
0x180003901  mov     dword ptr [rsp+2E0h+var_278], eax
0x180003905  mov     [rbp+1E0h+var_208], rax
0x180003909  mov     dword ptr [rsp+2E0h+var_278+4], eax
0x18000390d  mov     [rbp+1E0h+var_220], rax
0x180003911  mov     [rbp+1E0h+var_1F8], rax
0x180003915  mov     [rbp+1E0h+var_230], esi
0x180003918  mov     qword ptr [rbp+1E0h+var_1D8], rsi
0x18000391c  mov     dword ptr [rbp+1E0h+var_22C], esi
0x18000391f  mov     [rbp+1E0h+var_1B8], rax
0x180003923  mov     [rbp+1E0h+var_1C8], rax
0x180003927  mov     [rsp+2E0h+var_280], rax
0x18000392c  call    ?FindByIndex@RangeSetManager@@QEBAJKAEAV?$SharedRefPtr@VRangeSet@@@@@Z; RangeSetManager::FindByIndex(ulong,SharedRefPtr<RangeSet> &)
0x180003931  mov     r13d, eax
0x180003934  test    eax, eax
0x180003936  jnz     loc_180003DA0
0x18000393c  mov     rdi, [rsp+2E0h+var_280]
0x180003941  cmp     [rdi+8], esi
0x180003944  jbe     loc_18000491A
0x18000394a  lea     rcx, [rbx+100h]; this
0x180003951  mov     edx, 4; unsigned int
0x180003956  call    ?Initialize@ClockVectorManager@@QEAAJK@Z; ClockVectorManager::Initialize(ulong)
0x18000395b  mov     r13d, eax
0x18000395e  test    eax, eax
0x180003960  jnz     loc_180003E83
0x180003966  xor     r10d, r10d
0x180003969  mov     ebx, 0FFFFh
0x18000396e  mov     [rbp+1E0h+arg_18], r10d
0x180003975  mov     r14d, 8007000Eh
0x18000397b  nop     dword ptr [rax+rax+00h]
0x180003980  mov     eax, [rdi+8]
0x180003983  cmp     r10d, eax
0x180003986  jnb     loc_180003E7A
0x18000398c  lea     ecx, [r10+1]
0x180003990  mov     [rsp+2E0h+var_264], 0
0x180003998  mov     [rbp+1E0h+var_260], 0
0x1800039a0  cmp     ecx, eax
0x1800039a2  jnb     loc_180004902
0x1800039a8  mov     rdx, [rdi+18h]
0x1800039ac  lea     r8, [rdi+18h]
0x1800039b0  lea     rcx, [rcx+rcx*2]
0x1800039b4  mov     [rsp+2E0h+var_290], r8
0x1800039b9  lea     rax, [rdx+rcx*8]
0x1800039bd  lea     rcx, [rsp+2E0h+var_268]
0x1800039c2  cmp     rcx, rax
0x1800039c5  jz      short loc_1800039E2
0x1800039c7  mov     r9, [rax+8]
0x1800039cb  mov     ecx, [rax+4]
0x1800039ce  mov     [rsp+2E0h+var_264], ecx
0x1800039d2  mov     [rbp+1E0h+var_260], r9
0x1800039d6  test    r9, r9
0x1800039d9  jz      short loc_1800039E2
0x1800039db  lock inc dword ptr [r9]
0x1800039df  mov     rdx, [r8]
0x1800039e2  mov     ecx, r10d
0x1800039e5  mov     dword ptr [rsp+2E0h+var_2A0], 1
0x1800039ed  mov     [rsp+2E0h+var_298], rcx
0x1800039f2  lea     rax, [rcx+rcx*2]
0x1800039f6  lea     rax, ds:0[rax*8]
0x1800039fe  mov     r15d, [rdx+rax+4]
0x180003a03  lea     rsi, [rdx+rax]
0x180003a07  mov     r8d, r15d
0x180003a0a  mov     [rbp+1E0h+var_248], rax
0x180003a0e  movzx   r11d, r15w
0x180003a12  and     r8d, 10000h
0x180003a19  jnz     loc_18000479A
0x180003a1f  mov     eax, r8d
0x180003a22  neg     eax
0x180003a24  sbb     dx, dx
0x180003a27  and     dx, 2
0x180003a2b  movzx   eax, dx
0x180003a2e  cmp     eax, r11d
0x180003a31  jnb     loc_180004804
0x180003a37  mov     r10, [rsi+8]
0x180003a3b  mov     r9d, r15d
0x180003a3e  and     r9d, 20000h
0x180003a45  mov     rcx, r10
0x180003a48  lea     rax, [r10+4]
0x180003a4c  cmovz   rcx, rax
0x180003a50  movzx   eax, dx
0x180003a53  cmp     byte ptr [rcx+rax], 0FFh
0x180003a57  jz      loc_1800047FC
0x180003a5d  mov     edx, r15d
0x180003a60  mov     [rsp+2E0h+var_270], 0
0x180003a68  btr     edx, 11h
0x180003a6c  mov     [rbp+1E0h+var_B8], 0
0x180003a77  mov     r12d, edx
0x180003a7a  mov     [rbp+1E0h+arg_10], edx
0x180003a80  mov     [rbp+1E0h+var_BC], edx
0x180003a86  and     r12d, 10000h
0x180003a8d  jnz     loc_1800049CE
0x180003a93  test    r8d, r8d
0x180003a96  jnz     loc_180004A86
0x180003a9c  lea     rcx, [rbp+1E0h+lpMem]
0x180003aa0  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x180003aa5  mov     rcx, cs:hHeap; hHeap
0x180003aac  xor     edx, edx; dwFlags
0x180003aae  movzx   edi, r15w
0x180003ab2  lea     r8, [rdi+7]; dwBytes
0x180003ab6  call    cs:__imp_HeapAlloc
0x180003abc  mov     r8, [rbp+1E0h+lpMem]; lpMem
0x180003ac0  mov     rbx, rax
0x180003ac3  test    r8, r8
0x180003ac6  jz      short loc_180003AD7
0x180003ac8  mov     rcx, cs:hHeap; hHeap
0x180003acf  xor     edx, edx; dwFlags
0x180003ad1  call    cs:__imp_HeapFree
0x180003ad7  xor     r13d, r13d
0x180003ada  mov     [rbp+1E0h+lpMem], rbx
0x180003ade  test    rbx, rbx
0x180003ae1  cmovz   r13d, r14d
0x180003ae5  jz      loc_1800047DF
0x180003aeb  mov     rdx, [rsi+8]
0x180003aef  lea     r14, [rbx+4]
0x180003af3  test    dword ptr [rsi+4], 20000h
0x180003afa  mov     r8, rdi; Size
0x180003afd  mov     rcx, r14; void *
0x180003b00  lea     rax, [rdx+4]
0x180003b04  cmovz   rdx, rax; Src
0x180003b08  call    memcpy_0
0x180003b0d  test    r12d, r12d
0x180003b10  jnz     loc_1800042B1
0x180003b16  lea     rcx, [rdi+3]
0x180003b1a  add     rcx, rbx
0x180003b1d  cmp     rcx, r14
0x180003b20  jb      short loc_180003B2B
0x180003b22  add     byte ptr [rcx], 1
0x180003b25  jz      loc_1800047CD
0x180003b2b  mov     r10d, [rbp+1E0h+arg_10]
0x180003b32  mov     dword ptr [rbx], 1
0x180003b38  test    r12d, r12d
0x180003b3b  jnz     loc_1800049C5
0x180003b41  mov     rsi, rbx
0x180003b44  xor     ebx, ebx
0x180003b46  mov     [rbp+1E0h+lpMem], rbx
0x180003b4a  test    rbx, rbx
0x180003b4d  jz      short loc_180003B68
0x180003b4f  mov     rcx, cs:hHeap; hHeap
0x180003b56  mov     r8, rbx; lpMem
0x180003b59  xor     edx, edx; dwFlags
0x180003b5b  call    cs:__imp_HeapFree
0x180003b61  mov     r10d, [rbp+1E0h+arg_10]
0x180003b68  test    r13d, r13d
0x180003b6b  jnz     loc_180005972
0x180003b71  mov     r11d, [rsp+2E0h+var_264]
0x180003b76  mov     edi, r11d
0x180003b79  mov     r8, [rbp+1E0h+var_260]
0x180003b7d  mov     rcx, r8
0x180003b80  and     edi, 20000h
0x180003b86  jnz     short loc_180003B8C
0x180003b88  lea     rcx, [r8+4]
0x180003b8c  mov     edx, r10d
0x180003b8f  mov     eax, r11d
0x180003b92  mov     r9, rsi
0x180003b95  and     edx, 20000h
0x180003b9b  jz      loc_18000422D
0x180003ba1  cmp     rcx, r9
0x180003ba4  jz      loc_1800046D5
0x180003baa  bt      r11d, 10h
0x180003baf  jb      loc_180004925
0x180003bb5  movzx   ebx, ax
0x180003bb8  mov     eax, ebx
0x180003bba  shr     rax, 2
0x180003bbe  lea     r11, [rcx+rax*4]
0x180003bc2  cmp     rcx, r11
0x180003bc5  jnb     short loc_180003BE0
0x180003bc7  mov     edx, [r9]
0x180003bca  mov     r8d, [rcx]
0x180003bcd  cmp     r8d, edx
0x180003bd0  jnz     loc_180003DF7
0x180003bd6  add     rcx, 4
0x180003bda  add     r9, 4
0x180003bde  jmp     short loc_180003BC2
0x180003be0  test    bl, 3
0x180003be3  jz      loc_1800046CE
0x180003be9  mov     rax, [rbp+1E0h+var_260]
0x180003bed  test    edi, edi
0x180003bef  jz      loc_1800042D9
0x180003bf5  lea     r8, [rbx+rax]
0x180003bf9  cmp     rcx, r8
0x180003bfc  jnb     loc_1800046CE
0x180003c02  movzx   eax, byte ptr [r9]
0x180003c06  cmp     [rcx], al
0x180003c08  jbe     loc_180004789
0x180003c0e  mov     r10d, [rbp+1E0h+arg_10]
0x180003c15  xor     r15d, r15d
0x180003c18  bt      r10d, 11h
0x180003c1d  jb      short loc_180003C36
0x180003c1f  test    rsi, rsi
0x180003c22  jz      short loc_180003C36
0x180003c24  mov     eax, 0FFFFFFFFh
0x180003c29  lock xadd [rsi], eax
0x180003c2d  cmp     eax, 1
0x180003c30  jz      loc_18000481B
0x180003c36  test    r13d, r13d
0x180003c39  jnz     loc_180005A8D
0x180003c3f  mov     r12d, dword ptr [rsp+2E0h+var_2A0]
0x180003c44  test    r15d, r15d
0x180003c47  jz      loc_1800046E0
0x180003c4d  mov     rbx, [rbp+1E0h+var_248]
0x180003c51  mov     rax, [rsp+2E0h+var_280]
0x180003c56  xor     edi, edi
0x180003c58  mov     rsi, [rbp+1E0h+arg_0]
0x180003c5f  mov     [rsp+2E0h+var_288], rdi
0x180003c64  mov     rax, [rax+18h]
0x180003c68  mov     rsi, [rsi]
0x180003c6b  mov     r14d, [rax+rbx+10h]
0x180003c70  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c77  lea     rax, WPP_GLOBAL_Control
0x180003c7e  cmp     rcx, rax
0x180003c81  jz      short loc_180003C8D
0x180003c83  test    byte ptr [rcx+1Ch], 1
0x180003c87  jnz     loc_180004A5B
0x180003c8d  xor     ebx, ebx
0x180003c8f  cmp     r14d, [rsi+78h]
0x180003c93  jnb     loc_1800059A4
0x180003c99  mov     rax, [rsi+88h]
0x180003ca0  xor     r13d, r13d
0x180003ca3  lea     rdi, [rax+r14*8]
0x180003ca7  lea     rax, [rbp+1E0h+var_78]
0x180003cae  cmp     rax, rdi
0x180003cb1  jz      loc_180004866
0x180003cb7  mov     rdi, [rdi]
0x180003cba  test    rdi, rdi
0x180003cbd  jz      loc_180004863
0x180003cc3  mov     rax, [rdi]
0x180003cc6  mov     rcx, rdi
0x180003cc9  mov     rax, [rax+8]
0x180003ccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cd2  mov     rax, [rdi]
0x180003cd5  mov     rcx, rdi
0x180003cd8  mov     [rsp+2E0h+var_288], rdi
0x180003cdd  mov     rax, [rax+8]
0x180003ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ce6  mov     rbx, rdi
0x180003ce9  mov     rcx, cs:WPP_GLOBAL_Control
0x180003cf0  lea     rsi, WPP_GLOBAL_Control
0x180003cf7  cmp     rcx, rsi
0x180003cfa  jz      short loc_180003D06
0x180003cfc  test    byte ptr [rcx+1Ch], 1
0x180003d00  jnz     loc_180004ABA
0x180003d06  test    rbx, rbx
0x180003d09  jz      short loc_180003D1A
0x180003d0b  mov     rax, [rbx]
0x180003d0e  mov     rcx, rbx
0x180003d11  mov     rax, [rax+10h]
0x180003d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d1a  test    r13d, r13d
0x180003d1d  jnz     loc_180005A83
0x180003d23  mov     rbx, [rbp+1E0h+arg_0]
0x180003d2a  mov     rdx, [rbx+8]
0x180003d2e  cmp     rdx, rdi
  ... truncated ...
```
