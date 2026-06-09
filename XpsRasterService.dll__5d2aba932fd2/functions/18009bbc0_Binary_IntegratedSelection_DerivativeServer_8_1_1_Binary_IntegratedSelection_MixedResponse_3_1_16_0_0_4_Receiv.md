# Binary::IntegratedSelection::DerivativeServer<8,1,1,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<2,8,1,1,0,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0>,0>(void * const *,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int> const &)

- ea: `0x18009bbc0`
- end: `0x18009c434`
- name: `??$ReceiveUniqueLicense@V?$CreateDefinition@$01$07$00$00$0A@V?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@$0A@@IntegratedSelection@Binary@@$0A@@?$DerivativeServer@$07$00$00V?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@$0A@$03@IntegratedSelection@Binary@@IEAAXPEBQEAXAEBVImportantPreference@12@AEBV?$ShortTermResolution@H@Data@@@Z`
- size: `2164`
- prototype: `char __fastcall(__int64, unsigned __int8 **, int *, _OWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18009d5f0`

## callees

- `0x180003180`
- `0x1800588e0`
- `0x180067110`
- `0x1800963a0`
- `0x18009bbc0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall Binary::IntegratedSelection::DerivativeServer<8,1,1,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0,4>::ReceiveUniqueLicense<Binary::IntegratedSelection::CreateDefinition<2,8,1,1,0,Binary::IntegratedSelection::MixedResponse<3,1,16,0>,0>,0>(
        __int64 a1,
        unsigned __int8 **a2,
        int *a3,
        _OWORD *a4)
{
  __int64 v5; // rsi
  unsigned __int8 *v6; // rcx
  unsigned __int8 *v7; // rax
  unsigned __int8 *v8; // rdx
  int v9; // r14d
  unsigned __int8 *v10; // rbx
  int v11; // eax
  unsigned __int8 *v12; // r15
  int v13; // r11d
  int v14; // edi
  int v15; // r13d
  int v16; // ecx
  unsigned __int8 *v17; // r12
  int v18; // r10d
  __int64 v19; // r8
  int v20; // eax
  int v21; // r10d
  int v22; // r9d
  int v23; // eax
  __int64 v24; // rcx
  unsigned __int8 *v25; // r8
  int v26; // r14d
  __m128i *v27; // rsi
  unsigned __int8 *v28; // rcx
  __int64 v29; // r15
  unsigned __int8 *v30; // rbx
  __int64 v31; // rdi
  double v32; // xmm0_8
  float v33; // xmm7_4
  double v34; // xmm0_8
  float v35; // xmm6_4
  double v36; // xmm0_8
  int v37; // eax
  const __m128i *v38; // rcx
  __int64 v39; // r9
  __m128 *v40; // rax
  __int64 v41; // rdx
  __m128i v42; // xmm1
  __m128i v43; // xmm0
  __m128i v44; // xmm1
  __m128i si128; // xmm11
  __m128i *v46; // rdx
  __m128i v47; // xmm9
  __m128 *v48; // rax
  __m128i v49; // xmm12
  __m128i v50; // xmm5
  __m128i v51; // xmm11
  __m128i v52; // xmm3
  __m128i v53; // xmm7
  __m128i v54; // xmm4
  __m128i v55; // xmm3
  __m128i v56; // xmm2
  __int64 v57; // r10
  __m128i v58; // xmm9
  __m128i v59; // xmm4
  __m128i v60; // xmm0
  __m128i v61; // xmm6
  __m128i v62; // xmm1
  __m128i v63; // xmm5
  __m128i v64; // xmm10
  __m128i v65; // xmm8
  __m128i v66; // xmm10
  __m128i v67; // xmm2
  __m128i v68; // xmm12
  __m128i v69; // xmm0
  __m128i v70; // xmm6
  __m128i v71; // xmm11
  __m128i v72; // xmm7
  __m128i v73; // xmm1
  __m128i v74; // xmm10
  __m128i v75; // xmm6
  __m128i v76; // xmm11
  __m128i v77; // xmm8
  __m128i v78; // xmm3
  __m128i v79; // xmm4
  __m128i v80; // xmm0
  __m128i v81; // xmm3
  __m128i v82; // xmm2
  __m128i v83; // xmm1
  __m128i v84; // xmm0
  __m128i v85; // xmm4
  __m128i v86; // xmm4
  __m128i v87; // xmm3
  __m128i v88; // xmm0
  __m128i v89; // xmm4
  __m128i v90; // xmm3
  __m128i v91; // xmm1
  __m128i v92; // xmm2
  __m128i v93; // xmm1
  __m128i v94; // xmm0
  __m128i v95; // xmm4
  __m128i v96; // xmm4
  __m128i v97; // xmm3
  __m128i v98; // xmm0
  __m128i v99; // xmm4
  __m128i v100; // xmm3
  __m128i v101; // xmm2
  __m128 v102; // xmm1
  __m128 v103; // xmm0
  unsigned __int8 *v104; // rbx
  unsigned __int8 *v105; // rdi
  __int64 v106; // r12
  __int64 v107; // r14
  double v108; // xmm0_8
  float v109; // xmm7_4
  double v110; // xmm0_8
  float v111; // xmm6_4
  double v112; // xmm0_8
  __int64 v113; // rax
  int v115; // [rsp+30h] [rbp-D0h]
  unsigned __int8 *v116; // [rsp+38h] [rbp-C8h]
  unsigned __int8 *v119; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 *v120[2]; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v121[2]; // [rsp+70h] [rbp-90h]
  __int128 v122; // [rsp+78h] [rbp-88h]
  __int64 v123; // [rsp+88h] [rbp-78h]
  __m128 v124; // [rsp+A0h] [rbp-60h] BYREF
  __m128 v125; // [rsp+B0h] [rbp-50h] BYREF
  __m128 v126; // [rsp+C0h] [rbp-40h] BYREF
  __m128 v127; // [rsp+D0h] [rbp-30h] BYREF
  __m128i v128; // [rsp+E0h] [rbp-20h]
  __m128i v129; // [rsp+F0h] [rbp-10h]
  __m128i v130; // [rsp+100h] [rbp+0h]
  __m128i v131; // [rsp+110h] [rbp+10h]
  __m128 v132; // [rsp+120h] [rbp+20h]
  __m128 v133; // [rsp+130h] [rbp+30h]
  __m128 v134; // [rsp+140h] [rbp+40h]
  __m128 v135; // [rsp+150h] [rbp+50h]
  __m128i v136; // [rsp+160h] [rbp+60h]
  __m128i v137; // [rsp+170h] [rbp+70h]
  _OWORD v138[4]; // [rsp+180h] [rbp+80h] BYREF
  __int128 v139; // [rsp+1C0h] [rbp+C0h]
  int v140; // [rsp+1E0h] [rbp+E0h] BYREF
  int v141; // [rsp+1E4h] [rbp+E4h]
  __int64 v142; // [rsp+1E8h] [rbp+E8h]
  char v143[32]; // [rsp+1F0h] [rbp+F0h] BYREF
  int v144; // [rsp+210h] [rbp+110h]
  int v145; // [rsp+214h] [rbp+114h]
  int v146; // [rsp+218h] [rbp+118h]
  _DWORD v147[374]; // [rsp+21Ch] [rbp+11Ch]
  int v148; // [rsp+7F4h] [rbp+6F4h]
  int v149; // [rsp+7FCh] [rbp+6FCh]
  int v150; // [rsp+80Ch] [rbp+70Ch]

  *(_OWORD *)v120 = *a4;
  v5 = a1;
  Binary::IntegratedSelection::GeneralXPS::GeneralXPS((unsigned int)&v140, 1, 1, (_DWORD)a3, (__int64)v120, a1 + 8);
  v6 = a2[1];
  v7 = a2[2];
  v8 = a2[3];
  v9 = 0;
  if ( *a2 <= v6 )
    v6 = *a2;
  if ( v6 <= v7 )
    v7 = v6;
  if ( v7 <= v8 )
    v8 = v7;
  v10 = &v8[v142];
  *(_QWORD *)&v122 = &v8[v142];
  *((_QWORD *)&v122 + 1) = &v8[v142 + 2];
  v123 = (__int64)&v8[v142 + 4];
  LOBYTE(v11) = Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(
                  (Binary::IntegratedSelection::SmoothControl *)v143,
                  v8,
                  &v119,
                  v120);
  if ( (_BYTE)v11 )
  {
    v12 = 0;
    v120[0] = 0;
    v121[0] = 1;
    v115 = 0;
    if ( v140 > 0 )
    {
      v13 = v148;
      v14 = v144;
      v15 = v141;
      do
      {
        v144 = ++v14;
        if ( v14 == 1 )
        {
          v16 = *(_DWORD *)(v5 + 40);
          v17 = &v12[(_QWORD)v10];
          v18 = *(_DWORD *)(v5 + 28);
          v19 = *(int *)(v5 + 52);
          if ( v145 <= 0 )
            v9 = v145;
          v20 = *(_DWORD *)(v5 + 44);
          if ( v18 < v20 )
            v18 = *(_DWORD *)(v5 + 44);
          v21 = v18 - v20;
          v22 = v19 - 1;
          v23 = v146;
          v139 = v122;
          if ( v146 < v16 )
            v23 = v16;
          v24 = v19 * ((v23 - v16) % *(_DWORD *)(v5 + 48));
          if ( v21 <= v22 )
            v22 = v21;
          v25 = &v12[v123];
          v26 = -v9;
          v116 = &v12[v123];
          v27 = (__m128i *)(*(_QWORD *)(v5 + 56) + 2 * (v22 + v24));
          v28 = &v12[*((_QWORD *)&v139 + 1)];
          v29 = v150;
          v119 = v28;
          if ( v150 < 1LL )
          {
            v30 = v28;
            do
            {
              if ( v26 >= v15 )
                break;
              v31 = 8 * v26;
              v32 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v30[v31]);
              v33 = *(float *)&v32;
              v34 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v116[v31]);
              v35 = *(float *)&v34;
              v36 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v17[v31]);
              v27->m128i_i16[0] = (int)fmaxf(
                                         0.0,
                                         fminf(
                                           1023.0,
                                           (float)((float)(*(float *)&v36 + v33) + v35) * (float)(1023.0 / 3.0)));
              v27 = (__m128i *)((char *)v27 + 2);
              v37 = v121[v29++];
              v26 += v37;
            }
            while ( v29 < 1 );
            v13 = v148;
            v14 = v144;
            v15 = v141;
            v10 = (unsigned __int8 *)v122;
            v25 = v116;
          }
          if ( v26 < v15 - 15 )
          {
            v38 = (const __m128i *)&v17[8 * v26 + 32];
            v39 = ((unsigned int)(v15 - 15 - v26 - 1) >> 4) + 1;
            v26 += 16 * v39;
            do
            {
              v40 = &v126;
              v41 = 2;
              do
              {
                v40 += 4;
                v42 = _mm_loadu_si128(v38 - 1);
                v40[-6] = (__m128)_mm_loadu_si128(v38 - 2);
                v43 = _mm_loadu_si128(v38);
                v40[-5] = (__m128)v42;
                v44 = _mm_loadu_si128(v38 + 1);
                v38 += 4;
                v40[-4] = (__m128)v43;
                v40[-3] = (__m128)v44;
                --v41;
              }
              while ( v41 );
              si128 = _mm_load_si128((const __m128i *)&v124);
              v46 = (__m128i *)v138;
              v47 = _mm_load_si128((const __m128i *)&v125);
              v48 = &v125;
              v49 = _mm_unpacklo_epi16(si128, v128);
              v50 = _mm_unpacklo_epi16(v47, v129);
              v51 = _mm_unpackhi_epi16(si128, v128);
              v52 = _mm_load_si128((const __m128i *)&v126);
              v53 = _mm_unpackhi_epi16(v52, v130);
              v54 = _mm_load_si128((const __m128i *)&v127);
              v55 = _mm_unpacklo_epi16(v52, v130);
              v56 = _mm_unpacklo_epi16(v54, v131);
              v57 = 2;
              v58 = _mm_unpackhi_epi16(v47, v129);
              v59 = _mm_unpackhi_epi16(v54, v131);
              v60 = _mm_unpacklo_epi16(v50, v56);
              v61 = _mm_unpacklo_epi16(v51, v53);
              v62 = _mm_unpacklo_epi16(v58, v59);
              v63 = _mm_unpackhi_epi16(v50, v56);
              v64 = _mm_unpacklo_epi16(v49, v55);
              v65 = _mm_unpacklo_epi16(v64, v60);
              v66 = _mm_unpackhi_epi16(v64, v60);
              v67 = v65;
              v68 = _mm_unpacklo_epi16(_mm_unpackhi_epi16(v49, v55), v63);
              v69 = _mm_unpacklo_epi16(v61, v62);
              v70 = _mm_unpackhi_epi16(v61, v62);
              v71 = _mm_unpackhi_epi16(v51, v53);
              v72 = _mm_load_si128((const __m128i *)&_xmm);
              v73 = _mm_unpacklo_epi16(v66, v70);
              v74 = _mm_unpackhi_epi16(v66, v70);
              v75 = _mm_load_si128((const __m128i *)&_xmm);
              v76 = _mm_unpacklo_epi16(v71, _mm_unpackhi_epi16(v58, v59));
              v138[1] = _mm_unpackhi_epi16(v65, v69);
              v77 = _mm_load_si128((const __m128i *)&_xmm);
              v138[0] = _mm_unpacklo_epi16(v68, v76);
              v136 = _mm_unpacklo_epi16(v67, v69);
              v137 = v73;
              v138[2] = v74;
              v138[3] = _mm_unpackhi_epi16(v68, v76);
              do
              {
                v78 = _mm_andnot_si128(_mm_cmpeq_epi16(_mm_loadu_si128(v46 - 2), v77), v46[-2]);
                v79 = _mm_and_si128(v78, v72);
                v80 = _mm_srli_epi16(_mm_slli_epi16(v78, 1u), 0xBu);
                v81 = _mm_slli_epi16(v78, 6u);
                v82 = _mm_add_epi16(_mm_and_si128(_mm_cmpgt_epi16(v80, (__m128i)0LL), v75), v80);
                v83 = _mm_or_si128(
                        _mm_or_si128(
                          _mm_slli_epi32(_mm_unpacklo_epi16(v82, (__m128i)0LL), 0x17u),
                          _mm_slli_epi32(_mm_unpacklo_epi16(v81, (__m128i)0LL), 7u)),
                        _mm_unpacklo_epi16((__m128i)0LL, v79));
                v84 = _mm_unpackhi_epi16((__m128i)0LL, v79);
                v85 = _mm_loadu_si128(v46 - 1);
                v48[2] = (__m128)_mm_or_si128(
                                   _mm_or_si128(
                                     _mm_slli_epi32(_mm_unpackhi_epi16(v82, (__m128i)0LL), 0x17u),
                                     _mm_slli_epi32(_mm_unpackhi_epi16(v81, (__m128i)0LL), 7u)),
                                   v84);
                v86 = _mm_andnot_si128(_mm_cmpeq_epi16(v85, v77), v46[-1]);
                v48[-1] = (__m128)v83;
                v87 = v86;
                v88 = _mm_srli_epi16(_mm_slli_epi16(v86, 1u), 0xBu);
                v89 = _mm_and_si128(v86, v72);
                v90 = _mm_slli_epi16(v87, 6u);
                v91 = _mm_add_epi16(_mm_and_si128(_mm_cmpgt_epi16(v88, (__m128i)0LL), v75), v88);
                v92 = _mm_slli_epi32(_mm_unpackhi_epi16(v91, (__m128i)0LL), 0x17u);
                v93 = _mm_or_si128(
                        _mm_or_si128(
                          _mm_slli_epi32(_mm_unpacklo_epi16(v91, (__m128i)0LL), 0x17u),
                          _mm_slli_epi32(_mm_unpacklo_epi16(v90, (__m128i)0LL), 7u)),
                        _mm_unpacklo_epi16((__m128i)0LL, v89));
                v94 = _mm_unpackhi_epi16((__m128i)0LL, v89);
                v95 = _mm_loadu_si128(v46);
                v48[3] = (__m128)_mm_or_si128(
                                   _mm_or_si128(v92, _mm_slli_epi32(_mm_unpackhi_epi16(v90, (__m128i)0LL), 7u)),
                                   v94);
                v96 = _mm_andnot_si128(_mm_cmpeq_epi16(v95, v77), *v46);
                *v48 = (__m128)v93;
                v97 = v96;
                v98 = _mm_srli_epi16(_mm_slli_epi16(v96, 1u), 0xBu);
                v99 = _mm_and_si128(v96, v72);
                v100 = _mm_slli_epi16(v97, 6u);
                v101 = _mm_add_epi16(_mm_and_si128(_mm_cmpgt_epi16(v98, (__m128i)0LL), v75), v98);
                v48 += 6;
                v46 += 3;
                v48[-5] = (__m128)_mm_or_si128(
                                    _mm_or_si128(
                                      _mm_slli_epi32(_mm_unpacklo_epi16(v101, (__m128i)0LL), 0x17u),
                                      _mm_slli_epi32(_mm_unpacklo_epi16(v100, (__m128i)0LL), 7u)),
                                    _mm_unpacklo_epi16((__m128i)0LL, v99));
                v48[-2] = (__m128)_mm_or_si128(
                                    _mm_or_si128(
                                      _mm_slli_epi32(_mm_unpackhi_epi16(v101, (__m128i)0LL), 0x17u),
                                      _mm_slli_epi32(_mm_unpackhi_epi16(v100, (__m128i)0LL), 7u)),
                                    _mm_unpackhi_epi16((__m128i)0LL, v99));
                --v57;
              }
              while ( v57 );
              v102 = _mm_add_ps(v133, v134);
              v103 = _mm_add_ps((__m128)v130, (__m128)v131);
              *v27 = _mm_packs_epi32(
                       _mm_cvttps_epi32(
                         _mm_max_ps(
                           _mm_min_ps(_mm_mul_ps(_mm_add_ps(_mm_add_ps(v124, v125), v126), (__m128)_xmm), (__m128)_xmm),
                           (__m128)0LL)),
                       _mm_cvttps_epi32(
                         _mm_max_ps(
                           _mm_min_ps(
                             _mm_mul_ps(_mm_add_ps(_mm_add_ps(v127, (__m128)v128), (__m128)v129), (__m128)_xmm),
                             (__m128)_xmm),
                           (__m128)0LL)));
              v27[1] = _mm_packs_epi32(
                         _mm_cvttps_epi32(
                           _mm_max_ps(
                             _mm_min_ps(_mm_mul_ps(_mm_add_ps(v103, v132), (__m128)_xmm), (__m128)_xmm),
                             (__m128)0LL)),
                         _mm_cvttps_epi32(
                           _mm_max_ps(
                             _mm_min_ps(_mm_mul_ps(_mm_add_ps(v102, v135), (__m128)_xmm), (__m128)_xmm),
                             (__m128)0LL)));
              v27 += 2;
              --v39;
            }
            while ( v39 );
            v13 = v148;
            v14 = v144;
            v15 = v141;
          }
          if ( v26 < v15 )
          {
            v104 = (unsigned __int8 *)(v119 - v25);
            v105 = &v25[8 * v26];
            v106 = v17 - v25;
            v107 = (unsigned int)(v15 - v26);
            do
            {
              v108 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v105[(_QWORD)v104]);
              v109 = *(float *)&v108;
              v110 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(v105);
              v111 = *(float *)&v110;
              v112 = Binary::IntegratedSelection::FastDNS::Convert<unsigned short>(&v105[v106]);
              v105 += 8;
              v27->m128i_i16[0] = (int)fmaxf(
                                         0.0,
                                         fminf(
                                           1023.0,
                                           (float)((float)(*(float *)&v112 + v109) + v111) * (float)(1023.0 / 3.0)));
              v27 = (__m128i *)((char *)v27 + 2);
              --v107;
            }
            while ( v107 );
            v13 = v148;
            v14 = v144;
            v15 = v141;
            v10 = (unsigned __int8 *)v122;
          }
          v5 = a1;
          v9 = 0;
          v12 = v120[0];
          v113 = v13++;
          v14 -= v147[v113];
          if ( v13 >= v149 )
            v13 = 0;
          ++v146;
          v148 = v13;
        }
        v12 += *a3;
        v11 = v115 + 1;
        v120[0] = v12;
        v115 = v11;
      }
      while ( v11 < v140 );
    }
  }
  return v11;
}

```

## disassembly

```asm
0x18009bbc0  push    rbp
0x18009bbc2  push    rbx
0x18009bbc3  push    rsi
0x18009bbc4  push    r14
0x18009bbc6  lea     rbp, [rsp-7E8h]
0x18009bbce  sub     rsp, 8E8h
0x18009bbd5  mov     rax, cs:__security_cookie
0x18009bbdc  xor     rax, rsp
0x18009bbdf  mov     [rbp+800h+var_F0], rax
0x18009bbe6  movups  xmm0, xmmword ptr [r9]
0x18009bbea  lea     rax, [rcx+8]
0x18009bbee  mov     [rsp+900h+var_8B8], r8
0x18009bbf3  mov     [rsp+900h+var_8D8], rax
0x18009bbf8  mov     rbx, rdx
0x18009bbfb  mov     edx, 1
0x18009bc00  mov     [rsp+900h+var_8C0], rcx
0x18009bc05  lea     rax, [rsp+900h+var_8A0]
0x18009bc0a  movaps  xmmword ptr [rsp+900h+var_8A0], xmm0
0x18009bc0f  mov     rsi, rcx
0x18009bc12  mov     [rsp+900h+var_8E0], rax
0x18009bc17  mov     r9, r8
0x18009bc1a  lea     rcx, [rbp+800h+var_720]
0x18009bc21  mov     r8d, edx
0x18009bc24  call    ??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z; Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)
0x18009bc29  mov     rcx, [rbx+8]
0x18009bc2d  lea     r9, [rsp+900h+var_8A0]; unsigned __int8 **
0x18009bc32  mov     rax, [rbx+10h]
0x18009bc36  lea     r8, [rsp+900h+var_8B0]; unsigned __int8 **
0x18009bc3b  mov     rdx, [rbx+18h]
0x18009bc3f  xor     r14d, r14d
0x18009bc42  cmp     [rbx], rcx
0x18009bc45  cmovbe  rcx, [rbx]
0x18009bc49  mov     rbx, [rbp+800h+var_718]
0x18009bc50  cmp     rcx, rax
0x18009bc53  cmovbe  rax, rcx
0x18009bc57  lea     rcx, [rbp+800h+var_710]; this
0x18009bc5e  cmp     rax, rdx
0x18009bc61  cmovbe  rdx, rax; unsigned __int8 *
0x18009bc65  add     rbx, rdx
0x18009bc68  mov     qword ptr [rsp+900h+var_888], rbx
0x18009bc6d  lea     rax, [rbx+2]
0x18009bc71  mov     qword ptr [rbp+800h+var_888+8], rax
0x18009bc75  lea     rax, [rbx+4]
0x18009bc79  mov     [rbp+800h+var_878], rax
0x18009bc7d  call    ?BuildBooleanLicense@SmoothControl@IntegratedSelection@Binary@@QEAA_NPEAEAEAPEAE1@Z; Binary::IntegratedSelection::SmoothControl::BuildBooleanLicense(uchar *,uchar * &,uchar * &)
0x18009bc82  test    al, al
0x18009bc84  jz      loc_18009C418
0x18009bc8a  mov     [rsp+900h+var_38], r15
0x18009bc92  mov     r15d, r14d
0x18009bc95  mov     [rsp+900h+var_8A0], r14
0x18009bc9a  mov     [rsp+900h+var_890], 1
0x18009bca2  mov     [rsp+900h+var_8D0], r14d
0x18009bca7  cmp     [rbp+800h+var_720], r14d
0x18009bcae  jle     loc_18009C410
0x18009bcb4  mov     r11d, [rbp+800h+var_10C]
0x18009bcbb  mov     [rsp+900h+var_20], rdi
0x18009bcc3  mov     edi, [rbp+800h+var_6F0]
0x18009bcc9  mov     [rsp+900h+var_28], r12
0x18009bcd1  mov     [rsp+900h+var_30], r13
0x18009bcd9  mov     r13d, [rbp+800h+var_71C]
0x18009bce0  movaps  [rsp+900h+var_50], xmm6
0x18009bce8  movaps  [rsp+900h+var_60], xmm7
0x18009bcf0  movaps  [rsp+900h+var_70], xmm8
0x18009bcf9  movaps  [rsp+900h+var_80], xmm9
0x18009bd02  movaps  [rsp+900h+var_90], xmm10
0x18009bd0b  movaps  [rsp+900h+var_A0], xmm11
0x18009bd14  movaps  [rsp+900h+var_B0], xmm12
0x18009bd1d  movaps  [rsp+900h+var_C0], xmm13
0x18009bd26  movss   xmm13, cs:__real@447fc000
0x18009bd2f  movaps  [rsp+900h+var_D0], xmm14
0x18009bd38  movaps  [rsp+900h+var_E0], xmm15
0x18009bd41  inc     edi
0x18009bd43  mov     [rbp+800h+var_6F0], edi
0x18009bd49  cmp     edi, 1
0x18009bd4c  jnz     loc_18009C37A
0x18009bd52  mov     ecx, [rsi+28h]
0x18009bd55  lea     r12, [rbx+r15]
0x18009bd59  mov     eax, [rbp+800h+var_6EC]
0x18009bd5f  test    eax, eax
0x18009bd61  mov     r10d, [rsi+1Ch]
0x18009bd65  movsxd  r8, dword ptr [rsi+34h]
0x18009bd69  cmovle  r14d, eax
0x18009bd6d  mov     eax, [rsi+2Ch]
0x18009bd70  cmp     r10d, eax
0x18009bd73  movups  xmm0, [rsp+900h+var_888]
0x18009bd78  cmovl   r10d, eax
0x18009bd7c  sub     r10d, eax
0x18009bd7f  lea     r9d, [r8-1]
0x18009bd83  mov     eax, [rbp+800h+var_6E8]
0x18009bd89  cmp     eax, ecx
0x18009bd8b  movups  [rbp+800h+var_740], xmm0
0x18009bd92  cmovl   eax, ecx
0x18009bd95  sub     eax, ecx
0x18009bd97  cdq
0x18009bd98  idiv    dword ptr [rsi+30h]
0x18009bd9b  movsxd  rcx, edx
0x18009bd9e  imul    rcx, r8
0x18009bda2  mov     r8, [rbp+800h+var_878]
0x18009bda6  cmp     r10d, r9d
0x18009bda9  cmovle  r9d, r10d
0x18009bdad  add     r8, r15
0x18009bdb0  movsxd  rax, r9d
0x18009bdb3  neg     r14d
0x18009bdb6  add     rcx, rax
0x18009bdb9  mov     [rsp+900h+var_8C8], r8
0x18009bdbe  mov     rax, [rsi+38h]
0x18009bdc2  lea     rsi, [rax+rcx*2]
0x18009bdc6  mov     rcx, qword ptr [rbp+800h+var_740+8]
0x18009bdcd  add     rcx, r15
0x18009bdd0  movsxd  r15, [rbp+800h+var_F4]
0x18009bdd7  mov     [rsp+900h+var_8B0], rcx
0x18009bddc  cmp     r15, 1
0x18009bde0  jge     loc_18009BE86
0x18009bde6  mov     rbx, rcx
0x18009bde9  nop     dword ptr [rax+00000000h]
0x18009bdf0  cmp     r14d, r13d
0x18009bdf3  jge     short loc_18009BE68
0x18009bdf5  lea     eax, ds:0[r14*8]
0x18009bdfd  movsxd  rdi, eax
0x18009be00  lea     rcx, [rbx+rdi]
0x18009be04  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18009be09  mov     rcx, [rsp+900h+var_8C8]
0x18009be0e  movaps  xmm7, xmm0
0x18009be11  add     rcx, rdi
0x18009be14  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18009be19  lea     rcx, [rdi+r12]
0x18009be1d  movaps  xmm6, xmm0
0x18009be20  call    ??$Convert@G@FastDNS@IntegratedSelection@Binary@@SAMAEBG@Z; Binary::IntegratedSelection::FastDNS::Convert<ushort>(ushort const &)
0x18009be25  addss   xmm0, xmm7
0x18009be29  movaps  xmm1, xmm13
0x18009be2d  divss   xmm1, cs:?ImmediateMessage@?$MixedResponse@$02$00$0BA@$0A@@IntegratedSelection@Binary@@2MB; float const Binary::IntegratedSelection::MixedResponse<3,1,16,0>::ImmediateMessage
0x18009be35  addss   xmm0, xmm6
0x18009be39  movaps  xmm2, xmm13
0x18009be3d  mulss   xmm0, xmm1
0x18009be41  minss   xmm2, xmm0
0x18009be45  xorps   xmm0, xmm0
0x18009be48  maxss   xmm0, xmm2
0x18009be4c  cvttss2si eax, xmm0
0x18009be50  mov     [rsi], ax
0x18009be53  add     rsi, 2
0x18009be57  mov     eax, [rsp+r15*4+900h+var_890]
0x18009be5c  inc     r15
0x18009be5f  add     r14d, eax
0x18009be62  cmp     r15, 1
0x18009be66  jl      short loc_18009BDF0
0x18009be68  mov     r11d, [rbp+800h+var_10C]
0x18009be6f  mov     edi, [rbp+800h+var_6F0]
0x18009be75  mov     r13d, [rbp+800h+var_71C]
0x18009be7c  mov     rbx, qword ptr [rsp+900h+var_888]
0x18009be81  mov     r8, [rsp+900h+var_8C8]
0x18009be86  lea     edx, [r13-0Fh]
0x18009be8a  cmp     r14d, edx
0x18009be8d  jge     loc_18009C2A5
0x18009be93  movaps  xmm14, cs:__xmm@43aa800043aa800043aa800043aa8000
0x18009be9b  sub     edx, r14d
0x18009be9e  movsxd  rcx, r14d
0x18009bea1  xorps   xmm15, xmm15
0x18009bea5  add     rcx, 4
0x18009bea9  lea     eax, [rdx-1]
0x18009beac  shr     eax, 4
0x18009beaf  inc     eax
0x18009beb1  lea     rcx, [r12+rcx*8]
0x18009beb5  mov     r9d, eax
0x18009beb8  shl     eax, 4
0x18009bebb  add     r14d, eax
0x18009bebe  xchg    ax, ax
0x18009bec0  lea     rax, [rbp+800h+var_840]
0x18009bec4  mov     edx, 2
0x18009bec9  nop     dword ptr [rax+00000000h]
0x18009bed0  movdqu  xmm0, xmmword ptr [rcx-20h]
0x18009bed5  lea     rax, [rax+40h]
0x18009bed9  movdqu  xmm1, xmmword ptr [rcx-10h]
0x18009bede  movdqu  xmmword ptr [rax-60h], xmm0
0x18009bee3  movdqu  xmm0, xmmword ptr [rcx]
0x18009bee7  movdqu  xmmword ptr [rax-50h], xmm1
0x18009beec  movdqu  xmm1, xmmword ptr [rcx+10h]
0x18009bef1  add     rcx, 40h ; '@'
0x18009bef5  movdqu  xmmword ptr [rax-40h], xmm0
0x18009befa  movdqu  xmmword ptr [rax-30h], xmm1
0x18009beff  sub     rdx, 1
0x18009bf03  jnz     short loc_18009BED0
0x18009bf05  movdqa  xmm11, [rbp+800h+var_860]
0x18009bf0b  lea     rdx, [rbp+800h+var_780]
0x18009bf12  movdqa  xmm9, [rbp+800h+var_850]
0x18009bf18  lea     rax, [rbp+800h+var_850]
0x18009bf1c  movdqa  xmm7, [rbp+800h+var_840]
0x18009bf21  movdqa  xmm12, xmm11
0x18009bf26  punpcklwd xmm12, [rbp+800h+var_820]
0x18009bf2c  movdqa  xmm5, xmm9
0x18009bf31  punpcklwd xmm5, [rbp+800h+var_810]
0x18009bf36  movdqa  xmm10, xmm12
0x18009bf3b  punpckhwd xmm11, [rbp+800h+var_820]
0x18009bf41  movdqa  xmm3, xmm7
0x18009bf45  punpckhwd xmm7, [rbp+800h+var_800]
0x18009bf4a  movdqa  xmm0, xmm5
0x18009bf4e  movdqa  xmm4, [rbp+800h+var_830]
0x18009bf53  movdqa  xmm6, xmm11
0x18009bf58  punpcklwd xmm3, [rbp+800h+var_800]
0x18009bf5d  movdqa  xmm2, xmm4
0x18009bf61  punpcklwd xmm2, [rbp+800h+var_7F0]
0x18009bf66  mov     r10d, 2
0x18009bf6c  punpckhwd xmm9, [rbp+800h+var_810]
0x18009bf72  punpckhwd xmm4, [rbp+800h+var_7F0]
0x18009bf77  movdqa  xmm1, xmm9
0x18009bf7c  punpcklwd xmm0, xmm2
0x18009bf80  punpcklwd xmm6, xmm7
0x18009bf84  punpcklwd xmm1, xmm4
0x18009bf88  punpckhwd xmm5, xmm2
0x18009bf8c  punpcklwd xmm10, xmm3
0x18009bf91  movdqa  xmm8, xmm10
0x18009bf96  punpckhwd xmm12, xmm3
0x18009bf9b  punpcklwd xmm8, xmm0
0x18009bfa0  punpckhwd xmm10, xmm0
0x18009bfa5  movdqa  xmm2, xmm8
0x18009bfaa  movdqa  xmm0, xmm6
0x18009bfae  punpcklwd xmm12, xmm5
0x18009bfb3  punpcklwd xmm0, xmm1
0x18009bfb7  xorps   xmm5, xmm5
0x18009bfba  punpckhwd xmm8, xmm0
0x18009bfbf  punpckhwd xmm6, xmm1
0x18009bfc3  movdqa  xmm1, xmm10
0x18009bfc8  punpcklwd xmm2, xmm0
0x18009bfcc  movdqa  xmm0, xmm12
0x18009bfd1  punpckhwd xmm11, xmm7
0x18009bfd6  movdqa  xmm7, cs:__xmm@80008000800080008000800080008000
0x18009bfde  punpcklwd xmm1, xmm6
0x18009bfe2  punpckhwd xmm10, xmm6
0x18009bfe7  movdqa  xmm6, cs:__xmm@00700070007000700070007000700070
0x18009bfef  punpckhwd xmm9, xmm4
0x18009bff4  punpcklwd xmm11, xmm9
0x18009bff9  punpcklwd xmm0, xmm11
0x18009bffe  punpckhwd xmm12, xmm11
0x18009c003  movaps  [rbp+800h+var_770], xmm8
0x18009c00b  movdqa  xmm8, cs:__xmm@7fff7fff7fff7fff7fff7fff7fff7fff
0x18009c014  movaps  [rbp+800h+var_780], xmm0
0x18009c01b  movaps  [rbp+800h+var_7A0], xmm2
0x18009c01f  movaps  [rbp+800h+var_790], xmm1
0x18009c023  movaps  [rbp+800h+var_760], xmm10
0x18009c02b  movaps  [rbp+800h+var_750], xmm12
0x18009c033  nop     dword ptr [rax+00h]
0x18009c037  nop     word ptr [rax+rax+00000000h]
0x18009c040  movdqu  xmm4, xmmword ptr [rdx-20h]
0x18009c045  pcmpeqw xmm4, xmm8
0x18009c04a  pandn   xmm4, xmmword ptr [rdx-20h]
0x18009c04f  movdqa  xmm0, xmm4
0x18009c053  movdqa  xmm3, xmm4
0x18009c057  psllw   xmm0, 1
0x18009c05c  pand    xmm4, xmm7
0x18009c060  psrlw   xmm0, 0Bh
0x18009c065  movdqa  xmm2, xmm0
0x18009c069  psllw   xmm3, 6
0x18009c06e  pcmpgtw xmm2, xmm5
0x18009c072  pand    xmm2, xmm6
0x18009c076  paddw   xmm2, xmm0
0x18009c07a  movdqa  xmm0, xmm3
0x18009c07e  punpcklwd xmm0, xmm5
0x18009c082  movdqa  xmm1, xmm2
0x18009c086  pslld   xmm0, 7
0x18009c08b  punpckhwd xmm2, xmm5
0x18009c08f  pslld   xmm2, 17h
0x18009c094  punpcklwd xmm1, xmm5
0x18009c098  pslld   xmm1, 17h
0x18009c09d  por     xmm1, xmm0
0x18009c0a1  punpckhwd xmm3, xmm5
0x18009c0a5  pslld   xmm3, 7
0x18009c0aa  movdqa  xmm0, xmm5
0x18009c0ae  punpcklwd xmm0, xmm4
0x18009c0b2  por     xmm2, xmm3
0x18009c0b6  por     xmm1, xmm0
0x18009c0ba  movdqa  xmm0, xmm5
0x18009c0be  punpckhwd xmm0, xmm4
0x18009c0c2  movdqu  xmm4, xmmword ptr [rdx-10h]
0x18009c0c7  por     xmm2, xmm0
0x18009c0cb  movdqu  xmmword ptr [rax+20h], xmm2
0x18009c0d0  pcmpeqw xmm4, xmm8
0x18009c0d5  pandn   xmm4, xmmword ptr [rdx-10h]
0x18009c0da  movdqu  xmmword ptr [rax-10h], xmm1
0x18009c0df  movdqa  xmm0, xmm4
0x18009c0e3  psllw   xmm0, 1
0x18009c0e8  movdqa  xmm3, xmm4
0x18009c0ec  psrlw   xmm0, 0Bh
0x18009c0f1  pand    xmm4, xmm7
0x18009c0f5  movdqa  xmm2, xmm0
0x18009c0f9  psllw   xmm3, 6
0x18009c0fe  pcmpgtw xmm2, xmm5
0x18009c102  pand    xmm2, xmm6
0x18009c106  paddw   xmm2, xmm0
0x18009c10a  movdqa  xmm0, xmm3
0x18009c10e  movdqa  xmm1, xmm2
0x18009c112  punpcklwd xmm0, xmm5
0x18009c116  pslld   xmm0, 7
0x18009c11b  punpckhwd xmm2, xmm5
0x18009c11f  pslld   xmm2, 17h
0x18009c124  punpcklwd xmm1, xmm5
0x18009c128  pslld   xmm1, 17h
0x18009c12d  por     xmm1, xmm0
0x18009c131  punpckhwd xmm3, xmm5
0x18009c135  pslld   xmm3, 7
0x18009c13a  movdqa  xmm0, xmm5
0x18009c13e  punpcklwd xmm0, xmm4
  ... truncated ...
```
