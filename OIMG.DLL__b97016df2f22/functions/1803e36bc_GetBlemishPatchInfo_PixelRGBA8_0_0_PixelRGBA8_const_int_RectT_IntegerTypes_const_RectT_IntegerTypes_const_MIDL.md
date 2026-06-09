# GetBlemishPatchInfo<PixelRGBA8,0,0>(PixelRGBA8 const *,int,RectT<IntegerTypes> const &,RectT<IntegerTypes> const &,__MIDL___MIDL_itf_Imaging_0001_0125_0001 *)

- ea: `0x1803e36bc`
- end: `0x1803e4791`
- name: `??$GetBlemishPatchInfo@UPixelRGBA8@@$0A@$0A@@@YA_NPEBUPixelRGBA8@@HAEBU?$RectT@UIntegerTypes@@@@1PEAU__MIDL___MIDL_itf_Imaging_0001_0125_0001@@@Z`
- size: `4309`
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
- `0x1803e36bc`
- `0x1803e6884`
- `0x1803e69f4`
- `0x1804c6944`
- `0x18056bd00`
- `0x18056dc8e`
- `0x18056dcca`
- `0x18056dce0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1803e384b`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1803e384b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e4426`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e4486`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e44e6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e4546`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e45a6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e45bf`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e4615`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e465c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e46a3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e4703`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e4426`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e4486`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e44e6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e4546`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e45a6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e45bf`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e4615`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e465c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e46a3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e4703`
- `GDI32!CombineRgn` at `0x1803e3c18`
- `GDI32!CombineRgn` at `0x1803e3c18`
- `GDI32!DeleteObject` at `0x1803e3c27`
- `GDI32!DeleteObject` at `0x1803e45ce`
- `GDI32!DeleteObject` at `0x1803e3c27`
- `GDI32!DeleteObject` at `0x1803e45ce`
- `GDI32!CreateRectRgnIndirect` at `0x1803e3bc1`
- `GDI32!CreateRectRgnIndirect` at `0x1803e3bff`
- `GDI32!CreateRectRgnIndirect` at `0x1803e3bc1`
- `GDI32!CreateRectRgnIndirect` at `0x1803e3bff`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
char __fastcall GetBlemishPatchInfo<PixelRGBA8,0,0>(__int64 a1, int a2, int *a3, int *a4, __int64 a5)
{
  __int64 v7; // r12
  __int64 v8; // r13
  char v9; // r15
  unsigned int v10; // r14d
  char *v11; // rax
  _BYTE *v12; // rsi
  _DWORD *v13; // rbx
  _BYTE *v14; // rdi
  int v15; // eax
  double v16; // xmm1_8
  double v17; // xmm2_8
  double v18; // xmm3_8
  double v19; // xmm15_8
  int v20; // r8d
  int v21; // ecx
  int v22; // r10d
  int v23; // r11d
  __int64 v24; // rax
  int v25; // r8d
  int v26; // eax
  __int64 v27; // r9
  char *v28; // rcx
  int v29; // edx
  unsigned __int8 *v30; // r8
  int v31; // edx
  char *v32; // r9
  unsigned __int8 *v33; // rdx
  signed __int64 v34; // r14
  float v35; // xmm3_4
  float v36; // xmm1_4
  float v37; // xmm0_4
  float v38; // xmm5_4
  float v39; // xmm4_4
  float v40; // xmm2_4
  double v41; // xmm15_8
  HRGN v42; // r14
  int v43; // eax
  int v44; // ecx
  int v45; // ecx
  int v46; // eax
  float v47; // xmm7_4
  int v48; // r9d
  int v49; // eax
  int v50; // r10d
  int v51; // r11d
  int v52; // ecx
  int v53; // r12d
  double v54; // xmm13_8
  int v55; // r8d
  __m128d si128; // xmm14
  char *v57; // rdx
  double v58; // xmm8_8
  __int64 v59; // r10
  int v60; // ecx
  __int64 v61; // r8
  int v62; // r14d
  int v63; // eax
  int v64; // ecx
  double v65; // xmm14_8
  int v66; // edx
  __int64 v67; // r8
  int v68; // eax
  __int64 v69; // r9
  int v70; // r13d
  double v71; // xmm6_8
  double v72; // xmm5_8
  double v73; // xmm4_8
  double v74; // xmm7_8
  int v75; // r10d
  float *v76; // r11
  char *v77; // rdx
  _DWORD *v78; // rax
  char *v79; // rdx
  __int64 v80; // rcx
  __int64 v81; // rdx
  double v82; // xmm9_8
  double v83; // xmm10_8
  double v84; // xmm11_8
  double v85; // xmm5_8
  double v86; // xmm4_8
  double v87; // xmm7_8
  double v88; // xmm9_8
  void **v89; // rcx
  __int64 v90; // rax
  _DWORD *v91; // rdx
  _DWORD *v92; // rcx
  __int64 v93; // r8
  void *v94; // rcx
  __int64 v95; // r8
  bool v96; // al
  void *v97; // rcx
  __int64 v98; // r8
  bool v99; // al
  void *v100; // rcx
  __int64 v101; // r8
  bool v102; // al
  void *v103; // rcx
  __int64 v104; // r8
  bool v105; // al
  void *v106; // rcx
  __int64 v107; // r8
  bool v108; // al
  __int64 v109; // rcx
  __int64 v111; // rcx
  __int64 v113; // rcx
  void *v115; // rcx
  __int64 v116; // r8
  bool v117; // al
  char v119; // [rsp+48h] [rbp-C0h]
  int v120; // [rsp+4Ch] [rbp-BCh]
  int v121; // [rsp+4Ch] [rbp-BCh]
  int v122; // [rsp+4Ch] [rbp-BCh]
  int v123; // [rsp+50h] [rbp-B8h]
  int v124; // [rsp+50h] [rbp-B8h]
  int v125; // [rsp+54h] [rbp-B4h]
  int v126; // [rsp+54h] [rbp-B4h]
  int v127; // [rsp+58h] [rbp-B0h]
  int v128; // [rsp+58h] [rbp-B0h]
  int v130; // [rsp+60h] [rbp-A8h]
  int v131; // [rsp+60h] [rbp-A8h]
  __int64 v132; // [rsp+68h] [rbp-A0h]
  __int64 v133; // [rsp+68h] [rbp-A0h]
  int v134; // [rsp+70h] [rbp-98h]
  int v135; // [rsp+70h] [rbp-98h]
  float *v136; // [rsp+78h] [rbp-90h]
  int v137; // [rsp+78h] [rbp-90h]
  int v138; // [rsp+80h] [rbp-88h]
  _DWORD *v139; // [rsp+88h] [rbp-80h]
  __int64 v140; // [rsp+88h] [rbp-80h]
  char *ho; // [rsp+90h] [rbp-78h]
  HRGN hoa; // [rsp+90h] [rbp-78h]
  char *hob; // [rsp+90h] [rbp-78h]
  signed __int64 v144; // [rsp+98h] [rbp-70h]
  double v145; // [rsp+98h] [rbp-70h]
  _BYTE v146[24]; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int8 v147; // [rsp+C0h] [rbp-48h]
  int v148; // [rsp+C8h] [rbp-40h]
  int v149; // [rsp+CCh] [rbp-3Ch]
  signed __int64 v150; // [rsp+D0h] [rbp-38h]
  unsigned __int8 *v151; // [rsp+D8h] [rbp-30h]
  __int64 v152; // [rsp+E0h] [rbp-28h]
  __int64 v153; // [rsp+E8h] [rbp-20h]
  int v154; // [rsp+F0h] [rbp-18h]
  int v155; // [rsp+F4h] [rbp-14h]
  int v156; // [rsp+F8h] [rbp-10h]
  int v157; // [rsp+FCh] [rbp-Ch]
  int v158; // [rsp+100h] [rbp-8h]
  int v159; // [rsp+104h] [rbp-4h]
  int v160; // [rsp+108h] [rbp+0h]
  char *v161; // [rsp+110h] [rbp+8h]
  double v162; // [rsp+118h] [rbp+10h]
  double v163; // [rsp+120h] [rbp+18h]
  double v164; // [rsp+128h] [rbp+20h]
  _BYTE *v165; // [rsp+138h] [rbp+30h] BYREF
  int v166; // [rsp+140h] [rbp+38h]
  int v167; // [rsp+144h] [rbp+3Ch]
  char v168[8]; // [rsp+148h] [rbp+40h] BYREF
  __m128d v169; // [rsp+150h] [rbp+48h]
  void *v170; // [rsp+168h] [rbp+60h] BYREF
  int v171; // [rsp+170h] [rbp+68h]
  _DWORD v172[2]; // [rsp+178h] [rbp+70h] BYREF
  double v173; // [rsp+180h] [rbp+78h]
  double v174; // [rsp+188h] [rbp+80h]
  bool v175; // [rsp+190h] [rbp+88h]
  void *Block[4]; // [rsp+198h] [rbp+90h] BYREF
  HRGN v177; // [rsp+1B8h] [rbp+B0h]
  _DWORD *v178; // [rsp+1C0h] [rbp+B8h]
  _DWORD *v179; // [rsp+1C8h] [rbp+C0h]
  __int64 v180; // [rsp+1D0h] [rbp+C8h]
  char *v181; // [rsp+1D8h] [rbp+D0h] BYREF
  double v182; // [rsp+1E0h] [rbp+D8h]
  signed __int64 v183; // [rsp+1E8h] [rbp+E0h]
  signed __int64 v184; // [rsp+1F0h] [rbp+E8h]
  __int64 v185; // [rsp+1F8h] [rbp+F0h]
  void *v186[4]; // [rsp+200h] [rbp+F8h] BYREF
  void *v187[4]; // [rsp+220h] [rbp+118h] BYREF
  void *v188[4]; // [rsp+240h] [rbp+138h] BYREF
  void *v189[4]; // [rsp+260h] [rbp+158h] BYREF
  void *v190; // [rsp+280h] [rbp+178h] BYREF
  unsigned __int64 v191; // [rsp+288h] [rbp+180h]
  _DWORD *v192; // [rsp+2A0h] [rbp+198h]
  _BYTE *v193; // [rsp+2A8h] [rbp+1A0h]
  RECT rect; // [rsp+2B0h] [rbp+1A8h] BYREF
  RECT v195; // [rsp+2C8h] [rbp+1C0h] BYREF

  v179 = a4;
  v178 = a3;
  v152 = a1;
  v180 = a5;
  v153 = a3[3] - (__int64)a3[1];
  if ( (unsigned __int64)(v153 + 0x80000000LL) > 0xFFFFFFFF
    || (v132 = a3[2] - (__int64)*a3, (unsigned __int64)(v132 + 0x80000000LL) > 0xFFFFFFFF)
    || (v7 = a4[2] - (__int64)*a4, (unsigned __int64)(v7 + 0x80000000LL) > 0xFFFFFFFF)
    || (v8 = a4[3] - (__int64)a4[1], (unsigned __int64)(v8 + 0x80000000LL) > 0xFFFFFFFF) )
  {
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  }
  v165 = 0;
  v166 = v7;
  v167 = v8;
  PatchPoints::PatchPoints(&v170, &v165);
  v134 = v171;
  v9 = 1;
  v10 = v171 - v171 % 4;
  if ( (int)v10 < 4 )
    v10 = 4;
  v130 = v10;
  *(_OWORD *)v146 = *(_OWORD *)a4;
  RectT<IntegerTypes>::OffsetRect(v146, (unsigned int)-*a3, (unsigned int)-a3[1]);
  v11 = (char *)malloc(saturated_mul(v10, 0xCu));
  v161 = v11;
  if ( !v11 )
    ThrowOOM();
  v181 = v11;
  v12 = (_BYTE *)LargeAllocationNew<float>(v10, L"BlemishRemovalRedArray");
  v193 = v12;
  v13 = (_DWORD *)LargeAllocationNew<float>(v10, L"BlemishRemovalGreenArray");
  v192 = v13;
  v14 = (_BYTE *)LargeAllocationNew<float>(v10, L"BlemishRemovalBlueArray");
  v165 = v14;
  v15 = ((int)v7 + (int)v8) / 128;
  if ( v15 < 1 )
    v15 = 1;
  v138 = v15;
  v16 = 0.0;
  v162 = 0.0;
  v17 = 0.0;
  v164 = 0.0;
  v18 = 0.0;
  v163 = 0.0;
  v19 = 0.0;
  v125 = 0;
  v20 = *(_DWORD *)v146;
  v21 = 0;
  v123 = 0;
  v136 = (float *)v13;
  v139 = v161 + 8;
  v144 = v12 - (_BYTE *)v13;
  v150 = v14 - (_BYTE *)v13;
  v22 = v132;
  v23 = v153;
  while ( 1 )
  {
    v24 = *((_QWORD *)v170 + v21 / (int)v10);
    v25 = v24 + v20;
    v120 = v25;
    v26 = *(_DWORD *)&v146[4] + HIDWORD(v24);
    v27 = a2 * (*(_DWORD *)&v146[4] + HIDWORD(v24));
    ho = (char *)(4LL * v25);
    v28 = &ho[v27 + v152];
    v151 = (unsigned __int8 *)v28;
    if ( !v28[3] && !v28[2] && !v28[1] && !*v28 )
    {
      v9 = 0;
      goto LABEL_151;
    }
    v29 = 1;
    if ( v25 == v22 - 1 )
      v29 = -1;
    v30 = (unsigned __int8 *)(v152 + v27 + 4LL * (v25 + v29));
    v31 = 1;
    if ( v26 == v23 - 1 )
      v31 = -1;
    v32 = &ho[a2 * (v26 + v31) + v152];
    v33 = v151;
    *(_DWORD *)((char *)v136 + v144) = dword_1805FA580[v151[2]];
    *(_DWORD *)v136 = dword_1805FA580[v33[1]];
    v34 = v150;
    *(_DWORD *)((char *)v136 + v150) = dword_1805FA580[*v33];
    v121 = v120 - *(_DWORD *)v146;
    *(v139 - 2) = v121;
    *(v139 - 1) = v7 - v121 - 1;
    *v139 = v26 - *(_DWORD *)&v146[4];
    v162 = v16 + *(float *)((char *)v136 + v144);
    v164 = v17 + *v136;
    v163 = v18 + *(float *)((char *)v136 + v34);
    v35 = *(float *)&dword_1805FA580[v33[2]] - *(float *)&dword_1805FA580[v30[2]];
    v36 = *(float *)&dword_1805FA580[v33[1]] - *(float *)&dword_1805FA580[v30[1]];
    v37 = *(float *)&dword_1805FA580[*v33] - *(float *)&dword_1805FA580[*v30];
    v38 = *(float *)&dword_1805FA580[v33[2]] - *(float *)&dword_1805FA580[(unsigned __int8)v32[2]];
    v39 = *(float *)&dword_1805FA580[v33[1]] - *(float *)&dword_1805FA580[(unsigned __int8)v32[1]];
    v40 = *(float *)&dword_1805FA580[*v33] - *(float *)&dword_1805FA580[(unsigned __int8)*v32];
    v19 = v19
        + (float)((float)((float)(v35 * v35) + (float)(v36 * v36)) + (float)(v37 * v37))
        + (float)((float)((float)(v39 * v39) + (float)(v38 * v38)) + (float)(v40 * v40));
    ++v125;
    v21 = v134 + v123;
    v123 += v134;
    v139 += 3;
    ++v136;
    v10 = v130;
    v22 = v132;
    if ( v125 >= v130 )
      break;
    v16 = v162;
    v17 = v164;
    v18 = v163;
    v20 = *(_DWORD *)v146;
  }
  v41 = v19 / (double)(2 * v130);
  v154 = v130 / 5;
  *(_QWORD *)&rect.left = 0;
  rect.right = v132 - v7 + 1;
  rect.bottom = v153 - v8 + 1;
  v42 = CreateRectRgnIndirect(&rect);
  v177 = v42;
  *(_QWORD *)&v195.right = *(_QWORD *)&v146[8];
  v195.left = *(_DWORD *)v146 - v7 + 1;
  v195.top = 1 - v8 + *(_DWORD *)&v146[4];
  hoa = CreateRectRgnIndirect(&v195);
  CombineRgn(v42, v42, hoa, 4);
  if ( hoa )
    DeleteObject(hoa);
  RegionRects::RegionRects((RegionRects *)&v190, v42, 0x7FFFFFFF);
  v43 = 4;
  if ( (int)v191 < 4 )
    v43 = v191;
  v135 = v43;
  ListOfBestSourceMatches::ListOfBestSourceMatches((ListOfBestSourceMatches *)v189, 1);
  ListOfBestSourceMatches::ListOfBestSourceMatches((ListOfBestSourceMatches *)v188, 1);
  ListOfBestSourceMatches::ListOfBestSourceMatches((ListOfBestSourceMatches *)v187, 1);
  ListOfBestSourceMatches::ListOfBestSourceMatches((ListOfBestSourceMatches *)v186, 1);
  v44 = 0;
  if ( (int)v7 / 4 - v138 > 0 )
    v44 = (int)v7 / 4 - v138;
  v149 = v44;
  v45 = v138 / 2;
  if ( (int)v7 / 8 < v138 / 2 )
    v45 = (int)v7 / 8;
  v46 = 1;
  if ( v45 > 1 )
    v46 = v45;
  v159 = v46 - v138;
  v47 = sqrtf_0(0.5);
  v127 = (int)floor_0((float)((float)(int)v7 * v47) + 0.5);
  v48 = (int)floor_0((float)((float)(int)v8 * v47) + 0.5);
  v49 = v127 - 2;
  if ( v127 - 2 > 20 )
    v49 = 20;
  v158 = v49;
  v50 = v48 - 2;
  if ( v48 - 2 > 20 )
    v50 = 20;
  v157 = v50;
  if ( v49 <= 0 || v50 <= 0 )
  {
    v119 = 0;
    v51 = 0;
    v52 = 0;
  }
  else
  {
    v119 = 1;
    v51 = v127 / (v49 + 2);
    if ( v51 < 1 )
      v51 = 1;
    v52 = v48 / (v50 + 2);
    if ( v52 < 1 )
      v52 = 1;
  }
  v148 = v52;
  v124 = v51;
  v156 = v51 + ((int)v7 - v127) / 2;
  v155 = v52 + ((int)v8 - v48) / 2;
  v53 = v130;
  v182 = (float)((float)v130 * 3.0);
  v145 = (float)(0.5 / (float)v130);
  v54 = (double)v130 * 0.3;
  v55 = 0;
  v126 = 0;
  si128 = (__m128d)_mm_load_si128((const __m128i *)&_xmm);
  if ( v135 > 0 )
  {
    v151 = 0;
    v57 = 0;
    hob = 0;
    do
    {
      v58 = si128.m128d_f64[0];
      v169 = si128;
      if ( v55 < 0 )
        ATL::BaseAtlThrow(-2147024809);
      if ( v55 >= v191 )
        ATL::BaseAtlThrow(-2147024809);
      v59 = *(int *)((char *)v190 + (_QWORD)v57);
      v160 = *(_DWORD *)((char *)v190 + (_QWORD)v57);
      v131 = *(_DWORD *)((char *)v190 + (_QWORD)v57 + 8);
      v60 = *(_DWORD *)((char *)v190 + (_QWORD)v57 + 4);
      v137 = *(_DWORD *)((char *)v190 + (_QWORD)v57 + 12);
      if ( v60 < v137 )
      {
        v61 = 4 * v59;
        *(_QWORD *)v146 = 4 * v59;
        v62 = v60;
        v63 = a2 * v60;
        v128 = a2 * v60;
        v64 = v138;
        LODWORD(v153) = v138 * a2;
        *(_QWORD *)&v169.m128d_f64[1] = *(_OWORD *)&_mm_unpackhi_pd(si128, si128);
        v65 = v182;
        do
        {
          v66 = 0;
          v122 = 0;
          v67 = v61 + v63 + v152;
          *(_QWORD *)&rect.left = v67;
          v68 = v131;
          do
          {
            v69 = v67;
            v133 = v67;
            v70 = v59;
            if ( (int)v59 < v68 )
            {
              v185 = 4LL * v64;
              do
              {
                v71 = 0.0;
                v72 = 0.0;
                v73 = 0.0;
                v74 = 0.0;
                v75 = 0;
                v140 = 0;
                v76 = (float *)v13;
                v77 = v161;
                v78 = v161 + 8;
                v150 = (signed __int64)(v161 + 8);
                v183 = v12 - (_BYTE *)v13;
                v184 = v14 - (_BYTE *)v13;
                while ( 1 )
                {
                  v79 = &v77[12 * v75];
                  if ( v122 )
                    v79 += 4;
                  v80 = *(int *)v79;
                  v81 = v69 + a2 * *v78;
                  if ( !*(_BYTE *)(v81 + 4 * v80 + 3)
                    && !*(_BYTE *)(v81 + 4 * v80 + 2)
                    && !*(_BYTE *)(v81 + 4 * v80 + 1)
                    && !*(_BYTE *)(v81 + 4 * v80) )
                  {
                    goto LABEL_84;
                  }
                  v82 = *(float *)&dword_1805FA580[*(unsigned __int8 *)(v81 + 4 * v80 + 2)];
                  v83 = *(float *)&dword_1805FA580[*(unsigned __int8 *)(v81 + 4 * v80 + 1)];
                  v84 = *(float *)&dword_1805FA580[*(unsigned __int8 *)(v81 + 4 * v80)];
                  v71 = v71
                      + (v83 - *v76) * (v83 - *v76)
                      + (v82 - *(float *)((char *)v76 + v183)) * (v82 - *(float *)((char *)v76 + v183))
                      + (v84 - *(float *)((char *)v76 + v184)) * (v84 - *(float *)((char *)v76 + v184));
                  if ( (v75 & 0xF) == 0xF && v71 > v169.m128d_f64[1] * 2.0 )
                    break;
                  v72 = v72 + v82;
                  v73 = v73 + v83;
                  v74 = v74 + v84;
                  ++v75;
                  ++v140;
                  v78 = (_DWORD *)(v150 + 12);
                  v150 += 12LL;
                  ++v76;
                  if ( v75 >= v53 )
                  {
                    v85 = v72 - v162;
                    v86 = v73 - v164;
                    v87 = v74 - v163;
                    v88 = v71;
                    if ( v54 > COERCE_DOUBLE(*(_QWORD *)&v86 & _xmm)
                             + COERCE_DOUBLE(*(_QWORD *)&v85 & _xmm)
                             + COERCE_DOUBLE(*(_QWORD *)&v87 & _xmm) )
                      v71 = v71 - (v86 * v86 + v85 * v85 + v87 * v87) * v145;
                    if ( v119 )
                    {
                      v71 = v71
                          + COERCE_DOUBLE(
                              COERCE_UNSIGNED_INT64(sub_1803E69F4(
                                                      v152,
                                                      a2,
                                                      v70 + v156,
                                                      v62 + v155,
                                                      v124,
                                                      v148,
                                                      v158,
                                                      v157) - v41)
                            & _xmm)
                          * v65;
                      v69 = v133;
                    }
                    if ( v58 > v71 )
                    {
                      v172[0] = v70;
                      v172[1] = v62;
                      v173 = v71;
                      v174 = v88;
                      v175 = v122 == 1;
                      if ( v126 )
                      {
                        switch ( v126 )
                        {
                          case 1:
                            ListOfBestSourceMatches::ApplyValue(
                              (ListOfBestSourceMatches *)v188,
                              (const struct SourceMatch *)v172);
                            v89 = v188;
                            break;
                          case 2:
                            ListOfBestSourceMatches::ApplyValue(
                              (ListOfBestSourceMatches *)v187,
                              (const struct SourceMatch *)v172);
                            v89 = v187;
                            break;
                          case 3:
                            ListOfBestSourceMatches::ApplyValue(
                              (ListOfBestSourceMatches *)v186,
                              (const struct SourceMatch *)v172);
                            v89 = v186;
                            break;
                          default:
LABEL_80:
                            v90 = v159;
LABEL_83:
                            v69 += 4 * v90;
                            v70 += v90;
                            goto LABEL_84;
                        }
                      }
                      else
                      {
                        ListOfBestSourceMatches::ApplyValue(
                          (ListOfBestSourceMatches *)v189,
                          (const struct SourceMatch *)v172);
                        v89 = v189;
                      }
                      ListOfBestSourceMatches::GetWorst((ListOfBestSourceMatches *)v89, (struct SourceMatch *)v168);
                      v69 = v133;
                      v58 = v169.m128d_f64[0];
                      goto LABEL_80;
                    }
                    if ( v71 <= v58 * 3.0 )
                      goto LABEL_84;
                    v90 = v149;
                    goto LABEL_83;
                  }
                  v77 = v161;
                }
                if ( v140 < v154 )
                {
                  v70 += v149;
                  v69 += 4LL * v149;
                }
LABEL_84:
                v64 = v138;
                v70 += v138;
                v69 += v185;
                v133 = v69;
                v68 = v131;
              }
              while ( v70 < v131 );
              v66 = v122;
              LODWORD(v59) = v160;
              v67 = *(_QWORD *)&rect.left;
            }
            v122 = ++v66;
          }
          while ( v66 < 2 );
          v62 += v64;
          v63 = v153 + v128;
          v128 += v153;
          v61 = *(_QWORD *)v146;
        }
        while ( v62 < v137 );
        v42 = v177;
        si128 = (__m128d)_mm_load_si128((const __m128i *)&_xmm);
        v57 = hob;
        v55 = v126;
      }
      v126 = ++v55;
      ++v151;
      v57 += 16;
      hob = v57;
    }
    while ( (__int64)v151 < v135 );
  }
  ListOfBestSourceMatches::ListOfBestSourceMatches((ListOfBestSourceMatches *)Block, 4);
  *(_QWORD *)v146 = 0;
  *(__m128d *)&v146[8] = si128;
  v147 = 0;
  ListOfBestSourceMatches::GetBest((ListOfBestSourceMatches *)v189, (struct SourceMatch *)v146);
  ListOfBestSourceMatches::ApplyValue((ListOfBestSourceMatches *)Block, (const struct SourceMatch *)v146);
  ListOfBestSourceMatches::GetBest((ListOfBestSourceMatches *)v188, (struct SourceMatch *)v146);
  ListOfBestSourceMatches::ApplyValue((ListOfBestSourceMatches *)Block, (const struct SourceMatch *)v146);
  ListOfBestSourceMatches::GetBest((ListOfBestSourceMatches *)v187, (struct SourceMatch *)v146);
  ListOfBestSourceMatches::ApplyValue((ListOfBestSourceMatches *)Block, (const struct SourceMatch *)v146);
  ListOfBestSourceMatches::GetBest((ListOfBestSourceMatches *)v186, (struct SourceMatch *)v146);
  ListOfBestSourceMatches::ApplyValue((ListOfBestSourceMatches *)Block, (const struct SourceMatch *)v146);
  ListOfBestSourceMatches::GetBest((ListOfBestSourceMatches *)Block, (struct SourceMatch *)v146);
  v91 = v178;
  v92 = v179;
  v93 = v180;
  *(_DWORD *)(v180 + 16) = *(_DWORD *)v146 + *v178 - *v179;
  *(_DWORD *)(v93 + 20) = v91[1] + *(_DWORD *)&v146[4] - v92[1];
  *(_OWORD *)v93 = *(_OWORD *)v92;
  *(_DWORD *)(v93 + 24) = v147;
  if ( *(double *)&v146[8] == 3.399999975603521e28 )
    v9 = 0;
  v94 = Block[0];
  if ( Block[0] )
  {
    if ( ImagingEngine::s_singleton )
      v95 = *((_QWORD *)ImagingEngine::s_singleton + 10);
    else
      v95 = 0;
    if ( v95 )
    {
      v96 = (*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v95 + 88LL))(v95, Block[0]) == 0;
      v94 = Block[0];
    }
    else
    {
      v96 = 0;
    }
    if ( !v96 && v94 )
      free(v94);
    Block[0] = 0;
  }
  v97 = v186[0];
  if ( v186[0] )
  {
    if ( ImagingEngine::s_singleton )
      v98 = *((_QWORD *)ImagingEngine::s_singleton + 10);
    else
      v98 = 0;
    if ( v98 )
    {
      v99 = (*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v98 + 88LL))(v98, v186[0]) == 0;
      v97 = v186[0];
    }
    else
    {
      v99 = 0;
    }
    if ( !v99 && v97 )
      free(v97);
    v186[0] = 0;
  }
  v100 = v187[0];
  if ( v187[0] )
  {
    if ( ImagingEngine::s_singleton )
      v101 = *((_QWORD *)ImagingEngine::s_singleton + 10);
    else
      v101 = 0;
    if ( v101 )
    {
      v102 = (*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v101 + 88LL))(v101, v187[0]) == 0;
      v100 = v187[0];
    }
    else
    {
      v102 = 0;
    }
    if ( !v102 && v100 )
      free(v100);
    v187[0] = 0;
  }
  v103 = v188[0];
  if ( v188[0] )
  {
    if ( ImagingEngine::s_singleton )
      v104 = *((_QWORD *)ImagingEngine::s_singleton + 10);
    else
      v104 = 0;
    if ( v104 )
    {
      v105 = (*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v104 + 88LL))(v104, v188[0]) == 0;
      v103 = v188[0];
    }
    else
    {
      v105 = 0;
    }
    if ( !v105 && v103 )
      free(v103);
    v188[0] = 0;
  }
  v106 = v189[0];
  if ( v189[0] )
  {
    if ( ImagingEngine::s_singleton )
      v107 = *((_QWORD *)ImagingEngine::s_singleton + 10);
    else
      v107 = 0;
    if ( v107 )
    {
      v108 = (*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v107 + 88LL))(v107, v189[0]) == 0;
      v106 = v189[0];
    }
    else
    {
      v108 = 0;
    }
    if ( !v108 && v106 )
      free(v106);
    v189[0] = 0;
  }
  if ( v190 )
    free(v190);
  if ( v42 )
    DeleteObject(v42);
LABEL_151:
  if ( v14 )
  {
    v109 = ImagingEngine::s_singleton ? *((_QWORD *)ImagingEngine::s_singleton + 10) : 0LL;
    if ( !v109 || (*(unsigned int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v109 + 88LL))(v109, v14) != 0 )
      free(v14);
  }
  if ( v13 )
  {
    v111 = ImagingEngine::s_singleton ? *((_QWORD *)ImagingEngine::s_singleton + 10) : 0LL;
    if ( !v111 || (*(unsigned int (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v111 + 88LL))(v111, v13) != 0 )
      free(v13);
  }
  if ( v12 )
  {
    v113 = ImagingEngine::s_singleton ? *((_QWORD *)ImagingEngine::s_singleton + 10) : 0LL;
    if ( !v113 || (*(unsigned int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v113 + 88LL))(v113, v12) != 0 )
      free(v12);
  }
  Base::Ptr<ClonePeripheryData>::~Ptr<ClonePeripheryData>(&v181);
  v115 = v170;
  if ( v170 )
  {
    if ( ImagingEngine::s_singleton )
      v116 = *((_QWORD *)ImagingEngine::s_singleton + 10);
    else
      v116 = 0;
    if ( v116 )
    {
      v117 = (*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v116 + 88LL))(v116, v170) == 0;
      v115 = v170;
    }
    else
    {
      v117 = 0;
    }
    if ( !v117 && v115 )
      free(v115);
  }
  return v9;
}

```

## disassembly

```asm
0x1803e36bc  mov     rax, rsp
0x1803e36bf  push    rbp
0x1803e36c0  push    rbx
0x1803e36c1  push    rsi
0x1803e36c2  push    rdi
0x1803e36c3  push    r12
0x1803e36c5  push    r13
0x1803e36c7  push    r14
0x1803e36c9  push    r15
0x1803e36cb  lea     rbp, [rax-2B8h]
0x1803e36d2  sub     rsp, 378h
0x1803e36d9  movaps  xmmword ptr [rax-58h], xmm6
0x1803e36dd  movaps  xmmword ptr [rax-68h], xmm7
0x1803e36e1  movaps  xmmword ptr [rax-78h], xmm8
0x1803e36e6  movaps  xmmword ptr [rax-88h], xmm9
0x1803e36ee  movaps  xmmword ptr [rax-98h], xmm10
0x1803e36f6  movaps  xmmword ptr [rax-0A8h], xmm11
0x1803e36fe  movaps  xmmword ptr [rax-0B8h], xmm13
0x1803e3706  movaps  xmmword ptr [rax-0C8h], xmm14
0x1803e370e  movaps  xmmword ptr [rax-0D8h], xmm15
0x1803e3716  mov     rax, cs:__security_cookie
0x1803e371d  xor     rax, rsp
0x1803e3720  mov     [rbp+2B0h+var_E0], rax
0x1803e3727  mov     rbx, r9
0x1803e372a  mov     [rbp+2B0h+var_1F0], rbx
0x1803e3731  mov     rdi, r8
0x1803e3734  mov     [rbp+2B0h+var_1F8], r8
0x1803e373b  mov     [rsp+3B0h+var_35C], edx
0x1803e373f  mov     [rbp+2B0h+var_2D8], rcx
0x1803e3743  mov     rax, [rbp+2B0h+arg_20]
0x1803e374a  mov     [rbp+2B0h+var_1E8], rax
0x1803e3751  movsxd  rcx, dword ptr [r8+0Ch]
0x1803e3755  movsxd  rax, dword ptr [r8+4]
0x1803e3759  sub     rcx, rax
0x1803e375c  mov     [rbp+2B0h+var_2D0], rcx
0x1803e3760  mov     edx, 80000000h
0x1803e3765  lea     rax, [rcx+rdx]
0x1803e3769  mov     r8d, 0FFFFFFFFh
0x1803e376f  cmp     rax, r8
0x1803e3772  ja      loc_1803E4774
0x1803e3778  movsxd  rax, dword ptr [rdi]
0x1803e377b  movsxd  rcx, dword ptr [rdi+8]
0x1803e377f  sub     rcx, rax
0x1803e3782  mov     [rsp+3B0h+var_350], rcx
0x1803e3787  lea     rax, [rcx+rdx]
0x1803e378b  cmp     rax, r8
0x1803e378e  ja      loc_1803E4774
0x1803e3794  movsxd  rax, dword ptr [r9]
0x1803e3797  movsxd  r12, dword ptr [r9+8]
0x1803e379b  sub     r12, rax
0x1803e379e  lea     rax, [rdx+r12]
0x1803e37a2  cmp     rax, r8
0x1803e37a5  ja      loc_1803E4774
0x1803e37ab  movsxd  rax, dword ptr [r9+4]
0x1803e37af  movsxd  r13, dword ptr [r9+0Ch]
0x1803e37b3  sub     r13, rax
0x1803e37b6  lea     rax, [rdx+r13]
0x1803e37ba  cmp     rax, r8
0x1803e37bd  ja      loc_1803E4774
0x1803e37c3  mov     [rbp+2B0h+var_280], 0
0x1803e37cb  mov     [rbp+2B0h+var_278], r12d
0x1803e37cf  mov     [rbp+2B0h+var_274], r13d
0x1803e37d3  lea     rdx, [rbp+2B0h+var_280]
0x1803e37d7  lea     rcx, [rbp+2B0h+var_250]
0x1803e37db  call    ??0PatchPoints@@QEAA@U?$RectT@UIntegerTypes@@@@@Z; PatchPoints::PatchPoints(RectT<IntegerTypes>)
0x1803e37e0  mov     ecx, [rbp+2B0h+var_248]
0x1803e37e3  mov     dword ptr [rsp+3B0h+var_348], ecx
0x1803e37e7  mov     eax, ecx
0x1803e37e9  mov     r15d, 1
0x1803e37ef  and     eax, 80000003h
0x1803e37f4  jge     short loc_1803E37FF
0x1803e37f6  sub     eax, r15d
0x1803e37f9  or      eax, 0FFFFFFFCh
0x1803e37fc  add     eax, r15d
0x1803e37ff  mov     r14d, ecx
0x1803e3802  sub     r14d, eax
0x1803e3805  mov     eax, 4
0x1803e380a  cmp     r14d, eax
0x1803e380d  cmovl   r14d, eax
0x1803e3811  mov     dword ptr [rsp+3B0h+var_358], r14d
0x1803e3816  movups  xmm0, xmmword ptr [rbx]
0x1803e3819  movdqu  xmmword ptr [rbp+2B0h+var_310], xmm0
0x1803e381e  mov     r8d, [rdi+4]
0x1803e3822  neg     r8d
0x1803e3825  mov     edx, [rdi]
0x1803e3827  neg     edx
0x1803e3829  lea     rcx, [rbp+2B0h+var_310]
0x1803e382d  call    ?OffsetRect@?$RectT@UIntegerTypes@@@@QEAAXHH@Z; RectT<IntegerTypes>::OffsetRect(int,int)
0x1803e3832  mov     edi, r14d
0x1803e3835  mov     eax, 0Ch
0x1803e383a  mul     rdi
0x1803e383d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1803e3844  cmovb   rax, rcx
0x1803e3848  mov     rcx, rax; Size
0x1803e384b  call    cs:__imp_malloc
0x1803e3851  mov     [rbp+2B0h+var_2A8], rax
0x1803e3855  test    rax, rax
0x1803e3858  jz      loc_1803E477D
0x1803e385e  mov     [rbp+2B0h+var_1E0], rax
0x1803e3865  lea     rdx, aBlemishremoval_8; "BlemishRemovalRedArray"
0x1803e386c  mov     ecx, edi
0x1803e386e  call    ??$LargeAllocationNew@M@@YAPEAM_KPEB_W@Z; LargeAllocationNew<float>(unsigned __int64,wchar_t const *)
0x1803e3873  mov     rsi, rax
0x1803e3876  mov     [rbp+2B0h+var_110], rax
0x1803e387d  lea     rdx, aBlemishremoval_2; "BlemishRemovalGreenArray"
0x1803e3884  mov     ecx, edi
0x1803e3886  call    ??$LargeAllocationNew@M@@YAPEAM_KPEB_W@Z; LargeAllocationNew<float>(unsigned __int64,wchar_t const *)
0x1803e388b  mov     rbx, rax
0x1803e388e  mov     [rbp+2B0h+var_118], rax
0x1803e3895  lea     rdx, aBlemishremoval; "BlemishRemovalBlueArray"
0x1803e389c  mov     ecx, edi
0x1803e389e  call    ??$LargeAllocationNew@M@@YAPEAM_KPEB_W@Z; LargeAllocationNew<float>(unsigned __int64,wchar_t const *)
0x1803e38a3  mov     rdi, rax
0x1803e38a6  mov     [rbp+2B0h+var_280], rax
0x1803e38aa  lea     eax, [r12+r13]
0x1803e38ae  cdq
0x1803e38af  and     edx, 7Fh
0x1803e38b2  add     eax, edx
0x1803e38b4  sar     eax, 7
0x1803e38b7  cmp     eax, r15d
0x1803e38ba  cmovl   eax, r15d
0x1803e38be  mov     [rsp+3B0h+var_338], eax
0x1803e38c2  xorps   xmm1, xmm1
0x1803e38c5  movsd   [rbp+2B0h+var_2A0], xmm1
0x1803e38ca  xorps   xmm2, xmm2
0x1803e38cd  movsd   [rbp+2B0h+var_290], xmm2
0x1803e38d2  xorps   xmm3, xmm3
0x1803e38d5  movsd   [rbp+2B0h+var_298], xmm3
0x1803e38da  xorps   xmm15, xmm15
0x1803e38de  mov     [rsp+3B0h+var_364], 0
0x1803e38e6  mov     r8d, dword ptr [rbp+2B0h+var_310]
0x1803e38ea  test    r14d, r14d
0x1803e38ed  jle     loc_1803E3B67
0x1803e38f3  xor     ecx, ecx
0x1803e38f5  mov     [rsp+3B0h+var_368], ecx
0x1803e38f9  mov     [rsp+3B0h+var_340], rbx
0x1803e38fe  mov     rax, [rbp+2B0h+var_2A8]
0x1803e3902  add     rax, 8
0x1803e3906  mov     [rbp+2B0h+var_330], rax
0x1803e390a  mov     rax, rsi
0x1803e390d  sub     rax, rbx
0x1803e3910  mov     [rbp+2B0h+var_320], rax
0x1803e3914  mov     rax, rdi
0x1803e3917  sub     rax, rbx
0x1803e391a  mov     [rbp+2B0h+var_2E8], rax
0x1803e391e  mov     r10, [rsp+3B0h+var_350]
0x1803e3923  mov     r11, [rbp+2B0h+var_2D0]
0x1803e3927  mov     eax, ecx
0x1803e3929  cdq
0x1803e392a  idiv    r14d
0x1803e392d  movsxd  rcx, eax
0x1803e3930  mov     rax, [rbp+2B0h+var_250]
0x1803e3934  mov     rax, [rax+rcx*8]
0x1803e3938  add     r8d, eax
0x1803e393b  mov     [rsp+3B0h+var_36C], r8d
0x1803e3940  shr     rax, 20h
0x1803e3944  add     eax, dword ptr [rbp+2B0h+var_310+4]
0x1803e3947  movsxd  rdx, r8d
0x1803e394a  mov     ecx, eax
0x1803e394c  imul    ecx, [rsp+3B0h+var_35C]
0x1803e3951  movsxd  r9, ecx
0x1803e3954  lea     rcx, ds:0[rdx*4]
0x1803e395c  mov     [rbp+2B0h+ho], rcx
0x1803e3960  add     rcx, r9
0x1803e3963  add     rcx, [rbp+2B0h+var_2D8]
0x1803e3967  mov     [rbp+2B0h+var_2E0], rcx
0x1803e396b  xor     edx, edx
0x1803e396d  cmp     [rcx+3], dl
0x1803e3970  ja      short loc_1803E3984
0x1803e3972  cmp     [rcx+2], dl
0x1803e3975  ja      short loc_1803E3984
0x1803e3977  cmp     [rcx+1], dl
0x1803e397a  ja      short loc_1803E3984
0x1803e397c  cmp     [rcx], dl
0x1803e397e  jbe     loc_1803E3B5C
0x1803e3984  lea     ecx, [r10-1]
0x1803e3988  mov     edx, r15d
0x1803e398b  cmp     r8d, ecx
0x1803e398e  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1803e3995  cmovz   edx, r14d
0x1803e3999  add     edx, r8d
0x1803e399c  movsxd  rcx, edx
0x1803e399f  lea     r8, [r9+rcx*4]
0x1803e39a3  add     r8, [rbp+2B0h+var_2D8]
0x1803e39a7  lea     ecx, [r11-1]
0x1803e39ab  mov     edx, r15d
0x1803e39ae  cmp     eax, ecx
0x1803e39b0  cmovz   edx, r14d
0x1803e39b4  add     edx, eax
0x1803e39b6  imul    edx, [rsp+3B0h+var_35C]
0x1803e39bb  movsxd  r9, edx
0x1803e39be  add     r9, [rbp+2B0h+ho]
0x1803e39c2  add     r9, [rbp+2B0h+var_2D8]
0x1803e39c6  mov     rdx, [rbp+2B0h+var_2E0]
0x1803e39ca  movzx   ecx, byte ptr [rdx+2]
0x1803e39ce  lea     r10, dword_1805FA580
0x1803e39d5  mov     ecx, [r10+rcx*4]
0x1803e39d9  mov     r14, [rbp+2B0h+var_320]
0x1803e39dd  mov     r10, [rsp+3B0h+var_340]
0x1803e39e2  mov     [r10+r14], ecx
0x1803e39e6  movzx   ecx, byte ptr [rdx+1]
0x1803e39ea  lea     r10, dword_1805FA580
0x1803e39f1  mov     ecx, [r10+rcx*4]
0x1803e39f5  mov     r14, [rsp+3B0h+var_340]
0x1803e39fa  mov     [r14], ecx
0x1803e39fd  movzx   ecx, byte ptr [rdx]
0x1803e3a00  mov     ecx, [r10+rcx*4]
0x1803e3a04  mov     r14, [rbp+2B0h+var_2E8]
0x1803e3a08  mov     r10, [rsp+3B0h+var_340]
0x1803e3a0d  mov     [r10+r14], ecx
0x1803e3a11  mov     ecx, [rsp+3B0h+var_36C]
0x1803e3a15  sub     ecx, dword ptr [rbp+2B0h+var_310]
0x1803e3a18  mov     [rsp+3B0h+var_36C], ecx
0x1803e3a1c  mov     r10, [rbp+2B0h+var_330]
0x1803e3a20  mov     [r10-8], ecx
0x1803e3a24  mov     ecx, r12d
0x1803e3a27  sub     ecx, [rsp+3B0h+var_36C]
0x1803e3a2b  sub     ecx, r15d
0x1803e3a2e  mov     [r10-4], ecx
0x1803e3a32  sub     eax, dword ptr [rbp+2B0h+var_310+4]
0x1803e3a35  mov     [r10], eax
0x1803e3a38  mov     rax, [rbp+2B0h+var_320]
0x1803e3a3c  mov     rcx, [rsp+3B0h+var_340]
0x1803e3a41  movss   xmm0, dword ptr [rcx+rax]
0x1803e3a46  cvtps2pd xmm0, xmm0
0x1803e3a49  addsd   xmm1, xmm0
0x1803e3a4d  movsd   [rbp+2B0h+var_2A0], xmm1
0x1803e3a52  movss   xmm1, dword ptr [rcx]
0x1803e3a56  cvtps2pd xmm1, xmm1
0x1803e3a59  addsd   xmm2, xmm1
0x1803e3a5d  movsd   [rbp+2B0h+var_290], xmm2
0x1803e3a62  movss   xmm0, dword ptr [rcx+r14]
0x1803e3a68  cvtps2pd xmm0, xmm0
0x1803e3a6b  addsd   xmm3, xmm0
0x1803e3a6f  movsd   [rbp+2B0h+var_298], xmm3
0x1803e3a74  movzx   eax, byte ptr [rdx+2]
0x1803e3a78  lea     rcx, dword_1805FA580
0x1803e3a7f  movss   xmm5, dword ptr [rcx+rax*4]
0x1803e3a84  movzx   eax, byte ptr [r8+2]
0x1803e3a89  movaps  xmm3, xmm5
0x1803e3a8c  subss   xmm3, dword ptr [rcx+rax*4]
0x1803e3a91  movzx   eax, byte ptr [rdx+1]
0x1803e3a95  movss   xmm4, dword ptr [rcx+rax*4]
0x1803e3a9a  movzx   eax, byte ptr [r8+1]
0x1803e3a9f  movaps  xmm1, xmm4
0x1803e3aa2  subss   xmm1, dword ptr [rcx+rax*4]
0x1803e3aa7  movzx   eax, byte ptr [rdx]
0x1803e3aaa  movss   xmm2, dword ptr [rcx+rax*4]
0x1803e3aaf  movzx   eax, byte ptr [r8]
0x1803e3ab3  movaps  xmm0, xmm2
0x1803e3ab6  subss   xmm0, dword ptr [rcx+rax*4]
0x1803e3abb  movzx   eax, byte ptr [r9+2]
0x1803e3ac0  subss   xmm5, dword ptr [rcx+rax*4]
0x1803e3ac5  movzx   eax, byte ptr [r9+1]
0x1803e3aca  subss   xmm4, dword ptr [rcx+rax*4]
0x1803e3acf  movzx   eax, byte ptr [r9]
0x1803e3ad3  subss   xmm2, dword ptr [rcx+rax*4]
0x1803e3ad8  mulss   xmm3, xmm3
0x1803e3adc  mulss   xmm1, xmm1
0x1803e3ae0  addss   xmm3, xmm1
0x1803e3ae4  mulss   xmm0, xmm0
0x1803e3ae8  addss   xmm3, xmm0
0x1803e3aec  cvtps2pd xmm1, xmm3
0x1803e3aef  addsd   xmm15, xmm1
0x1803e3af4  mulss   xmm4, xmm4
0x1803e3af8  mulss   xmm5, xmm5
0x1803e3afc  addss   xmm4, xmm5
0x1803e3b00  mulss   xmm2, xmm2
0x1803e3b04  addss   xmm4, xmm2
0x1803e3b08  cvtps2pd xmm0, xmm4
0x1803e3b0b  addsd   xmm15, xmm0
0x1803e3b10  mov     eax, [rsp+3B0h+var_364]
0x1803e3b14  add     eax, r15d
0x1803e3b17  mov     [rsp+3B0h+var_364], eax
0x1803e3b1b  mov     ecx, [rsp+3B0h+var_368]
0x1803e3b1f  add     ecx, dword ptr [rsp+3B0h+var_348]
0x1803e3b23  mov     [rsp+3B0h+var_368], ecx
0x1803e3b27  add     r10, 0Ch
0x1803e3b2b  mov     [rbp+2B0h+var_330], r10
0x1803e3b2f  add     [rsp+3B0h+var_340], 4
0x1803e3b35  mov     r14d, dword ptr [rsp+3B0h+var_358]
0x1803e3b3a  cmp     eax, r14d
0x1803e3b3d  mov     r10, [rsp+3B0h+var_350]
0x1803e3b42  jge     short loc_1803E3B67
0x1803e3b44  movsd   xmm1, [rbp+2B0h+var_2A0]
0x1803e3b49  movsd   xmm2, [rbp+2B0h+var_290]
0x1803e3b4e  movsd   xmm3, [rbp+2B0h+var_298]
0x1803e3b53  mov     r8d, dword ptr [rbp+2B0h+var_310]
0x1803e3b57  jmp     loc_1803E3927
0x1803e3b5c  xor     r13d, r13d
0x1803e3b5f  mov     r15b, r13b
0x1803e3b62  jmp     loc_1803E45D5
0x1803e3b67  lea     eax, [r14+r14]
0x1803e3b6b  movd    xmm0, eax
0x1803e3b6f  cvtdq2pd xmm0, xmm0
0x1803e3b73  divsd   xmm15, xmm0
0x1803e3b78  mov     eax, 66666667h
0x1803e3b7d  imul    r14d
0x1803e3b80  mov     ecx, edx
0x1803e3b82  sar     ecx, 1
  ... truncated ...
```
