# AResampler<float,float,1>::createFilter(int,float,double)

- ea: `0x18007d000`
- end: `0x18007dce7`
- name: `?createFilter@?$AResampler@MM$00@@IEAAJHMN@Z`
- size: `3303`
- prototype: `__int64 __fastcall(__int64, int, float, double)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18007dde0`
- `0x18007f280`

## callees

- `0x18000b718`
- `0x18000b73c`
- `0x18006d510`
- `0x180072830`
- `0x18007d000`
- `0x18007ef50`
- `0x180085010`

## pseudocode

```c
__int64 __fastcall AResampler<float,float,1>::createFilter(__int64 a1, int a2, float a3, double a4)
{
  float v6; // xmm7_4
  __int64 result; // rax
  double v9; // xmm8_8
  float v10; // xmm0_4
  float v11; // xmm0_4
  float v12; // xmm7_4
  float v13; // xmm6_4
  float v14; // xmm1_4
  int v15; // ecx
  double v16; // xmm2_8
  double v17; // xmm3_8
  double v18; // xmm1_8
  double v19; // xmm3_8
  double v20; // xmm0_8
  float v21; // xmm5_4
  __m128 v22; // xmm2
  __m128d v23; // xmm1
  float *v24; // rax
  double v25; // xmm0_8
  __m128d v26; // xmm0
  int v27; // r10d
  bool v28; // al
  int v29; // r9d
  int v30; // esi
  bool v31; // r8
  int v32; // eax
  __int64 v33; // rcx
  __int64 *v34; // r12
  __int64 *v35; // rcx
  double v36; // xmm1_8
  double v37; // xmm0_8
  __int64 (__fastcall ***v38)(_QWORD, __int64, __int64, __int64); // rcx
  double v39; // xmm6_8
  int v40; // r13d
  unsigned int v41; // ebp
  int v42; // eax
  unsigned int v43; // edi
  __int64 v44; // rdi
  int v45; // eax
  int v46; // r8d
  double v47; // xmm7_8
  unsigned int v48; // r13d
  int v49; // r14d
  double v50; // xmm6_8
  int v51; // edx
  double v52; // xmm7_8
  int v53; // r15d
  int v54; // ebp
  int v55; // esi
  __int64 v56; // rcx
  int v57; // eax
  double v58; // xmm0_8
  int v59; // ebp
  int v60; // r10d
  int v61; // r14d
  int v62; // r11d
  int v63; // r9d
  int v64; // eax
  int v65; // edx
  __m128 v66; // xmm2
  float v67; // xmm1_4
  int v68; // ecx
  __m128 v69; // xmm1
  __m128 v70; // xmm3
  __int64 v71; // rax
  __m128 v72; // xmm3
  __m128 v73; // xmm1
  __int64 v74; // rax
  __int64 v75; // rax
  __m128 v76; // xmm1
  __m128 v77; // xmm2
  int v78; // ecx
  __int64 v79; // rax
  __int64 v80; // rax
  __int64 v81; // rax
  double v82; // xmm0_8
  float (__fastcall *v83)(_QWORD, __int64); // r14
  int v84; // eax
  unsigned int v85; // edi
  _DWORD *v86; // rax
  unsigned int v87; // r12d
  float *v88; // rbp
  unsigned int *v89; // r15
  int v90; // esi
  __int64 v91; // rdi
  float v92; // xmm0_4
  int v93; // [rsp+20h] [rbp-A8h]
  int v94; // [rsp+20h] [rbp-A8h]
  int v95; // [rsp+30h] [rbp-98h]
  int v96; // [rsp+34h] [rbp-94h]
  float v97; // [rsp+38h] [rbp-90h] BYREF
  int v98; // [rsp+3Ch] [rbp-8Ch]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  char v100; // [rsp+D0h] [rbp+8h]

  v6 = a3;
  if ( !*(_BYTE *)(a1 + 328) )
  {
    result = 0;
    *(_BYTE *)(a1 + 416) = 1;
    *(_QWORD *)(a1 + 368) = 0;
    *(_QWORD *)(a1 + 384) = 0;
    *(_DWORD *)(a1 + 464) = 0;
    *(_QWORD *)(a1 + 512) = 0x3FF0000000000000LL;
    *(_DWORD *)(a1 + 332) = 0;
    *(_DWORD *)(a1 + 336) = 2147383646;
    return result;
  }
  v9 = *(double *)(a1 + 368);
  if ( a3 == 0.0 )
  {
    if ( a2 < 100 )
    {
      if ( a2 > 2 )
      {
        v11 = o_logf_0();
        v10 = v11 * 0.06730802 - v11 * 0.005794964 * v11 + 0.804445578;
      }
      else
      {
        v10 = FLOAT_0_84829998;
      }
    }
    else
    {
      v10 = FLOAT_0_99000001;
    }
    v12 = *(float *)(a1 + 300) / *(float *)(a1 + 304);
    if ( v12 >= 1.0 )
      v12 = FLOAT_1_0;
    v6 = v12 * v10;
  }
  if ( a2 >= 30 )
  {
    v13 = FLOAT_100_0;
LABEL_15:
    v14 = (v13 - 8.699999999999999) * 0.1102;
    goto LABEL_18;
  }
  v13 = (float)((float)((float)((float)(30.0 - (float)a2) * 0.050270006) + 1.5081002) * (float)(2 * a2 + 1)) + 8.0;
  if ( v13 > 50.0 )
    goto LABEL_15;
  v14 = 0.0;
  if ( v13 >= 21.0 )
    v14 = powf(v13 - 21.0, 0.40000001) * 0.5842000000000001 + (float)(v13 - 21.0) * 0.07886;
LABEL_18:
  *(float *)(a1 + 568) = v14;
  v15 = 1;
  v16 = DOUBLE_1_0;
  v17 = v14 * 0.25 * v14;
  v18 = v17;
  do
  {
    ++v15;
    v16 = v16 + v18;
    v18 = v18 * (v17 * *(double *)&`Besseli0'::`2'::s_dblOneOverISqr[v15]);
  }
  while ( v18 >= 0.00000001 && v15 < 22 );
  v19 = (double)a2;
  *(double *)(a1 + 576) = 1.0 / v16;
  v20 = DOUBLE_1_0;
  *(double *)(a1 + 368) = (double)a2;
  if ( (double)a2 != 0.0 )
    v20 = 1.0 / v19;
  *(double *)(a1 + 376) = v20;
  v21 = *(float *)(a1 + 304);
  v22 = (__m128)*(unsigned int *)(a1 + 300);
  if ( v22.m128_f32[0] > v21 )
  {
    v23 = _mm_cvtps_pd(v22);
    v23.m128d_f64[0] = v23.m128d_f64[0] / v21 * v19;
  }
  else
  {
    v23 = (__m128d)COERCE_UNSIGNED_INT64((double)a2);
  }
  *(double *)(a1 + 384) = v23.m128d_f64[0];
  if ( v6 == 0.0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x81C,
      (unsigned int)"avcore\\codecdsp\\audio\\resample\\aresample.cpp",
      (const char *)0x80004001LL,
      v93);
    return 2147500033LL;
  }
  v24 = &v97;
  v97 = v22.m128_f32[0] / v6;
  if ( (float)(v22.m128_f32[0] / v6) <= v21 )
    v24 = (float *)(a1 + 304);
  if ( v21 >= v22.m128_f32[0] )
    v22.m128_f32[0] = v21;
  v25 = (float)(v22.m128_f32[0] / *v24);
  v23.m128d_f64[0] = v23.m128d_f64[0] / v25;
  *(double *)(a1 + 512) = v25;
  v26.m128d_f64[1] = v23.m128d_f64[1];
  *(double *)(a1 + 384) = v23.m128d_f64[0];
  v26.m128d_f64[0] = v23.m128d_f64[0] + v23.m128d_f64[0] + 1.0;
  if ( (double)(int)v26.m128d_f64[0] != v26.m128d_f64[0] )
    v26.m128d_f64[0] = (double)(!(_mm_movemask_pd(_mm_unpacklo_pd(v26, v26)) & 1) + (int)v26.m128d_f64[0]);
  *(_DWORD *)(a1 + 332) = (int)v26.m128d_f64[0] + 5;
  if ( (double)(int)v23.m128d_f64[0] != v23.m128d_f64[0] )
    v23.m128d_f64[0] = (double)(!(_mm_movemask_pd(_mm_unpacklo_pd(v23, v23)) & 1) + (int)v23.m128d_f64[0]);
  v27 = *(_DWORD *)(a1 + 324);
  *(_DWORD *)(a1 + 464) = (int)v23.m128d_f64[0];
  v28 = v27 * ((int)v23.m128d_f64[0] + 1) < 100000;
  *(_BYTE *)(a1 + 416) = v28;
  v29 = *(_DWORD *)(a1 + 320);
  v30 = v29;
  if ( v27 >= v29 )
    v30 = v27;
  if ( v30 <= 1280 )
  {
    v31 = v27 * ((int)v23.m128d_f64[0] + 1) < 100000;
  }
  else
  {
    v28 = 0;
    *(_BYTE *)(a1 + 416) = 0;
    v31 = 0;
  }
  if ( *(_BYTE *)(a1 + 308) )
  {
    *(_BYTE *)(a1 + 416) = 0;
    v31 = 0;
  }
  else if ( v28 )
  {
    v33 = 320;
    if ( v27 >= v29 )
      v33 = 324;
    v32 = 2137483647 / *(_DWORD *)(v33 + a1) - 1;
    goto LABEL_44;
  }
  v32 = 2147383646;
LABEL_44:
  *(_DWORD *)(a1 + 336) = v32;
  if ( !v31 )
  {
LABEL_52:
    if ( *(_BYTE *)(a1 + 468) )
    {
      if ( v19 == v9 )
        return 0;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x87B,
        (unsigned int)"avcore\\codecdsp\\audio\\resample\\aresample.cpp",
        (const char *)0x80004001LL,
        v93);
      return 2147500033LL;
    }
    else
    {
      v82 = 1073741824.0 / (v19 + 5.0);
      *(double *)(a1 + 352) = v82;
      *(double *)(a1 + 360) = 1.0 / v82;
      std::shared_ptr<IAudioSignalProcessingBuffer>::reset(a1 + 392);
      v83 = *(float (__fastcall **)(_QWORD, __int64))(a1 + 560);
      v84 = (***(__int64 (__fastcall ****)(_QWORD, __int64, __int64, __int64))a1)(*(_QWORD *)a1, 11, 131096, 1);
      v85 = v84;
      if ( v84 >= 0 )
      {
        v86 = (_DWORD *)(***(__int64 (__fastcall ****)(_QWORD))(a1 + 392))(*(_QWORD *)(a1 + 392));
        *(_QWORD *)(a1 + 408) = v86;
        v87 = 0;
        *v86 = 16385;
        *(_DWORD *)(*(_QWORD *)(a1 + 408) + 8LL) = 16;
        *(_DWORD *)(*(_QWORD *)(a1 + 408) + 4LL) = 1073676288;
        *(_DWORD *)(*(_QWORD *)(a1 + 408) + 12LL) = 0xFFFF;
        v88 = *(float **)(a1 + 408);
        v89 = (unsigned int *)&v88[*(unsigned int *)v88];
        v90 = 0;
        v88[4] = v83(0, a1);
        v91 = 0;
        do
        {
          v87 += 0x10000;
          v92 = v83(v87, a1);
          v88[v91 + 5] = v92;
          ++v90;
          *(float *)&v89[v91 + 4] = (float)(v92 - v88[v91 + 4]) * 0.000015258789;
          ++v91;
        }
        while ( v90 < 0x4000 );
        *(float *)&v89[v90 + 4] = (float)(v83(v87 + 0x10000, a1) - v88[v90 + 4]) * 0.000015258789;
        prvRsFnScaleTableSum2<float>(*(_QWORD *)(a1 + 408));
        *(_BYTE *)(a1 + 468) = 1;
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x49,
        (unsigned int)"avcore\\codecdsp\\audio\\resample\\rsfntableimpl.h",
        (const char *)(unsigned int)v84,
        a1 + 392);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8F6,
        (unsigned int)"avcore\\codecdsp\\audio\\resample\\aresample.cpp",
        (const char *)v85,
        v94);
      return v85;
    }
  }
  if ( *(_BYTE *)(a1 + 469) )
  {
    if ( v27 == *(_DWORD *)(a1 + 472)
      && v29 == *(_DWORD *)(a1 + 476)
      && a4 == *(double *)(a1 + 480)
      && *(double *)(a1 + 488) == *(double *)(a1 + 512)
      && *(_DWORD *)(a1 + 464) == *(_DWORD *)(a1 + 496) )
    {
      return 0;
    }
    *(_BYTE *)(a1 + 416) = 0;
    goto LABEL_52;
  }
  v34 = 0;
  v95 = 0;
  v100 = 0;
  if ( a4 == 0.0 && 1.0 == *(double *)(a1 + 512) )
  {
    v35 = (__int64 *)AResampler<float,float,1>::m_predesignFil;
    v36 = (double)v30;
    v37 = (double)(2 * a2 * v30 + 1);
    if ( (double)v30 == *(double *)&(*AResampler<float,float,1>::m_predesignFil)[0]
      && v37 == *(double *)&(*AResampler<float,float,1>::m_predesignFil)[1] )
    {
      goto LABEL_79;
    }
    v35 = AResampler<float,float,1>::m_fil_2_2;
    if ( v36 == 2.0 && v37 == *(double *)&AResampler<float,float,1>::m_fil_2_2[1] )
      goto LABEL_79;
    v35 = AResampler<float,float,1>::m_fil_2_3;
    if ( v36 == 2.0 && v37 == *(double *)&AResampler<float,float,1>::m_fil_2_3[1] )
      goto LABEL_79;
    v35 = AResampler<float,float,1>::m_fil_3_1;
    if ( v36 == 3.0 && v37 == *(double *)&AResampler<float,float,1>::m_fil_3_1[1] )
      goto LABEL_79;
    if ( (v35 = AResampler<float,float,1>::m_fil_3_2, v36 == 3.0)
      && v37 == *(double *)&AResampler<float,float,1>::m_fil_3_2[1]
      || (v35 = AResampler<float,float,1>::m_fil_3_3, v36 == 3.0)
      && v37 == *(double *)&AResampler<float,float,1>::m_fil_3_3[1]
      || (v35 = AResampler<float,float,1>::m_fil_4_1, v36 == 4.0)
      && v37 == *(double *)&AResampler<float,float,1>::m_fil_4_1[1]
      || (v35 = AResampler<float,float,1>::m_fil_4_2, v36 == 4.0)
      && v37 == *(double *)&AResampler<float,float,1>::m_fil_4_2[1]
      || (v35 = AResampler<float,float,1>::m_fil_4_3, v100 = 0, v95 = 0, v36 == 4.0)
      && v37 == *(double *)&AResampler<float,float,1>::m_fil_4_3[1] )
    {
LABEL_79:
      v100 = 1;
      v34 = v35 + 2;
      v95 = a2 * v30;
    }
  }
  v38 = *(__int64 (__fastcall ****)(_QWORD, __int64, __int64, __int64))a1;
  v39 = *(double *)(a1 + 512);
  v40 = 2 * *(_DWORD *)(a1 + 464);
  v41 = ((((v40 + 4) >> 31) & 3) + v40 + 4) & 0xFFFFFFFC;
  *(_DWORD *)(a1 + 456) = v41;
  *(_DWORD *)(a1 + 460) = v27 * v41;
  v42 = (**v38)(v38, 12, 4LL * (int)(v27 * v41), 16);
  v43 = v42;
  if ( v42 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8AA,
      (unsigned int)"avcore\\codecdsp\\audio\\resample\\aresample.cpp",
      (const char *)(unsigned int)v42,
      a1 + 432);
    return v43;
  }
  v44 = (***(__int64 (__fastcall ****)(_QWORD))(a1 + 432))(*(_QWORD *)(a1 + 432));
  *(_QWORD *)(a1 + 448) = v44;
  *(_QWORD *)(a1 + 424) = v44;
  v45 = *(_DWORD *)(a1 + 324);
  if ( v45 <= 0 )
    goto LABEL_116;
  v46 = *(_DWORD *)(a1 + 464);
  v47 = v39;
  v48 = v41 + ~v40;
  v49 = 0;
  v50 = v39 * a4;
  v51 = v45 * (v46 + 1);
  v52 = v47 / (double)v30;
  v96 = v51;
  do
  {
    v53 = v49 + 1;
    v98 = v49 + 1;
    v54 = -v46;
    v55 = *(_DWORD *)(a1 + 456) * (v49 + 1) - 1;
    if ( -v46 > (int)(v46 + v48) )
      goto LABEL_98;
    do
    {
      v56 = (unsigned int)(v49 + *(_DWORD *)(a1 + 324) * v54);
      if ( v100 )
      {
        v57 = -(int)v56;
        if ( (int)v56 > 0 )
          v57 = v49 + *(_DWORD *)(a1 + 324) * v54;
        if ( v57 > v95 )
          LODWORD(v58) = 0;
        else
          *(float *)&v58 = *(double *)&v34[v57];
        goto LABEL_95;
      }
      if ( (int)v56 >= 0 || (int)v56 < 1 - v51 || a4 != 0.0 )
      {
        v58 = (double)(int)v56 * v52 + v50;
        (*(void (__fastcall **)(__int64, __int64))(a1 + 552))(v56, a1);
        v51 = v96;
LABEL_95:
        *(_DWORD *)(v44 + 4LL * v55) = LODWORD(v58);
      }
      v46 = *(_DWORD *)(a1 + 464);
      ++v54;
      --v55;
    }
    while ( v54 <= (int)(v46 + v48) );
    v53 = v98;
LABEL_98:
    v45 = *(_DWORD *)(a1 + 324);
    v49 = v53;
  }
  while ( v53 < v45 );
  if ( v45 > 0 )
  {
    v59 = 0;
    do
    {
      v60 = -v46;
      v61 = v59 + 1;
      v98 = v59 + 1;
      if ( -v46 <= (int)(v46 + v48) )
      {
        v62 = *(_DWORD *)(a1 + 456) * (v59 + 1) - 1;
        do
        {
          v63 = v59 + v60 * *(_DWORD *)(a1 + 324);
          if ( v100 )
          {
            v64 = -v63;
            if ( v63 > 0 )
              v64 = v59 + v60 * *(_DWORD *)(a1 + 324);
            if ( v64 > v95 )
              *(_DWORD *)(v44 + 4LL * v62) = 0;
            else
              *(float *)(v44 + 4LL * v62) = *(double *)&v34[v64];
          }
          else if ( v63 < 0 && v63 >= 1 - v51 && a4 == 0.0 )
          {
            *(_DWORD *)(v44 + 4LL * v62) = *(_DWORD *)(v44
                                                     + 4LL
                                                     * (*(_DWORD *)(a1 + 456)
                                                      * (1 - *(_DWORD *)(a1 + 324) * -(v63 / *(_DWORD *)(a1 + 324)) - v63)
                                                      - v46
                                                      + v63 / *(_DWORD *)(a1 + 324))
                                                     - 4);
          }
          v46 = *(_DWORD *)(a1 + 464);
          ++v60;
          v51 = v96;
          --v62;
        }
        while ( v60 <= (int)(v46 + v48) );
        v61 = v98;
      }
      v45 = *(_DWORD *)(a1 + 324);
      v59 = v61;
      v51 = v96;
    }
    while ( v61 < v45 );
  }
LABEL_116:
  v65 = *(_DWORD *)(a1 + 460);
  v66 = (__m128)COERCE_UNSIGNED_INT((float)v45);
  if ( v65 > 0 )
  {
    v67 = 0.0;
    v68 = 0;
    if ( (unsigned int)v65 < 8 )
      goto LABEL_123;
    v69 = 0;
    v70 = 0;
    do
    {
      v71 = v68;
      v68 += 8;
      v69 = _mm_add_ps(v69, *(__m128 *)(v44 + 4 * v71));
      v70 = _mm_add_ps(v70, *(__m128 *)(v44 + 4 * v71 + 16));
    }
    while ( v68 < *(_DWORD *)(a1 + 460) - (*(_DWORD *)(a1 + 460) & 7) );
    v72 = _mm_add_ps(v70, v69);
    v73 = _mm_add_ps(_mm_movehl_ps(v72, v72), v72);
    v67 = v73.m128_f32[0] + _mm_shuffle_ps(v73, v73, 245).m128_f32[0];
    if ( v68 < v65 )
    {
LABEL_123:
      if ( v65 - v68 < 4 )
        goto LABEL_144;
      do
      {
        v74 = v68;
        v68 += 4;
        v67 = (float)((float)((float)(v67 + *(float *)(v44 + 4 * v74)) + *(float *)(v44 + 4 * v74 + 4))
                    + *(float *)(v44 + 4 * v74 + 8))
            + *(float *)(v44 + 4 * v74 + 12);
      }
      while ( v68 < v65 - 3 );
      if ( v68 < v65 )
      {
LABEL_144:
        do
        {
          v75 = v68++;
          v67 = v67 + *(float *)(v44 + 4 * v75);
        }
        while ( v68 < v65 );
      }
    }
    if ( v67 != 0.0 )
    {
      v66.m128_f32[0] = v66.m128_f32[0] / v67;
      v76 = _mm_shuffle_ps(v66, v66, 0);
      goto LABEL_128;
    }
  }
  v76 = _mm_shuffle_ps(v66, v66, 0);
  if ( v65 > 0 )
  {
LABEL_128:
    v77 = _mm_shuffle_ps(v66, v66, 0);
    v78 = 0;
    if ( (unsigned int)v65 < 0x10 )
      goto LABEL_133;
    do
    {
      v79 = v78;
      v78 += 16;
      *(__m128 *)(v44 + 4 * v79) = _mm_mul_ps(*(__m128 *)(v44 + 4 * v79), v76);
      *(__m128 *)(v44 + 4 * v79 + 16) = _mm_mul_ps(*(__m128 *)(v44 + 4 * v79 + 16), v76);
      *(__m128 *)(v44 + 4 * v79 + 32) = _mm_mul_ps(*(__m128 *)(v44 + 4 * v79 + 32), v76);
      *(__m128 *)(v44 + 4 * v79 + 48) = _mm_mul_ps(*(__m128 *)(v44 + 4 * v79 + 48), v76);
    }
    while ( v78 < v65 - (v65 & 0xF) );
    if ( v78 < v65 )
    {
LABEL_133:
      if ( v65 - v78 < 4 )
        goto LABEL_145;
      do
      {
        v80 = v78;
        v78 += 4;
        *(__m128 *)(v44 + 4 * v80) = _mm_mul_ps(*(__m128 *)(v44 + 4 * v80), v77);
      }
      while ( v78 < v65 - 3 );
      if ( v78 < v65 )
      {
LABEL_145:
        do
        {
          v81 = v78++;
          *(float *)(v44 + 4 * v81) = v77.m128_f32[0] * *(float *)(v44 + 4 * v81);
        }
        while ( v78 < v65 );
      }
    }
  }
  *(_DWORD *)(a1 + 472) = *(_DWORD *)(a1 + 324);
  *(_DWORD *)(a1 + 476) = *(_DWORD *)(a1 + 320);
  *(_QWORD *)(a1 + 488) = *(_QWORD *)(a1 + 512);
  *(_DWORD *)(a1 + 496) = *(_DWORD *)(a1 + 464);
  *(double *)(a1 + 480) = a4;
  *(_BYTE *)(a1 + 469) = 1;
  return 0;
}

```

## disassembly

```asm
0x18007d000  push    rbx
0x18007d002  push    rdi
0x18007d003  sub     rsp, 0B8h
0x18007d00a  cmp     byte ptr [rcx+148h], 0
0x18007d011  mov     edi, edx
0x18007d013  movaps  [rsp+0C8h+var_48], xmm7
0x18007d01b  mov     rbx, rcx
0x18007d01e  movaps  [rsp+0C8h+var_88], xmm11
0x18007d024  movaps  xmm7, xmm2
0x18007d027  movaps  xmm11, xmm3
0x18007d02b  jnz     short loc_18007D070
0x18007d02d  xor     eax, eax
0x18007d02f  mov     byte ptr [rbx+1A0h], 1
0x18007d036  mov     [rcx+170h], rax
0x18007d03d  mov     [rcx+180h], rax
0x18007d044  mov     [rcx+1D0h], eax
0x18007d04a  mov     rcx, 3FF0000000000000h
0x18007d054  mov     [rbx+200h], rcx
0x18007d05b  mov     [rbx+14Ch], eax
0x18007d061  mov     dword ptr [rbx+150h], 7FFE795Eh
0x18007d06b  jmp     loc_18007DCCF
0x18007d070  movaps  [rsp+0C8h+var_58], xmm8
0x18007d076  movsd   xmm8, qword ptr [rcx+170h]
0x18007d07f  movaps  [rsp+0C8h+var_68], xmm9
0x18007d085  xorps   xmm9, xmm9
0x18007d089  ucomiss xmm2, xmm9
0x18007d08d  movaps  [rsp+0C8h+var_78], xmm10
0x18007d093  jnz     short loc_18007D114
0x18007d095  cmp     edi, 64h ; 'd'
0x18007d098  jl      short loc_18007D0A4
0x18007d09a  movss   xmm0, cs:__real@3f7d70a4
0x18007d0a2  jmp     short loc_18007D0F0
0x18007d0a4  cmp     edi, 2
0x18007d0a7  jg      short loc_18007D0B3
0x18007d0a9  movss   xmm0, cs:__real@3f592a30
0x18007d0b1  jmp     short loc_18007D0F0
0x18007d0b3  xorps   xmm0, xmm0
0x18007d0b6  cvtsi2ss xmm0, edi
0x18007d0ba  call    _o_logf_0
0x18007d0bf  xorps   xmm1, xmm1
0x18007d0c2  cvtss2sd xmm1, xmm0
0x18007d0c6  movaps  xmm0, xmm1
0x18007d0c9  movaps  xmm2, xmm1
0x18007d0cc  mulsd   xmm2, cs:__real@3fb13b1930a8945e
0x18007d0d4  mulsd   xmm0, cs:__real@3f77bc75cdc8b170
0x18007d0dc  mulsd   xmm0, xmm1
0x18007d0e0  subsd   xmm2, xmm0
0x18007d0e4  addsd   xmm2, cs:__real@3fe9be04a71d7f87
0x18007d0ec  cvtpd2ps xmm0, xmm2
0x18007d0f0  movss   xmm7, dword ptr [rbx+12Ch]
0x18007d0f8  divss   xmm7, dword ptr [rbx+130h]
0x18007d100  movss   xmm1, cs:__real@3f800000
0x18007d108  comiss  xmm7, xmm1
0x18007d10b  jb      short loc_18007D110
0x18007d10d  movaps  xmm7, xmm1
0x18007d110  mulss   xmm7, xmm0
0x18007d114  movaps  [rsp+0C8h+var_38], xmm6
0x18007d11c  cmp     edi, 1Eh
0x18007d11f  jl      short loc_18007D12B
0x18007d121  movss   xmm6, cs:__real@42c80000
0x18007d129  jmp     short loc_18007D171
0x18007d12b  movss   xmm6, cs:__real@41f00000
0x18007d133  lea     eax, ds:1[rdi*2]
0x18007d13a  movd    xmm0, edi
0x18007d13e  cvtdq2ps xmm0, xmm0
0x18007d141  subss   xmm6, xmm0
0x18007d145  movd    xmm0, eax
0x18007d149  cvtdq2ps xmm0, xmm0
0x18007d14c  mulss   xmm6, cs:__real@3d4de7ec
0x18007d154  addss   xmm6, cs:__real@3fc1096d
0x18007d15c  mulss   xmm6, xmm0
0x18007d160  addss   xmm6, cs:__real@41000000
0x18007d168  comiss  xmm6, cs:__real@42480000
0x18007d16f  jbe     short loc_18007D18A
0x18007d171  cvtps2pd xmm0, xmm6
0x18007d174  subsd   xmm0, cs:__real@4021666666666666
0x18007d17c  mulsd   xmm0, cs:__real@3fbc36113404ea4b
0x18007d184  cvtpd2ps xmm1, xmm0
0x18007d188  jmp     short loc_18007D1D2
0x18007d18a  movss   xmm0, cs:__real@41a80000
0x18007d192  comiss  xmm6, xmm0
0x18007d195  jb      short loc_18007D1CF
0x18007d197  movss   xmm1, cs:__real@3ecccccd; Y
0x18007d19f  subss   xmm6, xmm0
0x18007d1a3  movaps  xmm0, xmm6; X
0x18007d1a6  call    powf
0x18007d1ab  xorps   xmm1, xmm1
0x18007d1ae  cvtss2sd xmm1, xmm0
0x18007d1b2  cvtps2pd xmm0, xmm6
0x18007d1b5  mulsd   xmm1, cs:__real@3fe2b1c432ca57a8
0x18007d1bd  mulsd   xmm0, cs:__real@3fb4302b40f66a55
0x18007d1c5  addsd   xmm1, xmm0
0x18007d1c9  cvtpd2ps xmm1, xmm1
0x18007d1cd  jmp     short loc_18007D1D2
0x18007d1cf  xorps   xmm1, xmm1
0x18007d1d2  movss   dword ptr [rbx+238h], xmm1
0x18007d1da  lea     rdx, ?s_dblOneOverISqr@?1??Besseli0@@YANN@Z@4PANA; double near * `Besseli0(double)'::`2'::s_dblOneOverISqr
0x18007d1e1  movsd   xmm4, cs:__real@3ff0000000000000
0x18007d1e9  mov     ecx, 1
0x18007d1ee  movsd   xmm5, cs:__real@3e45798ee2308c3a
0x18007d1f6  movaps  xmm2, xmm4
0x18007d1f9  cvtps2pd xmm0, xmm1
0x18007d1fc  movaps  xmm3, xmm0
0x18007d1ff  mulsd   xmm3, cs:__real@3fd0000000000000
0x18007d207  mulsd   xmm3, xmm0
0x18007d20b  movaps  xmm1, xmm3
0x18007d20e  xchg    ax, ax
0x18007d210  inc     ecx
0x18007d212  addsd   xmm2, xmm1
0x18007d216  movsxd  rax, ecx
0x18007d219  movaps  xmm0, xmm3
0x18007d21c  mulsd   xmm0, qword ptr [rdx+rax*8]
0x18007d221  mulsd   xmm1, xmm0
0x18007d225  comisd  xmm1, xmm5
0x18007d229  jb      short loc_18007D230
0x18007d22b  cmp     ecx, 16h
0x18007d22e  jl      short loc_18007D210
0x18007d230  movaps  xmm0, xmm4
0x18007d233  movd    xmm3, edi
0x18007d237  divsd   xmm0, xmm2
0x18007d23b  cvtdq2pd xmm3, xmm3
0x18007d23f  xorps   xmm10, xmm10
0x18007d243  movsd   qword ptr [rbx+240h], xmm0
0x18007d24b  ucomisd xmm3, xmm10
0x18007d250  movaps  xmm0, xmm4
0x18007d253  movsd   qword ptr [rbx+170h], xmm3
0x18007d25b  jz      short loc_18007D261
0x18007d25d  divsd   xmm0, xmm3
0x18007d261  movsd   qword ptr [rbx+178h], xmm0
0x18007d269  lea     rcx, [rbx+130h]
0x18007d270  movss   xmm5, dword ptr [rcx]
0x18007d274  movss   xmm2, dword ptr [rbx+12Ch]
0x18007d27c  comiss  xmm2, xmm5
0x18007d27f  ja      short loc_18007D286
0x18007d281  movaps  xmm1, xmm3
0x18007d284  jmp     short loc_18007D294
0x18007d286  cvtps2pd xmm1, xmm2
0x18007d289  cvtps2pd xmm0, xmm5
0x18007d28c  divsd   xmm1, xmm0
0x18007d290  mulsd   xmm1, xmm3
0x18007d294  ucomiss xmm7, xmm9
0x18007d298  movsd   qword ptr [rbx+180h], xmm1
0x18007d2a0  jnz     short loc_18007D2CB
0x18007d2a2  mov     rcx, [rsp+0C8h]; this
0x18007d2aa  lea     r8, aAvcoreCodecdsp; "avcore\\codecdsp\\audio\\resample\\ares"...
0x18007d2b1  mov     r9d, 80004001h; char *
0x18007d2b7  mov     edx, 81Ch; void *
0x18007d2bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d2c1  mov     eax, 80004001h
0x18007d2c6  jmp     loc_18007DCB5
0x18007d2cb  movaps  xmm0, xmm2
0x18007d2ce  mov     [rsp+0C8h+arg_10], rsi
0x18007d2d6  divss   xmm0, xmm7
0x18007d2da  lea     rax, [rsp+0C8h+var_90]
0x18007d2df  comiss  xmm0, xmm5
0x18007d2e2  movss   [rsp+0C8h+var_90], xmm0
0x18007d2e8  cmovbe  rax, rcx
0x18007d2ec  comiss  xmm5, xmm2
0x18007d2ef  jb      short loc_18007D2F4
0x18007d2f1  movaps  xmm2, xmm5
0x18007d2f4  divss   xmm2, dword ptr [rax]
0x18007d2f8  mov     rdx, 8000000000000000h
0x18007d302  cvtps2pd xmm0, xmm2
0x18007d305  xorps   xmm2, xmm2
0x18007d308  divsd   xmm1, xmm0
0x18007d30c  movsd   qword ptr [rbx+200h], xmm0
0x18007d314  movaps  xmm0, xmm1
0x18007d317  movsd   qword ptr [rbx+180h], xmm1
0x18007d31f  addsd   xmm0, xmm1
0x18007d323  addsd   xmm0, xmm4
0x18007d327  cvttsd2si rcx, xmm0
0x18007d32c  cmp     rcx, rdx
0x18007d32f  jz      short loc_18007D358
0x18007d331  xorps   xmm2, xmm2
0x18007d334  cvtsi2sd xmm2, rcx
0x18007d339  ucomisd xmm2, xmm0
0x18007d33d  jz      short loc_18007D358
0x18007d33f  unpcklpd xmm0, xmm0
0x18007d343  movmskpd eax, xmm0
0x18007d347  xorps   xmm0, xmm0
0x18007d34a  and     eax, 1
0x18007d34d  xor     eax, 1
0x18007d350  add     rcx, rax
0x18007d353  cvtsi2sd xmm0, rcx
0x18007d358  cvttsd2si eax, xmm0
0x18007d35c  cvttsd2si rcx, xmm1
0x18007d361  add     eax, 5
0x18007d364  mov     [rbx+14Ch], eax
0x18007d36a  xorps   xmm0, xmm0
0x18007d36d  cmp     rcx, rdx
0x18007d370  jz      short loc_18007D399
0x18007d372  xorps   xmm0, xmm0
0x18007d375  cvtsi2sd xmm0, rcx
0x18007d37a  ucomisd xmm0, xmm1
0x18007d37e  jz      short loc_18007D399
0x18007d380  unpcklpd xmm1, xmm1
0x18007d384  movmskpd eax, xmm1
0x18007d388  xorps   xmm1, xmm1
0x18007d38b  and     eax, 1
0x18007d38e  xor     eax, 1
0x18007d391  add     rcx, rax
0x18007d394  cvtsi2sd xmm1, rcx
0x18007d399  mov     r10d, [rbx+144h]
0x18007d3a0  cvttsd2si eax, xmm1
0x18007d3a4  mov     [rbx+1D0h], eax
0x18007d3aa  inc     eax
0x18007d3ac  imul    eax, r10d
0x18007d3b0  cmp     eax, 186A0h
0x18007d3b5  setl    al
0x18007d3b8  mov     [rbx+1A0h], al
0x18007d3be  mov     r9d, [rbx+140h]
0x18007d3c5  cmp     r10d, r9d
0x18007d3c8  mov     esi, r9d
0x18007d3cb  cmovge  esi, r10d
0x18007d3cf  cmp     esi, 500h
0x18007d3d5  jle     short loc_18007D3E5
0x18007d3d7  xor     al, al
0x18007d3d9  mov     byte ptr [rbx+1A0h], 0
0x18007d3e0  xor     r8b, r8b
0x18007d3e3  jmp     short loc_18007D3E9
0x18007d3e5  movzx   r8d, al
0x18007d3e9  cmp     byte ptr [rbx+134h], 0
0x18007d3f0  jz      loc_18007D4CE
0x18007d3f6  mov     byte ptr [rbx+1A0h], 0
0x18007d3fd  xor     r8b, r8b
0x18007d400  mov     eax, 7FFE795Eh
0x18007d405  mov     [rsp+0C8h+arg_8], rbp
0x18007d40d  mov     [rsp+0C8h+arg_18], r12
0x18007d415  mov     [rsp+0C8h+var_18], r13
0x18007d41d  mov     [rsp+0C8h+var_20], r14
0x18007d425  mov     [rsp+0C8h+var_28], r15
0x18007d42d  mov     [rbx+150h], eax
0x18007d433  test    r8b, r8b
0x18007d436  jz      short loc_18007D48D
0x18007d438  cmp     byte ptr [rbx+1D5h], 0
0x18007d43f  jz      loc_18007D4F6
0x18007d445  cmp     r10d, [rbx+1D8h]
0x18007d44c  jnz     short loc_18007D486
0x18007d44e  cmp     r9d, [rbx+1DCh]
0x18007d455  jnz     short loc_18007D486
0x18007d457  ucomisd xmm11, qword ptr [rbx+1E0h]
0x18007d460  jnz     short loc_18007D486
0x18007d462  movsd   xmm0, qword ptr [rbx+1E8h]
0x18007d46a  ucomisd xmm0, qword ptr [rbx+200h]
0x18007d472  jnz     short loc_18007D486
0x18007d474  mov     eax, [rbx+1F0h]
0x18007d47a  cmp     [rbx+1D0h], eax
0x18007d480  jz      loc_18007DC83
0x18007d486  mov     byte ptr [rbx+1A0h], 0
0x18007d48d  cmp     byte ptr [rbx+1D4h], 0
0x18007d494  jz      loc_18007DACD
0x18007d49a  ucomisd xmm3, xmm8
0x18007d49f  jz      loc_18007DC83
0x18007d4a5  mov     rcx, [rsp+0C8h]; this
0x18007d4ad  lea     r8, aAvcoreCodecdsp; "avcore\\codecdsp\\audio\\resample\\ares"...
0x18007d4b4  mov     r9d, 80004001h; char *
0x18007d4ba  mov     edx, 87Bh; void *
0x18007d4bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d4c4  mov     eax, 80004001h
0x18007d4c9  jmp     loc_18007DC85
0x18007d4ce  test    al, al
0x18007d4d0  jz      loc_18007D400
0x18007d4d6  cmp     r10d, r9d
0x18007d4d9  mov     eax, 144h
0x18007d4de  mov     ecx, 140h
0x18007d4e3  cmovge  ecx, eax
0x18007d4e6  mov     eax, 7F67697Fh
0x18007d4eb  cdq
0x18007d4ec  idiv    dword ptr [rcx+rbx]
0x18007d4ef  dec     eax
0x18007d4f1  jmp     loc_18007D405
0x18007d4f6  xor     r15d, r15d
0x18007d4f9  ucomisd xmm11, xmm10
0x18007d4fe  mov     r12d, r15d
0x18007d501  mov     [rsp+0C8h+var_98], r15d
0x18007d506  mov     [rsp+0C8h+arg_0], r12b
0x18007d50e  jnz     loc_18007D61B
0x18007d514  ucomisd xmm4, qword ptr [rbx+200h]
0x18007d51c  jnz     loc_18007D61B
0x18007d522  mov     rcx, cs:?m_predesignFil@?$AResampler@MM$00@@1QBQEBNB; double const * const near * const AResampler<float,float,1>::m_predesignFil
0x18007d529  mov     edx, esi
0x18007d52b  imul    edx, edi
0x18007d52e  movd    xmm1, esi
0x18007d532  cvtdq2pd xmm1, xmm1
0x18007d536  lea     eax, ds:1[rdx*2]
0x18007d53d  ucomisd xmm1, qword ptr [rcx]
0x18007d541  movd    xmm0, eax
0x18007d545  cvtdq2pd xmm0, xmm0
0x18007d549  jnz     short loc_18007D556
0x18007d54b  ucomisd xmm0, qword ptr [rcx+8]
0x18007d550  jz      loc_18007D60B
0x18007d556  mov     rcx, cs:off_1800871C8
0x18007d55d  ucomisd xmm1, qword ptr [rcx]
0x18007d561  jnz     short loc_18007D56E
0x18007d563  ucomisd xmm0, qword ptr [rcx+8]
0x18007d568  jz      loc_18007D60B
0x18007d56e  mov     rcx, cs:off_1800871D0
0x18007d575  ucomisd xmm1, qword ptr [rcx]
0x18007d579  jnz     short loc_18007D586
0x18007d57b  ucomisd xmm0, qword ptr [rcx+8]
  ... truncated ...
```
