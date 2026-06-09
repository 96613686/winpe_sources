# CBezier::AddLeastSquares(CData const &,int,C3Point const &,int,C3Point const &)

- ea: `0x1800154f0`
- end: `0x1800162ec`
- name: `?AddLeastSquares@CBezier@@IEAA_NAEBVCData@@HAEBVC3Point@@H1@Z`
- size: `3580`
- prototype: `bool __fastcall(CBezier *__hidden this, const struct CData *, int, const struct C3Point *, int, const struct C3Point *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180014aa0`

## callees

- `0x180002740`
- `0x1800154f0`
- `0x18004451c`
- `0x1800445e8`
- `0x180044658`
- `0x180044ab0`
- `0x180044ad2`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001601b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800160a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001601b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800160a8`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18001612b`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18001613c`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18001612b`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18001613c`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800161bd`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18001628d`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800161bd`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18001628d`

## pseudocode

```c
char __fastcall CBezier::AddLeastSquares(
        CBezier *this,
        const struct CData *a2,
        int a3,
        const struct C3Point *a4,
        int a5,
        __m128d *a6)
{
  double v8; // xmm1_8
  double v10; // xmm7_8
  double v11; // xmm10_8
  double v12; // xmm13_8
  double v13; // xmm14_8
  __int64 v14; // r11
  double v15; // xmm15_8
  int v16; // edx
  __int64 v17; // r8
  double v18; // xmm8_8
  double v19; // xmm0_8
  __int64 v20; // r9
  double v21; // xmm11_8
  double v22; // xmm12_8
  double v23; // xmm14_8
  double v24; // xmm15_8
  double v25; // xmm2_8
  double v26; // xmm11_8
  __int64 v27; // rax
  double v28; // xmm3_8
  double v29; // xmm3_8
  double v30; // xmm2_8
  double v31; // xmm6_8
  double v32; // xmm4_8
  double v33; // xmm5_8
  double v34; // xmm2_8
  double v35; // xmm7_8
  double v36; // xmm4_8
  double v37; // xmm3_8
  double v38; // xmm5_8
  double v39; // xmm0_8
  double v40; // xmm1_8
  double v41; // xmm3_8
  double v42; // xmm0_8
  double v43; // xmm0_8
  double v44; // xmm4_8
  __int64 v45; // rcx
  double v46; // xmm3_8
  double v47; // xmm11_8
  double v48; // xmm12_8
  double v49; // xmm8_8
  double v50; // xmm5_8
  double v51; // xmm2_8
  double v52; // xmm8_8
  double v53; // xmm5_8
  __m128d v54; // xmm6
  double v55; // xmm7_8
  double v56; // xmm10_8
  double v57; // xmm1_8
  double v58; // xmm3_8
  double v59; // xmm0_8
  double v60; // xmm6_8
  double v61; // xmm0_8
  __int64 v62; // rax
  __m128d v63; // xmm7
  unsigned __int64 v64; // r14
  unsigned int v65; // r10d
  __m128d v66; // xmm6
  unsigned __int64 v67; // rbp
  unsigned __int64 v68; // rbp
  SIZE_T v69; // r15
  void *v70; // rcx
  char v71; // al
  unsigned __int64 v72; // r8
  double v73; // xmm11_8
  double v74; // xmm12_8
  double *v75; // rcx
  __int64 v76; // rdx
  unsigned __int64 v77; // r15
  __int64 v78; // r9
  __int64 v79; // r14
  unsigned __int64 v80; // rbp
  __m128d v81; // xmm6
  SIZE_T v82; // r8
  unsigned __int64 v83; // rbp
  void *v84; // rcx
  char v85; // al
  unsigned __int64 v86; // r8
  __m128d *v87; // rcx
  __int64 v88; // rax
  __int64 v89; // rdx
  double v91; // xmm8_8
  __int64 v92; // rax
  double v93; // xmm3_8
  double v94; // xmm2_8
  double v95; // xmm6_8
  double v96; // xmm4_8
  double v97; // xmm5_8
  double v98; // xmm2_8
  double v99; // xmm7_8
  double v100; // xmm4_8
  double v101; // xmm3_8
  __int64 v102; // rax
  double v103; // xmm5_8
  double v104; // xmm10_8
  double v105; // xmm13_8
  double v106; // xmm1_8
  double v107; // xmm3_8
  double v108; // xmm4_8
  double v109; // xmm2_8
  double v110; // xmm5_8
  double v111; // xmm6_8
  double v112; // xmm2_8
  double v113; // xmm6_8
  double v114; // xmm3_8
  __int64 v115; // rax
  double v116; // xmm7_8
  double v117; // xmm13_8
  double v118; // xmm8_8
  double v119; // xmm4_8
  double v120; // xmm10_8
  double v121; // xmm0_8
  double v122; // xmm1_8
  double v123; // xmm3_8
  double v124; // xmm2_8
  double v125; // xmm3_8
  double v126; // xmm5_8
  double v127; // xmm7_8
  double v128; // xmm6_8
  double v129; // xmm8_8
  double v130; // xmm2_8
  double v131; // xmm3_8
  double v132; // xmm4_8
  void *v133; // r12
  LPVOID v134; // rax
  _QWORD *ThreadLocalStoragePointer; // rax
  double v136; // r8
  LPVOID v137; // rax
  double v138; // [rsp+20h] [rbp-138h]
  __int64 v139; // [rsp+20h] [rbp-138h]
  double v140; // [rsp+20h] [rbp-138h]
  double v141; // [rsp+20h] [rbp-138h]
  double pExceptionObject; // [rsp+28h] [rbp-130h] BYREF
  double v143; // [rsp+30h] [rbp-128h]
  double v144; // [rsp+38h] [rbp-120h]
  double v145; // [rsp+40h] [rbp-118h]
  double v146; // [rsp+48h] [rbp-110h]
  double v147; // [rsp+50h] [rbp-108h]
  double v148; // [rsp+58h] [rbp-100h]
  double v149; // [rsp+60h] [rbp-F8h]
  double v150; // [rsp+68h] [rbp-F0h]
  double v151; // [rsp+70h] [rbp-E8h]

  v8 = DOUBLE_3_0;
  v10 = 0.0;
  v11 = 0.0;
  v12 = 0.0;
  v13 = 0.0;
  v14 = a3;
  v15 = 0.0;
  v145 = 0.0;
  v143 = 0.0;
  v16 = a3 + 1;
  pExceptionObject = 0.0;
  v144 = 0.0;
  v147 = 0.0;
  v146 = 0.0;
  v138 = 0.0;
  if ( a3 + 1 >= a5 )
    goto LABEL_8;
  v17 = *((_QWORD *)a2 + 3);
  v18 = a6->m128d_f64[0];
  v19 = a6->m128d_f64[1];
  v20 = *((_QWORD *)a2 + 2);
  v21 = *(double *)(v17 + 8LL * a5);
  v22 = *(double *)(v17 + 8 * v14);
  v23 = *(double *)a4;
  v24 = *((double *)a4 + 1);
  v25 = DOUBLE_1_0;
  v151 = v21;
  v149 = v18;
  v148 = v19;
  if ( a5 - v16 < 3 )
  {
    v148 = v19;
    goto LABEL_4;
  }
  v91 = v21 - v22;
  v150 = v21 - v22;
  while ( 1 )
  {
    v92 = 32LL * v16;
    v93 = (*(double *)(v17 + 8LL * v16) - v22) / v91;
    v94 = v25 - v93;
    v95 = v94 * v8 * (v93 * v93);
    v96 = v94 * v94 * v8;
    v97 = v94 * v94 * v94;
    v98 = *(double *)(v92 + v20 + 8);
    v99 = v93 * v93 * v93 + v95;
    v100 = v96 * v93;
    v101 = *(double *)(v92 + v20);
    v102 = v16 + 1LL;
    v103 = v97 + v100;
    v104 = v11 + v95 * v95;
    v105 = v12 + v100 * v100;
    v143 = v143 + v95 * v100;
    v147 = v147 - v103 * v100;
    v146 = v146 - v99 * v100;
    v106 = (v101 * v23 + v98 * v24) * v100;
    v107 = (v101 * v149 + v98 * v148) * v95;
    v108 = (*(double *)(v17 + 8 * v102) - v22) / v91;
    pExceptionObject = pExceptionObject + v106;
    v109 = 1.0 - v108;
    v145 = v145 - v103 * v95;
    v140 = v138 - v99 * v95;
    v110 = v109 * v109 * 3.0 * v108;
    v144 = v144 + v107;
    v111 = v109 * v109 * v109;
    v102 *= 32;
    v112 = *(double *)(v102 + v20 + 8);
    v113 = v111 + v110;
    v114 = *(double *)(v102 + v20);
    v115 = v16 + 2LL;
    v116 = (1.0 - v108) * 3.0 * (v108 * v108);
    v117 = v105 + v110 * v110;
    v118 = v108 * v108 * v108 + v116;
    v119 = (*(double *)(v17 + 8 * v115) - v22) / v150;
    v120 = v104 + v116 * v116;
    v143 = v143 + v116 * v110;
    v147 = v147 - v113 * v110;
    v121 = v112 * v24;
    v146 = v146 - v118 * v110;
    v122 = v114 * v23;
    v123 = v114 * v149 + v112 * v148;
    v124 = 1.0 - v119;
    v125 = v123 * v116;
    pExceptionObject = pExceptionObject + (v122 + v121) * v110;
    v145 = v145 - v113 * v116;
    v141 = v140 - v118 * v116;
    v126 = v124 * v124 * 3.0 * v119;
    v127 = (1.0 - v119) * 3.0 * (v119 * v119);
    v144 = v144 + v125;
    v12 = v117 + v126 * v126;
    v11 = v120 + v127 * v127;
    v16 += 3;
    v115 *= 32;
    v128 = v124 * v124 * v124;
    v143 = v143 + v127 * v126;
    v129 = v119 * v119 * v119 + v127;
    v130 = *(double *)(v115 + v20 + 8);
    v131 = *(double *)(v115 + v20);
    v147 = v147 - (v128 + v126) * v126;
    v146 = v146 - v129 * v126;
    pExceptionObject = pExceptionObject + (v131 * v23 + v130 * v24) * v126;
    v144 = v144 + (v131 * v149 + v130 * v148) * v127;
    v25 = DOUBLE_1_0;
    v145 = v145 - (v128 + v126) * v127;
    v132 = v141 - v129 * v127;
    v91 = v150;
    v138 = v132;
    if ( v16 >= a5 - 2 )
      break;
    v8 = DOUBLE_3_0;
  }
  v21 = v151;
  if ( v16 < a5 )
  {
    v18 = v149;
    v8 = DOUBLE_3_0;
LABEL_4:
    v26 = v21 - v22;
    do
    {
      v27 = v16++;
      v28 = *(double *)(v17 + 8 * v27);
      v27 *= 32;
      v29 = (v28 - v22) / v26;
      v30 = v25 - v29;
      v31 = v30 * v8 * (v29 * v29);
      v32 = v30 * v30 * v8;
      v33 = v30 * v30 * v30;
      v34 = *(double *)(v27 + v20);
      v35 = v29 * v29 * v29 + v31;
      v36 = v32 * v29;
      v37 = *(double *)(v27 + v20 + 8);
      v11 = v11 + v31 * v31;
      v38 = v33 + v36;
      v12 = v12 + v36 * v36;
      v143 = v143 + v31 * v36;
      v147 = v147 - v38 * v36;
      v39 = v34 * v23;
      v146 = v146 - v35 * v36;
      v40 = v37 * v24;
      v41 = v37 * v148 + v34 * v18;
      v25 = DOUBLE_1_0;
      v42 = pExceptionObject + (v40 + v39) * v36;
      v8 = DOUBLE_3_0;
      pExceptionObject = v42;
      v145 = v145 - v38 * v31;
      v138 = v138 - v35 * v31;
      v43 = v144 + v41 * v31;
      v144 = v43;
    }
    while ( v16 < a5 );
    v13 = v43;
    goto LABEL_7;
  }
  v13 = v144;
LABEL_7:
  v15 = v145;
  v10 = pExceptionObject;
LABEL_8:
  v44 = a6->m128d_f64[0];
  v45 = *((_QWORD *)a2 + 2);
  v46 = a6->m128d_f64[1];
  v47 = *((double *)a4 + 1);
  v48 = *(double *)a4;
  v54 = (__m128d)*(unsigned __int64 *)(v45 + 32LL * a5 + 8);
  v49 = v46 * v47 + a6->m128d_f64[0] * *(double *)a4;
  v50 = *(double *)(v45 + 32LL * a5 + 8);
  v51 = *(double *)(v45 + 32LL * a5);
  v148 = *(double *)(32 * v14 + v45 + 8);
  v52 = v49 * v143;
  v143 = *(double *)(32 * v14 + v45);
  v53 = (v50 * v47 + v51 * v48) * v146 + (v148 * v47 + v143 * v48) * v147 + v10;
  v54.m128d_f64[0] = (v54.m128d_f64[0] * v46 + v51 * v44) * v138 + (v148 * v46 + v143 * v44) * v15 + v13;
  v55 = v53 * v11 - v54.m128d_f64[0] * v52;
  v56 = v11 * v12 - v52 * v52;
  *(_QWORD *)&v57 = *(_QWORD *)&v56 ^ _xmm;
  if ( v56 < 0.0 )
    *(_QWORD *)&v58 = *(_QWORD *)&v56 ^ _xmm;
  else
    v58 = v56;
  v59 = v55;
  if ( v55 < 0.0 )
    *(_QWORD *)&v59 = *(_QWORD *)&v55 ^ _xmm;
  if ( v58 <= v59 * 0.000000001 )
    goto LABEL_18;
  v60 = v54.m128d_f64[0] * v12 - v53 * v52;
  if ( v56 >= 0.0 )
    v57 = v56;
  v61 = v60;
  if ( v60 < 0.0 )
    *(_QWORD *)&v61 = *(_QWORD *)&v60 ^ _xmm;
  if ( v57 <= v61 * 0.000000001
    || (v63.m128d_f64[0] = v55 / v56, v63.m128d_f64[0] <= 0.000001)
    || (v54.m128d_f64[0] = v60 / v56, v54.m128d_f64[0] <= 0.000001) )
  {
LABEL_18:
    v62 = *((_QWORD *)a2 + 3);
    v63 = (__m128d)*(unsigned __int64 *)(v62 + 8LL * a5);
    v63.m128d_f64[0] = (v63.m128d_f64[0] - *(double *)(v62 + 8 * v14)) / 3.0;
    v54 = v63;
  }
  v64 = *((_QWORD *)this + 2);
  v65 = tls_index;
  v66 = _mm_unpacklo_pd(v54, v54);
  v139 = 16;
  v67 = v64 + 1;
  if ( v64 + 1 <= *((_QWORD *)this + 3) )
    goto LABEL_30;
  if ( v67 >= 0x20 )
  {
    v68 = v67 | 0xF;
    goto LABEL_67;
  }
  if ( v67 < 2 )
  {
    v68 = 1;
    v69 = 16;
  }
  else if ( v67 < 4 )
  {
    v68 = 3;
    v69 = 48;
  }
  else
  {
    if ( v67 >= 8 )
    {
      if ( v67 < 0x10 )
      {
        v68 = 15;
        v69 = 240;
        goto LABEL_69;
      }
      v68 = 31;
LABEL_67:
      if ( v68 > 0xFFFFFFFFFFFFFFFLL )
        goto LABEL_26;
      v69 = 16 * v68;
      if ( 16 * v68 > 0xFFFFFFFF )
        goto LABEL_26;
      goto LABEL_69;
    }
    v68 = 7;
    v69 = 112;
  }
LABEL_69:
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v136 = *((double *)this + 1);
  v149 = v136;
  if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA > *(_DWORD *)(ThreadLocalStoragePointer[tls_index] + 4LL) )
  {
    Init_thread_header(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
    if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA == -1 )
    {
      `WinHeap::GetDefault'::`2'::s_WinHeap = 0;
      dwFlags = 0;
      `WinHeap::GetDefault'::`2'::s_WinHeap = HeapCreate(0, 0x10000u, 0);
      atexit(`WinHeap::GetDefault'::`2'::`dynamic atexit destructor for 's_WinHeap'');
      Init_thread_footer(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
    }
    v136 = v149;
  }
  if ( `WinHeap::GetDefault'::`2'::s_WinHeap )
  {
    v137 = v136 == 0.0
         ? HeapAlloc(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, v69)
         : HeapReAlloc(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, *(LPVOID *)&v136, v69);
    if ( v137 )
    {
      *((_QWORD *)this + 1) = v137;
      v71 = 1;
      goto LABEL_29;
    }
  }
LABEL_26:
  v70 = (void *)*((_QWORD *)this + 1);
  if ( v70 )
  {
    WinFree(v70);
    *((_QWORD *)this + 1) = 0;
  }
  v71 = 0;
  *((_QWORD *)this + 2) = 0;
  v68 = 0;
LABEL_29:
  *((_QWORD *)this + 3) = v68;
  v65 = tls_index;
  if ( !v71 )
  {
    v77 = *((_QWORD *)this + 2);
    v76 = *((_QWORD *)this + 1);
    v75 = (double *)(v76 + 16 * v77);
    goto LABEL_33;
  }
LABEL_30:
  v72 = *((_QWORD *)this + 2);
  v73 = v47 * v63.m128d_f64[0] + v148;
  v74 = v48 * v63.m128d_f64[0] + v143;
  if ( v64 < v72 )
  {
    memmove_0(
      (void *)(*((_QWORD *)this + 1) + 16 * v64 + 16),
      (const void *)(*((_QWORD *)this + 1) + 16 * v64),
      16 * (v72 - v64));
    v65 = tls_index;
  }
  v75 = (double *)(16 * v64 + *((_QWORD *)this + 1));
  *v75 = v74;
  v75[1] = v73;
  v76 = *((_QWORD *)this + 1);
  v77 = *((_QWORD *)this + 2) + 1LL;
  *((_QWORD *)this + 2) = v77;
LABEL_33:
  v78 = v76;
  v79 = 16 * v77;
  if ( (double *)(v76 + 16 * v77) == v75 )
  {
    LODWORD(pExceptionObject) = -2147024882;
    throw (long *)&pExceptionObject;
  }
  v80 = v77 + 1;
  v81 = _mm_add_pd(_mm_mul_pd(v66, *a6), *(__m128d *)(*((_QWORD *)a2 + 2) + 32LL * a5));
  if ( v77 + 1 <= *((_QWORD *)this + 3) )
    goto LABEL_44;
  if ( v80 >= 0x20 )
  {
    v83 = v80 | 0xF;
  }
  else
  {
    if ( v80 < 2 )
    {
      v83 = 1;
      v82 = 16;
      goto LABEL_59;
    }
    if ( v80 < 4 )
    {
      v82 = 48;
      v83 = 3;
      v139 = 48;
      goto LABEL_59;
    }
    if ( v80 < 8 )
    {
      v82 = 112;
      v83 = 7;
      v139 = 112;
      goto LABEL_59;
    }
    if ( v80 < 0x10 )
    {
      v82 = 240;
      v83 = 15;
      v139 = 240;
      goto LABEL_59;
    }
    v83 = 31;
  }
  if ( v83 > 0xFFFFFFFFFFFFFFFLL || (v82 = 16 * v83, v139 = 16 * v83, 16 * v83 > 0xFFFFFFFF) )
  {
LABEL_39:
    v84 = (void *)*((_QWORD *)this + 1);
    if ( v84 )
    {
      WinFree(v84);
      *((_QWORD *)this + 1) = 0;
    }
    v85 = 0;
    *((_QWORD *)this + 2) = 0;
    v83 = 0;
    goto LABEL_42;
  }
LABEL_59:
  v133 = (void *)*((_QWORD *)this + 1);
  if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                   + v65)
                                                                 + 4LL) )
  {
    Init_thread_header(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
    if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA == -1 )
    {
      `WinHeap::GetDefault'::`2'::s_WinHeap = 0;
      dwFlags = 0;
      `WinHeap::GetDefault'::`2'::s_WinHeap = HeapCreate(0, 0x10000u, 0);
      atexit(`WinHeap::GetDefault'::`2'::`dynamic atexit destructor for 's_WinHeap'');
      Init_thread_footer(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
    }
    v82 = v139;
  }
  if ( !`WinHeap::GetDefault'::`2'::s_WinHeap )
    goto LABEL_39;
  v134 = v133
       ? HeapReAlloc(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, v133, v82)
       : HeapAlloc(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, v82);
  if ( !v134 )
    goto LABEL_39;
  *((_QWORD *)this + 1) = v134;
  v85 = 1;
LABEL_42:
  *((_QWORD *)this + 3) = v83;
  if ( !v85 )
  {
    v88 = *((_QWORD *)this + 2);
    v89 = *((_QWORD *)this + 1);
    v87 = (__m128d *)(v89 + 16 * v88);
    goto LABEL_47;
  }
  v78 = *((_QWORD *)this + 1);
LABEL_44:
  v86 = *((_QWORD *)this + 2);
  if ( v77 < v86 )
    memmove_0((void *)(v78 + v79 + 16), (const void *)(v78 + v79), 16 * (v86 - v77));
  v87 = (__m128d *)(v79 + *((_QWORD *)this + 1));
  *v87 = v81;
  v88 = ++*((_QWORD *)this + 2);
  v89 = *((_QWORD *)this + 1);
LABEL_47:
  if ( (__m128d *)(v89 + 16 * v88) == v87 )
  {
    LODWORD(pExceptionObject) = -2147024882;
    throw (long *)&pExceptionObject;
  }
  (*(void (__fastcall **)(CBezier *, const struct CData *, _QWORD, __int64))(*(_QWORD *)this + 16LL))(
    this,
    a2,
    (unsigned int)a5,
    v78);
  return 1;
}

```

## disassembly

```asm
0x1800154f0  mov     rax, rsp
0x1800154f3  mov     [rax+18h], rbx
0x1800154f7  push    rbp
0x1800154f8  push    rsi
0x1800154f9  push    rdi
0x1800154fa  push    r12
0x1800154fc  push    r13
0x1800154fe  push    r14
0x180015500  push    r15
0x180015502  sub     rsp, 120h
0x180015509  movsxd  rdi, [rsp+158h+arg_20]
0x180015511  mov     rsi, rdx
0x180015514  mov     r12, [rsp+158h+arg_28]
0x18001551c  mov     r10, r9
0x18001551f  movsd   xmm1, cs:__real@4008000000000000
0x180015527  mov     rbx, rcx
0x18001552a  movaps  xmmword ptr [rax-48h], xmm6
0x18001552e  movaps  xmmword ptr [rax-58h], xmm7
0x180015532  xorps   xmm7, xmm7
0x180015535  movaps  xmmword ptr [rax-68h], xmm8
0x18001553a  movaps  xmmword ptr [rax-78h], xmm9
0x18001553f  xorps   xmm9, xmm9
0x180015543  movaps  xmmword ptr [rax-88h], xmm10
0x18001554b  xorps   xmm10, xmm10
0x18001554f  movaps  xmmword ptr [rax-98h], xmm11
0x180015557  movaps  xmmword ptr [rax-0A8h], xmm12
0x18001555f  movaps  xmmword ptr [rax-0B8h], xmm13
0x180015567  xorps   xmm13, xmm13
0x18001556b  movaps  xmmword ptr [rax-0C8h], xmm14
0x180015573  xorps   xmm14, xmm14
0x180015577  movsxd  r11, r8d
0x18001557a  movaps  xmmword ptr [rax-0D8h], xmm15
0x180015582  xorps   xmm15, xmm15
0x180015586  movsd   [rsp+158h+var_118], xmm15
0x18001558d  movsd   [rsp+158h+var_128], xmm9
0x180015594  lea     edx, [r11+1]
0x180015598  movsd   [rsp+158h+pExceptionObject], xmm7
0x18001559e  movsd   [rsp+158h+var_120], xmm14
0x1800155a5  movsd   [rsp+158h+var_108], xmm9
0x1800155ac  movsd   [rsp+158h+var_110], xmm9
0x1800155b3  movsd   [rsp+158h+var_138], xmm9
0x1800155ba  cmp     edx, edi
0x1800155bc  jge     loc_180015783
0x1800155c2  mov     r8, [rsi+18h]
0x1800155c6  mov     eax, edi
0x1800155c8  movsd   xmm8, qword ptr [r12]
0x1800155ce  sub     eax, edx
0x1800155d0  movsd   xmm0, qword ptr [r12+8]
0x1800155d7  mov     r9, [rsi+10h]
0x1800155db  movsd   xmm11, qword ptr [r8+rdi*8]
0x1800155e1  movsd   xmm12, qword ptr [r8+r11*8]
0x1800155e7  movsd   xmm14, qword ptr [r10]
0x1800155ec  movsd   xmm15, qword ptr [r10+8]
0x1800155f2  movsd   xmm2, cs:__real@3ff0000000000000
0x1800155fa  movsd   [rsp+158h+var_E8], xmm11
0x180015601  movsd   [rsp+158h+var_F8], xmm8
0x180015608  movsd   [rsp+158h+var_100], xmm0
0x18001560e  cmp     eax, 3
0x180015611  jge     loc_180015B8B
0x180015617  movsd   [rsp+158h+var_100], xmm0
0x18001561d  movsd   xmm9, [rsp+158h+var_100]
0x180015624  subsd   xmm11, xmm12
0x180015629  movsxd  rax, edx
0x18001562c  inc     edx
0x18001562e  movsd   xmm3, qword ptr [r8+rax*8]
0x180015634  subsd   xmm3, xmm12
0x180015639  shl     rax, 5
0x18001563d  divsd   xmm3, xmm11
0x180015642  subsd   xmm2, xmm3
0x180015646  movaps  xmm7, xmm3
0x180015649  mulsd   xmm7, xmm3
0x18001564d  movaps  xmm5, xmm2
0x180015650  movaps  xmm6, xmm2
0x180015653  mulsd   xmm6, xmm1
0x180015657  mulsd   xmm5, xmm2
0x18001565b  mulsd   xmm6, xmm7
0x18001565f  mulsd   xmm7, xmm3
0x180015663  movaps  xmm4, xmm5
0x180015666  mulsd   xmm4, xmm1
0x18001566a  mulsd   xmm5, xmm2
0x18001566e  movaps  xmm1, xmm6
0x180015671  movsd   xmm2, qword ptr [rax+r9]
0x180015677  addsd   xmm7, xmm6
0x18001567b  mulsd   xmm1, xmm6
0x18001567f  mulsd   xmm4, xmm3
0x180015683  movsd   xmm3, qword ptr [rax+r9+8]
0x18001568a  addsd   xmm10, xmm1
0x18001568f  movsd   xmm1, [rsp+158h+var_128]
0x180015695  addsd   xmm5, xmm4
0x180015699  movaps  xmm0, xmm4
0x18001569c  mulsd   xmm0, xmm4
0x1800156a0  addsd   xmm13, xmm0
0x1800156a5  movaps  xmm0, xmm6
0x1800156a8  mulsd   xmm0, xmm4
0x1800156ac  addsd   xmm1, xmm0
0x1800156b0  movaps  xmm0, xmm5
0x1800156b3  mulsd   xmm0, xmm4
0x1800156b7  mulsd   xmm5, xmm6
0x1800156bb  movsd   [rsp+158h+var_128], xmm1
0x1800156c1  movsd   xmm1, [rsp+158h+var_108]
0x1800156c7  subsd   xmm1, xmm0
0x1800156cb  movaps  xmm0, xmm7
0x1800156ce  mulsd   xmm0, xmm4
0x1800156d2  mulsd   xmm7, xmm6
0x1800156d6  movsd   [rsp+158h+var_108], xmm1
0x1800156dc  movsd   xmm1, [rsp+158h+var_110]
0x1800156e2  subsd   xmm1, xmm0
0x1800156e6  movaps  xmm0, xmm2
0x1800156e9  mulsd   xmm0, xmm14
0x1800156ee  mulsd   xmm2, xmm8
0x1800156f3  movsd   [rsp+158h+var_110], xmm1
0x1800156f9  movaps  xmm1, xmm3
0x1800156fc  mulsd   xmm1, xmm15
0x180015701  mulsd   xmm3, xmm9
0x180015706  addsd   xmm1, xmm0
0x18001570a  movsd   xmm0, [rsp+158h+pExceptionObject]
0x180015710  addsd   xmm3, xmm2
0x180015714  movsd   xmm2, cs:__real@3ff0000000000000
0x18001571c  mulsd   xmm1, xmm4
0x180015720  mulsd   xmm3, xmm6
0x180015724  addsd   xmm0, xmm1
0x180015728  movsd   xmm1, cs:__real@4008000000000000
0x180015730  movsd   [rsp+158h+pExceptionObject], xmm0
0x180015736  movsd   xmm0, [rsp+158h+var_118]
0x18001573c  subsd   xmm0, xmm5
0x180015740  movsd   [rsp+158h+var_118], xmm0
0x180015746  movsd   xmm0, [rsp+158h+var_138]
0x18001574c  subsd   xmm0, xmm7
0x180015750  movsd   [rsp+158h+var_138], xmm0
0x180015756  movsd   xmm0, [rsp+158h+var_120]
0x18001575c  addsd   xmm0, xmm3
0x180015760  movsd   [rsp+158h+var_120], xmm0
0x180015766  cmp     edx, edi
0x180015768  jl      loc_180015629
0x18001576e  xorps   xmm9, xmm9
0x180015772  movaps  xmm14, xmm0
0x180015776  movsd   xmm15, [rsp+158h+var_118]
0x18001577d  movsd   xmm7, [rsp+158h+pExceptionObject]
0x180015783  movsd   xmm4, qword ptr [r12]
0x180015789  mov     rax, r11
0x18001578c  mov     rcx, [rsi+10h]
0x180015790  movaps  xmm0, xmm4
0x180015793  movsd   xmm3, qword ptr [r12+8]
0x18001579a  mov     r13, rdi
0x18001579d  movsd   xmm11, qword ptr [r10+8]
0x1800157a3  movaps  xmm8, xmm3
0x1800157a7  movsd   xmm12, qword ptr [r10]
0x1800157ac  mulsd   xmm0, xmm12
0x1800157b1  shl     rax, 5
0x1800157b5  mulsd   xmm8, xmm11
0x1800157ba  shl     r13, 5
0x1800157be  movsd   xmm6, qword ptr [rcx+r13+8]
0x1800157c5  addsd   xmm8, xmm0
0x1800157ca  movsd   xmm0, qword ptr [rax+rcx+8]
0x1800157d0  movaps  xmm5, xmm6
0x1800157d3  movsd   xmm2, qword ptr [rcx+r13]
0x1800157d9  movsd   [rsp+158h+var_100], xmm0
0x1800157df  movsd   xmm0, qword ptr [rax+rcx]
0x1800157e4  mulsd   xmm8, [rsp+158h+var_128]
0x1800157eb  movsd   xmm1, [rsp+158h+var_100]
0x1800157f1  movsd   [rsp+158h+var_128], xmm0
0x1800157f7  movaps  xmm0, xmm2
0x1800157fa  mulsd   xmm0, xmm12
0x1800157ff  mulsd   xmm1, xmm11
0x180015804  mulsd   xmm5, xmm11
0x180015809  mulsd   xmm6, xmm3
0x18001580d  mulsd   xmm2, xmm4
0x180015811  addsd   xmm5, xmm0
0x180015815  movsd   xmm0, [rsp+158h+var_128]
0x18001581b  mulsd   xmm0, xmm12
0x180015820  addsd   xmm6, xmm2
0x180015824  mulsd   xmm5, [rsp+158h+var_110]
0x18001582a  addsd   xmm1, xmm0
0x18001582e  movsd   xmm0, [rsp+158h+var_128]
0x180015834  mulsd   xmm6, [rsp+158h+var_138]
0x18001583a  mulsd   xmm0, xmm4
0x18001583e  mulsd   xmm1, [rsp+158h+var_108]
0x180015844  movsd   xmm4, qword ptr cs:__xmm@80000000000000008000000000000000
0x18001584c  addsd   xmm5, xmm1
0x180015850  movsd   xmm1, [rsp+158h+var_100]
0x180015856  mulsd   xmm1, xmm3
0x18001585a  addsd   xmm5, xmm7
0x18001585e  addsd   xmm1, xmm0
0x180015862  movaps  xmm7, xmm5
0x180015865  mulsd   xmm1, xmm15
0x18001586a  mulsd   xmm7, xmm10
0x18001586f  mulsd   xmm10, xmm13
0x180015874  addsd   xmm6, xmm1
0x180015878  addsd   xmm6, xmm14
0x18001587d  movaps  xmm0, xmm6
0x180015880  mulsd   xmm0, xmm8
0x180015885  subsd   xmm7, xmm0
0x180015889  movaps  xmm0, xmm8
0x18001588d  mulsd   xmm0, xmm8
0x180015892  subsd   xmm10, xmm0
0x180015897  comisd  xmm10, xmm9
0x18001589c  movaps  xmm1, xmm10
0x1800158a0  xorps   xmm1, xmm4
0x1800158a3  jb      loc_180016154
0x1800158a9  movaps  xmm3, xmm10
0x1800158ad  comisd  xmm7, xmm9
0x1800158b2  movaps  xmm0, xmm7
0x1800158b5  jb      loc_18001615C
0x1800158bb  movsd   xmm2, cs:__real@3e112e0be826d695
0x1800158c3  mulsd   xmm0, xmm2
0x1800158c7  comisd  xmm3, xmm0
0x1800158cb  jbe     short loc_180015902
0x1800158cd  comisd  xmm10, xmm9
0x1800158d2  mulsd   xmm6, xmm13
0x1800158d7  mulsd   xmm5, xmm8
0x1800158dc  subsd   xmm6, xmm5
0x1800158e0  jb      short loc_1800158E6
0x1800158e2  movaps  xmm1, xmm10
0x1800158e6  comisd  xmm6, xmm9
0x1800158eb  movaps  xmm0, xmm6
0x1800158ee  jb      loc_180016164
0x1800158f4  mulsd   xmm0, xmm2
0x1800158f8  comisd  xmm1, xmm0
0x1800158fc  ja      loc_1800160EB
0x180015902  mov     rax, [rsi+18h]
0x180015906  movsd   xmm7, qword ptr [rax+rdi*8]
0x18001590b  subsd   xmm7, qword ptr [rax+r11*8]
0x180015911  divsd   xmm7, cs:__real@4008000000000000
0x180015919  movaps  xmm6, xmm7
0x18001591c  mov     r14, [rbx+10h]
0x180015920  mov     eax, 10h
0x180015925  mov     r10d, cs:_tls_index
0x18001592c  mov     ecx, 0FFFFFFFFh
0x180015931  unpcklpd xmm6, xmm6
0x180015935  mov     r11, 0FFFFFFFFFFFFFFFh
0x18001593f  mov     [rsp+158h+var_138], rax
0x180015944  lea     rbp, [r14+1]
0x180015948  mov     r9d, 4
0x18001594e  cmp     rbp, [rbx+18h]
0x180015952  jbe     loc_1800159D8
0x180015958  cmp     rbp, 20h ; ' '
0x18001595c  jnb     loc_180016116
0x180015962  cmp     rbp, 2
0x180015966  jb      loc_18001616C
0x18001596c  cmp     rbp, 4
0x180015970  jb      loc_180016035
0x180015976  cmp     rbp, 8
0x18001597a  jb      loc_180016179
0x180015980  cmp     rbp, rax
0x180015983  jnb     loc_180016042
0x180015989  mov     ebp, 0Fh
0x18001598e  mov     r15d, 0F0h
0x180015994  jmp     loc_180016060
0x180015999  mov     rcx, [rbx+8]; void *
0x18001599d  test    rcx, rcx
0x1800159a0  jz      short loc_1800159AF
0x1800159a2  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x1800159a7  mov     qword ptr [rbx+8], 0
0x1800159af  xor     al, al
0x1800159b1  mov     qword ptr [rbx+10h], 0
0x1800159b9  xor     ebp, ebp
0x1800159bb  mov     [rbx+18h], rbp
0x1800159bf  mov     r11, 0FFFFFFFFFFFFFFFh
0x1800159c9  mov     r10d, cs:_tls_index
0x1800159d0  test    al, al
0x1800159d2  jz      loc_1800161EC
0x1800159d8  mov     r8, [rbx+10h]
0x1800159dc  mulsd   xmm11, xmm7
0x1800159e1  mulsd   xmm12, xmm7
0x1800159e6  addsd   xmm11, [rsp+158h+var_100]
0x1800159ed  addsd   xmm12, [rsp+158h+var_128]
0x1800159f4  cmp     r14, r8
0x1800159f7  jb      loc_180016203
0x1800159fd  mov     rcx, [rbx+8]
0x180015a01  shl     r14, 4
0x180015a05  add     rcx, r14
0x180015a08  movsd   qword ptr [rcx], xmm12
0x180015a0d  movsd   qword ptr [rcx+8], xmm11
0x180015a13  mov     r15, [rbx+10h]
0x180015a17  mov     rdx, [rbx+8]
0x180015a1b  inc     r15
0x180015a1e  mov     [rbx+10h], r15
0x180015a22  mov     r14, r15
0x180015a25  mov     r9, rdx
0x180015a28  shl     r14, 4
0x180015a2c  lea     rax, [rdx+r14]
0x180015a30  cmp     rax, rcx
0x180015a33  jz      loc_180015B07
0x180015a39  movups  xmm0, xmmword ptr [r12]
0x180015a3e  mov     rax, [rsi+10h]
0x180015a42  lea     rbp, [r15+1]
0x180015a46  mulpd   xmm6, xmm0
0x180015a4a  movups  xmm0, xmmword ptr [rax+r13]
0x180015a4f  addpd   xmm6, xmm0
0x180015a53  cmp     rbp, [rbx+18h]
0x180015a57  jbe     short loc_180015ABE
0x180015a59  cmp     rbp, 20h ; ' '
0x180015a5d  jnb     loc_18001611F
0x180015a63  cmp     rbp, 2
0x180015a67  jb      loc_180016234
0x180015a6d  cmp     rbp, 4
0x180015a71  jnb     loc_1800160C2
0x180015a77  mov     r8d, 30h ; '0'
0x180015a7d  mov     ebp, 3
0x180015a82  mov     [rsp+158h+var_138], r8
  ... truncated ...
```
