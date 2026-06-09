# FaceFilter::updateFaceDetection(utl::vector<DetectedBox,utl::allocator<DetectedBox>> &,int,int)

- ea: `0x180028580`
- end: `0x180029033`
- name: `?updateFaceDetection@FaceFilter@@QEAAXAEAV?$vector@VDetectedBox@@V?$allocator@VDetectedBox@@@utl@@@utl@@HH@Z`
- size: `2739`
- prototype: `__int64 __fastcall(int *, float **, int, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, installer_update`

## callers

- `0x180026668`

## callees

- `0x1800028cc`
- `0x180003985`
- `0x18001c930`
- `0x18001f3d4`
- `0x18001f928`
- `0x18001fc60`
- `0x18001fd18`
- `0x180023560`
- `0x180025344`
- `0x180027750`
- `0x180027898`
- `0x180027b60`
- `0x180027e34`
- `0x180028108`
- `0x180028580`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800285f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800285f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FaceFilter::updateFaceDetection(int *a1, float **a2, int a3, int a4)
{
  ULONGLONG TickCount64; // rsi
  __int64 v9; // r9
  float v10; // xmm14_4
  float v11; // xmm7_4
  float v12; // xmm13_4
  float v13; // xmm9_4
  float v14; // xmm10_4
  float v15; // xmm8_4
  __int64 v16; // r8
  float *v17; // rdi
  float *v18; // r14
  unsigned __int32 v19; // xmm12_4
  struct DetectedBox *v20; // rbx
  float v21; // xmm0_4
  float v22; // xmm1_4
  float v23; // xmm6_4
  float *v24; // rdx
  bool v25; // cc
  struct DetectedBox *v26; // rdi
  int *v27; // r12
  __int64 v28; // rax
  int *v29; // r14
  float v30; // xmm6_4
  int v31; // r8d
  const struct DetectedBox *i; // rdx
  float v33; // xmm7_4
  __int64 v34; // rdx
  int v35; // r8d
  int v36; // r9d
  float v37; // xmm0_4
  int v38; // eax
  __int64 v39; // rdx
  __int128 v40; // xmm1
  int v41; // ecx
  unsigned __int64 v42; // r8
  DetectedBox *v43; // rdi
  DetectedBox *v44; // rbx
  unsigned __int64 v45; // rax
  unsigned __int64 v46; // rsi
  int v47; // edx
  bool v48; // cl
  bool v49; // al
  __int64 v50; // rax
  __int64 v51; // rcx
  char v52; // al
  unsigned __int64 v53; // rbx
  struct DetectedBox *v54; // r13
  float v55; // xmm6_4
  int v56; // edi
  const struct DetectedBox *v57; // rsi
  float v58; // xmm7_4
  __int64 v59; // rdx
  float v60; // xmm0_4
  int v61; // r11d
  unsigned __int64 v62; // rdx
  void **v63; // rdi
  void **v64; // rax
  __int64 v65; // rcx
  __int64 v66; // rax
  __int64 v67; // rdi
  __int64 v68; // rdx
  __int64 v69; // rcx
  void *v70; // rcx
  float **v71; // rdi
  float *v72; // rcx
  float *v73; // rbx
  float v74; // xmm7_4
  float v75; // xmm8_4
  const struct DetectedBox *v76; // rdx
  DetectedBox *v77; // rcx
  float *v78; // rdx
  float *v79; // rcx
  float v80; // xmm6_4
  float v81; // xmm0_4
  float v82; // xmm6_4
  float v83; // xmm1_4
  float v84; // xmm2_4
  float v85; // xmm5_4
  float v86; // xmm3_4
  const struct DetectedBox *v87; // rcx
  float v88; // xmm0_4
  float *v89; // rbx
  float v90; // xmm5_4
  float v91; // xmm4_4
  float v92; // xmm7_4
  float v93; // xmm6_4
  float v94; // xmm2_4
  float v95; // xmm0_4
  float v96; // xmm3_4
  float v97; // xmm1_4
  float v98; // xmm2_4
  float v99; // xmm4_4
  float v100; // xmm0_4
  float v101; // xmm0_4
  void *v103; // [rsp+28h] [rbp-E0h] BYREF
  void **v104; // [rsp+30h] [rbp-D8h]
  void **v105; // [rsp+38h] [rbp-D0h]
  __int64 v106; // [rsp+40h] [rbp-C8h]
  struct DetectedBox *v107[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v108; // [rsp+58h] [rbp-B0h]
  __m128i si128; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v110; // [rsp+70h] [rbp-98h]
  unsigned __int64 v111; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v112[24]; // [rsp+80h] [rbp-88h] BYREF
  int v113; // [rsp+98h] [rbp-70h]

  if ( *((_BYTE *)a1 + 196) )
  {
    *((_QWORD *)a1 + 12) = *((_QWORD *)a1 + 11);
    return utl::vector<DetectedBox,utl::allocator<DetectedBox>>::assign(a1 + 16, a2);
  }
  TickCount64 = GetTickCount64();
  v10 = (float)a3;
  v11 = (float)a3 * *((float *)a1 + 3);
  v12 = (float)a4;
  v13 = (float)a4 * *((float *)a1 + 4);
  v14 = (float)a3 * *((float *)a1 + 1);
  v15 = (float)a4 * *((float *)a1 + 2);
  *(__m128i *)v107 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v16 = -1;
  v108 = -1;
  v17 = *a2;
  v18 = a2[1];
  v19 = _mm_load_si128((const __m128i *)&_xmm).m128i_u32[0];
  v20 = v107[1];
  while ( v17 != v18 )
  {
    v21 = v17[3];
    if ( v21 < v11 || (v22 = v17[4], v22 < v13) || v14 < v21 || v15 < v22 )
    {
      if ( *((_BYTE *)a1 + 62) && *((_QWORD *)a1 + 11) != *((_QWORD *)a1 + 12) )
      {
        v25 = DetectedBox::GeneralIntersectionOverUnion((DetectedBox *)v17, (const struct DetectedBox *)(a1 + 42)) <= 0.5;
LABEL_15:
        if ( v25 )
          goto LABEL_19;
LABEL_16:
        if ( v20 == (struct DetectedBox *)v16 )
        {
          utl::vector<DetectedBox,utl::allocator<DetectedBox>>::_PushBackOne2<DetectedBox const &>(v107, v17);
          v16 = v108;
          v20 = v107[1];
        }
        else
        {
          *(_OWORD *)v20 = *(_OWORD *)v17;
          *((float *)v20 + 4) = v17[4];
          v20 = (struct DetectedBox *)((char *)v20 + 20);
          v107[1] = v20;
        }
      }
    }
    else
    {
      v23 = *v17;
      if ( *v17 >= (float)a1[5] )
        goto LABEL_16;
      if ( *((_BYTE *)a1 + 28)
        && DetectedBox::GeneralIntersectionOverUnion((DetectedBox *)v17, (const struct DetectedBox *)(a1 + 42)) > 0.5 )
      {
        v25 = COERCE_FLOAT(COERCE_UNSIGNED_INT(*v24 - v23) & v19) <= 0.25;
        goto LABEL_15;
      }
    }
LABEL_19:
    v17 += 5;
  }
  LOBYTE(v9) = 0;
  v26 = v107[0];
  utl::_SortImp_utl::_ArrayIt_DetectedBox____int64__lambda_63882ce32f653aab47f6148cfcdaed0c___(
    v107[0],
    v20,
    0xCCCCCCCCCCCCCCCDuLL * ((v20 - v107[0]) >> 2),
    v9);
  if ( (int)(-858993459 * ((v20 - v26) >> 2)) > *a1 )
  {
    utl::vector<DetectedBox,utl::allocator<DetectedBox>>::_Resize<,0>(v107, *a1);
    v20 = v107[1];
    v26 = v107[0];
  }
  if ( *((_QWORD *)a1 + 20) - *((_QWORD *)a1 + 19) > *((_QWORD *)a1 + 4)
    || (v27 = a1 + 22, *((_QWORD *)a1 + 11) == *((_QWORD *)a1 + 12)) )
  {
    v29 = a1 + 16;
    v28 = *((_QWORD *)a1 + 8);
    *((_QWORD *)a1 + 9) = v28;
    *((_QWORD *)a1 + 19) = TickCount64;
    v27 = a1 + 22;
  }
  else
  {
    v28 = *((_QWORD *)a1 + 8);
    v29 = a1 + 16;
  }
  if ( *((_BYTE *)a1 + 28) )
  {
    v29 = a1 + 16;
    if ( v28 != *((_QWORD *)a1 + 9) )
    {
      v27 = a1 + 22;
      v30 = FLOAT_NInf;
      v31 = -1;
      for ( i = v26; i != v20; i = (const struct DetectedBox *)(v34 + 20) )
      {
        v33 = v30;
        v37 = DetectedBox::GeneralIntersectionOverUnion(*(DetectedBox **)v27, i);
        if ( v37 > v30 )
          v30 = v37;
        v38 = v36;
        if ( v37 <= v33 )
          v38 = v35;
        v31 = v38;
      }
      if ( v31 <= 0 )
      {
        *((_QWORD *)a1 + 19) = TickCount64;
      }
      else
      {
        v39 = 5LL * v31;
        v40 = *(_OWORD *)v26;
        v41 = *((_DWORD *)v26 + 4);
        *(_OWORD *)v26 = *(_OWORD *)((char *)v26 + 20 * v31);
        *((_DWORD *)v26 + 4) = *((_DWORD *)v26 + 5 * v31 + 4);
        *(_OWORD *)((char *)v26 + 4 * v39) = v40;
        *((_DWORD *)v26 + v39 + 4) = v41;
        *((_QWORD *)a1 + 20) = TickCount64;
      }
    }
  }
  *((_QWORD *)a1 + 15) = *((_QWORD *)a1 + 14);
  utl::vector<DetectedBox,utl::allocator<DetectedBox>>::assign(v29, v107);
  v42 = 0xCCCCCCCCCCCCCCCDuLL;
  if ( *((_BYTE *)a1 + 40) )
  {
    v43 = (DetectedBox *)*((_QWORD *)v27 + 1);
    v44 = *(DetectedBox **)v27;
    v45 = 0xCCCCCCCCCCCCCCCDuLL * (((__int64)v43 - *(_QWORD *)v27) >> 2);
    v46 = 0xCCCCCCCCCCCCCCCDuLL * ((v107[1] - v107[0]) >> 2);
    v47 = -858993459 * ((v107[1] - v107[0]) >> 2) - v45;
    v48 = *((float *)a1 + 37) != 0.0 && *((float *)a1 + 36) != 0.0;
    v49 = !v45 && v46;
    if ( v47 == 1 || v49 || v48 )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      v50 = -1;
      v110 = -1;
      v103 = &v103;
      v104 = &v103;
      v105 = &v103;
      v106 = 0;
      v51 = si128.m128i_i64[1];
      while ( v44 != v43 )
      {
        if ( si128.m128i_i64[0] == v51 )
        {
          if ( v51 != v50
            || (v52 = utl::vector<DetectedBox,utl::allocator<DetectedBox>>::_Grow(&si128, si128.m128i_i64[0], v42),
                v51 = si128.m128i_i64[1],
                v52) )
          {
            *(_OWORD *)v51 = *(_OWORD *)v44;
            *(_DWORD *)(v51 + 16) = *((_DWORD *)v44 + 4);
            v51 = si128.m128i_i64[1] + 20;
            si128.m128i_i64[1] += 20;
          }
        }
        else
        {
          *(_OWORD *)&v112[8] = *(_OWORD *)v44;
          v113 = *((_DWORD *)v44 + 4);
          *(_QWORD *)v112 = &si128;
          utl::vector<DetectedBox,utl::allocator<DetectedBox>>::_InsertOne(&si128, si128.m128i_i64[0], &v112[8]);
          v51 = si128.m128i_i64[1];
        }
        v44 = (DetectedBox *)((char *)v44 + 20);
        v50 = v110;
      }
      v111 = 0;
      if ( v46 )
      {
        do
        {
          utl::_Tree<unsigned __int64,unsigned __int64,utl::less<unsigned __int64>,utl::allocator<unsigned __int64>,0>::_InsertImpl<unsigned __int64 const &>(
            &v103,
            v112,
            v42,
            &v111);
          ++v111;
        }
        while ( v111 < v46 );
        v51 = si128.m128i_i64[1];
      }
      v53 = (unsigned __int64)v105;
      v54 = v107[0];
      while ( si128.m128i_i64[0] != v51 )
      {
        v55 = FLOAT_NInf;
        v56 = -1;
        v57 = (const struct DetectedBox *)(v51 - 20);
        while ( (void **)v53 != &v103 )
        {
          v58 = v55;
          v60 = DetectedBox::GeneralIntersectionOverUnion(
                  (struct DetectedBox *)((char *)v54 + 20 * *(_QWORD *)(v53 + 24)),
                  v57);
          if ( v60 > v55 )
            v55 = v60;
          LOBYTE(v59) = 1;
          v53 = utl::_TreeNodeHeader<unsigned __int64>::_Traverse(v53, v59);
          if ( v60 <= v58 )
            v61 = v56;
          v56 = v61;
        }
        v53 = (unsigned __int64)v105;
        if ( v56 > -1 && v105 != &v103 )
        {
          v62 = v56;
          v63 = &v103;
          v64 = (void **)v103;
          do
          {
            if ( (unsigned __int64)v64[3] < v62 )
            {
              v65 = 2;
            }
            else
            {
              v63 = v64;
              v65 = 1;
            }
            v64 = (void **)v64[v65];
          }
          while ( v64 != &utl::_TreeSentinel );
          if ( v63 != &v103 && v62 >= (unsigned __int64)v63[3] )
          {
            utl::_TreeNodeHeader<unsigned __int64>::_HeadUnlinkNode(&v103, v63, &utl::_TreeSentinel);
            --v106;
            operator delete(v63, (const struct std::nothrow_t *)&std::nothrow);
            v53 = (unsigned __int64)v105;
          }
        }
        v51 = si128.m128i_i64[1] - 20;
        si128.m128i_i64[1] -= 20;
      }
      if ( v106 )
      {
        v66 = *(_QWORD *)(v53 + 24);
        v67 = 5 * v66;
        v68 = *(_QWORD *)v29 + 20 * v66;
        if ( *((float *)a1 + 6) > *(float *)v68 )
        {
          if ( *((_QWORD *)v29 + 1) - *(_QWORD *)v29 == 20 )
          {
            v69 = *((_QWORD *)a1 + 15);
            if ( v69 == *((_QWORD *)a1 + 16) )
            {
              utl::vector<DetectedBox,utl::allocator<DetectedBox>>::_PushBackOne2<DetectedBox const &>(a1 + 28, v68);
            }
            else
            {
              *(_OWORD *)v69 = *(_OWORD *)v68;
              *(_DWORD *)(v69 + 16) = *(_DWORD *)(v68 + 16);
              *((_QWORD *)a1 + 15) += 20LL;
            }
          }
          memmove_0(
            (void *)(*(_QWORD *)v29 + 4 * v67),
            (const void *)(*(_QWORD *)v29 + 4 * v67 + 20),
            20 * ((*((_QWORD *)v29 + 1) - (*(_QWORD *)v29 + 4 * v67) - 20) / 20));
          *((_QWORD *)v29 + 1) -= 20LL;
          v53 = (unsigned __int64)v105;
        }
      }
      if ( (void **)v53 != &v103 )
      {
        while ( 1 )
        {
          while ( *(void ***)(v53 + 8) != &utl::_TreeSentinel )
            v53 = *(_QWORD *)(v53 + 8);
LABEL_94:
          if ( *(void ***)(v53 + 16) == &utl::_TreeSentinel )
            break;
          v53 = *(_QWORD *)(v53 + 16);
        }
        while ( 1 )
        {
          v70 = (void *)v53;
          v53 = *(_QWORD *)v53 & 0xFFFFFFFFFFFFFFFEuLL;
          operator delete(v70, (const struct std::nothrow_t *)&std::nothrow);
          if ( (void **)v53 == &v103 )
            break;
          if ( *(void ***)(v53 + 8) != &utl::_TreeSentinel )
          {
            *(_QWORD *)(v53 + 8) = &utl::_TreeSentinel;
            goto LABEL_94;
          }
        }
        v103 = &v103;
        v104 = &v103;
        v105 = &v103;
        v106 = 0;
      }
      utl::vector<DetectedBox,utl::allocator<DetectedBox>>::_Uninit(&si128);
    }
  }
  if ( *((_BYTE *)a1 + 61) && *((_BYTE *)a1 + 28) )
  {
    v71 = (float **)(v29 + 2);
    v72 = (float *)*((_QWORD *)v29 + 1);
    v73 = *(float **)v29;
    if ( 0xCCCCCCCCCCCCCCCDuLL * (((__int64)v72 - *(_QWORD *)v29) >> 2) > 1 )
    {
      v74 = v73[3];
      v75 = v73[4];
LABEL_102:
      v73 += 5;
      while ( v73 != v72 )
      {
        if ( (float)(v74 * 0.30000001) <= v73[3] && (float)(v75 * 0.30000001) <= v73[4] )
          goto LABEL_102;
        memmove_0(v73, v73 + 5, 20 * (((char *)v72 - (char *)v73 - 20) / 20));
        *v71 -= 5;
        v72 = *v71;
      }
    }
  }
  else
  {
    v71 = (float **)(v29 + 2);
  }
  if ( *((_BYTE *)a1 + 28)
    && *((_BYTE *)a1 + 60)
    && *(float **)v29 != *v71
    && DetectedBox::IntersectArea((DetectedBox *)(a1 + 42), *(const struct DetectedBox **)v29) != 0.0 )
  {
    v80 = DetectedBox::GeneralIntersectionOverUnion(v77, v76);
    v81 = *((float *)a1 + 48);
    if ( v80 < v81 )
    {
      v83 = *((float *)a1 + 47);
      if ( v80 < v83 )
        v82 = 0.0;
      else
        v82 = (float)(v80 - v83) / (float)(v81 - v83);
    }
    else
    {
      v82 = FLOAT_1_0;
    }
    v84 = v78[1];
    v85 = v78[2];
    v86 = (float)(v82 * *((float *)a1 + 44)) + (float)((float)(1.0 - v82) * v85);
    *(float *)&v112[4] = (float)(v82 * *((float *)a1 + 43)) + (float)((float)(1.0 - v82) * v84);
    *(float *)&v112[8] = v86;
    *(float *)&v112[12] = (float)((float)((float)(v79[3] + v79[1]) * v82)
                                + (float)((float)(v84 + v78[3]) * (float)(1.0 - v82)))
                        - *(float *)&v112[4];
    *(float *)&v112[16] = (float)((float)((float)(v79[4] + v79[2]) * v82)
                                + (float)((float)(v85 + v78[4]) * (float)(1.0 - v82)))
                        - v86;
    *(_OWORD *)(v78 + 1) = *(_OWORD *)&v112[4];
  }
  v87 = *(const struct DetectedBox **)v29;
  if ( *(float **)v29 != *v71 && *((_BYTE *)a1 + 28) )
  {
    *(_OWORD *)(a1 + 42) = *(_OWORD *)v87;
    a1[46] = *((_DWORD *)v87 + 4);
    v88 = *(float *)v87;
    if ( *(float *)v87 <= (float)a1[5] )
      v88 = (float)a1[5];
    *((float *)a1 + 42) = v88;
  }
  utl::vector<DetectedBox,utl::allocator<DetectedBox>>::assign(v27, v107);
  v89 = *(float **)v29;
  while ( v89 != *v71 )
  {
    v90 = v89[1];
    v91 = v90 + v89[3];
    v92 = v89[2];
    v93 = v92 + v89[4];
    v94 = v10 - 1.0;
    if ( *((_BYTE *)a1 + 41) )
    {
      v95 = v93 - v92;
      v96 = fmaxf((float)((float)(v91 - v90) * *((float *)a1 + 11)) + v90, 0.0);
      if ( v94 <= v96 )
        v96 = v10 - 1.0;
      v97 = fmaxf((float)((float)(v91 - v90) * *((float *)a1 + 12)) + v91, 0.0);
      if ( v94 <= v97 )
        v97 = v10 - 1.0;
      v98 = fmaxf((float)(v95 * *((float *)a1 + 13)) + v92, 0.0);
      v99 = v12 - 1.0;
      if ( (float)(v12 - 1.0) <= v98 )
        v98 = v12 - 1.0;
      v100 = (float)(v95 * *((float *)a1 + 14)) + v93;
    }
    else
    {
      v96 = fmaxf(v90, 0.0);
      if ( v94 <= v96 )
        v96 = v10 - 1.0;
      v97 = fmaxf(v91, 0.0);
      if ( v94 <= v97 )
        v97 = v10 - 1.0;
      v98 = fmaxf(v92, 0.0);
      v99 = v12 - 1.0;
      if ( (float)(v12 - 1.0) <= v98 )
        v98 = v12 - 1.0;
      v100 = v89[2] + v89[4];
    }
    v101 = fmaxf(v100, 0.0);
    if ( v99 <= v101 )
      v101 = v99;
    if ( v97 <= v96 || v101 <= v98 )
    {
      memmove_0(v89, v89 + 5, 20 * (((char *)*v71 - (char *)v89 - 20) / 20));
      *v71 -= 5;
    }
    else
    {
      v89[1] = v96;
      v89[2] = v98;
      v89[3] = v97 - v96;
      v89[4] = v101 - v98;
      v89 += 5;
    }
  }
  return utl::vector<DetectedBox,utl::allocator<DetectedBox>>::_Uninit(v107);
}

```

## disassembly

```asm
0x180028580  mov     rax, rsp
0x180028583  mov     [rax+18h], rbx
0x180028587  push    rbp
0x180028588  push    rsi
0x180028589  push    rdi
0x18002858a  push    r12
0x18002858c  push    r13
0x18002858e  push    r14
0x180028590  push    r15
0x180028592  lea     rbp, [rax-68h]
0x180028596  sub     rsp, 130h
0x18002859d  movaps  xmmword ptr [rax-48h], xmm6
0x1800285a1  movaps  xmmword ptr [rax-58h], xmm7
0x1800285a5  movaps  xmmword ptr [rax-68h], xmm8
0x1800285aa  movaps  xmmword ptr [rax-78h], xmm9
0x1800285af  movaps  xmmword ptr [rax-88h], xmm10
0x1800285b7  movaps  xmmword ptr [rax-98h], xmm11
0x1800285bf  movaps  xmmword ptr [rax-0A8h], xmm12
0x1800285c7  movaps  xmmword ptr [rax-0B8h], xmm13
0x1800285cf  movaps  xmmword ptr [rax-0C8h], xmm14
0x1800285d7  mov     edi, r9d
0x1800285da  mov     r14d, r8d
0x1800285dd  mov     rbx, rdx
0x1800285e0  mov     r15, rcx
0x1800285e3  xor     r13d, r13d
0x1800285e6  cmp     [rcx+0C4h], r13b
0x1800285ed  jnz     loc_180028FD7
0x1800285f3  call    cs:__imp_GetTickCount64
0x1800285f9  mov     rsi, rax
0x1800285fc  movd    xmm14, r14d
0x180028601  cvtdq2ps xmm14, xmm14
0x180028605  movaps  xmm7, xmm14
0x180028609  mulss   xmm7, dword ptr [r15+0Ch]
0x18002860f  movd    xmm13, edi
0x180028614  cvtdq2ps xmm13, xmm13
0x180028618  movaps  xmm9, xmm13
0x18002861c  mulss   xmm9, dword ptr [r15+10h]
0x180028622  movaps  xmm10, xmm14
0x180028626  mulss   xmm10, dword ptr [r15+4]
0x18002862c  movaps  xmm8, xmm13
0x180028630  mulss   xmm8, dword ptr [r15+8]
0x180028636  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18002863e  movdqu  xmmword ptr [rsp+160h+var_128+8], xmm0
0x180028644  or      r8, 0FFFFFFFFFFFFFFFFh
0x180028648  mov     qword ptr [rsp+160h+var_110], r8
0x18002864d  mov     rdi, [rbx]
0x180028650  mov     r14, [rbx+8]
0x180028654  movdqa  xmm12, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x18002865d  movss   xmm11, cs:__real@3f000000
0x180028666  mov     rbx, [rsp+160h+var_118]
0x18002866b  cmp     rdi, r14
0x18002866e  jz      loc_18002873C
0x180028674  movss   xmm0, dword ptr [rdi+0Ch]
0x180028679  comiss  xmm0, xmm7
0x18002867c  jb      short loc_1800286DB
0x18002867e  movss   xmm1, dword ptr [rdi+10h]
0x180028683  comiss  xmm1, xmm9
0x180028687  jb      short loc_1800286DB
0x180028689  comiss  xmm10, xmm0
0x18002868d  jb      short loc_1800286DB
0x18002868f  comiss  xmm8, xmm1
0x180028693  jb      short loc_1800286DB
0x180028695  movss   xmm6, dword ptr [rdi]
0x180028699  movd    xmm0, dword ptr [r15+14h]
0x18002869f  cvtdq2ps xmm0, xmm0
0x1800286a2  comiss  xmm6, xmm0
0x1800286a5  jnb     short loc_180028700
0x1800286a7  cmp     [r15+1Ch], r13b
0x1800286ab  jz      loc_180028733
0x1800286b1  lea     rdx, [r15+0A8h]; struct DetectedBox *
0x1800286b8  mov     rcx, rdi; this
0x1800286bb  call    ?GeneralIntersectionOverUnion@DetectedBox@@QEBAMAEBV1@@Z; DetectedBox::GeneralIntersectionOverUnion(DetectedBox const &)
0x1800286c0  comiss  xmm0, xmm11
0x1800286c4  jbe     short loc_180028733
0x1800286c6  movss   xmm0, dword ptr [rdx]
0x1800286ca  subss   xmm0, xmm6
0x1800286ce  andps   xmm0, xmm12
0x1800286d2  comiss  xmm0, cs:__real@3e800000
0x1800286d9  jmp     short loc_1800286FE
0x1800286db  cmp     [r15+3Eh], r13b
0x1800286df  jz      short loc_180028733
0x1800286e1  mov     rax, [r15+60h]
0x1800286e5  cmp     [r15+58h], rax
0x1800286e9  jz      short loc_180028733
0x1800286eb  lea     rdx, [r15+0A8h]; struct DetectedBox *
0x1800286f2  mov     rcx, rdi; this
0x1800286f5  call    ?GeneralIntersectionOverUnion@DetectedBox@@QEBAMAEBV1@@Z; DetectedBox::GeneralIntersectionOverUnion(DetectedBox const &)
0x1800286fa  comiss  xmm0, xmm11
0x1800286fe  jbe     short loc_180028733
0x180028700  cmp     rbx, r8
0x180028703  jz      short loc_18002871C
0x180028705  movups  xmm0, xmmword ptr [rdi]
0x180028708  movups  xmmword ptr [rbx], xmm0
0x18002870b  mov     eax, [rdi+10h]
0x18002870e  mov     [rbx+10h], eax
0x180028711  add     rbx, 14h
0x180028715  mov     [rsp+160h+var_118], rbx
0x18002871a  jmp     short loc_180028733
0x18002871c  mov     rdx, rdi
0x18002871f  lea     rcx, [rsp+160h+var_128+8]
0x180028724  call    ??$_PushBackOne2@AEBVDetectedBox@@@?$vector@VDetectedBox@@V?$allocator@VDetectedBox@@@utl@@@utl@@AEAA_NAEBVDetectedBox@@@Z; utl::vector<DetectedBox,utl::allocator<DetectedBox>>::_PushBackOne2<DetectedBox const &>(DetectedBox const &)
0x180028729  mov     r8, qword ptr [rsp+160h+var_110]
0x18002872e  mov     rbx, [rsp+160h+var_118]
0x180028733  add     rdi, 14h
0x180028737  jmp     loc_18002866B
0x18002873c  mov     r9b, r13b
0x18002873f  mov     rdi, [rsp+160h+var_128+8]
0x180028744  mov     r8, rbx
0x180028747  sub     r8, rdi
0x18002874a  sar     r8, 2
0x18002874e  mov     r14, 0CCCCCCCCCCCCCCCDh
0x180028758  imul    r8, r14
0x18002875c  mov     rdx, rbx
0x18002875f  mov     rcx, rdi
0x180028762  call    utl___SortImp_utl___ArrayIt_DetectedBox____int64__lambda_63882ce32f653aab47f6148cfcdaed0c___
0x180028767  mov     rax, rbx
0x18002876a  sub     rax, rdi
0x18002876d  sar     rax, 2
0x180028771  imul    rax, r14
0x180028775  cmp     eax, [r15]
0x180028778  jle     short loc_180028791
0x18002877a  movsxd  rdx, dword ptr [r15]
0x18002877d  lea     rcx, [rsp+160h+var_128+8]
0x180028782  call    ??$_Resize@$$V$0A@@?$vector@VDetectedBox@@V?$allocator@VDetectedBox@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<DetectedBox,utl::allocator<DetectedBox>>::_Resize<,0>(unsigned __int64)
0x180028787  mov     rbx, [rsp+160h+var_118]
0x18002878c  mov     rdi, [rsp+160h+var_128+8]
0x180028791  mov     rax, [r15+0A0h]
0x180028798  sub     rax, [r15+98h]
0x18002879f  cmp     rax, [r15+20h]
0x1800287a3  jg      short loc_1800287BE
0x1800287a5  lea     r12, [r15+58h]
0x1800287a9  mov     rax, [r12+8]
0x1800287ae  cmp     [r12], rax
0x1800287b2  jz      short loc_1800287BE
0x1800287b4  mov     rax, [r15+40h]
0x1800287b8  lea     r14, [r15+40h]
0x1800287bc  jmp     short loc_1800287D4
0x1800287be  lea     r14, [r15+40h]
0x1800287c2  mov     rax, [r14]
0x1800287c5  mov     [r14+8], rax
0x1800287c9  mov     [r15+98h], rsi
0x1800287d0  lea     r12, [r15+58h]
0x1800287d4  movss   xmm8, cs:__real@ff800000
0x1800287dd  cmp     [r15+1Ch], r13b
0x1800287e1  jz      loc_18002886A
0x1800287e7  lea     r14, [r15+40h]
0x1800287eb  cmp     rax, [r14+8]
0x1800287ef  jz      short loc_18002886A
0x1800287f1  lea     r12, [r15+58h]
0x1800287f5  movaps  xmm6, xmm8
0x1800287f9  or      r8d, 0FFFFFFFFh
0x1800287fd  mov     r9d, r13d
0x180028800  mov     rdx, rdi; struct DetectedBox *
0x180028803  cmp     rdx, rbx
0x180028806  jz      short loc_180028832
0x180028808  movaps  xmm7, xmm6
0x18002880b  mov     rcx, [r12]; this
0x18002880f  call    ?GeneralIntersectionOverUnion@DetectedBox@@QEBAMAEBV1@@Z; DetectedBox::GeneralIntersectionOverUnion(DetectedBox const &)
0x180028814  comiss  xmm0, xmm6
0x180028817  jbe     short loc_18002881C
0x180028819  movaps  xmm6, xmm0
0x18002881c  mov     eax, r9d
0x18002881f  comiss  xmm0, xmm7
0x180028822  cmovbe  eax, r8d
0x180028826  mov     r8d, eax
0x180028829  inc     r9d
0x18002882c  add     rdx, 14h
0x180028830  jmp     short loc_180028803
0x180028832  test    r8d, r8d
0x180028835  jle     short loc_180028863
0x180028837  movsxd  rax, r8d
0x18002883a  lea     rdx, [rax+rax*4]
0x18002883e  movups  xmm1, xmmword ptr [rdi]
0x180028841  mov     ecx, [rdi+10h]
0x180028844  movups  xmm0, xmmword ptr [rdi+rdx*4]
0x180028848  movups  xmmword ptr [rdi], xmm0
0x18002884b  mov     eax, [rdi+rdx*4+10h]
0x18002884f  mov     [rdi+10h], eax
0x180028852  movups  xmmword ptr [rdi+rdx*4], xmm1
0x180028856  mov     [rdi+rdx*4+10h], ecx
0x18002885a  mov     [r15+0A0h], rsi
0x180028861  jmp     short loc_18002886A
0x180028863  mov     [r15+98h], rsi
0x18002886a  mov     rax, [r15+70h]
0x18002886e  mov     [r15+78h], rax
0x180028872  lea     rdx, [rsp+160h+var_128+8]
0x180028877  mov     rcx, r14
0x18002887a  call    ?assign@?$vector@VDetectedBox@@V?$allocator@VDetectedBox@@@utl@@@utl@@QEAA_NAEBV12@@Z; utl::vector<DetectedBox,utl::allocator<DetectedBox>>::assign(utl::vector<DetectedBox,utl::allocator<DetectedBox>> const &)
0x18002887f  mov     rsi, 6666666666666667h
0x180028889  xorps   xmm9, xmm9
0x18002888d  mov     r8, 0CCCCCCCCCCCCCCCDh
0x180028897  cmp     byte ptr [r15+28h], 0
0x18002889c  jz      loc_180028C62
0x1800288a2  mov     rdi, [r12+8]
0x1800288a7  mov     rbx, [r12]
0x1800288ab  mov     rax, rdi
0x1800288ae  sub     rax, rbx
0x1800288b1  sar     rax, 2
0x1800288b5  imul    rax, r8
0x1800288b9  mov     rsi, [rsp+160h+var_118]
0x1800288be  sub     rsi, [rsp+160h+var_128+8]
0x1800288c3  sar     rsi, 2
0x1800288c7  imul    rsi, r8
0x1800288cb  mov     edx, esi
0x1800288cd  sub     edx, eax
0x1800288cf  movss   xmm0, dword ptr [r15+94h]
0x1800288d8  ucomiss xmm0, xmm9
0x1800288dc  jp      short loc_1800288E0
0x1800288de  jz      short loc_1800288F1
0x1800288e0  movss   xmm0, dword ptr [r15+90h]
0x1800288e9  ucomiss xmm0, xmm9
0x1800288ed  jp      short loc_1800288F5
0x1800288ef  jnz     short loc_1800288F5
0x1800288f1  xor     cl, cl
0x1800288f3  jmp     short loc_1800288F7
0x1800288f5  mov     cl, 1
0x1800288f7  test    rax, rax
0x1800288fa  jnz     short loc_180028905
0x1800288fc  test    rsi, rsi
0x1800288ff  jz      short loc_180028905
0x180028901  mov     al, 1
0x180028903  jmp     short loc_180028907
0x180028905  xor     al, al
0x180028907  cmp     edx, 1
0x18002890a  jz      short loc_180028918
0x18002890c  test    al, al
0x18002890e  jnz     short loc_180028918
0x180028910  test    cl, cl
0x180028912  jz      loc_180028C58
0x180028918  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180028920  movdqu  [rsp+160h+var_110+8], xmm0
0x180028926  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002892a  mov     [rsp+160h+var_F8], rax
0x18002892f  lea     rcx, [rsp+160h+var_140]
0x180028934  mov     [rsp+160h+var_140], rcx
0x180028939  lea     rcx, [rsp+160h+var_140]
0x18002893e  mov     [rsp+160h+var_138], rcx
0x180028943  mov     [rsp+160h+var_130], rcx
0x180028948  mov     [rsp+160h+var_128], 0
0x180028951  mov     rcx, [rsp+160h+var_100]
0x180028956  cmp     rbx, rdi
0x180028959  jz      short loc_1800289CE
0x18002895b  mov     rdx, qword ptr [rsp+160h+var_110+8]
0x180028960  cmp     rdx, rcx
0x180028963  jnz     short loc_180028999
0x180028965  cmp     rcx, rax
0x180028968  jnz     short loc_18002897D
0x18002896a  lea     rcx, [rsp+160h+var_110+8]
0x18002896f  call    ?_Grow@?$vector@VDetectedBox@@V?$allocator@VDetectedBox@@@utl@@@utl@@AEAA_NXZ; utl::vector<DetectedBox,utl::allocator<DetectedBox>>::_Grow(void)
0x180028974  mov     rcx, [rsp+160h+var_100]
0x180028979  test    al, al
0x18002897b  jz      short loc_1800289C3
0x18002897d  movups  xmm0, xmmword ptr [rbx]
0x180028980  movups  xmmword ptr [rcx], xmm0
0x180028983  mov     eax, [rbx+10h]
0x180028986  mov     [rcx+10h], eax
0x180028989  mov     rcx, [rsp+160h+var_100]
0x18002898e  add     rcx, 14h
0x180028992  mov     [rsp+160h+var_100], rcx
0x180028997  jmp     short loc_1800289C3
0x180028999  movups  xmm0, xmmword ptr [rbx]
0x18002899c  movups  [rbp+60h+var_E0], xmm0
0x1800289a0  mov     eax, [rbx+10h]
0x1800289a3  mov     [rbp+60h+var_D0], eax
0x1800289a6  lea     rax, [rsp+160h+var_110+8]
0x1800289ab  mov     qword ptr [rsp+160h+var_F0+8], rax
0x1800289b0  lea     r8, [rbp+60h+var_E0]
0x1800289b4  lea     rcx, [rsp+160h+var_110+8]
0x1800289b9  call    ?_InsertOne@?$vector@VDetectedBox@@V?$allocator@VDetectedBox@@@utl@@@utl@@AEAAPEAVDetectedBox@@PEAV3@$$QEAV3@@Z; utl::vector<DetectedBox,utl::allocator<DetectedBox>>::_InsertOne(DetectedBox *,DetectedBox &&)
0x1800289be  mov     rcx, [rsp+160h+var_100]
0x1800289c3  add     rbx, 14h
0x1800289c7  mov     rax, [rsp+160h+var_F8]
0x1800289cc  jmp     short loc_180028956
0x1800289ce  mov     qword ptr [rsp+160h+var_F0], 0
0x1800289d7  test    rsi, rsi
0x1800289da  jz      short loc_180028A07
0x1800289dc  lea     r9, [rsp+160h+var_F0]
0x1800289e1  lea     rdx, [rsp+160h+var_F0+8]
0x1800289e6  lea     rcx, [rsp+160h+var_140]
0x1800289eb  call    ??$_InsertImpl@AEB_K@?$_Tree@_K_KU?$less@_K@utl@@V?$allocator@_K@2@$0A@@utl@@AEAA?AU?$pair@V?$_TreeConstIt@_K@utl@@_N@1@PEAU?$_TreeNode@_K@1@AEB_K@Z; utl::_Tree<unsigned __int64,unsigned __int64,utl::less<unsigned __int64>,utl::allocator<unsigned __int64>,0>::_InsertImpl<unsigned __int64 const &>(utl::_TreeNode<unsigned __int64> *,unsigned __int64 const &)
0x1800289f0  mov     rax, qword ptr [rsp+160h+var_F0]
0x1800289f5  inc     rax
0x1800289f8  mov     qword ptr [rsp+160h+var_F0], rax
0x1800289fd  cmp     rax, rsi
0x180028a00  jb      short loc_1800289DC
0x180028a02  mov     rcx, [rsp+160h+var_100]
0x180028a07  lea     r8, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x180028a0e  mov     rbx, [rsp+160h+var_130]
0x180028a13  mov     r13, [rsp+160h+var_128+8]
0x180028a18  cmp     qword ptr [rsp+160h+var_110+8], rcx
0x180028a1d  jz      loc_180028B0D
0x180028a23  movaps  xmm6, xmm8
0x180028a27  or      edi, 0FFFFFFFFh
0x180028a2a  lea     rsi, [rcx-14h]
0x180028a2e  lea     rax, [rsp+160h+var_140]
0x180028a33  cmp     rbx, rax
0x180028a36  jz      short loc_180028A77
0x180028a38  movaps  xmm7, xmm6
0x180028a3b  mov     r11, [rbx+18h]
0x180028a3f  lea     rax, [r11+r11*4]
  ... truncated ...
```
