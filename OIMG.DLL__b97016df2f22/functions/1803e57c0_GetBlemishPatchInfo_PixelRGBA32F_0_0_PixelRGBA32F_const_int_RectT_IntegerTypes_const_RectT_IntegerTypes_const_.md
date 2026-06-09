# GetBlemishPatchInfo<PixelRGBA32F,0,0>(PixelRGBA32F const *,int,RectT<IntegerTypes> const &,RectT<IntegerTypes> const &,__MIDL___MIDL_itf_Imaging_0001_0125_0001 *)

- ea: `0x1803e57c0`
- end: `0x1803e6882`
- name: `??$GetBlemishPatchInfo@UPixelRGBA32F@@$0A@$0A@@@YA_NPEBUPixelRGBA32F@@HAEBU?$RectT@UIntegerTypes@@@@1PEAU__MIDL___MIDL_itf_Imaging_0001_0125_0001@@@Z`
- size: `4290`
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
- `0x1803e57c0`
- `0x1803e6884`
- `0x1803e6bb4`
- `0x1804c6944`
- `0x18056bd00`
- `0x18056dc8e`
- `0x18056dcca`
- `0x18056dce0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1803e5943`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1803e5943`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e6510`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e6570`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e65d0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e6630`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e6690`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e66a9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e66ff`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e6746`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e678d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e67f4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e6510`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e6570`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e65d0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e6630`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e6690`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e66a9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e66ff`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e6746`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e678d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1803e67f4`
- `GDI32!CombineRgn` at `0x1803e5cf4`
- `GDI32!CombineRgn` at `0x1803e5cf4`
- `GDI32!DeleteObject` at `0x1803e5d04`
- `GDI32!DeleteObject` at `0x1803e66b8`
- `GDI32!DeleteObject` at `0x1803e5d04`
- `GDI32!DeleteObject` at `0x1803e66b8`
- `GDI32!CreateRectRgnIndirect` at `0x1803e5c9c`
- `GDI32!CreateRectRgnIndirect` at `0x1803e5cda`
- `GDI32!CreateRectRgnIndirect` at `0x1803e5c9c`
- `GDI32!CreateRectRgnIndirect` at `0x1803e5cda`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
char __fastcall GetBlemishPatchInfo<PixelRGBA32F,0,0>(__int64 a1, int a2, int *a3, int *a4, __int64 a5)
{
  __int64 v7; // r14
  __int64 v8; // r12
  __int64 v9; // r13
  char v10; // r15
  unsigned int v11; // ebx
  unsigned int v12; // edi
  char *v13; // rax
  _BYTE *v14; // rsi
  float *v15; // rbx
  _BYTE *v16; // rdi
  int v17; // eax
  double v18; // xmm1_8
  double v19; // xmm2_8
  double v20; // xmm3_8
  double v21; // xmm6_8
  int v22; // r8d
  int v23; // ecx
  int v24; // edx
  int v25; // r10d
  __int64 v26; // rax
  int v27; // r8d
  int v28; // eax
  float *v29; // r11
  int v30; // edx
  float *v31; // r9
  int v32; // edx
  float *v33; // r8
  int v34; // r10d
  int v35; // ecx
  _DWORD *v36; // r10
  float v37; // xmm0_4
  float v38; // xmm1_4
  HRGN v39; // r14
  int v40; // eax
  int v41; // ecx
  int v42; // ecx
  int v43; // eax
  float v44; // xmm7_4
  int v45; // r9d
  int v46; // eax
  int v47; // r10d
  int v48; // r11d
  int v49; // ecx
  int v50; // r12d
  double v51; // xmm10_8
  double v52; // xmm3_8
  double v53; // xmm14_8
  int v54; // r8d
  __m128d si128; // xmm15
  char *v56; // rdx
  double v57; // xmm8_8
  __int64 v58; // r10
  int v59; // ecx
  __int64 v60; // r8
  int v61; // r14d
  int v62; // eax
  int v63; // ecx
  double v64; // xmm15_8
  int v65; // edx
  float *v66; // r8
  int v67; // eax
  float *v68; // r9
  int v69; // r13d
  double v70; // xmm6_8
  double v71; // xmm5_8
  double v72; // xmm4_8
  double v73; // xmm7_8
  int v74; // r10d
  float *v75; // r11
  char *v76; // rdx
  int *v77; // rax
  int v78; // r8d
  char *v79; // rdx
  __int64 v80; // rax
  int v81; // edx
  float *v82; // rcx
  double v83; // xmm9_8
  double v84; // xmm10_8
  double v85; // xmm11_8
  __int64 v86; // rax
  double v87; // xmm5_8
  double v88; // xmm4_8
  double v89; // xmm7_8
  double v90; // xmm9_8
  void **v91; // rcx
  _DWORD *v92; // rdx
  _DWORD *v93; // rcx
  __int64 v94; // r8
  void *v95; // rcx
  __int64 v96; // r8
  bool v97; // al
  void *v98; // rcx
  __int64 v99; // r8
  bool v100; // al
  void *v101; // rcx
  __int64 v102; // r8
  bool v103; // al
  void *v104; // rcx
  __int64 v105; // r8
  bool v106; // al
  void *v107; // rcx
  __int64 v108; // r8
  bool v109; // al
  __int64 v110; // rcx
  __int64 v112; // rcx
  __int64 v114; // rcx
  void *v116; // rcx
  __int64 v117; // r8
  bool v118; // al
  char v120; // [rsp+48h] [rbp-C0h]
  int v121; // [rsp+4Ch] [rbp-BCh]
  int v122; // [rsp+4Ch] [rbp-BCh]
  int v123; // [rsp+50h] [rbp-B8h]
  int v124; // [rsp+50h] [rbp-B8h]
  int v125; // [rsp+50h] [rbp-B8h]
  int v126; // [rsp+54h] [rbp-B4h]
  int v127; // [rsp+54h] [rbp-B4h]
  int v128; // [rsp+58h] [rbp-B0h]
  int v129; // [rsp+58h] [rbp-B0h]
  float *v131; // [rsp+60h] [rbp-A8h]
  float *v132; // [rsp+60h] [rbp-A8h]
  int v133; // [rsp+68h] [rbp-A0h]
  int v134; // [rsp+68h] [rbp-A0h]
  int v135; // [rsp+6Ch] [rbp-9Ch]
  HGDIOBJ ho; // [rsp+70h] [rbp-98h]
  HRGN hoa; // [rsp+70h] [rbp-98h]
  char *hob; // [rsp+70h] [rbp-98h]
  signed __int64 v139; // [rsp+78h] [rbp-90h]
  double v140; // [rsp+78h] [rbp-90h]
  signed __int64 v141; // [rsp+80h] [rbp-88h]
  double v142; // [rsp+80h] [rbp-88h]
  _BYTE v143[24]; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int8 v144; // [rsp+A0h] [rbp-68h]
  int v145; // [rsp+A8h] [rbp-60h]
  int v146; // [rsp+ACh] [rbp-5Ch]
  int v147; // [rsp+B0h] [rbp-58h]
  __int64 v148; // [rsp+B8h] [rbp-50h]
  __int64 v149; // [rsp+C0h] [rbp-48h]
  _DWORD *v150; // [rsp+C8h] [rbp-40h]
  __int64 v151; // [rsp+D0h] [rbp-38h]
  int v152; // [rsp+D8h] [rbp-30h]
  int v153; // [rsp+DCh] [rbp-2Ch]
  int v154; // [rsp+E0h] [rbp-28h]
  int v155; // [rsp+E4h] [rbp-24h]
  int v156; // [rsp+E8h] [rbp-20h]
  int v157; // [rsp+ECh] [rbp-1Ch]
  int v158; // [rsp+F0h] [rbp-18h]
  char *v159; // [rsp+F8h] [rbp-10h]
  __int64 v160; // [rsp+100h] [rbp-8h]
  double v161; // [rsp+108h] [rbp+0h]
  double v162; // [rsp+110h] [rbp+8h]
  double v163; // [rsp+118h] [rbp+10h]
  char *v164; // [rsp+120h] [rbp+18h]
  _BYTE *v165; // [rsp+128h] [rbp+20h] BYREF
  int v166; // [rsp+130h] [rbp+28h]
  int v167; // [rsp+134h] [rbp+2Ch]
  char v168[8]; // [rsp+138h] [rbp+30h] BYREF
  __m128d v169; // [rsp+140h] [rbp+38h]
  void *v170; // [rsp+158h] [rbp+50h] BYREF
  int v171; // [rsp+160h] [rbp+58h]
  _DWORD v172[2]; // [rsp+168h] [rbp+60h] BYREF
  double v173; // [rsp+170h] [rbp+68h]
  double v174; // [rsp+178h] [rbp+70h]
  bool v175; // [rsp+180h] [rbp+78h]
  void *Block[4]; // [rsp+188h] [rbp+80h] BYREF
  double v177; // [rsp+1A8h] [rbp+A0h]
  signed __int64 v178; // [rsp+1B0h] [rbp+A8h]
  signed __int64 v179; // [rsp+1B8h] [rbp+B0h]
  __int64 v180; // [rsp+1C0h] [rbp+B8h]
  HRGN v181; // [rsp+1C8h] [rbp+C0h]
  _DWORD *v182; // [rsp+1D0h] [rbp+C8h]
  _DWORD *v183; // [rsp+1D8h] [rbp+D0h]
  char *v184; // [rsp+1E0h] [rbp+D8h] BYREF
  __int64 v185; // [rsp+1E8h] [rbp+E0h]
  void *v186[4]; // [rsp+1F0h] [rbp+E8h] BYREF
  void *v187[4]; // [rsp+210h] [rbp+108h] BYREF
  void *v188[4]; // [rsp+230h] [rbp+128h] BYREF
  void *v189[4]; // [rsp+250h] [rbp+148h] BYREF
  void *v190; // [rsp+270h] [rbp+168h] BYREF
  unsigned __int64 v191; // [rsp+278h] [rbp+170h]
  _BYTE *v192; // [rsp+290h] [rbp+188h]
  float *v193; // [rsp+298h] [rbp+190h]
  RECT rect; // [rsp+2A0h] [rbp+198h] BYREF
  RECT v195; // [rsp+2B8h] [rbp+1B0h] BYREF

  v183 = a4;
  v182 = a3;
  v148 = a1;
  v185 = a5;
  v149 = a3[3] - (__int64)a3[1];
  if ( (unsigned __int64)(v149 + 0x80000000LL) > 0xFFFFFFFF
    || (v7 = a3[2] - (__int64)*a3, (unsigned __int64)(v7 + 0x80000000LL) > 0xFFFFFFFF)
    || (v8 = a4[2] - (__int64)*a4, (unsigned __int64)(v8 + 0x80000000LL) > 0xFFFFFFFF)
    || (v9 = a4[3] - (__int64)a4[1], (unsigned __int64)(v9 + 0x80000000LL) > 0xFFFFFFFF) )
  {
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  }
  v165 = 0;
  v166 = v8;
  v167 = v9;
  PatchPoints::PatchPoints(&v170, &v165);
  v123 = v171;
  v10 = 1;
  v11 = v171 - v171 % 4;
  if ( (int)v11 < 4 )
    v11 = 4;
  v121 = v11;
  *(_OWORD *)v143 = *(_OWORD *)a4;
  RectT<IntegerTypes>::OffsetRect(v143, (unsigned int)-*a3, (unsigned int)-a3[1]);
  v12 = v11;
  v13 = (char *)malloc(saturated_mul(v11, 0xCu));
  v159 = v13;
  if ( !v13 )
    ThrowOOM();
  v184 = v13;
  v14 = (_BYTE *)LargeAllocationNew<float>(v11, L"BlemishRemovalRedArray");
  v192 = v14;
  v15 = (float *)LargeAllocationNew<float>(v11, L"BlemishRemovalGreenArray");
  v193 = v15;
  v16 = (_BYTE *)LargeAllocationNew<float>(v12, L"BlemishRemovalBlueArray");
  v165 = v16;
  v17 = ((int)v8 + (int)v9) / 128;
  if ( v17 < 1 )
    v17 = 1;
  v135 = v17;
  v18 = 0.0;
  v161 = 0.0;
  v19 = 0.0;
  v162 = 0.0;
  v20 = 0.0;
  v163 = 0.0;
  v21 = 0.0;
  v128 = 0;
  v22 = *(_DWORD *)v143;
  v23 = v121;
  if ( v121 <= 0 )
  {
LABEL_23:
    v177 = v21 / (double)(2 * v23);
    v152 = v23 / 5;
    *(_QWORD *)&rect.left = 0;
    rect.right = v7 - v8 + 1;
    rect.bottom = v149 - v9 + 1;
    v39 = CreateRectRgnIndirect(&rect);
    v181 = v39;
    *(_QWORD *)&v195.right = *(_QWORD *)&v143[8];
    v195.left = *(_DWORD *)v143 - v8 + 1;
    v195.top = 1 - v9 + *(_DWORD *)&v143[4];
    hoa = CreateRectRgnIndirect(&v195);
    CombineRgn(v39, v39, hoa, 4);
    if ( hoa )
      DeleteObject(hoa);
    RegionRects::RegionRects((RegionRects *)&v190, v39, 0x7FFFFFFF);
    v40 = 4;
    if ( (int)v191 < 4 )
      v40 = v191;
    v134 = v40;
    ListOfBestSourceMatches::ListOfBestSourceMatches((ListOfBestSourceMatches *)v189, 1);
    ListOfBestSourceMatches::ListOfBestSourceMatches((ListOfBestSourceMatches *)v188, 1);
    ListOfBestSourceMatches::ListOfBestSourceMatches((ListOfBestSourceMatches *)v187, 1);
    ListOfBestSourceMatches::ListOfBestSourceMatches((ListOfBestSourceMatches *)v186, 1);
    v41 = 0;
    if ( (int)v8 / 4 - v135 > 0 )
      v41 = (int)v8 / 4 - v135;
    v146 = v41;
    v42 = v135 / 2;
    if ( (int)v8 / 8 < v135 / 2 )
      v42 = (int)v8 / 8;
    v43 = 1;
    if ( v42 > 1 )
      v43 = v42;
    v157 = v43 - v135;
    v44 = sqrtf_0(0.5);
    v124 = (int)floor_0((float)((float)(int)v8 * v44) + 0.5);
    v45 = (int)floor_0((float)((float)(int)v9 * v44) + 0.5);
    v46 = v124 - 2;
    if ( v124 - 2 > 20 )
      v46 = 20;
    v156 = v46;
    v47 = v45 - 2;
    if ( v45 - 2 > 20 )
      v47 = 20;
    v155 = v47;
    if ( v46 <= 0 || v47 <= 0 )
    {
      v120 = 0;
      v48 = 0;
      v49 = 0;
    }
    else
    {
      v120 = 1;
      v48 = v124 / (v46 + 2);
      if ( v48 < 1 )
        v48 = 1;
      v49 = v45 / (v47 + 2);
      if ( v49 < 1 )
        v49 = 1;
    }
    v145 = v49;
    v127 = v48;
    v154 = v48 + ((int)v8 - v124) / 2;
    v153 = v49 + ((int)v9 - v45) / 2;
    v50 = v121;
    v51 = (float)((float)v121 * 3.0);
    v140 = v51;
    v52 = (float)(0.5 / (float)v121);
    v142 = v52;
    v53 = (double)v121 * 0.3;
    v54 = 0;
    v129 = 0;
    si128 = (__m128d)_mm_load_si128((const __m128i *)&_xmm);
    if ( v134 <= 0 )
    {
LABEL_95:
      ListOfBestSourceMatches::ListOfBestSourceMatches((ListOfBestSourceMatches *)Block, 4);
      *(_QWORD *)v143 = 0;
      *(__m128d *)&v143[8] = si128;
      v144 = 0;
      ListOfBestSourceMatches::GetBest((ListOfBestSourceMatches *)v189, (struct SourceMatch *)v143);
      ListOfBestSourceMatches::ApplyValue((ListOfBestSourceMatches *)Block, (const struct SourceMatch *)v143);
      ListOfBestSourceMatches::GetBest((ListOfBestSourceMatches *)v188, (struct SourceMatch *)v143);
      ListOfBestSourceMatches::ApplyValue((ListOfBestSourceMatches *)Block, (const struct SourceMatch *)v143);
      ListOfBestSourceMatches::GetBest((ListOfBestSourceMatches *)v187, (struct SourceMatch *)v143);
      ListOfBestSourceMatches::ApplyValue((ListOfBestSourceMatches *)Block, (const struct SourceMatch *)v143);
      ListOfBestSourceMatches::GetBest((ListOfBestSourceMatches *)v186, (struct SourceMatch *)v143);
      ListOfBestSourceMatches::ApplyValue((ListOfBestSourceMatches *)Block, (const struct SourceMatch *)v143);
      ListOfBestSourceMatches::GetBest((ListOfBestSourceMatches *)Block, (struct SourceMatch *)v143);
      v92 = v182;
      v93 = v183;
      v94 = v185;
      *(_DWORD *)(v185 + 16) = *(_DWORD *)v143 + *v182 - *v183;
      *(_DWORD *)(v94 + 20) = v92[1] + *(_DWORD *)&v143[4] - v93[1];
      *(_OWORD *)v94 = *(_OWORD *)v93;
      *(_DWORD *)(v94 + 24) = v144;
      if ( *(double *)&v143[8] == 3.399999975603521e28 )
        v10 = 0;
      v95 = Block[0];
      if ( Block[0] )
      {
        if ( ImagingEngine::s_singleton )
          v96 = *((_QWORD *)ImagingEngine::s_singleton + 10);
        else
          v96 = 0;
        if ( v96 )
        {
          v97 = (*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v96 + 88LL))(v96, Block[0]) == 0;
          v95 = Block[0];
        }
        else
        {
          v97 = 0;
        }
        if ( !v97 && v95 )
          free(v95);
        Block[0] = 0;
      }
      v98 = v186[0];
      if ( v186[0] )
      {
        if ( ImagingEngine::s_singleton )
          v99 = *((_QWORD *)ImagingEngine::s_singleton + 10);
        else
          v99 = 0;
        if ( v99 )
        {
          v100 = (*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v99 + 88LL))(v99, v186[0]) == 0;
          v98 = v186[0];
        }
        else
        {
          v100 = 0;
        }
        if ( !v100 && v98 )
          free(v98);
        v186[0] = 0;
      }
      v101 = v187[0];
      if ( v187[0] )
      {
        if ( ImagingEngine::s_singleton )
          v102 = *((_QWORD *)ImagingEngine::s_singleton + 10);
        else
          v102 = 0;
        if ( v102 )
        {
          v103 = (*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v102 + 88LL))(v102, v187[0]) == 0;
          v101 = v187[0];
        }
        else
        {
          v103 = 0;
        }
        if ( !v103 && v101 )
          free(v101);
        v187[0] = 0;
      }
      v104 = v188[0];
      if ( v188[0] )
      {
        if ( ImagingEngine::s_singleton )
          v105 = *((_QWORD *)ImagingEngine::s_singleton + 10);
        else
          v105 = 0;
        if ( v105 )
        {
          v106 = (*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v105 + 88LL))(v105, v188[0]) == 0;
          v104 = v188[0];
        }
        else
        {
          v106 = 0;
        }
        if ( !v106 && v104 )
          free(v104);
        v188[0] = 0;
      }
      v107 = v189[0];
      if ( v189[0] )
      {
        if ( ImagingEngine::s_singleton )
          v108 = *((_QWORD *)ImagingEngine::s_singleton + 10);
        else
          v108 = 0;
        if ( v108 )
        {
          v109 = (*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v108 + 88LL))(v108, v189[0]) == 0;
          v107 = v189[0];
        }
        else
        {
          v109 = 0;
        }
        if ( !v109 && v107 )
          free(v107);
        v189[0] = 0;
      }
      if ( v190 )
        free(v190);
      if ( v39 )
        DeleteObject(v39);
      goto LABEL_156;
    }
    v151 = 0;
    v56 = 0;
    hob = 0;
    while ( 1 )
    {
      v57 = si128.m128d_f64[0];
      v169 = si128;
      if ( v54 < 0 )
        ATL::BaseAtlThrow(-2147024809);
      if ( v54 >= v191 )
        ATL::BaseAtlThrow(-2147024809);
      v58 = *(int *)((char *)v190 + (_QWORD)v56);
      v158 = *(_DWORD *)((char *)v190 + (_QWORD)v56);
      v147 = *(_DWORD *)((char *)v190 + (_QWORD)v56 + 8);
      v59 = *(_DWORD *)((char *)v190 + (_QWORD)v56 + 4);
      LODWORD(v150) = *(_DWORD *)((char *)v190 + (_QWORD)v56 + 12);
      if ( v59 < (int)v150 )
        break;
LABEL_94:
      v129 = ++v54;
      ++v151;
      v56 += 16;
      hob = v56;
      if ( v151 >= v134 )
        goto LABEL_95;
    }
    v60 = 16 * v58;
    *(_QWORD *)v143 = 16 * v58;
    v61 = v59;
    v62 = a2 * v59;
    v125 = a2 * v59;
    v63 = v135;
    LODWORD(v149) = v135 * a2;
    *(_QWORD *)&v169.m128d_f64[1] = *(_OWORD *)&_mm_unpackhi_pd(si128, si128);
    v64 = v177;
LABEL_51:
    v65 = 0;
    v122 = 0;
    v66 = (float *)(v148 + v62 + v60);
    *(_QWORD *)&rect.left = v66;
    v67 = v147;
LABEL_52:
    v68 = v66;
    v132 = v66;
    v69 = v58;
    if ( (int)v58 >= v67 )
      goto LABEL_91;
    v180 = 16LL * v63;
    while ( 1 )
    {
      v70 = 0.0;
      v71 = 0.0;
      v72 = 0.0;
      v73 = 0.0;
      v74 = 0;
      v160 = 0;
      if ( v50 > 0 )
      {
        v75 = v15;
        v76 = v159;
        v77 = (int *)(v159 + 8);
        v164 = v159 + 8;
        v178 = v14 - (_BYTE *)v15;
        v179 = v16 - (_BYTE *)v15;
        while ( 1 )
        {
          v78 = *v77;
          v79 = &v76[12 * v74];
          if ( v122 )
            v79 += 4;
          v80 = 4LL * *(int *)v79;
          v81 = a2;
          v82 = (float *)((char *)&v68[v80] + a2 * v78);
          if ( v82[3] <= 0.0 && *v82 <= 0.0 && v82[1] <= 0.0 && v82[2] <= 0.0 )
            goto LABEL_89;
          v83 = *v82;
          v84 = v82[1];
          v85 = v82[2];
          v70 = v70
              + (v84 - *v75) * (v84 - *v75)
              + (v83 - *(float *)((char *)v75 + v178)) * (v83 - *(float *)((char *)v75 + v178))
              + (v85 - *(float *)((char *)v75 + v179)) * (v85 - *(float *)((char *)v75 + v179));
          if ( (v74 & 0xF) == 0xF && v70 > v169.m128d_f64[1] * 2.0 )
          {
            if ( v160 >= v152 )
              goto LABEL_89;
            v69 += v146;
            v86 = v146;
            goto LABEL_88;
          }
          v71 = v71 + v83;
          v72 = v72 + v84;
          v73 = v73 + v85;
          ++v74;
          ++v160;
          v77 = (int *)(v164 + 12);
          v164 += 12;
          ++v75;
          if ( v74 >= v50 )
          {
            v51 = v140;
            v52 = v142;
            v48 = v127;
            goto LABEL_70;
          }
          v76 = v159;
        }
      }
      v81 = a2;
LABEL_70:
      v87 = v71 - v161;
      v88 = v72 - v162;
      v89 = v73 - v163;
      v90 = v70;
      if ( v53 > COERCE_DOUBLE(*(_QWORD *)&v88 & _xmm)
               + COERCE_DOUBLE(*(_QWORD *)&v87 & _xmm)
               + COERCE_DOUBLE(*(_QWORD *)&v89 & _xmm) )
        v70 = v70 - (v88 * v88 + v87 * v87 + v89 * v89) * v52;
      if ( v120 )
      {
        v70 = v70
            + COERCE_DOUBLE(
                COERCE_UNSIGNED_INT64(sub_1803E6BB4(v148, v81, v69 + v154, v61 + v153, v48, v145, v156, v155) - v64)
              & _xmm)
            * v51;
        v68 = v132;
      }
      if ( v57 > v70 )
        break;
      if ( v70 > v57 * 3.0 )
      {
        v86 = v146;
LABEL_87:
        v69 += v86;
LABEL_88:
        v68 += 4 * v86;
      }
LABEL_89:
      v63 = v135;
      v69 += v135;
      v68 = (float *)((char *)v68 + v180);
      v132 = v68;
      v67 = v147;
      v51 = v140;
      v52 = v142;
      v48 = v127;
      if ( v69 >= v147 )
      {
        v65 = v122;
        LODWORD(v58) = v158;
        v66 = *(float **)&rect.left;
LABEL_91:
        v122 = ++v65;
        if ( v65 >= 2 )
        {
          v61 += v63;
          v62 = v149 + v125;
          v125 += v149;
          v60 = *(_QWORD *)v143;
          if ( v61 >= (int)v150 )
          {
            v39 = v181;
            si128 = (__m128d)_mm_load_si128((const __m128i *)&_xmm);
            v56 = hob;
            v54 = v129;
            goto LABEL_94;
          }
          goto LABEL_51;
        }
        goto LABEL_52;
      }
    }
    v172[0] = v69;
    v172[1] = v61;
    v173 = v70;
    v174 = v90;
    v175 = v122 == 1;
    if ( v129 )
    {
      switch ( v129 )
      {
        case 1:
          ListOfBestSourceMatches::ApplyValue((ListOfBestSourceMatches *)v188, (const struct SourceMatch *)v172);
          v91 = v188;
          break;
        case 2:
          ListOfBestSourceMatches::ApplyValue((ListOfBestSourceMatches *)v187, (const struct SourceMatch *)v172);
          v91 = v187;
          break;
        case 3:
          ListOfBestSourceMatches::ApplyValue((ListOfBestSourceMatches *)v186, (const struct SourceMatch *)v172);
          v91 = v186;
          break;
        default:
LABEL_84:
          v86 = v157;
          goto LABEL_87;
      }
    }
    else
    {
      ListOfBestSourceMatches::ApplyValue((ListOfBestSourceMatches *)v189, (const struct SourceMatch *)v172);
      v91 = v189;
    }
    ListOfBestSourceMatches::GetWorst((ListOfBestSourceMatches *)v91, (struct SourceMatch *)v168);
    v68 = v132;
    v57 = v169.m128d_f64[0];
    goto LABEL_84;
  }
  v24 = 0;
  v126 = 0;
  v131 = v15;
  v150 = v159 + 8;
  v141 = v14 - (_BYTE *)v15;
  v139 = v16 - (_BYTE *)v15;
  v25 = v149;
  while ( 1 )
  {
    v26 = *((_QWORD *)v170 + v24 / v23);
    v27 = v26 + v22;
    v133 = v27;
    v28 = *(_DWORD *)&v143[4] + HIDWORD(v26);
    ho = (HGDIOBJ)(a2 * (*(_DWORD *)&v143[4] + HIDWORD(v26)));
    v151 = 16LL * v27;
    v29 = (float *)((char *)ho + v151 + v148);
    if ( v29[3] <= 0.0 && *v29 <= 0.0 && v29[1] <= 0.0 && v29[2] <= 0.0 )
      break;
    v30 = 1;
    if ( v27 == (_DWORD)v7 - 1 )
      v30 = -1;
    v31 = (float *)((char *)ho + 16 * v27 + 16 * v30 + v148);
    v32 = 1;
    if ( v28 == v25 - 1 )
      v32 = -1;
    v33 = (float *)(v148 + v151 + a2 * (v28 + v32));
    *(float *)((char *)v131 + v141) = *v29;
    *v131 = v29[1];
    *(float *)((char *)v131 + v139) = v29[2];
    v34 = v133 - *(_DWORD *)v143;
    *(v150 - 2) = v133 - *(_DWORD *)v143;
    v35 = v8 - v34 - 1;
    v36 = v150;
    *(v150 - 1) = v35;
    *v36 = v28 - *(_DWORD *)&v143[4];
    v161 = v18 + *(float *)((char *)v131 + v141);
    v162 = v19 + *v131;
    v163 = v20 + *(float *)((char *)v131 + v139);
    v37 = v29[1] - v31[1];
    v38 = v29[2] - v31[2];
    v21 = v21
        + (float)((float)((float)((float)(*v29 - *v31) * (float)(*v29 - *v31)) + (float)(v37 * v37)) + (float)(v38 * v38))
        + (float)((float)((float)((float)(*v29 - *v33) * (float)(*v29 - *v33))
                        + (float)((float)(v29[1] - v33[1]) * (float)(v29[1] - v33[1])))
                + (float)((float)(v29[2] - v33[2]) * (float)(v29[2] - v33[2])));
    ++v128;
    v24 = v123 + v126;
    v126 += v123;
    v150 = v36 + 3;
    ++v131;
    v23 = v121;
    v25 = v149;
    if ( v128 >= v121 )
      goto LABEL_23;
    v18 = v161;
    v19 = v162;
    v20 = v163;
    v22 = *(_DWORD *)v143;
  }
  v10 = 0;
LABEL_156:
  if ( v16 )
  {
    v110 = ImagingEngine::s_singleton ? *((_QWORD *)ImagingEngine::s_singleton + 10) : 0LL;
    if ( !v110 || (*(unsigned int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v110 + 88LL))(v110, v16) != 0 )
      free(v16);
  }
  if ( v15 )
  {
    v112 = ImagingEngine::s_singleton ? *((_QWORD *)ImagingEngine::s_singleton + 10) : 0LL;
    if ( !v112 || (*(unsigned int (__fastcall **)(__int64, float *))(*(_QWORD *)v112 + 88LL))(v112, v15) != 0 )
      free(v15);
  }
  if ( v14 )
  {
    v114 = ImagingEngine::s_singleton ? *((_QWORD *)ImagingEngine::s_singleton + 10) : 0LL;
    if ( !v114 || (*(unsigned int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v114 + 88LL))(v114, v14) != 0 )
      free(v14);
  }
  Base::Ptr<ClonePeripheryData>::~Ptr<ClonePeripheryData>(&v184);
  v116 = v170;
  if ( v170 )
  {
    if ( ImagingEngine::s_singleton )
      v117 = *((_QWORD *)ImagingEngine::s_singleton + 10);
    else
      v117 = 0;
    if ( v117 )
    {
      v118 = (*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v117 + 88LL))(v117, v170) == 0;
      v116 = v170;
    }
    else
    {
      v118 = 0;
    }
    if ( !v118 && v116 )
      free(v116);
  }
  return v10;
}

```

## disassembly

```asm
0x1803e57c0  mov     rax, rsp
0x1803e57c3  push    rbp
0x1803e57c4  push    rbx
0x1803e57c5  push    rsi
0x1803e57c6  push    rdi
0x1803e57c7  push    r12
0x1803e57c9  push    r13
0x1803e57cb  push    r14
0x1803e57cd  push    r15
0x1803e57cf  lea     rbp, [rax-2A8h]
0x1803e57d6  sub     rsp, 368h
0x1803e57dd  movaps  xmmword ptr [rax-58h], xmm6
0x1803e57e1  movaps  xmmword ptr [rax-68h], xmm7
0x1803e57e5  movaps  xmmword ptr [rax-78h], xmm8
0x1803e57ea  movaps  xmmword ptr [rax-88h], xmm9
0x1803e57f2  movaps  xmmword ptr [rax-98h], xmm10
0x1803e57fa  movaps  xmmword ptr [rax-0A8h], xmm11
0x1803e5802  movaps  xmmword ptr [rax-0B8h], xmm12
0x1803e580a  movaps  xmmword ptr [rax-0C8h], xmm14
0x1803e5812  movaps  xmmword ptr [rax-0D8h], xmm15
0x1803e581a  mov     rax, cs:__security_cookie
0x1803e5821  xor     rax, rsp
0x1803e5824  mov     [rbp+2A0h+var_E0], rax
0x1803e582b  mov     rdi, r9
0x1803e582e  mov     [rbp+2A0h+var_1D0], r9
0x1803e5835  mov     rsi, r8
0x1803e5838  mov     [rbp+2A0h+var_1D8], r8
0x1803e583f  mov     dword ptr [rsp+3A0h+var_350+4], edx
0x1803e5843  mov     [rbp+2A0h+var_2F0], rcx
0x1803e5847  mov     rax, [rbp+2A0h+arg_20]
0x1803e584e  mov     [rbp+2A0h+var_1C0], rax
0x1803e5855  movsxd  rax, dword ptr [r8+4]
0x1803e5859  movsxd  rcx, dword ptr [r8+0Ch]
0x1803e585d  sub     rcx, rax
0x1803e5860  mov     [rbp+2A0h+var_2E8], rcx
0x1803e5864  mov     edx, 80000000h
0x1803e5869  lea     rax, [rcx+rdx]
0x1803e586d  mov     ecx, 0FFFFFFFFh
0x1803e5872  cmp     rax, rcx
0x1803e5875  ja      loc_1803E6865
0x1803e587b  movsxd  rax, dword ptr [r8]
0x1803e587e  movsxd  r14, dword ptr [r8+8]
0x1803e5882  sub     r14, rax
0x1803e5885  lea     rax, [r14+rdx]
0x1803e5889  cmp     rax, rcx
0x1803e588c  ja      loc_1803E6865
0x1803e5892  movsxd  rax, dword ptr [r9]
0x1803e5895  movsxd  r12, dword ptr [r9+8]
0x1803e5899  sub     r12, rax
0x1803e589c  lea     rax, [rdx+r12]
0x1803e58a0  cmp     rax, rcx
0x1803e58a3  ja      loc_1803E6865
0x1803e58a9  movsxd  rax, dword ptr [r9+4]
0x1803e58ad  movsxd  r13, dword ptr [r9+0Ch]
0x1803e58b1  sub     r13, rax
0x1803e58b4  lea     rax, [rdx+r13]
0x1803e58b8  cmp     rax, rcx
0x1803e58bb  ja      loc_1803E6865
0x1803e58c1  mov     [rbp+2A0h+var_280], 0
0x1803e58c9  mov     [rbp+2A0h+var_278], r12d
0x1803e58cd  mov     [rbp+2A0h+var_274], r13d
0x1803e58d1  lea     rdx, [rbp+2A0h+var_280]
0x1803e58d5  lea     rcx, [rbp+2A0h+var_250]
0x1803e58d9  call    ??0PatchPoints@@QEAA@U?$RectT@UIntegerTypes@@@@@Z; PatchPoints::PatchPoints(RectT<IntegerTypes>)
0x1803e58de  mov     ecx, [rbp+2A0h+var_248]
0x1803e58e1  mov     [rsp+3A0h+var_358], ecx
0x1803e58e5  mov     eax, ecx
0x1803e58e7  mov     r15d, 1
0x1803e58ed  and     eax, 80000003h
0x1803e58f2  jge     short loc_1803E58FD
0x1803e58f4  sub     eax, r15d
0x1803e58f7  or      eax, 0FFFFFFFCh
0x1803e58fa  add     eax, r15d
0x1803e58fd  mov     ebx, ecx
0x1803e58ff  sub     ebx, eax
0x1803e5901  mov     eax, 4
0x1803e5906  cmp     ebx, eax
0x1803e5908  cmovl   ebx, eax
0x1803e590b  mov     [rsp+3A0h+var_35C], ebx
0x1803e590f  movups  xmm0, xmmword ptr [rdi]
0x1803e5912  movdqu  xmmword ptr [rbp+2A0h+var_320], xmm0
0x1803e5917  mov     r8d, [rsi+4]
0x1803e591b  neg     r8d
0x1803e591e  mov     edx, [rsi]
0x1803e5920  neg     edx
0x1803e5922  lea     rcx, [rbp+2A0h+var_320]
0x1803e5926  call    ?OffsetRect@?$RectT@UIntegerTypes@@@@QEAAXHH@Z; RectT<IntegerTypes>::OffsetRect(int,int)
0x1803e592b  mov     edi, ebx
0x1803e592d  mov     eax, 0Ch
0x1803e5932  mul     rdi
0x1803e5935  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1803e593c  cmovb   rax, rcx
0x1803e5940  mov     rcx, rax; Size
0x1803e5943  call    cs:__imp_malloc
0x1803e5949  mov     [rbp+2A0h+var_2B0], rax
0x1803e594d  test    rax, rax
0x1803e5950  jz      loc_1803E686E
0x1803e5956  mov     [rbp+2A0h+var_1C8], rax
0x1803e595d  lea     rdx, aBlemishremoval_8; "BlemishRemovalRedArray"
0x1803e5964  mov     ecx, edi
0x1803e5966  call    ??$LargeAllocationNew@M@@YAPEAM_KPEB_W@Z; LargeAllocationNew<float>(unsigned __int64,wchar_t const *)
0x1803e596b  mov     rsi, rax
0x1803e596e  mov     [rbp+2A0h+var_118], rax
0x1803e5975  lea     rdx, aBlemishremoval_2; "BlemishRemovalGreenArray"
0x1803e597c  mov     ecx, edi
0x1803e597e  call    ??$LargeAllocationNew@M@@YAPEAM_KPEB_W@Z; LargeAllocationNew<float>(unsigned __int64,wchar_t const *)
0x1803e5983  mov     rbx, rax
0x1803e5986  mov     [rbp+2A0h+var_110], rax
0x1803e598d  lea     rdx, aBlemishremoval; "BlemishRemovalBlueArray"
0x1803e5994  mov     ecx, edi
0x1803e5996  call    ??$LargeAllocationNew@M@@YAPEAM_KPEB_W@Z; LargeAllocationNew<float>(unsigned __int64,wchar_t const *)
0x1803e599b  mov     rdi, rax
0x1803e599e  mov     [rbp+2A0h+var_280], rax
0x1803e59a2  lea     eax, [r12+r13]
0x1803e59a6  cdq
0x1803e59a7  and     edx, 7Fh
0x1803e59aa  add     eax, edx
0x1803e59ac  sar     eax, 7
0x1803e59af  cmp     eax, r15d
0x1803e59b2  cmovl   eax, r15d
0x1803e59b6  mov     dword ptr [rsp+3A0h+var_340+4], eax
0x1803e59ba  xorps   xmm1, xmm1
0x1803e59bd  movsd   [rbp+2A0h+var_2A0], xmm1
0x1803e59c2  xorps   xmm2, xmm2
0x1803e59c5  movsd   [rbp+2A0h+var_298], xmm2
0x1803e59ca  xorps   xmm3, xmm3
0x1803e59cd  movsd   [rbp+2A0h+var_290], xmm3
0x1803e59d2  xorps   xmm6, xmm6
0x1803e59d5  mov     dword ptr [rsp+3A0h+var_350], 0
0x1803e59dd  mov     r8d, dword ptr [rbp+2A0h+var_320]
0x1803e59e1  xorps   xmm12, xmm12
0x1803e59e5  mov     ecx, [rsp+3A0h+var_35C]
0x1803e59e9  test    ecx, ecx
0x1803e59eb  jle     loc_1803E5C41
0x1803e59f1  xor     edx, edx
0x1803e59f3  mov     [rsp+3A0h+var_354], edx
0x1803e59f7  mov     [rsp+3A0h+var_348], rbx
0x1803e59fc  mov     rax, [rbp+2A0h+var_2B0]
0x1803e5a00  add     rax, 8
0x1803e5a04  mov     [rbp+2A0h+var_2E0], rax
0x1803e5a08  mov     rax, rsi
0x1803e5a0b  sub     rax, rbx
0x1803e5a0e  mov     [rsp+3A0h+var_328], rax
0x1803e5a13  mov     rax, rdi
0x1803e5a16  sub     rax, rbx
0x1803e5a19  mov     [rsp+3A0h+var_330], rax
0x1803e5a1e  mov     r10, [rbp+2A0h+var_2E8]
0x1803e5a22  mov     eax, edx
0x1803e5a24  cdq
0x1803e5a25  idiv    ecx
0x1803e5a27  movsxd  rcx, eax
0x1803e5a2a  mov     rax, [rbp+2A0h+var_250]
0x1803e5a2e  mov     rax, [rax+rcx*8]
0x1803e5a32  add     r8d, eax
0x1803e5a35  mov     dword ptr [rsp+3A0h+var_340], r8d
0x1803e5a3a  shr     rax, 20h
0x1803e5a3e  add     eax, dword ptr [rbp+2A0h+var_320+4]
0x1803e5a41  movsxd  rdx, r8d
0x1803e5a44  mov     ecx, eax
0x1803e5a46  imul    ecx, dword ptr [rsp+3A0h+var_350+4]
0x1803e5a4b  movsxd  rcx, ecx
0x1803e5a4e  mov     [rsp+3A0h+ho], rcx
0x1803e5a53  shl     rdx, 4
0x1803e5a57  mov     [rbp+2A0h+var_2D8], rdx
0x1803e5a5b  lea     r11, [rdx+rcx]
0x1803e5a5f  add     r11, [rbp+2A0h+var_2F0]
0x1803e5a63  movss   xmm0, dword ptr [r11+0Ch]
0x1803e5a69  comiss  xmm0, xmm12
0x1803e5a6d  ja      short loc_1803E5A96
0x1803e5a6f  movss   xmm0, dword ptr [r11]
0x1803e5a74  comiss  xmm0, xmm12
0x1803e5a78  ja      short loc_1803E5A96
0x1803e5a7a  movss   xmm0, dword ptr [r11+4]
0x1803e5a80  comiss  xmm0, xmm12
0x1803e5a84  ja      short loc_1803E5A96
0x1803e5a86  movss   xmm0, dword ptr [r11+8]
0x1803e5a8c  comiss  xmm0, xmm12
0x1803e5a90  jbe     loc_1803E5C36
0x1803e5a96  lea     ecx, [r14-1]
0x1803e5a9a  mov     edx, r15d
0x1803e5a9d  cmp     r8d, ecx
0x1803e5aa0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1803e5aa7  cmovz   edx, ecx
0x1803e5aaa  add     edx, r8d
0x1803e5aad  movsxd  r9, edx
0x1803e5ab0  shl     r9, 4
0x1803e5ab4  add     r9, [rsp+3A0h+ho]
0x1803e5ab9  add     r9, [rbp+2A0h+var_2F0]
0x1803e5abd  lea     ecx, [r10-1]
0x1803e5ac1  mov     edx, r15d
0x1803e5ac4  cmp     eax, ecx
0x1803e5ac6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1803e5acd  cmovz   edx, ecx
0x1803e5ad0  add     edx, eax
0x1803e5ad2  imul    edx, dword ptr [rsp+3A0h+var_350+4]
0x1803e5ad7  movsxd  r8, edx
0x1803e5ada  add     r8, [rbp+2A0h+var_2D8]
0x1803e5ade  add     r8, [rbp+2A0h+var_2F0]
0x1803e5ae2  mov     ecx, [r11]
0x1803e5ae5  mov     rdx, [rsp+3A0h+var_328]
0x1803e5aea  mov     r10, [rsp+3A0h+var_348]
0x1803e5aef  mov     [r10+rdx], ecx
0x1803e5af3  mov     ecx, [r11+4]
0x1803e5af7  mov     [r10], ecx
0x1803e5afa  mov     ecx, [r11+8]
0x1803e5afe  mov     r10, [rsp+3A0h+var_330]
0x1803e5b03  mov     rdx, [rsp+3A0h+var_348]
0x1803e5b08  mov     [r10+rdx], ecx
0x1803e5b0c  mov     r10d, dword ptr [rsp+3A0h+var_340]
0x1803e5b11  sub     r10d, dword ptr [rbp+2A0h+var_320]
0x1803e5b15  mov     rcx, [rbp+2A0h+var_2E0]
0x1803e5b19  mov     [rcx-8], r10d
0x1803e5b1d  mov     ecx, r12d
0x1803e5b20  sub     ecx, r10d
0x1803e5b23  sub     ecx, r15d
0x1803e5b26  mov     r10, [rbp+2A0h+var_2E0]
0x1803e5b2a  mov     [r10-4], ecx
0x1803e5b2e  sub     eax, dword ptr [rbp+2A0h+var_320+4]
0x1803e5b31  mov     [r10], eax
0x1803e5b34  mov     rdx, [rsp+3A0h+var_328]
0x1803e5b39  mov     rcx, [rsp+3A0h+var_348]
0x1803e5b3e  movss   xmm0, dword ptr [rcx+rdx]
0x1803e5b43  cvtps2pd xmm0, xmm0
0x1803e5b46  addsd   xmm1, xmm0
0x1803e5b4a  movsd   [rbp+2A0h+var_2A0], xmm1
0x1803e5b4f  movss   xmm1, dword ptr [rcx]
0x1803e5b53  cvtps2pd xmm1, xmm1
0x1803e5b56  addsd   xmm2, xmm1
0x1803e5b5a  movsd   [rbp+2A0h+var_298], xmm2
0x1803e5b5f  mov     rax, [rsp+3A0h+var_330]
0x1803e5b64  movss   xmm0, dword ptr [rcx+rax]
0x1803e5b69  cvtps2pd xmm0, xmm0
0x1803e5b6c  addsd   xmm3, xmm0
0x1803e5b70  movsd   [rbp+2A0h+var_290], xmm3
0x1803e5b75  movss   xmm5, dword ptr [r11]
0x1803e5b7a  movaps  xmm2, xmm5
0x1803e5b7d  subss   xmm2, dword ptr [r9]
0x1803e5b82  movss   xmm3, dword ptr [r11+4]
0x1803e5b88  movaps  xmm0, xmm3
0x1803e5b8b  subss   xmm0, dword ptr [r9+4]
0x1803e5b91  movss   xmm4, dword ptr [r11+8]
0x1803e5b97  movaps  xmm1, xmm4
0x1803e5b9a  subss   xmm1, dword ptr [r9+8]
0x1803e5ba0  subss   xmm5, dword ptr [r8]
0x1803e5ba5  subss   xmm3, dword ptr [r8+4]
0x1803e5bab  subss   xmm4, dword ptr [r8+8]
0x1803e5bb1  mulss   xmm2, xmm2
0x1803e5bb5  mulss   xmm0, xmm0
0x1803e5bb9  addss   xmm2, xmm0
0x1803e5bbd  mulss   xmm1, xmm1
0x1803e5bc1  addss   xmm2, xmm1
0x1803e5bc5  cvtps2pd xmm1, xmm2
0x1803e5bc8  addsd   xmm6, xmm1
0x1803e5bcc  mulss   xmm5, xmm5
0x1803e5bd0  mulss   xmm3, xmm3
0x1803e5bd4  addss   xmm5, xmm3
0x1803e5bd8  mulss   xmm4, xmm4
0x1803e5bdc  addss   xmm5, xmm4
0x1803e5be0  cvtps2pd xmm0, xmm5
0x1803e5be3  addsd   xmm6, xmm0
0x1803e5be7  mov     r9d, dword ptr [rsp+3A0h+var_350]
0x1803e5bec  add     r9d, r15d
0x1803e5bef  mov     dword ptr [rsp+3A0h+var_350], r9d
0x1803e5bf4  mov     edx, [rsp+3A0h+var_354]
0x1803e5bf8  add     edx, [rsp+3A0h+var_358]
0x1803e5bfc  mov     [rsp+3A0h+var_354], edx
0x1803e5c00  add     r10, 0Ch
0x1803e5c04  mov     [rbp+2A0h+var_2E0], r10
0x1803e5c08  add     rcx, 4
0x1803e5c0c  mov     [rsp+3A0h+var_348], rcx
0x1803e5c11  mov     ecx, [rsp+3A0h+var_35C]
0x1803e5c15  cmp     r9d, ecx
0x1803e5c18  mov     r10, [rbp+2A0h+var_2E8]
0x1803e5c1c  jge     short loc_1803E5C41
0x1803e5c1e  movsd   xmm1, [rbp+2A0h+var_2A0]
0x1803e5c23  movsd   xmm2, [rbp+2A0h+var_298]
0x1803e5c28  movsd   xmm3, [rbp+2A0h+var_290]
0x1803e5c2d  mov     r8d, dword ptr [rbp+2A0h+var_320]
0x1803e5c31  jmp     loc_1803E5A22
0x1803e5c36  xor     r13d, r13d
0x1803e5c39  mov     r15b, r13b
0x1803e5c3c  jmp     loc_1803E66BF
0x1803e5c41  lea     eax, [rcx+rcx]
0x1803e5c44  movd    xmm0, eax
0x1803e5c48  cvtdq2pd xmm0, xmm0
0x1803e5c4c  divsd   xmm6, xmm0
0x1803e5c50  movsd   [rbp+2A0h+var_200], xmm6
0x1803e5c58  mov     eax, 66666667h
0x1803e5c5d  imul    ecx
0x1803e5c5f  mov     ecx, edx
0x1803e5c61  sar     ecx, 1
0x1803e5c63  mov     eax, ecx
0x1803e5c65  shr     eax, 1Fh
0x1803e5c68  add     ecx, eax
0x1803e5c6a  mov     [rbp+2A0h+var_2D0], ecx
0x1803e5c6d  mov     qword ptr [rbp+2A0h+rect.left], 0
0x1803e5c78  sub     r14d, r12d
0x1803e5c7b  add     r14d, r15d
0x1803e5c7e  mov     [rbp+2A0h+rect.right], r14d
0x1803e5c85  mov     rax, [rbp+2A0h+var_2E8]
  ... truncated ...
```
