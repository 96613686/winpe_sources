# Mso::SVG::PatternRenderer::ComputePaint(Mso::SVG::StyleResolveChain const &,GEL::Rect const *,bool)

- ea: `0x1801035d0`
- end: `0x180103c4e`
- name: `?ComputePaint@PatternRenderer@SVG@Mso@@UEAA?AV?$TCntPtr@UIBrush@GEL@@@3@AEBVStyleResolveChain@23@PEBURect@GEL@@_N@Z`
- size: `1662`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002bec`
- `0x180007230`
- `0x18003f8f0`
- `0x18003fd34`
- `0x180041d60`
- `0x180041df8`
- `0x180043440`
- `0x1800435fc`
- `0x18004e760`
- `0x18004eba4`
- `0x18004f538`
- `0x180100ee4`
- `0x180100fb8`
- `0x180101010`
- `0x180101064`
- `0x1801010b4`
- `0x180101104`
- `0x180101154`
- `0x1801035d0`
- `0x1801395e4`
- `0x180139658`
- `0x18013e0c0`
- `0x18013f7e8`
- `0x18013f810`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180103c29`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180103c37`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180103c47`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180103c29`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180103c37`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180103c47`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180103bbc`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180103bd6`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180103bbc`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180103bd6`
- `gfx!?Create@IBrushEffect@GEL@@SA?AV?$TCntPtr@UIBrushEffect@GEL@@@Ofc@@AEBU?$TRect@N@Math@@AEBUIEffect@2@AEBU?$TAffine3x3@N@6@PEBU86@@Z` at `0x180103ab5`
- `gfx!?Create@IBrushEffect@GEL@@SA?AV?$TCntPtr@UIBrushEffect@GEL@@@Ofc@@AEBU?$TRect@N@Math@@AEBUIEffect@2@AEBU?$TAffine3x3@N@6@PEBU86@@Z` at `0x180103ab5`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
_QWORD *__fastcall Mso::SVG::PatternRenderer::ComputePaint(__int64 a1, _QWORD *a2, __int64 a3, double *a4)
{
  __int64 v8; // rdi
  int Units; // r12d
  Mso::SVG::LengthResolver *p_si128; // rsi
  __int64 v11; // rax
  const struct Mso::SVG::Length *v12; // rax
  double v13; // xmm9_8
  const struct Mso::SVG::Length *v14; // rax
  double v15; // xmm10_8
  const struct Mso::SVG::Length *Width; // rax
  double v17; // xmm8_8
  const struct Mso::SVG::Length *Height; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  double v21; // xmm0_8
  double v22; // xmm2_8
  double v23; // xmm1_8
  double v24; // xmm7_8
  double v25; // xmm6_8
  double v26; // xmm1_8
  Mso::SVG::RenderableRenderer *v27; // rsi
  bool v28; // r12
  _QWORD *EffectOrEmptyContainer; // rax
  __int128 *TransformedBounds; // rax
  __int64 v31; // rbx
  __int64 v32; // rax
  __int64 v33; // rbx
  __int128 *v34; // rax
  Mso::SVG::RenderableRenderer *v35; // rcx
  struct GEL::Rect *v36; // rdi
  void (__fastcall ****v37)(_QWORD); // rax
  void (__fastcall ***v38)(_QWORD); // rcx
  Mso::SVG::RenderableRenderer *v39; // rcx
  __int64 v40; // rcx
  Mso::Memory *v41; // rbx
  Mso::Memory *v42; // rdi
  void *v43; // rdx
  void *v44; // rdx
  bool v46; // [rsp+30h] [rbp-D8h]
  Mso::SVG::RenderableRenderer *v47; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B8h] BYREF
  Mso::Memory *v49; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v50[2]; // [rsp+60h] [rbp-A8h] BYREF
  Mso::SVG::LengthResolver *v51; // [rsp+70h] [rbp-98h]
  __int64 v52; // [rsp+78h] [rbp-90h] BYREF
  __int128 v53; // [rsp+80h] [rbp-88h] BYREF
  _QWORD v54[2]; // [rsp+90h] [rbp-78h] BYREF
  __int128 v55; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v56; // [rsp+B0h] [rbp-58h]
  __int64 v57; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v58; // [rsp+D0h] [rbp-38h] BYREF
  __int128 v59; // [rsp+E0h] [rbp-28h]
  __int128 v60; // [rsp+F0h] [rbp-18h]
  _QWORD v61[3]; // [rsp+100h] [rbp-8h] BYREF
  __m128i v62; // [rsp+118h] [rbp+10h] BYREF
  __m128i v63; // [rsp+128h] [rbp+20h]
  __int128 v64; // [rsp+138h] [rbp+30h]
  _OWORD v65[2]; // [rsp+148h] [rbp+40h] BYREF
  double v66; // [rsp+168h] [rbp+60h]
  double v67; // [rsp+170h] [rbp+68h]
  __m128i si128; // [rsp+178h] [rbp+70h] BYREF
  double v69; // [rsp+188h] [rbp+80h]
  __int128 v70; // [rsp+190h] [rbp+88h] BYREF
  double v71; // [rsp+1A0h] [rbp+98h]
  double v72; // [rsp+1A8h] [rbp+A0h]
  __m128i v73; // [rsp+1B0h] [rbp+A8h]
  __m128i v74; // [rsp+1C0h] [rbp+B8h]
  __int128 v75; // [rsp+1D0h] [rbp+C8h]
  _OWORD v76[8]; // [rsp+1E0h] [rbp+D8h] BYREF
  struct GEL::Rect *v77; // [rsp+298h] [rbp+190h] BYREF

  v8 = *(_QWORD *)(a1 + 16);
  if ( !v8 )
    goto LABEL_52;
  _castguard_slow_path_check_user_handled(*(_QWORD *)v8, 7696, 0);
  if ( !*(_BYTE *)(v8 + 320) )
    goto LABEL_49;
  Units = Mso::SVG::PatternContext::GetUnits(v8);
  LODWORD(v77) = Mso::SVG::PatternContext::GetContentUnits(v8);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v69 = sqrt_0(1.0);
  if ( Units )
    p_si128 = (Mso::SVG::LengthResolver *)&si128;
  else
    p_si128 = *(Mso::SVG::LengthResolver **)(a3 + 16);
  v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 104LL))(v8);
  v50[0] = 0;
  v50[1] = v11;
  v51 = p_si128;
  v12 = (const struct Mso::SVG::Length *)Mso::SVG::PatternContext::GetX(v8, v54);
  v13 = Mso::SVG::LengthResolver::ResolveLength(p_si128, v12, (const struct Mso::SVG::StyleResolveChain *)v50);
  v14 = (const struct Mso::SVG::Length *)Mso::SVG::PatternContext::GetY(v8, v54);
  v15 = Mso::SVG::LengthResolver::ResolveLength(v51, v14, (const struct Mso::SVG::StyleResolveChain *)v50);
  Width = (const struct Mso::SVG::Length *)Mso::SVG::PatternContext::GetWidth(v8, v54);
  v17 = Mso::SVG::LengthResolver::ResolveLength(v51, Width, (const struct Mso::SVG::StyleResolveChain *)v50);
  Height = (const struct Mso::SVG::Length *)Mso::SVG::PatternContext::GetHeight(v8, v54);
  v21 = Mso::SVG::LengthResolver::ResolveLength(v51, Height, (const struct Mso::SVG::StyleResolveChain *)v50);
  if ( Units == 1 )
  {
    v22 = a4[2] - *a4;
    v17 = v17 * v22;
    v23 = a4[3] - a4[1];
    v21 = v21 * v23;
    v13 = v13 * v22 + *a4;
    v15 = v15 * v23 + a4[1];
  }
  if ( v17 <= 0.0 || v21 <= 0.0 )
  {
LABEL_49:
    *a2 = 0;
    return a2;
  }
  v24 = fmax(1.0, v17);
  v25 = fmax(1.0, v21);
  v62 = _mm_load_si128((const __m128i *)&_xmm);
  v63 = _mm_load_si128((const __m128i *)&_xmm);
  v64 = 0;
  if ( *(_BYTE *)(a1 + 72) )
  {
    Mso::SVG::ViewboxAdapter::CalculateViewboxTransform(a1 + 40, v19, v20, &v62);
  }
  else if ( (_DWORD)v77 == 1 )
  {
    v26 = a4[3] - a4[1];
    *(double *)v62.m128i_i64 = a4[2] - *a4;
    *(double *)&v63.m128i_i64[1] = v26;
  }
  v49 = 0;
  Mso::SVG::PatternContext::GetChildren(v8, &v48, &v49);
  Mso::SVG::RenderableRenderer::Create(&v47, v48, *(_QWORD *)(a1 + 24));
  v27 = v47;
  if ( v47 )
    _castguard_slow_path_check_user_handled(*(_QWORD *)v47, 13376, 144);
  else
    v27 = 0;
  v54[0] = v27;
  if ( v27 )
    (**(void (__fastcall ***)(Mso::SVG::RenderableRenderer *))v27)(v27);
  v55 = 0;
  v56 = 0;
  v77 = 0;
  if ( !v27 )
  {
LABEL_53:
    CrashWithRecovery(0x1E3C3840u, 0);
    JUMPOUT(0x180103C4DLL);
  }
  v28 = Mso::SVG::RenderableRenderer::BeginRendering(
          v27,
          (const struct Mso::SVG::StyleResolveChain *)v50,
          (struct GEL::Rect *)&v55,
          0,
          &v77,
          v46);
  v53 = 0;
  Mso::SVG::ContainerRenderer::RenderChildren(
    v27,
    (struct GEL::EffectAccumulator *)&v53,
    (const struct Mso::SVG::StyleResolveChain *)v50,
    v77,
    0);
  v65[0] = _mm_load_si128((const __m128i *)&_xmm);
  v65[1] = _mm_load_si128((const __m128i *)&_xmm);
  v66 = v13;
  v67 = v15;
  v58 = *(_OWORD *)(a1 + 88);
  v59 = *(_OWORD *)(a1 + 104);
  v60 = *(_OWORD *)(a1 + 120);
  Math::operator*=<double,double,0>(v65, &v58);
  EffectOrEmptyContainer = (_QWORD *)GEL::EffectAccumulator::GetEffectOrEmptyContainer(&v53, &v52);
  Mso::SVG::ApplyTransform(&v57, *EffectOrEmptyContainer, &v62);
  if ( v52 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 8LL))(v52);
  if ( v28 )
  {
    TransformedBounds = (__int128 *)GEL::Rect::GetTransformedBounds(&v55, &v58, &v62);
    v55 = *TransformedBounds;
    v56 = TransformedBounds[1];
  }
  v70 = 0;
  v71 = v24;
  v72 = v25;
  v31 = *(_QWORD *)(a3 + 16);
  v32 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 104LL))(v8);
  v61[0] = 0;
  v61[1] = v32;
  v61[2] = v31;
  v73 = _mm_load_si128((const __m128i *)&_xmm);
  v74 = _mm_load_si128((const __m128i *)&_xmm);
  v75 = 0;
  v33 = v57;
  Mso::SVG::RenderableRenderer::ApplyStandardOverflowEffects(
    (_DWORD)v27,
    (unsigned int)&v77,
    v57,
    (unsigned int)v61,
    (__int64)&v70,
    (__int64)v77);
  if ( v28 )
  {
    v34 = (__int128 *)GEL::Rect::GetTransformedBounds(&v55, &v58, v65);
    v55 = *v34;
    v56 = v34[1];
  }
  v35 = *(Mso::SVG::RenderableRenderer **)(a1 + 32);
  if ( !v35 )
  {
    CrashWithRecovery(0x1E3C3840u, 0);
LABEL_52:
    CrashWithRecovery(0x1E3C3843u, 0);
    goto LABEL_53;
  }
  Mso::SVG::RenderableRenderer::EndRendering(v35, (const struct GEL::Rect *)&v55, 0, 0);
  v36 = v77;
  if ( v77 )
  {
    v76[0] = _mm_load_si128((const __m128i *)&_xmm);
    v76[1] = _mm_load_si128((const __m128i *)&_xmm);
    v76[2] = 0;
    v58 = 0;
    *(double *)&v59 = v24;
    *((double *)&v59 + 1) = v25;
    v37 = (void (__fastcall ****)(_QWORD))GEL::IBrushEffect::Create(&v52, &v58, v77, v76, v65);
    v38 = *v37;
    *a2 = *v37;
    if ( v38 )
      (**v38)(v38);
    if ( v52 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 8LL))(v52);
    (*(void (__fastcall **)(struct GEL::Rect *))(*(_QWORD *)v36 + 8LL))(v36);
  }
  else
  {
    *a2 = 0;
  }
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 8LL))(v33);
  if ( *((_QWORD *)&v53 + 1) )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v53 + 1) + 8LL))(*((_QWORD *)&v53 + 1));
  if ( (_QWORD)v53 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v53 + 8LL))(v53);
  (*(void (__fastcall **)(Mso::SVG::RenderableRenderer *))(*(_QWORD *)v27 + 8LL))(v27);
  v39 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(Mso::SVG::RenderableRenderer *))(*(_QWORD *)v39 + 8LL))(v39);
  }
  v40 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 8LL))(v40);
  }
  v41 = v49;
  if ( v49 )
  {
    v49 = 0;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v41, 0xFFFFFFFF) == 1 )
    {
      v42 = (Mso::Memory *)*((_QWORD *)v41 + 2);
      if ( v42 )
      {
        __1__tuple_U__StyleRawData__01_SVG_Mso__U__StyleRawData__02_23_U__StyleRawData__03_23_U__StyleRawData__04_23_U__StyleRawData__05_23_U__StyleRawData__06_23_U__StyleRawData__07_23_U__StyleRawData__08_23_U__StyleRawData__09_23_U__StyleRawData__0L__23_U__StyleRawData__0M__23_U__StyleRawData__0N__23_U__StyleRawData__0O__23_U__StyleRawData__0P__23_U__StyleRawData__0BA__23_U__StyleRawData__0BB__23_U__StyleRawData__0BC__23_U__StyleRawData__0BD__23_U__StyleRawData__0BE__23_U__StyleRawData__0BF__23_U__StyleRawData__0BG__23_U__StyleRawData__0BH__23_U__StyleRawData__0BI__23_U__StyleRawData__0BJ__23_U__StyleRawData__0BK__23_U__StyleRawData__0BL__23_U__StyleRawData__0BM__23_U__StyleRawData__0BN__23_U__StyleRawData__0BO__23_U__StyleRawData__0BP__23_U__StyleRawData__0CA__23_U__StyleRawData__0CB__23_U__StyleRawData__0CC__23_U__StyleRawData__0CD__23_U__StyleRawData__0CE__23_U__StyleRawData__0CF__23_U__StyleRawData__0CG__23_U__StyleRawData__0CH__23_U__StyleRawData__0CI__23_U__StyleRawData__0CJ__23_U__StyleRawData__0CK__23_U__StyleRawData__0CL__23_U__StyleRawData__0CM__23_U__StyleRawData__0CN__23_U__StyleRawData__0CO__23_U__StyleRawData__0CP__23__std__QEAA_XZ(*((_QWORD *)v41 + 2));
        Mso::Memory::Free(v42, v43);
      }
      *((_QWORD *)v41 + 2) = 19937;
      Mso::TCntPtr<Mso::SVG::Style const>::~TCntPtr<Mso::SVG::Style const>((char *)v41 + 8);
      Mso::Memory::Free(v41, v44);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1801035d0  mov     rax, rsp
0x1801035d3  mov     [rax+10h], rbx
0x1801035d7  mov     [rax+18h], rsi
0x1801035db  mov     [rax+20h], rdi
0x1801035df  push    rbp
0x1801035e0  push    r12
0x1801035e2  push    r13
0x1801035e4  push    r14
0x1801035e6  push    r15
0x1801035e8  lea     rbp, [rax-188h]
0x1801035ef  sub     rsp, 260h
0x1801035f6  movaps  xmmword ptr [rax-38h], xmm6
0x1801035fa  movaps  xmmword ptr [rax-48h], xmm7
0x1801035fe  movaps  xmmword ptr [rax-58h], xmm8
0x180103603  movaps  xmmword ptr [rax-68h], xmm9
0x180103608  movaps  xmmword ptr [rax-78h], xmm10
0x18010360d  mov     rbx, r9
0x180103610  mov     r13, r8
0x180103613  mov     r14, rdx
0x180103616  mov     r15, rcx
0x180103619  mov     rdi, [rcx+10h]
0x18010361d  test    rdi, rdi
0x180103620  jz      loc_180103C30
0x180103626  xor     r8d, r8d
0x180103629  mov     edx, 1E10h
0x18010362e  mov     rcx, [rdi]
0x180103631  call    __castguard_slow_path_check_user_handled
0x180103636  cmp     byte ptr [rdi+140h], 0
0x18010363d  jz      loc_180103BDE
0x180103643  mov     rcx, rdi
0x180103646  call    ?GetUnits@PatternContext@SVG@Mso@@QEBA?AW4PatternUnits@23@XZ; Mso::SVG::PatternContext::GetUnits(void)
0x18010364b  mov     r12d, eax
0x18010364e  mov     rcx, rdi
0x180103651  call    ?GetContentUnits@PatternContext@SVG@Mso@@QEBA?AW4PatternUnits@23@XZ; Mso::SVG::PatternContext::GetContentUnits(void)
0x180103656  mov     dword ptr [rbp+180h+arg_0], eax
0x18010365c  movdqa  xmm0, cs:__xmm@3ff00000000000003ff0000000000000
0x180103664  movups  [rbp+180h+var_110], xmm0
0x180103668  movsd   xmm6, cs:__real@3ff0000000000000
0x180103670  movaps  xmm0, xmm6; X
0x180103673  call    sqrt_0
0x180103678  movsd   [rbp+180h+var_100], xmm0
0x180103680  test    r12d, r12d
0x180103683  jnz     short loc_18010368B
0x180103685  mov     rsi, [r13+10h]
0x180103689  jmp     short loc_18010368F
0x18010368b  lea     rsi, [rbp+180h+var_110]
0x18010368f  mov     rax, [rdi]
0x180103692  mov     rcx, rdi
0x180103695  mov     rax, [rax+68h]
0x180103699  call    cs:__guard_dispatch_icall_fptr
0x18010369f  mov     [rsp+280h+var_228], 0
0x1801036a8  mov     [rsp+280h+var_220], rax
0x1801036ad  mov     [rsp+280h+var_218], rsi
0x1801036b2  lea     rdx, [rbp+180h+var_1F8]
0x1801036b6  mov     rcx, rdi
0x1801036b9  call    ?GetX@PatternContext@SVG@Mso@@QEBA?AULength@23@XZ; Mso::SVG::PatternContext::GetX(void)
0x1801036be  lea     r8, [rsp+280h+var_228]; struct Mso::SVG::StyleResolveChain *
0x1801036c3  mov     rdx, rax; struct Mso::SVG::Length *
0x1801036c6  mov     rcx, [rsp+280h+var_218]; this
0x1801036cb  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x1801036d0  movaps  xmm9, xmm0
0x1801036d4  lea     rdx, [rbp+180h+var_1F8]
0x1801036d8  mov     rcx, rdi
0x1801036db  call    ?GetY@PatternContext@SVG@Mso@@QEBA?AULength@23@XZ; Mso::SVG::PatternContext::GetY(void)
0x1801036e0  lea     r8, [rsp+280h+var_228]; struct Mso::SVG::StyleResolveChain *
0x1801036e5  mov     rdx, rax; struct Mso::SVG::Length *
0x1801036e8  mov     rcx, [rsp+280h+var_218]; this
0x1801036ed  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x1801036f2  movaps  xmm10, xmm0
0x1801036f6  lea     rdx, [rbp+180h+var_1F8]
0x1801036fa  mov     rcx, rdi
0x1801036fd  call    ?GetWidth@PatternContext@SVG@Mso@@QEBA?AULength@23@XZ; Mso::SVG::PatternContext::GetWidth(void)
0x180103702  lea     r8, [rsp+280h+var_228]; struct Mso::SVG::StyleResolveChain *
0x180103707  mov     rdx, rax; struct Mso::SVG::Length *
0x18010370a  mov     rcx, [rsp+280h+var_218]; this
0x18010370f  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x180103714  movaps  xmm8, xmm0
0x180103718  lea     rdx, [rbp+180h+var_1F8]
0x18010371c  mov     rcx, rdi
0x18010371f  call    ?GetHeight@PatternContext@SVG@Mso@@QEBA?AULength@23@XZ; Mso::SVG::PatternContext::GetHeight(void)
0x180103724  lea     r8, [rsp+280h+var_228]; struct Mso::SVG::StyleResolveChain *
0x180103729  mov     rdx, rax; struct Mso::SVG::Length *
0x18010372c  mov     rcx, [rsp+280h+var_218]; this
0x180103731  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x180103736  cmp     r12d, 1
0x18010373a  jnz     short loc_18010376D
0x18010373c  movsd   xmm2, qword ptr [rbx+10h]
0x180103741  subsd   xmm2, qword ptr [rbx]
0x180103745  mulsd   xmm8, xmm2
0x18010374a  movsd   xmm1, qword ptr [rbx+18h]
0x18010374f  subsd   xmm1, qword ptr [rbx+8]
0x180103754  mulsd   xmm0, xmm1
0x180103758  mulsd   xmm9, xmm2
0x18010375d  addsd   xmm9, qword ptr [rbx]
0x180103762  mulsd   xmm10, xmm1
0x180103767  addsd   xmm10, qword ptr [rbx+8]
0x18010376d  xorps   xmm1, xmm1
0x180103770  comisd  xmm1, xmm8
0x180103775  jnb     loc_180103BDE
0x18010377b  comisd  xmm1, xmm0
0x18010377f  jnb     loc_180103BDE
0x180103785  movaps  xmm7, xmm6
0x180103788  maxsd   xmm7, xmm8
0x18010378d  maxsd   xmm6, xmm0
0x180103791  movdqa  xmm0, cs:__xmm@00000000000000003ff0000000000000
0x180103799  movups  [rbp+180h+var_170], xmm0
0x18010379d  movdqa  xmm1, cs:__xmm@3ff00000000000000000000000000000
0x1801037a5  movups  [rbp+180h+var_160], xmm1
0x1801037a9  xorps   xmm0, xmm0
0x1801037ac  movups  [rbp+180h+var_150], xmm0
0x1801037b0  lea     rcx, [r15+28h]
0x1801037b4  cmp     byte ptr [rcx+20h], 0
0x1801037b8  jz      short loc_1801037CB
0x1801037ba  lea     r9, [rbp+180h+var_170]
0x1801037be  movaps  xmm2, xmm6
0x1801037c1  movaps  xmm1, xmm7
0x1801037c4  call    ?CalculateViewboxTransform@ViewboxAdapter@SVG@Mso@@QEBAXNNAEAU?$TAffine3x3@N@Math@@@Z; Mso::SVG::ViewboxAdapter::CalculateViewboxTransform(double,double,Math::TAffine3x3<double> &)
0x1801037c9  jmp     short loc_1801037F1
0x1801037cb  cmp     dword ptr [rbp+180h+arg_0], 1
0x1801037d2  jnz     short loc_1801037F1
0x1801037d4  movsd   xmm1, qword ptr [rbx+18h]
0x1801037d9  subsd   xmm1, qword ptr [rbx+8]
0x1801037de  movsd   xmm0, qword ptr [rbx+10h]
0x1801037e3  subsd   xmm0, qword ptr [rbx]
0x1801037e7  movsd   qword ptr [rbp+180h+var_170], xmm0
0x1801037ec  movsd   qword ptr [rbp+180h+var_160+8], xmm1
0x1801037f1  xor     ebx, ebx
0x1801037f3  mov     [rsp+280h+var_230], rbx
0x1801037f8  lea     r8, [rsp+280h+var_230]
0x1801037fd  lea     rdx, [rsp+280h+var_238]
0x180103802  mov     rcx, rdi
0x180103805  call    ?GetChildren@PatternContext@SVG@Mso@@QEBA?AV?$TCntPtr@VContainerContext@SVG@Mso@@@3@AEAV?$TCntPtr@$$CBVStyle@SVG@Mso@@@3@@Z; Mso::SVG::PatternContext::GetChildren(Mso::TCntPtr<Mso::SVG::Style const> &)
0x18010380a  nop
0x18010380b  mov     r8, [r15+18h]
0x18010380f  mov     rdx, [rsp+280h+var_238]
0x180103814  lea     rcx, [rsp+280h+var_240]
0x180103819  call    ?Create@RenderableRenderer@SVG@Mso@@SA?AV?$TCntPtr@VRenderableRenderer@SVG@Mso@@@3@AEAVRenderableContext@23@AEAVEnvironmentRenderer@23@@Z; Mso::SVG::RenderableRenderer::Create(Mso::SVG::RenderableContext &,Mso::SVG::EnvironmentRenderer &)
0x18010381e  nop
0x18010381f  mov     rsi, [rsp+280h+var_240]
0x180103824  test    rsi, rsi
0x180103827  jz      short loc_18010383E
0x180103829  mov     edx, 3440h
0x18010382e  mov     r8d, 90h
0x180103834  mov     rcx, [rsi]
0x180103837  call    __castguard_slow_path_check_user_handled
0x18010383c  jmp     short loc_180103841
0x18010383e  mov     rsi, rbx
0x180103841  mov     [rbp+180h+var_1F8], rsi
0x180103845  test    rsi, rsi
0x180103848  jz      short loc_18010385A
0x18010384a  mov     rax, [rsi]
0x18010384d  mov     rcx, rsi
0x180103850  mov     rax, [rax]
0x180103853  call    cs:__guard_dispatch_icall_fptr
0x180103859  nop
0x18010385a  xorps   xmm0, xmm0
0x18010385d  movups  [rbp+180h+var_1E8], xmm0
0x180103861  xorps   xmm1, xmm1
0x180103864  movups  [rbp+180h+var_1D8], xmm1
0x180103868  mov     [rbp+180h+arg_0], rbx
0x18010386f  test    rsi, rsi
0x180103872  jz      loc_180103C40
0x180103878  lea     rax, [rbp+180h+arg_0]
0x18010387f  mov     [rsp+280h+var_260], rax; struct GEL::Rect **
0x180103884  xor     r9d, r9d; struct GEL::Rect *
0x180103887  lea     r8, [rbp+180h+var_1E8]; struct GEL::Rect *
0x18010388b  lea     rdx, [rsp+280h+var_228]; struct Mso::SVG::StyleResolveChain *
0x180103890  mov     rcx, rsi; this
0x180103893  call    ?BeginRendering@RenderableRenderer@SVG@Mso@@QEBA_NAEBVStyleResolveChain@23@AEAURect@GEL@@PEBU56@AEAPEAU56@_N@Z; Mso::SVG::RenderableRenderer::BeginRendering(Mso::SVG::StyleResolveChain const &,GEL::Rect &,GEL::Rect const *,GEL::Rect * &,bool)
0x180103898  mov     r12b, al
0x18010389b  xorps   xmm0, xmm0
0x18010389e  movdqu  [rsp+280h+var_210+8], xmm0
0x1801038a4  mov     [rsp+280h+var_260], rbx; struct GEL::IColorResolver *
0x1801038a9  mov     r9, [rbp+180h+arg_0]; struct GEL::Rect *
0x1801038b0  lea     r8, [rsp+280h+var_228]; struct Mso::SVG::StyleResolveChain *
0x1801038b5  lea     rdx, [rsp+280h+var_210+8]; struct GEL::EffectAccumulator *
0x1801038ba  mov     rcx, rsi; this
0x1801038bd  call    ?RenderChildren@ContainerRenderer@SVG@Mso@@QEAAXAEAVEffectAccumulator@GEL@@AEBVStyleResolveChain@23@PEAURect@5@PEBUIColorResolver@5@@Z; Mso::SVG::ContainerRenderer::RenderChildren(GEL::EffectAccumulator &,Mso::SVG::StyleResolveChain const &,GEL::Rect *,GEL::IColorResolver const *)
0x1801038c2  movdqa  xmm0, cs:__xmm@00000000000000003ff0000000000000
0x1801038ca  movups  [rbp+180h+var_140], xmm0
0x1801038ce  movdqa  xmm1, cs:__xmm@3ff00000000000000000000000000000
0x1801038d6  movups  [rbp+180h+var_130], xmm1
0x1801038da  movsd   [rbp+180h+var_120], xmm9
0x1801038e0  movsd   [rbp+180h+var_118], xmm10
0x1801038e6  movups  xmm0, xmmword ptr [r15+58h]
0x1801038eb  movups  [rbp+180h+var_1B8], xmm0
0x1801038ef  movups  xmm1, xmmword ptr [r15+68h]
0x1801038f4  movups  [rbp+180h+var_1A8], xmm1
0x1801038f8  movups  xmm0, xmmword ptr [r15+78h]
0x1801038fd  movups  [rbp+180h+var_198], xmm0
0x180103901  lea     rdx, [rbp+180h+var_1B8]
0x180103905  lea     rcx, [rbp+180h+var_140]
0x180103909  call    ??$?XNN$0A@@Math@@YAAEAU?$TAffine3x3@N@0@AEAU10@AEBU10@@Z; Math::operator*=<double,double,0>(Math::TAffine3x3<double> &,Math::TAffine3x3<double> const &)
0x18010390e  lea     rdx, [rsp+280h+var_210]
0x180103913  lea     rcx, [rsp+280h+var_210+8]
0x180103918  call    ?GetEffectOrEmptyContainer@EffectAccumulator@GEL@@QEAA?AV?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@XZ; GEL::EffectAccumulator::GetEffectOrEmptyContainer(void)
0x18010391d  nop
0x18010391e  lea     r8, [rbp+180h+var_170]
0x180103922  mov     rdx, [rax]
0x180103925  lea     rcx, [rbp+180h+var_1C0]
0x180103929  call    ?ApplyTransform@SVG@Mso@@YA?AV?$TCntPtr@$$CBUIEffect@GEL@@@2@AEBUIEffect@GEL@@AEBU?$TAffine3x3@N@Math@@@Z; Mso::SVG::ApplyTransform(GEL::IEffect const &,Math::TAffine3x3<double> const &)
0x18010392e  nop
0x18010392f  mov     rcx, qword ptr [rsp+280h+var_210]
0x180103934  test    rcx, rcx
0x180103937  jz      short loc_180103946
0x180103939  mov     rax, [rcx]
0x18010393c  mov     rax, [rax+8]
0x180103940  call    cs:__guard_dispatch_icall_fptr
0x180103946  test    r12b, r12b
0x180103949  jz      short loc_18010396B
0x18010394b  lea     r8, [rbp+180h+var_170]
0x18010394f  lea     rdx, [rbp+180h+var_1B8]
0x180103953  lea     rcx, [rbp+180h+var_1E8]
0x180103957  call    ?GetTransformedBounds@Rect@GEL@@QEBA?AU12@AEBU?$TAffine3x3@N@Math@@@Z; GEL::Rect::GetTransformedBounds(Math::TAffine3x3<double> const &)
0x18010395c  movups  xmm0, xmmword ptr [rax]
0x18010395f  movups  [rbp+180h+var_1E8], xmm0
0x180103963  movups  xmm1, xmmword ptr [rax+10h]
0x180103967  movups  [rbp+180h+var_1D8], xmm1
0x18010396b  xorps   xmm0, xmm0
0x18010396e  movups  [rbp+180h+var_F8], xmm0
0x180103975  movsd   [rbp+180h+var_E8], xmm7
0x18010397d  movsd   [rbp+180h+var_E0], xmm6
0x180103985  mov     rbx, [r13+10h]
0x180103989  mov     rax, [rdi]
0x18010398c  mov     rcx, rdi
0x18010398f  mov     rax, [rax+68h]
0x180103993  call    cs:__guard_dispatch_icall_fptr
0x180103999  xor     r13d, r13d
0x18010399c  mov     [rbp+180h+var_188], r13
0x1801039a0  mov     [rbp+180h+var_180], rax
0x1801039a4  mov     [rbp+180h+var_178], rbx
0x1801039a8  movdqa  xmm0, cs:__xmm@00000000000000003ff0000000000000
0x1801039b0  movups  [rbp+180h+var_D8], xmm0
0x1801039b7  movdqa  xmm1, cs:__xmm@3ff00000000000000000000000000000
0x1801039bf  movups  [rbp+180h+var_C8], xmm1
0x1801039c6  xorps   xmm0, xmm0
0x1801039c9  movups  [rbp+180h+var_B8], xmm0
0x1801039d0  lea     rax, [rbp+180h+var_D8]
0x1801039d7  mov     [rsp+280h+var_248], rax
0x1801039dc  mov     rax, [rbp+180h+arg_0]
0x1801039e3  mov     qword ptr [rsp+280h+var_258], rax
0x1801039e8  lea     rax, [rbp+180h+var_F8]
0x1801039ef  mov     [rsp+280h+var_260], rax
0x1801039f4  lea     r9, [rbp+180h+var_188]
0x1801039f8  mov     rbx, [rbp+180h+var_1C0]
0x1801039fc  mov     r8, rbx
0x1801039ff  lea     rdx, [rbp+180h+arg_0]
0x180103a06  mov     rcx, rsi
0x180103a09  call    ?ApplyStandardOverflowEffects@RenderableRenderer@SVG@Mso@@QEBA?AV?$TCntPtr@$$CBUIEffect@GEL@@@3@AEBUIEffect@GEL@@AEBVStyleResolveChain@23@AEBURect@6@PEBU86@_NPEBU?$TAffine3x3@N@Math@@@Z; Mso::SVG::RenderableRenderer::ApplyStandardOverflowEffects(GEL::IEffect const &,Mso::SVG::StyleResolveChain const &,GEL::Rect const &,GEL::Rect const *,bool,Math::TAffine3x3<double> const *)
0x180103a0e  nop
0x180103a0f  test    r12b, r12b
0x180103a12  jz      short loc_180103A34
0x180103a14  lea     r8, [rbp+180h+var_140]
0x180103a18  lea     rdx, [rbp+180h+var_1B8]
0x180103a1c  lea     rcx, [rbp+180h+var_1E8]
0x180103a20  call    ?GetTransformedBounds@Rect@GEL@@QEBA?AU12@AEBU?$TAffine3x3@N@Math@@@Z; GEL::Rect::GetTransformedBounds(Math::TAffine3x3<double> const &)
0x180103a25  movups  xmm0, xmmword ptr [rax]
0x180103a28  movups  [rbp+180h+var_1E8], xmm0
0x180103a2c  movups  xmm1, xmmword ptr [rax+10h]
0x180103a30  movups  [rbp+180h+var_1D8], xmm1
0x180103a34  mov     rcx, [r15+20h]; this
0x180103a38  test    rcx, rcx
0x180103a3b  jz      loc_180103C22
0x180103a41  xor     r9d, r9d; bool
0x180103a44  xor     r8d, r8d; struct GEL::Rect *
0x180103a47  lea     rdx, [rbp+180h+var_1E8]; struct GEL::Rect *
0x180103a4b  call    ?EndRendering@RenderableRenderer@SVG@Mso@@QEBAXAEBURect@GEL@@PEAU45@_N@Z; Mso::SVG::RenderableRenderer::EndRendering(GEL::Rect const &,GEL::Rect *,bool)
0x180103a50  mov     rdi, [rbp+180h+arg_0]
0x180103a57  test    rdi, rdi
0x180103a5a  jz      loc_180103AFC
0x180103a60  movdqa  xmm0, cs:__xmm@000000000000000040c29a8000000000
0x180103a68  movups  [rbp+180h+var_A8], xmm0
0x180103a6f  movdqa  xmm1, cs:__xmm@40c29a80000000000000000000000000
0x180103a77  movups  [rbp+180h+var_98], xmm1
0x180103a7e  xorps   xmm0, xmm0
0x180103a81  movups  [rbp+180h+var_88], xmm0
0x180103a88  xorps   xmm1, xmm1
0x180103a8b  movups  [rbp+180h+var_1B8], xmm1
0x180103a8f  movsd   qword ptr [rbp+180h+var_1A8], xmm7
0x180103a94  movsd   qword ptr [rbp+180h+var_1A8+8], xmm6
0x180103a99  lea     rax, [rbp+180h+var_140]
0x180103a9d  mov     [rsp+280h+var_260], rax
0x180103aa2  lea     r9, [rbp+180h+var_A8]
0x180103aa9  mov     r8, rdi
0x180103aac  lea     rdx, [rbp+180h+var_1B8]
0x180103ab0  lea     rcx, [rsp+280h+var_210]
0x180103ab5  call    cs:__imp_?Create@IBrushEffect@GEL@@SA?AV?$TCntPtr@UIBrushEffect@GEL@@@Ofc@@AEBU?$TRect@N@Math@@AEBUIEffect@2@AEBU?$TAffine3x3@N@6@PEBU86@@Z; GEL::IBrushEffect::Create(Math::TRect<double> const &,GEL::IEffect const &,Math::TAffine3x3<double> const &,Math::TAffine3x3<double> const *)
0x180103abb  mov     rcx, [rax]
0x180103abe  mov     [r14], rcx
0x180103ac1  test    rcx, rcx
0x180103ac4  jz      short loc_180103AD2
0x180103ac6  mov     rax, [rcx]
0x180103ac9  mov     rax, [rax]
0x180103acc  call    cs:__guard_dispatch_icall_fptr
0x180103ad2  mov     rcx, qword ptr [rsp+280h+var_210]
0x180103ad7  test    rcx, rcx
0x180103ada  jz      short loc_180103AEA
0x180103adc  mov     rax, [rcx]
0x180103adf  mov     rax, [rax+8]
0x180103ae3  call    cs:__guard_dispatch_icall_fptr
  ... truncated ...
```
