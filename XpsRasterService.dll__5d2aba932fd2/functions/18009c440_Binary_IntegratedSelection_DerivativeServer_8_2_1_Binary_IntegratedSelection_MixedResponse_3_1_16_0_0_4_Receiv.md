# Binary::IntegratedSelection::DerivativeServer<8,2,1,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<2,8,2,1,1,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0>,1>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x18009c440`
- end: `0x18009ce60`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$01$07$01$00$00V?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@$0A@@IntegratedSelection@Binary@@$00@?$DerivativeServer@$07$01$00V?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@$0A@$03@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `2592`
- prototype: `char __fastcall(__int64, unsigned __int8 **, int *, __int128 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18009d600`

## callees

- `0x180003180`
- `0x1800588e0`
- `0x180067110`
- `0x1800963a0`
- `0x18009c440`

## pseudocode

```c
char __fastcall Binary::IntegratedSelection::DerivativeServer<8,2,1,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<2,8,2,1,1,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0>,1>(
        __int64 a1,
        unsigned __int8 **a2,
        int *a3,
        __int128 *a4)
{
  __int64 v5; // rsi
  unsigned __int8 *v6; // rcx
  unsigned __int8 *v7; // rax
  unsigned __int8 *v8; // rdx
  int v9; // eax
  int v10; // ecx
  __int64 v11; // rdi
  int v12; // r11d
  int v13; // edx
  int v14; // r13d
  int v15; // edx
  int v16; // r15d
  int v17; // ecx
  int v18; // r10d
  __int64 v19; // r8
  int v20; // r9d
  int v21; // r10d
  int v22; // edx
  __int64 v23; // rax
  __int64 v24; // rsi
  __int64 v25; // r14
  __int64 v26; // rbx
  __int64 v27; // r12
  __int64 v28; // rdi
  double v29; // xmm0_8
  float v30; // xmm7_4
  double v31; // xmm0_8
  float v32; // xmm6_4
  double v33; // xmm0_8
  __m128i *v34; // rdi
  int v35; // eax
  int v36; // r14d
  __int64 v37; // rsi
  _DWORD *v38; // r15
  __int64 v39; // rbx
  double v40; // xmm0_8
  float v41; // xmm7_4
  double v42; // xmm0_8
  float v43; // xmm6_4
  double v44; // xmm0_8
  int v45; // eax
  __int64 v46; // rbx
  double v47; // xmm0_8
  float v48; // xmm7_4
  double v49; // xmm0_8
  float v50; // xmm6_4
  double v51; // xmm0_8
  _DWORD *v52; // rax
  int v53; // r14d
  const __m128i *v54; // rcx
  __int64 v55; // r9
  __m128i *v56; // rax
  __int64 v57; // rdx
  __m128i v58; // xmm1
  __m128i v59; // xmm0
  __m128i v60; // xmm1
  __m128i v61; // xmm12
  __m128i *v62; // rdx
  __m128i v63; // xmm10
  __m128 *v64; // rax
  __m128i v65; // xmm11
  __m128i v66; // xmm12
  __m128i v67; // xmm3
  __m128i v68; // xmm8
  __m128i v69; // xmm5
  __m128i v70; // xmm6
  __m128i v71; // xmm3
  __m128i v72; // xmm10
  __int64 v73; // r8
  __m128i v74; // xmm2
  __m128i v75; // xmm5
  __m128i v76; // xmm0
  __m128i v77; // xmm4
  __m128i v78; // xmm1
  __m128i v79; // xmm7
  __m128i v80; // xmm4
  __m128i v81; // xmm0
  __m128i v82; // xmm12
  __m128i si128; // xmm8
  __m128i v84; // xmm9
  __m128i v85; // xmm7
  __m128i v86; // xmm3
  __m128i v87; // xmm4
  __m128i v88; // xmm0
  __m128i v89; // xmm3
  __m128i v90; // xmm2
  __m128i v91; // xmm1
  __m128i v92; // xmm0
  __m128i v93; // xmm4
  __m128i v94; // xmm4
  __m128i v95; // xmm3
  __m128i v96; // xmm0
  __m128i v97; // xmm4
  __m128i v98; // xmm3
  __m128i v99; // xmm1
  __m128i v100; // xmm2
  __m128i v101; // xmm1
  __m128i v102; // xmm0
  __m128i v103; // xmm4
  __m128i v104; // xmm4
  __m128i v105; // xmm3
  __m128i v106; // xmm0
  __m128i v107; // xmm4
  __m128i v108; // xmm3
  __m128i v109; // xmm2
  __m128i v110; // xmm4
  __m128i v111; // xmm3
  int v112; // edx
  unsigned __int8 *v113; // r14
  __int64 v114; // rsi
  __int64 v115; // r12
  __int64 v116; // rbx
  __int64 v117; // r15
  double v118; // xmm0_8
  float v119; // xmm7_4
  double v120; // xmm0_8
  float v121; // xmm6_4
  double v122; // xmm0_8
  int v123; // eax
  double v124; // xmm0_8
  float v125; // xmm7_4
  double v126; // xmm0_8
  float v127; // xmm6_4
  double v128; // xmm0_8
  int v129; // ecx
  int v131; // [rsp+30h] [rbp-D0h]
  __int64 v132; // [rsp+38h] [rbp-C8h]
  __int64 v133; // [rsp+40h] [rbp-C0h]
  __int64 v134; // [rsp+48h] [rbp-B8h]
  __int64 v135; // [rsp+50h] [rbp-B0h]
  __int128 v138; // [rsp+70h] [rbp-90h] BYREF
  __m128i v139; // [rsp+80h] [rbp-80h] BYREF
  __m128i v140; // [rsp+90h] [rbp-70h] BYREF
  __m128i v141; // [rsp+A0h] [rbp-60h] BYREF
  __m128i v142; // [rsp+B0h] [rbp-50h] BYREF
  __m128i v143; // [rsp+C0h] [rbp-40h]
  __m128i v144; // [rsp+D0h] [rbp-30h]
  __m128i v145; // [rsp+E0h] [rbp-20h]
  __m128i v146; // [rsp+F0h] [rbp-10h]
  unsigned __int8 *v147; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int8 *v148; // [rsp+108h] [rbp+8h] BYREF
  _DWORD v149[2]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v150; // [rsp+118h] [rbp+18h]
  __int128 v151; // [rsp+128h] [rbp+28h]
  __int128 v152; // [rsp+138h] [rbp+38h]
  __int128 v153; // [rsp+148h] [rbp+48h]
  __m128i v154; // [rsp+160h] [rbp+60h]
  __m128i v155; // [rsp+170h] [rbp+70h]
  _OWORD v156[5]; // [rsp+180h] [rbp+80h] BYREF
  __m128 v157[11]; // [rsp+1D0h] [rbp+D0h] BYREF
  int v158; // [rsp+280h] [rbp+180h] BYREF
  int v159; // [rsp+284h] [rbp+184h]
  __int64 v160; // [rsp+288h] [rbp+188h]
  char v161[32]; // [rsp+290h] [rbp+190h] BYREF
  int v162; // [rsp+2B0h] [rbp+1B0h]
  int v163; // [rsp+2B4h] [rbp+1B4h]
  int v164; // [rsp+2B8h] [rbp+1B8h]
  _DWORD v165[374]; // [rsp+2BCh] [rbp+1BCh]
  int v166; // [rsp+894h] [rbp+794h]
  int v167; // [rsp+89Ch] [rbp+79Ch]
  int v168; // [rsp+8ACh] [rbp+7ACh]

  v5 = a1;
  v138 = *a4;
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((unsigned int)&v158, 2, 1, (_DWORD)a3, (__int64)&v138, a1 + 8);
  v6 = a2[1];
  v7 = a2[2];
  if ( *a2 <= v6 )
    v6 = *a2;
  v8 = a2[3];
  if ( v6 <= v7 )
    v7 = v6;
  if ( v7 <= v8 )
    v8 = v7;
  *(_QWORD *)&v152 = &v8[v160];
  *((_QWORD *)&v152 + 1) = &v8[v160 + 2];
  *(_QWORD *)&v153 = &v8[v160 + 4];
  *((_QWORD *)&v153 + 1) = &v8[v160 + 6];
  LOBYTE(v9) = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
                 (Binary::IntegratedSelection::SmoothControl *)v161,
                 v8,
                 &v148,
                 &v147);
  if ( (_BYTE)v9 )
  {
    v10 = v158;
    v11 = 0;
    v134 = 0;
    v149[0] = 2;
    v131 = 0;
    if ( v158 > 0 )
    {
      v12 = v164;
      v13 = v162;
      v14 = v159;
      do
      {
        v162 = ++v13;
        if ( v13 == 1 )
        {
          v15 = *(_DWORD *)(v5 + 40);
          v16 = 0;
          v17 = *(_DWORD *)(v5 + 44);
          v18 = *(_DWORD *)(v5 + 28);
          v19 = *(int *)(v5 + 52);
          if ( v163 <= 0 )
            v16 = v163;
          if ( v18 < v17 )
            v18 = *(_DWORD *)(v5 + 44);
          v20 = v19 - 1;
          v21 = v18 - v17;
          v150 = v152;
          if ( v12 < v15 )
            v12 = v15;
          v22 = (v12 - v15) % *(_DWORD *)(v5 + 48);
          v23 = *(_QWORD *)(v5 + 56);
          v24 = v168;
          v151 = v153;
          if ( v21 <= v20 )
            v20 = v21;
          v25 = v20;
          v26 = v23 + 2 * v19 * v22;
          v132 = v11 + v152;
          v27 = v11 + v152;
          *(_QWORD *)&v150 = v11 + v152;
          v147 = (unsigned __int8 *)(v11 + *((_QWORD *)&v150 + 1));
          v133 = v11 + v153;
          *(_QWORD *)&v151 = v11 + v153;
          *((_QWORD *)&v150 + 1) += v11;
          v135 = *((_QWORD *)&v150 + 1);
          v28 = -8 * v16;
          v29 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v28 + *((_QWORD *)&v150 + 1));
          v30 = *(float *)&v29;
          v31 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v28 + v133);
          v32 = *(float *)&v31;
          v33 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v28 + v27);
          v34 = (__m128i *)(v26 + 2 * (v25 + 1));
          *(_WORD *)(v26 + 2 * v25) = (int)fmaxf(
                                             0.0,
                                             fminf(
                                               1023.0,
                                               (float)((float)(*(float *)&v33 + v30) + v32) * (float)(1023.0 / 3.0)));
          v35 = v24 + 1;
          v36 = v149[v24] - v16;
          v37 = v35;
          if ( v35 < 1LL )
          {
            v38 = &v149[v35];
            do
            {
              if ( v36 >= v14 )
                break;
              v39 = 8 * v36;
              v40 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v39 + v135);
              v41 = *(float *)&v40;
              v42 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v39 + v133);
              v43 = *(float *)&v42;
              v44 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v39 + v132);
              v45 = (int)fmaxf(0.0, fminf(1023.0, (float)((float)(*(float *)&v44 + v41) + v43) * (float)(1023.0 / 3.0)));
              if ( (unsigned __int16)v45 > 0x3ECu )
              {
                _mm_lfence();
                v46 = 8 * v36 - 8;
                v147 = (unsigned __int8 *)*((_QWORD *)&v150 + 1);
                v47 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(*((_QWORD *)&v150 + 1) + v46);
                v48 = *(float *)&v47;
                v49 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v46 + v151);
                v27 = v150;
                v50 = *(float *)&v49;
                v51 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v150 + v46);
                v45 = (int)fmaxf(
                             0.0,
                             fminf(1023.0, (float)((float)(*(float *)&v51 + v48) + v50) * (float)(1023.0 / 3.0)));
              }
              v34->m128i_i16[0] = v45;
              ++v37;
              v52 = v38;
              v34 = (__m128i *)((char *)v34 + 2);
              ++v38;
              v36 += *v52;
            }
            while ( v37 < 1 );
          }
          v14 = v159;
          v53 = v36 - 1;
          if ( v53 < v159 - 15 )
          {
            v54 = (const __m128i *)(v132 + 8LL * v53 + 32);
            v55 = ((unsigned int)(v159 - 15 - v53 - 1) >> 4) + 1;
            v53 += 16 * v55;
            do
            {
              v56 = &v141;
              v57 = 2;
              do
              {
                v56 += 4;
                v58 = _mm_loadu_si128(v54 - 1);
                v56[-6] = _mm_loadu_si128(v54 - 2);
                v59 = _mm_loadu_si128(v54);
                v56[-5] = v58;
                v60 = _mm_loadu_si128(v54 + 1);
                v54 += 4;
                v56[-4] = v59;
                v56[-3] = v60;
                --v57;
              }
              while ( v57 );
              v61 = _mm_load_si128(&v139);
              v62 = (__m128i *)v156;
              v63 = _mm_load_si128(&v140);
              v64 = v157;
              v65 = _mm_unpacklo_epi16(v61, v143);
              v66 = _mm_unpackhi_epi16(v61, v143);
              v67 = _mm_load_si128(&v141);
              v68 = _mm_unpackhi_epi16(v67, v145);
              v69 = _mm_load_si128(&v142);
              v70 = _mm_unpacklo_epi16(v63, v144);
              v71 = _mm_unpacklo_epi16(v67, v145);
              v72 = _mm_unpackhi_epi16(v63, v144);
              v73 = 2;
              v74 = _mm_unpacklo_epi16(v69, v146);
              v75 = _mm_unpackhi_epi16(v69, v146);
              v76 = _mm_unpacklo_epi16(v70, v74);
              v77 = _mm_unpacklo_epi16(v65, v71);
              v78 = _mm_unpacklo_epi16(v72, v75);
              v79 = _mm_unpackhi_epi16(v77, v76);
              v80 = _mm_unpacklo_epi16(v77, v76);
              v81 = _mm_unpacklo_epi16(v66, v68);
              v82 = _mm_unpackhi_epi16(v66, v68);
              si128 = _mm_load_si128((const __m128i *)&_xmm);
              v156[2] = _mm_unpackhi_epi16(v81, v78);
              v84 = _mm_load_si128((const __m128i *)&_xmm);
              v155 = v79;
              v85 = _mm_load_si128((const __m128i *)&_xmm);
              v156[1] = _mm_unpacklo_epi16(v81, v78);
              v154 = v80;
              v156[0] = _mm_unpacklo_epi16(_mm_unpackhi_epi16(v65, v71), _mm_unpackhi_epi16(v70, v74));
              v156[3] = _mm_unpacklo_epi16(v82, _mm_unpackhi_epi16(v72, v75));
              do
              {
                v86 = _mm_andnot_si128(_mm_cmpeq_epi16(_mm_loadu_si128(v62 - 2), v84), v62[-2]);
                v87 = _mm_and_si128(v86, si128);
                v88 = _mm_srli_epi16(_mm_slli_epi16(v86, 1u), 0xBu);
                v89 = _mm_slli_epi16(v86, 6u);
                v90 = _mm_add_epi16(_mm_and_si128(_mm_cmpgt_epi16(v88, (__m128i)0LL), v85), v88);
                v91 = _mm_or_si128(
                        _mm_or_si128(
                          _mm_slli_epi32(_mm_unpacklo_epi16(v90, (__m128i)0LL), 0x17u),
                          _mm_slli_epi32(_mm_unpacklo_epi16(v89, (__m128i)0LL), 7u)),
                        _mm_unpacklo_epi16((__m128i)0LL, v87));
                v92 = _mm_unpackhi_epi16((__m128i)0LL, v87);
                v93 = _mm_loadu_si128(v62 - 1);
                v64[2] = (__m128)_mm_or_si128(
                                   _mm_or_si128(
                                     _mm_slli_epi32(_mm_unpackhi_epi16(v90, (__m128i)0LL), 0x17u),
                                     _mm_slli_epi32(_mm_unpackhi_epi16(v89, (__m128i)0LL), 7u)),
                                   v92);
                v94 = _mm_andnot_si128(_mm_cmpeq_epi16(v93, v84), v62[-1]);
                v64[-1] = (__m128)v91;
                v95 = v94;
                v96 = _mm_srli_epi16(_mm_slli_epi16(v94, 1u), 0xBu);
                v97 = _mm_and_si128(v94, si128);
                v98 = _mm_slli_epi16(v95, 6u);
                v99 = _mm_add_epi16(_mm_and_si128(_mm_cmpgt_epi16(v96, (__m128i)0LL), v85), v96);
                v100 = _mm_slli_epi32(_mm_unpackhi_epi16(v99, (__m128i)0LL), 0x17u);
                v101 = _mm_or_si128(
                         _mm_or_si128(
                           _mm_slli_epi32(_mm_unpacklo_epi16(v99, (__m128i)0LL), 0x17u),
                           _mm_slli_epi32(_mm_unpacklo_epi16(v98, (__m128i)0LL), 7u)),
                         _mm_unpacklo_epi16((__m128i)0LL, v97));
                v102 = _mm_unpackhi_epi16((__m128i)0LL, v97);
                v103 = _mm_loadu_si128(v62);
                v64[3] = (__m128)_mm_or_si128(
                                   _mm_or_si128(v100, _mm_slli_epi32(_mm_unpackhi_epi16(v98, (__m128i)0LL), 7u)),
                                   v102);
                v104 = _mm_andnot_si128(_mm_cmpeq_epi16(v103, v84), *v62);
                *v64 = (__m128)v101;
                v105 = v104;
                v106 = _mm_srli_epi16(_mm_slli_epi16(v104, 1u), 0xBu);
                v107 = _mm_and_si128(v104, si128);
                v108 = _mm_slli_epi16(v105, 6u);
                v109 = _mm_add_epi16(_mm_and_si128(_mm_cmpgt_epi16(v106, (__m128i)0LL), v85), v106);
                v64 += 6;
                v62 += 3;
                v64[-5] = (__m128)_mm_or_si128(
                                    _mm_or_si128(
                                      _mm_slli_epi32(_mm_unpacklo_epi16(v109, (__m128i)0LL), 0x17u),
                                      _mm_slli_epi32(_mm_unpacklo_epi16(v108, (__m128i)0LL), 7u)),
                                    _mm_unpacklo_epi16((__m128i)0LL, v107));
                v64[-2] = (__m128)_mm_or_si128(
                                    _mm_or_si128(
                                      _mm_slli_epi32(_mm_unpackhi_epi16(v109, (__m128i)0LL), 0x17u),
                                      _mm_slli_epi32(_mm_unpackhi_epi16(v108, (__m128i)0LL), 7u)),
                                    _mm_unpackhi_epi16((__m128i)0LL, v107));
                --v73;
              }
              while ( v73 );
              v110 = _mm_packs_epi32(
                       _mm_cvttps_epi32(
                         _mm_max_ps(
                           _mm_min_ps(
                             _mm_mul_ps(_mm_add_ps(_mm_add_ps(v157[5], v157[6]), v157[7]), (__m128)_xmm),
                             (__m128)_xmm),
                           (__m128)0LL)),
                       _mm_cvttps_epi32(
                         _mm_max_ps(
                           _mm_min_ps(
                             _mm_mul_ps(_mm_add_ps(_mm_add_ps(v157[8], v157[9]), v157[10]), (__m128)_xmm),
                             (__m128)_xmm),
                           (__m128)0LL)));
              v111 = _mm_cmpgt_epi16(v110, (__m128i)_xmm);
              *v34++ = _mm_add_epi16(
                         _mm_and_si128(
                           _mm_packs_epi32(
                             _mm_cvttps_epi32(
                               _mm_max_ps(
                                 _mm_min_ps(
                                   _mm_mul_ps(_mm_add_ps(_mm_add_ps((__m128)v156[4], v157[0]), v157[1]), (__m128)_xmm),
                                   (__m128)_xmm),
                                 (__m128)0LL)),
                             _mm_cvttps_epi32(
                               _mm_max_ps(
                                 _mm_min_ps(
                                   _mm_mul_ps(_mm_add_ps(_mm_add_ps(v157[2], v157[3]), v157[4]), (__m128)_xmm),
                                   (__m128)_xmm),
                                 (__m128)0LL))),
                           v111),
                         _mm_andnot_si128(v111, v110));
              --v55;
            }
            while ( v55 );
            v14 = v159;
          }
          v112 = v53 + 1;
          if ( v53 + 1 < v14 )
          {
            v113 = &v147[-v151];
            v114 = v151 + 8 * v112;
            v115 = v27 - v151;
            v116 = v151 + 8 * v112 - 8;
            v117 = ((unsigned int)(v14 - v112 - 1) >> 1) + 1;
            do
            {
              v118 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v113[v114]);
              v119 = *(float *)&v118;
              v120 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v114);
              v121 = *(float *)&v120;
              v122 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v115 + v114);
              v123 = (int)fmaxf(
                            0.0,
                            fminf(1023.0, (float)((float)(*(float *)&v122 + v119) + v121) * (float)(1023.0 / 3.0)));
              if ( (unsigned __int16)v123 > 0x3ECu )
              {
                _mm_lfence();
                v124 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v113[v116]);
                v125 = *(float *)&v124;
                v126 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v116);
                v127 = *(float *)&v126;
                v128 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v115 + v116);
                v123 = (int)fmaxf(
                              0.0,
                              fminf(1023.0, (float)((float)(*(float *)&v128 + v125) + v127) * (float)(1023.0 / 3.0)));
              }
              v34->m128i_i16[0] = v123;
              v114 += 16;
              v34 = (__m128i *)((char *)v34 + 2);
              v116 += 16;
              --v117;
            }
            while ( v117 );
            v14 = v159;
          }
          v11 = v134;
          v13 = v162 - v165[v166];
          v129 = v166 + 1;
          v5 = a1;
          if ( v166 + 1 >= v167 )
            v129 = 0;
          v12 = v164 + 1;
          v166 = v129;
          v10 = v158;
          ++v164;
        }
        v11 += *a3;
        v9 = v131 + 1;
        v134 = v11;
        v131 = v9;
      }
      while ( v9 < v10 );
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18009c440  push    rbp
0x18009c442  push    rbx
0x18009c443  push    rsi
0x18009c444  lea     rbp, [rsp-890h]
0x18009c44c  sub     rsp, 990h
0x18009c453  mov     rax, cs:__security_cookie
0x18009c45a  xor     rax, rsp
0x18009c45d  mov     [rbp+8A0h+var_F0], rax
0x18009c464  movups  xmm0, xmmword ptr [r9]
0x18009c468  lea     rax, [rcx+8]
0x18009c46c  mov     [rsp+9A0h+var_940], r8
0x18009c471  mov     [rsp+9A0h+var_978], rax
0x18009c476  mov     rbx, rdx
0x18009c479  mov     edx, 2
0x18009c47e  mov     [rsp+9A0h+var_948], rcx
0x18009c483  mov     rsi, rcx
0x18009c486  movaps  [rsp+9A0h+var_930], xmm0
0x18009c48b  lea     rax, [rsp+9A0h+var_930]
0x18009c490  mov     r9, r8
0x18009c493  lea     rcx, [rbp+8A0h+var_720]
0x18009c49a  mov     [rsp+9A0h+var_980], rax
0x18009c49f  lea     r8d, [rdx-1]
0x18009c4a3  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x18009c4a8  mov     rcx, [rbx+8]
0x18009c4ac  lea     r9, [rbp+8A0h+var_8A0]; unsigned __int8 **
0x18009c4b0  cmp     [rbx], rcx
0x18009c4b3  lea     r8, [rbp+8A0h+var_898]; unsigned __int8 **
0x18009c4b7  mov     rax, [rbx+10h]
0x18009c4bb  cmovbe  rcx, [rbx]
0x18009c4bf  mov     rdx, [rbx+18h]
0x18009c4c3  cmp     rcx, rax
0x18009c4c6  cmovbe  rax, rcx
0x18009c4ca  mov     rcx, [rbp+8A0h+var_718]
0x18009c4d1  cmp     rax, rdx
0x18009c4d4  cmovbe  rdx, rax; unsigned __int8 *
0x18009c4d8  add     rcx, rdx
0x18009c4db  mov     qword ptr [rbp+8A0h+var_868], rcx
0x18009c4df  lea     rax, [rcx+2]
0x18009c4e3  mov     qword ptr [rbp+8A0h+var_868+8], rax
0x18009c4e7  lea     rax, [rcx+4]
0x18009c4eb  mov     qword ptr [rbp+8A0h+var_858], rax
0x18009c4ef  lea     rax, [rcx+6]
0x18009c4f3  lea     rcx, [rbp+8A0h+var_710]; this
0x18009c4fa  mov     qword ptr [rbp+8A0h+var_858+8], rax
0x18009c4fe  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18009c503  test    al, al
0x18009c505  jz      loc_18009CE46
0x18009c50b  mov     ecx, [rbp+8A0h+var_720]
0x18009c511  xor     r8d, r8d
0x18009c514  mov     [rsp+9A0h+var_18], rdi
0x18009c51c  mov     edi, r8d
0x18009c51f  mov     [rsp+9A0h+var_958], r8
0x18009c524  mov     [rbp+8A0h+var_890], 2
0x18009c52b  mov     [rsp+9A0h+var_970], r8d
0x18009c530  test    ecx, ecx
0x18009c532  jle     loc_18009CE3E
0x18009c538  mov     r11d, [rbp+8A0h+var_6E8]
0x18009c53f  mov     edx, [rbp+8A0h+var_6F0]
0x18009c545  mov     [rsp+9A0h+var_20], r12
0x18009c54d  mov     [rsp+9A0h+var_28], r13
0x18009c555  mov     r13d, [rbp+8A0h+var_71C]
0x18009c55c  mov     [rsp+9A0h+var_30], r14
0x18009c564  mov     [rsp+9A0h+var_38], r15
0x18009c56c  movaps  [rsp+9A0h+var_50], xmm6
0x18009c574  movaps  [rsp+9A0h+var_60], xmm7
0x18009c57c  movaps  [rsp+9A0h+var_70], xmm8
0x18009c585  movaps  [rsp+9A0h+var_80], xmm9
0x18009c58e  movaps  [rsp+9A0h+var_90], xmm10
0x18009c597  movaps  [rsp+9A0h+var_A0], xmm11
0x18009c5a0  movaps  [rsp+9A0h+var_B0], xmm12
0x18009c5a9  movaps  [rsp+9A0h+var_C0], xmm13
0x18009c5b2  movss   xmm13, cs:__real@447fc000
0x18009c5bb  movaps  [rsp+9A0h+var_D0], xmm14
0x18009c5c4  movaps  [rsp+9A0h+var_E0], xmm15
0x18009c5cd  nop     dword ptr [rax]
0x18009c5d0  inc     edx
0x18009c5d2  mov     [rbp+8A0h+var_6F0], edx
0x18009c5d8  cmp     edx, 1
0x18009c5db  jnz     loc_18009CDA4
0x18009c5e1  mov     edx, [rsi+28h]
0x18009c5e4  mov     r15d, r8d
0x18009c5e7  mov     ecx, [rsi+2Ch]
0x18009c5ea  mov     eax, [rbp+8A0h+var_6EC]
0x18009c5f0  test    eax, eax
0x18009c5f2  mov     r10d, [rsi+1Ch]
0x18009c5f6  movsxd  r8, dword ptr [rsi+34h]
0x18009c5fa  cmovle  r15d, eax
0x18009c5fe  movups  xmm1, [rbp+8A0h+var_858]
0x18009c602  cmp     r10d, ecx
0x18009c605  movups  xmm0, [rbp+8A0h+var_868]
0x18009c609  cmovl   r10d, ecx
0x18009c60d  lea     r9d, [r8-1]
0x18009c611  sub     r10d, ecx
0x18009c614  cmp     r11d, edx
0x18009c617  movups  [rbp+8A0h+var_888], xmm0
0x18009c61b  cmovl   r11d, edx
0x18009c61f  sub     r11d, edx
0x18009c622  mov     eax, r11d
0x18009c625  cdq
0x18009c626  idiv    dword ptr [rsi+30h]
0x18009c629  mov     rax, [rsi+38h]
0x18009c62d  movsxd  rsi, [rbp+8A0h+var_F4]
0x18009c634  movsxd  rcx, edx
0x18009c637  imul    rcx, r8
0x18009c63b  movups  [rbp+8A0h+var_878], xmm1
0x18009c63f  cmp     r10d, r9d
0x18009c642  cmovle  r9d, r10d
0x18009c646  movsxd  r14, r9d
0x18009c649  lea     rbx, [rax+rcx*2]
0x18009c64d  mov     rcx, qword ptr [rbp+8A0h+var_888+8]
0x18009c651  mov     rax, qword ptr [rbp+8A0h+var_868]
0x18009c655  add     rcx, rdi
0x18009c658  add     rax, rdi
0x18009c65b  mov     [rsp+9A0h+var_950], rcx
0x18009c660  mov     [rsp+9A0h+var_968], rax
0x18009c665  mov     r12, rax
0x18009c668  mov     qword ptr [rbp+8A0h+var_888], rax
0x18009c66c  movq    rax, xmm1
0x18009c671  add     rax, rdi
0x18009c674  mov     [rbp+8A0h+var_8A0], rcx
0x18009c678  mov     [rsp+9A0h+var_960], rax
0x18009c67d  mov     qword ptr [rbp+8A0h+var_878], rax
0x18009c681  mov     eax, r15d
0x18009c684  neg     eax
0x18009c686  mov     qword ptr [rbp+8A0h+var_888+8], rcx
0x18009c68a  shl     eax, 3
0x18009c68d  movsxd  rdi, eax
0x18009c690  add     rcx, rdi
0x18009c693  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18009c698  mov     rcx, [rsp+9A0h+var_960]
0x18009c69d  movaps  xmm7, xmm0
0x18009c6a0  add     rcx, rdi
0x18009c6a3  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18009c6a8  mov     rcx, r12
0x18009c6ab  movaps  xmm6, xmm0
0x18009c6ae  add     rcx, rdi
0x18009c6b1  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18009c6b6  addss   xmm0, xmm7
0x18009c6ba  movaps  xmm1, xmm13
0x18009c6be  divss   xmm1, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x18009c6c6  lea     rdi, [r14+1]
0x18009c6ca  lea     rdi, [rbx+rdi*2]
0x18009c6ce  addss   xmm0, xmm6
0x18009c6d2  movaps  xmm2, xmm13
0x18009c6d6  mulss   xmm0, xmm1
0x18009c6da  minss   xmm2, xmm0
0x18009c6de  xorps   xmm0, xmm0
0x18009c6e1  maxss   xmm0, xmm2
0x18009c6e5  cvttss2si eax, xmm0
0x18009c6e9  mov     [rbx+r14*2], ax
0x18009c6ee  lea     eax, [rsi+1]
0x18009c6f1  mov     r14d, [rbp+rsi*4+8A0h+var_890]
0x18009c6f6  sub     r14d, r15d
0x18009c6f9  movsxd  rsi, eax
0x18009c6fc  cmp     rsi, 1
0x18009c700  jge     loc_18009C810
0x18009c706  lea     r15, [rbp+8A0h+var_890]
0x18009c70a  lea     r15, [r15+rsi*4]
0x18009c70e  xchg    ax, ax
0x18009c710  cmp     r14d, r13d
0x18009c713  jge     loc_18009C810
0x18009c719  mov     rcx, [rsp+9A0h+var_950]
0x18009c71e  lea     eax, ds:0[r14*8]
0x18009c726  movsxd  rbx, eax
0x18009c729  add     rcx, rbx
0x18009c72c  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18009c731  mov     rcx, [rsp+9A0h+var_960]
0x18009c736  movaps  xmm7, xmm0
0x18009c739  add     rcx, rbx
0x18009c73c  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18009c741  mov     rcx, [rsp+9A0h+var_968]
0x18009c746  movaps  xmm6, xmm0
0x18009c749  add     rcx, rbx
0x18009c74c  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18009c751  addss   xmm0, xmm7
0x18009c755  movaps  xmm1, xmm13
0x18009c759  divss   xmm1, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x18009c761  mov     ecx, 3ECh
0x18009c766  addss   xmm0, xmm6
0x18009c76a  movaps  xmm2, xmm13
0x18009c76e  mulss   xmm0, xmm1
0x18009c772  minss   xmm2, xmm0
0x18009c776  xorps   xmm0, xmm0
0x18009c779  maxss   xmm0, xmm2
0x18009c77d  cvttss2si eax, xmm0
0x18009c781  cmp     ax, cx
0x18009c784  jbe     short loc_18009C7F2
0x18009c786  lfence
0x18009c789  lea     eax, ds:0[r14*8]
0x18009c791  add     eax, 0FFFFFFF8h
0x18009c794  movsxd  rbx, eax
0x18009c797  mov     rax, qword ptr [rbp+8A0h+var_888+8]
0x18009c79b  mov     [rbp+8A0h+var_8A0], rax
0x18009c79f  lea     rcx, [rax+rbx]
0x18009c7a3  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18009c7a8  mov     rcx, qword ptr [rbp+8A0h+var_878]
0x18009c7ac  movaps  xmm7, xmm0
0x18009c7af  add     rcx, rbx
0x18009c7b2  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18009c7b7  mov     r12, qword ptr [rbp+8A0h+var_888]
0x18009c7bb  movaps  xmm6, xmm0
0x18009c7be  lea     rcx, [r12+rbx]
0x18009c7c2  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18009c7c7  addss   xmm0, xmm7
0x18009c7cb  movaps  xmm1, xmm13
0x18009c7cf  divss   xmm1, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x18009c7d7  addss   xmm0, xmm6
0x18009c7db  movaps  xmm2, xmm13
0x18009c7df  mulss   xmm0, xmm1
0x18009c7e3  minss   xmm2, xmm0
0x18009c7e7  xorps   xmm0, xmm0
0x18009c7ea  maxss   xmm0, xmm2
0x18009c7ee  cvttss2si eax, xmm0
0x18009c7f2  mov     [rdi], ax
0x18009c7f5  inc     rsi
0x18009c7f8  mov     rax, r15
0x18009c7fb  add     rdi, 2
0x18009c7ff  add     r15, 4
0x18009c803  add     r14d, [rax]
0x18009c806  cmp     rsi, 1
0x18009c80a  jl      loc_18009C710
0x18009c810  mov     r13d, [rbp+8A0h+var_71C]
0x18009c817  dec     r14d
0x18009c81a  lea     edx, [r13-0Fh]
0x18009c81e  cmp     r14d, edx
0x18009c821  jge     loc_18009CC56
0x18009c827  mov     rcx, [rsp+9A0h+var_968]
0x18009c82c  sub     edx, r14d
0x18009c82f  movaps  xmm15, cs:__xmm@43aa800043aa800043aa800043aa8000
0x18009c837  xorps   xmm14, xmm14
0x18009c83b  movsxd  rax, r14d
0x18009c83e  lea     rcx, [rcx+rax*8]
0x18009c842  lea     eax, [rdx-1]
0x18009c845  add     rcx, 20h ; ' '
0x18009c849  shr     eax, 4
0x18009c84c  inc     eax
0x18009c84e  mov     r9d, eax
0x18009c851  shl     eax, 4
0x18009c854  add     r14d, eax
0x18009c857  nop     word ptr [rax+rax+00000000h]
0x18009c860  lea     rax, [rbp+8A0h+var_900]
0x18009c864  mov     edx, 2
0x18009c869  nop     dword ptr [rax+00000000h]
0x18009c870  movdqu  xmm0, xmmword ptr [rcx-20h]
0x18009c875  lea     rax, [rax+40h]
0x18009c879  movdqu  xmm1, xmmword ptr [rcx-10h]
0x18009c87e  movdqu  xmmword ptr [rax-60h], xmm0
0x18009c883  movdqu  xmm0, xmmword ptr [rcx]
0x18009c887  movdqu  xmmword ptr [rax-50h], xmm1
0x18009c88c  movdqu  xmm1, xmmword ptr [rcx+10h]
0x18009c891  add     rcx, 40h ; '@'
0x18009c895  movdqu  xmmword ptr [rax-40h], xmm0
0x18009c89a  movdqu  xmmword ptr [rax-30h], xmm1
0x18009c89f  sub     rdx, 1
0x18009c8a3  jnz     short loc_18009C870
0x18009c8a5  movdqa  xmm12, [rbp+8A0h+var_920]
0x18009c8ab  lea     rdx, [rbp+8A0h+var_820]
0x18009c8b2  movdqa  xmm10, [rbp+8A0h+var_910]
0x18009c8b8  lea     rax, [rbp+8A0h+var_7D0]
0x18009c8bf  movdqa  xmm8, [rbp+8A0h+var_900]
0x18009c8c5  movdqa  xmm11, xmm12
0x18009c8ca  punpcklwd xmm11, [rbp+8A0h+var_8E0]
0x18009c8d0  movdqa  xmm6, xmm10
0x18009c8d5  punpckhwd xmm12, [rbp+8A0h+var_8E0]
0x18009c8db  movdqa  xmm3, xmm8
0x18009c8e0  punpckhwd xmm8, [rbp+8A0h+var_8C0]
0x18009c8e6  movdqa  xmm7, xmm11
0x18009c8eb  movdqa  xmm5, [rbp+8A0h+var_8F0]
0x18009c8f0  movdqa  xmm9, xmm12
0x18009c8f5  punpcklwd xmm6, [rbp+8A0h+var_8D0]
0x18009c8fa  movdqa  xmm2, xmm5
0x18009c8fe  punpcklwd xmm3, [rbp+8A0h+var_8C0]
0x18009c903  movdqa  xmm0, xmm6
0x18009c907  punpckhwd xmm10, [rbp+8A0h+var_8D0]
0x18009c90d  mov     r8d, 2
0x18009c913  punpcklwd xmm2, [rbp+8A0h+var_8B0]
0x18009c918  movdqa  xmm1, xmm10
0x18009c91d  punpckhwd xmm5, [rbp+8A0h+var_8B0]
0x18009c922  punpcklwd xmm0, xmm2
0x18009c926  punpcklwd xmm9, xmm8
0x18009c92b  punpcklwd xmm7, xmm3
0x18009c92f  movdqa  xmm4, xmm7
0x18009c933  punpcklwd xmm1, xmm5
0x18009c937  punpckhwd xmm7, xmm0
0x18009c93b  punpcklwd xmm4, xmm0
0x18009c93f  movdqa  xmm0, xmm9
0x18009c944  punpckhwd xmm12, xmm8
0x18009c949  movdqa  xmm8, cs:__xmm@80008000800080008000800080008000
0x18009c952  punpckhwd xmm9, xmm1
0x18009c957  punpckhwd xmm11, xmm3
0x18009c95c  punpckhwd xmm6, xmm2
0x18009c960  punpckhwd xmm10, xmm5
0x18009c965  punpcklwd xmm0, xmm1
0x18009c969  punpcklwd xmm11, xmm6
0x18009c96e  punpcklwd xmm12, xmm10
0x18009c973  movaps  [rbp+8A0h+var_800], xmm9
0x18009c97b  movdqa  xmm9, cs:__xmm@7fff7fff7fff7fff7fff7fff7fff7fff
0x18009c984  movaps  [rbp+8A0h+var_830], xmm7
0x18009c988  movdqa  xmm7, cs:__xmm@00700070007000700070007000700070
0x18009c990  movaps  [rbp+8A0h+var_810], xmm0
  ... truncated ...
```
