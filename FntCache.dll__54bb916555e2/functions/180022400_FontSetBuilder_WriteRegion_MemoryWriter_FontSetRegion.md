# FontSetBuilder::WriteRegion(MemoryWriter<FontSetRegion> &)

- ea: `0x180022400`
- end: `0x180023ff9`
- name: `?WriteRegion@FontSetBuilder@@QEAAXAEAV?$MemoryWriter@VFontSetRegion@@@@@Z`
- size: `7161`
- prototype: ``
- caller_count: `2`
- callee_count: `52`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180041d18`
- `0x180095970`

## callees

- `0x180004810`
- `0x180007c80`
- `0x18001713c`
- `0x18001d7e4`
- `0x18001d85c`
- `0x1800213d8`
- `0x180021474`
- `0x1800217ac`
- `0x1800217e0`
- `0x180021b80`
- `0x180021fa0`
- `0x180022400`
- `0x180024000`
- `0x180024c50`
- `0x180024c5c`
- `0x180024d2c`
- `0x1800429b0`
- `0x180048588`
- `0x18004d664`
- `0x18004e95c`
- `0x18004e9a4`
- `0x18004f1c8`
- `0x18004f93c`
- `0x18004f9f0`
- `0x180070590`
- `0x1800734d8`
- `0x180075c3c`
- `0x18007dcfc`
- `0x180087c88`
- `0x18008ebec`
- `0x18009185c`
- `0x180094f58`
- `0x180096854`
- `0x18009977c`
- `0x18009d96c`
- `0x18009e420`
- `0x1800a1b74`
- `0x1800a20d0`
- `0x1800a5454`
- `0x1800aa650`
- `0x1800aa674`
- `0x1800aaa58`
- `0x1800aaf88`
- `0x1800ab0aa`
- `0x1800ab168`
- `0x1800ab180`
- `0x1800ab468`
- `0x1800ab4dc`
- `0x1800b2f6c`
- `0x1800b447c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180023f4e`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180023f4e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180022d76`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180022f18`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002302d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002342c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002349b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800234a9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800234f7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002395d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180023a7e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180023b6e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180023e90`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180023eb9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180023f36`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180023f9f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180023fd8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180022d76`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180022f18`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002302d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002342c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002349b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800234a9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800234f7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002395d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180023a7e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180023b6e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180023e90`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180023eb9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180023f36`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180023f9f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180023fd8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800236c7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800236c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=58
void __fastcall FontSetBuilder::WriteRegion(_BYTE *a1, MemoryWriterImpl *a2)
{
  unsigned __int64 v2; // r14
  MemoryWriterImpl *v3; // r12
  _BYTE *v4; // r13
  rsize_t v5; // rdx
  char *v6; // r8
  char *v7; // r9
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rcx
  __int64 v10; // rcx
  unsigned int v11; // eax
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rbx
  __int64 v14; // rbx
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned __int64 v17; // rsi
  unsigned __int64 v18; // rdi
  rsize_t v19; // rbx
  unsigned int v20; // eax
  int v21; // ebx
  _DWORD *v22; // rax
  unsigned __int64 v23; // rax
  FontFaceKey *v24; // r15
  const char *v25; // rdx
  unsigned __int64 SerializedByteSize; // r8
  __int64 v27; // r9
  unsigned __int64 v28; // rcx
  unsigned __int64 v29; // rbx
  __int64 v30; // rbx
  unsigned int v31; // eax
  unsigned __int64 v32; // rax
  __int64 v33; // rdx
  int *v34; // r12
  int *i; // rdi
  __int64 v36; // r15
  unsigned __int64 v37; // rbx
  __int64 v38; // rdx
  __int128 *v39; // r8
  unsigned __int64 j; // rax
  _QWORD *v41; // rbx
  __int64 v42; // rcx
  __int64 v43; // rcx
  void *v44; // rcx
  const struct FontNameList *v45; // rdx
  FontNameList *v46; // rcx
  __int16 v47; // dx
  __int16 v48; // cx
  __int64 k; // r9
  __int16 v50; // dx
  const struct FontNameList *v51; // rdx
  FontNameList *v52; // rcx
  __int64 v53; // rbx
  __int64 v54; // r13
  unsigned __int64 v55; // rcx
  __int64 v56; // r9
  unsigned int v57; // eax
  unsigned __int64 v58; // rdx
  unsigned __int64 v59; // r15
  unsigned __int64 v60; // r13
  unsigned __int64 v61; // rdi
  const void *v62; // r12
  unsigned __int64 v63; // rax
  _DWORD *v64; // rax
  __int64 v65; // rdx
  _WORD *v66; // rbx
  size_t v67; // r8
  void *v68; // rcx
  char *v69; // rdx
  unsigned __int64 v70; // rcx
  size_t v71; // r8
  char *v72; // r9
  unsigned __int64 v73; // rbx
  unsigned int v74; // r10d
  unsigned __int64 v75; // rdx
  unsigned __int64 v76; // r15
  unsigned __int64 v77; // r13
  unsigned __int64 v78; // rdi
  const void *v79; // r12
  unsigned __int64 v80; // rax
  _DWORD *v81; // rax
  __int64 v82; // rdx
  _WORD *v83; // rbx
  size_t v84; // r8
  void *v85; // rcx
  unsigned __int64 v86; // rax
  int v87; // eax
  const char *v88; // rdx
  unsigned int v89; // ebx
  FontFaceKey *v90; // r15
  __int64 v91; // rbx
  __int64 v92; // rdi
  volatile signed __int32 *v93; // rcx
  unsigned int v94; // r8d
  _BYTE *v95; // rax
  __int64 v96; // rdx
  __int64 v97; // rcx
  __int64 v98; // rax
  __int64 v99; // rcx
  unsigned __int64 v100; // r10
  unsigned __int16 *v101; // r8
  unsigned int v102; // edx
  int v103; // r9d
  void *v104; // rcx
  __int64 v105; // rdx
  __int64 v106; // r8
  __int64 v107; // r9
  const void *v108; // rdi
  unsigned __int64 v109; // rcx
  unsigned int v110; // ebx
  MemoryWriterImpl *v111; // rbx
  __int64 v112; // r8
  unsigned __int64 v113; // rdx
  __int64 v114; // r8
  __int64 v115; // r9
  unsigned __int64 v116; // rcx
  unsigned __int64 v117; // rax
  unsigned __int64 v118; // rax
  __int64 v119; // rcx
  unsigned int v120; // eax
  _OWORD *v121; // rcx
  unsigned int v122; // eax
  unsigned __int64 v123; // rbx
  volatile signed __int32 *v124; // r12
  unsigned int v125; // eax
  __int64 v126; // rdx
  __int64 v127; // rax
  _DWORD *v128; // rax
  __int64 v129; // rdx
  __int64 v130; // r8
  char *v131; // r15
  _OWORD *v132; // rcx
  _OWORD *v133; // rax
  char *v134; // rcx
  unsigned int v135; // eax
  __int64 v136; // rdx
  __int64 v137; // rdx
  __int64 v138; // rcx
  __int64 v139; // r8
  __int64 m; // rax
  __int64 v141; // r13
  _QWORD *v142; // r14
  __int64 v143; // r12
  __int64 v144; // r9
  StringToIndexList *v145; // r8
  unsigned __int64 v146; // rcx
  unsigned __int64 v147; // rdx
  char *v148; // rcx
  unsigned int v149; // edi
  char *v150; // rdx
  __int64 v151; // rsi
  _DWORD *v152; // r8
  char *v153; // rcx
  const WCHAR *v154; // r10
  int v155; // eax
  const void *v156; // r15
  unsigned int v157; // ebx
  StringToIndexList *v158; // rdx
  void *v159; // rcx
  void *v160; // rcx
  void *v161; // rcx
  __int64 v162; // r15
  MemoryWriterImpl *v163; // r12
  __int64 v164; // rcx
  unsigned int v165; // edi
  unsigned __int64 v166; // r13
  unsigned __int64 v167; // r14
  __int64 v168; // rbx
  __int64 v169; // r8
  unsigned __int64 v170; // rdx
  unsigned __int64 v171; // rcx
  size_t v172; // r8
  const char *v173; // r9
  __int64 v174; // rcx
  unsigned int v175; // eax
  FontFaceKey **v176; // rcx
  size_t v177; // r8
  _BYTE *v178; // r13
  _QWORD *v179; // rbx
  _QWORD *v180; // r8
  __int64 v181; // r12
  MemoryWriterImpl *v182; // r13
  _DWORD *v183; // rax
  unsigned __int64 v184; // rbx
  unsigned int n; // edi
  _QWORD *v186; // rsi
  size_t v187; // r15
  size_t v188; // r14
  const char *v189; // rdx
  unsigned int v190; // eax
  char *v191; // rcx
  unsigned __int64 v192; // rax
  size_t v193; // rax
  __int64 v194; // rcx
  unsigned int v195; // eax
  char *v196; // r10
  const char *v197; // rdx
  unsigned int v198; // eax
  char *v199; // rcx
  const char *v200; // rdx
  void *v201; // rbx
  void *v202; // rbx
  unsigned int v203; // ecx
  __int64 v204; // rdx
  __int64 v205; // rcx
  __int64 v206; // r8
  __int64 v207; // rdx
  __int64 v208; // rcx
  __int64 v209; // r8
  _QWORD *v210; // rbx
  __int64 v211; // r8
  __int64 v212; // rdx
  __int64 v213; // rcx
  __int64 v214; // r8
  __int64 v215; // rdx
  __int64 v216; // rcx
  __int64 v217; // r8
  unsigned int v218; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v219; // [rsp+34h] [rbp-CCh]
  unsigned __int64 v220; // [rsp+38h] [rbp-C8h]
  unsigned int v221; // [rsp+40h] [rbp-C0h] BYREF
  void *Src[2]; // [rsp+48h] [rbp-B8h] BYREF
  char *v223; // [rsp+58h] [rbp-A8h]
  unsigned __int8 v224; // [rsp+60h] [rbp-A0h]
  void *v225; // [rsp+68h] [rbp-98h] BYREF
  __int128 Source; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v227; // [rsp+80h] [rbp-80h] BYREF
  MemoryWriterImpl *v228; // [rsp+88h] [rbp-78h]
  FontFaceKey *v229; // [rsp+90h] [rbp-70h]
  StringToIndexList *v230; // [rsp+98h] [rbp-68h] BYREF
  StringToIndexList *v231; // [rsp+A0h] [rbp-60h]
  StringToIndexList *v232; // [rsp+A8h] [rbp-58h]
  void *v233; // [rsp+B0h] [rbp-50h] BYREF
  void *v234; // [rsp+B8h] [rbp-48h] BYREF
  void *v235; // [rsp+C0h] [rbp-40h] BYREF
  char *v236; // [rsp+C8h] [rbp-38h]
  void *v237; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v238; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE *v239; // [rsp+E0h] [rbp-20h]
  char *v240; // [rsp+E8h] [rbp-18h]
  _OWORD *v241; // [rsp+F0h] [rbp-10h]
  void *v242; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v243; // [rsp+100h] [rbp+0h] BYREF
  int v244; // [rsp+108h] [rbp+8h]
  int v245; // [rsp+110h] [rbp+10h]
  volatile signed __int32 *v246; // [rsp+118h] [rbp+18h] BYREF
  unsigned int v247; // [rsp+120h] [rbp+20h]
  int v248; // [rsp+124h] [rbp+24h]
  unsigned int v249; // [rsp+128h] [rbp+28h]
  __int64 v250; // [rsp+130h] [rbp+30h]
  StringToIndexList *v251; // [rsp+138h] [rbp+38h] BYREF
  volatile signed __int32 *v252; // [rsp+140h] [rbp+40h] BYREF
  unsigned int v253; // [rsp+148h] [rbp+48h]
  int v254; // [rsp+14Ch] [rbp+4Ch]
  _WORD *v255; // [rsp+158h] [rbp+58h] BYREF
  _WORD *v256; // [rsp+160h] [rbp+60h] BYREF
  void **v257; // [rsp+168h] [rbp+68h]
  char *v258; // [rsp+170h] [rbp+70h]
  unsigned __int64 v259; // [rsp+178h] [rbp+78h]
  void **v260; // [rsp+180h] [rbp+80h]
  __int64 v261; // [rsp+188h] [rbp+88h]
  __int64 v262; // [rsp+190h] [rbp+90h]
  void **v263; // [rsp+198h] [rbp+98h]
  __int128 v264; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v265; // [rsp+1B0h] [rbp+B0h]
  unsigned __int64 v266; // [rsp+1B8h] [rbp+B8h]
  void *v267[3]; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int64 v268; // [rsp+1D8h] [rbp+D8h]
  void *Block; // [rsp+1E0h] [rbp+E0h]
  __int128 v270; // [rsp+1F0h] [rbp+F0h] BYREF
  _OWORD v271[4]; // [rsp+200h] [rbp+100h]
  _QWORD v272[3]; // [rsp+240h] [rbp+140h] BYREF
  _QWORD v273[3]; // [rsp+258h] [rbp+158h] BYREF
  _QWORD v274[3]; // [rsp+270h] [rbp+170h] BYREF
  _QWORD v275[30]; // [rsp+288h] [rbp+188h] BYREF
  _QWORD v276[7]; // [rsp+378h] [rbp+278h] BYREF
  _BYTE v277[368]; // [rsp+3B0h] [rbp+2B0h] BYREF

  v3 = a2;
  v228 = a2;
  v4 = a1;
  v239 = a1;
  memset_0(&v270, 0, 0x50u);
  DWORD1(Source) = 0;
  v8 = *((unsigned int *)v3 + 4);
  v9 = v8 + 3;
  if ( v8 + 3 < v8 )
    goto LABEL_339;
  v5 = 0xFFFFFFFFLL;
  if ( v9 > 0xFFFFFFFF )
    goto LABEL_339;
  v10 = (unsigned int)v9 & 0xFFFFFFFC;
  v6 = *(char **)v3;
  if ( *(_QWORD *)v3 )
  {
    v11 = *((_DWORD *)v3 + 2);
    if ( v11 < (unsigned int)v10 || v11 - (unsigned int)v10 < 0x50 )
    {
      FailAssert(0x4Bu, (const char *)0xFFFFFFFFLL);
      __debugbreak();
    }
  }
  v12 = (unsigned int)v10;
  v9 = v10 + 80;
  if ( v9 < v12 )
    goto LABEL_339;
  if ( v9 > 0xFFFFFFFF )
    goto LABEL_339;
  v9 = (unsigned int)v9;
  *((_DWORD *)v3 + 4) = v9;
  *((_QWORD *)&Source + 1) = *(_QWORD *)v4;
  LODWORD(Source) = *((_DWORD *)v4 + 4) + 16;
  v13 = (unsigned int)v9 + 7LL;
  if ( v13 < (unsigned int)v9 || v13 > 0xFFFFFFFF )
    goto LABEL_339;
  v14 = (unsigned int)v13 & 0xFFFFFFF8;
  if ( v6 )
  {
    v15 = *((_DWORD *)v3 + 2);
    if ( v15 < (unsigned int)v14 || (v16 = v15 - v14, v16 < 0x10) )
    {
      FailAssert(0x4Bu, (const char *)0xFFFFFFFFLL);
      __debugbreak();
    }
    v17 = (unsigned int)v14;
    memcpy_s(&v6[v14], v16, &Source, 0x10u);
    v5 = 0xFFFFFFFFLL;
  }
  else
  {
    v17 = (unsigned int)v14;
  }
  v18 = v17 + 16;
  if ( v17 + 16 < v17 || v18 > 0xFFFFFFFF )
    goto LABEL_339;
  *((_DWORD *)v3 + 4) = v18;
  DWORD1(v270) = v14;
  v19 = *((unsigned int *)v4 + 4);
  v7 = *(char **)v3;
  if ( *(_QWORD *)v3 )
  {
    v20 = *((_DWORD *)v3 + 2);
    if ( v20 < (unsigned int)v18 || (v5 = v20 - (unsigned int)v18, v5 < v19) )
    {
      FailAssert(0x4Bu, (const char *)v5);
      goto LABEL_348;
    }
    v6 = (char *)*((_QWORD *)v4 + 1);
    if ( v6 )
      memcpy_s(&v7[(unsigned int)v18], v5, v6, (unsigned int)v19);
  }
  v9 = (unsigned int)v18 + v19;
  if ( v9 < (unsigned int)v18 || v9 > 0xFFFFFFFF )
LABEL_339:
    SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v9, v5, v6, v7);
  *((_DWORD *)v3 + 4) = v9;
  v227 = 0x8F5C28F5C28F5C29uLL * ((__int64)(*((_QWORD *)v4 + 4) - *((_QWORD *)v4 + 3)) >> 3);
  v21 = v227;
  v22 = (_DWORD *)MemoryWriter<FontSetRegion>::WriteArray<FontSetRegion::FontEntry>(v3);
  v2 = (unsigned int)*v22;
  DWORD2(v270) = *v22;
  v242 = 0;
  v243 = 0;
  v244 = 0;
  v245 = 0;
  v235 = 0;
  `eh vector constructor iterator'(
    v277,
    0x18u,
    0xFu,
    std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>,
    std::vector<StringToFontIndex>::~vector<StringToFontIndex>);
  v23 = 0;
  v219 = 0;
  if ( v21 )
  {
    v17 = 0x676174676E616CLL;
    while ( 1 )
    {
      v259 = v23;
      v24 = (FontFaceKey *)(*((_QWORD *)v4 + 3) + 200 * v23);
      v229 = v24;
      *((_DWORD *)v24 + 15) = FontFaceKey::GetSerializedByteSize(v24);
      SerializedByteSize = FontFaceKey::GetSerializedByteSize(v24);
      v28 = *((unsigned int *)v3 + 4);
      v29 = v28 + 7;
      if ( v28 + 7 < v28 || v29 > 0xFFFFFFFF )
        goto LABEL_336;
      v30 = (unsigned int)v29 & 0xFFFFFFF8;
      v28 = *(_QWORD *)v3;
      if ( *(_QWORD *)v3 )
      {
        v31 = *((_DWORD *)v3 + 2);
        if ( v31 < (unsigned int)v30 || v31 - (unsigned int)v30 < SerializedByteSize )
        {
          FailAssert(0x4Bu, v25);
LABEL_342:
          FailAssert(0x4Bu, v189);
          __debugbreak();
        }
      }
      v25 = (const char *)(unsigned int)v30;
      v32 = SerializedByteSize + v30;
      if ( SerializedByteSize + v30 < (unsigned int)v30 || v32 > 0xFFFFFFFF )
        goto LABEL_336;
      *((_DWORD *)v3 + 4) = v32;
      if ( v28 )
        FontFaceKey::SerializeTo(v24, (void *)(v28 + (unsigned int)v30), SerializedByteSize);
      *((_DWORD *)v24 + 14) = v30;
      `eh vector constructor iterator'(
        v272,
        0x18u,
        0xFu,
        (void (*)(void *))FontNameList::FontNameList,
        (void (*)(void *))FontNameList::~FontNameList);
      v33 = *((_QWORD *)v4 + 9);
      v34 = (int *)(v33 + 24LL * *((unsigned int *)v24 + 43));
      for ( i = (int *)(v33 + 24LL * *((unsigned int *)v24 + 42)); i != v34; i += 6 )
      {
        v36 = *i;
        if ( (unsigned int)v36 < 0xF )
        {
          v37 = *(unsigned int *)(*((_QWORD *)i + 2) + 4LL);
          v264 = 0;
          v265 = 0;
          v266 = 0;
          std::wstring::_Construct_empty(&v264);
          if ( v37 )
          {
            std::wstring::assign(&v264, v38 + 8, (unsigned int)v37);
            v39 = &v264;
            if ( v266 > 7 )
              v39 = (__int128 *)v264;
            for ( j = 0; j < v37; ++j )
            {
              v47 = *((_WORD *)v39 + j);
              if ( (unsigned __int16)(v47 - 97) > 0x19u )
              {
                if ( (unsigned __int16)(v47 - 65) > 0x19u )
                  break;
                *((_WORD *)v39 + j) = v47 + 32;
              }
            }
            if ( j - 1 > 7 )
            {
              Exception::Exception((Exception *)&v218, -2147024809, 0);
              LogAndThrow<ArgumentException>((int *)&v218, v17, 120);
            }
            while ( j < v37 )
            {
              v48 = *((_WORD *)v39 + j);
              if ( v48 != 45 && v48 != 95 )
                goto LABEL_72;
              for ( k = ++j; j < v37; ++j )
              {
                v50 = *((_WORD *)v39 + j);
                if ( (unsigned __int16)(v50 - 97) > 0x19u && (unsigned __int16)(v50 - 48) > 9u )
                {
                  if ( (unsigned __int16)(v50 - 65) > 0x19u )
                    break;
                  *((_WORD *)v39 + j) = v50 + 32;
                }
              }
              if ( j - k - 1 > 7 )
              {
                v218 = -2147024809;
                CaptureStack(-2147024809, 0);
                LogAndThrow<ArgumentException>((int *)&v218, v17, 142);
              }
            }
            if ( j != v37 )
            {
LABEL_72:
              v218 = -2147024809;
              CaptureStack(-2147024809, 0);
              LogAndThrow<ArgumentException>((int *)&v218, v17, 147);
            }
          }
          v41 = &v272[3 * v36];
          v260 = v267;
          std::wstring::wstring(v267, &v264);
          Block = (void *)*((_QWORD *)i + 1);
          _InterlockedIncrement((volatile signed __int32 *)Block);
          v42 = v41[1];
          if ( v42 == v41[2] )
          {
            std::vector<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>>::_Emplace_reallocate<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>>(
              &v272[3 * v36],
              v41[1],
              (__int64)v267);
          }
          else
          {
            v261 = v41[1];
            v262 = v42;
            std::wstring::wstring(v42, v267);
            *(_QWORD *)(v43 + 32) = Block;
            _InterlockedIncrement((volatile signed __int32 *)Block);
            v41[1] += 40LL;
          }
          v44 = Block;
          if ( Block != &DWrite::RefString::empty_
            && _InterlockedExchangeAdd((volatile signed __int32 *)Block, 0xFFFFFFFF) == 1 )
          {
            operator delete(v44);
          }
          v263 = v267;
          if ( v268 > 7 )
            std::_Deallocate<16>(v267[0], 2 * v268 + 2);
          v267[2] = 0;
          v268 = 7;
          LOWORD(v267[0]) = 0;
          if ( v266 > 7 )
            std::_Deallocate<16>((void *)v264, 2 * v266 + 2);
          v265 = 0;
          v266 = 7;
          LOWORD(v264) = 0;
        }
      }
      if ( v274[0] == v274[1] )
      {
        v45 = (const struct FontNameList *)v273;
        v46 = (FontNameList *)v274;
      }
      else
      {
        if ( v273[0] != v273[1] )
          goto LABEL_75;
        v45 = (const struct FontNameList *)v274;
        v46 = (FontNameList *)v273;
      }
      FontNameList::AppendItems(v46, v45);
LABEL_75:
      if ( v276[0] == v276[1] )
      {
        v51 = (const struct FontNameList *)v275;
        v52 = (FontNameList *)v276;
        goto LABEL_79;
      }
      if ( v275[0] == v275[1] )
      {
        v51 = (const struct FontNameList *)v276;
        v52 = (FontNameList *)v275;
LABEL_79:
        FontNameList::AppendItems(v52, v51);
      }
      v53 = 0;
      v221 = 0;
      do
      {
        v54 = 24 * v53;
        v225 = (void *)(24 * v53);
        std::_Sort_unchecked<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString> *,std::less<void>>(
          v272[3 * v53],
          v272[3 * v53 + 1],
          0xCCCCCCCCCCCCCCCDuLL * ((__int64)(v272[3 * v53 + 1] - v272[3 * v53]) >> 3),
          0);
        v57 = 0;
        v58 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(v272[3 * v53 + 1] - v272[3 * v53]) >> 3);
        v236 = (char *)v58;
        if ( v58 )
        {
          if ( v58 > 0xFFFFFFFF
            || (v55 = 8LL * (unsigned int)v58, !is_mul_ok(8u, v58))
            || (v240 = (char *)((unsigned int)v55 + 4LL), (unsigned __int64)v240 > 0xFFFFFFFF) )
          {
LABEL_189:
            SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v55, v58, 0xFFFFFFFFLL, v56);
          }
          v59 = 0;
          v220 = 0;
          do
          {
            v55 = *(_QWORD *)((char *)v272 + v54);
            if ( v59 >= 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*(_QWORD *)((char *)&v272[1] + v54) - v55) >> 3) )
            {
              FailAssert(0x35u, (const char *)v58);
LABEL_363:
              FailAssert(0x95u, v69);
              __debugbreak();
            }
            v60 = v55 + 40 * v59;
            v61 = *(_QWORD *)(v60 + 16);
            if ( *(_QWORD *)(v60 + 24) <= 7u )
              v62 = (const void *)(v55 + 40 * v59);
            else
              v62 = *(const void **)v60;
            if ( v61 )
            {
              if ( v61 > 0xFFFFFFFF )
                goto LABEL_189;
              v55 = 2LL * (unsigned int)v61;
              if ( !is_mul_ok(2u, v61) )
                goto LABEL_189;
              v63 = (unsigned int)v55;
              v55 = (unsigned int)v55 + 10LL;
              if ( v55 < v63 || v55 > 0xFFFFFFFF )
                goto LABEL_189;
              v64 = operator new((unsigned int)v55);
              v66 = v64;
              *v64 = 1;
              v64[1] = v61;
              if ( v62 )
              {
                v67 = 2 * v61;
                if ( 2 * v61 )
                {
                  v68 = v64 + 2;
                  if ( v64 == (_DWORD *)-8LL )
                  {
                    *(_DWORD *)_o__errno(v68, v65, v67) = 22;
                    invalid_parameter_noinfo();
                  }
                  else
                  {
                    memcpy_0(v68, v62, v67);
                  }
                }
              }
              v66[v61 + 4] = 0;
              v59 = v220;
            }
            else
            {
              v66 = &DWrite::RefString::empty_;
            }
            v255 = v66;
            StringMemoryRegionDictionary::WriteString(
              (StringMemoryRegionDictionary *)&v242,
              (const struct DWrite::RefString *)&v255,
              (struct MemoryWriterImpl *)&v243);
            if ( v66 != (_WORD *)&DWrite::RefString::empty_
              && _InterlockedExchangeAdd((volatile signed __int32 *)v66, 0xFFFFFFFF) == 1 )
            {
              operator delete(v66);
            }
            StringMemoryRegionDictionary::WriteString(
              (StringMemoryRegionDictionary *)&v242,
              (const struct DWrite::RefString *)(v60 + 32),
              (struct MemoryWriterImpl *)&v243);
            v220 = ++v59;
            v54 = (__int64)v225;
          }
          while ( v59 < (unsigned __int64)v236 );
          v57 = (unsigned int)v240;
        }
        RefCountedArrayImpl::AllocData(&v237, v57, 1);
        v73 = 0xCCCCCCCCCCCCCCCDuLL
            * ((__int64)(*(_QWORD *)((char *)&v272[1] + v54) - *(_QWORD *)((char *)v272 + v54)) >> 3);
        v241 = (_OWORD *)v73;
        if ( v73 )
        {
          v71 = 0xFFFFFFFFLL;
          if ( v73 > 0xFFFFFFFF )
            goto LABEL_162;
          v74 = *((_DWORD *)v237 + 1);
          v218 = v74;
          v72 = (char *)v237 + 8;
          v236 = (char *)v237 + 8;
          if ( v237 != (void *)-8LL )
          {
            if ( v74 < 4 )
            {
              FailAssert(0x4Bu, v69);
LABEL_336:
              SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v28, v25, SerializedByteSize, v27);
            }
            *(_DWORD *)v72 = v73;
            v71 = 0xFFFFFFFFLL;
          }
          v70 = 8LL * (unsigned int)v73;
          if ( !is_mul_ok(8u, v73) )
            goto LABEL_162;
          v75 = (unsigned int)v70;
          if ( v72 )
          {
            if ( v74 < 4 || (v70 = v74 - 4, v70 < v75) )
            {
              FailAssert(0x4Bu, (const char *)v75);
              __debugbreak();
            }
          }
          v69 = (char *)(v75 + 4);
          v240 = v69;
          if ( (unsigned __int64)v69 > 0xFFFFFFFF )
LABEL_162:
            SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v70, v69, v71, v72);
          v76 = 0;
          v220 = 0;
          while ( 2 )
          {
            v70 = *(_QWORD *)((char *)v272 + v54);
            if ( v76 >= 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*(_QWORD *)((char *)&v272[1] + v54) - v70) >> 3) )
            {
              FailAssert(0x35u, v69);
              __debugbreak();
            }
            v77 = v70 + 40 * v76;
            v78 = *(_QWORD *)(v77 + 16);
            if ( *(_QWORD *)(v77 + 24) <= 7u )
              v79 = (const void *)(v70 + 40 * v76);
            else
              v79 = *(const void **)v77;
            if ( v78 )
            {
              if ( v78 > 0xFFFFFFFF )
                goto LABEL_162;
              v70 = 2LL * (unsigned int)v78;
              if ( !is_mul_ok(2u, v78) )
                goto LABEL_162;
              v80 = (unsigned int)v70;
              v70 = (unsigned int)v70 + 10LL;
              if ( v70 < v80 || v70 > 0xFFFFFFFF )
                goto LABEL_162;
              v81 = operator new((unsigned int)v70);
              v83 = v81;
              *v81 = 1;
              v81[1] = v78;
              if ( v79 )
              {
                v84 = 2 * v78;
                if ( 2 * v78 )
                {
                  v85 = v81 + 2;
                  if ( v81 == (_DWORD *)-8LL )
                  {
                    *(_DWORD *)_o__errno(v85, v82, v84) = 22;
                    invalid_parameter_noinfo();
                  }
                  else
                  {
                    memcpy_0(v85, v79, v84);
                  }
                }
              }
              v83[v78 + 4] = 0;
              v76 = v220;
            }
            else
            {
              v83 = &DWrite::RefString::empty_;
            }
            v256 = v83;
            LODWORD(v250) = StringMemoryRegionDictionary::WriteString(
                              (StringMemoryRegionDictionary *)&v242,
                              (const struct DWrite::RefString *)&v256,
                              (struct MemoryWriterImpl *)&v243);
            if ( v83 != (_WORD *)&DWrite::RefString::empty_
              && _InterlockedExchangeAdd((volatile signed __int32 *)v83, 0xFFFFFFFF) == 1 )
            {
              operator delete(v83);
            }
            HIDWORD(v250) = StringMemoryRegionDictionary::WriteString(
                              (StringMemoryRegionDictionary *)&v242,
                              (const struct DWrite::RefString *)(v77 + 32),
                              (struct MemoryWriterImpl *)&v243);
            v72 = v236;
            if ( v236 )
            {
              if ( v76 > 0xFFFFFFFF )
                goto LABEL_162;
              v70 = 8LL * (unsigned int)v76;
              if ( !is_mul_ok(8u, v76) )
                goto LABEL_162;
              v86 = (unsigned int)v70;
              v70 = (unsigned int)v70 + 4LL;
              if ( v70 < v86 )
                goto LABEL_162;
              v69 = v240;
              if ( (unsigned int)v240 <= 8 || (unsigned int)v70 > (unsigned __int64)(unsigned int)v240 - 8 )
              {
                FailAssert(0x94u, v240);
                __debugbreak();
              }
              if ( v218 < (unsigned int)v240 )
                goto LABEL_363;
              v72 = &v236[(unsigned int)v70];
              if ( !v72 )
              {
                *(_DWORD *)_o__errno((unsigned int)v70, v240, v71) = 22;
                goto LABEL_143;
              }
              v71 = v218 - (unsigned int)v70;
              if ( v71 < 8 )
              {
                memset_0(v72, 0, v71);
                *(_DWORD *)_o__errno(v205, v204, v206) = 34;
LABEL_143:
                invalid_parameter_noinfo();
              }
              else
              {
                *(_QWORD *)v72 = v250;
              }
            }
            v220 = ++v76;
            v54 = (__int64)v225;
            if ( v76 >= (unsigned __int64)v241 )
              break;
            v71 = 0xFFFFFFFFLL;
            continue;
          }
        }
        v87 = InnerMemoryRegionDictionary::WriteInnerRegion(&v235, &v237, v71, v228);
        v89 = v221;
        v90 = v229;
        *((_DWORD *)v229 + v221 + 26) = v87;
        if ( v89 != 12 )
        {
          if ( v89 == 5 )
          {
            v19 = *(_QWORD *)((char *)v272 + v54);
            v18 = *(_QWORD *)((char *)&v272[1] + v54);
            while ( v19 != v18 )
            {
              v124 = *(volatile signed __int32 **)(v19 + 32);
              v246 = v124;
              _InterlockedIncrement(v124);
              v125 = v219;
              v247 = v219;
              v248 = 0;
              v4 = &v277[v54];
              v126 = *((_QWORD *)v4 + 1);
              if ( v126 == *((_QWORD *)v4 + 2) )
              {
LABEL_348:
                std::vector<StringToFontIndex>::_Emplace_reallocate<StringToFontIndex const &>(v4, v126, &v246);
                v124 = v246;
              }
              else
              {
                v257 = (void **)*((_QWORD *)v4 + 1);
                *(_QWORD *)v126 = v124;
                _InterlockedIncrement(v124);
                *(_DWORD *)(v126 + 8) = v125;
                *((_QWORD *)v4 + 1) += 16LL;
              }
              v127 = *(_QWORD *)(v19 + 32);
              if ( *(_DWORD *)(v127 + 4) > 0x1Fu )
              {
                v241 = (_OWORD *)(v127 + 8);
                v128 = operator new(0x48u);
                v131 = (char *)v128;
                *v128 = 1;
                v128[1] = 31;
                v132 = v241;
                if ( v241 )
                {
                  v133 = v128 + 2;
                  if ( v133 )
                  {
                    *v133 = *v241;
                    v133[1] = v132[1];
                    v133[2] = v132[2];
                    *(_OWORD *)((char *)v133 + 46) = *(_OWORD *)((char *)v132 + 46);
                  }
                  else
                  {
                    *(_DWORD *)_o__errno(v241, v129, v130) = 22;
                    invalid_parameter_noinfo();
                  }
                }
                *((_WORD *)v131 + 35) = 0;
                v258 = v131;
                v134 = v131;
                *(_QWORD *)&Source = v131;
                _InterlockedIncrement((volatile signed __int32 *)v131);
                v135 = v219;
                *((_QWORD *)&Source + 1) = v219;
                v136 = *((_QWORD *)v4 + 1);
                if ( v136 == *((_QWORD *)v4 + 2) )
                {
                  std::vector<StringToFontIndex>::_Emplace_reallocate<StringToFontIndex const &>(v4, v136, &Source);
                  v134 = (char *)Source;
                }
                else
                {
                  v251 = (StringToIndexList *)*((_QWORD *)v4 + 1);
                  *(_QWORD *)v136 = v131;
                  _InterlockedIncrement((volatile signed __int32 *)v131);
                  *(_DWORD *)(v136 + 8) = v135;
                  *((_QWORD *)v4 + 1) += 16LL;
                }
                if ( v134 != (char *)&DWrite::RefString::empty_
                  && _InterlockedExchangeAdd((volatile signed __int32 *)v134, 0xFFFFFFFF) == 1 )
                {
                  operator delete(v134);
                }
                if ( v131 != (char *)&DWrite::RefString::empty_
                  && _InterlockedExchangeAdd((volatile signed __int32 *)v131, 0xFFFFFFFF) == 1 )
                {
                  operator delete(v131);
                }
              }
              if ( v124 != (volatile signed __int32 *)&DWrite::RefString::empty_
                && _InterlockedExchangeAdd(v124, 0xFFFFFFFF) == 1 )
              {
                operator delete((void *)v124);
              }
              v19 += 40LL;
              v54 = (__int64)v225;
            }
            v90 = v229;
            goto LABEL_161;
          }
          if ( v89 - 10 >= 2 )
          {
            v91 = *(_QWORD *)((char *)v272 + v54);
            v92 = *(_QWORD *)((char *)&v272[1] + v54);
            while ( v91 != v92 )
            {
              v93 = *(volatile signed __int32 **)(v91 + 32);
              v252 = v93;
              _InterlockedIncrement(v93);
              v94 = v219;
              v253 = v219;
              v254 = 0;
              v95 = &v277[v54];
              v96 = *(_QWORD *)&v277[v54 + 8];
              if ( v96 == *(_QWORD *)&v277[v54 + 16] )
              {
                std::vector<StringToFontIndex>::_Emplace_reallocate<StringToFontIndex const &>(v95, v96, &v252);
                v93 = v252;
              }
              else
              {
                v233 = *(void **)&v277[v54 + 8];
                *(_QWORD *)v96 = v93;
                _InterlockedIncrement(v93);
                *(_DWORD *)(v96 + 8) = v94;
                *((_QWORD *)v95 + 1) += 16LL;
              }
              if ( v93 != (volatile signed __int32 *)&DWrite::RefString::empty_
                && _InterlockedExchangeAdd(v93, 0xFFFFFFFF) == 1 )
              {
                operator delete((void *)v93);
              }
              v91 += 40;
            }
LABEL_161:
            v89 = v221;
            goto LABEL_168;
          }
        }
        v97 = *(_QWORD *)((char *)v272 + v54);
        v98 = *(_QWORD *)((char *)&v272[1] + v54);
        if ( v97 != v98 )
        {
          if ( !(0xCCCCCCCCCCCCCCCDuLL * ((v98 - v97) >> 3)) )
          {
            FailAssert(0x35u, v88);
LABEL_367:
            FailAssert(0x95u, (const char *)v113);
            __debugbreak();
          }
          v99 = *(_QWORD *)(v97 + 32);
          v100 = v99 + 2 * (*(unsigned int *)(v99 + 4) + 4LL);
          v101 = (unsigned __int16 *)(v99 + 8);
          v102 = 0;
          if ( v99 + 8 < v100 )
          {
            while ( (unsigned __int64)v101 < v100 )
            {
              v103 = *v101;
              if ( (unsigned int)(v103 - 48) > 9 )
                goto LABEL_168;
              v203 = v102;
              v102 = v103 + 2 * (5 * v102 - 24);
              if ( v102 < v203 )
                goto LABEL_168;
              ++v101;
            }
            if ( v89 == 10 )
            {
              if ( v102 - 1 <= 0x3E6 )
              {
                *((_WORD *)v90 + 36) = v102;
                *((_WORD *)v90 + 37) = v102;
              }
            }
            else if ( v89 == 11 )
            {
              if ( v102 - 1 <= 8 )
                *((_BYTE *)v90 + 76) = v102;
            }
            else if ( v89 == 12 && v102 <= 2 )
            {
              *((_BYTE *)v90 + 77) = v102;
              *((_BYTE *)v90 + 78) = v102;
            }
          }
        }
LABEL_168:
        v104 = v237;
        if ( v237 && _InterlockedExchangeAdd((volatile signed __int32 *)v237, 0xFFFFFFFF) == 1 )
          operator delete(v104);
        v53 = v89 + 1;
        v221 = v53;
      }
      while ( (unsigned int)v53 < 0xF );
      AddStandardAxes((char *)v90 + 56, v90, (char *)v90 + 176);
      v108 = (const void *)*((_QWORD *)v90 + 22);
      v109 = 4 * ((__int64)(*((_QWORD *)v90 + 23) - (_QWORD)v108) >> 2);
      if ( v109 > 0xFFFFFFFF )
        goto LABEL_369;
      v110 = 4 * ((__int64)(*((_QWORD *)v90 + 23) - (_QWORD)v108) >> 2);
      RefCountedArrayImpl::AllocData(&v238, (unsigned int)v109, 1);
      memcpy_0((void *)(v238 + 8), v108, v110);
      v111 = v228;
      *((_DWORD *)v90 + 41) = InnerMemoryRegionDictionary::WriteInnerRegion(&v235, &v238, v112, v228);
      v116 = v2 + 4;
      if ( v2 + 4 < v2 )
        goto LABEL_223;
      if ( v116 > 0xFFFFFFFF )
        goto LABEL_223;
      v117 = (unsigned int)v116;
      v116 = (unsigned int)v116 + 7LL;
      if ( v116 < v117 || v116 > 0xFFFFFFFF )
        goto LABEL_223;
      v114 = *(_QWORD *)v111;
      if ( !*(_QWORD *)v111 )
        goto LABEL_217;
      if ( v259 > 0xFFFFFFFF
        || (v113 = 112LL * v219, !is_mul_ok(0x70u, v219))
        || (v118 = (unsigned int)v113,
            v113 = (unsigned int)v113 + (unsigned __int64)((unsigned int)v116 & 0xFFFFFFF8),
            v113 < v118)
        || v113 > 0xFFFFFFFF )
      {
LABEL_223:
        SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v116, v113, v114, v115);
      }
      v119 = *((unsigned int *)v111 + 4);
      if ( (unsigned int)v119 <= 0x70
        || (v113 = (unsigned int)v113, (unsigned int)v113 > (unsigned __int64)(v119 - 112)) )
      {
        FailAssert(0x94u, (const char *)v113);
LABEL_369:
        SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v109, v105, v106, v107);
      }
      v120 = *((_DWORD *)v111 + 2);
      if ( v120 < (unsigned int)v119 )
        goto LABEL_367;
      v121 = (_OWORD *)(v114 + (unsigned int)v113);
      if ( !v121 )
      {
        *(_DWORD *)_o__errno(0, (unsigned int)v113, v114) = 22;
        goto LABEL_216;
      }
      v122 = v120 - v113;
      v123 = v122;
      if ( v90 != (FontFaceKey *)-56LL && v122 >= 0x70uLL )
      {
        *v121 = *(_OWORD *)((char *)v90 + 56);
        v121[1] = *(_OWORD *)((char *)v90 + 72);
        v121[2] = *(_OWORD *)((char *)v90 + 88);
        v121[3] = *(_OWORD *)((char *)v90 + 104);
        v121[4] = *(_OWORD *)((char *)v90 + 120);
        v121[5] = *(_OWORD *)((char *)v90 + 136);
        v121[6] = *(_OWORD *)((char *)v90 + 152);
        goto LABEL_217;
      }
      memset_0(v121, 0, v122);
      if ( v90 == (FontFaceKey *)-56LL )
      {
        *(_DWORD *)_o__errno(v138, v137, v139) = 22;
LABEL_216:
        invalid_parameter_noinfo();
      }
      else if ( v123 < 0x70 )
      {
        *(_DWORD *)_o__errno(v138, v137, v139) = 34;
        goto LABEL_216;
      }
LABEL_217:
      std::pair<RefCountedArray<unsigned char> const,unsigned int>::~pair<RefCountedArray<unsigned char> const,unsigned int>(&v238);
      `eh vector destructor iterator'(v272, 0x18u, 0xFu, (void (*)(void *))FontNameList::~FontNameList);
      v23 = v219 + 1;
      v219 = v23;
      if ( (unsigned int)v23 >= (unsigned int)v227 )
        break;
      v3 = v228;
      v4 = v239;
    }
  }
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(Src);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(&v230);
  for ( m = 0; ; m = v218 + 1 )
  {
    v218 = m;
    if ( (unsigned int)m >= 0xF )
      break;
    v141 = (unsigned int)m;
    v142 = &v277[16 * m + 8 * (unsigned int)m];
    v143 = (__int64)(v142[1] - *v142) >> 4;
    std::_Sort_unchecked<StringToFontIndex *,std::less<void>>(*v142, v142[1], v143, 0);
    v145 = v230;
    if ( v230 != v231 )
    {
      std::_Destroy_range<std::allocator<StringToIndexList>>(v230);
      v145 = v230;
      v231 = v230;
    }
    v146 = (__int64)(v142[1] - *v142) >> 4;
    v227 = v146;
    if ( v146 > (v232 - v145) >> 4 )
    {
      if ( v146 > 0xFFFFFFFFFFFFFFFLL )
        goto LABEL_372;
      std::vector<StringToIndexList>::_Reallocate<0>(&v230, &v227);
    }
    v147 = (__int64)(v142[1] - *v142) >> 4;
    v227 = v147;
    v148 = (char *)Src[0];
    if ( v147 > (v223 - (char *)Src[0]) >> 2 )
    {
      if ( v147 > 0x3FFFFFFFFFFFFFFFLL )
LABEL_372:
        std::_Xlength_error("vector too long");
      std::vector<unsigned int>::_Reallocate<0>(Src, &v227);
      v148 = (char *)Src[0];
    }
    v149 = 0;
    while ( v149 < (unsigned int)v143 )
    {
      v150 = (char *)Src[1];
      if ( v148 != Src[1] )
      {
        v150 = v148;
        Src[1] = v148;
      }
      v151 = 16LL * v149;
      v152 = (_DWORD *)(*v142 + v151 + 8);
      if ( v150 == v223 )
      {
        std::vector<unsigned int>::_Emplace_reallocate<unsigned int>(Src, v150, v152);
        v153 = (char *)Src[1];
      }
      else
      {
        *(_DWORD *)v150 = *v152;
        v153 = (char *)Src[1] + 4;
        Src[1] = (char *)Src[1] + 4;
      }
      if ( ++v149 < (unsigned int)v143 )
      {
        do
        {
          v150 = *(char **)(*v142 + 16LL * v149);
          v152 = v150 + 8;
          v144 = *(_QWORD *)(v151 + *v142);
          v154 = (const WCHAR *)(v144 + 8);
          if ( v144 == -8 )
          {
            if ( v150 != (char *)-8LL )
              break;
          }
          else
          {
            if ( v150 == (char *)-8LL )
              break;
            if ( *((_DWORD *)v150 + 1) > 0x7FFFFFFFu )
              goto LABEL_373;
            v144 = *(unsigned int *)(v144 + 4);
            if ( (unsigned int)v144 > 0x7FFFFFFF )
              goto LABEL_373;
            v155 = CompareStringW(0x7Fu, 1u, v154, v144, (PCNZWCH)v150 + 4, *((_DWORD *)v150 + 1));
            v153 = (char *)Src[1];
            if ( v155 != 2 )
              break;
          }
          v150 = (char *)*(unsigned int *)(*v142 + 16LL * v149 + 8);
          v221 = *(_DWORD *)(*v142 + 16LL * v149 + 8);
          if ( Src[0] == v153 || *((_DWORD *)v153 - 1) != (_DWORD)v150 )
          {
            if ( v153 == v223 )
            {
              std::vector<unsigned int>::_Emplace_reallocate<unsigned int>(Src, v153, &v221);
              v153 = (char *)Src[1];
            }
            else
            {
              *(_DWORD *)v153 = (_DWORD)v150;
              v153 = (char *)Src[1] + 4;
              Src[1] = (char *)Src[1] + 4;
            }
          }
          ++v149;
        }
        while ( v149 < (unsigned int)v143 );
      }
      v156 = Src[0];
      v153 = (char *)((v153 - (char *)Src[0]) & 0xFFFFFFFFFFFFFFFCuLL);
      if ( (unsigned __int64)v153 > 0xFFFFFFFF )
LABEL_373:
        SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v153, v150, v152, v144);
      v157 = (unsigned int)v153;
      RefCountedArrayImpl::AllocData(&v225, (unsigned int)v153, 1);
      memcpy_0((char *)v225 + 8, v156, v157);
      v233 = *(void **)(v151 + *v142);
      _InterlockedIncrement((volatile signed __int32 *)v233);
      v234 = v225;
      if ( v225 )
        _InterlockedIncrement((volatile signed __int32 *)v225);
      v158 = v231;
      if ( v231 == v232 )
      {
        std::vector<StringToIndexList>::_Emplace_reallocate<StringToIndexList const &>(&v230, v231, &v233);
      }
      else
      {
        v251 = v231;
        *(_QWORD *)v231 = v233;
        _InterlockedIncrement((volatile signed __int32 *)v233);
        v258 = (char *)v158 + 8;
        *((_QWORD *)v158 + 1) = v234;
        if ( v234 )
          _InterlockedIncrement((volatile signed __int32 *)v234);
        v231 = (StringToIndexList *)((char *)v231 + 16);
      }
      v257 = &v234;
      v159 = v234;
      if ( v234 && _InterlockedExchangeAdd((volatile signed __int32 *)v234, 0xFFFFFFFF) == 1 )
        operator delete(v159);
      v160 = v233;
      if ( v233 != &DWrite::RefString::empty_
        && _InterlockedExchangeAdd((volatile signed __int32 *)v233, 0xFFFFFFFF) == 1 )
      {
        operator delete(v160);
      }
      v161 = v225;
      if ( v225 && _InterlockedExchangeAdd((volatile signed __int32 *)v225, 0xFFFFFFFF) == 1 )
        operator delete(v161);
      v148 = (char *)Src[0];
    }
    v162 = (v231 - v230) >> 4;
    v163 = v228;
    v164 = *(unsigned int *)MemoryWriter<FontSetRegion>::WriteArray<FontSetRegion::StringToIndexList>(v228);
    *((_DWORD *)v271 + v141 + 1) = v164;
    v165 = 0;
    if ( (_DWORD)v162 )
    {
      v166 = (unsigned int)v164;
      v167 = v164 + 4;
      do
      {
        v168 = 16LL * v165;
        LODWORD(v229) = StringMemoryRegionDictionary::WriteString(
                          (StringMemoryRegionDictionary *)&v242,
                          (StringToIndexList *)((char *)v230 + v168),
                          (struct MemoryWriterImpl *)&v243);
        HIDWORD(v229) = InnerMemoryRegionDictionary::WriteInnerRegion(&v235, (char *)v230 + v168 + 8, v169, v163);
        if ( v167 < v166 )
          goto LABEL_291;
        if ( v167 > 0xFFFFFFFF )
          goto LABEL_291;
        v170 = (unsigned int)v167 + 3LL;
        if ( v170 < (unsigned int)v167 || v170 > 0xFFFFFFFF )
          goto LABEL_291;
        v173 = *(const char **)v163;
        if ( *(_QWORD *)v163 )
        {
          v171 = 8LL * v165;
          if ( !is_mul_ok(8u, v165) )
            goto LABEL_291;
          v172 = (unsigned int)v171 + (unsigned __int64)((unsigned int)v170 & 0xFFFFFFFC);
          if ( v172 < (unsigned int)v171 || v172 > 0xFFFFFFFF )
            goto LABEL_291;
          v174 = *((unsigned int *)v163 + 4);
          if ( (unsigned int)v174 <= 8 || (v170 = (unsigned int)v172, (unsigned int)v172 > (unsigned __int64)(v174 - 8)) )
          {
            FailAssert(0x94u, (const char *)v170);
            __debugbreak();
          }
          v175 = *((_DWORD *)v163 + 2);
          if ( v175 < (unsigned int)v174 )
          {
            FailAssert(0x95u, (const char *)(unsigned int)v172);
            __debugbreak();
          }
          v176 = (FontFaceKey **)&v173[(unsigned int)v172];
          if ( v176 )
          {
            v177 = v175 - (unsigned int)v172;
            if ( v177 >= 8 )
            {
              *v176 = v229;
              goto LABEL_287;
            }
            memset_0(v176, 0, v177);
            *(_DWORD *)_o__errno(v208, v207, v209) = 34;
          }
          else
          {
            *(_DWORD *)_o__errno(0, (unsigned int)v172, v172) = 22;
          }
          invalid_parameter_noinfo();
        }
LABEL_287:
        ++v165;
      }
      while ( v165 < (unsigned int)v162 );
    }
  }
  v178 = v239;
  std::_Sort_unchecked_FontSetBuilder::FileEntry____lambda_0f18e48da815e7d4c6cb3f627fd23bdc___(
    *((_QWORD *)v239 + 6),
    *((_QWORD *)v239 + 7),
    (__int64)(*((_QWORD *)v239 + 7) - *((_QWORD *)v239 + 6)) >> 4,
    v224);
  v179 = (_QWORD *)*((_QWORD *)v178 + 7);
  v180 = *(_QWORD **)std::unique<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<FontSetBuilder::FileEntry>>>>(
                       &v251,
                       *((_QWORD *)v178 + 6),
                       v179);
  if ( v180 != v179 )
  {
    v210 = std::_Move_unchecked<FontSetBuilder::FileEntry *,FontSetBuilder::FileEntry *>(
             v179,
             *((_QWORD **)v178 + 7),
             v180);
    std::_Destroy_range<std::allocator<FontSetBuilder::FileEntry>>(v210, *((_QWORD *)v178 + 7), v211);
    *((_QWORD *)v178 + 7) = v210;
  }
  v181 = (__int64)(*((_QWORD *)v178 + 7) - *((_QWORD *)v178 + 6)) >> 4;
  v182 = v228;
  v183 = (_DWORD *)MemoryWriter<FontSetRegion>::WriteArray<FontSetRegion::FileEntry>(v228);
  v184 = (unsigned int)*v183;
  HIDWORD(v270) = *v183;
  for ( n = 0; n < (unsigned int)v181; ++n )
  {
    v186 = (_QWORD *)(*((_QWORD *)v239 + 6) + 16LL * n);
    *(_QWORD *)&Source = *v186;
    v171 = v186[1];
    v187 = *(unsigned int *)(v171 + 4);
    v188 = *((unsigned int *)v182 + 4);
    v189 = *(const char **)v182;
    if ( *(_QWORD *)v182 )
    {
      v190 = *((_DWORD *)v182 + 2);
      if ( v190 < (unsigned int)v188 || v190 - (unsigned int)v188 < v187 )
        goto LABEL_342;
      v173 = (const char *)(v171 + 8);
      if ( v171 != -8 && *(_DWORD *)(v171 + 4) )
      {
        v191 = (char *)&v189[(unsigned int)v188];
        if ( v191 )
        {
          memcpy_0(v191, v173, v187);
        }
        else
        {
          *(_DWORD *)_o__errno(0, v189, v172) = 22;
          invalid_parameter_noinfo();
        }
      }
    }
    v170 = v188 + v187;
    if ( v188 + v187 < v188
      || v170 > 0xFFFFFFFF
      || (*((_DWORD *)v182 + 4) = v170,
          HIDWORD(Source) = v188,
          DWORD2(Source) = *(_DWORD *)(v186[1] + 4LL),
          v171 = v184 + 4,
          v184 + 4 < v184)
      || v171 > 0xFFFFFFFF
      || (v192 = (unsigned int)v171, v171 = (unsigned int)v171 + 7LL, v171 < v192)
      || v171 > 0xFFFFFFFF )
    {
LABEL_291:
      SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v171, v170, v172, v173);
    }
    v173 = *(const char **)v182;
    if ( *(_QWORD *)v182 )
    {
      v172 = 16LL * n;
      if ( !is_mul_ok(0x10u, n) )
        goto LABEL_291;
      v193 = (unsigned int)v172;
      v172 = (unsigned int)v172 + (unsigned __int64)((unsigned int)v171 & 0xFFFFFFF8);
      if ( v172 < v193 || v172 > 0xFFFFFFFF )
        goto LABEL_291;
      if ( (unsigned int)v170 <= 0x10
        || (v194 = (unsigned int)v172, (unsigned int)v172 > (unsigned __int64)(unsigned int)v170 - 16) )
      {
        FailAssert(0x94u, (const char *)v170);
        __debugbreak();
      }
      v195 = *((_DWORD *)v182 + 2);
      if ( v195 < (unsigned int)v170 )
      {
        FailAssert(0x95u, (const char *)v170);
        __debugbreak();
      }
      v196 = (char *)&v173[(unsigned int)v172];
      if ( v196 )
      {
        v172 = v195 - (unsigned int)v172;
        if ( v172 >= 0x10 )
        {
          *(_OWORD *)v196 = Source;
          continue;
        }
        memset_0((void *)&v173[v194], 0, v172);
        *(_DWORD *)_o__errno(v213, v212, v214) = 34;
      }
      else
      {
        *(_DWORD *)_o__errno((unsigned int)v172, v170, v172) = 22;
      }
      invalid_parameter_noinfo();
    }
  }
  MemoryWriterImpl::BeginInnerRegionImpl(v182, &Source, 4);
  v246 = (volatile signed __int32 *)Source;
  v247 = DWORD2(Source);
  v249 = 0;
  StringMemoryRegionDictionary::WriteRegion((StringMemoryRegionDictionary *)&v242, (struct MemoryWriterImpl *)&v246);
  LODWORD(v271[0]) = MemoryWriterImpl::EndInnerRegionImpl(v182, v249, 4u);
  v198 = *((_DWORD *)v182 + 4);
  LODWORD(v270) = v198;
  v199 = *(char **)v182;
  if ( *(_QWORD *)v182 )
  {
    if ( v198 < 0x50 )
    {
      FailAssert(0x7Au, v197);
      JUMPOUT(0x180023FF8LL);
    }
    v200 = (const char *)*((unsigned int *)v182 + 2);
    if ( (unsigned int)v200 < v198 )
    {
      FailAssert(0x7Bu, v200);
      __debugbreak();
    }
    if ( (unsigned __int64)v200 < 0x50 )
    {
      memset_0(v199, 0, (unsigned int)v200);
      *(_DWORD *)_o__errno(v216, v215, v217) = 34;
      invalid_parameter_noinfo();
    }
    else
    {
      *(_OWORD *)v199 = v270;
      *((_OWORD *)v199 + 1) = v271[0];
      *((_OWORD *)v199 + 2) = v271[1];
      *((_OWORD *)v199 + 3) = v271[2];
      *((_OWORD *)v199 + 4) = v271[3];
    }
  }
  std::vector<StringToIndexList>::_Tidy(&v230);
  if ( Src[0] )
  {
    std::_Deallocate<16>(Src[0], (v223 - (char *)Src[0]) & 0xFFFFFFFFFFFFFFFCuLL);
    *(_OWORD *)Src = 0;
    v223 = 0;
  }
  `eh vector destructor iterator'(v277, 0x18u, 0xFu, std::vector<StringToFontIndex>::~vector<StringToFontIndex>);
  v201 = v235;
  if ( v235 )
  {
    std::_Tree<std::_Tmap_traits<RefCountedArray<unsigned char>,unsigned int,InnerMemoryRegionDictionary::OffsetMap::Comparer,std::allocator<std::pair<RefCountedArray<unsigned char> const,unsigned int>>,0>>::~_Tree<std::_Tmap_traits<RefCountedArray<unsigned char>,unsigned int,InnerMemoryRegionDictionary::OffsetMap::Comparer,std::allocator<std::pair<RefCountedArray<unsigned char> const,unsigned int>>,0>>(v235);
    operator delete(v201, 0x10u);
  }
  v202 = v242;
  if ( v242 )
  {
    std::_Tree<std::_Tmap_traits<DWrite::RefString,unsigned int,std::less<DWrite::RefString>,std::allocator<std::pair<DWrite::RefString const,unsigned int>>,0>>::~_Tree<std::_Tmap_traits<DWrite::RefString,unsigned int,std::less<DWrite::RefString>,std::allocator<std::pair<DWrite::RefString const,unsigned int>>,0>>(v242);
    operator delete(v202, 0x10u);
  }
}

```

## disassembly

```asm
0x180022400  mov     [rsp-8+arg_10], rbx
0x180022405  push    rbp
0x180022406  push    rsi
0x180022407  push    rdi
0x180022408  push    r12
0x18002240a  push    r13
0x18002240c  push    r14
0x18002240e  push    r15
0x180022410  lea     rbp, [rsp-430h]
0x180022418  sub     rsp, 530h
0x18002241f  mov     rax, cs:__security_cookie
0x180022426  xor     rax, rsp
0x180022429  mov     [rbp+460h+var_40], rax
0x180022430  mov     r12, rdx
0x180022433  mov     [rbp+460h+var_4D8], rdx
0x180022437  mov     r13, rcx
0x18002243a  mov     [rbp+460h+var_480], rcx
0x18002243e  xor     ebx, ebx
0x180022440  xor     edx, edx; Val
0x180022442  mov     r8d, 50h ; 'P'; Size
0x180022448  lea     rcx, [rbp+460h+var_370]; void *
0x18002244f  call    memset_0
0x180022454  mov     dword ptr [rsp+560h+Source+4], ebx
0x180022458  mov     eax, [r12+10h]
0x18002245d  lea     rcx, [rax+3]
0x180022461  cmp     rcx, rax
0x180022464  jb      loc_180023D5E
0x18002246a  mov     edx, 0FFFFFFFFh; char *
0x18002246f  cmp     rcx, rdx
0x180022472  ja      loc_180023D5E
0x180022478  mov     eax, 0FFFFFFFCh
0x18002247d  and     ecx, eax
0x18002247f  mov     r8, [r12]
0x180022483  test    r8, r8
0x180022486  jz      short loc_1800224A0
0x180022488  mov     eax, [r12+8]
0x18002248d  cmp     eax, ecx
0x18002248f  jb      loc_180023DBF
0x180022495  sub     eax, ecx
0x180022497  cmp     eax, 50h ; 'P'
0x18002249a  jb      loc_180023DBF
0x1800224a0  mov     eax, ecx
0x1800224a2  add     rcx, 50h ; 'P'
0x1800224a6  cmp     rcx, rax
0x1800224a9  jb      loc_180023D5E
0x1800224af  cmp     rcx, rdx
0x1800224b2  ja      loc_180023D5E
0x1800224b8  mov     ecx, ecx
0x1800224ba  mov     [r12+10h], ecx
0x1800224bf  mov     rax, [r13+0]
0x1800224c3  mov     qword ptr [rsp+560h+Source+8], rax
0x1800224c8  mov     eax, [r13+10h]
0x1800224cc  add     eax, 10h
0x1800224cf  mov     dword ptr [rsp+560h+Source], eax
0x1800224d3  lea     rbx, [rcx+7]
0x1800224d7  cmp     rbx, rcx
0x1800224da  jb      loc_180023D5E
0x1800224e0  cmp     rbx, rdx
0x1800224e3  ja      loc_180023D5E
0x1800224e9  mov     eax, 0FFFFFFF8h
0x1800224ee  and     ebx, eax
0x1800224f0  test    r8, r8
0x1800224f3  jz      loc_180023D57
0x1800224f9  mov     eax, [r12+8]
0x1800224fe  cmp     eax, ebx
0x180022500  jb      loc_180023DCA
0x180022506  sub     eax, ebx
0x180022508  cmp     eax, 10h
0x18002250b  jb      loc_180023DCA
0x180022511  mov     esi, ebx
0x180022513  mov     edx, eax; DestinationSize
0x180022515  lea     rcx, [rbx+r8]; Destination
0x180022519  mov     r9d, 10h; SourceSize
0x18002251f  lea     r8, [rsp+560h+Source]; Source
0x180022524  call    memcpy_s
0x180022529  mov     edx, 0FFFFFFFFh; char *
0x18002252e  lea     rdi, [rsi+10h]
0x180022532  cmp     rdi, rsi
0x180022535  jb      loc_180023D5E
0x18002253b  cmp     rdi, rdx
0x18002253e  ja      loc_180023D5E
0x180022544  mov     [r12+10h], edi
0x180022549  mov     dword ptr [rbp+460h+var_370+4], ebx
0x18002254f  mov     ebx, [r13+10h]
0x180022553  mov     r9, [r12]
0x180022557  test    r9, r9
0x18002255a  jz      short loc_18002258C
0x18002255c  mov     eax, [r12+8]
0x180022561  cmp     eax, edi
0x180022563  jb      loc_180023DD5
0x180022569  sub     eax, edi
0x18002256b  mov     edx, eax; DestinationSize
0x18002256d  cmp     rdx, rbx
0x180022570  jb      loc_180023DD5
0x180022576  mov     r8, [r13+8]; Source
0x18002257a  test    r8, r8
0x18002257d  jz      short loc_18002258C
0x18002257f  mov     ecx, edi
0x180022581  add     rcx, r9; Destination
0x180022584  mov     r9d, ebx; SourceSize
0x180022587  call    memcpy_s
0x18002258c  mov     eax, edi
0x18002258e  lea     rcx, [rax+rbx]
0x180022592  cmp     rcx, rax
0x180022595  jb      loc_180023D5E
0x18002259b  mov     edi, 0FFFFFFFFh
0x1800225a0  cmp     rcx, rdi
0x1800225a3  ja      loc_180023D5E
0x1800225a9  mov     [r12+10h], ecx
0x1800225ae  mov     rbx, [r13+20h]
0x1800225b2  sub     rbx, [r13+18h]
0x1800225b6  sar     rbx, 3
0x1800225ba  mov     rax, 8F5C28F5C28F5C29h
0x1800225c4  imul    rbx, rax
0x1800225c8  mov     [rbp+460h+var_4E0], rbx
0x1800225cc  mov     r9d, ebx
0x1800225cf  lea     rdx, [rsp+560h+var_530]
0x1800225d4  mov     rcx, r12; this
0x1800225d7  call    ??$WriteArray@UFontEntry@FontSetRegion@@@?$MemoryWriter@VFontSetRegion@@@@QEAA?AV?$BasedArrayPtr@VFontSetRegion@@UFontEntry@1@II$07@@PEBUFontEntry@FontSetRegion@@_K@Z; MemoryWriter<FontSetRegion>::WriteArray<FontSetRegion::FontEntry>(FontSetRegion::FontEntry const *,unsigned __int64)
0x1800225dc  mov     r14d, [rax]
0x1800225df  mov     dword ptr [rbp+460h+var_370+8], r14d
0x1800225e6  mov     [rbp+460h+var_468], 0
0x1800225ee  mov     [rbp+460h+var_460], 0
0x1800225f6  mov     [rbp+460h+var_458], 0
0x1800225fd  mov     [rbp+460h+var_450], 0
0x180022604  mov     [rbp+460h+var_4A0], 0
0x18002260c  lea     rax, ??1?$vector@UStringToFontIndex@@V?$allocator@UStringToFontIndex@@@std@@@std@@QEAA@XZ; std::vector<StringToFontIndex>::~vector<StringToFontIndex>(void)
0x180022613  mov     [rsp+560h+lpString2], rax; void (*)(void *)
0x180022618  lea     r9, ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; void (*)(void *)
0x18002261f  mov     edx, 18h; unsigned __int64
0x180022624  mov     r8d, 0Fh; unsigned __int64
0x18002262a  lea     rcx, [rbp+460h+var_1B0]; void *
0x180022631  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180022636  nop
0x180022637  xor     eax, eax
0x180022639  mov     [rsp+560h+var_52C], eax
0x18002263d  test    ebx, ebx
0x18002263f  jz      loc_180023508
0x180022645  mov     rsi, 676174676E616Ch
0x18002264f  nop
0x180022650  mov     [rbp+460h+var_3E8], rax
0x180022654  imul    r15, rax, 0C8h
0x18002265b  add     r15, [r13+18h]
0x18002265f  mov     [rbp+460h+var_4D0], r15
0x180022663  mov     rcx, r15; this
0x180022666  call    ?GetSerializedByteSize@FontFaceKey@@QEBAIXZ; FontFaceKey::GetSerializedByteSize(void)
0x18002266b  mov     [r15+3Ch], eax
0x18002266f  mov     rcx, r15; this
0x180022672  call    ?GetSerializedByteSize@FontFaceKey@@QEBAIXZ; FontFaceKey::GetSerializedByteSize(void)
0x180022677  mov     r8d, eax; unsigned int
0x18002267a  mov     ecx, [r12+10h]
0x18002267f  lea     rbx, [rcx+7]
0x180022683  cmp     rbx, rcx
0x180022686  jb      loc_180023D45
0x18002268c  cmp     rbx, rdi
0x18002268f  ja      loc_180023D45
0x180022695  mov     eax, 0FFFFFFF8h
0x18002269a  and     ebx, eax
0x18002269c  mov     rcx, [r12]
0x1800226a0  test    rcx, rcx
0x1800226a3  jz      short loc_1800226BD
0x1800226a5  mov     eax, [r12+8]
0x1800226aa  cmp     eax, ebx
0x1800226ac  jb      loc_180023D79
0x1800226b2  sub     eax, ebx
0x1800226b4  cmp     rax, r8
0x1800226b7  jb      loc_180023D79
0x1800226bd  mov     edx, ebx
0x1800226bf  lea     rax, [r8+rbx]
0x1800226c3  cmp     rax, rdx
0x1800226c6  jb      loc_180023D45
0x1800226cc  cmp     rax, rdi
0x1800226cf  ja      loc_180023D45
0x1800226d5  mov     [r12+10h], eax
0x1800226da  test    rcx, rcx
0x1800226dd  jz      short loc_1800226EA
0x1800226df  add     rdx, rcx; void *
0x1800226e2  mov     rcx, r15; this
0x1800226e5  call    ?SerializeTo@FontFaceKey@@QEBAXPEAXI@Z; FontFaceKey::SerializeTo(void *,uint)
0x1800226ea  mov     [r15+38h], ebx
0x1800226ee  lea     rax, ??1FontNameList@@QEAA@XZ; FontNameList::~FontNameList(void)
0x1800226f5  mov     [rsp+560h+lpString2], rax; void (*)(void *)
0x1800226fa  lea     r9, ??0FontNameList@@QEAA@XZ; void (*)(void *)
0x180022701  mov     edx, 18h; unsigned __int64
0x180022706  mov     r8d, 0Fh; unsigned __int64
0x18002270c  lea     rcx, [rbp+460h+var_320]; void *
0x180022713  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180022718  nop
0x180022719  mov     rdx, [r13+48h]
0x18002271d  mov     eax, [r15+0ACh]
0x180022724  lea     rcx, [rax+rax*2]
0x180022728  lea     r12, [rdx+rcx*8]
0x18002272c  mov     eax, [r15+0A8h]
0x180022733  lea     rcx, [rax+rax*2]
0x180022737  lea     rdi, [rdx+rcx*8]
0x18002273b  cmp     rdi, r12
0x18002273e  jz      loc_18002290D
0x180022744  nop     dword ptr [rax+00h]
0x180022748  nop     dword ptr [rax+rax+00000000h]
0x180022750  movsxd  r15, dword ptr [rdi]
0x180022753  cmp     r15d, 0Fh
0x180022757  jnb     loc_180022900
0x18002275d  mov     rdx, [rdi+10h]
0x180022761  mov     ebx, [rdx+4]
0x180022764  xorps   xmm0, xmm0
0x180022767  movups  [rbp+460h+var_3C0], xmm0
0x18002276e  xor     r13d, r13d
0x180022771  mov     [rbp+460h+var_3B0], r13
0x180022778  mov     [rbp+460h+var_3A8], r13
0x18002277f  lea     rcx, [rbp+460h+var_3C0]
0x180022786  call    ?_Construct_empty@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18002278b  nop
0x18002278c  test    rbx, rbx
0x18002278f  jz      short loc_1800227F3
0x180022791  add     rdx, 8
0x180022795  mov     r8d, ebx
0x180022798  lea     rcx, [rbp+460h+var_3C0]
0x18002279f  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x1800227a4  lea     r8, [rbp+460h+var_3C0]
0x1800227ab  cmp     [rbp+460h+var_3A8], 7
0x1800227b3  cmova   r8, qword ptr [rbp+460h+var_3C0]
0x1800227bb  mov     eax, r13d
0x1800227be  test    rbx, rbx
0x1800227c1  jnz     loc_180022950
0x1800227c7  xor     r8d, r8d; unsigned int
0x1800227ca  mov     edx, 80070057h; int
0x1800227cf  lea     rcx, [rsp+560h+var_530]; this
0x1800227d4  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x1800227d9  mov     r8d, 78h ; 'x'
0x1800227df  mov     rdx, rsi
0x1800227e2  lea     rcx, [rsp+560h+var_530]
0x1800227e7  call    ??$LogAndThrow@VArgumentException@@@@YAXAEBVArgumentException@@VEventTag@@I@Z; LogAndThrow<ArgumentException>(ArgumentException const &,EventTag,uint)
0x1800227ed  jnz     loc_180022A28
0x1800227f3  lea     rcx, [r15+r15*2]
0x1800227f7  lea     rbx, [rbp+460h+var_320]
0x1800227fe  lea     rbx, [rbx+rcx*8]
0x180022802  lea     rax, [rbp+460h+var_3A0]
0x180022809  mov     [rbp+460h+var_3E0], rax
0x180022810  lea     rdx, [rbp+460h+var_3C0]
0x180022817  lea     rcx, [rbp+460h+var_3A0]
0x18002281e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180022823  nop
0x180022824  mov     rax, [rdi+8]
0x180022828  mov     [rbp+460h+Block], rax
0x18002282f  lock inc dword ptr [rax]
0x180022832  mov     rcx, [rbx+8]
0x180022836  cmp     rcx, [rbx+10h]
0x18002283a  jz      loc_180022A11
0x180022840  mov     [rbp+460h+var_3D8], rcx
0x180022847  mov     [rbp+460h+var_3D0], rcx
0x18002284e  lea     rdx, [rbp+460h+var_3A0]
0x180022855  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18002285a  nop
0x18002285b  mov     rax, [rbp+460h+Block]
0x180022862  mov     [rcx+20h], rax
0x180022866  mov     rax, [rbp+460h+Block]
0x18002286d  lock inc dword ptr [rax]
0x180022870  add     qword ptr [rbx+8], 28h ; '('
0x180022875  mov     rcx, [rbp+460h+Block]; Block
0x18002287c  lea     rax, ?empty_@RefString@DWrite@@0UData@12@A; DWrite::RefString::Data DWrite::RefString::empty_
0x180022883  cmp     rcx, rax
0x180022886  jz      short loc_18002289C
0x180022888  mov     eax, 0FFFFFFFFh
0x18002288d  lock xadd [rcx], eax
0x180022891  cmp     eax, 1
0x180022894  jnz     short loc_18002289C
0x180022896  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002289b  nop
0x18002289c  lea     rax, [rbp+460h+var_3A0]
0x1800228a3  mov     [rbp+460h+var_3C8], rax
0x1800228aa  mov     rdx, [rbp+460h+var_388]
0x1800228b1  cmp     rdx, 7
0x1800228b5  ja      loc_1800234D8
0x1800228bb  mov     [rbp+460h+var_390], r13
0x1800228c2  mov     [rbp+460h+var_388], 7
0x1800228cd  mov     word ptr [rbp+460h+var_3A0], r13w
0x1800228d5  mov     rdx, [rbp+460h+var_3A8]
0x1800228dc  cmp     rdx, 7
0x1800228e0  ja      loc_1800234BF
0x1800228e6  mov     [rbp+460h+var_3B0], r13
0x1800228ed  mov     [rbp+460h+var_3A8], 7
0x1800228f8  mov     word ptr [rbp+460h+var_3C0], r13w
0x180022900  add     rdi, 18h
0x180022904  cmp     rdi, r12
0x180022907  jnz     loc_180022750
0x18002290d  mov     rax, [rbp+460h+var_2E8]
0x180022914  cmp     [rbp+460h+var_2F0], rax
0x18002291b  jz      loc_180022A50
0x180022921  mov     rax, [rbp+460h+var_300]
0x180022928  cmp     [rbp+460h+var_308], rax
0x18002292f  jnz     loc_180022A63
0x180022935  lea     rdx, [rbp+460h+var_2F0]
0x18002293c  lea     rcx, [rbp+460h+var_308]
0x180022943  jmp     loc_180022A5E
0x180022950  movzx   edx, word ptr [r8+rax*2]
0x180022955  lea     ecx, [rdx-61h]
0x180022958  cmp     cx, 19h
0x18002295c  jbe     short loc_180022970
0x18002295e  lea     ecx, [rdx-41h]
0x180022961  cmp     cx, 19h
  ... truncated ...
```
