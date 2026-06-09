# Mso::SVG::LinearGradientRenderer::ComputePaint(Mso::SVG::StyleResolveChain const &,GEL::Rect const *,bool)

- ea: `0x1800fd7d0`
- end: `0x1800fddda`
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
- `0x1800fc1c4`
- `0x1800fc21c`
- `0x1800fc6b0`
- `0x1800fc700`
- `0x1800fc754`
- `0x1800fc7a4`
- `0x1800fd530`
- `0x1800fd6e4`
- `0x1800fd7d0`
- `0x1801395e4`
- `0x18013e0c0`
- `0x18013f7ac`
- `0x18013f7e8`
- `0x18013f810`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fddb7`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fddc5`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fddd3`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fddb7`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fddc5`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fddd3`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800fda84`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800fdda9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800fda84`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800fdda9`
- `gfx!??0LinearGradientInfo@GEL@@QEAA@XZ` at `0x1800fdb03`
- `gfx!??0LinearGradientInfo@GEL@@QEAA@XZ` at `0x1800fdb03`
- `gfx!??1LinearGradientInfo@GEL@@UEAA@XZ` at `0x1800fdd8f`
- `gfx!??1LinearGradientInfo@GEL@@UEAA@XZ` at `0x1800fdd8f`
- `gfx!?SetShadeColors@GradientInfo@GEL@@QEAAXPEBUGradientStop@2@I@Z` at `0x1800fdbcd`
- `gfx!?SetShadeColors@GradientInfo@GEL@@QEAAXPEBUGradientStop@2@I@Z` at `0x1800fdbcd`
- `gfx!?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z` at `0x1800fdac0`
- `gfx!?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z` at `0x1800fdac0`
- `gfx!?Create@IBrushLinearGradient@GEL@@SA?AV?$TCntPtr@UIBrushLinearGradient@GEL@@@Ofc@@AEBULinearGradientInfo@2@PEBU?$TAffine3x3@N@Math@@@Z` at `0x1800fdd2e`
- `gfx!?Create@IBrushLinearGradient@GEL@@SA?AV?$TCntPtr@UIBrushLinearGradient@GEL@@@Ofc@@AEBULinearGradientInfo@2@PEBU?$TAffine3x3@N@Math@@@Z` at `0x1800fdd2e`

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
    JUMPOUT(0x1800FDDD9LL);
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
0x1800fd7d0  mov     rax, rsp
0x1800fd7d3  mov     [rax+10h], rbx
0x1800fd7d7  mov     [rax+18h], rsi
0x1800fd7db  mov     [rax+20h], rdi
0x1800fd7df  push    rbp
0x1800fd7e0  push    r12
0x1800fd7e2  push    r13
0x1800fd7e4  push    r14
0x1800fd7e6  push    r15
0x1800fd7e8  lea     rbp, [rax-128h]
0x1800fd7ef  sub     rsp, 200h
0x1800fd7f6  movaps  xmmword ptr [rax-38h], xmm6
0x1800fd7fa  movaps  xmmword ptr [rax-48h], xmm7
0x1800fd7fe  movaps  xmmword ptr [rax-58h], xmm8
0x1800fd803  movaps  xmmword ptr [rax-68h], xmm9
0x1800fd808  movaps  xmmword ptr [rax-78h], xmm10
0x1800fd80d  movaps  xmmword ptr [rax-88h], xmm11
0x1800fd815  movaps  xmmword ptr [rax-98h], xmm12
0x1800fd81d  movaps  xmmword ptr [rax-0A8h], xmm13
0x1800fd825  mov     r12, r9
0x1800fd828  mov     rsi, r8
0x1800fd82b  mov     rdi, rdx
0x1800fd82e  mov     rbx, rcx
0x1800fd831  xor     r13d, r13d
0x1800fd834  mov     r14, [rcx+10h]
0x1800fd838  test    r14, r14
0x1800fd83b  jz      loc_1800FDDBE
0x1800fd841  xor     r8d, r8d
0x1800fd844  mov     edx, 1CB0h
0x1800fd849  mov     rcx, [r14]
0x1800fd84c  call    __castguard_slow_path_check_user_handled
0x1800fd851  movdqa  xmm0, cs:__xmm@3ff00000000000003ff0000000000000
0x1800fd859  movups  [rbp+120h+var_110], xmm0
0x1800fd85d  movsd   xmm0, cs:__real@3ff0000000000000; X
0x1800fd865  call    sqrt_0
0x1800fd86a  movsd   [rbp+120h+var_100], xmm0
0x1800fd86f  mov     rcx, r14
0x1800fd872  call    ?GetUnits@GradientContext@SVG@Mso@@QEBA?AW4GradientUnits@23@XZ; Mso::SVG::GradientContext::GetUnits(void)
0x1800fd877  cmp     eax, 1
0x1800fd87a  lea     r15, [rbp+120h+var_110]
0x1800fd87e  jz      short loc_1800FD884
0x1800fd880  mov     r15, [rsi+10h]
0x1800fd884  mov     rax, [r14]
0x1800fd887  mov     rcx, r14
0x1800fd88a  mov     rax, [rax+68h]
0x1800fd88e  call    cs:__guard_dispatch_icall_fptr
0x1800fd894  mov     [rsp+220h+var_1F0], r13
0x1800fd899  mov     [rsp+220h+var_1E8], rax
0x1800fd89e  mov     [rsp+220h+var_1E0], r15
0x1800fd8a3  mov     rax, [rbx+58h]
0x1800fd8a7  cmp     rax, [rbx+50h]
0x1800fd8ab  jnz     short loc_1800FD8FC
0x1800fd8ad  mov     [rdi], r13
0x1800fd8b0  mov     rax, rdi
0x1800fd8b3  lea     r11, [rsp+220h+var_20]
0x1800fd8bb  mov     rbx, [r11+38h]
0x1800fd8bf  mov     rsi, [r11+40h]
0x1800fd8c3  mov     rdi, [r11+48h]
0x1800fd8c7  movaps  xmm6, xmmword ptr [r11-10h]
0x1800fd8cc  movaps  xmm7, xmmword ptr [r11-20h]
0x1800fd8d1  movaps  xmm8, xmmword ptr [r11-30h]
0x1800fd8d6  movaps  xmm9, xmmword ptr [r11-40h]
0x1800fd8db  movaps  xmm10, xmmword ptr [r11-50h]
0x1800fd8e0  movaps  xmm11, xmmword ptr [r11-60h]
0x1800fd8e5  movaps  xmm12, xmmword ptr [r11-70h]
0x1800fd8ea  movaps  xmm13, xmmword ptr [r11-80h]
0x1800fd8ef  mov     rsp, r11
0x1800fd8f2  pop     r15
0x1800fd8f4  pop     r14
0x1800fd8f6  pop     r13
0x1800fd8f8  pop     r12
0x1800fd8fa  pop     rbp
0x1800fd8fb  retn
0x1800fd8fc  lea     rdx, [rsp+220h+var_1D8]
0x1800fd901  mov     rcx, r14
0x1800fd904  call    ?GetX1@LinearGradientContext@SVG@Mso@@QEBA?AULength@23@XZ; Mso::SVG::LinearGradientContext::GetX1(void)
0x1800fd909  lea     r8, [rsp+220h+var_1F0]; struct Mso::SVG::StyleResolveChain *
0x1800fd90e  mov     rdx, rax; struct Mso::SVG::Length *
0x1800fd911  mov     rcx, [rsp+220h+var_1E0]; this
0x1800fd916  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x1800fd91b  movaps  xmm12, xmm0
0x1800fd91f  lea     rdx, [rsp+220h+var_1D8]
0x1800fd924  mov     rcx, r14
0x1800fd927  call    ?GetY1@LinearGradientContext@SVG@Mso@@QEBA?AULength@23@XZ; Mso::SVG::LinearGradientContext::GetY1(void)
0x1800fd92c  lea     r8, [rsp+220h+var_1F0]; struct Mso::SVG::StyleResolveChain *
0x1800fd931  mov     rdx, rax; struct Mso::SVG::Length *
0x1800fd934  mov     rcx, [rsp+220h+var_1E0]; this
0x1800fd939  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x1800fd93e  movaps  xmm13, xmm0
0x1800fd942  lea     rdx, [rsp+220h+var_1D8]
0x1800fd947  mov     rcx, r14
0x1800fd94a  call    ?GetX2@LinearGradientContext@SVG@Mso@@QEBA?AULength@23@XZ; Mso::SVG::LinearGradientContext::GetX2(void)
0x1800fd94f  lea     r8, [rsp+220h+var_1F0]; struct Mso::SVG::StyleResolveChain *
0x1800fd954  mov     rdx, rax; struct Mso::SVG::Length *
0x1800fd957  mov     rcx, [rsp+220h+var_1E0]; this
0x1800fd95c  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x1800fd961  movaps  xmm11, xmm0
0x1800fd965  lea     rdx, [rsp+220h+var_1D8]
0x1800fd96a  mov     rcx, r14
0x1800fd96d  call    ?GetY2@LinearGradientContext@SVG@Mso@@QEBA?AULength@23@XZ; Mso::SVG::LinearGradientContext::GetY2(void)
0x1800fd972  lea     r8, [rsp+220h+var_1F0]; struct Mso::SVG::StyleResolveChain *
0x1800fd977  mov     rdx, rax; struct Mso::SVG::Length *
0x1800fd97a  mov     rcx, [rsp+220h+var_1E0]; this
0x1800fd97f  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x1800fd984  movaps  xmm6, xmm0
0x1800fd987  mov     rdx, [rsi+8]
0x1800fd98b  mov     rax, [rdx+10h]
0x1800fd98f  cmp     [rbp+120h+arg_20], r13b
0x1800fd996  jz      short loc_1800FD9E4
0x1800fd998  test    rax, rax
0x1800fd99b  jz      short loc_1800FD9A5
0x1800fd99d  add     rax, 438h
0x1800fd9a3  jmp     short loc_1800FD9B9
0x1800fd9a5  cmp     [rdx+8], r13
0x1800fd9a9  lea     rax, ?initial@?$StyleMetaData@$08@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<9>::initial
0x1800fd9b0  jz      short loc_1800FD9B9
0x1800fd9b2  lea     rax, ?inherit@?$StyleMetaData@$08@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<9>::inherit
0x1800fd9b9  mov     ecx, 8
0x1800fd9be  cmp     [rax+8], r13b
0x1800fd9c2  jnz     short loc_1800FDA2E
0x1800fd9c4  mov     rax, [rsi]
0x1800fd9c7  test    rax, rax
0x1800fd9ca  jz      short loc_1800FD9D6
0x1800fd9cc  mov     rcx, rax
0x1800fd9cf  call    ??$Get@$08@StyleResolveChain@SVG@Mso@@QEBAAEBNXZ; Mso::SVG::StyleResolveChain::Get<9>(void)
0x1800fd9d4  jmp     short loc_1800FDA2E
0x1800fd9d6  mov     rdx, [rdx+rcx]
0x1800fd9da  mov     rcx, rsi
0x1800fd9dd  call    ??$GetNormal@$08@StyleResolveChain@SVG@Mso@@AEBAAEBNAEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<9>(Mso::SVG::Style const &)
0x1800fd9e2  jmp     short loc_1800FDA2E
0x1800fd9e4  test    rax, rax
0x1800fd9e7  jz      short loc_1800FD9F1
0x1800fd9e9  add     rax, 3C8h
0x1800fd9ef  jmp     short loc_1800FDA05
0x1800fd9f1  cmp     [rdx+8], r13
0x1800fd9f5  lea     rax, ?initial@?$StyleMetaData@$0M@@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<12>::initial
0x1800fd9fc  jz      short loc_1800FDA05
0x1800fd9fe  lea     rax, ?inherit@?$StyleMetaData@$0M@@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<12>::inherit
0x1800fda05  mov     ecx, 8
0x1800fda0a  cmp     [rax+8], r13b
0x1800fda0e  jnz     short loc_1800FDA2E
0x1800fda10  mov     rax, [rsi]
0x1800fda13  test    rax, rax
0x1800fda16  jz      short loc_1800FDA22
0x1800fda18  mov     rcx, rax
0x1800fda1b  call    ??$Get@$0M@@StyleResolveChain@SVG@Mso@@QEBAAEBNXZ; Mso::SVG::StyleResolveChain::Get<12>(void)
0x1800fda20  jmp     short loc_1800FDA2E
0x1800fda22  mov     rdx, [rdx+rcx]
0x1800fda26  mov     rcx, rsi
0x1800fda29  call    ??$GetNormal@$0M@@StyleResolveChain@SVG@Mso@@AEBAAEBNAEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<12>(Mso::SVG::Style const &)
0x1800fda2e  movsd   xmm7, qword ptr [rax]
0x1800fda32  cvtpd2ps xmm7, xmm7
0x1800fda36  mov     byte ptr [rsp+220h+var_1D0], r13b
0x1800fda3b  ucomisd xmm6, xmm13
0x1800fda40  jp      loc_1800FDAFF
0x1800fda46  jnz     loc_1800FDAFF
0x1800fda4c  ucomisd xmm11, xmm12
0x1800fda51  jp      loc_1800FDAFF
0x1800fda57  jnz     loc_1800FDAFF
0x1800fda5d  mov     rcx, [rbx+50h]
0x1800fda61  mov     rax, [rbx+58h]
0x1800fda65  sub     rax, rcx
0x1800fda68  sar     rax, 3
0x1800fda6c  lea     rdx, [rax-1]
0x1800fda70  cmp     rdx, rax
0x1800fda73  jb      short loc_1800FDA8B
0x1800fda75  mov     [rsp+220h+Reserved], r13; Reserved
0x1800fda7a  xor     r9d, r9d; LineNo
0x1800fda7d  xor     r8d, r8d; FileName
0x1800fda80  xor     edx, edx; FunctionName
0x1800fda82  xor     ecx, ecx; Expression
0x1800fda84  call    cs:__imp__invoke_watson
0x1800fda8b  mov     rcx, [rcx+rdx*8]
0x1800fda8f  test    rcx, rcx
0x1800fda92  jz      loc_1800FDDCC
0x1800fda98  lea     rax, [rsp+220h+var_1D8]
0x1800fda9d  mov     [rsp+220h+Reserved], rax
0x1800fdaa2  movaps  xmm3, xmm7
0x1800fdaa5  lea     r8, [rsp+220h+var_1F0]
0x1800fdaaa  lea     rdx, [rbp+120h+var_130]
0x1800fdaae  call    ?ComputeColorStop@ColorStopRenderer@SVG@Mso@@QEBA?AUGradientStop@GEL@@AEBVStyleResolveChain@23@MAEAV?$optional@N@std@@@Z; Mso::SVG::ColorStopRenderer::ComputeColorStop(Mso::SVG::StyleResolveChain const &,float,std::optional<double> &)
0x1800fdab3  mov     rdx, rax
0x1800fdab6  xor     r8d, r8d
0x1800fdab9  lea     rcx, [rbp+120h+arg_0]
0x1800fdac0  call    cs:__imp_?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z; GEL::IBrushSolid::Create(GEL::Color const &,GEL::CropInfo const *)
0x1800fdac6  mov     rcx, [rax]
0x1800fdac9  mov     [rdi], rcx
0x1800fdacc  test    rcx, rcx
0x1800fdacf  jz      short loc_1800FDADD
0x1800fdad1  mov     rax, [rcx]
0x1800fdad4  mov     rax, [rax]
0x1800fdad7  call    cs:__guard_dispatch_icall_fptr
0x1800fdadd  mov     rcx, [rbp+120h+arg_0]
0x1800fdae4  test    rcx, rcx
0x1800fdae7  jz      loc_1800FD8B0
0x1800fdaed  mov     rax, [rcx]
0x1800fdaf0  mov     rax, [rax+8]
0x1800fdaf4  call    cs:__guard_dispatch_icall_fptr
0x1800fdafa  jmp     loc_1800FD8B0
0x1800fdaff  lea     rcx, [rbp+120h+var_1A0]
0x1800fdb03  call    cs:__imp_??0LinearGradientInfo@GEL@@QEAA@XZ; GEL::LinearGradientInfo::LinearGradientInfo(void)
0x1800fdb09  nop
0x1800fdb0a  xorps   xmm0, xmm0
0x1800fdb0d  movdqu  [rsp+220h+var_1D0+8], xmm0
0x1800fdb13  mov     [rsp+220h+var_1B8], r13
0x1800fdb18  mov     rsi, [rbx+50h]
0x1800fdb1c  mov     r15, [rbx+58h]
0x1800fdb20  jmp     short loc_1800FDB7A
0x1800fdb22  mov     rcx, [rsi]
0x1800fdb25  test    rcx, rcx
0x1800fdb28  jz      loc_1800FDDB0
0x1800fdb2e  lea     rax, [rsp+220h+var_1D8]
0x1800fdb33  mov     [rsp+220h+Reserved], rax
0x1800fdb38  movaps  xmm3, xmm7
0x1800fdb3b  lea     r8, [rsp+220h+var_1F0]
0x1800fdb40  lea     rdx, [rbp+120h+var_130]
0x1800fdb44  call    ?ComputeColorStop@ColorStopRenderer@SVG@Mso@@QEBA?AUGradientStop@GEL@@AEBVStyleResolveChain@23@MAEAV?$optional@N@std@@@Z; Mso::SVG::ColorStopRenderer::ComputeColorStop(Mso::SVG::StyleResolveChain const &,float,std::optional<double> &)
0x1800fdb49  mov     rdx, [rsp+220h+var_1C0]
0x1800fdb4e  cmp     rdx, [rsp+220h+var_1B8]
0x1800fdb53  jz      short loc_1800FDB69
0x1800fdb55  movups  xmm0, xmmword ptr [rax]
0x1800fdb58  movups  xmmword ptr [rdx], xmm0
0x1800fdb5b  mov     eax, [rax+10h]
0x1800fdb5e  mov     [rdx+10h], eax
0x1800fdb61  add     [rsp+220h+var_1C0], 14h
0x1800fdb67  jmp     short loc_1800FDB76
0x1800fdb69  mov     r8, rax
0x1800fdb6c  lea     rcx, [rsp+220h+var_1D0+8]
0x1800fdb71  call    ??$_Emplace_reallocate@AEBUGradientStop@GEL@@@?$vector@UGradientStop@GEL@@V?$allocator@UGradientStop@GEL@@@std@@@std@@AEAAPEAUGradientStop@GEL@@QEAU23@AEBU23@@Z; std::vector<GEL::GradientStop>::_Emplace_reallocate<GEL::GradientStop const &>(GEL::GradientStop * const,GEL::GradientStop const &)
0x1800fdb76  add     rsi, 8
0x1800fdb7a  cmp     rsi, r15
0x1800fdb7d  jnz     short loc_1800FDB22
0x1800fdb7f  mov     r8, [rsp+220h+var_1C0]
0x1800fdb84  mov     rdx, qword ptr [rsp+220h+var_1D0+8]
0x1800fdb89  sub     r8, rdx
0x1800fdb8c  sar     r8, 2
0x1800fdb90  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800fdb9a  imul    r8, rax
0x1800fdb9e  test    r8, r8
0x1800fdba1  jz      loc_1800FDD9A
0x1800fdba7  movups  xmm0, xmmword ptr [rdx]
0x1800fdbaa  movdqu  [rbp+120h+var_190], xmm0
0x1800fdbaf  lea     rax, [r8-1]
0x1800fdbb3  cmp     rax, r8
0x1800fdbb6  jnb     loc_1800FDD9A
0x1800fdbbc  lea     rax, [rax+rax*4]
0x1800fdbc0  movups  xmm0, xmmword ptr [rdx+rax*4]
0x1800fdbc4  movdqu  [rbp+120h+var_180], xmm0
0x1800fdbc9  lea     rcx, [rbp+120h+var_1A0]
0x1800fdbcd  call    cs:__imp_?SetShadeColors@GradientInfo@GEL@@QEAAXPEBUGradientStop@2@I@Z; GEL::GradientInfo::SetShadeColors(GEL::GradientStop const *,uint)
0x1800fdbd3  mov     [rbp+120h+var_170], 3F800000h
0x1800fdbda  mov     [rbp+120h+var_16C], 1
0x1800fdbe1  mov     rcx, r14
0x1800fdbe4  call    ?GetSpread@GradientContext@SVG@Mso@@QEBA?AW4ExtendMode@ARC@@XZ; Mso::SVG::GradientContext::GetSpread(void)
0x1800fdbe9  mov     [rbp+120h+var_168], eax
0x1800fdbec  mov     r8, r12
0x1800fdbef  lea     rdx, [rbp+120h+var_F8]
0x1800fdbf3  mov     rcx, rbx
0x1800fdbf6  call    ?ComputeTransform@GradientRenderer@SVG@Mso@@QEBA?AU?$TAffine3x3@N@Math@@PEBURect@GEL@@@Z; Mso::SVG::GradientRenderer::ComputeTransform(GEL::Rect const *)
0x1800fdbfb  movaps  xmm7, xmm6
0x1800fdbfe  maxsd   xmm7, xmm13
0x1800fdc03  movaps  xmm8, xmm11
0x1800fdc07  maxsd   xmm8, xmm12
0x1800fdc0c  movaps  xmm9, xmm13
0x1800fdc10  minsd   xmm9, xmm6
0x1800fdc15  movaps  xmm10, xmm12
0x1800fdc19  minsd   xmm10, xmm11
0x1800fdc1e  movsd   [rbp+120h+var_130], xmm10
0x1800fdc24  movsd   [rbp+120h+var_128], xmm9
0x1800fdc2a  movsd   [rbp+120h+var_120], xmm8
0x1800fdc30  movsd   [rbp+120h+var_118], xmm7
0x1800fdc35  mov     rbx, r13
0x1800fdc38  mov     [rsp+220h+var_1D8], rbx
0x1800fdc3d  subsd   xmm6, xmm13
0x1800fdc42  subsd   xmm11, xmm12
0x1800fdc47  mov     rcx, r14
0x1800fdc4a  call    ?GetUnits@GradientContext@SVG@Mso@@QEBA?AW4GradientUnits@23@XZ; Mso::SVG::GradientContext::GetUnits(void)
0x1800fdc4f  cmp     eax, 1
0x1800fdc52  jnz     loc_1800FDCDF
0x1800fdc58  lea     r8, [rbp+120h+var_F8]
0x1800fdc5c  lea     rdx, [rbp+120h+var_C8]
0x1800fdc60  lea     rcx, [rbp+120h+var_130]
0x1800fdc64  call    ?GetTransformedBounds@Rect@GEL@@QEBA?AU12@AEBU?$TAffine3x3@N@Math@@@Z; GEL::Rect::GetTransformedBounds(Math::TAffine3x3<double> const &)
0x1800fdc69  movups  xmm0, xmmword ptr [rax]
0x1800fdc6c  movaps  [rbp+120h+var_160], xmm0
0x1800fdc70  movups  xmm1, xmmword ptr [rax+10h]
0x1800fdc74  movaps  [rbp+120h+var_150], xmm1
0x1800fdc78  mov     rax, [r14]
0x1800fdc7b  mov     rcx, r14
0x1800fdc7e  mov     rax, [rax+70h]
0x1800fdc82  call    cs:__guard_dispatch_icall_fptr
0x1800fdc88  movups  xmm5, xmmword ptr [rax]
0x1800fdc8b  movups  [rbp+120h+var_F8], xmm5
0x1800fdc8f  movups  xmm4, xmmword ptr [rax+10h]
0x1800fdc93  movups  [rbp+120h+var_E8], xmm4
0x1800fdc97  movups  xmm0, xmmword ptr [rax+20h]
0x1800fdc9b  movups  [rbp+120h+var_D8], xmm0
0x1800fdc9f  movaps  xmm0, xmm6
0x1800fdca2  movaps  xmm1, xmm4
0x1800fdca5  unpckhpd xmm1, xmm4
  ... truncated ...
```
