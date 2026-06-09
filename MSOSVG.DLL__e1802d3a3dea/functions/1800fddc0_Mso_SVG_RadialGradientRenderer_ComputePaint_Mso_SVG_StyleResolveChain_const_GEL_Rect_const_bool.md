# Mso::SVG::RadialGradientRenderer::ComputePaint(Mso::SVG::StyleResolveChain const &,GEL::Rect const *,bool)

- ea: `0x1800fddc0`
- end: `0x1800fe2b0`
- name: `?ComputePaint@RadialGradientRenderer@SVG@Mso@@UEAA?AV?$TCntPtr@UIBrush@GEL@@@3@AEBVStyleResolveChain@23@PEBURect@GEL@@_N@Z`
- size: `1264`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0x18001aa14`
- `0x18001aa70`
- `0x18001ccd0`
- `0x18001cd30`
- `0x180023800`
- `0x180024120`
- `0x1800fc1a4`
- `0x1800fc1fc`
- `0x1800fcd40`
- `0x1800fcd94`
- `0x1800fcde8`
- `0x1800fce40`
- `0x1800fce90`
- `0x1800fd510`
- `0x1800fd6c4`
- `0x1800fddc0`
- `0x1801395a4`
- `0x18013e010`
- `0x18013f738`
- `0x18013f760`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fe29b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fe2a9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fe29b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fe2a9`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800fe151`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800fe151`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x1800fe15c`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x1800fe15c`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800fe28d`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800fe28d`
- `gfx!?SetShadeColors@GradientInfo@GEL@@QEAAXPEBUGradientStop@2@I@Z` at `0x1800fe1cb`
- `gfx!?SetShadeColors@GradientInfo@GEL@@QEAAXPEBUGradientStop@2@I@Z` at `0x1800fe1cb`
- `gfx!??0RadialGradientInfo@GEL@@QEAA@XZ` at `0x1800fe0cf`
- `gfx!??0RadialGradientInfo@GEL@@QEAA@XZ` at `0x1800fe0cf`
- `gfx!??1RadialGradientInfo@GEL@@UEAA@XZ` at `0x1800fe273`
- `gfx!??1RadialGradientInfo@GEL@@UEAA@XZ` at `0x1800fe273`
- `gfx!?Create@IBrushRadialGradient@GEL@@SA?AV?$TCntPtr@UIBrushRadialGradient@GEL@@@Ofc@@AEBURadialGradientInfo@2@@Z` at `0x1800fe217`
- `gfx!?Create@IBrushRadialGradient@GEL@@SA?AV?$TCntPtr@UIBrushRadialGradient@GEL@@@Ofc@@AEBURadialGradientInfo@2@@Z` at `0x1800fe217`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall Mso::SVG::RadialGradientRenderer::ComputePaint(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4,
        char a5)
{
  _QWORD *v9; // rdi
  Mso::SVG::LengthResolver *p_si128; // r15
  __int64 v11; // rax
  const struct Mso::SVG::Length *CX; // rax
  double v14; // xmm11_8
  const struct Mso::SVG::Length *CY; // rax
  double v16; // xmm12_8
  const struct Mso::SVG::Length *v17; // rax
  double v18; // xmm13_8
  double v19; // xmm10_8
  double v20; // xmm7_8
  double v21; // xmm6_8
  double v22; // xmm8_8
  double v23; // xmm9_8
  double v24; // xmm0_8
  __int64 v25; // rdx
  __int64 v26; // rax
  __int64 *v27; // rax
  __int64 *v28; // rax
  unsigned int v29; // r8d
  int v30; // r9d
  _QWORD *v31; // rbx
  _QWORD *v32; // r15
  __int64 v33; // rax
  Mso::SVG::LengthResolver *v34; // rdx
  void *v35; // rax
  unsigned __int64 v36; // r8
  void (__fastcall ****v37)(_QWORD); // rax
  void (__fastcall ***v38)(_QWORD); // rcx
  _QWORD v39[2]; // [rsp+38h] [rbp-D0h] BYREF
  Mso::SVG::LengthResolver *v40; // [rsp+48h] [rbp-C0h]
  Mso::SVG::LengthResolver *v41[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v42; // [rsp+60h] [rbp-A8h]
  _BYTE v43[32]; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v44[16]; // [rsp+88h] [rbp-80h] BYREF
  __int128 v45; // [rsp+98h] [rbp-70h]
  __int128 v46; // [rsp+A8h] [rbp-60h]
  int v47; // [rsp+B8h] [rbp-50h]
  int v48; // [rsp+BCh] [rbp-4Ch]
  int Spread; // [rsp+C0h] [rbp-48h]
  double v50; // [rsp+C8h] [rbp-40h]
  double v51; // [rsp+D0h] [rbp-38h]
  double v52; // [rsp+D8h] [rbp-30h]
  double v53; // [rsp+E0h] [rbp-28h]
  double v54; // [rsp+E8h] [rbp-20h]
  double v55; // [rsp+F0h] [rbp-18h]
  __int64 v56; // [rsp+F8h] [rbp-10h]
  __m128i si128; // [rsp+108h] [rbp+0h] BYREF
  double v58; // [rsp+118h] [rbp+10h]
  _BYTE v59[24]; // [rsp+120h] [rbp+18h] BYREF
  _BYTE v60[24]; // [rsp+138h] [rbp+30h] BYREF
  char v61; // [rsp+150h] [rbp+48h] BYREF
  void *v62; // [rsp+218h] [rbp+110h] BYREF

  v9 = (_QWORD *)a1[2];
  if ( !v9 )
  {
LABEL_49:
    CrashWithRecovery(0x1E3C3843u, 0);
    JUMPOUT(0x1800FE2AFLL);
  }
  _castguard_slow_path_check_user_handled(*v9, 7520, 0);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v58 = sqrt_0(1.0);
  p_si128 = (Mso::SVG::LengthResolver *)&si128;
  if ( (unsigned int)Mso::SVG::GradientContext::GetUnits(v9) != 1 )
    p_si128 = (Mso::SVG::LengthResolver *)a3[2];
  v11 = (*(__int64 (__fastcall **)(_QWORD *))(*v9 + 104LL))(v9);
  v39[0] = 0;
  v39[1] = v11;
  v40 = p_si128;
  if ( a1[11] == a1[10] )
  {
    *a2 = 0;
  }
  else
  {
    CX = (const struct Mso::SVG::Length *)Mso::SVG::RadialGradientContext::GetCX(v9, v43);
    v14 = Mso::SVG::LengthResolver::ResolveLength(v40, CX, (const struct Mso::SVG::StyleResolveChain *)v39);
    CY = (const struct Mso::SVG::Length *)Mso::SVG::RadialGradientContext::GetCY(v9, v43);
    v16 = Mso::SVG::LengthResolver::ResolveLength(v40, CY, (const struct Mso::SVG::StyleResolveChain *)v39);
    v17 = (const struct Mso::SVG::Length *)Mso::SVG::RadialGradientContext::GetR(v9, v43);
    v18 = Mso::SVG::LengthResolver::ResolveLength(v40, v17, (const struct Mso::SVG::StyleResolveChain *)v39);
    *(_QWORD *)&v19 = *(_QWORD *)&v18 & _xmm;
    Mso::SVG::RadialGradientContext::GetFX(v9, v59);
    Mso::SVG::RadialGradientContext::GetFY(v9, v60);
    if ( v59[16] )
      v20 = Mso::SVG::LengthResolver::ResolveLength(
              v40,
              (const struct Mso::SVG::Length *)v59,
              (const struct Mso::SVG::StyleResolveChain *)v39);
    else
      v20 = v14;
    if ( v60[16] )
      v21 = Mso::SVG::LengthResolver::ResolveLength(
              v40,
              (const struct Mso::SVG::Length *)v60,
              (const struct Mso::SVG::StyleResolveChain *)v39);
    else
      v21 = v16;
    v22 = v20 - v14;
    v23 = v21 - v16;
    v24 = sqrt_0(v22 * v22 + v23 * v23);
    if ( v24 > v19 )
    {
      v20 = v22 / v24 * v19 + v14;
      v21 = v23 / v24 * v19 + v16;
    }
    v25 = a3[1];
    v26 = *(_QWORD *)(v25 + 16);
    if ( a5 )
    {
      if ( v26 )
      {
        v27 = (__int64 *)(v26 + 1080);
      }
      else
      {
        v27 = (__int64 *)&Mso::SVG::StyleMetaData<9>::initial;
        if ( *(_QWORD *)(v25 + 8) )
          v27 = Mso::SVG::StyleMetaData<9>::inherit;
      }
      if ( !*((_BYTE *)v27 + 8) )
      {
        if ( *a3 )
          Mso::SVG::StyleResolveChain::Get<9>(*a3, v25);
        else
          Mso::SVG::StyleResolveChain::GetNormal<9>(a3, *(_QWORD *)(v25 + 8));
      }
    }
    else
    {
      if ( v26 )
      {
        v28 = (__int64 *)(v26 + 968);
      }
      else
      {
        v28 = (__int64 *)&Mso::SVG::StyleMetaData<12>::initial;
        if ( *(_QWORD *)(v25 + 8) )
          v28 = Mso::SVG::StyleMetaData<12>::inherit;
      }
      if ( !*((_BYTE *)v28 + 8) )
      {
        if ( *a3 )
          Mso::SVG::StyleResolveChain::Get<12>(*a3, v25);
        else
          Mso::SVG::StyleResolveChain::GetNormal<12>(a3, *(_QWORD *)(v25 + 8));
      }
    }
    v43[8] = 0;
    GEL::RadialGradientInfo::RadialGradientInfo((GEL::RadialGradientInfo *)v44);
    *(_OWORD *)v41 = 0;
    v42 = 0;
    v31 = (_QWORD *)a1[10];
    v32 = (_QWORD *)a1[11];
    while ( v31 != v32 )
    {
      if ( !*v31 )
      {
        CrashWithRecovery(0x1E3C3840u, 0);
        goto LABEL_49;
      }
      v33 = Mso::SVG::ColorStopRenderer::ComputeColorStop(
              *v31,
              (unsigned int)&v61,
              (unsigned int)v39,
              v30,
              (__int64)v43);
      v34 = v41[1];
      if ( v41[1] == (Mso::SVG::LengthResolver *)v42 )
      {
        std::vector<GEL::GradientStop>::_Emplace_reallocate<GEL::GradientStop const &>(v41, v41[1], v33);
      }
      else
      {
        *(_OWORD *)v41[1] = *(_OWORD *)v33;
        *((_DWORD *)v34 + 4) = *(_DWORD *)(v33 + 16);
        v41[1] = (Mso::SVG::LengthResolver *)((char *)v41[1] + 20);
      }
      ++v31;
    }
    v35 = Mso::Memory::AllocateEx((Mso::Memory *)0x30, 0, v29);
    if ( !v35 )
    {
      ThrowOOM();
      __debugbreak();
    }
    v62 = v35;
    v56 = Mso::SVG::GradientRenderer::ComputeTransform(a1, v35, a4);
    v36 = 0xCCCCCCCCCCCCCCCDuLL * ((v41[1] - v41[0]) >> 2);
    if ( !v36 )
      _invoke_watson(0, 0, 0, 0, 0);
    v45 = *(_OWORD *)v41[0];
    v46 = *(_OWORD *)((char *)v41[0] + 20 * v36 - 20);
    GEL::GradientInfo::SetShadeColors((GEL::GradientInfo *)v44, v41[0], v36);
    v47 = 1065353216;
    v48 = 1;
    v52 = v20;
    v53 = v21;
    v50 = v14;
    v51 = v16;
    v54 = v18;
    v55 = v18;
    Spread = Mso::SVG::GradientContext::GetSpread(v9);
    v37 = (void (__fastcall ****)(_QWORD))GEL::IBrushRadialGradient::Create(&v62, v44);
    v38 = *v37;
    *a2 = *v37;
    if ( v38 )
      (**v38)(v38);
    if ( v62 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v62 + 8LL))(v62);
    std::vector<GEL::GradientStop>::_Tidy(v41);
    *(__m128i *)v41 = _mm_load_si128((const __m128i *)&_xmm);
    v42 = 19937;
    GEL::RadialGradientInfo::~RadialGradientInfo((GEL::RadialGradientInfo *)v44);
  }
  return a2;
}

```

## disassembly

```asm
0x1800fddc0  mov     rax, rsp
0x1800fddc3  mov     [rax+10h], rbx
0x1800fddc7  mov     [rax+18h], rsi
0x1800fddcb  mov     [rax+20h], rdi
0x1800fddcf  push    rbp
0x1800fddd0  push    r12
0x1800fddd2  push    r13
0x1800fddd4  push    r14
0x1800fddd6  push    r15
0x1800fddd8  lea     rbp, [rax-108h]
0x1800fdddf  sub     rsp, 1E0h
0x1800fdde6  movaps  xmmword ptr [rax-38h], xmm6
0x1800fddea  movaps  xmmword ptr [rax-48h], xmm7
0x1800fddee  movaps  xmmword ptr [rax-58h], xmm8
0x1800fddf3  movaps  xmmword ptr [rax-68h], xmm9
0x1800fddf8  movaps  xmmword ptr [rax-78h], xmm10
0x1800fddfd  movaps  xmmword ptr [rax-88h], xmm11
0x1800fde05  movaps  xmmword ptr [rax-98h], xmm12
0x1800fde0d  movaps  xmmword ptr [rax-0A8h], xmm13
0x1800fde15  mov     r12, r9
0x1800fde18  mov     rbx, r8
0x1800fde1b  mov     rsi, rdx
0x1800fde1e  mov     r14, rcx
0x1800fde21  xor     r13d, r13d
0x1800fde24  mov     rdi, [rcx+10h]
0x1800fde28  test    rdi, rdi
0x1800fde2b  jz      loc_1800FE2A2
0x1800fde31  xor     r8d, r8d
0x1800fde34  mov     edx, 1D60h
0x1800fde39  mov     rcx, [rdi]
0x1800fde3c  call    __castguard_slow_path_check_user_handled
0x1800fde41  movdqa  xmm0, cs:__xmm@3ff00000000000003ff0000000000000
0x1800fde49  movups  [rbp+100h+var_100], xmm0
0x1800fde4d  movsd   xmm0, cs:__real@3ff0000000000000; X
0x1800fde55  call    sqrt_0
0x1800fde5a  movsd   [rbp+100h+var_F0], xmm0
0x1800fde5f  mov     rcx, rdi
0x1800fde62  call    ?GetUnits@GradientContext@SVG@Mso@@QEBA?AW4GradientUnits@23@XZ; Mso::SVG::GradientContext::GetUnits(void)
0x1800fde67  cmp     eax, 1
0x1800fde6a  lea     r15, [rbp+100h+var_100]
0x1800fde6e  jz      short loc_1800FDE74
0x1800fde70  mov     r15, [rbx+10h]
0x1800fde74  mov     rax, [rdi]
0x1800fde77  mov     rcx, rdi
0x1800fde7a  mov     rax, [rax+68h]
0x1800fde7e  call    cs:__guard_dispatch_icall_fptr
0x1800fde84  mov     [rsp+200h+var_1D0], r13
0x1800fde89  mov     [rsp+200h+var_1C8], rax
0x1800fde8e  mov     [rsp+200h+var_1C0], r15
0x1800fde93  mov     rax, [r14+58h]
0x1800fde97  cmp     rax, [r14+50h]
0x1800fde9b  jnz     short loc_1800FDEEC
0x1800fde9d  mov     [rsi], r13
0x1800fdea0  mov     rax, rsi
0x1800fdea3  lea     r11, [rsp+200h+var_20]
0x1800fdeab  mov     rbx, [r11+38h]
0x1800fdeaf  mov     rsi, [r11+40h]
0x1800fdeb3  mov     rdi, [r11+48h]
0x1800fdeb7  movaps  xmm6, xmmword ptr [r11-10h]
0x1800fdebc  movaps  xmm7, xmmword ptr [r11-20h]
0x1800fdec1  movaps  xmm8, xmmword ptr [r11-30h]
0x1800fdec6  movaps  xmm9, xmmword ptr [r11-40h]
0x1800fdecb  movaps  xmm10, xmmword ptr [r11-50h]
0x1800fded0  movaps  xmm11, xmmword ptr [r11-60h]
0x1800fded5  movaps  xmm12, xmmword ptr [r11-70h]
0x1800fdeda  movaps  xmm13, xmmword ptr [r11-80h]
0x1800fdedf  mov     rsp, r11
0x1800fdee2  pop     r15
0x1800fdee4  pop     r14
0x1800fdee6  pop     r13
0x1800fdee8  pop     r12
0x1800fdeea  pop     rbp
0x1800fdeeb  retn
0x1800fdeec  lea     rdx, [rsp+200h+var_1A0]
0x1800fdef1  mov     rcx, rdi
0x1800fdef4  call    ?GetCX@RadialGradientContext@SVG@Mso@@QEBA?AULength@23@XZ; Mso::SVG::RadialGradientContext::GetCX(void)
0x1800fdef9  lea     r8, [rsp+200h+var_1D0]; struct Mso::SVG::StyleResolveChain *
0x1800fdefe  mov     rdx, rax; struct Mso::SVG::Length *
0x1800fdf01  mov     rcx, [rsp+200h+var_1C0]; this
0x1800fdf06  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x1800fdf0b  movaps  xmm11, xmm0
0x1800fdf0f  lea     rdx, [rsp+200h+var_1A0]
0x1800fdf14  mov     rcx, rdi
0x1800fdf17  call    ?GetCY@RadialGradientContext@SVG@Mso@@QEBA?AULength@23@XZ; Mso::SVG::RadialGradientContext::GetCY(void)
0x1800fdf1c  lea     r8, [rsp+200h+var_1D0]; struct Mso::SVG::StyleResolveChain *
0x1800fdf21  mov     rdx, rax; struct Mso::SVG::Length *
0x1800fdf24  mov     rcx, [rsp+200h+var_1C0]; this
0x1800fdf29  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x1800fdf2e  movaps  xmm12, xmm0
0x1800fdf32  lea     rdx, [rsp+200h+var_1A0]
0x1800fdf37  mov     rcx, rdi
0x1800fdf3a  call    ?GetR@RadialGradientContext@SVG@Mso@@QEBA?AULength@23@XZ; Mso::SVG::RadialGradientContext::GetR(void)
0x1800fdf3f  lea     r8, [rsp+200h+var_1D0]; struct Mso::SVG::StyleResolveChain *
0x1800fdf44  mov     rdx, rax; struct Mso::SVG::Length *
0x1800fdf47  mov     rcx, [rsp+200h+var_1C0]; this
0x1800fdf4c  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x1800fdf51  movaps  xmm13, xmm0
0x1800fdf55  movaps  xmm10, xmm0
0x1800fdf59  andps   xmm10, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x1800fdf61  lea     rdx, [rbp+100h+var_E8]
0x1800fdf65  mov     rcx, rdi
0x1800fdf68  call    ?GetFX@RadialGradientContext@SVG@Mso@@QEBA?AV?$optional@ULength@SVG@Mso@@@std@@XZ; Mso::SVG::RadialGradientContext::GetFX(void)
0x1800fdf6d  lea     rdx, [rbp+100h+var_D0]
0x1800fdf71  mov     rcx, rdi
0x1800fdf74  call    ?GetFY@RadialGradientContext@SVG@Mso@@QEBA?AV?$optional@ULength@SVG@Mso@@@std@@XZ; Mso::SVG::RadialGradientContext::GetFY(void)
0x1800fdf79  cmp     [rbp+100h+var_D8], r13b
0x1800fdf7d  jz      short loc_1800FDF97
0x1800fdf7f  lea     r8, [rsp+200h+var_1D0]; struct Mso::SVG::StyleResolveChain *
0x1800fdf84  lea     rdx, [rbp+100h+var_E8]; struct Mso::SVG::Length *
0x1800fdf88  mov     rcx, [rsp+200h+var_1C0]; this
0x1800fdf8d  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x1800fdf92  movaps  xmm7, xmm0
0x1800fdf95  jmp     short loc_1800FDF9B
0x1800fdf97  movaps  xmm7, xmm11
0x1800fdf9b  cmp     [rbp+100h+var_C0], r13b
0x1800fdf9f  jz      short loc_1800FDFB9
0x1800fdfa1  lea     r8, [rsp+200h+var_1D0]; struct Mso::SVG::StyleResolveChain *
0x1800fdfa6  lea     rdx, [rbp+100h+var_D0]; struct Mso::SVG::Length *
0x1800fdfaa  mov     rcx, [rsp+200h+var_1C0]; this
0x1800fdfaf  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x1800fdfb4  movaps  xmm6, xmm0
0x1800fdfb7  jmp     short loc_1800FDFBD
0x1800fdfb9  movaps  xmm6, xmm12
0x1800fdfbd  movaps  xmm8, xmm7
0x1800fdfc1  subsd   xmm8, xmm11
0x1800fdfc6  movaps  xmm9, xmm6
0x1800fdfca  subsd   xmm9, xmm12
0x1800fdfcf  movaps  xmm0, xmm8
0x1800fdfd3  mulsd   xmm0, xmm8
0x1800fdfd8  movaps  xmm1, xmm9
0x1800fdfdc  mulsd   xmm1, xmm9
0x1800fdfe1  addsd   xmm0, xmm1; X
0x1800fdfe5  call    sqrt_0
0x1800fdfea  comisd  xmm0, xmm10
0x1800fdfef  jbe     short loc_1800FE015
0x1800fdff1  movaps  xmm7, xmm8
0x1800fdff5  divsd   xmm7, xmm0
0x1800fdff9  mulsd   xmm7, xmm10
0x1800fdffe  addsd   xmm7, xmm11
0x1800fe003  movaps  xmm6, xmm9
0x1800fe007  divsd   xmm6, xmm0
0x1800fe00b  mulsd   xmm6, xmm10
0x1800fe010  addsd   xmm6, xmm12
0x1800fe015  mov     rdx, [rbx+8]
0x1800fe019  mov     rax, [rdx+10h]
0x1800fe01d  cmp     [rbp+100h+arg_20], r13b
0x1800fe024  jz      short loc_1800FE072
0x1800fe026  test    rax, rax
0x1800fe029  jz      short loc_1800FE033
0x1800fe02b  add     rax, 438h
0x1800fe031  jmp     short loc_1800FE047
0x1800fe033  cmp     [rdx+8], r13
0x1800fe037  lea     rax, ?initial@?$StyleMetaData@$08@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<9>::initial
0x1800fe03e  jz      short loc_1800FE047
0x1800fe040  lea     rax, ?inherit@?$StyleMetaData@$08@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<9>::inherit
0x1800fe047  mov     ecx, 8
0x1800fe04c  cmp     [rax+8], r13b
0x1800fe050  jnz     short loc_1800FE0BC
0x1800fe052  mov     rax, [rbx]
0x1800fe055  test    rax, rax
0x1800fe058  jz      short loc_1800FE064
0x1800fe05a  mov     rcx, rax
0x1800fe05d  call    ??$Get@$08@StyleResolveChain@SVG@Mso@@QEBAAEBNXZ; Mso::SVG::StyleResolveChain::Get<9>(void)
0x1800fe062  jmp     short loc_1800FE0BC
0x1800fe064  mov     rdx, [rdx+rcx]
0x1800fe068  mov     rcx, rbx
0x1800fe06b  call    ??$GetNormal@$08@StyleResolveChain@SVG@Mso@@AEBAAEBNAEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<9>(Mso::SVG::Style const &)
0x1800fe070  jmp     short loc_1800FE0BC
0x1800fe072  test    rax, rax
0x1800fe075  jz      short loc_1800FE07F
0x1800fe077  add     rax, 3C8h
0x1800fe07d  jmp     short loc_1800FE093
0x1800fe07f  cmp     [rdx+8], r13
0x1800fe083  lea     rax, ?initial@?$StyleMetaData@$0M@@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<12>::initial
0x1800fe08a  jz      short loc_1800FE093
0x1800fe08c  lea     rax, ?inherit@?$StyleMetaData@$0M@@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<12>::inherit
0x1800fe093  mov     ecx, 8
0x1800fe098  cmp     [rax+8], r13b
0x1800fe09c  jnz     short loc_1800FE0BC
0x1800fe09e  mov     rax, [rbx]
0x1800fe0a1  test    rax, rax
0x1800fe0a4  jz      short loc_1800FE0B0
0x1800fe0a6  mov     rcx, rax
0x1800fe0a9  call    ??$Get@$0M@@StyleResolveChain@SVG@Mso@@QEBAAEBNXZ; Mso::SVG::StyleResolveChain::Get<12>(void)
0x1800fe0ae  jmp     short loc_1800FE0BC
0x1800fe0b0  mov     rdx, [rdx+rcx]
0x1800fe0b4  mov     rcx, rbx
0x1800fe0b7  call    ??$GetNormal@$0M@@StyleResolveChain@SVG@Mso@@AEBAAEBNAEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<12>(Mso::SVG::Style const &)
0x1800fe0bc  movsd   xmm8, qword ptr [rax]
0x1800fe0c1  cvtpd2ps xmm8, xmm8
0x1800fe0c6  mov     [rsp+200h+var_198], r13b
0x1800fe0cb  lea     rcx, [rbp+100h+var_180]
0x1800fe0cf  call    cs:__imp_??0RadialGradientInfo@GEL@@QEAA@XZ; GEL::RadialGradientInfo::RadialGradientInfo(void)
0x1800fe0d5  nop
0x1800fe0d6  xorps   xmm0, xmm0
0x1800fe0d9  movdqu  xmmword ptr [rsp+200h+var_1C0+8], xmm0
0x1800fe0df  mov     [rsp+200h+var_1A8], r13
0x1800fe0e4  mov     rbx, [r14+50h]
0x1800fe0e8  mov     r15, [r14+58h]
0x1800fe0ec  jmp     short loc_1800FE147
0x1800fe0ee  mov     rcx, [rbx]
0x1800fe0f1  test    rcx, rcx
0x1800fe0f4  jz      loc_1800FE294
0x1800fe0fa  lea     rax, [rsp+200h+var_1A0]
0x1800fe0ff  mov     [rsp+200h+Reserved], rax
0x1800fe104  movaps  xmm3, xmm8
0x1800fe108  lea     r8, [rsp+200h+var_1D0]
0x1800fe10d  lea     rdx, [rbp+100h+var_B8]
0x1800fe111  call    ?ComputeColorStop@ColorStopRenderer@SVG@Mso@@QEBA?AUGradientStop@GEL@@AEBVStyleResolveChain@23@MAEAV?$optional@N@std@@@Z; Mso::SVG::ColorStopRenderer::ComputeColorStop(Mso::SVG::StyleResolveChain const &,float,std::optional<double> &)
0x1800fe116  mov     rdx, [rsp+200h+var_1B0]
0x1800fe11b  cmp     rdx, [rsp+200h+var_1A8]
0x1800fe120  jz      short loc_1800FE136
0x1800fe122  movups  xmm0, xmmword ptr [rax]
0x1800fe125  movups  xmmword ptr [rdx], xmm0
0x1800fe128  mov     eax, [rax+10h]
0x1800fe12b  mov     [rdx+10h], eax
0x1800fe12e  add     [rsp+200h+var_1B0], 14h
0x1800fe134  jmp     short loc_1800FE143
0x1800fe136  mov     r8, rax
0x1800fe139  lea     rcx, [rsp+200h+var_1C0+8]
0x1800fe13e  call    ??$_Emplace_reallocate@AEBUGradientStop@GEL@@@?$vector@UGradientStop@GEL@@V?$allocator@UGradientStop@GEL@@@std@@@std@@AEAAPEAUGradientStop@GEL@@QEAU23@AEBU23@@Z; std::vector<GEL::GradientStop>::_Emplace_reallocate<GEL::GradientStop const &>(GEL::GradientStop * const,GEL::GradientStop const &)
0x1800fe143  add     rbx, 8
0x1800fe147  cmp     rbx, r15
0x1800fe14a  jnz     short loc_1800FE0EE
0x1800fe14c  xor     edx, edx
0x1800fe14e  lea     ecx, [rdx+30h]
0x1800fe151  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1800fe157  test    rax, rax
0x1800fe15a  jnz     short loc_1800FE163
0x1800fe15c  call    cs:__imp_?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x1800fe162  int     3; Trap to Debugger
0x1800fe163  mov     [rbp+100h+arg_0], rax
0x1800fe16a  mov     r8, r12
0x1800fe16d  mov     rdx, rax
0x1800fe170  mov     rcx, r14
0x1800fe173  call    ?ComputeTransform@GradientRenderer@SVG@Mso@@QEBA?AU?$TAffine3x3@N@Math@@PEBURect@GEL@@@Z; Mso::SVG::GradientRenderer::ComputeTransform(GEL::Rect const *)
0x1800fe178  nop
0x1800fe179  mov     [rbp+100h+var_110], rax
0x1800fe17d  mov     r8, [rsp+200h+var_1B0]
0x1800fe182  mov     rdx, [rsp+200h+var_1C0+8]
0x1800fe187  sub     r8, rdx
0x1800fe18a  sar     r8, 2
0x1800fe18e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800fe198  imul    r8, rax
0x1800fe19c  test    r8, r8
0x1800fe19f  jz      loc_1800FE27E
0x1800fe1a5  movups  xmm0, xmmword ptr [rdx]
0x1800fe1a8  movdqu  [rbp+100h+var_170], xmm0
0x1800fe1ad  lea     rax, [r8-1]
0x1800fe1b1  cmp     rax, r8
0x1800fe1b4  jnb     loc_1800FE27E
0x1800fe1ba  lea     rax, [rax+rax*4]
0x1800fe1be  movups  xmm0, xmmword ptr [rdx+rax*4]
0x1800fe1c2  movdqu  [rbp+100h+var_160], xmm0
0x1800fe1c7  lea     rcx, [rbp+100h+var_180]
0x1800fe1cb  call    cs:__imp_?SetShadeColors@GradientInfo@GEL@@QEAAXPEBUGradientStop@2@I@Z; GEL::GradientInfo::SetShadeColors(GEL::GradientStop const *,uint)
0x1800fe1d1  mov     [rbp+100h+var_150], 3F800000h
0x1800fe1d8  mov     [rbp+100h+var_14C], 1
0x1800fe1df  movsd   [rbp+100h+var_130], xmm7
0x1800fe1e4  movsd   [rbp+100h+var_128], xmm6
0x1800fe1e9  movsd   [rbp+100h+var_140], xmm11
0x1800fe1ef  movsd   [rbp+100h+var_138], xmm12
0x1800fe1f5  movsd   [rbp+100h+var_120], xmm13
0x1800fe1fb  movsd   [rbp+100h+var_118], xmm13
0x1800fe201  mov     rcx, rdi
0x1800fe204  call    ?GetSpread@GradientContext@SVG@Mso@@QEBA?AW4ExtendMode@ARC@@XZ; Mso::SVG::GradientContext::GetSpread(void)
0x1800fe209  mov     [rbp+100h+var_148], eax
0x1800fe20c  lea     rdx, [rbp+100h+var_180]
0x1800fe210  lea     rcx, [rbp+100h+arg_0]
0x1800fe217  call    cs:__imp_?Create@IBrushRadialGradient@GEL@@SA?AV?$TCntPtr@UIBrushRadialGradient@GEL@@@Ofc@@AEBURadialGradientInfo@2@@Z; GEL::IBrushRadialGradient::Create(GEL::RadialGradientInfo const &)
0x1800fe21d  mov     rcx, [rax]
0x1800fe220  mov     [rsi], rcx
0x1800fe223  test    rcx, rcx
0x1800fe226  jz      short loc_1800FE234
0x1800fe228  mov     rax, [rcx]
0x1800fe22b  mov     rax, [rax]
0x1800fe22e  call    cs:__guard_dispatch_icall_fptr
0x1800fe234  mov     rcx, [rbp+100h+arg_0]
0x1800fe23b  test    rcx, rcx
0x1800fe23e  jz      short loc_1800FE24E
0x1800fe240  mov     rax, [rcx]
0x1800fe243  mov     rax, [rax+8]
0x1800fe247  call    cs:__guard_dispatch_icall_fptr
0x1800fe24d  nop
0x1800fe24e  lea     rcx, [rsp+200h+var_1C0+8]
0x1800fe253  call    ?_Tidy@?$vector@UGradientStop@GEL@@V?$allocator@UGradientStop@GEL@@@std@@@std@@AEAAXXZ; std::vector<GEL::GradientStop>::_Tidy(void)
0x1800fe258  movdqa  xmm0, cs:__xmm@0000000000004de10000000000004de1
0x1800fe260  movdqu  xmmword ptr [rsp+200h+var_1C0+8], xmm0
0x1800fe266  mov     [rsp+200h+var_1A8], 4DE1h
0x1800fe26f  lea     rcx, [rbp+100h+var_180]
0x1800fe273  call    cs:__imp_??1RadialGradientInfo@GEL@@UEAA@XZ; GEL::RadialGradientInfo::~RadialGradientInfo(void)
0x1800fe279  jmp     loc_1800FDEA0
0x1800fe27e  mov     [rsp+200h+Reserved], r13; Reserved
0x1800fe283  xor     r9d, r9d; LineNo
0x1800fe286  xor     r8d, r8d; FileName
0x1800fe289  xor     edx, edx; FunctionName
0x1800fe28b  xor     ecx, ecx; Expression
0x1800fe28d  call    cs:__imp__invoke_watson
0x1800fe294  xor     edx, edx
0x1800fe296  mov     ecx, 1E3C3840h
  ... truncated ...
```
