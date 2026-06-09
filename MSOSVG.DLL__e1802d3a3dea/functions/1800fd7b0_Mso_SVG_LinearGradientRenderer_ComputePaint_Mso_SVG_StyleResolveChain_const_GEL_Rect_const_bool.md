# Mso::SVG::LinearGradientRenderer::ComputePaint(Mso::SVG::StyleResolveChain const &,GEL::Rect const *,bool)

- ea: `0x1800fd7b0`
- end: `0x1800fddba`
- name: `?ComputePaint@LinearGradientRenderer@SVG@Mso@@UEAA?AV?$TCntPtr@UIBrush@GEL@@@3@AEBVStyleResolveChain@23@PEBURect@GEL@@_N@Z`
- size: `1546`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `broker_com_uri`

## callees

- `0x18001aa14`
- `0x18001aa70`
- `0x18001ccd0`
- `0x18001cd30`
- `0x180023800`
- `0x180024120`
- `0x18003f8f0`
- `0x1800fc1a4`
- `0x1800fc1fc`
- `0x1800fc690`
- `0x1800fc6e0`
- `0x1800fc734`
- `0x1800fc784`
- `0x1800fd510`
- `0x1800fd6c4`
- `0x1800fd7b0`
- `0x1801395a4`
- `0x18013e010`
- `0x18013f6fc`
- `0x18013f738`
- `0x18013f760`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fdd97`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fdda5`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fddb3`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fdd97`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fdda5`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fddb3`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800fda64`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800fdd89`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800fda64`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800fdd89`
- `gfx!??0LinearGradientInfo@GEL@@QEAA@XZ` at `0x1800fdae3`
- `gfx!??0LinearGradientInfo@GEL@@QEAA@XZ` at `0x1800fdae3`
- `gfx!??1LinearGradientInfo@GEL@@UEAA@XZ` at `0x1800fdd6f`
- `gfx!??1LinearGradientInfo@GEL@@UEAA@XZ` at `0x1800fdd6f`
- `gfx!?SetShadeColors@GradientInfo@GEL@@QEAAXPEBUGradientStop@2@I@Z` at `0x1800fdbad`
- `gfx!?SetShadeColors@GradientInfo@GEL@@QEAAXPEBUGradientStop@2@I@Z` at `0x1800fdbad`
- `gfx!?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z` at `0x1800fdaa0`
- `gfx!?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z` at `0x1800fdaa0`
- `gfx!?Create@IBrushLinearGradient@GEL@@SA?AV?$TCntPtr@UIBrushLinearGradient@GEL@@@Ofc@@AEBULinearGradientInfo@2@PEBU?$TAffine3x3@N@Math@@@Z` at `0x1800fdd0e`
- `gfx!?Create@IBrushLinearGradient@GEL@@SA?AV?$TCntPtr@UIBrushLinearGradient@GEL@@@Ofc@@AEBULinearGradientInfo@2@PEBU?$TAffine3x3@N@Math@@@Z` at `0x1800fdd0e`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall Mso::SVG::LinearGradientRenderer::ComputePaint(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4,
        char a5)
{
  _QWORD *v9; // r14
  Mso::SVG::LengthResolver *p_si128; // r15
  __int64 v11; // rax
  const struct Mso::SVG::Length *X1; // rax
  double v14; // xmm12_8
  const struct Mso::SVG::Length *Y1; // rax
  double v16; // xmm13_8
  const struct Mso::SVG::Length *X2; // rax
  double v18; // xmm11_8
  const struct Mso::SVG::Length *Y2; // rax
  int v20; // r9d
  double v21; // xmm0_8
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 *v24; // rax
  __int64 *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rax
  void (__fastcall ****v30)(_QWORD); // rax
  void (__fastcall ***v31)(_QWORD); // rcx
  int v32; // r9d
  _QWORD *v33; // rsi
  _QWORD *v34; // r15
  __int64 v35; // rax
  __int64 v36; // rdx
  unsigned __int64 v37; // r8
  double v38; // xmm7_8
  double v39; // xmm8_8
  double v40; // xmm9_8
  double v41; // xmm10_8
  void (__fastcall ***v42)(_QWORD); // rbx
  double v43; // xmm6_8
  double v44; // xmm11_8
  __int128 *TransformedBounds; // rax
  __int64 v46; // rax
  double v47; // xmm0_8
  __m128d *v48; // r8
  float v49; // xmm0_4
  _QWORD *v50; // rax
  void (__fastcall ***v51)(_QWORD); // rsi
  _QWORD v52[2]; // [rsp+38h] [rbp-D0h] BYREF
  Mso::SVG::LengthResolver *v53; // [rsp+48h] [rbp-C0h]
  __int64 v54; // [rsp+50h] [rbp-B8h] BYREF
  char v55; // [rsp+58h] [rbp-B0h]
  __m128i v56; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v57; // [rsp+70h] [rbp-98h]
  _BYTE v58[16]; // [rsp+88h] [rbp-80h] BYREF
  __int128 v59; // [rsp+98h] [rbp-70h]
  __int128 v60; // [rsp+A8h] [rbp-60h]
  int v61; // [rsp+B8h] [rbp-50h]
  int v62; // [rsp+BCh] [rbp-4Ch]
  int Spread; // [rsp+C0h] [rbp-48h]
  __int128 v64; // [rsp+C8h] [rbp-40h]
  __int128 v65; // [rsp+D8h] [rbp-30h]
  float v66; // [rsp+E8h] [rbp-20h]
  char v67; // [rsp+ECh] [rbp-1Ch]
  _QWORD v68[4]; // [rsp+F8h] [rbp-10h] BYREF
  __m128i si128; // [rsp+118h] [rbp+10h] BYREF
  double v70; // [rsp+128h] [rbp+20h]
  __m128d v71; // [rsp+130h] [rbp+28h] BYREF
  __m128d v72; // [rsp+140h] [rbp+38h]
  __int128 v73; // [rsp+150h] [rbp+48h]
  _BYTE v74[168]; // [rsp+160h] [rbp+58h] BYREF
  __int64 v75; // [rsp+238h] [rbp+130h] BYREF

  v9 = (_QWORD *)a1[2];
  if ( !v9 )
  {
LABEL_51:
    CrashWithRecovery(0x1E3C3843u, 0);
    goto LABEL_52;
  }
  _castguard_slow_path_check_user_handled(*v9, 7344, 0);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v70 = sqrt_0(1.0);
  p_si128 = (Mso::SVG::LengthResolver *)&si128;
  if ( (unsigned int)Mso::SVG::GradientContext::GetUnits(v9) != 1 )
    p_si128 = (Mso::SVG::LengthResolver *)a3[2];
  v11 = (*(__int64 (__fastcall **)(_QWORD *))(*v9 + 104LL))(v9);
  v52[0] = 0;
  v52[1] = v11;
  v53 = p_si128;
  if ( a1[11] == a1[10] )
  {
    *a2 = 0;
    return a2;
  }
  X1 = (const struct Mso::SVG::Length *)Mso::SVG::LinearGradientContext::GetX1(v9, &v54);
  v14 = Mso::SVG::LengthResolver::ResolveLength(v53, X1, (const struct Mso::SVG::StyleResolveChain *)v52);
  Y1 = (const struct Mso::SVG::Length *)Mso::SVG::LinearGradientContext::GetY1(v9, &v54);
  v16 = Mso::SVG::LengthResolver::ResolveLength(v53, Y1, (const struct Mso::SVG::StyleResolveChain *)v52);
  X2 = (const struct Mso::SVG::Length *)Mso::SVG::LinearGradientContext::GetX2(v9, &v54);
  v18 = Mso::SVG::LengthResolver::ResolveLength(v53, X2, (const struct Mso::SVG::StyleResolveChain *)v52);
  Y2 = (const struct Mso::SVG::Length *)Mso::SVG::LinearGradientContext::GetY2(v9, &v54);
  v21 = Mso::SVG::LengthResolver::ResolveLength(v53, Y2, (const struct Mso::SVG::StyleResolveChain *)v52);
  v22 = a3[1];
  v23 = *(_QWORD *)(v22 + 16);
  if ( a5 )
  {
    if ( v23 )
    {
      v24 = (__int64 *)(v23 + 1080);
    }
    else
    {
      v24 = (__int64 *)&Mso::SVG::StyleMetaData<9>::initial;
      if ( *(_QWORD *)(v22 + 8) )
        v24 = Mso::SVG::StyleMetaData<9>::inherit;
    }
    if ( !*((_BYTE *)v24 + 8) )
    {
      if ( *a3 )
        Mso::SVG::StyleResolveChain::Get<9>(*a3, v22);
      else
        Mso::SVG::StyleResolveChain::GetNormal<9>(a3, *(_QWORD *)(v22 + 8));
    }
  }
  else
  {
    if ( v23 )
    {
      v25 = (__int64 *)(v23 + 968);
    }
    else
    {
      v25 = (__int64 *)&Mso::SVG::StyleMetaData<12>::initial;
      if ( *(_QWORD *)(v22 + 8) )
        v25 = Mso::SVG::StyleMetaData<12>::inherit;
    }
    if ( !*((_BYTE *)v25 + 8) )
    {
      if ( *a3 )
        Mso::SVG::StyleResolveChain::Get<12>(*a3, v22);
      else
        Mso::SVG::StyleResolveChain::GetNormal<12>(a3, *(_QWORD *)(v22 + 8));
    }
  }
  v55 = 0;
  if ( v21 == v16 && v18 == v14 )
  {
    v26 = a1[10];
    v27 = (a1[11] - v26) >> 3;
    if ( !v27 )
      _invoke_watson(0, 0, 0, 0, 0);
    v28 = *(_QWORD *)(v26 + 8 * (v27 - 1));
    if ( v28 )
    {
      v29 = Mso::SVG::ColorStopRenderer::ComputeColorStop(v28, (unsigned int)v68, (unsigned int)v52, v20, (__int64)&v54);
      v30 = (void (__fastcall ****)(_QWORD))GEL::IBrushSolid::Create(&v75, v29, 0);
      v31 = *v30;
      *a2 = *v30;
      if ( v31 )
        (**v31)(v31);
      if ( v75 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 8LL))(v75);
      return a2;
    }
LABEL_52:
    CrashWithRecovery(0x1E3C3840u, 0);
    JUMPOUT(0x1800FDDB9LL);
  }
  GEL::LinearGradientInfo::LinearGradientInfo((GEL::LinearGradientInfo *)v58);
  v56 = 0;
  v57 = 0;
  v33 = (_QWORD *)a1[10];
  v34 = (_QWORD *)a1[11];
  while ( v33 != v34 )
  {
    if ( !*v33 )
    {
      CrashWithRecovery(0x1E3C3840u, 0);
      goto LABEL_51;
    }
    v35 = Mso::SVG::ColorStopRenderer::ComputeColorStop(*v33, (unsigned int)v68, (unsigned int)v52, v32, (__int64)&v54);
    v36 = v56.m128i_i64[1];
    if ( v56.m128i_i64[1] == v57 )
    {
      std::vector<GEL::GradientStop>::_Emplace_reallocate<GEL::GradientStop const &>(&v56, v56.m128i_i64[1], v35);
    }
    else
    {
      *(_OWORD *)v56.m128i_i64[1] = *(_OWORD *)v35;
      *(_DWORD *)(v36 + 16) = *(_DWORD *)(v35 + 16);
      v56.m128i_i64[1] += 20;
    }
    ++v33;
  }
  v37 = 0xCCCCCCCCCCCCCCCDuLL * ((v56.m128i_i64[1] - v56.m128i_i64[0]) >> 2);
  if ( !v37 )
    _invoke_watson(0, 0, 0, 0, 0);
  v59 = *(_OWORD *)v56.m128i_i64[0];
  v60 = *(_OWORD *)(v56.m128i_i64[0] + 20 * (v37 - 1));
  GEL::GradientInfo::SetShadeColors((GEL::GradientInfo *)v58, (const struct GEL::GradientStop *)v56.m128i_i64[0], v37);
  v61 = 1065353216;
  v62 = 1;
  Spread = Mso::SVG::GradientContext::GetSpread(v9);
  Mso::SVG::GradientRenderer::ComputeTransform(a1, &v71, a4);
  v38 = fmax(v21, v16);
  v39 = fmax(v18, v14);
  v40 = fmin(v16, v21);
  v41 = fmin(v14, v18);
  *(double *)v68 = v41;
  *(double *)&v68[1] = v40;
  *(double *)&v68[2] = v39;
  *(double *)&v68[3] = v38;
  v42 = 0;
  v54 = 0;
  v43 = v21 - v16;
  v44 = v18 - v14;
  if ( (unsigned int)Mso::SVG::GradientContext::GetUnits(v9) == 1 )
  {
    TransformedBounds = (__int128 *)GEL::Rect::GetTransformedBounds(v68, v74, &v71);
    v64 = *TransformedBounds;
    v65 = TransformedBounds[1];
    v46 = (*(__int64 (__fastcall **)(_QWORD *))(*v9 + 112LL))(v9);
    v71 = *(__m128d *)v46;
    v72 = *(__m128d *)(v46 + 16);
    v73 = *(_OWORD *)(v46 + 32);
    v47 = atan2_0(
            v43 * _mm_unpackhi_pd(v72, v72).m128d_f64[0] + v44 * _mm_unpackhi_pd(v71, v71).m128d_f64[0],
            v43 * v72.m128d_f64[0] + v44 * v71.m128d_f64[0]);
    v67 = 1;
    v48 = 0;
  }
  else
  {
    *(double *)&v64 = v41;
    *((double *)&v64 + 1) = v40;
    *(double *)&v65 = v39;
    *((double *)&v65 + 1) = v38;
    v47 = atan2_0(v43, v44);
    v67 = 0;
    v48 = &v71;
  }
  v49 = v47 * 180.0 / 3.141592653589793;
  v66 = v49;
  v50 = (_QWORD *)GEL::IBrushLinearGradient::Create(&v75, v58, v48);
  v51 = (void (__fastcall ***)(_QWORD))*v50;
  if ( *v50 )
  {
    (**v51)(*v50);
    v42 = v51;
  }
  if ( v75 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 8LL))(v75);
  *a2 = v42;
  std::vector<GEL::GradientStop>::_Tidy(&v56);
  v56 = _mm_load_si128((const __m128i *)&_xmm);
  v57 = 19937;
  GEL::LinearGradientInfo::~LinearGradientInfo((GEL::LinearGradientInfo *)v58);
  return a2;
}

```

## disassembly

```asm
0x1800fd7b0  mov     rax, rsp
0x1800fd7b3  mov     [rax+10h], rbx
0x1800fd7b7  mov     [rax+18h], rsi
0x1800fd7bb  mov     [rax+20h], rdi
0x1800fd7bf  push    rbp
0x1800fd7c0  push    r12
0x1800fd7c2  push    r13
0x1800fd7c4  push    r14
0x1800fd7c6  push    r15
0x1800fd7c8  lea     rbp, [rax-128h]
0x1800fd7cf  sub     rsp, 200h
0x1800fd7d6  movaps  xmmword ptr [rax-38h], xmm6
0x1800fd7da  movaps  xmmword ptr [rax-48h], xmm7
0x1800fd7de  movaps  xmmword ptr [rax-58h], xmm8
0x1800fd7e3  movaps  xmmword ptr [rax-68h], xmm9
0x1800fd7e8  movaps  xmmword ptr [rax-78h], xmm10
0x1800fd7ed  movaps  xmmword ptr [rax-88h], xmm11
0x1800fd7f5  movaps  xmmword ptr [rax-98h], xmm12
0x1800fd7fd  movaps  xmmword ptr [rax-0A8h], xmm13
0x1800fd805  mov     r12, r9
0x1800fd808  mov     rsi, r8
0x1800fd80b  mov     rdi, rdx
0x1800fd80e  mov     rbx, rcx
0x1800fd811  xor     r13d, r13d
0x1800fd814  mov     r14, [rcx+10h]
0x1800fd818  test    r14, r14
0x1800fd81b  jz      loc_1800FDD9E
0x1800fd821  xor     r8d, r8d
0x1800fd824  mov     edx, 1CB0h
0x1800fd829  mov     rcx, [r14]
0x1800fd82c  call    __castguard_slow_path_check_user_handled
0x1800fd831  movdqa  xmm0, cs:__xmm@3ff00000000000003ff0000000000000
0x1800fd839  movups  [rbp+120h+var_110], xmm0
0x1800fd83d  movsd   xmm0, cs:__real@3ff0000000000000; X
0x1800fd845  call    sqrt_0
0x1800fd84a  movsd   [rbp+120h+var_100], xmm0
0x1800fd84f  mov     rcx, r14
0x1800fd852  call    ?GetUnits@GradientContext@SVG@Mso@@QEBA?AW4GradientUnits@23@XZ; Mso::SVG::GradientContext::GetUnits(void)
0x1800fd857  cmp     eax, 1
0x1800fd85a  lea     r15, [rbp+120h+var_110]
0x1800fd85e  jz      short loc_1800FD864
0x1800fd860  mov     r15, [rsi+10h]
0x1800fd864  mov     rax, [r14]
0x1800fd867  mov     rcx, r14
0x1800fd86a  mov     rax, [rax+68h]
0x1800fd86e  call    cs:__guard_dispatch_icall_fptr
0x1800fd874  mov     [rsp+220h+var_1F0], r13
0x1800fd879  mov     [rsp+220h+var_1E8], rax
0x1800fd87e  mov     [rsp+220h+var_1E0], r15
0x1800fd883  mov     rax, [rbx+58h]
0x1800fd887  cmp     rax, [rbx+50h]
0x1800fd88b  jnz     short loc_1800FD8DC
0x1800fd88d  mov     [rdi], r13
0x1800fd890  mov     rax, rdi
0x1800fd893  lea     r11, [rsp+220h+var_20]
0x1800fd89b  mov     rbx, [r11+38h]
0x1800fd89f  mov     rsi, [r11+40h]
0x1800fd8a3  mov     rdi, [r11+48h]
0x1800fd8a7  movaps  xmm6, xmmword ptr [r11-10h]
0x1800fd8ac  movaps  xmm7, xmmword ptr [r11-20h]
0x1800fd8b1  movaps  xmm8, xmmword ptr [r11-30h]
0x1800fd8b6  movaps  xmm9, xmmword ptr [r11-40h]
0x1800fd8bb  movaps  xmm10, xmmword ptr [r11-50h]
0x1800fd8c0  movaps  xmm11, xmmword ptr [r11-60h]
0x1800fd8c5  movaps  xmm12, xmmword ptr [r11-70h]
0x1800fd8ca  movaps  xmm13, xmmword ptr [r11-80h]
0x1800fd8cf  mov     rsp, r11
0x1800fd8d2  pop     r15
0x1800fd8d4  pop     r14
0x1800fd8d6  pop     r13
0x1800fd8d8  pop     r12
0x1800fd8da  pop     rbp
0x1800fd8db  retn
0x1800fd8dc  lea     rdx, [rsp+220h+var_1D8]
0x1800fd8e1  mov     rcx, r14
0x1800fd8e4  call    ?GetX1@LinearGradientContext@SVG@Mso@@QEBA?AULength@23@XZ; Mso::SVG::LinearGradientContext::GetX1(void)
0x1800fd8e9  lea     r8, [rsp+220h+var_1F0]; struct Mso::SVG::StyleResolveChain *
0x1800fd8ee  mov     rdx, rax; struct Mso::SVG::Length *
0x1800fd8f1  mov     rcx, [rsp+220h+var_1E0]; this
0x1800fd8f6  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x1800fd8fb  movaps  xmm12, xmm0
0x1800fd8ff  lea     rdx, [rsp+220h+var_1D8]
0x1800fd904  mov     rcx, r14
0x1800fd907  call    ?GetY1@LinearGradientContext@SVG@Mso@@QEBA?AULength@23@XZ; Mso::SVG::LinearGradientContext::GetY1(void)
0x1800fd90c  lea     r8, [rsp+220h+var_1F0]; struct Mso::SVG::StyleResolveChain *
0x1800fd911  mov     rdx, rax; struct Mso::SVG::Length *
0x1800fd914  mov     rcx, [rsp+220h+var_1E0]; this
0x1800fd919  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x1800fd91e  movaps  xmm13, xmm0
0x1800fd922  lea     rdx, [rsp+220h+var_1D8]
0x1800fd927  mov     rcx, r14
0x1800fd92a  call    ?GetX2@LinearGradientContext@SVG@Mso@@QEBA?AULength@23@XZ; Mso::SVG::LinearGradientContext::GetX2(void)
0x1800fd92f  lea     r8, [rsp+220h+var_1F0]; struct Mso::SVG::StyleResolveChain *
0x1800fd934  mov     rdx, rax; struct Mso::SVG::Length *
0x1800fd937  mov     rcx, [rsp+220h+var_1E0]; this
0x1800fd93c  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x1800fd941  movaps  xmm11, xmm0
0x1800fd945  lea     rdx, [rsp+220h+var_1D8]
0x1800fd94a  mov     rcx, r14
0x1800fd94d  call    ?GetY2@LinearGradientContext@SVG@Mso@@QEBA?AULength@23@XZ; Mso::SVG::LinearGradientContext::GetY2(void)
0x1800fd952  lea     r8, [rsp+220h+var_1F0]; struct Mso::SVG::StyleResolveChain *
0x1800fd957  mov     rdx, rax; struct Mso::SVG::Length *
0x1800fd95a  mov     rcx, [rsp+220h+var_1E0]; this
0x1800fd95f  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x1800fd964  movaps  xmm6, xmm0
0x1800fd967  mov     rdx, [rsi+8]
0x1800fd96b  mov     rax, [rdx+10h]
0x1800fd96f  cmp     [rbp+120h+arg_20], r13b
0x1800fd976  jz      short loc_1800FD9C4
0x1800fd978  test    rax, rax
0x1800fd97b  jz      short loc_1800FD985
0x1800fd97d  add     rax, 438h
0x1800fd983  jmp     short loc_1800FD999
0x1800fd985  cmp     [rdx+8], r13
0x1800fd989  lea     rax, ?initial@?$StyleMetaData@$08@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<9>::initial
0x1800fd990  jz      short loc_1800FD999
0x1800fd992  lea     rax, ?inherit@?$StyleMetaData@$08@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<9>::inherit
0x1800fd999  mov     ecx, 8
0x1800fd99e  cmp     [rax+8], r13b
0x1800fd9a2  jnz     short loc_1800FDA0E
0x1800fd9a4  mov     rax, [rsi]
0x1800fd9a7  test    rax, rax
0x1800fd9aa  jz      short loc_1800FD9B6
0x1800fd9ac  mov     rcx, rax
0x1800fd9af  call    ??$Get@$08@StyleResolveChain@SVG@Mso@@QEBAAEBNXZ; Mso::SVG::StyleResolveChain::Get<9>(void)
0x1800fd9b4  jmp     short loc_1800FDA0E
0x1800fd9b6  mov     rdx, [rdx+rcx]
0x1800fd9ba  mov     rcx, rsi
0x1800fd9bd  call    ??$GetNormal@$08@StyleResolveChain@SVG@Mso@@AEBAAEBNAEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<9>(Mso::SVG::Style const &)
0x1800fd9c2  jmp     short loc_1800FDA0E
0x1800fd9c4  test    rax, rax
0x1800fd9c7  jz      short loc_1800FD9D1
0x1800fd9c9  add     rax, 3C8h
0x1800fd9cf  jmp     short loc_1800FD9E5
0x1800fd9d1  cmp     [rdx+8], r13
0x1800fd9d5  lea     rax, ?initial@?$StyleMetaData@$0M@@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<12>::initial
0x1800fd9dc  jz      short loc_1800FD9E5
0x1800fd9de  lea     rax, ?inherit@?$StyleMetaData@$0M@@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<12>::inherit
0x1800fd9e5  mov     ecx, 8
0x1800fd9ea  cmp     [rax+8], r13b
0x1800fd9ee  jnz     short loc_1800FDA0E
0x1800fd9f0  mov     rax, [rsi]
0x1800fd9f3  test    rax, rax
0x1800fd9f6  jz      short loc_1800FDA02
0x1800fd9f8  mov     rcx, rax
0x1800fd9fb  call    ??$Get@$0M@@StyleResolveChain@SVG@Mso@@QEBAAEBNXZ; Mso::SVG::StyleResolveChain::Get<12>(void)
0x1800fda00  jmp     short loc_1800FDA0E
0x1800fda02  mov     rdx, [rdx+rcx]
0x1800fda06  mov     rcx, rsi
0x1800fda09  call    ??$GetNormal@$0M@@StyleResolveChain@SVG@Mso@@AEBAAEBNAEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<12>(Mso::SVG::Style const &)
0x1800fda0e  movsd   xmm7, qword ptr [rax]
0x1800fda12  cvtpd2ps xmm7, xmm7
0x1800fda16  mov     byte ptr [rsp+220h+var_1D0], r13b
0x1800fda1b  ucomisd xmm6, xmm13
0x1800fda20  jp      loc_1800FDADF
0x1800fda26  jnz     loc_1800FDADF
0x1800fda2c  ucomisd xmm11, xmm12
0x1800fda31  jp      loc_1800FDADF
0x1800fda37  jnz     loc_1800FDADF
0x1800fda3d  mov     rcx, [rbx+50h]
0x1800fda41  mov     rax, [rbx+58h]
0x1800fda45  sub     rax, rcx
0x1800fda48  sar     rax, 3
0x1800fda4c  lea     rdx, [rax-1]
0x1800fda50  cmp     rdx, rax
0x1800fda53  jb      short loc_1800FDA6B
0x1800fda55  mov     [rsp+220h+Reserved], r13; Reserved
0x1800fda5a  xor     r9d, r9d; LineNo
0x1800fda5d  xor     r8d, r8d; FileName
0x1800fda60  xor     edx, edx; FunctionName
0x1800fda62  xor     ecx, ecx; Expression
0x1800fda64  call    cs:__imp__invoke_watson
0x1800fda6b  mov     rcx, [rcx+rdx*8]
0x1800fda6f  test    rcx, rcx
0x1800fda72  jz      loc_1800FDDAC
0x1800fda78  lea     rax, [rsp+220h+var_1D8]
0x1800fda7d  mov     [rsp+220h+Reserved], rax
0x1800fda82  movaps  xmm3, xmm7
0x1800fda85  lea     r8, [rsp+220h+var_1F0]
0x1800fda8a  lea     rdx, [rbp+120h+var_130]
0x1800fda8e  call    ?ComputeColorStop@ColorStopRenderer@SVG@Mso@@QEBA?AUGradientStop@GEL@@AEBVStyleResolveChain@23@MAEAV?$optional@N@std@@@Z; Mso::SVG::ColorStopRenderer::ComputeColorStop(Mso::SVG::StyleResolveChain const &,float,std::optional<double> &)
0x1800fda93  mov     rdx, rax
0x1800fda96  xor     r8d, r8d
0x1800fda99  lea     rcx, [rbp+120h+arg_0]
0x1800fdaa0  call    cs:__imp_?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z; GEL::IBrushSolid::Create(GEL::Color const &,GEL::CropInfo const *)
0x1800fdaa6  mov     rcx, [rax]
0x1800fdaa9  mov     [rdi], rcx
0x1800fdaac  test    rcx, rcx
0x1800fdaaf  jz      short loc_1800FDABD
0x1800fdab1  mov     rax, [rcx]
0x1800fdab4  mov     rax, [rax]
0x1800fdab7  call    cs:__guard_dispatch_icall_fptr
0x1800fdabd  mov     rcx, [rbp+120h+arg_0]
0x1800fdac4  test    rcx, rcx
0x1800fdac7  jz      loc_1800FD890
0x1800fdacd  mov     rax, [rcx]
0x1800fdad0  mov     rax, [rax+8]
0x1800fdad4  call    cs:__guard_dispatch_icall_fptr
0x1800fdada  jmp     loc_1800FD890
0x1800fdadf  lea     rcx, [rbp+120h+var_1A0]
0x1800fdae3  call    cs:__imp_??0LinearGradientInfo@GEL@@QEAA@XZ; GEL::LinearGradientInfo::LinearGradientInfo(void)
0x1800fdae9  nop
0x1800fdaea  xorps   xmm0, xmm0
0x1800fdaed  movdqu  [rsp+220h+var_1D0+8], xmm0
0x1800fdaf3  mov     [rsp+220h+var_1B8], r13
0x1800fdaf8  mov     rsi, [rbx+50h]
0x1800fdafc  mov     r15, [rbx+58h]
0x1800fdb00  jmp     short loc_1800FDB5A
0x1800fdb02  mov     rcx, [rsi]
0x1800fdb05  test    rcx, rcx
0x1800fdb08  jz      loc_1800FDD90
0x1800fdb0e  lea     rax, [rsp+220h+var_1D8]
0x1800fdb13  mov     [rsp+220h+Reserved], rax
0x1800fdb18  movaps  xmm3, xmm7
0x1800fdb1b  lea     r8, [rsp+220h+var_1F0]
0x1800fdb20  lea     rdx, [rbp+120h+var_130]
0x1800fdb24  call    ?ComputeColorStop@ColorStopRenderer@SVG@Mso@@QEBA?AUGradientStop@GEL@@AEBVStyleResolveChain@23@MAEAV?$optional@N@std@@@Z; Mso::SVG::ColorStopRenderer::ComputeColorStop(Mso::SVG::StyleResolveChain const &,float,std::optional<double> &)
0x1800fdb29  mov     rdx, [rsp+220h+var_1C0]
0x1800fdb2e  cmp     rdx, [rsp+220h+var_1B8]
0x1800fdb33  jz      short loc_1800FDB49
0x1800fdb35  movups  xmm0, xmmword ptr [rax]
0x1800fdb38  movups  xmmword ptr [rdx], xmm0
0x1800fdb3b  mov     eax, [rax+10h]
0x1800fdb3e  mov     [rdx+10h], eax
0x1800fdb41  add     [rsp+220h+var_1C0], 14h
0x1800fdb47  jmp     short loc_1800FDB56
0x1800fdb49  mov     r8, rax
0x1800fdb4c  lea     rcx, [rsp+220h+var_1D0+8]
0x1800fdb51  call    ??$_Emplace_reallocate@AEBUGradientStop@GEL@@@?$vector@UGradientStop@GEL@@V?$allocator@UGradientStop@GEL@@@std@@@std@@AEAAPEAUGradientStop@GEL@@QEAU23@AEBU23@@Z; std::vector<GEL::GradientStop>::_Emplace_reallocate<GEL::GradientStop const &>(GEL::GradientStop * const,GEL::GradientStop const &)
0x1800fdb56  add     rsi, 8
0x1800fdb5a  cmp     rsi, r15
0x1800fdb5d  jnz     short loc_1800FDB02
0x1800fdb5f  mov     r8, [rsp+220h+var_1C0]
0x1800fdb64  mov     rdx, qword ptr [rsp+220h+var_1D0+8]
0x1800fdb69  sub     r8, rdx
0x1800fdb6c  sar     r8, 2
0x1800fdb70  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800fdb7a  imul    r8, rax
0x1800fdb7e  test    r8, r8
0x1800fdb81  jz      loc_1800FDD7A
0x1800fdb87  movups  xmm0, xmmword ptr [rdx]
0x1800fdb8a  movdqu  [rbp+120h+var_190], xmm0
0x1800fdb8f  lea     rax, [r8-1]
0x1800fdb93  cmp     rax, r8
0x1800fdb96  jnb     loc_1800FDD7A
0x1800fdb9c  lea     rax, [rax+rax*4]
0x1800fdba0  movups  xmm0, xmmword ptr [rdx+rax*4]
0x1800fdba4  movdqu  [rbp+120h+var_180], xmm0
0x1800fdba9  lea     rcx, [rbp+120h+var_1A0]
0x1800fdbad  call    cs:__imp_?SetShadeColors@GradientInfo@GEL@@QEAAXPEBUGradientStop@2@I@Z; GEL::GradientInfo::SetShadeColors(GEL::GradientStop const *,uint)
0x1800fdbb3  mov     [rbp+120h+var_170], 3F800000h
0x1800fdbba  mov     [rbp+120h+var_16C], 1
0x1800fdbc1  mov     rcx, r14
0x1800fdbc4  call    ?GetSpread@GradientContext@SVG@Mso@@QEBA?AW4ExtendMode@ARC@@XZ; Mso::SVG::GradientContext::GetSpread(void)
0x1800fdbc9  mov     [rbp+120h+var_168], eax
0x1800fdbcc  mov     r8, r12
0x1800fdbcf  lea     rdx, [rbp+120h+var_F8]
0x1800fdbd3  mov     rcx, rbx
0x1800fdbd6  call    ?ComputeTransform@GradientRenderer@SVG@Mso@@QEBA?AU?$TAffine3x3@N@Math@@PEBURect@GEL@@@Z; Mso::SVG::GradientRenderer::ComputeTransform(GEL::Rect const *)
0x1800fdbdb  movaps  xmm7, xmm6
0x1800fdbde  maxsd   xmm7, xmm13
0x1800fdbe3  movaps  xmm8, xmm11
0x1800fdbe7  maxsd   xmm8, xmm12
0x1800fdbec  movaps  xmm9, xmm13
0x1800fdbf0  minsd   xmm9, xmm6
0x1800fdbf5  movaps  xmm10, xmm12
0x1800fdbf9  minsd   xmm10, xmm11
0x1800fdbfe  movsd   [rbp+120h+var_130], xmm10
0x1800fdc04  movsd   [rbp+120h+var_128], xmm9
0x1800fdc0a  movsd   [rbp+120h+var_120], xmm8
0x1800fdc10  movsd   [rbp+120h+var_118], xmm7
0x1800fdc15  mov     rbx, r13
0x1800fdc18  mov     [rsp+220h+var_1D8], rbx
0x1800fdc1d  subsd   xmm6, xmm13
0x1800fdc22  subsd   xmm11, xmm12
0x1800fdc27  mov     rcx, r14
0x1800fdc2a  call    ?GetUnits@GradientContext@SVG@Mso@@QEBA?AW4GradientUnits@23@XZ; Mso::SVG::GradientContext::GetUnits(void)
0x1800fdc2f  cmp     eax, 1
0x1800fdc32  jnz     loc_1800FDCBF
0x1800fdc38  lea     r8, [rbp+120h+var_F8]
0x1800fdc3c  lea     rdx, [rbp+120h+var_C8]
0x1800fdc40  lea     rcx, [rbp+120h+var_130]
0x1800fdc44  call    ?GetTransformedBounds@Rect@GEL@@QEBA?AU12@AEBU?$TAffine3x3@N@Math@@@Z; GEL::Rect::GetTransformedBounds(Math::TAffine3x3<double> const &)
0x1800fdc49  movups  xmm0, xmmword ptr [rax]
0x1800fdc4c  movaps  [rbp+120h+var_160], xmm0
0x1800fdc50  movups  xmm1, xmmword ptr [rax+10h]
0x1800fdc54  movaps  [rbp+120h+var_150], xmm1
0x1800fdc58  mov     rax, [r14]
0x1800fdc5b  mov     rcx, r14
0x1800fdc5e  mov     rax, [rax+70h]
0x1800fdc62  call    cs:__guard_dispatch_icall_fptr
0x1800fdc68  movups  xmm5, xmmword ptr [rax]
0x1800fdc6b  movups  [rbp+120h+var_F8], xmm5
0x1800fdc6f  movups  xmm4, xmmword ptr [rax+10h]
0x1800fdc73  movups  [rbp+120h+var_E8], xmm4
0x1800fdc77  movups  xmm0, xmmword ptr [rax+20h]
0x1800fdc7b  movups  [rbp+120h+var_D8], xmm0
0x1800fdc7f  movaps  xmm0, xmm6
0x1800fdc82  movaps  xmm1, xmm4
0x1800fdc85  unpckhpd xmm1, xmm4
  ... truncated ...
```
