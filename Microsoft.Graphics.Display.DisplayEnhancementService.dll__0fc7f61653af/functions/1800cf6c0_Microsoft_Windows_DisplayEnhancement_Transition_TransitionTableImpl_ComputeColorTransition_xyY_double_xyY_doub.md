# Microsoft::Windows::DisplayEnhancement::Transition::TransitionTableImpl::ComputeColorTransition(xyY<double>,xyY<double>)

- ea: `0x1800cf6c0`
- end: `0x1800cfd45`
- name: `?ComputeColorTransition@TransitionTableImpl@Transition@DisplayEnhancement@Windows@Microsoft@@AEAA?AV?$list@UTransitionTableEntry@Transition@DisplayEnhancement@Windows@Microsoft@@V?$allocator@UTransitionTableEntry@Transition@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@U?$xyY@N@@0@Z`
- size: `1669`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800cf460`

## callees

- `0x18000638c`
- `0x1800063a4`
- `0x1800063d4`
- `0x1800063ec`
- `0x1800063f8`
- `0x180008ae8`
- `0x18001edd0`
- `0x18001f4b4`
- `0x18003e644`
- `0x18003eb30`
- `0x18003ef70`
- `0x18003f174`
- `0x18004fc88`
- `0x180061060`
- `0x1800753fc`
- `0x1800754ac`
- `0x1800cf6c0`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800cfd3e`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800cfd3e`

## string_xrefs

- `0x1800cfcce`: `Microsoft.Graphics.Display.DisplayEnhancementService.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall Microsoft::Windows::DisplayEnhancement::Transition::TransitionTableImpl::ComputeColorTransition(
        __int64 a1,
        _QWORD *a2,
        double *a3,
        __m128d *a4)
{
  __m128d v7; // xmm7
  double v8; // xmm6_8
  __m128d *v9; // r8
  double v10; // xmm0_8
  double v11; // xmm0_8
  char v12; // xmm7_1
  double v13; // xmm6_8
  double v14; // xmm9_8
  int v15; // edx
  int v16; // r8d
  int v17; // r15d
  PVOID *v18; // rbx
  const GUID *v19; // rcx
  __int64 v20; // xmm6_8
  int v21; // edx
  __int64 v22; // rcx
  unsigned int v23; // esi
  int v24; // r8d
  double v25; // xmm0_8
  int v26; // esi
  int v27; // edx
  int v28; // ecx
  int v29; // r8d
  int v30; // r15d
  double v31; // xmm2_8
  double v32; // xmm12_8
  double v33; // xmm6_8
  double v34; // xmm10_8
  double v35; // xmm7_8
  double v36; // xmm11_8
  double v37; // xmm9_8
  unsigned int i; // r14d
  __m128d v39; // xmm0
  __m128d v40; // xmm2
  double v41; // xmm1_8
  __int64 v42; // rbx
  _QWORD *v43; // rax
  __int64 v44; // rcx
  _QWORD *v45; // rax
  _QWORD *v46; // rcx
  int v48; // [rsp+28h] [rbp-E0h]
  int v49; // [rsp+48h] [rbp-C0h]
  double v50; // [rsp+50h] [rbp-B8h]
  double v51; // [rsp+50h] [rbp-B8h]
  double v52; // [rsp+50h] [rbp-B8h]
  double v53; // [rsp+58h] [rbp-B0h]
  __m128d v54; // [rsp+78h] [rbp-90h] BYREF
  double v55; // [rsp+88h] [rbp-80h]
  int v56; // [rsp+98h] [rbp-70h]
  __int128 v57; // [rsp+A0h] [rbp-68h] BYREF
  double v58; // [rsp+B0h] [rbp-58h]
  __m128d v59; // [rsp+B8h] [rbp-50h] BYREF
  double v60; // [rsp+C8h] [rbp-40h]
  int v61; // [rsp+D0h] [rbp-38h]
  int v62; // [rsp+D4h] [rbp-34h]
  __m128d v63; // [rsp+D8h] [rbp-30h] BYREF
  double v64; // [rsp+E8h] [rbp-20h]
  __int128 v65; // [rsp+F0h] [rbp-18h] BYREF
  double v66; // [rsp+100h] [rbp-8h]
  __int128 v67; // [rsp+108h] [rbp+0h] BYREF
  double v68; // [rsp+118h] [rbp+10h]
  __m128d v69; // [rsp+120h] [rbp+18h] BYREF
  double v70; // [rsp+130h] [rbp+28h]
  _QWORD *v71; // [rsp+138h] [rbp+30h]

  v71 = a2;
  v56 = 0;
  v69 = 0;
  v70 = 0.0;
  v65 = 0;
  v66 = 0.0;
  v67 = 0;
  v68 = 0.0;
  v57 = 0;
  v58 = 0.0;
  v63 = 0;
  v64 = 0.0;
  v54.m128d_f64[0] = *(float *)(a1 + 68) * 0.6666666666666666 + *a3 * 0.3333333333333333;
  v54.m128d_f64[1] = *(float *)(a1 + 72) * 0.6666666666666666 + a3[1] * 0.3333333333333333;
  v55 = *(float *)(a1 + 64) * 0.6666666666666666 + a3[2] * 0.3333333333333333;
  xyY2XYZ(&v54, &v69);
  v7 = v69;
  v54 = v69;
  v8 = v70;
  v55 = v70;
  v59 = *v9;
  v60 = v9[1].m128d_f64[0];
  xyY2LCh(&v59, &v54, &v65, &v57);
  v59 = v7;
  v60 = v8;
  v54 = *a4;
  v55 = a4[1].m128d_f64[0];
  xyY2LCh(&v54, &v59, &v67, &v63);
  v7.m128d_f64[0] = pow(*((double *)&v65 + 1) - *((double *)&v67 + 1), 2.0);
  v7.m128d_f64[0] = v7.m128d_f64[0] + pow(*(double *)&v65 - *(double *)&v67, 2.0);
  v10 = pow(v66 - v68, 2.0);
  v11 = sqrt(v10 + v7.m128d_f64[0]);
  v12 = LOBYTE(v11);
  v13 = (double)*(int *)(a1 + 48);
  v14 = (double)*(int *)(a1 + 8);
  v17 = (int)((double (*)(void))o_ceil_0)();
  v18 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) == 0
    || (LOBYTE(v15) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
  {
    LOBYTE(v15) = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    || (LOBYTE(v16) = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
  {
    LOBYTE(v16) = 0;
  }
  v19 = &WPP_d16748abdc3b3c7a9d56c5dd92375b2b_Traceguids;
  if ( (_BYTE)v15 || (_BYTE)v16 )
  {
    v50 = (double)v17;
    WPP_RECORDER_AND_TRACE_SF_sgggq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v15,
      v16,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v48,
      14,
      13,
      &WPP_d16748abdc3b3c7a9d56c5dd92375b2b_Traceguids,
      v49,
      SLOBYTE(v50),
      SLOBYTE(v14),
      SLOBYTE(v13),
      a1);
    v18 = (PVOID *)WPP_GLOBAL_Control;
  }
  v20 = *(_QWORD *)(a1 + 24);
  v23 = (int)o_ceil_0(v19);
  if ( v18 == &WPP_GLOBAL_Control
    || (*((_DWORD *)v18 + 7) & 0x2000) == 0
    || (LOBYTE(v21) = 1, *((_BYTE *)v18 + 25) < 5u) )
  {
    LOBYTE(v21) = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || (LOBYTE(v24) = 1, !*((_WORD *)v18 + 24)) )
    LOBYTE(v24) = 0;
  if ( (_BYTE)v21 || (_BYTE)v24 )
  {
    v51 = (double)(int)v23;
    WPP_RECORDER_AND_TRACE_SF_sgggq(
      (int)v18[2],
      v21,
      v24,
      (int)v18[5],
      v48,
      14,
      14,
      &WPP_d16748abdc3b3c7a9d56c5dd92375b2b_Traceguids,
      v49,
      SLOBYTE(v51),
      v12,
      v20,
      a1);
    v18 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v17 >= v23 )
    v23 = v17;
  if ( v23 <= 1 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v18 = (PVOID *)WPP_GLOBAL_Control;
  }
  v25 = o_ceil_0(v22);
  v26 = (int)v25 - 1;
  v28 = (int)(o_ceil_0(*(_DWORD *)(a1 + 8) / (unsigned int)(int)v25) * 1000.0);
  v30 = v28;
  if ( (unsigned int)v28 <= *(_DWORD *)(a1 + 48) )
    v30 = *(_DWORD *)(a1 + 48);
  if ( v18 == &WPP_GLOBAL_Control
    || (*((_DWORD *)v18 + 7) & 0x2000) == 0
    || (LOBYTE(v27) = 1, *((_BYTE *)v18 + 25) < 5u) )
  {
    LOBYTE(v27) = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || (LOBYTE(v29) = 1, !*((_WORD *)v18 + 24)) )
    LOBYTE(v29) = 0;
  if ( (_BYTE)v27 || (_BYTE)v29 )
  {
    v31 = (double)*(int *)(a1 + 48);
    v53 = (double)v28;
    v52 = (double)v30;
    WPP_RECORDER_AND_TRACE_SF_sgggq(
      (int)v18[2],
      v27,
      v29,
      (int)v18[5],
      v48,
      14,
      15,
      &WPP_d16748abdc3b3c7a9d56c5dd92375b2b_Traceguids,
      v49,
      SLOBYTE(v52),
      SLOBYTE(v53),
      SLOBYTE(v31),
      a1);
  }
  std::list<std::wstring>::list<std::wstring>(a2);
  v56 = 1;
  if ( v26 )
  {
    v32 = *(double *)&v57;
    v33 = (v63.m128d_f64[0] - *(double *)&v57) / (double)v26;
    v34 = *((double *)&v57 + 1);
    v35 = (v63.m128d_f64[1] - *((double *)&v57 + 1)) / (double)v26;
    v36 = v58;
    v37 = (v64 - v58) / (double)v26;
    for ( i = 0; i < v26; ++i )
    {
      v63 = 0;
      v64 = 0.0;
      v57 = 0;
      v58 = 0.0;
      v32 = v32 + v33;
      v34 = v34 + v35;
      v36 = v37 + v36;
      v54.m128d_f64[0] = v32;
      v54.m128d_f64[1] = cos(v36) * v34;
      v55 = o_sin_0(v36) * v34;
      Lab2XYZ(&v54, &v69, &v57);
      v39 = (__m128d)(unsigned __int64)v57;
      if ( *(double *)&v57 <= 0.0 )
        v39 = 0;
      v40 = (__m128d)*((unsigned __int64 *)&v57 + 1);
      if ( *((double *)&v57 + 1) <= 0.0 )
        v40 = 0;
      v41 = v58;
      if ( v58 <= 0.0 )
        v41 = 0.0;
      v59 = _mm_unpacklo_pd(v39, v40);
      v60 = v41;
      if ( (unsigned int)XYZ2xyY(&v59, &v63) != -1 )
      {
        v62 = 0;
        v59 = v63;
        v60 = a4[1].m128d_f64[0];
        v61 = v30;
        if ( a2[1] == 0x555555555555555LL )
          std::_Xlength_error("list too long");
        v42 = *a2;
        v65 = (unsigned __int64)a2;
        v43 = std::_Allocate<16,std::_Default_allocate_traits>(0x30u);
        v45 = (_QWORD *)std::_Default_allocator_traits<std::allocator<std::_List_node<Microsoft::Windows::DisplayEnhancement::Transition::TransitionTableEntry,void *>>>::construct<Microsoft::Windows::DisplayEnhancement::Transition::TransitionTableEntry,Microsoft::Windows::DisplayEnhancement::Transition::TransitionTableEntry const &>(
                          v44,
                          v43 + 2,
                          &v59);
        ++a2[1];
        v46 = *(_QWORD **)(v42 + 8);
        *v45 = v42;
        v45[1] = v46;
        *((_QWORD *)&v65 + 1) = 0;
        *(_QWORD *)(v42 + 8) = v45;
        *v46 = v45;
        std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::wstring,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::wstring,void *>>>(&v65);
      }
    }
  }
  if ( v26 != a2[1] )
    MicrosoftTelemetryAssertTriggeredArgs(
      "Microsoft.Graphics.Display.DisplayEnhancementService.dll",
      (unsigned int)v26,
      *((unsigned int *)a2 + 2));
  *(double *)(*(_QWORD *)(*a2 + 8LL) + 16LL) = a4->m128d_f64[0];
  *(double *)(*(_QWORD *)(*a2 + 8LL) + 24LL) = a4->m128d_f64[1];
  return a2;
}

```

## disassembly

```asm
0x1800cf6c0  mov     rax, rsp
0x1800cf6c3  push    rbp
0x1800cf6c4  push    rbx
0x1800cf6c5  push    rsi
0x1800cf6c6  push    rdi
0x1800cf6c7  push    r12
0x1800cf6c9  push    r13
0x1800cf6cb  push    r14
0x1800cf6cd  push    r15
0x1800cf6cf  lea     rbp, [rax-0F8h]
0x1800cf6d6  sub     rsp, 1B8h
0x1800cf6dd  movaps  xmmword ptr [rax-58h], xmm6
0x1800cf6e1  movaps  xmmword ptr [rax-68h], xmm7
0x1800cf6e5  movaps  xmmword ptr [rax-78h], xmm8
0x1800cf6ea  movaps  xmmword ptr [rax-88h], xmm9
0x1800cf6f2  movaps  xmmword ptr [rax-98h], xmm10
0x1800cf6fa  movaps  xmmword ptr [rax-0A8h], xmm11
0x1800cf702  movaps  xmmword ptr [rax-0B8h], xmm12
0x1800cf70a  mov     r12, r9
0x1800cf70d  mov     rdi, rdx
0x1800cf710  mov     r14, rcx
0x1800cf713  mov     [rbp+0F0h+var_C0], rdx
0x1800cf717  xor     r13d, r13d
0x1800cf71a  mov     [rbp+0F0h+var_160], r13d
0x1800cf71e  xorps   xmm0, xmm0
0x1800cf721  movups  [rbp+0F0h+var_D8], xmm0
0x1800cf725  xorps   xmm8, xmm8
0x1800cf729  movsd   [rbp+0F0h+var_C8], xmm8
0x1800cf72f  xor     eax, eax
0x1800cf731  movups  [rbp+0F0h+var_108], xmm0
0x1800cf735  mov     [rbp+0F0h+var_F8], rax
0x1800cf739  xorps   xmm1, xmm1
0x1800cf73c  movups  [rbp+0F0h+var_F0], xmm1
0x1800cf740  mov     [rbp+0F0h+var_E0], rax
0x1800cf744  movups  [rbp+0F0h+var_158], xmm0
0x1800cf748  mov     [rbp+0F0h+var_148], rax
0x1800cf74c  movups  [rbp+0F0h+var_120], xmm1
0x1800cf750  mov     [rbp+0F0h+var_110], rax
0x1800cf754  movss   xmm2, dword ptr [rcx+44h]
0x1800cf759  cvtps2pd xmm2, xmm2
0x1800cf75c  movsd   xmm4, cs:__real@3fe5555555555555
0x1800cf764  mulsd   xmm2, xmm4
0x1800cf768  movsd   xmm0, qword ptr [r8]
0x1800cf76d  movsd   xmm3, cs:__real@3fd5555555555555
0x1800cf775  mulsd   xmm0, xmm3
0x1800cf779  addsd   xmm2, xmm0
0x1800cf77d  movsd   qword ptr [rsp+1F0h+var_188+8], xmm2
0x1800cf783  movss   xmm1, dword ptr [rcx+48h]
0x1800cf788  cvtps2pd xmm1, xmm1
0x1800cf78b  mulsd   xmm1, xmm4
0x1800cf78f  movsd   xmm0, qword ptr [r8+8]
0x1800cf795  mulsd   xmm0, xmm3
0x1800cf799  addsd   xmm1, xmm0
0x1800cf79d  movsd   [rsp+1F0h+var_178], xmm1
0x1800cf7a3  movss   xmm2, dword ptr [rcx+40h]
0x1800cf7a8  cvtps2pd xmm2, xmm2
0x1800cf7ab  mulsd   xmm2, xmm4
0x1800cf7af  movsd   xmm0, qword ptr [r8+10h]
0x1800cf7b5  mulsd   xmm0, xmm3
0x1800cf7b9  addsd   xmm2, xmm0
0x1800cf7bd  movsd   [rbp+0F0h+var_170], xmm2
0x1800cf7c2  lea     rdx, [rbp+0F0h+var_D8]
0x1800cf7c6  lea     rcx, [rsp+1F0h+var_188+8]
0x1800cf7cb  call    ?xyY2XYZ@@YAHAEBU?$xyY@N@@PEAV?$XYZ@N@@@Z; xyY2XYZ(xyY<double> const &,XYZ<double> *)
0x1800cf7d0  movups  xmm7, [rbp+0F0h+var_D8]
0x1800cf7d4  movaps  [rsp+1F0h+var_188+8], xmm7
0x1800cf7d9  movsd   xmm6, [rbp+0F0h+var_C8]
0x1800cf7de  movsd   [rbp+0F0h+var_170], xmm6
0x1800cf7e3  movaps  xmm0, xmmword ptr [r8]
0x1800cf7e7  movaps  [rbp+0F0h+var_140], xmm0
0x1800cf7eb  movsd   xmm1, qword ptr [r8+10h]
0x1800cf7f1  movsd   [rbp+0F0h+var_130], xmm1
0x1800cf7f6  lea     r9, [rbp+0F0h+var_158]
0x1800cf7fa  lea     r8, [rbp+0F0h+var_108]
0x1800cf7fe  lea     rdx, [rsp+1F0h+var_188+8]
0x1800cf803  lea     rcx, [rbp+0F0h+var_140]
0x1800cf807  call    ?xyY2LCh@@YAHU?$xyY@N@@V?$XYZ@N@@AEAU?$Lab@N@@AEAU?$LCh@N@@@Z; xyY2LCh(xyY<double>,XYZ<double>,Lab<double> &,LCh<double> &)
0x1800cf80c  movaps  [rbp+0F0h+var_140], xmm7
0x1800cf810  movsd   [rbp+0F0h+var_130], xmm6
0x1800cf815  movaps  xmm0, xmmword ptr [r12]
0x1800cf81a  movaps  [rsp+1F0h+var_188+8], xmm0
0x1800cf81f  movsd   xmm1, qword ptr [r12+10h]
0x1800cf826  movsd   [rbp+0F0h+var_170], xmm1
0x1800cf82b  lea     r9, [rbp+0F0h+var_120]
0x1800cf82f  lea     r8, [rbp+0F0h+var_F0]
0x1800cf833  lea     rdx, [rbp+0F0h+var_140]
0x1800cf837  lea     rcx, [rsp+1F0h+var_188+8]
0x1800cf83c  call    ?xyY2LCh@@YAHU?$xyY@N@@V?$XYZ@N@@AEAU?$Lab@N@@AEAU?$LCh@N@@@Z; xyY2LCh(xyY<double>,XYZ<double>,Lab<double> &,LCh<double> &)
0x1800cf841  movsd   xmm0, qword ptr [rbp+0F0h+var_108+8]
0x1800cf846  subsd   xmm0, qword ptr [rbp+0F0h+var_F0+8]; X
0x1800cf84b  movsd   xmm6, cs:__real@4000000000000000
0x1800cf853  movaps  xmm1, xmm6; Y
0x1800cf856  call    pow
0x1800cf85b  movaps  xmm7, xmm0
0x1800cf85e  movsd   xmm0, qword ptr [rbp+0F0h+var_108]
0x1800cf863  subsd   xmm0, qword ptr [rbp+0F0h+var_F0]; X
0x1800cf868  movaps  xmm1, xmm6; Y
0x1800cf86b  call    pow
0x1800cf870  addsd   xmm7, xmm0
0x1800cf874  movsd   xmm0, [rbp+0F0h+var_F8]
0x1800cf879  subsd   xmm0, [rbp+0F0h+var_E0]; X
0x1800cf87e  movaps  xmm1, xmm6; Y
0x1800cf881  call    pow
0x1800cf886  addsd   xmm0, xmm7; X
0x1800cf88a  call    sqrt
0x1800cf88f  movaps  xmm7, xmm0
0x1800cf892  mov     eax, [r14+30h]
0x1800cf896  xorps   xmm6, xmm6
0x1800cf899  cvtsi2sd xmm6, rax
0x1800cf89e  mov     eax, [r14+8]
0x1800cf8a2  xorps   xmm9, xmm9
0x1800cf8a6  cvtsi2sd xmm9, rax
0x1800cf8ab  movaps  xmm1, xmm6
0x1800cf8ae  movsd   xmm10, cs:__real@408f400000000000
0x1800cf8b7  divsd   xmm1, xmm10
0x1800cf8bc  movaps  xmm0, xmm9
0x1800cf8c0  divsd   xmm0, xmm1
0x1800cf8c4  call    _o_ceil_0
0x1800cf8c9  cvttsd2si r15, xmm0
0x1800cf8ce  lea     rax, WPP_GLOBAL_Control
0x1800cf8d5  mov     rbx, cs:WPP_GLOBAL_Control
0x1800cf8dc  cmp     rbx, rax
0x1800cf8df  jz      short loc_1800CF8F2
0x1800cf8e1  test    dword ptr [rbx+1Ch], 2000h
0x1800cf8e8  jz      short loc_1800CF8F2
0x1800cf8ea  cmp     byte ptr [rbx+19h], 5
0x1800cf8ee  mov     dl, 1
0x1800cf8f0  jnb     short loc_1800CF8F5
0x1800cf8f2  mov     dl, r13b; int
0x1800cf8f5  lea     rax, WPP_RECORDER_INITIALIZED
0x1800cf8fc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800cf903  jz      short loc_1800CF90F
0x1800cf905  cmp     [rbx+30h], r13w
0x1800cf90a  mov     r8b, 1
0x1800cf90d  jnz     short loc_1800CF912
0x1800cf90f  mov     r8b, r13b; int
0x1800cf912  lea     rcx, WPP_d16748abdc3b3c7a9d56c5dd92375b2b_Traceguids
0x1800cf919  test    dl, dl
0x1800cf91b  jnz     short loc_1800CF922
0x1800cf91d  test    r8b, r8b
0x1800cf920  jz      short loc_1800CF96D
0x1800cf922  mov     eax, r15d
0x1800cf925  xorps   xmm0, xmm0
0x1800cf928  cvtsi2sd xmm0, rax
0x1800cf92d  mov     qword ptr [rsp+1F0h+var_190], r14; char
0x1800cf932  movsd   qword ptr [rsp+1F0h+var_198], xmm6; char
0x1800cf938  movsd   qword ptr [rsp+1F0h+var_1A0], xmm9; char
0x1800cf93f  movsd   qword ptr [rsp+1F0h+var_1A8], xmm0; char
0x1800cf945  mov     [rsp+1F0h+MessageGuid], rcx; MessageGuid
0x1800cf94a  mov     [rsp+1F0h+var_1C0], 0Dh; __int16
0x1800cf951  mov     [rsp+1F0h+var_1C8], 0Eh; int
0x1800cf959  mov     r9, [rbx+28h]; int
0x1800cf95d  mov     rcx, [rbx+10h]; int
0x1800cf961  call    WPP_RECORDER_AND_TRACE_SF_sgggq
0x1800cf966  mov     rbx, cs:WPP_GLOBAL_Control
0x1800cf96d  movsd   xmm6, qword ptr [r14+18h]
0x1800cf973  movaps  xmm0, xmm7
0x1800cf976  divsd   xmm0, xmm6
0x1800cf97a  call    _o_ceil_0
0x1800cf97f  cvttsd2si rsi, xmm0
0x1800cf984  lea     rax, WPP_GLOBAL_Control
0x1800cf98b  cmp     rbx, rax
0x1800cf98e  jz      short loc_1800CF9A1
0x1800cf990  test    dword ptr [rbx+1Ch], 2000h
0x1800cf997  jz      short loc_1800CF9A1
0x1800cf999  cmp     byte ptr [rbx+19h], 5
0x1800cf99d  mov     dl, 1
0x1800cf99f  jnb     short loc_1800CF9A4
0x1800cf9a1  mov     dl, r13b; int
0x1800cf9a4  lea     rax, WPP_RECORDER_INITIALIZED
0x1800cf9ab  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800cf9b2  jz      short loc_1800CF9BE
0x1800cf9b4  cmp     [rbx+30h], r13w
0x1800cf9b9  mov     r8b, 1
0x1800cf9bc  jnz     short loc_1800CF9C1
0x1800cf9be  mov     r8b, r13b; int
0x1800cf9c1  test    dl, dl
0x1800cf9c3  jnz     short loc_1800CF9CA
0x1800cf9c5  test    r8b, r8b
0x1800cf9c8  jz      short loc_1800CFA19
0x1800cf9ca  mov     eax, esi
0x1800cf9cc  xorps   xmm0, xmm0
0x1800cf9cf  cvtsi2sd xmm0, rax
0x1800cf9d4  mov     qword ptr [rsp+1F0h+var_190], r14; char
0x1800cf9d9  movsd   qword ptr [rsp+1F0h+var_198], xmm6; char
0x1800cf9df  movsd   qword ptr [rsp+1F0h+var_1A0], xmm7; char
0x1800cf9e5  movsd   qword ptr [rsp+1F0h+var_1A8], xmm0; char
0x1800cf9eb  lea     rax, WPP_d16748abdc3b3c7a9d56c5dd92375b2b_Traceguids
0x1800cf9f2  mov     [rsp+1F0h+MessageGuid], rax; MessageGuid
0x1800cf9f7  mov     eax, 0Eh
0x1800cf9fc  mov     [rsp+1F0h+var_1C0], ax; __int16
0x1800cfa01  mov     [rsp+1F0h+var_1C8], eax; int
0x1800cfa05  mov     r9, [rbx+28h]; int
0x1800cfa09  mov     rcx, [rbx+10h]; int
0x1800cfa0d  call    WPP_RECORDER_AND_TRACE_SF_sgggq
0x1800cfa12  mov     rbx, cs:WPP_GLOBAL_Control
0x1800cfa19  cmp     r15d, esi
0x1800cfa1c  cmovnb  esi, r15d
0x1800cfa20  cmp     esi, 1
0x1800cfa23  ja      short loc_1800CFA31
0x1800cfa25  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800cfa2a  mov     rbx, cs:WPP_GLOBAL_Control
0x1800cfa31  mov     eax, esi
0x1800cfa33  xorps   xmm0, xmm0
0x1800cfa36  cvtsi2sd xmm0, rax
0x1800cfa3b  divsd   xmm0, qword ptr [r14+10h]
0x1800cfa41  call    _o_ceil_0
0x1800cfa46  cvttsd2si ecx, xmm0
0x1800cfa4a  lea     esi, [rcx-1]
0x1800cfa4d  xor     edx, edx
0x1800cfa4f  mov     eax, [r14+8]
0x1800cfa53  div     ecx
0x1800cfa55  mov     ecx, eax
0x1800cfa57  xorps   xmm0, xmm0
0x1800cfa5a  cvtsi2sd xmm0, rcx
0x1800cfa5f  call    _o_ceil_0
0x1800cfa64  mulsd   xmm0, xmm10
0x1800cfa69  cvttsd2si rcx, xmm0
0x1800cfa6e  mov     r15d, ecx
0x1800cfa71  cmp     ecx, [r14+30h]
0x1800cfa75  cmovbe  r15d, [r14+30h]
0x1800cfa7a  lea     rax, WPP_GLOBAL_Control
0x1800cfa81  cmp     rbx, rax
0x1800cfa84  jz      short loc_1800CFA97
0x1800cfa86  test    dword ptr [rbx+1Ch], 2000h
0x1800cfa8d  jz      short loc_1800CFA97
0x1800cfa8f  cmp     byte ptr [rbx+19h], 5
0x1800cfa93  mov     dl, 1
0x1800cfa95  jnb     short loc_1800CFA9A
0x1800cfa97  mov     dl, r13b; int
0x1800cfa9a  lea     rax, WPP_RECORDER_INITIALIZED
0x1800cfaa1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800cfaa8  jz      short loc_1800CFAB4
0x1800cfaaa  cmp     [rbx+30h], r13w
0x1800cfaaf  mov     r8b, 1
0x1800cfab2  jnz     short loc_1800CFAB7
0x1800cfab4  mov     r8b, r13b; int
0x1800cfab7  test    dl, dl
0x1800cfab9  jnz     short loc_1800CFAC0
0x1800cfabb  test    r8b, r8b
0x1800cfabe  jz      short loc_1800CFB20
0x1800cfac0  mov     eax, [r14+30h]
0x1800cfac4  xorps   xmm2, xmm2
0x1800cfac7  cvtsi2sd xmm2, rax
0x1800cfacc  mov     eax, ecx
0x1800cface  xorps   xmm1, xmm1
0x1800cfad1  cvtsi2sd xmm1, rax
0x1800cfad6  mov     eax, r15d
0x1800cfad9  xorps   xmm0, xmm0
0x1800cfadc  cvtsi2sd xmm0, rax
0x1800cfae1  mov     qword ptr [rsp+1F0h+var_190], r14; char
0x1800cfae6  movsd   qword ptr [rsp+1F0h+var_198], xmm2; char
0x1800cfaec  movsd   qword ptr [rsp+1F0h+var_1A0], xmm1; char
0x1800cfaf2  movsd   qword ptr [rsp+1F0h+var_1A8], xmm0; char
0x1800cfaf8  lea     rcx, WPP_d16748abdc3b3c7a9d56c5dd92375b2b_Traceguids
0x1800cfaff  mov     [rsp+1F0h+MessageGuid], rcx; MessageGuid
0x1800cfb04  mov     [rsp+1F0h+var_1C0], 0Fh; __int16
0x1800cfb0b  mov     [rsp+1F0h+var_1C8], 0Eh; int
0x1800cfb13  mov     r9, [rbx+28h]; int
0x1800cfb17  mov     rcx, [rbx+10h]; int
0x1800cfb1b  call    WPP_RECORDER_AND_TRACE_SF_sgggq
0x1800cfb20  mov     rcx, rdi
0x1800cfb23  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::list<std::wstring>(void)
0x1800cfb28  mov     [rbp+0F0h+var_160], 1
0x1800cfb2f  test    esi, esi
0x1800cfb31  jz      loc_1800CFCC0
0x1800cfb37  mov     eax, esi
0x1800cfb39  xorps   xmm0, xmm0
0x1800cfb3c  cvtsi2sd xmm0, rax
0x1800cfb41  movsd   xmm6, qword ptr [rbp+0F0h+var_120]
0x1800cfb46  movsd   xmm12, qword ptr [rbp+0F0h+var_158]
0x1800cfb4c  subsd   xmm6, xmm12
0x1800cfb51  divsd   xmm6, xmm0
0x1800cfb55  movsd   xmm7, qword ptr [rbp+0F0h+var_120+8]
0x1800cfb5a  movsd   xmm10, qword ptr [rbp+0F0h+var_158+8]
0x1800cfb60  subsd   xmm7, xmm10
0x1800cfb65  divsd   xmm7, xmm0
0x1800cfb69  movsd   xmm9, [rbp+0F0h+var_110]
0x1800cfb6f  movsd   xmm11, [rbp+0F0h+var_148]
0x1800cfb75  subsd   xmm9, xmm11
0x1800cfb7a  divsd   xmm9, xmm0
0x1800cfb7f  mov     r14d, r13d
0x1800cfb82  xorps   xmm0, xmm0
0x1800cfb85  xor     eax, eax
0x1800cfb87  movups  [rbp+0F0h+var_120], xmm0
0x1800cfb8b  mov     [rbp+0F0h+var_110], rax
0x1800cfb8f  xorps   xmm1, xmm1
0x1800cfb92  movups  [rbp+0F0h+var_158], xmm1
0x1800cfb96  movsd   [rbp+0F0h+var_148], xmm8
0x1800cfb9c  addsd   xmm12, xmm6
0x1800cfba1  addsd   xmm10, xmm7
0x1800cfba6  movaps  xmm0, xmm9
0x1800cfbaa  addsd   xmm0, xmm11; X
0x1800cfbaf  movaps  xmm11, xmm0
0x1800cfbb3  movsd   qword ptr [rsp+1F0h+var_188+8], xmm12
0x1800cfbba  call    cos
0x1800cfbbf  mulsd   xmm0, xmm10
0x1800cfbc4  movsd   [rsp+1F0h+var_178], xmm0
0x1800cfbca  movaps  xmm0, xmm11; X
0x1800cfbce  call    _o_sin_0
  ... truncated ...
```
