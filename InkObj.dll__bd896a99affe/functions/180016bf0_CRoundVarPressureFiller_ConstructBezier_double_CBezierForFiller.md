# CRoundVarPressureFiller::ConstructBezier(double,CBezierForFiller &)

- ea: `0x180016bf0`
- end: `0x180017585`
- name: `?ConstructBezier@CRoundVarPressureFiller@@MEAA_NNAEAVCBezierForFiller@@@Z`
- size: `2453`
- prototype: `bool __fastcall(CRoundVarPressureFiller *__hidden this, double, struct CBezierForFiller *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180002740`
- `0x180016bf0`
- `0x1800176f0`
- `0x18002689c`
- `0x18002704c`
- `0x18004451c`
- `0x1800445e8`
- `0x180044658`
- `0x1800446dc`
- `0x180044ab0`
- `0x180104ee6`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016c9f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016d8e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016de7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016c9f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016d8e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016de7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017124`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017124`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800172cb`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18001732d`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18001738f`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180017551`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800172cb`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18001732d`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18001738f`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180017551`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall CRoundVarPressureFiller::ConstructBezier(
        CRoundVarPressureFiller *this,
        double a2,
        struct CBezierForFiller *a3)
{
  void *v5; // rcx
  unsigned __int64 v6; // rcx
  SIZE_T v7; // rdi
  double *v8; // rcx
  int v9; // r14d
  int v10; // r9d
  int v11; // r8d
  __int64 v12; // rdx
  float *v13; // r13
  unsigned __int64 v14; // r9
  int v15; // edi
  int v16; // r12d
  unsigned __int64 v17; // r15
  SIZE_T v18; // rsi
  void *v19; // rax
  __int64 v20; // rsi
  bool v21; // cf
  SIZE_T v22; // rsi
  _QWORD *v23; // rax
  void *v24; // rsi
  double *v25; // rax
  int v26; // r12d
  int v27; // r9d
  int v28; // edx
  int v29; // ecx
  __int64 v30; // rcx
  char *v31; // rax
  __int64 v32; // r8
  __int64 v33; // rax
  double v34; // xmm0_8
  __m128d v35; // xmm1
  double v36; // xmm0_8
  int v37; // ecx
  int v38; // r8d
  double v39; // xmm3_8
  double v40; // xmm4_8
  double v41; // xmm6_8
  double v42; // xmm5_8
  int v43; // ecx
  __int64 v44; // rax
  double v45; // xmm1_8
  double v46; // xmm0_8
  double v47; // xmm2_8
  double v48; // xmm6_8
  double v49; // xmm5_8
  double v50; // xmm5_8
  double v51; // xmm0_8
  double v52; // xmm1_8
  int AllCusps; // eax
  struct CBezierForFiller *v54; // rbx
  unsigned int v55; // edx
  char v56; // di
  void *v57; // rbx
  int v59; // ecx
  float v60; // xmm2_4
  unsigned int v61; // edx
  float v62; // xmm3_4
  double v63; // xmm1_8
  __int64 v64; // [rsp+48h] [rbp-69h] BYREF
  int v65; // [rsp+50h] [rbp-61h]
  LPVOID lpMem[2]; // [rsp+58h] [rbp-59h]
  double v67; // [rsp+68h] [rbp-49h]
  void *v68; // [rsp+70h] [rbp-41h]
  __int128 v69; // [rsp+78h] [rbp-39h]
  __m128i si128; // [rsp+88h] [rbp-29h]
  double v71; // [rsp+98h] [rbp-19h]
  _QWORD *pExceptionObject; // [rsp+118h] [rbp+67h] BYREF
  struct CBezierForFiller *v73; // [rsp+128h] [rbp+77h]
  __int64 v74; // [rsp+130h] [rbp+7Fh]

  v73 = a3;
  if ( *((_DWORD *)this + 4) < 2u )
    return 0;
  v5 = (void *)*((_QWORD *)this + 24);
  if ( v5 )
  {
    WinFree(v5);
    *((_QWORD *)this + 24) = 0;
  }
  v6 = *((int *)this + 4);
  v7 = 8 * v6;
  if ( !is_mul_ok(v6, 8u) )
    v7 = -1;
  v74 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA > *(_DWORD *)(v74 + 4) )
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
  }
  if ( !`WinHeap::GetDefault'::`2'::s_WinHeap )
  {
    *((_QWORD *)this + 24) = 0;
LABEL_67:
    LODWORD(pExceptionObject) = -2147024882;
    throw (long *)&pExceptionObject;
  }
  v8 = (double *)HeapAlloc(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, v7);
  *((_QWORD *)this + 24) = v8;
  if ( !v8 )
    goto LABEL_67;
  v9 = **((_DWORD **)this + 3);
  *((_DWORD *)this + 16) = v9;
  v10 = **((_DWORD **)this + 4);
  *((_DWORD *)this + 17) = v10;
  v11 = **((_DWORD **)this + 20);
  *((_DWORD *)this + 46) = v11;
  v12 = *((_QWORD *)this + 1);
  if ( *(_QWORD *)v12 )
  {
    v13 = (float *)(*(_QWORD *)v12 + 16LL);
    if ( *(_QWORD *)v12 != -16 )
    {
      v60 = (float)v9;
      v9 = (int)(float)((float)((float)((float)v10 * *(float *)(*(_QWORD *)v12 + 24LL))
                              + (float)((float)v9 * *(float *)(*(_QWORD *)v12 + 16LL)))
                      + *(float *)(*(_QWORD *)v12 + 32LL));
      *((_DWORD *)this + 17) = (int)(float)((float)((float)((float)v10 * *(float *)(*(_QWORD *)v12 + 28LL))
                                                  + (float)(v60 * *(float *)(*(_QWORD *)v12 + 20LL)))
                                          + *(float *)(*(_QWORD *)v12 + 36LL));
      *((_DWORD *)this + 16) = v9;
    }
  }
  else
  {
    v13 = 0;
  }
  v14 = *((int *)this + 4);
  v64 = v12;
  v65 = 0;
  *(_OWORD *)lpMem = 0;
  v67 = 0.0;
  v68 = 0;
  v69 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v71 = DOUBLE_4_0;
  v15 = 1;
  if ( (int)v14 >= 1 )
  {
    v16 = *((_DWORD *)this + 17);
    v17 = v14;
    v18 = 8 * v14;
    if ( !is_mul_ok(v14, 8u) )
      v18 = -1;
    if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA > *(_DWORD *)(v74 + 4) )
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
    }
    if ( `WinHeap::GetDefault'::`2'::s_WinHeap )
      v19 = HeapAlloc(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, v18);
    else
      v19 = 0;
    lpMem[1] = v19;
    v20 = 32 * v17;
    if ( !is_mul_ok(v17, 0x20u) )
      v20 = -1;
    v21 = __CFADD__(v20, 8);
    v22 = v20 + 8;
    if ( v21 )
      v22 = -1;
    if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA > *(_DWORD *)(v74 + 4) )
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
    }
    if ( `WinHeap::GetDefault'::`2'::s_WinHeap )
      v23 = HeapAlloc(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, v22);
    else
      v23 = 0;
    pExceptionObject = v23;
    if ( v23 )
    {
      *v23 = v17;
      v24 = v23 + 1;
      `eh vector constructor iterator'(
        v23 + 1,
        0x20u,
        v17,
        (void (*)(void *))CData::CDataPoint::CDataPoint,
        wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy);
    }
    else
    {
      v24 = 0;
    }
    lpMem[0] = v24;
    if ( !v24 || !lpMem[1] )
    {
      WinFree(lpMem[1]);
      if ( lpMem[0] )
        CData::CDataPoint::`vector deleting destructor'((CData::CDataPoint *)lpMem[0], v61);
      lpMem[1] = 0;
      lpMem[0] = 0;
      LODWORD(pExceptionObject) = -2147024882;
      throw (long *)&pExceptionObject;
    }
    *(_QWORD *)lpMem[1] = 0;
    v25 = (double *)lpMem[0];
    *(double *)lpMem[0] = (double)v9;
    v25[1] = (double)v16;
    *((_DWORD *)lpMem[0] + 4) = 0;
    v65 = 1;
    v11 = *((_DWORD *)this + 46);
    v8 = (double *)*((_QWORD *)this + 24);
  }
  *v8 = ((double)v11 + *((double *)this + 21)) * *((double *)this + 22);
  *((_DWORD *)this + 50) = 1;
  v26 = *((_DWORD *)this + 16);
  v27 = *((_DWORD *)this + 17);
  if ( *((int *)this + 4) > 1 )
  {
    do
    {
      v28 = *(_DWORD *)(*((_QWORD *)this + 3) + 4LL * v15);
      *((_DWORD *)this + 16) = v28;
      v29 = *(_DWORD *)(*((_QWORD *)this + 4) + 4LL * v15);
      *((_DWORD *)this + 17) = v29;
      if ( v13 )
      {
        v62 = (float)v28;
        v28 = (int)(float)((float)((float)((float)v29 * v13[2]) + (float)((float)v28 * *v13)) + v13[4]);
        *((_DWORD *)this + 17) = (int)(float)((float)((float)(v62 * v13[1]) + (float)((float)v29 * v13[3])) + v13[5]);
        *((_DWORD *)this + 16) = v28;
      }
      if ( v26 == v28 && v27 == *((_DWORD *)this + 17) )
      {
        v59 = *(_DWORD *)(*((_QWORD *)this + 20) + 4LL * v15);
        if ( v59 > *((_DWORD *)this + 46) )
        {
          *((_DWORD *)this + 46) = v59;
          *(double *)(*((_QWORD *)this + 24) + 8LL * *((int *)this + 50) - 8) = ((double)v59 + *((double *)this + 21))
                                                                              * *((double *)this + 22);
        }
      }
      else
      {
        v26 = v28;
        LODWORD(pExceptionObject) = *((_DWORD *)this + 17);
        v27 = (int)pExceptionObject;
        v30 = 32LL * v65;
        v31 = (char *)lpMem[0];
        *(double *)((char *)lpMem[0] + v30) = (double)v28;
        *(double *)&v31[v30 + 8] = (double)v27;
        v32 = 32LL * (v65 - 1);
        v33 = 32LL * v65;
        v34 = *(double *)((char *)lpMem[0] + v33 + 8) - *(double *)((char *)lpMem[0] + v32 + 8);
        v35 = (__m128d)*(unsigned __int64 *)((char *)lpMem[0] + v33);
        v35.m128d_f64[0] = (v35.m128d_f64[0] - *(double *)((char *)lpMem[0] + v32))
                         * (v35.m128d_f64[0] - *(double *)((char *)lpMem[0] + v32))
                         + v34 * v34;
        if ( v35.m128d_f64[0] < 0.0 )
        {
          v36 = sqrt_0(v35.m128d_f64[0]);
          v27 = (int)pExceptionObject;
        }
        else
        {
          *(_QWORD *)&v36 = *(_OWORD *)&_mm_sqrt_pd(v35);
        }
        *((double *)lpMem[1] + v65) = v36 + *((double *)lpMem[1] + v65 - 1);
        *((_DWORD *)lpMem[0] + 8 * v65 + 4) = v65;
        ++v65;
        v37 = *(_DWORD *)(*((_QWORD *)this + 20) + 4LL * v15);
        *((_DWORD *)this + 46) = v37;
        *(double *)(*((_QWORD *)this + 24) + 8LL * (int)(*((_DWORD *)this + 50))++) = ((double)v37
                                                                                     + *((double *)this + 21))
                                                                                    * *((double *)this + 22);
      }
      ++v15;
    }
    while ( v15 < *((_DWORD *)this + 4) );
  }
  v38 = v65;
  if ( v65 < 2 )
  {
    CData::~CData((CData *)&v64);
    return 0;
  }
  *((_QWORD *)this + 11) = **((_QWORD **)this + 24);
  v39 = *(double *)lpMem[0];
  v40 = *((double *)lpMem[0] + 1);
  v41 = *(double *)lpMem[0];
  v42 = v40;
  v43 = 0;
  do
  {
    v44 = 32LL * v43;
    v39 = fmin(*(double *)((char *)lpMem[0] + v44), v39);
    v45 = fmax(*(double *)((char *)lpMem[0] + v44), v41);
    v41 = v45;
    v46 = fmin(*(double *)((char *)lpMem[0] + v44 + 8), v40);
    v40 = v46;
    v47 = fmax(*(double *)((char *)lpMem[0] + v44 + 8), v42);
    v42 = v47;
    ++v43;
  }
  while ( v43 < v38 );
  v48 = v45 - v39;
  v49 = v47 - v46;
  if ( v45 - v39 < 0.0 )
    *(_QWORD *)&v48 ^= _xmm;
  if ( v49 < 0.0 )
    *(_QWORD *)&v49 ^= _xmm;
  v50 = v49 + v48;
  v67 = v50;
  v51 = a2;
  if ( a2 < 0.0 )
    *(_QWORD *)&v51 = *(_QWORD *)&a2 ^ _xmm;
  if ( v51 <= 0.000000001 )
  {
    if ( v50 <= 0.0 )
    {
      v52 = *(double *)si128.m128i_i64;
    }
    else
    {
      v63 = *((double *)lpMem[1] + v38 - 1);
      v52 = v63 * v63 * 0.75 / ((double)v38 * v50);
      *(double *)si128.m128i_i64 = v52;
    }
  }
  else
  {
    v52 = a2;
    *(double *)si128.m128i_i64 = a2;
  }
  if ( v52 < 1.0 )
    *(double *)si128.m128i_i64 = DOUBLE_1_0;
  AllCusps = CData::FindAllCusps((CData *)&v64);
  if ( AllCusps < 0 )
  {
    LODWORD(pExceptionObject) = AllCusps;
    throw (long *)&pExceptionObject;
  }
  v54 = v73;
  if ( (*(unsigned __int8 (__fastcall **)(struct CBezierForFiller *, __int64 *))(*(_QWORD *)v73 + 8LL))(v73, &v64) )
  {
    *((_DWORD *)v54 + 24) = v65;
    *((LPVOID *)v54 + 11) = lpMem[1];
    v57 = 0;
    lpMem[1] = 0;
    v56 = 1;
  }
  else
  {
    v56 = 0;
    v57 = lpMem[1];
  }
  if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA > *(_DWORD *)(v74 + 4) )
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
  }
  if ( `WinHeap::GetDefault'::`2'::s_WinHeap && v57 )
    HeapFree(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, v57);
  if ( lpMem[0] )
    CData::CDataPoint::`vector deleting destructor'((CData::CDataPoint *)lpMem[0], v55);
  if ( v68 )
    WinFree(v68);
  return v56;
}

```

## disassembly

```asm
0x180016bf0  mov     rax, rsp
0x180016bf3  mov     [rax+10h], rbx
0x180016bf7  mov     [rax+18h], r8
0x180016bfb  push    rbp
0x180016bfc  push    rsi
0x180016bfd  push    rdi
0x180016bfe  push    r12
0x180016c00  push    r13
0x180016c02  push    r14
0x180016c04  push    r15
0x180016c06  lea     rbp, [rax-5Fh]
0x180016c0a  sub     rsp, 0D0h
0x180016c11  movaps  xmmword ptr [rax-48h], xmm6
0x180016c15  movaps  xmmword ptr [rax-58h], xmm7
0x180016c19  movaps  xmmword ptr [rax-68h], xmm8
0x180016c1e  movaps  xmm7, xmm1
0x180016c21  mov     rbx, rcx
0x180016c24  cmp     dword ptr [rcx+10h], 2
0x180016c28  jb      loc_18001746C
0x180016c2e  mov     rcx, [rcx+0C0h]; void *
0x180016c35  xor     r15d, r15d
0x180016c38  test    rcx, rcx
0x180016c3b  jnz     loc_180017289
0x180016c41  movsxd  rcx, dword ptr [rbx+10h]
0x180016c45  mov     eax, 8
0x180016c4a  mul     rcx
0x180016c4d  mov     rdi, rax
0x180016c50  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180016c57  cmovb   rdi, rax
0x180016c5b  mov     ecx, cs:_tls_index
0x180016c61  mov     rax, gs:58h
0x180016c6a  mov     edx, 4
0x180016c6f  mov     rax, [rax+rcx*8]
0x180016c73  mov     [rbp+57h+arg_18], rax
0x180016c77  mov     eax, [rax+rdx]
0x180016c7a  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x180016c80  jg      loc_18001729A
0x180016c86  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x180016c8d  test    rcx, rcx
0x180016c90  jz      loc_1800171CA
0x180016c96  mov     r8, rdi; dwBytes
0x180016c99  mov     edx, cs:dwFlags; dwFlags
0x180016c9f  call    cs:__imp_HeapAlloc
0x180016ca5  mov     rcx, rax
0x180016ca8  mov     [rbx+0C0h], rax
0x180016caf  test    rax, rax
0x180016cb2  jz      loc_1800171D1
0x180016cb8  mov     rax, [rbx+18h]
0x180016cbc  mov     r14d, [rax]
0x180016cbf  mov     [rbx+40h], r14d
0x180016cc3  mov     rax, [rbx+20h]
0x180016cc7  mov     r9d, [rax]
0x180016cca  mov     [rbx+44h], r9d
0x180016cce  mov     rax, [rbx+0A0h]
0x180016cd5  mov     r8d, [rax]
0x180016cd8  mov     [rbx+0B8h], r8d
0x180016cdf  mov     rdx, [rbx+8]
0x180016ce3  mov     r13, [rdx]
0x180016ce6  test    r13, r13
0x180016ce9  jnz     loc_180017208
0x180016cef  mov     r13, r15
0x180016cf2  movsxd  r9, dword ptr [rbx+10h]
0x180016cf6  mov     [rbp+57h+var_C0], rdx
0x180016cfa  mov     [rbp+57h+var_B8], r15d
0x180016cfe  xorps   xmm0, xmm0
0x180016d01  movdqu  xmmword ptr [rbp+57h+lpMem], xmm0
0x180016d06  xorps   xmm8, xmm8
0x180016d0a  movsd   [rbp+57h+var_A0], xmm8
0x180016d10  mov     [rbp+57h+var_98], r15
0x180016d14  movdqu  [rbp+57h+var_90], xmm0
0x180016d19  movdqa  xmm0, cs:__xmm@3fc999999999999a4008000000000000
0x180016d21  movups  [rbp+57h+var_80], xmm0
0x180016d25  movsd   xmm0, cs:__real@4010000000000000
0x180016d2d  movsd   [rbp+57h+var_70], xmm0
0x180016d32  mov     edi, 1
0x180016d37  cmp     r9d, edi
0x180016d3a  jl      loc_180016E80
0x180016d40  mov     r12d, [rbx+44h]
0x180016d44  mov     r15, r9
0x180016d47  mov     eax, 8
0x180016d4c  mul     r9
0x180016d4f  mov     rsi, rax
0x180016d52  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180016d59  cmovb   rsi, rax
0x180016d5d  mov     rax, [rbp+57h+arg_18]
0x180016d61  mov     ecx, 4
0x180016d66  mov     eax, [rax+rcx]
0x180016d69  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x180016d6f  jg      loc_1800172F5
0x180016d75  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x180016d7c  test    rcx, rcx
0x180016d7f  jz      loc_1800171E9
0x180016d85  mov     r8, rsi; dwBytes
0x180016d88  mov     edx, cs:dwFlags; dwFlags
0x180016d8e  call    cs:__imp_HeapAlloc
0x180016d94  mov     [rbp+57h+lpMem+8], rax
0x180016d98  mov     eax, 20h ; ' '
0x180016d9d  mul     r15
0x180016da0  mov     rsi, rax
0x180016da3  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180016daa  cmovb   rsi, rax
0x180016dae  add     rsi, 8
0x180016db2  cmovb   rsi, rax
0x180016db6  mov     rax, [rbp+57h+arg_18]
0x180016dba  mov     ecx, 4
0x180016dbf  mov     eax, [rax+rcx]
0x180016dc2  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x180016dc8  jg      loc_180017357
0x180016dce  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x180016dd5  test    rcx, rcx
0x180016dd8  jz      loc_1800171F0
0x180016dde  mov     r8, rsi; dwBytes
0x180016de1  mov     edx, cs:dwFlags; dwFlags
0x180016de7  call    cs:__imp_HeapAlloc
0x180016ded  mov     [rbp+57h+pExceptionObject], rax
0x180016df1  test    rax, rax
0x180016df4  jnz     short loc_180016DFE
0x180016df6  xor     r15d, r15d
0x180016df9  mov     esi, r15d
0x180016dfc  jmp     short loc_180016E2B
0x180016dfe  mov     [rax], r15
0x180016e01  lea     rsi, [rax+8]
0x180016e05  lea     rax, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180016e0c  mov     [rsp+100h+var_E0], rax; void (*)(void *)
0x180016e11  lea     r9, ??0CDataPoint@CData@@QEAA@XZ; void (*)(void *)
0x180016e18  mov     r8, r15; unsigned __int64
0x180016e1b  mov     edx, 20h ; ' '; unsigned __int64
0x180016e20  mov     rcx, rsi; void *
0x180016e23  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180016e28  xor     r15d, r15d
0x180016e2b  mov     [rbp+57h+lpMem], rsi
0x180016e2f  test    rsi, rsi
0x180016e32  jz      loc_1800173B9
0x180016e38  mov     rax, [rbp+57h+lpMem+8]
0x180016e3c  test    rax, rax
0x180016e3f  jz      loc_1800173B9
0x180016e45  mov     [rax], r15
0x180016e48  mov     rax, [rbp+57h+lpMem]
0x180016e4c  movd    xmm0, r14d
0x180016e51  cvtdq2pd xmm0, xmm0
0x180016e55  movsd   qword ptr [rax], xmm0
0x180016e59  movd    xmm1, r12d
0x180016e5e  cvtdq2pd xmm1, xmm1
0x180016e62  movsd   qword ptr [rax+8], xmm1
0x180016e67  mov     rax, [rbp+57h+lpMem]
0x180016e6b  mov     [rax+10h], r15d
0x180016e6f  mov     [rbp+57h+var_B8], edi
0x180016e72  mov     r8d, [rbx+0B8h]
0x180016e79  mov     rcx, [rbx+0C0h]
0x180016e80  movd    xmm0, r8d
0x180016e85  cvtdq2pd xmm0, xmm0
0x180016e89  addsd   xmm0, qword ptr [rbx+0A8h]
0x180016e91  mulsd   xmm0, qword ptr [rbx+0B0h]
0x180016e99  movsd   qword ptr [rcx], xmm0
0x180016e9d  mov     [rbx+0C8h], edi
0x180016ea3  mov     r12d, [rbx+40h]
0x180016ea7  mov     r9d, [rbx+44h]
0x180016eab  cmp     dword ptr [rbx+10h], 1
0x180016eaf  jle     loc_180016FE2
0x180016eb5  nop     word ptr [rax+rax+00000000h]
0x180016ec0  movsxd  rsi, edi
0x180016ec3  mov     rax, [rbx+18h]
0x180016ec7  mov     edx, [rax+rsi*4]
0x180016eca  mov     [rbx+40h], edx
0x180016ecd  mov     rax, [rbx+20h]
0x180016ed1  mov     ecx, [rax+rsi*4]
0x180016ed4  mov     [rbx+44h], ecx
0x180016ed7  test    r13, r13
0x180016eda  jnz     loc_1800173F0
0x180016ee0  cmp     r12d, edx
0x180016ee3  jz      loc_180017173
0x180016ee9  mov     r12d, edx
0x180016eec  mov     r9d, [rbx+44h]
0x180016ef0  mov     dword ptr [rbp+57h+pExceptionObject], r9d
0x180016ef4  movsxd  rcx, [rbp+57h+var_B8]
0x180016ef8  shl     rcx, 5
0x180016efc  mov     rax, [rbp+57h+lpMem]
0x180016f00  movd    xmm0, edx
0x180016f04  cvtdq2pd xmm0, xmm0
0x180016f08  movsd   qword ptr [rcx+rax], xmm0
0x180016f0d  movd    xmm1, r9d
0x180016f12  cvtdq2pd xmm1, xmm1
0x180016f16  movsd   qword ptr [rcx+rax+8], xmm1
0x180016f1c  movsxd  rcx, [rbp+57h+var_B8]
0x180016f20  lea     eax, [rcx-1]
0x180016f23  movsxd  r14, eax
0x180016f26  mov     r8, r14
0x180016f29  shl     r8, 5
0x180016f2d  mov     rdx, [rbp+57h+lpMem]
0x180016f31  mov     r15, rcx
0x180016f34  mov     rax, rcx
0x180016f37  shl     rax, 5
0x180016f3b  movsd   xmm0, qword ptr [rax+rdx+8]
0x180016f41  subsd   xmm0, qword ptr [r8+rdx+8]
0x180016f48  movsd   xmm1, qword ptr [rax+rdx]
0x180016f4d  subsd   xmm1, qword ptr [r8+rdx]
0x180016f53  mulsd   xmm1, xmm1
0x180016f57  mulsd   xmm0, xmm0
0x180016f5b  addsd   xmm1, xmm0
0x180016f5f  xorps   xmm0, xmm0
0x180016f62  ucomisd xmm0, xmm1
0x180016f66  ja      loc_1800171F7
0x180016f6c  sqrtpd  xmm0, xmm1
0x180016f70  mov     rax, [rbp+57h+lpMem+8]
0x180016f74  addsd   xmm0, qword ptr [rax+r14*8]
0x180016f7a  movsd   qword ptr [rax+r15*8], xmm0
0x180016f80  movsxd  rdx, [rbp+57h+var_B8]
0x180016f84  mov     rcx, rdx
0x180016f87  shl     rcx, 5
0x180016f8b  mov     rax, [rbp+57h+lpMem]
0x180016f8f  mov     [rcx+rax+10h], edx
0x180016f93  inc     [rbp+57h+var_B8]
0x180016f96  mov     rax, [rbx+0A0h]
0x180016f9d  mov     ecx, [rax+rsi*4]
0x180016fa0  mov     [rbx+0B8h], ecx
0x180016fa6  movd    xmm0, ecx
0x180016faa  cvtdq2pd xmm0, xmm0
0x180016fae  addsd   xmm0, qword ptr [rbx+0A8h]
0x180016fb6  mulsd   xmm0, qword ptr [rbx+0B0h]
0x180016fbe  movsxd  rcx, dword ptr [rbx+0C8h]
0x180016fc5  mov     rax, [rbx+0C0h]
0x180016fcc  movsd   qword ptr [rax+rcx*8], xmm0
0x180016fd1  inc     dword ptr [rbx+0C8h]
0x180016fd7  inc     edi
0x180016fd9  cmp     edi, [rbx+10h]
0x180016fdc  jl      loc_180016EC0
0x180016fe2  mov     r8d, [rbp+57h+var_B8]
0x180016fe6  cmp     r8d, 2
0x180016fea  jl      loc_180017463
0x180016ff0  mov     rax, [rbx+0C0h]
0x180016ff7  mov     rcx, [rax]
0x180016ffa  mov     [rbx+58h], rcx
0x180016ffe  mov     rdx, [rbp+57h+lpMem]
0x180017002  movsd   xmm3, qword ptr [rdx]
0x180017006  movsd   xmm4, qword ptr [rdx+8]
0x18001700b  movaps  xmm6, xmm3
0x18001700e  movaps  xmm5, xmm4
0x180017011  xor     ecx, ecx
0x180017013  nop     dword ptr [rax+00h]
0x180017017  nop     word ptr [rax+rax+00000000h]
0x180017020  movsxd  rax, ecx
0x180017023  shl     rax, 5
0x180017027  movsd   xmm1, qword ptr [rax+rdx]
0x18001702c  movaps  xmm0, xmm1
0x18001702f  minsd   xmm0, xmm3
0x180017033  movaps  xmm3, xmm0
0x180017036  maxsd   xmm1, xmm6
0x18001703a  movaps  xmm6, xmm1
0x18001703d  movsd   xmm2, qword ptr [rax+rdx+8]
0x180017043  movaps  xmm0, xmm2
0x180017046  minsd   xmm0, xmm4
0x18001704a  movaps  xmm4, xmm0
0x18001704d  maxsd   xmm2, xmm5
0x180017051  movaps  xmm5, xmm2
0x180017054  inc     ecx
0x180017056  cmp     ecx, r8d
0x180017059  jl      short loc_180017020
0x18001705b  subsd   xmm6, xmm3
0x18001705f  subsd   xmm5, xmm0
0x180017063  comisd  xmm6, xmm8
0x180017068  jb      loc_180017473
0x18001706e  comisd  xmm5, xmm8
0x180017073  jb      loc_18001747F
0x180017079  addsd   xmm5, xmm6
0x18001707d  movsd   [rbp+57h+var_A0], xmm5
0x180017082  movaps  xmm0, xmm7
0x180017085  comisd  xmm7, xmm8
0x18001708a  jb      loc_18001748B
0x180017090  comisd  xmm0, cs:__real@3e112e0be826d695
0x180017098  jbe     loc_180017497
0x18001709e  movaps  xmm1, xmm7
0x1800170a1  movsd   qword ptr [rbp+57h+var_80], xmm7
0x1800170a6  movsd   xmm0, cs:__real@3ff0000000000000
0x1800170ae  comisd  xmm0, xmm1
0x1800170b2  ja      loc_1800174DF
0x1800170b8  lea     rcx, [rbp+57h+var_C0]; this
0x1800170bc  call    ?FindAllCusps@CData@@IEAAJXZ; CData::FindAllCusps(void)
0x1800170c1  test    eax, eax
0x1800170c3  js      loc_1800174E9
0x1800170c9  mov     rbx, [rbp+57h+arg_10]
0x1800170cd  mov     rax, [rbx]
0x1800170d0  movaps  xmm2, xmm7
0x1800170d3  lea     rdx, [rbp+57h+var_C0]
0x1800170d7  mov     rcx, rbx
0x1800170da  mov     rax, [rax+8]
0x1800170de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170e3  test    al, al
0x1800170e5  jnz     loc_1800174FD
0x1800170eb  xor     dil, dil
0x1800170ee  mov     rbx, [rbp+57h+lpMem+8]
0x1800170f2  mov     rax, [rbp+57h+arg_18]
0x1800170f6  mov     ecx, 4
0x1800170fb  mov     eax, [rax+rcx]
0x1800170fe  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x180017104  jg      loc_180017519
0x18001710a  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x180017111  test    rcx, rcx
0x180017114  jz      short loc_18001712A
0x180017116  test    rbx, rbx
0x180017119  jz      short loc_18001712A
  ... truncated ...
```
