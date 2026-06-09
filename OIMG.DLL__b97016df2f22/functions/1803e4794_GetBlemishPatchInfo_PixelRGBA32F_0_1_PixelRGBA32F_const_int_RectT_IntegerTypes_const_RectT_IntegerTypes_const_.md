# GetBlemishPatchInfo<PixelRGBA32F,0,1>(PixelRGBA32F const *,int,RectT<IntegerTypes> const &,RectT<IntegerTypes> const &,__MIDL___MIDL_itf_Imaging_0001_0125_0001 *)

- ea: `0x1803e4794`
- end: `0x1803e57bc`
- name: `??$GetBlemishPatchInfo@UPixelRGBA32F@@$0A@$00@@YA_NPEBUPixelRGBA32F@@HAEBU?$RectT@UIntegerTypes@@@@1PEAU__MIDL___MIDL_itf_Imaging_0001_0125_0001@@@Z`
- size: `4136`
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
- `0x1803e4794`
- `0x1803e6884`
- `0x1803e6bb4`
- `0x1804c6944`
- `0x18056bd00`
- `0x18056dc8e`
- `0x18056dcca`
- `0x18056dce0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1803e4925`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1803e4925`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e5449`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e54a6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e5506`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e5566`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e55c6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e55df`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e563f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e5686`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e56cd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e572a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e5449`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e54a6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e5506`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e5566`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e55c6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e55df`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e563f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e5686`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e56cd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e572a`
- `GDI32!CombineRgn` at `0x1803e4c89`
- `GDI32!CombineRgn` at `0x1803e4c89`
- `GDI32!DeleteObject` at `0x1803e4c99`
- `GDI32!DeleteObject` at `0x1803e55f8`
- `GDI32!DeleteObject` at `0x1803e4c99`
- `GDI32!DeleteObject` at `0x1803e55f8`
- `GDI32!CreateRectRgnIndirect` at `0x1803e4c31`
- `GDI32!CreateRectRgnIndirect` at `0x1803e4c6f`
- `GDI32!CreateRectRgnIndirect` at `0x1803e4c31`
- `GDI32!CreateRectRgnIndirect` at `0x1803e4c6f`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
char __fastcall GetBlemishPatchInfo<PixelRGBA32F,0,1>(__int64 a1, int a2, int *a3, int *a4, __int64 a5)
{
  __int64 v7; // r14
  __int64 v8; // r12
  __int64 v9; // r13
  char v10; // r15
  unsigned int v11; // ebx
  unsigned int v12; // edi
  char *v13; // rax
  __int64 v14; // rsi
  __int64 v15; // rbx
  __int64 v16; // rdi
  int v17; // eax
  double v18; // xmm1_8
  double v19; // xmm2_8
  double v20; // xmm3_8
  double v21; // xmm15_8
  int v22; // r10d
  int v23; // ecx
  int v24; // edi
  char *v25; // rbx
  __int64 v26; // r14
  __int64 v27; // rax
  int v28; // r8d
  int v29; // r9d
  __int64 v30; // rcx
  __int64 v31; // rdx
  float *v32; // r11
  int v33; // eax
  float *v34; // r10
  int v35; // eax
  float *v36; // rcx
  __int64 v37; // rdx
  int v38; // r8d
  int v39; // eax
  _DWORD *v40; // r8
  float v41; // xmm0_4
  float v42; // xmm1_4
  float v43; // xmm3_4
  float *v44; // rbx
  _BYTE *v45; // rdi
  _BYTE *v46; // rsi
  int v47; // r13d
  double v48; // xmm15_8
  HRGN v49; // r14
  int v50; // eax
  int v51; // ecx
  int v52; // ecx
  int v53; // eax
  float v54; // xmm7_4
  int v55; // r9d
  int v56; // eax
  int v57; // r10d
  int v58; // r11d
  int v59; // ecx
  int v60; // r9d
  int v61; // r8d
  __m128d si128; // xmm14
  char *v63; // rdx
  double v64; // xmm8_8
  __int64 v65; // r10
  int v66; // ecx
  __int64 v67; // r8
  int v68; // r14d
  int v69; // eax
  int v70; // ecx
  double v71; // xmm14_8
  int v72; // edx
  __int64 v73; // r8
  int v74; // eax
  __int64 v75; // r13
  int v76; // r12d
  double v77; // xmm6_8
  double v78; // xmm5_8
  double v79; // xmm4_8
  double v80; // xmm7_8
  int v81; // r10d
  float *v82; // r11
  char *v83; // rdx
  _DWORD *v84; // rax
  char *v85; // rdx
  __int64 v86; // rcx
  __int64 v87; // rax
  double v88; // xmm9_8
  double v89; // xmm10_8
  double v90; // xmm11_8
  __int64 v91; // rax
  double v92; // xmm5_8
  double v93; // xmm4_8
  double v94; // xmm7_8
  double v95; // xmm9_8
  void **v96; // rcx
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
  int v133; // [rsp+5Ch] [rbp-ACh]
  int v134; // [rsp+60h] [rbp-A8h]
  int v135; // [rsp+64h] [rbp-A4h]
  int v136; // [rsp+64h] [rbp-A4h]
  int v137; // [rsp+68h] [rbp-A0h]
  int v138; // [rsp+6Ch] [rbp-9Ch]
  char *ho; // [rsp+70h] [rbp-98h]
  HRGN hoa; // [rsp+70h] [rbp-98h]
  char *hob; // [rsp+70h] [rbp-98h]
  float *v142; // [rsp+78h] [rbp-90h]
  int v143; // [rsp+78h] [rbp-90h]
  __int64 v144; // [rsp+80h] [rbp-88h]
  _BYTE v145[24]; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int8 v146; // [rsp+A0h] [rbp-68h]
  int v147; // [rsp+A8h] [rbp-60h]
  int v148; // [rsp+ACh] [rbp-5Ch]
  __int64 v149; // [rsp+B0h] [rbp-58h]
  _DWORD *v150; // [rsp+B8h] [rbp-50h]
  __int64 v151; // [rsp+C0h] [rbp-48h]
  __int64 v152; // [rsp+C8h] [rbp-40h]
  __int64 v153; // [rsp+D0h] [rbp-38h]
  int v154; // [rsp+D8h] [rbp-30h]
  int v155; // [rsp+DCh] [rbp-2Ch]
  int v156; // [rsp+E0h] [rbp-28h]
  int v157; // [rsp+E4h] [rbp-24h]
  int v158; // [rsp+E8h] [rbp-20h]
  int v159; // [rsp+ECh] [rbp-1Ch]
  __int64 v160; // [rsp+F0h] [rbp-18h]
  char *v161; // [rsp+F8h] [rbp-10h]
  double v162; // [rsp+100h] [rbp-8h]
  double v163; // [rsp+108h] [rbp+0h]
  double v164; // [rsp+110h] [rbp+8h]
  char *v165; // [rsp+118h] [rbp+10h] BYREF
  int v166; // [rsp+120h] [rbp+18h]
  int v167; // [rsp+124h] [rbp+1Ch]
  char v168[8]; // [rsp+128h] [rbp+20h] BYREF
  __m128d v169; // [rsp+130h] [rbp+28h]
  void *v170; // [rsp+148h] [rbp+40h] BYREF
  int v171; // [rsp+150h] [rbp+48h]
  _DWORD v172[2]; // [rsp+158h] [rbp+50h] BYREF
  double v173; // [rsp+160h] [rbp+58h]
  double v174; // [rsp+168h] [rbp+60h]
  bool v175; // [rsp+170h] [rbp+68h]
  void *Block[4]; // [rsp+178h] [rbp+70h] BYREF
  __int64 v177; // [rsp+198h] [rbp+90h]
  float *v178; // [rsp+1A0h] [rbp+98h]
  HRGN v179; // [rsp+1A8h] [rbp+A0h]
  _DWORD *v180; // [rsp+1B0h] [rbp+A8h]
  _BYTE *v181; // [rsp+1B8h] [rbp+B0h]
  __int64 v182; // [rsp+1C0h] [rbp+B8h]
  _BYTE *v183; // [rsp+1C8h] [rbp+C0h]
  double v184; // [rsp+1D0h] [rbp+C8h]
  signed __int64 v185; // [rsp+1D8h] [rbp+D0h]
  _DWORD *v186; // [rsp+1E0h] [rbp+D8h]
  signed __int64 v187; // [rsp+1E8h] [rbp+E0h]
  void *v188[4]; // [rsp+1F0h] [rbp+E8h] BYREF
  void *v189[4]; // [rsp+210h] [rbp+108h] BYREF
  void *v190[4]; // [rsp+230h] [rbp+128h] BYREF
  void *v191[4]; // [rsp+250h] [rbp+148h] BYREF
  void *v192; // [rsp+270h] [rbp+168h] BYREF
  unsigned __int64 v193; // [rsp+278h] [rbp+170h]
  RECT rect; // [rsp+290h] [rbp+188h] BYREF
  RECT v195; // [rsp+2A8h] [rbp+1A0h] BYREF

  v186 = a4;
  v180 = a3;
  v151 = a1;
  v182 = a5;
  v144 = a3[3] - (__int64)a3[1];
  if ( (unsigned __int64)(v144 + 0x80000000LL) > 0xFFFFFFFF
    || (v7 = a3[2] - (__int64)*a3, v160 = v7, (unsigned __int64)(v7 + 0x80000000LL) > 0xFFFFFFFF)
    || (v8 = a4[2] - (__int64)*a4, (unsigned __int64)(v8 + 0x80000000LL) > 0xFFFFFFFF)
    || (v9 = a4[3] - (__int64)a4[1], v149 = v9, (unsigned __int64)(v9 + 0x80000000LL) > 0xFFFFFFFF) )
  {
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  }
  v165 = 0;
  v166 = v8;
  v167 = v9;
  PatchPoints::PatchPoints(&v170, &v165);
  v126 = v171;
  v10 = 1;
  v11 = v171 - v171 % 4;
  if ( (int)v11 < 4 )
    v11 = 4;
  v129 = v11;
  *(_OWORD *)v145 = *(_OWORD *)a4;
  RectT<IntegerTypes>::OffsetRect(v145, (unsigned int)-*a3, (unsigned int)-a3[1]);
  v12 = v11;
  ho = (char *)v11;
  v13 = (char *)malloc(saturated_mul(v11, 0xCu));
  v161 = v13;
  if ( !v13 )
    ThrowOOM();
  v165 = v13;
  v14 = LargeAllocationNew<float>(v11, L"BlemishRemovalRedArray");
  v183 = (_BYTE *)v14;
  v15 = LargeAllocationNew<float>(v11, L"BlemishRemovalGreenArray");
  v178 = (float *)v15;
  v16 = LargeAllocationNew<float>(v12, L"BlemishRemovalBlueArray");
  v181 = (_BYTE *)v16;
  v17 = ((int)v8 + (int)v9) / 128;
  if ( v17 < 1 )
    v17 = 1;
  v138 = v17;
  v18 = 0.0;
  v162 = 0.0;
  v19 = 0.0;
  v164 = 0.0;
  v20 = 0.0;
  v163 = 0.0;
  v21 = 0.0;
  v22 = v7 - 1;
  v135 = v7 - 1;
  v23 = 0;
  v130 = 0;
  v142 = (float *)v15;
  v150 = v161 + 8;
  v153 = v14 - v15;
  v152 = v16 - v15;
  v24 = *(_DWORD *)v145;
  v25 = ho;
  v26 = v153;
  do
  {
    v27 = *((_QWORD *)v170 + v23 / v129);
    v28 = v27 + v24;
    v29 = HIDWORD(v27) + *(_DWORD *)&v145[4];
    v30 = a2 * (HIDWORD(v27) + *(_DWORD *)&v145[4]);
    v31 = 16LL * ((int)v27 + v24);
    v32 = (float *)(v151 + v31 + v30);
    v33 = 1;
    if ( v28 == v22 )
      v33 = -1;
    v34 = (float *)(v151 + v30 + 16LL * (v28 + v33));
    v35 = 1;
    if ( v29 == (_DWORD)v144 - 1 )
      v35 = -1;
    v36 = (float *)(v151 + v31 + a2 * (v29 + v35));
    *(float *)((char *)v142 + v26) = *v32;
    *v142 = v32[1];
    v37 = v152;
    *(float *)((char *)v142 + v152) = v32[2];
    v38 = v28 - v24;
    *(v150 - 2) = v38;
    v39 = v8 - v38 - 1;
    v40 = v150;
    *(v150 - 1) = v39;
    *v40 = v29 - *(_DWORD *)&v145[4];
    v162 = v18 + *(float *)((char *)v142 + v26);
    v164 = v19 + *v142;
    v163 = v20 + *(float *)((char *)v142 + v37);
    v41 = v32[1] - v34[1];
    v42 = v32[2] - v34[2];
    v43 = v32[2] - v36[2];
    v21 = v21
        + (float)((float)((float)((float)(*v32 - *v34) * (float)(*v32 - *v34)) + (float)(v41 * v41)) + (float)(v42 * v42))
        + (float)((float)((float)((float)(v32[1] - v36[1]) * (float)(v32[1] - v36[1]))
                        + (float)((float)(*v32 - *v36) * (float)(*v32 - *v36)))
                + (float)(v43 * v43));
    v23 = v126 + v130;
    v130 += v126;
    v150 = v40 + 3;
    ++v142;
    --v25;
    v18 = v162;
    v19 = v164;
    v20 = v163;
    v22 = v135;
  }
  while ( v25 );
  v44 = v178;
  v45 = v181;
  v46 = v183;
  v47 = v149;
  v48 = v21 / (double)(2 * v129);
  v154 = v129 / 5;
  *(_QWORD *)&rect.left = 0;
  rect.right = v160 - v8 + 1;
  rect.bottom = v144 - v149 + 1;
  v49 = CreateRectRgnIndirect(&rect);
  v179 = v49;
  *(_QWORD *)&v195.right = *(_QWORD *)&v145[8];
  v195.left = *(_DWORD *)v145 - v8 + 1;
  v195.top = 1 - v47 + *(_DWORD *)&v145[4];
  hoa = CreateRectRgnIndirect(&v195);
  CombineRgn(v49, v49, hoa, 4);
  if ( hoa )
    DeleteObject(hoa);
  RegionRects::RegionRects((RegionRects *)&v192, v49, 0x7FFFFFFF);
  v50 = 4;
  if ( (int)v193 < 4 )
    v50 = v193;
  v137 = v50;
  ListOfBestSourceMatches::ListOfBestSourceMatches((ListOfBestSourceMatches *)v191, 1);
  ListOfBestSourceMatches::ListOfBestSourceMatches((ListOfBestSourceMatches *)v190, 1);
  ListOfBestSourceMatches::ListOfBestSourceMatches((ListOfBestSourceMatches *)v189, 1);
  ListOfBestSourceMatches::ListOfBestSourceMatches((ListOfBestSourceMatches *)v188, 1);
  v51 = 0;
  if ( (int)v8 / 4 - v138 > 0 )
    v51 = (int)v8 / 4 - v138;
  v148 = v51;
  v52 = v138 / 2;
  if ( (int)v8 / 8 < v138 / 2 )
    v52 = (int)v8 / 8;
  v53 = 1;
  if ( v52 > 1 )
    v53 = v52;
  v159 = v53 - v138;
  v54 = sqrtf_0(0.5);
  v127 = (int)floor_0((float)((float)(int)v8 * v54) + 0.5);
  v55 = (int)floor_0((float)((float)v47 * v54) + 0.5);
  v56 = v127 - 2;
  if ( v127 - 2 > 20 )
    v56 = 20;
  v158 = v56;
  v57 = v55 - 2;
  if ( v55 - 2 > 20 )
    v57 = 20;
  v157 = v57;
  if ( v56 <= 0 || v57 <= 0 )
  {
    v125 = 0;
    v58 = 0;
    v59 = 0;
  }
  else
  {
    v125 = 1;
    v58 = v127 / (v56 + 2);
    if ( v58 < 1 )
      v58 = 1;
    v59 = v55 / (v57 + 2);
    if ( v59 < 1 )
      v59 = 1;
  }
  v147 = v59;
  v133 = v58;
  v156 = v58 + ((int)v8 - v127) / 2;
  v155 = v59 + (v47 - v55) / 2;
  v60 = v129;
  v184 = (float)((float)v129 * 3.0);
  v61 = 0;
  v131 = 0;
  si128 = (__m128d)_mm_load_si128((const __m128i *)&_xmm);
  if ( v137 > 0 )
  {
    v153 = 0;
    v63 = 0;
    hob = 0;
    do
    {
      v64 = si128.m128d_f64[0];
      v169 = si128;
      if ( v61 < 0 )
        ATL::BaseAtlThrow(-2147024809);
      if ( v61 >= v193 )
        ATL::BaseAtlThrow(-2147024809);
      v65 = *(int *)((char *)v192 + (_QWORD)v63);
      LODWORD(v160) = *(_DWORD *)((char *)v192 + (_QWORD)v63);
      v136 = *(_DWORD *)((char *)v192 + (_QWORD)v63 + 8);
      v66 = *(_DWORD *)((char *)v192 + (_QWORD)v63 + 4);
      v143 = *(_DWORD *)((char *)v192 + (_QWORD)v63 + 12);
      if ( v66 < v143 )
      {
        v67 = 16 * v65;
        *(_QWORD *)v145 = 16 * v65;
        v68 = v66;
        v69 = a2 * v66;
        v128 = a2 * v66;
        v70 = v138;
        LODWORD(v150) = v138 * a2;
        *(_QWORD *)&v169.m128d_f64[1] = *(_OWORD *)&_mm_unpackhi_pd(si128, si128);
        v71 = v184;
        do
        {
          v72 = 0;
          v134 = 0;
          v73 = v67 + v69 + v151;
          *(_QWORD *)&rect.left = v73;
          v74 = v136;
          do
          {
            v75 = v73;
            v76 = v65;
            if ( (int)v65 < v74 )
            {
              v177 = 16LL * v70;
              do
              {
                v77 = 0.0;
                v78 = 0.0;
                v79 = 0.0;
                v80 = 0.0;
                v81 = 0;
                v149 = 0;
                v82 = v44;
                v83 = v161;
                v84 = v161 + 8;
                v152 = (__int64)(v161 + 8);
                v185 = v46 - (_BYTE *)v44;
                v187 = v45 - (_BYTE *)v44;
                while ( 1 )
                {
                  v85 = &v83[12 * v81];
                  if ( v134 )
                    v85 += 4;
                  v86 = a2 * *v84;
                  v87 = v75 + 16LL * *(int *)v85;
                  v88 = *(float *)(v86 + v87 + 4);
                  v89 = *(float *)(v86 + v87 + 8);
                  v90 = *(float *)(v86 + v87);
                  v77 = v77
                      + (v88 - *v82) * (v88 - *v82)
                      + (v90 - *(float *)((char *)v82 + v185)) * (v90 - *(float *)((char *)v82 + v185))
                      + (v89 - *(float *)((char *)v82 + v187)) * (v89 - *(float *)((char *)v82 + v187));
                  if ( (v81 & 0xF) == 0xF && v77 > v169.m128d_f64[1] * 2.0 )
                    break;
                  v78 = v78 + v90;
                  v79 = v79 + v88;
                  v80 = v80 + v89;
                  ++v81;
                  ++v149;
                  v84 = (_DWORD *)(v152 + 12);
                  v152 += 12;
                  ++v82;
                  if ( v81 >= v60 )
                  {
                    v92 = v78 - v162;
                    v93 = v79 - v164;
                    v94 = v80 - v163;
                    v95 = v77;
                    if ( (double)v129 * 0.3 > COERCE_DOUBLE(*(_QWORD *)&v93 & _xmm)
                                            + COERCE_DOUBLE(*(_QWORD *)&v92 & _xmm)
                                            + COERCE_DOUBLE(*(_QWORD *)&v94 & _xmm) )
                      v77 = v77 - (v93 * v93 + v92 * v92 + v94 * v94) * (float)(0.5 / (float)v129);
                    if ( v125 )
                      v77 = v77
                          + COERCE_DOUBLE(
                              COERCE_UNSIGNED_INT64(sub_1803E6BB4(
                                                      v151,
                                                      a2,
                                                      v76 + v156,
                                                      v68 + v155,
                                                      v133,
                                                      v147,
                                                      v158,
                                                      v157) - v48)
                            & _xmm)
                          * v71;
                    if ( v64 > v77 )
                    {
                      v172[0] = v76;
                      v172[1] = v68;
                      v173 = v77;
                      v174 = v95;
                      v175 = v134 == 1;
                      if ( v131 )
                      {
                        switch ( v131 )
                        {
                          case 1:
                            ListOfBestSourceMatches::ApplyValue(
                              (ListOfBestSourceMatches *)v190,
                              (const struct SourceMatch *)v172);
                            v96 = v190;
                            break;
                          case 2:
                            ListOfBestSourceMatches::ApplyValue(
                              (ListOfBestSourceMatches *)v189,
                              (const struct SourceMatch *)v172);
                            v96 = v189;
                            break;
                          case 3:
                            ListOfBestSourceMatches::ApplyValue(
                              (ListOfBestSourceMatches *)v188,
                              (const struct SourceMatch *)v172);
                            v96 = v188;
                            break;
                          default:
LABEL_70:
                            v91 = v159;
LABEL_73:
                            v76 += v91;
                            goto LABEL_74;
                        }
                      }
                      else
                      {
                        ListOfBestSourceMatches::ApplyValue(
                          (ListOfBestSourceMatches *)v191,
                          (const struct SourceMatch *)v172);
                        v96 = v191;
                      }
                      ListOfBestSourceMatches::GetWorst((ListOfBestSourceMatches *)v96, (struct SourceMatch *)v168);
                      v64 = v169.m128d_f64[0];
                      goto LABEL_70;
                    }
                    if ( v77 <= v64 * 3.0 )
                      goto LABEL_75;
                    v91 = v148;
                    goto LABEL_73;
                  }
                  v83 = v161;
                }
                if ( v149 >= v154 )
                  goto LABEL_75;
                v76 += v148;
                v91 = v148;
LABEL_74:
                v75 += 16 * v91;
LABEL_75:
                v70 = v138;
                v76 += v138;
                v75 += v177;
                v74 = v136;
                v60 = v129;
              }
              while ( v76 < v136 );
              v72 = v134;
              LODWORD(v65) = v160;
              v73 = *(_QWORD *)&rect.left;
            }
            v134 = ++v72;
          }
          while ( v72 < 2 );
          v68 += v70;
          v69 = (_DWORD)v150 + v128;
          v128 += (int)v150;
          v67 = *(_QWORD *)v145;
        }
        while ( v68 < v143 );
        v49 = v179;
        si128 = (__m128d)_mm_load_si128((const __m128i *)&_xmm);
        v63 = hob;
        v61 = v131;
      }
      v131 = ++v61;
      ++v153;
      v63 += 16;
      hob = v63;
    }
    while ( v153 < v137 );
  }
  ListOfBestSourceMatches::ListOfBestSourceMatches((ListOfBestSourceMatches *)Block, 4);
  *(_QWORD *)v145 = 0;
  *(__m128d *)&v145[8] = si128;
  v146 = 0;
  ListOfBestSourceMatches::GetBest((ListOfBestSourceMatches *)v191, (struct SourceMatch *)v145);
  ListOfBestSourceMatches::ApplyValue((ListOfBestSourceMatches *)Block, (const struct SourceMatch *)v145);
  ListOfBestSourceMatches::GetBest((ListOfBestSourceMatches *)v190, (struct SourceMatch *)v145);
  ListOfBestSourceMatches::ApplyValue((ListOfBestSourceMatches *)Block, (const struct SourceMatch *)v145);
  ListOfBestSourceMatches::GetBest((ListOfBestSourceMatches *)v189, (struct SourceMatch *)v145);
  ListOfBestSourceMatches::ApplyValue((ListOfBestSourceMatches *)Block, (const struct SourceMatch *)v145);
  ListOfBestSourceMatches::GetBest((ListOfBestSourceMatches *)v188, (struct SourceMatch *)v145);
  ListOfBestSourceMatches::ApplyValue((ListOfBestSourceMatches *)Block, (const struct SourceMatch *)v145);
  ListOfBestSourceMatches::GetBest((ListOfBestSourceMatches *)Block, (struct SourceMatch *)v145);
  v97 = v180;
  v98 = v186;
  v99 = v182;
  *(_DWORD *)(v182 + 16) = *(_DWORD *)v145 + *v180 - *v186;
  *(_DWORD *)(v99 + 20) = *(_DWORD *)&v145[4] + v97[1] - v98[1];
  *(_OWORD *)v99 = *(_OWORD *)v98;
  *(_DWORD *)(v99 + 24) = v146;
  if ( *(double *)&v145[8] == 3.399999975603521e28 )
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
  v109 = v190[0];
  if ( v190[0] )
  {
    if ( ImagingEngine::s_singleton )
      v110 = *((_QWORD *)ImagingEngine::s_singleton + 10);
    else
      v110 = 0;
    if ( v110 )
    {
      v111 = (*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v110 + 88LL))(v110, v190[0]) == 0;
      v109 = v190[0];
    }
    else
    {
      v111 = 0;
    }
    if ( !v111 && v109 )
      free(v109);
    v190[0] = 0;
  }
  v112 = v191[0];
  if ( v191[0] )
  {
    if ( ImagingEngine::s_singleton )
      v113 = *((_QWORD *)ImagingEngine::s_singleton + 10);
    else
      v113 = 0;
    if ( v113 )
    {
      v114 = (*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v113 + 88LL))(v113, v191[0]) == 0;
      v112 = v191[0];
    }
    else
    {
      v114 = 0;
    }
    if ( !v114 && v112 )
      free(v112);
    v191[0] = 0;
  }
  if ( v192 )
    free(v192);
  if ( v49 )
    DeleteObject(v49);
  if ( v45 )
  {
    v115 = ImagingEngine::s_singleton ? *((_QWORD *)ImagingEngine::s_singleton + 10) : 0LL;
    if ( !v115 || (*(unsigned int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v115 + 88LL))(v115, v45) != 0 )
      free(v45);
  }
  if ( v44 )
  {
    v117 = ImagingEngine::s_singleton ? *((_QWORD *)ImagingEngine::s_singleton + 10) : 0LL;
    if ( !v117 || (*(unsigned int (__fastcall **)(__int64, float *))(*(_QWORD *)v117 + 88LL))(v117, v44) != 0 )
      free(v44);
  }
  if ( v46 )
  {
    v119 = ImagingEngine::s_singleton ? *((_QWORD *)ImagingEngine::s_singleton + 10) : 0LL;
    if ( !v119 || (*(unsigned int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v119 + 88LL))(v119, v46) != 0 )
      free(v46);
  }
  Base::Ptr<ClonePeripheryData>::~Ptr<ClonePeripheryData>(&v165);
  v121 = v170;
  if ( v170 )
  {
    if ( ImagingEngine::s_singleton )
      v122 = *((_QWORD *)ImagingEngine::s_singleton + 10);
    else
      v122 = 0;
    if ( v122 )
    {
      v123 = (*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v122 + 88LL))(v122, v170) == 0;
      v121 = v170;
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
0x1803e4794  mov     rax, rsp
0x1803e4797  push    rbp
0x1803e4798  push    rbx
0x1803e4799  push    rsi
0x1803e479a  push    rdi
0x1803e479b  push    r12
0x1803e479d  push    r13
0x1803e479f  push    r14
0x1803e47a1  push    r15
0x1803e47a3  lea     rbp, [rax-298h]
0x1803e47aa  sub     rsp, 358h
0x1803e47b1  movaps  xmmword ptr [rax-58h], xmm6
0x1803e47b5  movaps  xmmword ptr [rax-68h], xmm7
0x1803e47b9  movaps  xmmword ptr [rax-78h], xmm8
0x1803e47be  movaps  xmmword ptr [rax-88h], xmm9
0x1803e47c6  movaps  xmmword ptr [rax-98h], xmm10
0x1803e47ce  movaps  xmmword ptr [rax-0A8h], xmm11
0x1803e47d6  movaps  xmmword ptr [rax-0B8h], xmm13
0x1803e47de  movaps  xmmword ptr [rax-0C8h], xmm14
0x1803e47e6  movaps  xmmword ptr [rax-0D8h], xmm15
0x1803e47ee  mov     rax, cs:__security_cookie
0x1803e47f5  xor     rax, rsp
0x1803e47f8  mov     [rbp+290h+var_E0], rax
0x1803e47ff  mov     rdi, r9
0x1803e4802  mov     [rbp+290h+var_1B8], r9
0x1803e4809  mov     rsi, r8
0x1803e480c  mov     [rbp+290h+var_1E8], r8
0x1803e4813  mov     [rsp+390h+var_340], edx
0x1803e4817  mov     [rbp+290h+var_2D8], rcx
0x1803e481b  mov     rax, [rbp+290h+arg_20]
0x1803e4822  mov     [rbp+290h+var_1D8], rax
0x1803e4829  movsxd  rax, dword ptr [r8+4]
0x1803e482d  movsxd  rcx, dword ptr [r8+0Ch]
0x1803e4831  sub     rcx, rax
0x1803e4834  mov     [rsp+390h+var_318], rcx
0x1803e4839  mov     edx, 80000000h
0x1803e483e  lea     rax, [rcx+rdx]
0x1803e4842  mov     ecx, 0FFFFFFFFh
0x1803e4847  cmp     rax, rcx
0x1803e484a  ja      loc_1803E579D
0x1803e4850  movsxd  rax, dword ptr [r8]
0x1803e4853  movsxd  r14, dword ptr [r8+8]
0x1803e4857  sub     r14, rax
0x1803e485a  mov     [rbp+290h+var_2A8], r14
0x1803e485e  lea     rax, [r14+rdx]
0x1803e4862  cmp     rax, rcx
0x1803e4865  ja      loc_1803E579D
0x1803e486b  movsxd  rax, dword ptr [r9]
0x1803e486e  movsxd  r12, dword ptr [r9+8]
0x1803e4872  sub     r12, rax
0x1803e4875  lea     rax, [rdx+r12]
0x1803e4879  cmp     rax, rcx
0x1803e487c  ja      loc_1803E579D
0x1803e4882  movsxd  rax, dword ptr [r9+4]
0x1803e4886  movsxd  r13, dword ptr [r9+0Ch]
0x1803e488a  sub     r13, rax
0x1803e488d  mov     [rbp+290h+var_2E8], r13
0x1803e4891  lea     rax, [rdx+r13]
0x1803e4895  cmp     rax, rcx
0x1803e4898  ja      loc_1803E579D
0x1803e489e  mov     [rbp+290h+var_280], 0
0x1803e48a6  mov     [rbp+290h+var_278], r12d
0x1803e48aa  mov     [rbp+290h+var_274], r13d
0x1803e48ae  lea     rdx, [rbp+290h+var_280]
0x1803e48b2  lea     rcx, [rbp+290h+var_250]
0x1803e48b6  call    ??0PatchPoints@@QEAA@U?$RectT@UIntegerTypes@@@@@Z; PatchPoints::PatchPoints(RectT<IntegerTypes>)
0x1803e48bb  mov     ecx, [rbp+290h+var_248]
0x1803e48be  mov     [rsp+390h+var_34C], ecx
0x1803e48c2  mov     eax, ecx
0x1803e48c4  mov     r15d, 1
0x1803e48ca  and     eax, 80000003h
0x1803e48cf  jge     short loc_1803E48DA
0x1803e48d1  sub     eax, r15d
0x1803e48d4  or      eax, 0FFFFFFFCh
0x1803e48d7  add     eax, r15d
0x1803e48da  mov     ebx, ecx
0x1803e48dc  sub     ebx, eax
0x1803e48de  mov     eax, 4
0x1803e48e3  cmp     ebx, eax
0x1803e48e5  cmovl   ebx, eax
0x1803e48e8  mov     [rsp+390h+var_348], ebx
0x1803e48ec  movups  xmm0, xmmword ptr [rdi]
0x1803e48ef  movdqu  xmmword ptr [rbp+290h+var_310], xmm0
0x1803e48f4  mov     r8d, [rsi+4]
0x1803e48f8  neg     r8d
0x1803e48fb  mov     edx, [rsi]
0x1803e48fd  neg     edx
0x1803e48ff  lea     rcx, [rbp+290h+var_310]
0x1803e4903  call    ?OffsetRect@?$RectT@UIntegerTypes@@@@QEAAXHH@Z; RectT<IntegerTypes>::OffsetRect(int,int)
0x1803e4908  mov     edi, ebx
0x1803e490a  mov     [rsp+390h+ho], rdi
0x1803e490f  mov     eax, 0Ch
0x1803e4914  mul     rdi
0x1803e4917  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1803e491e  cmovb   rax, rcx
0x1803e4922  mov     rcx, rax; Size
0x1803e4925  call    cs:__imp_malloc
0x1803e492b  mov     [rbp+290h+var_2A0], rax
0x1803e492f  test    rax, rax
0x1803e4932  jz      loc_1803E57A7
0x1803e4938  mov     [rbp+290h+var_280], rax
0x1803e493c  lea     rdx, aBlemishremoval_8; "BlemishRemovalRedArray"
0x1803e4943  mov     ecx, edi
0x1803e4945  call    ??$LargeAllocationNew@M@@YAPEAM_KPEB_W@Z; LargeAllocationNew<float>(unsigned __int64,wchar_t const *)
0x1803e494a  mov     rsi, rax
0x1803e494d  mov     [rbp+290h+var_1D0], rax
0x1803e4954  lea     rdx, aBlemishremoval_2; "BlemishRemovalGreenArray"
0x1803e495b  mov     ecx, edi
0x1803e495d  call    ??$LargeAllocationNew@M@@YAPEAM_KPEB_W@Z; LargeAllocationNew<float>(unsigned __int64,wchar_t const *)
0x1803e4962  mov     rbx, rax
0x1803e4965  mov     [rbp+290h+var_1F8], rax
0x1803e496c  lea     rdx, aBlemishremoval; "BlemishRemovalBlueArray"
0x1803e4973  mov     ecx, edi
0x1803e4975  call    ??$LargeAllocationNew@M@@YAPEAM_KPEB_W@Z; LargeAllocationNew<float>(unsigned __int64,wchar_t const *)
0x1803e497a  mov     rdi, rax
0x1803e497d  mov     [rbp+290h+var_1E0], rax
0x1803e4984  lea     eax, [r12+r13]
0x1803e4988  cdq
0x1803e4989  and     edx, 7Fh
0x1803e498c  add     eax, edx
0x1803e498e  sar     eax, 7
0x1803e4991  cmp     eax, r15d
0x1803e4994  cmovl   eax, r15d
0x1803e4998  mov     dword ptr [rsp+390h+var_330+4], eax
0x1803e499c  xorps   xmm1, xmm1
0x1803e499f  movsd   [rbp+290h+var_298], xmm1
0x1803e49a4  xorps   xmm2, xmm2
0x1803e49a7  movsd   [rbp+290h+var_288], xmm2
0x1803e49ac  xorps   xmm3, xmm3
0x1803e49af  movsd   [rbp+290h+var_290], xmm3
0x1803e49b4  xorps   xmm15, xmm15
0x1803e49b8  mov     ecx, [rsp+390h+var_348]
0x1803e49bc  test    ecx, ecx
0x1803e49be  jle     loc_1803E4BDC
0x1803e49c4  lea     r10d, [r14-1]
0x1803e49c8  mov     [rsp+390h+var_334], r10d
0x1803e49cd  mov     rax, [rsp+390h+var_318]
0x1803e49d2  dec     eax
0x1803e49d4  mov     dword ptr [rsp+390h+var_330], eax
0x1803e49d8  xor     ecx, ecx
0x1803e49da  mov     [rsp+390h+var_344], ecx
0x1803e49de  mov     [rsp+390h+var_320], rbx
0x1803e49e3  mov     rax, [rbp+290h+var_2A0]
0x1803e49e7  add     rax, 8
0x1803e49eb  mov     [rbp+290h+var_2E0], rax
0x1803e49ef  mov     rax, rsi
0x1803e49f2  sub     rax, rbx
0x1803e49f5  mov     [rbp+290h+var_2C8], rax
0x1803e49f9  mov     rax, rdi
0x1803e49fc  sub     rax, rbx
0x1803e49ff  mov     [rbp+290h+var_2D0], rax
0x1803e4a03  mov     esi, [rsp+390h+var_348]
0x1803e4a07  mov     edi, dword ptr [rbp+290h+var_310]
0x1803e4a0a  mov     rbx, [rsp+390h+ho]
0x1803e4a0f  mov     r14, [rbp+290h+var_2C8]
0x1803e4a13  mov     eax, ecx
0x1803e4a15  cdq
0x1803e4a16  idiv    esi
0x1803e4a18  movsxd  rcx, eax
0x1803e4a1b  mov     rax, [rbp+290h+var_250]
0x1803e4a1f  mov     rax, [rax+rcx*8]
0x1803e4a23  lea     r8d, [rax+rdi]
0x1803e4a27  shr     rax, 20h
0x1803e4a2b  mov     r9d, dword ptr [rbp+290h+var_310+4]
0x1803e4a2f  add     r9d, eax
0x1803e4a32  mov     eax, r9d
0x1803e4a35  imul    eax, [rsp+390h+var_340]
0x1803e4a3a  movsxd  rcx, eax
0x1803e4a3d  movsxd  rdx, r8d
0x1803e4a40  shl     rdx, 4
0x1803e4a44  lea     r11, [rdx+rcx]
0x1803e4a48  add     r11, [rbp+290h+var_2D8]
0x1803e4a4c  mov     eax, r15d
0x1803e4a4f  cmp     r8d, r10d
0x1803e4a52  mov     r10, 0FFFFFFFFFFFFFFFFh
0x1803e4a59  cmovz   eax, r10d
0x1803e4a5d  add     eax, r8d
0x1803e4a60  movsxd  r10, eax
0x1803e4a63  shl     r10, 4
0x1803e4a67  add     r10, rcx
0x1803e4a6a  add     r10, [rbp+290h+var_2D8]
0x1803e4a6e  mov     eax, r15d
0x1803e4a71  cmp     r9d, dword ptr [rsp+390h+var_330]
0x1803e4a76  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1803e4a7d  cmovz   eax, ecx
0x1803e4a80  add     eax, r9d
0x1803e4a83  imul    eax, [rsp+390h+var_340]
0x1803e4a88  movsxd  rcx, eax
0x1803e4a8b  add     rcx, rdx
0x1803e4a8e  add     rcx, [rbp+290h+var_2D8]
0x1803e4a92  mov     eax, [r11]
0x1803e4a95  mov     rdx, [rsp+390h+var_320]
0x1803e4a9a  mov     [rdx+r14], eax
0x1803e4a9e  mov     eax, [r11+4]
0x1803e4aa2  mov     [rdx], eax
0x1803e4aa4  mov     eax, [r11+8]
0x1803e4aa8  mov     rdx, [rbp+290h+var_2D0]
0x1803e4aac  mov     r13, [rsp+390h+var_320]
0x1803e4ab1  mov     [rdx+r13], eax
0x1803e4ab5  sub     r8d, edi
0x1803e4ab8  mov     rax, [rbp+290h+var_2E0]
0x1803e4abc  mov     [rax-8], r8d
0x1803e4ac0  mov     eax, r12d
0x1803e4ac3  sub     eax, r8d
0x1803e4ac6  sub     eax, r15d
0x1803e4ac9  mov     r8, [rbp+290h+var_2E0]
0x1803e4acd  mov     [r8-4], eax
0x1803e4ad1  sub     r9d, dword ptr [rbp+290h+var_310+4]
0x1803e4ad5  mov     [r8], r9d
0x1803e4ad8  movss   xmm0, dword ptr [r13+r14+0]
0x1803e4adf  cvtps2pd xmm0, xmm0
0x1803e4ae2  addsd   xmm1, xmm0
0x1803e4ae6  movsd   [rbp+290h+var_298], xmm1
0x1803e4aeb  movss   xmm1, dword ptr [r13+0]
0x1803e4af1  cvtps2pd xmm1, xmm1
0x1803e4af4  addsd   xmm2, xmm1
0x1803e4af8  movsd   [rbp+290h+var_288], xmm2
0x1803e4afd  movss   xmm0, dword ptr [r13+rdx+0]
0x1803e4b04  cvtps2pd xmm0, xmm0
0x1803e4b07  addsd   xmm3, xmm0
0x1803e4b0b  movsd   [rbp+290h+var_290], xmm3
0x1803e4b10  movss   xmm4, dword ptr [r11]
0x1803e4b15  movaps  xmm2, xmm4
0x1803e4b18  subss   xmm2, dword ptr [r10]
0x1803e4b1d  movss   xmm5, dword ptr [r11+4]
0x1803e4b23  movaps  xmm0, xmm5
0x1803e4b26  subss   xmm0, dword ptr [r10+4]
0x1803e4b2c  movss   xmm3, dword ptr [r11+8]
0x1803e4b32  movaps  xmm1, xmm3
0x1803e4b35  subss   xmm1, dword ptr [r10+8]
0x1803e4b3b  subss   xmm4, dword ptr [rcx]
0x1803e4b3f  subss   xmm5, dword ptr [rcx+4]
0x1803e4b44  subss   xmm3, dword ptr [rcx+8]
0x1803e4b49  mulss   xmm2, xmm2
0x1803e4b4d  mulss   xmm0, xmm0
0x1803e4b51  addss   xmm2, xmm0
0x1803e4b55  mulss   xmm1, xmm1
0x1803e4b59  addss   xmm2, xmm1
0x1803e4b5d  cvtps2pd xmm1, xmm2
0x1803e4b60  addsd   xmm15, xmm1
0x1803e4b65  mulss   xmm5, xmm5
0x1803e4b69  mulss   xmm4, xmm4
0x1803e4b6d  addss   xmm5, xmm4
0x1803e4b71  mulss   xmm3, xmm3
0x1803e4b75  addss   xmm5, xmm3
0x1803e4b79  cvtps2pd xmm0, xmm5
0x1803e4b7c  addsd   xmm15, xmm0
0x1803e4b81  mov     ecx, [rsp+390h+var_344]
0x1803e4b85  add     ecx, [rsp+390h+var_34C]
0x1803e4b89  mov     [rsp+390h+var_344], ecx
0x1803e4b8d  add     r8, 0Ch
0x1803e4b91  mov     [rbp+290h+var_2E0], r8
0x1803e4b95  lea     rax, [r13+4]
0x1803e4b99  mov     [rsp+390h+var_320], rax
0x1803e4b9e  sub     rbx, r15
0x1803e4ba1  movsd   xmm1, [rbp+290h+var_298]
0x1803e4ba6  movsd   xmm2, [rbp+290h+var_288]
0x1803e4bab  movsd   xmm3, [rbp+290h+var_290]
0x1803e4bb0  mov     r10d, [rsp+390h+var_334]
0x1803e4bb5  jnz     loc_1803E4A13
0x1803e4bbb  mov     rbx, [rbp+290h+var_1F8]
0x1803e4bc2  mov     rdi, [rbp+290h+var_1E0]
0x1803e4bc9  mov     rsi, [rbp+290h+var_1D0]
0x1803e4bd0  mov     r13, [rbp+290h+var_2E8]
0x1803e4bd4  mov     r14, [rbp+290h+var_2A8]
0x1803e4bd8  mov     ecx, [rsp+390h+var_348]
0x1803e4bdc  lea     eax, [rcx+rcx]
0x1803e4bdf  movd    xmm0, eax
0x1803e4be3  cvtdq2pd xmm0, xmm0
0x1803e4be7  divsd   xmm15, xmm0
0x1803e4bec  mov     eax, 66666667h
0x1803e4bf1  imul    ecx
0x1803e4bf3  mov     ecx, edx
0x1803e4bf5  sar     ecx, 1
0x1803e4bf7  mov     eax, ecx
0x1803e4bf9  shr     eax, 1Fh
0x1803e4bfc  add     ecx, eax
0x1803e4bfe  mov     [rbp+290h+var_2C0], ecx
0x1803e4c01  mov     qword ptr [rbp+290h+rect.left], 0
0x1803e4c0c  sub     r14d, r12d
0x1803e4c0f  add     r14d, r15d
0x1803e4c12  mov     [rbp+290h+rect.right], r14d
0x1803e4c19  mov     rax, [rsp+390h+var_318]
0x1803e4c1e  sub     eax, r13d
0x1803e4c21  add     eax, r15d
0x1803e4c24  mov     [rbp+290h+rect.bottom], eax
0x1803e4c2a  lea     rcx, [rbp+290h+rect]; lprect
0x1803e4c31  call    cs:__imp_CreateRectRgnIndirect
0x1803e4c37  mov     r14, rax
0x1803e4c3a  mov     [rbp+290h+var_1F0], rax
0x1803e4c41  movaps  xmm0, xmmword ptr [rbp+290h+var_310]
0x1803e4c45  movdqa  xmmword ptr [rbp+290h+var_F0.left], xmm0
0x1803e4c4d  mov     eax, dword ptr [rbp+290h+var_310]
0x1803e4c50  sub     eax, r12d
0x1803e4c53  add     eax, r15d
0x1803e4c56  mov     [rbp+290h+var_F0.left], eax
0x1803e4c5c  mov     eax, r15d
0x1803e4c5f  sub     eax, r13d
0x1803e4c62  add     [rbp+290h+var_F0.top], eax
0x1803e4c68  lea     rcx, [rbp+290h+var_F0]; lprect
  ... truncated ...
```
