# Mso::SVG::RadialGradientRenderer::ComputePaint(Mso::SVG::StyleResolveChain const &,GEL::Rect const *,bool)

- ea: `0x1800fdde0`
- end: `0x1800fe2d0`
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
- `0x1800fc1c4`
- `0x1800fc21c`
- `0x1800fcd60`
- `0x1800fcdb4`
- `0x1800fce08`
- `0x1800fce60`
- `0x1800fceb0`
- `0x1800fd530`
- `0x1800fd6e4`
- `0x1800fdde0`
- `0x1801395e4`
- `0x18013e0c0`
- `0x18013f7e8`
- `0x18013f810`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fe2bb`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fe2c9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fe2bb`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fe2c9`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800fe171`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800fe171`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x1800fe17c`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x1800fe17c`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800fe2ad`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800fe2ad`
- `gfx!?SetShadeColors@GradientInfo@GEL@@QEAAXPEBUGradientStop@2@I@Z` at `0x1800fe1eb`
- `gfx!?SetShadeColors@GradientInfo@GEL@@QEAAXPEBUGradientStop@2@I@Z` at `0x1800fe1eb`
- `gfx!??0RadialGradientInfo@GEL@@QEAA@XZ` at `0x1800fe0ef`
- `gfx!??0RadialGradientInfo@GEL@@QEAA@XZ` at `0x1800fe0ef`
- `gfx!??1RadialGradientInfo@GEL@@UEAA@XZ` at `0x1800fe293`
- `gfx!??1RadialGradientInfo@GEL@@UEAA@XZ` at `0x1800fe293`
- `gfx!?Create@IBrushRadialGradient@GEL@@SA?AV?$TCntPtr@UIBrushRadialGradient@GEL@@@Ofc@@AEBURadialGradientInfo@2@@Z` at `0x1800fe237`
- `gfx!?Create@IBrushRadialGradient@GEL@@SA?AV?$TCntPtr@UIBrushRadialGradient@GEL@@@Ofc@@AEBURadialGradientInfo@2@@Z` at `0x1800fe237`

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
    JUMPOUT(0x1800FE2CFLL);
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
0x1800fdde0  mov     rax, rsp
0x1800fdde3  mov     [rax+10h], rbx
0x1800fdde7  mov     [rax+18h], rsi
0x1800fddeb  mov     [rax+20h], rdi
0x1800fddef  push    rbp
0x1800fddf0  push    r12
0x1800fddf2  push    r13
0x1800fddf4  push    r14
0x1800fddf6  push    r15
0x1800fddf8  lea     rbp, [rax-108h]
0x1800fddff  sub     rsp, 1E0h
0x1800fde06  movaps  xmmword ptr [rax-38h], xmm6
0x1800fde0a  movaps  xmmword ptr [rax-48h], xmm7
0x1800fde0e  movaps  xmmword ptr [rax-58h], xmm8
0x1800fde13  movaps  xmmword ptr [rax-68h], xmm9
0x1800fde18  movaps  xmmword ptr [rax-78h], xmm10
0x1800fde1d  movaps  xmmword ptr [rax-88h], xmm11
0x1800fde25  movaps  xmmword ptr [rax-98h], xmm12
0x1800fde2d  movaps  xmmword ptr [rax-0A8h], xmm13
0x1800fde35  mov     r12, r9
0x1800fde38  mov     rbx, r8
0x1800fde3b  mov     rsi, rdx
0x1800fde3e  mov     r14, rcx
0x1800fde41  xor     r13d, r13d
0x1800fde44  mov     rdi, [rcx+10h]
0x1800fde48  test    rdi, rdi
0x1800fde4b  jz      loc_1800FE2C2
0x1800fde51  xor     r8d, r8d
0x1800fde54  mov     edx, 1D60h
0x1800fde59  mov     rcx, [rdi]
0x1800fde5c  call    __castguard_slow_path_check_user_handled
0x1800fde61  movdqa  xmm0, cs:__xmm@3ff00000000000003ff0000000000000
0x1800fde69  movups  [rbp+100h+var_100], xmm0
0x1800fde6d  movsd   xmm0, cs:__real@3ff0000000000000; X
0x1800fde75  call    sqrt_0
0x1800fde7a  movsd   [rbp+100h+var_F0], xmm0
0x1800fde7f  mov     rcx, rdi
0x1800fde82  call    ?GetUnits@GradientContext@SVG@Mso@@QEBA?AW4GradientUnits@23@XZ; Mso::SVG::GradientContext::GetUnits(void)
0x1800fde87  cmp     eax, 1
0x1800fde8a  lea     r15, [rbp+100h+var_100]
0x1800fde8e  jz      short loc_1800FDE94
0x1800fde90  mov     r15, [rbx+10h]
0x1800fde94  mov     rax, [rdi]
0x1800fde97  mov     rcx, rdi
0x1800fde9a  mov     rax, [rax+68h]
0x1800fde9e  call    cs:__guard_dispatch_icall_fptr
0x1800fdea4  mov     [rsp+200h+var_1D0], r13
0x1800fdea9  mov     [rsp+200h+var_1C8], rax
0x1800fdeae  mov     [rsp+200h+var_1C0], r15
0x1800fdeb3  mov     rax, [r14+58h]
0x1800fdeb7  cmp     rax, [r14+50h]
0x1800fdebb  jnz     short loc_1800FDF0C
0x1800fdebd  mov     [rsi], r13
0x1800fdec0  mov     rax, rsi
0x1800fdec3  lea     r11, [rsp+200h+var_20]
0x1800fdecb  mov     rbx, [r11+38h]
0x1800fdecf  mov     rsi, [r11+40h]
0x1800fded3  mov     rdi, [r11+48h]
0x1800fded7  movaps  xmm6, xmmword ptr [r11-10h]
0x1800fdedc  movaps  xmm7, xmmword ptr [r11-20h]
0x1800fdee1  movaps  xmm8, xmmword ptr [r11-30h]
0x1800fdee6  movaps  xmm9, xmmword ptr [r11-40h]
0x1800fdeeb  movaps  xmm10, xmmword ptr [r11-50h]
0x1800fdef0  movaps  xmm11, xmmword ptr [r11-60h]
0x1800fdef5  movaps  xmm12, xmmword ptr [r11-70h]
0x1800fdefa  movaps  xmm13, xmmword ptr [r11-80h]
0x1800fdeff  mov     rsp, r11
0x1800fdf02  pop     r15
0x1800fdf04  pop     r14
0x1800fdf06  pop     r13
0x1800fdf08  pop     r12
0x1800fdf0a  pop     rbp
0x1800fdf0b  retn
0x1800fdf0c  lea     rdx, [rsp+200h+var_1A0]
0x1800fdf11  mov     rcx, rdi
0x1800fdf14  call    ?GetCX@RadialGradientContext@SVG@Mso@@QEBA?AULength@23@XZ; Mso::SVG::RadialGradientContext::GetCX(void)
0x1800fdf19  lea     r8, [rsp+200h+var_1D0]; struct Mso::SVG::StyleResolveChain *
0x1800fdf1e  mov     rdx, rax; struct Mso::SVG::Length *
0x1800fdf21  mov     rcx, [rsp+200h+var_1C0]; this
0x1800fdf26  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x1800fdf2b  movaps  xmm11, xmm0
0x1800fdf2f  lea     rdx, [rsp+200h+var_1A0]
0x1800fdf34  mov     rcx, rdi
0x1800fdf37  call    ?GetCY@RadialGradientContext@SVG@Mso@@QEBA?AULength@23@XZ; Mso::SVG::RadialGradientContext::GetCY(void)
0x1800fdf3c  lea     r8, [rsp+200h+var_1D0]; struct Mso::SVG::StyleResolveChain *
0x1800fdf41  mov     rdx, rax; struct Mso::SVG::Length *
0x1800fdf44  mov     rcx, [rsp+200h+var_1C0]; this
0x1800fdf49  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x1800fdf4e  movaps  xmm12, xmm0
0x1800fdf52  lea     rdx, [rsp+200h+var_1A0]
0x1800fdf57  mov     rcx, rdi
0x1800fdf5a  call    ?GetR@RadialGradientContext@SVG@Mso@@QEBA?AULength@23@XZ; Mso::SVG::RadialGradientContext::GetR(void)
0x1800fdf5f  lea     r8, [rsp+200h+var_1D0]; struct Mso::SVG::StyleResolveChain *
0x1800fdf64  mov     rdx, rax; struct Mso::SVG::Length *
0x1800fdf67  mov     rcx, [rsp+200h+var_1C0]; this
0x1800fdf6c  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x1800fdf71  movaps  xmm13, xmm0
0x1800fdf75  movaps  xmm10, xmm0
0x1800fdf79  andps   xmm10, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x1800fdf81  lea     rdx, [rbp+100h+var_E8]
0x1800fdf85  mov     rcx, rdi
0x1800fdf88  call    ?GetFX@RadialGradientContext@SVG@Mso@@QEBA?AV?$optional@ULength@SVG@Mso@@@std@@XZ; Mso::SVG::RadialGradientContext::GetFX(void)
0x1800fdf8d  lea     rdx, [rbp+100h+var_D0]
0x1800fdf91  mov     rcx, rdi
0x1800fdf94  call    ?GetFY@RadialGradientContext@SVG@Mso@@QEBA?AV?$optional@ULength@SVG@Mso@@@std@@XZ; Mso::SVG::RadialGradientContext::GetFY(void)
0x1800fdf99  cmp     [rbp+100h+var_D8], r13b
0x1800fdf9d  jz      short loc_1800FDFB7
0x1800fdf9f  lea     r8, [rsp+200h+var_1D0]; struct Mso::SVG::StyleResolveChain *
0x1800fdfa4  lea     rdx, [rbp+100h+var_E8]; struct Mso::SVG::Length *
0x1800fdfa8  mov     rcx, [rsp+200h+var_1C0]; this
0x1800fdfad  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x1800fdfb2  movaps  xmm7, xmm0
0x1800fdfb5  jmp     short loc_1800FDFBB
0x1800fdfb7  movaps  xmm7, xmm11
0x1800fdfbb  cmp     [rbp+100h+var_C0], r13b
0x1800fdfbf  jz      short loc_1800FDFD9
0x1800fdfc1  lea     r8, [rsp+200h+var_1D0]; struct Mso::SVG::StyleResolveChain *
0x1800fdfc6  lea     rdx, [rbp+100h+var_D0]; struct Mso::SVG::Length *
0x1800fdfca  mov     rcx, [rsp+200h+var_1C0]; this
0x1800fdfcf  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x1800fdfd4  movaps  xmm6, xmm0
0x1800fdfd7  jmp     short loc_1800FDFDD
0x1800fdfd9  movaps  xmm6, xmm12
0x1800fdfdd  movaps  xmm8, xmm7
0x1800fdfe1  subsd   xmm8, xmm11
0x1800fdfe6  movaps  xmm9, xmm6
0x1800fdfea  subsd   xmm9, xmm12
0x1800fdfef  movaps  xmm0, xmm8
0x1800fdff3  mulsd   xmm0, xmm8
0x1800fdff8  movaps  xmm1, xmm9
0x1800fdffc  mulsd   xmm1, xmm9
0x1800fe001  addsd   xmm0, xmm1; X
0x1800fe005  call    sqrt_0
0x1800fe00a  comisd  xmm0, xmm10
0x1800fe00f  jbe     short loc_1800FE035
0x1800fe011  movaps  xmm7, xmm8
0x1800fe015  divsd   xmm7, xmm0
0x1800fe019  mulsd   xmm7, xmm10
0x1800fe01e  addsd   xmm7, xmm11
0x1800fe023  movaps  xmm6, xmm9
0x1800fe027  divsd   xmm6, xmm0
0x1800fe02b  mulsd   xmm6, xmm10
0x1800fe030  addsd   xmm6, xmm12
0x1800fe035  mov     rdx, [rbx+8]
0x1800fe039  mov     rax, [rdx+10h]
0x1800fe03d  cmp     [rbp+100h+arg_20], r13b
0x1800fe044  jz      short loc_1800FE092
0x1800fe046  test    rax, rax
0x1800fe049  jz      short loc_1800FE053
0x1800fe04b  add     rax, 438h
0x1800fe051  jmp     short loc_1800FE067
0x1800fe053  cmp     [rdx+8], r13
0x1800fe057  lea     rax, ?initial@?$StyleMetaData@$08@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<9>::initial
0x1800fe05e  jz      short loc_1800FE067
0x1800fe060  lea     rax, ?inherit@?$StyleMetaData@$08@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<9>::inherit
0x1800fe067  mov     ecx, 8
0x1800fe06c  cmp     [rax+8], r13b
0x1800fe070  jnz     short loc_1800FE0DC
0x1800fe072  mov     rax, [rbx]
0x1800fe075  test    rax, rax
0x1800fe078  jz      short loc_1800FE084
0x1800fe07a  mov     rcx, rax
0x1800fe07d  call    ??$Get@$08@StyleResolveChain@SVG@Mso@@QEBAAEBNXZ; Mso::SVG::StyleResolveChain::Get<9>(void)
0x1800fe082  jmp     short loc_1800FE0DC
0x1800fe084  mov     rdx, [rdx+rcx]
0x1800fe088  mov     rcx, rbx
0x1800fe08b  call    ??$GetNormal@$08@StyleResolveChain@SVG@Mso@@AEBAAEBNAEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<9>(Mso::SVG::Style const &)
0x1800fe090  jmp     short loc_1800FE0DC
0x1800fe092  test    rax, rax
0x1800fe095  jz      short loc_1800FE09F
0x1800fe097  add     rax, 3C8h
0x1800fe09d  jmp     short loc_1800FE0B3
0x1800fe09f  cmp     [rdx+8], r13
0x1800fe0a3  lea     rax, ?initial@?$StyleMetaData@$0M@@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<12>::initial
0x1800fe0aa  jz      short loc_1800FE0B3
0x1800fe0ac  lea     rax, ?inherit@?$StyleMetaData@$0M@@SVG@Mso@@2V?$optional@N@std@@B; std::optional<double> const Mso::SVG::StyleMetaData<12>::inherit
0x1800fe0b3  mov     ecx, 8
0x1800fe0b8  cmp     [rax+8], r13b
0x1800fe0bc  jnz     short loc_1800FE0DC
0x1800fe0be  mov     rax, [rbx]
0x1800fe0c1  test    rax, rax
0x1800fe0c4  jz      short loc_1800FE0D0
0x1800fe0c6  mov     rcx, rax
0x1800fe0c9  call    ??$Get@$0M@@StyleResolveChain@SVG@Mso@@QEBAAEBNXZ; Mso::SVG::StyleResolveChain::Get<12>(void)
0x1800fe0ce  jmp     short loc_1800FE0DC
0x1800fe0d0  mov     rdx, [rdx+rcx]
0x1800fe0d4  mov     rcx, rbx
0x1800fe0d7  call    ??$GetNormal@$0M@@StyleResolveChain@SVG@Mso@@AEBAAEBNAEBVStyle@12@@Z; Mso::SVG::StyleResolveChain::GetNormal<12>(Mso::SVG::Style const &)
0x1800fe0dc  movsd   xmm8, qword ptr [rax]
0x1800fe0e1  cvtpd2ps xmm8, xmm8
0x1800fe0e6  mov     [rsp+200h+var_198], r13b
0x1800fe0eb  lea     rcx, [rbp+100h+var_180]
0x1800fe0ef  call    cs:__imp_??0RadialGradientInfo@GEL@@QEAA@XZ; GEL::RadialGradientInfo::RadialGradientInfo(void)
0x1800fe0f5  nop
0x1800fe0f6  xorps   xmm0, xmm0
0x1800fe0f9  movdqu  xmmword ptr [rsp+200h+var_1C0+8], xmm0
0x1800fe0ff  mov     [rsp+200h+var_1A8], r13
0x1800fe104  mov     rbx, [r14+50h]
0x1800fe108  mov     r15, [r14+58h]
0x1800fe10c  jmp     short loc_1800FE167
0x1800fe10e  mov     rcx, [rbx]
0x1800fe111  test    rcx, rcx
0x1800fe114  jz      loc_1800FE2B4
0x1800fe11a  lea     rax, [rsp+200h+var_1A0]
0x1800fe11f  mov     [rsp+200h+Reserved], rax
0x1800fe124  movaps  xmm3, xmm8
0x1800fe128  lea     r8, [rsp+200h+var_1D0]
0x1800fe12d  lea     rdx, [rbp+100h+var_B8]
0x1800fe131  call    ?ComputeColorStop@ColorStopRenderer@SVG@Mso@@QEBA?AUGradientStop@GEL@@AEBVStyleResolveChain@23@MAEAV?$optional@N@std@@@Z; Mso::SVG::ColorStopRenderer::ComputeColorStop(Mso::SVG::StyleResolveChain const &,float,std::optional<double> &)
0x1800fe136  mov     rdx, [rsp+200h+var_1B0]
0x1800fe13b  cmp     rdx, [rsp+200h+var_1A8]
0x1800fe140  jz      short loc_1800FE156
0x1800fe142  movups  xmm0, xmmword ptr [rax]
0x1800fe145  movups  xmmword ptr [rdx], xmm0
0x1800fe148  mov     eax, [rax+10h]
0x1800fe14b  mov     [rdx+10h], eax
0x1800fe14e  add     [rsp+200h+var_1B0], 14h
0x1800fe154  jmp     short loc_1800FE163
0x1800fe156  mov     r8, rax
0x1800fe159  lea     rcx, [rsp+200h+var_1C0+8]
0x1800fe15e  call    ??$_Emplace_reallocate@AEBUGradientStop@GEL@@@?$vector@UGradientStop@GEL@@V?$allocator@UGradientStop@GEL@@@std@@@std@@AEAAPEAUGradientStop@GEL@@QEAU23@AEBU23@@Z; std::vector<GEL::GradientStop>::_Emplace_reallocate<GEL::GradientStop const &>(GEL::GradientStop * const,GEL::GradientStop const &)
0x1800fe163  add     rbx, 8
0x1800fe167  cmp     rbx, r15
0x1800fe16a  jnz     short loc_1800FE10E
0x1800fe16c  xor     edx, edx
0x1800fe16e  lea     ecx, [rdx+30h]
0x1800fe171  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1800fe177  test    rax, rax
0x1800fe17a  jnz     short loc_1800FE183
0x1800fe17c  call    cs:__imp_?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x1800fe182  int     3; Trap to Debugger
0x1800fe183  mov     [rbp+100h+arg_0], rax
0x1800fe18a  mov     r8, r12
0x1800fe18d  mov     rdx, rax
0x1800fe190  mov     rcx, r14
0x1800fe193  call    ?ComputeTransform@GradientRenderer@SVG@Mso@@QEBA?AU?$TAffine3x3@N@Math@@PEBURect@GEL@@@Z; Mso::SVG::GradientRenderer::ComputeTransform(GEL::Rect const *)
0x1800fe198  nop
0x1800fe199  mov     [rbp+100h+var_110], rax
0x1800fe19d  mov     r8, [rsp+200h+var_1B0]
0x1800fe1a2  mov     rdx, [rsp+200h+var_1C0+8]
0x1800fe1a7  sub     r8, rdx
0x1800fe1aa  sar     r8, 2
0x1800fe1ae  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800fe1b8  imul    r8, rax
0x1800fe1bc  test    r8, r8
0x1800fe1bf  jz      loc_1800FE29E
0x1800fe1c5  movups  xmm0, xmmword ptr [rdx]
0x1800fe1c8  movdqu  [rbp+100h+var_170], xmm0
0x1800fe1cd  lea     rax, [r8-1]
0x1800fe1d1  cmp     rax, r8
0x1800fe1d4  jnb     loc_1800FE29E
0x1800fe1da  lea     rax, [rax+rax*4]
0x1800fe1de  movups  xmm0, xmmword ptr [rdx+rax*4]
0x1800fe1e2  movdqu  [rbp+100h+var_160], xmm0
0x1800fe1e7  lea     rcx, [rbp+100h+var_180]
0x1800fe1eb  call    cs:__imp_?SetShadeColors@GradientInfo@GEL@@QEAAXPEBUGradientStop@2@I@Z; GEL::GradientInfo::SetShadeColors(GEL::GradientStop const *,uint)
0x1800fe1f1  mov     [rbp+100h+var_150], 3F800000h
0x1800fe1f8  mov     [rbp+100h+var_14C], 1
0x1800fe1ff  movsd   [rbp+100h+var_130], xmm7
0x1800fe204  movsd   [rbp+100h+var_128], xmm6
0x1800fe209  movsd   [rbp+100h+var_140], xmm11
0x1800fe20f  movsd   [rbp+100h+var_138], xmm12
0x1800fe215  movsd   [rbp+100h+var_120], xmm13
0x1800fe21b  movsd   [rbp+100h+var_118], xmm13
0x1800fe221  mov     rcx, rdi
0x1800fe224  call    ?GetSpread@GradientContext@SVG@Mso@@QEBA?AW4ExtendMode@ARC@@XZ; Mso::SVG::GradientContext::GetSpread(void)
0x1800fe229  mov     [rbp+100h+var_148], eax
0x1800fe22c  lea     rdx, [rbp+100h+var_180]
0x1800fe230  lea     rcx, [rbp+100h+arg_0]
0x1800fe237  call    cs:__imp_?Create@IBrushRadialGradient@GEL@@SA?AV?$TCntPtr@UIBrushRadialGradient@GEL@@@Ofc@@AEBURadialGradientInfo@2@@Z; GEL::IBrushRadialGradient::Create(GEL::RadialGradientInfo const &)
0x1800fe23d  mov     rcx, [rax]
0x1800fe240  mov     [rsi], rcx
0x1800fe243  test    rcx, rcx
0x1800fe246  jz      short loc_1800FE254
0x1800fe248  mov     rax, [rcx]
0x1800fe24b  mov     rax, [rax]
0x1800fe24e  call    cs:__guard_dispatch_icall_fptr
0x1800fe254  mov     rcx, [rbp+100h+arg_0]
0x1800fe25b  test    rcx, rcx
0x1800fe25e  jz      short loc_1800FE26E
0x1800fe260  mov     rax, [rcx]
0x1800fe263  mov     rax, [rax+8]
0x1800fe267  call    cs:__guard_dispatch_icall_fptr
0x1800fe26d  nop
0x1800fe26e  lea     rcx, [rsp+200h+var_1C0+8]
0x1800fe273  call    ?_Tidy@?$vector@UGradientStop@GEL@@V?$allocator@UGradientStop@GEL@@@std@@@std@@AEAAXXZ; std::vector<GEL::GradientStop>::_Tidy(void)
0x1800fe278  movdqa  xmm0, cs:__xmm@0000000000004de10000000000004de1
0x1800fe280  movdqu  xmmword ptr [rsp+200h+var_1C0+8], xmm0
0x1800fe286  mov     [rsp+200h+var_1A8], 4DE1h
0x1800fe28f  lea     rcx, [rbp+100h+var_180]
0x1800fe293  call    cs:__imp_??1RadialGradientInfo@GEL@@UEAA@XZ; GEL::RadialGradientInfo::~RadialGradientInfo(void)
0x1800fe299  jmp     loc_1800FDEC0
0x1800fe29e  mov     [rsp+200h+Reserved], r13; Reserved
0x1800fe2a3  xor     r9d, r9d; LineNo
0x1800fe2a6  xor     r8d, r8d; FileName
0x1800fe2a9  xor     edx, edx; FunctionName
0x1800fe2ab  xor     ecx, ecx; Expression
0x1800fe2ad  call    cs:__imp__invoke_watson
0x1800fe2b4  xor     edx, edx
0x1800fe2b6  mov     ecx, 1E3C3840h
  ... truncated ...
```
