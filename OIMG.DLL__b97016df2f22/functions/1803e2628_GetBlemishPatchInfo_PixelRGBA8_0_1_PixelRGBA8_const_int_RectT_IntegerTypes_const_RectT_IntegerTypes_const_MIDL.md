# GetBlemishPatchInfo<PixelRGBA8,0,1>(PixelRGBA8 const *,int,RectT<IntegerTypes> const &,RectT<IntegerTypes> const &,__MIDL___MIDL_itf_Imaging_0001_0125_0001 *)

- ea: `0x1803e2628`
- end: `0x1803e36b9`
- name: `??$GetBlemishPatchInfo@UPixelRGBA8@@$0A@$00@@YA_NPEBUPixelRGBA8@@HAEBU?$RectT@UIntegerTypes@@@@1PEAU__MIDL___MIDL_itf_Imaging_0001_0125_0001@@@Z`
- size: `4241`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1803df2a0`

## callees

- `0x18001397c`
- `0x18001db0c`
- `0x1802243f4`
- `0x1802266d4`
- `0x1803de0dc`
- `0x1803de1f0`
- `0x1803de2a4`
- `0x1803de338`
- `0x1803de3cc`
- `0x1803e13a4`
- `0x1803e2628`
- `0x1803e6884`
- `0x1803e69f4`
- `0x1804c6944`
- `0x18056bd00`
- `0x18056dc8e`
- `0x18056dcca`
- `0x18056dce0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1803e27b9`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1803e27b9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e334b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e33ab`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e340b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e346b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e34cb`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e34e4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e3540`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e3587`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e35ce`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e362b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e334b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e33ab`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e340b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e346b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e34cb`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e34e4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e3540`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e3587`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e35ce`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e362b`
- `GDI32!CombineRgn` at `0x1803e2b5d`
- `GDI32!CombineRgn` at `0x1803e2b5d`
- `GDI32!DeleteObject` at `0x1803e2b6d`
- `GDI32!DeleteObject` at `0x1803e34f3`
- `GDI32!DeleteObject` at `0x1803e2b6d`
- `GDI32!DeleteObject` at `0x1803e34f3`
- `GDI32!CreateRectRgnIndirect` at `0x1803e2b05`
- `GDI32!CreateRectRgnIndirect` at `0x1803e2b43`
- `GDI32!CreateRectRgnIndirect` at `0x1803e2b05`
- `GDI32!CreateRectRgnIndirect` at `0x1803e2b43`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
char __fastcall GetBlemishPatchInfo<PixelRGBA8,0,1>(__int64 a1, int a2, int *a3, int *a4, __int64 a5)
{
  __int64 v7; // r14
  __int64 v8; // r12
  __int64 v9; // r13
  char v10; // r15
  unsigned int v11; // ebx
  unsigned int v12; // edi
  char *v13; // rax
  _BYTE *v14; // rsi
  _DWORD *v15; // rbx
  _BYTE *v16; // rdi
  int v17; // eax
  double v18; // xmm1_8
  double v19; // xmm2_8
  double v20; // xmm3_8
  double v21; // xmm14_8
  int v22; // ecx
  int v23; // r10d
  int v24; // ecx
  int v25; // edi
  char *v26; // rbx
  signed __int64 v27; // r14
  __int64 v28; // rax
  int v29; // r8d
  int v30; // r9d
  __int64 v31; // rcx
  __int64 v32; // rdx
  unsigned __int8 *v33; // r11
  int v34; // eax
  unsigned __int8 *v35; // r10
  int v36; // eax
  unsigned __int8 *v37; // rcx
  float *v38; // rdx
  int v39; // r8d
  _DWORD *v40; // r13
  float v41; // xmm3_4
  float v42; // xmm1_4
  float v43; // xmm0_4
  float v44; // xmm5_4
  float v45; // xmm4_4
  float v46; // xmm2_4
  double v47; // xmm14_8
  HRGN v48; // r14
  int v49; // eax
  int v50; // ecx
  int v51; // ecx
  int v52; // eax
  float v53; // xmm7_4
  int v54; // r10d
  int v55; // eax
  int v56; // r11d
  int v57; // r8d
  int v58; // ecx
  int v59; // r10d
  double v60; // xmm3_8
  int v61; // r8d
  __m128d si128; // xmm15
  char *v63; // rdx
  double v64; // xmm8_8
  __int64 v65; // r11
  int v66; // ecx
  __int64 v67; // r8
  int v68; // r14d
  int v69; // eax
  int v70; // ecx
  double v71; // xmm15_8
  int v72; // r9d
  __int64 v73; // rdx
  int v74; // eax
  __int64 v75; // r13
  int v76; // r12d
  double v77; // xmm6_8
  double v78; // xmm5_8
  double v79; // xmm4_8
  double v80; // xmm7_8
  int v81; // r11d
  char *v82; // rdx
  _DWORD *v83; // rax
  char *v84; // rdx
  __int64 v85; // r9
  int v86; // edx
  __int64 v87; // rcx
  double v88; // xmm9_8
  double v89; // xmm10_8
  double v90; // xmm11_8
  double v91; // xmm5_8
  double v92; // xmm4_8
  double v93; // xmm7_8
  double v94; // xmm9_8
  void **v95; // rcx
  __int64 v96; // rax
  _DWORD *v97; // rdx
  _DWORD *v98; // rcx
  __int64 v99; // r8
  void *v100; // rcx
  __int64 v101; // r8
  bool v102; // al
  void *v103; // rcx
  __int64 v104; // r8
  bool v105; // al
  void *v106; // rcx
  __int64 v107; // r8
  bool v108; // al
  void *v109; // rcx
  __int64 v110; // r8
  bool v111; // al
  void *v112; // rcx
  __int64 v113; // r8
  bool v114; // al
  __int64 v115; // rcx
  __int64 v117; // rcx
  __int64 v119; // rcx
  void *v121; // rcx
  __int64 v122; // r8
  bool v123; // al
  char v125; // [rsp+48h] [rbp-C0h]
  int v126; // [rsp+4Ch] [rbp-BCh]
  int v127; // [rsp+4Ch] [rbp-BCh]
  int v128; // [rsp+4Ch] [rbp-BCh]
  int v129; // [rsp+50h] [rbp-B8h]
  int v130; // [rsp+54h] [rbp-B4h]
  int v131; // [rsp+54h] [rbp-B4h]
  int v132; // [rsp+58h] [rbp-B0h]
  int v134; // [rsp+60h] [rbp-A8h]
  int v135; // [rsp+60h] [rbp-A8h]
  int v136; // [rsp+64h] [rbp-A4h]
  int v137; // [rsp+68h] [rbp-A0h]
  float *v138; // [rsp+70h] [rbp-98h]
  int v139; // [rsp+70h] [rbp-98h]
  char *ho; // [rsp+78h] [rbp-90h]
  HRGN hoa; // [rsp+78h] [rbp-90h]
  char *hob; // [rsp+78h] [rbp-90h]
  __int64 v143; // [rsp+80h] [rbp-88h]
  _BYTE v144[24]; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int8 v145; // [rsp+A0h] [rbp-68h]
  int v146; // [rsp+A8h] [rbp-60h]
  int v147; // [rsp+ACh] [rbp-5Ch]
  int v148; // [rsp+B0h] [rbp-58h]
  _DWORD *v149; // [rsp+B8h] [rbp-50h]
  __int64 v150; // [rsp+C0h] [rbp-48h]
  __int64 v151; // [rsp+C8h] [rbp-40h]
  __int64 v152; // [rsp+D0h] [rbp-38h]
  float *v153; // [rsp+D8h] [rbp-30h]
  signed __int64 v154; // [rsp+E0h] [rbp-28h]
  int v155; // [rsp+E8h] [rbp-20h]
  int v156; // [rsp+ECh] [rbp-1Ch]
  int v157; // [rsp+F0h] [rbp-18h]
  int v158; // [rsp+F4h] [rbp-14h]
  int v159; // [rsp+F8h] [rbp-10h]
  int v160; // [rsp+FCh] [rbp-Ch]
  int v161; // [rsp+100h] [rbp-8h]
  char *v162; // [rsp+108h] [rbp+0h]
  double v163; // [rsp+110h] [rbp+8h]
  double v164; // [rsp+118h] [rbp+10h]
  double v165; // [rsp+120h] [rbp+18h]
  char *v166; // [rsp+128h] [rbp+20h] BYREF
  int v167; // [rsp+130h] [rbp+28h]
  int v168; // [rsp+134h] [rbp+2Ch]
  char v169[8]; // [rsp+138h] [rbp+30h] BYREF
  __m128d v170; // [rsp+140h] [rbp+38h]
  void *v171; // [rsp+158h] [rbp+50h] BYREF
  int v172; // [rsp+160h] [rbp+58h]
  _DWORD v173[2]; // [rsp+168h] [rbp+60h] BYREF
  double v174; // [rsp+170h] [rbp+68h]
  double v175; // [rsp+178h] [rbp+70h]
  bool v176; // [rsp+180h] [rbp+78h]
  void *Block[4]; // [rsp+188h] [rbp+80h] BYREF
  _DWORD *v178; // [rsp+1A8h] [rbp+A0h]
  _BYTE *v179; // [rsp+1B0h] [rbp+A8h]
  _BYTE *v180; // [rsp+1B8h] [rbp+B0h]
  double v181; // [rsp+1C0h] [rbp+B8h]
  signed __int64 v182; // [rsp+1C8h] [rbp+C0h]
  signed __int64 v183; // [rsp+1D0h] [rbp+C8h]
  __int64 v184; // [rsp+1D8h] [rbp+D0h]
  _DWORD *v185; // [rsp+1E0h] [rbp+D8h]
  _DWORD *v186; // [rsp+1E8h] [rbp+E0h]
  __int64 v187; // [rsp+1F0h] [rbp+E8h]
  HRGN v188; // [rsp+1F8h] [rbp+F0h]
  void *v189[4]; // [rsp+200h] [rbp+F8h] BYREF
  void *v190[4]; // [rsp+220h] [rbp+118h] BYREF
  void *v191[4]; // [rsp+240h] [rbp+138h] BYREF
  void *v192[4]; // [rsp+260h] [rbp+158h] BYREF
  void *v193; // [rsp+280h] [rbp+178h] BYREF
  unsigned __int64 v194; // [rsp+288h] [rbp+180h]
  RECT rect; // [rsp+2A0h] [rbp+198h] BYREF
  RECT v196; // [rsp+2B8h] [rbp+1B0h] BYREF

  v186 = a4;
  v185 = a3;
  v150 = a1;
  v187 = a5;
  v143 = a3[3] - (__int64)a3[1];
  if ( (unsigned __int64)(v143 + 0x80000000LL) > 0xFFFFFFFF
    || (v7 = a3[2] - (__int64)*a3, v151 = v7, (unsigned __int64)(v7 + 0x80000000LL) > 0xFFFFFFFF)
    || (v8 = a4[2] - (__int64)*a4, (unsigned __int64)(v8 + 0x80000000LL) > 0xFFFFFFFF)
    || (v9 = a4[3] - (__int64)a4[1], v152 = v9, (unsigned __int64)(v9 + 0x80000000LL) > 0xFFFFFFFF) )
  {
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  }
  v166 = 0;
  v167 = v8;
  v168 = v9;
  PatchPoints::PatchPoints(&v171, &v166);
  v126 = v172;
  v10 = 1;
  v11 = v172 - v172 % 4;
  if ( (int)v11 < 4 )
    v11 = 4;
  v129 = v11;
  *(_OWORD *)v144 = *(_OWORD *)a4;
  RectT<IntegerTypes>::OffsetRect(v144, (unsigned int)-*a3, (unsigned int)-a3[1]);
  v12 = v11;
  ho = (char *)v11;
  v13 = (char *)malloc(saturated_mul(v11, 0xCu));
  v162 = v13;
  if ( !v13 )
    ThrowOOM();
  v166 = v13;
  v14 = (_BYTE *)LargeAllocationNew<float>(v11, L"BlemishRemovalRedArray");
  v180 = v14;
  v15 = (_DWORD *)LargeAllocationNew<float>(v11, L"BlemishRemovalGreenArray");
  v178 = v15;
  v16 = (_BYTE *)LargeAllocationNew<float>(v12, L"BlemishRemovalBlueArray");
  v179 = v16;
  v17 = ((int)v8 + (int)v9) / 128;
  if ( v17 < 1 )
    v17 = 1;
  v137 = v17;
  v18 = 0.0;
  v163 = 0.0;
  v19 = 0.0;
  v165 = 0.0;
  v20 = 0.0;
  v164 = 0.0;
  v21 = 0.0;
  v22 = v129;
  if ( v129 > 0 )
  {
    v23 = v7 - 1;
    v134 = v7 - 1;
    v24 = 0;
    v130 = 0;
    v138 = (float *)v15;
    v149 = v162 + 8;
    v154 = v14 - (_BYTE *)v15;
    v153 = (float *)(v16 - (_BYTE *)v15);
    v25 = *(_DWORD *)v144;
    v26 = ho;
    v27 = v154;
    do
    {
      v28 = *((_QWORD *)v171 + v24 / v129);
      v29 = v28 + v25;
      v30 = HIDWORD(v28) + *(_DWORD *)&v144[4];
      v31 = a2 * (HIDWORD(v28) + *(_DWORD *)&v144[4]);
      v32 = 4LL * ((int)v28 + v25);
      v33 = (unsigned __int8 *)(v150 + v32 + v31);
      v34 = 1;
      if ( v29 == v23 )
        v34 = -1;
      v35 = (unsigned __int8 *)(v150 + v31 + 4LL * (v29 + v34));
      v36 = 1;
      if ( v30 == (_DWORD)v143 - 1 )
        v36 = -1;
      v37 = (unsigned __int8 *)(v150 + v32 + a2 * (v30 + v36));
      *(_DWORD *)((char *)v138 + v27) = dword_1805FA580[v33[2]];
      *(_DWORD *)v138 = dword_1805FA580[v33[1]];
      v38 = v153;
      *(_DWORD *)((char *)v138 + (_QWORD)v153) = dword_1805FA580[*v33];
      v39 = v29 - v25;
      v40 = v149;
      *(v149 - 2) = v39;
      *(v40 - 1) = v8 - v39 - 1;
      *v40 = v30 - *(_DWORD *)&v144[4];
      v163 = v18 + *(float *)((char *)v138 + v27);
      v165 = v19 + *v138;
      v164 = v20 + *(float *)((char *)v138 + (_QWORD)v38);
      v41 = *(float *)&dword_1805FA580[v33[2]] - *(float *)&dword_1805FA580[v35[2]];
      v42 = *(float *)&dword_1805FA580[v33[1]] - *(float *)&dword_1805FA580[v35[1]];
      v43 = *(float *)&dword_1805FA580[*v33] - *(float *)&dword_1805FA580[*v35];
      v44 = *(float *)&dword_1805FA580[v33[2]] - *(float *)&dword_1805FA580[v37[2]];
      v45 = *(float *)&dword_1805FA580[v33[1]] - *(float *)&dword_1805FA580[v37[1]];
      v46 = *(float *)&dword_1805FA580[*v33] - *(float *)&dword_1805FA580[*v37];
      v21 = v21
          + (float)((float)((float)(v41 * v41) + (float)(v42 * v42)) + (float)(v43 * v43))
          + (float)((float)((float)(v45 * v45) + (float)(v44 * v44)) + (float)(v46 * v46));
      v24 = v126 + v130;
      v130 += v126;
      v149 += 3;
      ++v138;
      --v26;
      v18 = v163;
      v19 = v165;
      v20 = v164;
      v23 = v134;
    }
    while ( v26 );
    v15 = v178;
    v16 = v179;
    v14 = v180;
    LODWORD(v9) = v152;
    LODWORD(v7) = v151;
    v22 = v129;
  }
  v47 = v21 / (double)(2 * v22);
  v155 = v22 / 5;
  *(_QWORD *)&rect.left = 0;
  rect.right = v7 - v8 + 1;
  rect.bottom = v143 - v9 + 1;
  v48 = CreateRectRgnIndirect(&rect);
  v188 = v48;
  *(_QWORD *)&v196.right = *(_QWORD *)&v144[8];
  v196.left = *(_DWORD *)v144 - v8 + 1;
  v196.top = 1 - v9 + *(_DWORD *)&v144[4];
  hoa = CreateRectRgnIndirect(&v196);
  CombineRgn(v48, v48, hoa, 4);
  if ( hoa )
    DeleteObject(hoa);
  RegionRects::RegionRects((RegionRects *)&v193, v48, 0x7FFFFFFF);
  v49 = 4;
  if ( (int)v194 < 4 )
    v49 = v194;
  v136 = v49;
  ListOfBestSourceMatches::ListOfBestSourceMatches((ListOfBestSourceMatches *)v192, 1);
  ListOfBestSourceMatches::ListOfBestSourceMatches((ListOfBestSourceMatches *)v191, 1);
  ListOfBestSourceMatches::ListOfBestSourceMatches((ListOfBestSourceMatches *)v190, 1);
  ListOfBestSourceMatches::ListOfBestSourceMatches((ListOfBestSourceMatches *)v189, 1);
  v50 = 0;
  if ( (int)v8 / 4 - v137 > 0 )
    v50 = (int)v8 / 4 - v137;
  v148 = v50;
  v51 = v137 / 2;
  if ( (int)v8 / 8 < v137 / 2 )
    v51 = (int)v8 / 8;
  v52 = 1;
  if ( v51 > 1 )
    v52 = v51;
  v160 = v52 - v137;
  v53 = sqrtf_0(0.5);
  v127 = (int)floor_0((float)((float)(int)v8 * v53) + 0.5);
  v54 = (int)floor_0((float)((float)(int)v9 * v53) + 0.5);
  v55 = v127 - 2;
  if ( v127 - 2 > 20 )
    v55 = 20;
  v159 = v55;
  v56 = v54 - 2;
  if ( v54 - 2 > 20 )
    v56 = 20;
  v158 = v56;
  if ( v55 <= 0 || v56 <= 0 )
  {
    v125 = 0;
    v57 = 0;
    v58 = 0;
  }
  else
  {
    v125 = 1;
    v57 = v127 / (v55 + 2);
    if ( v57 < 1 )
      v57 = 1;
    v58 = v54 / (v56 + 2);
    if ( v58 < 1 )
      v58 = 1;
  }
  v146 = v58;
  v147 = v57;
  v157 = v57 + ((int)v8 - v127) / 2;
  v156 = v58 + ((int)v9 - v54) / 2;
  v59 = v129;
  v181 = (float)((float)v129 * 3.0);
  v60 = (float)(0.5 / (float)v129);
  v61 = 0;
  v131 = 0;
  si128 = (__m128d)_mm_load_si128((const __m128i *)&_xmm);
  if ( v136 > 0 )
  {
    v154 = 0;
    v63 = 0;
    hob = 0;
    while ( 1 )
    {
      v64 = si128.m128d_f64[0];
      v170 = si128;
      if ( v61 < 0 )
        ATL::BaseAtlThrow(-2147024809);
      if ( v61 >= v194 )
        ATL::BaseAtlThrow(-2147024809);
      v65 = *(int *)((char *)v193 + (_QWORD)v63);
      v161 = *(_DWORD *)((char *)v193 + (_QWORD)v63);
      v135 = *(_DWORD *)((char *)v193 + (_QWORD)v63 + 8);
      v66 = *(_DWORD *)((char *)v193 + (_QWORD)v63 + 4);
      v139 = *(_DWORD *)((char *)v193 + (_QWORD)v63 + 12);
      if ( v66 < v139 )
        break;
LABEL_84:
      v131 = ++v61;
      ++v154;
      v63 += 16;
      hob = v63;
      if ( v154 >= v136 )
        goto LABEL_85;
    }
    v67 = 4 * v65;
    *(_QWORD *)v144 = 4 * v65;
    v68 = v66;
    v69 = a2 * v66;
    v128 = a2 * v66;
    v70 = v137;
    LODWORD(v149) = v137 * a2;
    *(_QWORD *)&v170.m128d_f64[1] = *(_OWORD *)&_mm_unpackhi_pd(si128, si128);
    v71 = v181;
LABEL_46:
    v72 = 0;
    v132 = 0;
    v73 = v67 + v69 + v150;
    *(_QWORD *)&rect.left = v73;
    v74 = v135;
LABEL_47:
    v75 = v73;
    v76 = v65;
    if ( (int)v65 >= v74 )
      goto LABEL_81;
    v184 = 4LL * v70;
    while ( 1 )
    {
      v77 = 0.0;
      v78 = 0.0;
      v79 = 0.0;
      v80 = 0.0;
      v81 = 0;
      v151 = 0;
      if ( v59 > 0 )
      {
        v153 = (float *)v15;
        v82 = v162;
        v83 = v162 + 8;
        v152 = (__int64)(v162 + 8);
        v182 = v14 - (_BYTE *)v15;
        v183 = v16 - (_BYTE *)v15;
        while ( 1 )
        {
          v84 = &v82[12 * v81];
          if ( v72 )
            v84 += 4;
          v85 = *(int *)v84;
          v86 = a2;
          v87 = v75 + a2 * *v83;
          v88 = *(float *)&dword_1805FA580[*(unsigned __int8 *)(v87 + 4 * v85 + 2)];
          v89 = *(float *)&dword_1805FA580[*(unsigned __int8 *)(v87 + 4 * v85 + 1)];
          v90 = *(float *)&dword_1805FA580[*(unsigned __int8 *)(v87 + 4 * v85)];
          v77 = v77
              + (v89 - *v153) * (v89 - *v153)
              + (v88 - *(float *)((char *)v153 + v182)) * (v88 - *(float *)((char *)v153 + v182))
              + (v90 - *(float *)((char *)v153 + v183)) * (v90 - *(float *)((char *)v153 + v183));
          if ( (v81 & 0xF) == 0xF && v77 > v170.m128d_f64[1] * 2.0 )
            break;
          v78 = v78 + v88;
          v79 = v79 + v89;
          v80 = v80 + v90;
          ++v81;
          ++v151;
          v83 = (_DWORD *)(v152 + 12);
          v152 += 12;
          ++v153;
          if ( v81 >= v59 )
          {
            v60 = (float)(0.5 / (float)v129);
            goto LABEL_61;
          }
          v72 = v132;
          v82 = v162;
        }
        if ( v151 < v155 )
        {
          v76 += v148;
          v75 += 4LL * v148;
        }
        goto LABEL_79;
      }
      v86 = a2;
LABEL_61:
      v91 = v78 - v163;
      v92 = v79 - v165;
      v93 = v80 - v164;
      v94 = v77;
      if ( (double)v129 * 0.3 > COERCE_DOUBLE(*(_QWORD *)&v92 & _xmm)
                              + COERCE_DOUBLE(*(_QWORD *)&v91 & _xmm)
                              + COERCE_DOUBLE(*(_QWORD *)&v93 & _xmm) )
        v77 = v77 - (v92 * v92 + v91 * v91 + v93 * v93) * v60;
      if ( v125 )
        v77 = v77
            + COERCE_DOUBLE(
                COERCE_UNSIGNED_INT64(sub_1803E69F4(v150, v86, v76 + v157, v68 + v156, v147, v146, v159, v158) - v47)
              & _xmm)
            * v71;
      if ( v64 > v77 )
        break;
      if ( v77 > v64 * 3.0 )
      {
        v96 = v148;
        goto LABEL_78;
      }
LABEL_79:
      v70 = v137;
      v76 += v137;
      v75 += v184;
      v74 = v135;
      v60 = (float)(0.5 / (float)v129);
      v59 = v129;
      v72 = v132;
      if ( v76 >= v135 )
      {
        LODWORD(v65) = v161;
        v73 = *(_QWORD *)&rect.left;
LABEL_81:
        v132 = ++v72;
        if ( v72 >= 2 )
        {
          v68 += v70;
          v69 = (_DWORD)v149 + v128;
          v128 += (int)v149;
          v67 = *(_QWORD *)v144;
          if ( v68 >= v139 )
          {
            v48 = v188;
            si128 = (__m128d)_mm_load_si128((const __m128i *)&_xmm);
            v63 = hob;
            v61 = v131;
            goto LABEL_84;
          }
          goto LABEL_46;
        }
        goto LABEL_47;
      }
    }
    v173[0] = v76;
    v173[1] = v68;
    v174 = v77;
    v175 = v94;
    v176 = v132 == 1;
    if ( v131 )
    {
      switch ( v131 )
      {
        case 1:
          ListOfBestSourceMatches::ApplyValue((ListOfBestSourceMatches *)v191, (const struct SourceMatch *)v173);
          v95 = v191;
          break;
        case 2:
          ListOfBestSourceMatches::ApplyValue((ListOfBestSourceMatches *)v190, (const struct SourceMatch *)v173);
          v95 = v190;
          break;
        case 3:
          ListOfBestSourceMatches::ApplyValue((ListOfBestSourceMatches *)v189, (const struct SourceMatch *)v173);
          v95 = v189;
          break;
        default:
LABEL_75:
          v96 = v160;
LABEL_78:
          v75 += 4 * v96;
          v76 += v96;
          goto LABEL_79;
      }
    }
    else
    {
      ListOfBestSourceMatches::ApplyValue((ListOfBestSourceMatches *)v192, (const struct SourceMatch *)v173);
      v95 = v192;
    }
    ListOfBestSourceMatches::GetWorst((ListOfBestSourceMatches *)v95, (struct SourceMatch *)v169);
    v64 = v170.m128d_f64[0];
    goto LABEL_75;
  }
LABEL_85:
  ListOfBestSourceMatches::ListOfBestSourceMatches((ListOfBestSourceMatches *)Block, 4);
  *(_QWORD *)v144 = 0;
  *(__m128d *)&v144[8] = si128;
  v145 = 0;
  ListOfBestSourceMatches::GetBest((ListOfBestSourceMatches *)v192, (struct SourceMatch *)v144);
  ListOfBestSourceMatches::ApplyValue((ListOfBestSourceMatches *)Block, (const struct SourceMatch *)v144);
  ListOfBestSourceMatches::GetBest((ListOfBestSourceMatches *)v191, (struct SourceMatch *)v144);
  ListOfBestSourceMatches::ApplyValue((ListOfBestSourceMatches *)Block, (const struct SourceMatch *)v144);
  ListOfBestSourceMatches::GetBest((ListOfBestSourceMatches *)v190, (struct SourceMatch *)v144);
  ListOfBestSourceMatches::ApplyValue((ListOfBestSourceMatches *)Block, (const struct SourceMatch *)v144);
  ListOfBestSourceMatches::GetBest((ListOfBestSourceMatches *)v189, (struct SourceMatch *)v144);
  ListOfBestSourceMatches::ApplyValue((ListOfBestSourceMatches *)Block, (const struct SourceMatch *)v144);
  ListOfBestSourceMatches::GetBest((ListOfBestSourceMatches *)Block, (struct SourceMatch *)v144);
  v97 = v185;
  v98 = v186;
  v99 = v187;
  *(_DWORD *)(v187 + 16) = *(_DWORD *)v144 + *v185 - *v186;
  *(_DWORD *)(v99 + 20) = *(_DWORD *)&v144[4] + v97[1] - v98[1];
  *(_OWORD *)v99 = *(_OWORD *)v98;
  *(_DWORD *)(v99 + 24) = v145;
  if ( *(double *)&v144[8] == 3.399999975603521e28 )
    v10 = 0;
  v100 = Block[0];
  if ( Block[0] )
  {
    if ( ImagingEngine::s_singleton )
      v101 = *((_QWORD *)ImagingEngine::s_singleton + 10);
    else
      v101 = 0;
    if ( v101 )
    {
      v102 = (*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v101 + 88LL))(v101, Block[0]) == 0;
      v100 = Block[0];
    }
    else
    {
      v102 = 0;
    }
    if ( !v102 && v100 )
      free(v100);
    Block[0] = 0;
  }
  v103 = v189[0];
  if ( v189[0] )
  {
    if ( ImagingEngine::s_singleton )
      v104 = *((_QWORD *)ImagingEngine::s_singleton + 10);
    else
      v104 = 0;
    if ( v104 )
    {
      v105 = (*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v104 + 88LL))(v104, v189[0]) == 0;
      v103 = v189[0];
    }
    else
    {
      v105 = 0;
    }
    if ( !v105 && v103 )
      free(v103);
    v189[0] = 0;
  }
  v106 = v190[0];
  if ( v190[0] )
  {
    if ( ImagingEngine::s_singleton )
      v107 = *((_QWORD *)ImagingEngine::s_singleton + 10);
    else
      v107 = 0;
    if ( v107 )
    {
      v108 = (*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v107 + 88LL))(v107, v190[0]) == 0;
      v106 = v190[0];
    }
    else
    {
      v108 = 0;
    }
    if ( !v108 && v106 )
      free(v106);
    v190[0] = 0;
  }
  v109 = v191[0];
  if ( v191[0] )
  {
    if ( ImagingEngine::s_singleton )
      v110 = *((_QWORD *)ImagingEngine::s_singleton + 10);
    else
      v110 = 0;
    if ( v110 )
    {
      v111 = (*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v110 + 88LL))(v110, v191[0]) == 0;
      v109 = v191[0];
    }
    else
    {
      v111 = 0;
    }
    if ( !v111 && v109 )
      free(v109);
    v191[0] = 0;
  }
  v112 = v192[0];
  if ( v192[0] )
  {
    if ( ImagingEngine::s_singleton )
      v113 = *((_QWORD *)ImagingEngine::s_singleton + 10);
    else
      v113 = 0;
    if ( v113 )
    {
      v114 = (*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v113 + 88LL))(v113, v192[0]) == 0;
      v112 = v192[0];
    }
    else
    {
      v114 = 0;
    }
    if ( !v114 && v112 )
      free(v112);
    v192[0] = 0;
  }
  if ( v193 )
    free(v193);
  if ( v48 )
    DeleteObject(v48);
  if ( v16 )
  {
    v115 = ImagingEngine::s_singleton ? *((_QWORD *)ImagingEngine::s_singleton + 10) : 0LL;
    if ( !v115 || (*(unsigned int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v115 + 88LL))(v115, v16) != 0 )
      free(v16);
  }
  if ( v15 )
  {
    v117 = ImagingEngine::s_singleton ? *((_QWORD *)ImagingEngine::s_singleton + 10) : 0LL;
    if ( !v117 || (*(unsigned int (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v117 + 88LL))(v117, v15) != 0 )
      free(v15);
  }
  if ( v14 )
  {
    v119 = ImagingEngine::s_singleton ? *((_QWORD *)ImagingEngine::s_singleton + 10) : 0LL;
    if ( !v119 || (*(unsigned int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v119 + 88LL))(v119, v14) != 0 )
      free(v14);
  }
  Base::Ptr<ClonePeripheryData>::~Ptr<ClonePeripheryData>(&v166);
  v121 = v171;
  if ( v171 )
  {
    if ( ImagingEngine::s_singleton )
      v122 = *((_QWORD *)ImagingEngine::s_singleton + 10);
    else
      v122 = 0;
    if ( v122 )
    {
      v123 = (*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v122 + 88LL))(v122, v171) == 0;
      v121 = v171;
    }
    else
    {
      v123 = 0;
    }
    if ( !v123 && v121 )
      free(v121);
  }
  return v10;
}

```

## disassembly

```asm
0x1803e2628  mov     rax, rsp
0x1803e262b  push    rbp
0x1803e262c  push    rbx
0x1803e262d  push    rsi
0x1803e262e  push    rdi
0x1803e262f  push    r12
0x1803e2631  push    r13
0x1803e2633  push    r14
0x1803e2635  push    r15
0x1803e2637  lea     rbp, [rax-2A8h]
0x1803e263e  sub     rsp, 368h
0x1803e2645  movaps  xmmword ptr [rax-58h], xmm6
0x1803e2649  movaps  xmmword ptr [rax-68h], xmm7
0x1803e264d  movaps  xmmword ptr [rax-78h], xmm8
0x1803e2652  movaps  xmmword ptr [rax-88h], xmm9
0x1803e265a  movaps  xmmword ptr [rax-98h], xmm10
0x1803e2662  movaps  xmmword ptr [rax-0A8h], xmm11
0x1803e266a  movaps  xmmword ptr [rax-0B8h], xmm13
0x1803e2672  movaps  xmmword ptr [rax-0C8h], xmm14
0x1803e267a  movaps  xmmword ptr [rax-0D8h], xmm15
0x1803e2682  mov     rax, cs:__security_cookie
0x1803e2689  xor     rax, rsp
0x1803e268c  mov     [rbp+2A0h+var_E0], rax
0x1803e2693  mov     rdi, r9
0x1803e2696  mov     [rbp+2A0h+var_1C0], r9
0x1803e269d  mov     rsi, r8
0x1803e26a0  mov     [rbp+2A0h+var_1C8], r8
0x1803e26a7  mov     [rsp+3A0h+var_34C], edx
0x1803e26ab  mov     [rbp+2A0h+var_2E8], rcx
0x1803e26af  mov     rax, [rbp+2A0h+arg_20]
0x1803e26b6  mov     [rbp+2A0h+var_1B8], rax
0x1803e26bd  movsxd  rax, dword ptr [r8+4]
0x1803e26c1  movsxd  rcx, dword ptr [r8+0Ch]
0x1803e26c5  sub     rcx, rax
0x1803e26c8  mov     [rsp+3A0h+var_328], rcx
0x1803e26cd  mov     edx, 80000000h
0x1803e26d2  lea     rax, [rcx+rdx]
0x1803e26d6  mov     ecx, 0FFFFFFFFh
0x1803e26db  cmp     rax, rcx
0x1803e26de  ja      loc_1803E369C
0x1803e26e4  movsxd  rax, dword ptr [r8]
0x1803e26e7  movsxd  r14, dword ptr [r8+8]
0x1803e26eb  sub     r14, rax
0x1803e26ee  mov     [rbp+2A0h+var_2E0], r14
0x1803e26f2  lea     rax, [r14+rdx]
0x1803e26f6  cmp     rax, rcx
0x1803e26f9  ja      loc_1803E369C
0x1803e26ff  movsxd  rax, dword ptr [r9]
0x1803e2702  movsxd  r12, dword ptr [r9+8]
0x1803e2706  sub     r12, rax
0x1803e2709  lea     rax, [rdx+r12]
0x1803e270d  cmp     rax, rcx
0x1803e2710  ja      loc_1803E369C
0x1803e2716  movsxd  rax, dword ptr [r9+4]
0x1803e271a  movsxd  r13, dword ptr [r9+0Ch]
0x1803e271e  sub     r13, rax
0x1803e2721  mov     [rbp+2A0h+var_2D8], r13
0x1803e2725  lea     rax, [rdx+r13]
0x1803e2729  cmp     rax, rcx
0x1803e272c  ja      loc_1803E369C
0x1803e2732  mov     [rbp+2A0h+var_280], 0
0x1803e273a  mov     [rbp+2A0h+var_278], r12d
0x1803e273e  mov     [rbp+2A0h+var_274], r13d
0x1803e2742  lea     rdx, [rbp+2A0h+var_280]
0x1803e2746  lea     rcx, [rbp+2A0h+var_250]
0x1803e274a  call    ??0PatchPoints@@QEAA@U?$RectT@UIntegerTypes@@@@@Z; PatchPoints::PatchPoints(RectT<IntegerTypes>)
0x1803e274f  mov     ecx, [rbp+2A0h+var_248]
0x1803e2752  mov     [rsp+3A0h+var_35C], ecx
0x1803e2756  mov     eax, ecx
0x1803e2758  mov     r15d, 1
0x1803e275e  and     eax, 80000003h
0x1803e2763  jge     short loc_1803E276E
0x1803e2765  sub     eax, r15d
0x1803e2768  or      eax, 0FFFFFFFCh
0x1803e276b  add     eax, r15d
0x1803e276e  mov     ebx, ecx
0x1803e2770  sub     ebx, eax
0x1803e2772  mov     eax, 4
0x1803e2777  cmp     ebx, eax
0x1803e2779  cmovl   ebx, eax
0x1803e277c  mov     [rsp+3A0h+var_358], ebx
0x1803e2780  movups  xmm0, xmmword ptr [rdi]
0x1803e2783  movdqu  xmmword ptr [rbp+2A0h+var_320], xmm0
0x1803e2788  mov     r8d, [rsi+4]
0x1803e278c  neg     r8d
0x1803e278f  mov     edx, [rsi]
0x1803e2791  neg     edx
0x1803e2793  lea     rcx, [rbp+2A0h+var_320]
0x1803e2797  call    ?OffsetRect@?$RectT@UIntegerTypes@@@@QEAAXHH@Z; RectT<IntegerTypes>::OffsetRect(int,int)
0x1803e279c  mov     edi, ebx
0x1803e279e  mov     [rsp+3A0h+ho], rdi
0x1803e27a3  mov     eax, 0Ch
0x1803e27a8  mul     rdi
0x1803e27ab  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1803e27b2  cmovb   rax, rcx
0x1803e27b6  mov     rcx, rax; Size
0x1803e27b9  call    cs:__imp_malloc
0x1803e27bf  mov     [rbp+2A0h+var_2A0], rax
0x1803e27c3  test    rax, rax
0x1803e27c6  jz      loc_1803E36A5
0x1803e27cc  mov     [rbp+2A0h+var_280], rax
0x1803e27d0  lea     rdx, aBlemishremoval_8; "BlemishRemovalRedArray"
0x1803e27d7  mov     ecx, edi
0x1803e27d9  call    ??$LargeAllocationNew@M@@YAPEAM_KPEB_W@Z; LargeAllocationNew<float>(unsigned __int64,wchar_t const *)
0x1803e27de  mov     rsi, rax
0x1803e27e1  mov     [rbp+2A0h+var_1F0], rax
0x1803e27e8  lea     rdx, aBlemishremoval_2; "BlemishRemovalGreenArray"
0x1803e27ef  mov     ecx, edi
0x1803e27f1  call    ??$LargeAllocationNew@M@@YAPEAM_KPEB_W@Z; LargeAllocationNew<float>(unsigned __int64,wchar_t const *)
0x1803e27f6  mov     rbx, rax
0x1803e27f9  mov     [rbp+2A0h+var_200], rax
0x1803e2800  lea     rdx, aBlemishremoval; "BlemishRemovalBlueArray"
0x1803e2807  mov     ecx, edi
0x1803e2809  call    ??$LargeAllocationNew@M@@YAPEAM_KPEB_W@Z; LargeAllocationNew<float>(unsigned __int64,wchar_t const *)
0x1803e280e  mov     rdi, rax
0x1803e2811  mov     [rbp+2A0h+var_1F8], rax
0x1803e2818  lea     eax, [r12+r13]
0x1803e281c  cdq
0x1803e281d  and     edx, 7Fh
0x1803e2820  add     eax, edx
0x1803e2822  sar     eax, 7
0x1803e2825  cmp     eax, r15d
0x1803e2828  cmovl   eax, r15d
0x1803e282c  mov     dword ptr [rsp+3A0h+var_340], eax
0x1803e2830  xorps   xmm1, xmm1
0x1803e2833  movsd   [rbp+2A0h+var_298], xmm1
0x1803e2838  xorps   xmm2, xmm2
0x1803e283b  movsd   [rbp+2A0h+var_288], xmm2
0x1803e2840  xorps   xmm3, xmm3
0x1803e2843  movsd   [rbp+2A0h+var_290], xmm3
0x1803e2848  xorps   xmm14, xmm14
0x1803e284c  mov     ecx, [rsp+3A0h+var_358]
0x1803e2850  test    ecx, ecx
0x1803e2852  jle     loc_1803E2AB0
0x1803e2858  lea     r10d, [r14-1]
0x1803e285c  mov     [rsp+3A0h+var_348], r10d
0x1803e2861  mov     rax, [rsp+3A0h+var_328]
0x1803e2866  dec     eax
0x1803e2868  mov     [rsp+3A0h+var_344], eax
0x1803e286c  xor     ecx, ecx
0x1803e286e  mov     [rsp+3A0h+var_354], ecx
0x1803e2872  mov     [rsp+3A0h+var_338], rbx
0x1803e2877  mov     rax, [rbp+2A0h+var_2A0]
0x1803e287b  add     rax, 8
0x1803e287f  mov     [rbp+2A0h+var_2F0], rax
0x1803e2883  mov     rax, rsi
0x1803e2886  sub     rax, rbx
0x1803e2889  mov     [rbp+2A0h+var_2C8], rax
0x1803e288d  mov     rax, rdi
0x1803e2890  sub     rax, rbx
0x1803e2893  mov     [rbp+2A0h+var_2D0], rax
0x1803e2897  mov     esi, [rsp+3A0h+var_358]
0x1803e289b  mov     edi, dword ptr [rbp+2A0h+var_320]
0x1803e289e  mov     rbx, [rsp+3A0h+ho]
0x1803e28a3  mov     r14, [rbp+2A0h+var_2C8]
0x1803e28a7  mov     eax, ecx
0x1803e28a9  cdq
0x1803e28aa  idiv    esi
0x1803e28ac  movsxd  rcx, eax
0x1803e28af  mov     rax, [rbp+2A0h+var_250]
0x1803e28b3  mov     rax, [rax+rcx*8]
0x1803e28b7  lea     r8d, [rax+rdi]
0x1803e28bb  shr     rax, 20h
0x1803e28bf  mov     r9d, dword ptr [rbp+2A0h+var_320+4]
0x1803e28c3  add     r9d, eax
0x1803e28c6  mov     eax, r9d
0x1803e28c9  imul    eax, [rsp+3A0h+var_34C]
0x1803e28ce  movsxd  rcx, eax
0x1803e28d1  movsxd  rax, r8d
0x1803e28d4  lea     rdx, ds:0[rax*4]
0x1803e28dc  lea     r11, [rdx+rcx]
0x1803e28e0  add     r11, [rbp+2A0h+var_2E8]
0x1803e28e4  mov     eax, r15d
0x1803e28e7  cmp     r8d, r10d
0x1803e28ea  mov     r10, 0FFFFFFFFFFFFFFFFh
0x1803e28f1  cmovz   eax, r10d
0x1803e28f5  add     eax, r8d
0x1803e28f8  cdqe
0x1803e28fa  lea     r10, [rcx+rax*4]
0x1803e28fe  add     r10, [rbp+2A0h+var_2E8]
0x1803e2902  mov     eax, r15d
0x1803e2905  cmp     r9d, [rsp+3A0h+var_344]
0x1803e290a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1803e2911  cmovz   eax, ecx
0x1803e2914  add     eax, r9d
0x1803e2917  imul    eax, [rsp+3A0h+var_34C]
0x1803e291c  movsxd  rcx, eax
0x1803e291f  add     rcx, rdx
0x1803e2922  add     rcx, [rbp+2A0h+var_2E8]
0x1803e2926  movzx   eax, byte ptr [r11+2]
0x1803e292b  lea     r13, dword_1805FA580
0x1803e2932  mov     eax, [r13+rax*4+0]
0x1803e2937  mov     rdx, [rsp+3A0h+var_338]
0x1803e293c  mov     [rdx+r14], eax
0x1803e2940  movzx   eax, byte ptr [r11+1]
0x1803e2945  mov     eax, [r13+rax*4+0]
0x1803e294a  mov     [rdx], eax
0x1803e294c  movzx   eax, byte ptr [r11]
0x1803e2950  mov     eax, [r13+rax*4+0]
0x1803e2955  mov     rdx, [rbp+2A0h+var_2D0]
0x1803e2959  mov     r13, [rsp+3A0h+var_338]
0x1803e295e  mov     [rdx+r13], eax
0x1803e2962  sub     r8d, edi
0x1803e2965  mov     r13, [rbp+2A0h+var_2F0]
0x1803e2969  mov     [r13-8], r8d
0x1803e296d  mov     eax, r12d
0x1803e2970  sub     eax, r8d
0x1803e2973  sub     eax, r15d
0x1803e2976  mov     [r13-4], eax
0x1803e297a  sub     r9d, dword ptr [rbp+2A0h+var_320+4]
0x1803e297e  mov     [r13+0], r9d
0x1803e2982  mov     r8, [rsp+3A0h+var_338]
0x1803e2987  movss   xmm0, dword ptr [r8+r14]
0x1803e298d  cvtps2pd xmm0, xmm0
0x1803e2990  addsd   xmm1, xmm0
0x1803e2994  movsd   [rbp+2A0h+var_298], xmm1
0x1803e2999  movss   xmm1, dword ptr [r8]
0x1803e299e  cvtps2pd xmm1, xmm1
0x1803e29a1  addsd   xmm2, xmm1
0x1803e29a5  movsd   [rbp+2A0h+var_288], xmm2
0x1803e29aa  movss   xmm0, dword ptr [rdx+r8]
0x1803e29b0  cvtps2pd xmm0, xmm0
0x1803e29b3  addsd   xmm3, xmm0
0x1803e29b7  movsd   [rbp+2A0h+var_290], xmm3
0x1803e29bc  movzx   eax, byte ptr [r11+2]
0x1803e29c1  lea     rdx, dword_1805FA580
0x1803e29c8  movss   xmm5, dword ptr [rdx+rax*4]
0x1803e29cd  movzx   eax, byte ptr [r10+2]
0x1803e29d2  movaps  xmm3, xmm5
0x1803e29d5  subss   xmm3, dword ptr [rdx+rax*4]
0x1803e29da  movzx   eax, byte ptr [r11+1]
0x1803e29df  movss   xmm4, dword ptr [rdx+rax*4]
0x1803e29e4  movzx   eax, byte ptr [r10+1]
0x1803e29e9  movaps  xmm1, xmm4
0x1803e29ec  subss   xmm1, dword ptr [rdx+rax*4]
0x1803e29f1  movzx   eax, byte ptr [r11]
0x1803e29f5  movss   xmm2, dword ptr [rdx+rax*4]
0x1803e29fa  movzx   eax, byte ptr [r10]
0x1803e29fe  movaps  xmm0, xmm2
0x1803e2a01  subss   xmm0, dword ptr [rdx+rax*4]
0x1803e2a06  movzx   eax, byte ptr [rcx+2]
0x1803e2a0a  subss   xmm5, dword ptr [rdx+rax*4]
0x1803e2a0f  movzx   eax, byte ptr [rcx+1]
0x1803e2a13  subss   xmm4, dword ptr [rdx+rax*4]
0x1803e2a18  movzx   eax, byte ptr [rcx]
0x1803e2a1b  subss   xmm2, dword ptr [rdx+rax*4]
0x1803e2a20  mulss   xmm3, xmm3
0x1803e2a24  mulss   xmm1, xmm1
0x1803e2a28  addss   xmm3, xmm1
0x1803e2a2c  mulss   xmm0, xmm0
0x1803e2a30  addss   xmm3, xmm0
0x1803e2a34  cvtps2pd xmm1, xmm3
0x1803e2a37  addsd   xmm14, xmm1
0x1803e2a3c  mulss   xmm4, xmm4
0x1803e2a40  mulss   xmm5, xmm5
0x1803e2a44  addss   xmm4, xmm5
0x1803e2a48  mulss   xmm2, xmm2
0x1803e2a4c  addss   xmm4, xmm2
0x1803e2a50  cvtps2pd xmm0, xmm4
0x1803e2a53  addsd   xmm14, xmm0
0x1803e2a58  mov     ecx, [rsp+3A0h+var_354]
0x1803e2a5c  add     ecx, [rsp+3A0h+var_35C]
0x1803e2a60  mov     [rsp+3A0h+var_354], ecx
0x1803e2a64  add     [rbp+2A0h+var_2F0], 0Ch
0x1803e2a69  add     r8, 4
0x1803e2a6d  mov     [rsp+3A0h+var_338], r8
0x1803e2a72  sub     rbx, r15
0x1803e2a75  movsd   xmm1, [rbp+2A0h+var_298]
0x1803e2a7a  movsd   xmm2, [rbp+2A0h+var_288]
0x1803e2a7f  movsd   xmm3, [rbp+2A0h+var_290]
0x1803e2a84  mov     r10d, [rsp+3A0h+var_348]
0x1803e2a89  jnz     loc_1803E28A7
0x1803e2a8f  mov     rbx, [rbp+2A0h+var_200]
0x1803e2a96  mov     rdi, [rbp+2A0h+var_1F8]
0x1803e2a9d  mov     rsi, [rbp+2A0h+var_1F0]
0x1803e2aa4  mov     r13, [rbp+2A0h+var_2D8]
0x1803e2aa8  mov     r14, [rbp+2A0h+var_2E0]
0x1803e2aac  mov     ecx, [rsp+3A0h+var_358]
0x1803e2ab0  lea     eax, [rcx+rcx]
0x1803e2ab3  movd    xmm0, eax
0x1803e2ab7  cvtdq2pd xmm0, xmm0
0x1803e2abb  divsd   xmm14, xmm0
0x1803e2ac0  mov     eax, 66666667h
0x1803e2ac5  imul    ecx
0x1803e2ac7  mov     ecx, edx
0x1803e2ac9  sar     ecx, 1
0x1803e2acb  mov     eax, ecx
0x1803e2acd  shr     eax, 1Fh
0x1803e2ad0  add     ecx, eax
0x1803e2ad2  mov     [rbp+2A0h+var_2C0], ecx
0x1803e2ad5  mov     qword ptr [rbp+2A0h+rect.left], 0
0x1803e2ae0  sub     r14d, r12d
0x1803e2ae3  add     r14d, r15d
0x1803e2ae6  mov     [rbp+2A0h+rect.right], r14d
0x1803e2aed  mov     rax, [rsp+3A0h+var_328]
0x1803e2af2  sub     eax, r13d
0x1803e2af5  add     eax, r15d
0x1803e2af8  mov     [rbp+2A0h+rect.bottom], eax
0x1803e2afe  lea     rcx, [rbp+2A0h+rect]; lprect
0x1803e2b05  call    cs:__imp_CreateRectRgnIndirect
  ... truncated ...
```
