# Mso::SVG::PatternRenderer::ComputePaint(Mso::SVG::StyleResolveChain const &,GEL::Rect const *,bool)

- ea: `0x1801035b0`
- end: `0x180103c27`
- name: `?ComputePaint@PatternRenderer@SVG@Mso@@UEAA?AV?$TCntPtr@UIBrush@GEL@@@3@AEBVStyleResolveChain@23@PEBURect@GEL@@_N@Z`
- size: `1655`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `broker_com_uri`

## callees

- `0x180002bec`
- `0x180007230`
- `0x18003f8f0`
- `0x18003fd34`
- `0x180041d48`
- `0x180041de0`
- `0x180043428`
- `0x1800435e0`
- `0x18004e740`
- `0x18004eb84`
- `0x18004f518`
- `0x180100ec4`
- `0x180100f98`
- `0x180100ff0`
- `0x180101044`
- `0x180101094`
- `0x1801010e4`
- `0x180101134`
- `0x1801035b0`
- `0x1801395a4`
- `0x180139618`
- `0x18013e010`
- `0x18013f738`
- `0x18013f760`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180103c04`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180103c12`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180103c20`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180103c04`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180103c12`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180103c20`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180103b97`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180103bb1`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180103b97`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180103bb1`
- `gfx!?Create@IBrushEffect@GEL@@SA?AV?$TCntPtr@UIBrushEffect@GEL@@@Ofc@@AEBU?$TRect@N@Math@@AEBUIEffect@2@AEBU?$TAffine3x3@N@6@PEBU86@@Z` at `0x180103a8e`
- `gfx!?Create@IBrushEffect@GEL@@SA?AV?$TCntPtr@UIBrushEffect@GEL@@@Ofc@@AEBU?$TRect@N@Math@@AEBUIEffect@2@AEBU?$TAffine3x3@N@6@PEBU86@@Z` at `0x180103a8e`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
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
  Mso::SVG::LengthResolver *v52[2]; // [rsp+78h] [rbp-90h] BYREF
  __int128 v53; // [rsp+88h] [rbp-80h] BYREF
  __int128 v54; // [rsp+98h] [rbp-70h]
  __int128 v55; // [rsp+A8h] [rbp-60h] BYREF
  double v56; // [rsp+B8h] [rbp-50h]
  double v57; // [rsp+C0h] [rbp-48h]
  __int64 v58; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v59; // [rsp+D8h] [rbp-30h] BYREF
  __m128i v60; // [rsp+E0h] [rbp-28h] BYREF
  __m128i v61; // [rsp+F0h] [rbp-18h]
  __int128 v62; // [rsp+100h] [rbp-8h]
  _QWORD v63[3]; // [rsp+110h] [rbp+8h] BYREF
  __m128i v64; // [rsp+128h] [rbp+20h] BYREF
  __m128i v65; // [rsp+138h] [rbp+30h]
  __int128 v66; // [rsp+148h] [rbp+40h]
  _OWORD v67[2]; // [rsp+158h] [rbp+50h] BYREF
  double v68; // [rsp+178h] [rbp+70h]
  double v69; // [rsp+180h] [rbp+78h]
  __m128i si128; // [rsp+188h] [rbp+80h] BYREF
  double v71; // [rsp+198h] [rbp+90h]
  __int128 v72; // [rsp+1A0h] [rbp+98h] BYREF
  double v73; // [rsp+1B0h] [rbp+A8h]
  double v74; // [rsp+1B8h] [rbp+B0h]
  __m128i v75; // [rsp+1C0h] [rbp+B8h]
  __m128i v76; // [rsp+1D0h] [rbp+C8h]
  __int128 v77; // [rsp+1E0h] [rbp+D8h]
  struct GEL::Rect *v78; // [rsp+278h] [rbp+170h] BYREF

  v8 = *(_QWORD *)(a1 + 16);
  if ( !v8 )
    goto LABEL_52;
  _castguard_slow_path_check_user_handled(*(_QWORD *)v8, 7696, 0);
  if ( !*(_BYTE *)(v8 + 320) )
    goto LABEL_49;
  Units = Mso::SVG::PatternContext::GetUnits(v8);
  LODWORD(v78) = Mso::SVG::PatternContext::GetContentUnits(v8);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v71 = sqrt_0(1.0);
  if ( Units )
    p_si128 = (Mso::SVG::LengthResolver *)&si128;
  else
    p_si128 = *(Mso::SVG::LengthResolver **)(a3 + 16);
  v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 104LL))(v8);
  v50[0] = 0;
  v50[1] = v11;
  v51 = p_si128;
  v12 = (const struct Mso::SVG::Length *)Mso::SVG::PatternContext::GetX(v8, &v55);
  v13 = Mso::SVG::LengthResolver::ResolveLength(p_si128, v12, (const struct Mso::SVG::StyleResolveChain *)v50);
  v14 = (const struct Mso::SVG::Length *)Mso::SVG::PatternContext::GetY(v8, &v55);
  v15 = Mso::SVG::LengthResolver::ResolveLength(v51, v14, (const struct Mso::SVG::StyleResolveChain *)v50);
  Width = (const struct Mso::SVG::Length *)Mso::SVG::PatternContext::GetWidth(v8, &v55);
  v17 = Mso::SVG::LengthResolver::ResolveLength(v51, Width, (const struct Mso::SVG::StyleResolveChain *)v50);
  Height = (const struct Mso::SVG::Length *)Mso::SVG::PatternContext::GetHeight(v8, &v55);
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
  v64 = _mm_load_si128((const __m128i *)&_xmm);
  v65 = _mm_load_si128((const __m128i *)&_xmm);
  v66 = 0;
  if ( *(_BYTE *)(a1 + 72) )
  {
    Mso::SVG::ViewboxAdapter::CalculateViewboxTransform(a1 + 40, v19, v20, &v64);
  }
  else if ( (_DWORD)v78 == 1 )
  {
    v26 = a4[3] - a4[1];
    *(double *)v64.m128i_i64 = a4[2] - *a4;
    *(double *)&v65.m128i_i64[1] = v26;
  }
  v49 = 0;
  Mso::SVG::PatternContext::GetChildren(v8, &v48, &v49);
  Mso::SVG::RenderableRenderer::Create(&v47, v48, *(_QWORD *)(a1 + 24));
  v27 = v47;
  if ( v47 )
    _castguard_slow_path_check_user_handled(*(_QWORD *)v47, 13376, 144);
  else
    v27 = 0;
  *(_QWORD *)&v55 = v27;
  if ( v27 )
    (**(void (__fastcall ***)(Mso::SVG::RenderableRenderer *))v27)(v27);
  v53 = 0;
  v54 = 0;
  v78 = 0;
  if ( !v27 )
  {
LABEL_53:
    CrashWithRecovery(0x1E3C3840u, 0);
    JUMPOUT(0x180103C26LL);
  }
  v28 = Mso::SVG::RenderableRenderer::BeginRendering(
          v27,
          (const struct Mso::SVG::StyleResolveChain *)v50,
          (struct GEL::Rect *)&v53,
          0,
          &v78,
          v46);
  *(_OWORD *)v52 = 0;
  Mso::SVG::ContainerRenderer::RenderChildren(
    v27,
    (struct GEL::EffectAccumulator *)v52,
    (const struct Mso::SVG::StyleResolveChain *)v50,
    v78,
    0);
  v67[0] = _mm_load_si128((const __m128i *)&_xmm);
  v67[1] = _mm_load_si128((const __m128i *)&_xmm);
  v68 = v13;
  v69 = v15;
  v60 = *(__m128i *)(a1 + 88);
  v61 = *(__m128i *)(a1 + 104);
  v62 = *(_OWORD *)(a1 + 120);
  Math::operator*=<double,double,0>(v67, &v60);
  EffectOrEmptyContainer = (_QWORD *)GEL::EffectAccumulator::GetEffectOrEmptyContainer(v52, &v58);
  Mso::SVG::ApplyTransform(&v59, *EffectOrEmptyContainer, &v64);
  if ( v58 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 8LL))(v58);
  if ( v28 )
  {
    TransformedBounds = (__int128 *)GEL::Rect::GetTransformedBounds(&v53, &v60, &v64);
    v53 = *TransformedBounds;
    v54 = TransformedBounds[1];
  }
  v72 = 0;
  v73 = v24;
  v74 = v25;
  v31 = *(_QWORD *)(a3 + 16);
  v32 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 104LL))(v8);
  v63[0] = 0;
  v63[1] = v32;
  v63[2] = v31;
  v75 = _mm_load_si128((const __m128i *)&_xmm);
  v76 = _mm_load_si128((const __m128i *)&_xmm);
  v77 = 0;
  v33 = v59;
  Mso::SVG::RenderableRenderer::ApplyStandardOverflowEffects(
    (_DWORD)v27,
    (unsigned int)&v78,
    v59,
    (unsigned int)v63,
    (__int64)&v72,
    (__int64)v78);
  if ( v28 )
  {
    v34 = (__int128 *)GEL::Rect::GetTransformedBounds(&v53, &v60, v67);
    v53 = *v34;
    v54 = v34[1];
  }
  v35 = *(Mso::SVG::RenderableRenderer **)(a1 + 32);
  if ( !v35 )
  {
    CrashWithRecovery(0x1E3C3840u, 0);
LABEL_52:
    CrashWithRecovery(0x1E3C3843u, 0);
    goto LABEL_53;
  }
  Mso::SVG::RenderableRenderer::EndRendering(v35, (const struct GEL::Rect *)&v53, 0, 0);
  v36 = v78;
  if ( v78 )
  {
    v60 = _mm_load_si128((const __m128i *)&_xmm);
    v61 = _mm_load_si128((const __m128i *)&_xmm);
    v62 = 0;
    v55 = 0;
    v56 = v24;
    v57 = v25;
    v37 = (void (__fastcall ****)(_QWORD))GEL::IBrushEffect::Create(&v78, &v55, v78, &v60, v67);
    v38 = *v37;
    *a2 = *v37;
    if ( v38 )
      (**v38)(v38);
    if ( v78 )
      (*(void (__fastcall **)(struct GEL::Rect *))(*(_QWORD *)v78 + 8LL))(v78);
    (*(void (__fastcall **)(struct GEL::Rect *))(*(_QWORD *)v36 + 8LL))(v36);
  }
  else
  {
    *a2 = 0;
  }
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 8LL))(v33);
  if ( v52[1] )
    (*(void (__fastcall **)(Mso::SVG::LengthResolver *))(*(_QWORD *)v52[1] + 8LL))(v52[1]);
  if ( v52[0] )
    (*(void (__fastcall **)(Mso::SVG::LengthResolver *))(*(_QWORD *)v52[0] + 8LL))(v52[0]);
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
0x1801035b0  mov     rax, rsp
0x1801035b3  mov     [rax+10h], rbx
0x1801035b7  mov     [rax+18h], rsi
0x1801035bb  mov     [rax+20h], rdi
0x1801035bf  push    rbp
0x1801035c0  push    r12
0x1801035c2  push    r13
0x1801035c4  push    r14
0x1801035c6  push    r15
0x1801035c8  lea     rbp, [rax-168h]
0x1801035cf  sub     rsp, 240h
0x1801035d6  movaps  xmmword ptr [rax-38h], xmm6
0x1801035da  movaps  xmmword ptr [rax-48h], xmm7
0x1801035de  movaps  xmmword ptr [rax-58h], xmm8
0x1801035e3  movaps  xmmword ptr [rax-68h], xmm9
0x1801035e8  movaps  xmmword ptr [rax-78h], xmm10
0x1801035ed  mov     rbx, r9
0x1801035f0  mov     r13, r8
0x1801035f3  mov     r14, rdx
0x1801035f6  mov     r15, rcx
0x1801035f9  mov     rdi, [rcx+10h]
0x1801035fd  test    rdi, rdi
0x180103600  jz      loc_180103C0B
0x180103606  xor     r8d, r8d
0x180103609  mov     edx, 1E10h
0x18010360e  mov     rcx, [rdi]
0x180103611  call    __castguard_slow_path_check_user_handled
0x180103616  cmp     byte ptr [rdi+140h], 0
0x18010361d  jz      loc_180103BB9
0x180103623  mov     rcx, rdi
0x180103626  call    ?GetUnits@PatternContext@SVG@Mso@@QEBA?AW4PatternUnits@23@XZ; Mso::SVG::PatternContext::GetUnits(void)
0x18010362b  mov     r12d, eax
0x18010362e  mov     rcx, rdi
0x180103631  call    ?GetContentUnits@PatternContext@SVG@Mso@@QEBA?AW4PatternUnits@23@XZ; Mso::SVG::PatternContext::GetContentUnits(void)
0x180103636  mov     dword ptr [rbp+160h+arg_0], eax
0x18010363c  movdqa  xmm0, cs:__xmm@3ff00000000000003ff0000000000000
0x180103644  movups  [rbp+160h+var_E0], xmm0
0x18010364b  movsd   xmm6, cs:__real@3ff0000000000000
0x180103653  movaps  xmm0, xmm6; X
0x180103656  call    sqrt_0
0x18010365b  movsd   [rbp+160h+var_D0], xmm0
0x180103663  test    r12d, r12d
0x180103666  jnz     short loc_18010366E
0x180103668  mov     rsi, [r13+10h]
0x18010366c  jmp     short loc_180103675
0x18010366e  lea     rsi, [rbp+160h+var_E0]
0x180103675  mov     rax, [rdi]
0x180103678  mov     rcx, rdi
0x18010367b  mov     rax, [rax+68h]
0x18010367f  call    cs:__guard_dispatch_icall_fptr
0x180103685  mov     [rsp+260h+var_208], 0
0x18010368e  mov     [rsp+260h+var_200], rax
0x180103693  mov     [rsp+260h+var_1F8], rsi
0x180103698  lea     rdx, [rbp+160h+var_1C0]
0x18010369c  mov     rcx, rdi
0x18010369f  call    ?GetX@PatternContext@SVG@Mso@@QEBA?AULength@23@XZ; Mso::SVG::PatternContext::GetX(void)
0x1801036a4  lea     r8, [rsp+260h+var_208]; struct Mso::SVG::StyleResolveChain *
0x1801036a9  mov     rdx, rax; struct Mso::SVG::Length *
0x1801036ac  mov     rcx, [rsp+260h+var_1F8]; this
0x1801036b1  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x1801036b6  movaps  xmm9, xmm0
0x1801036ba  lea     rdx, [rbp+160h+var_1C0]
0x1801036be  mov     rcx, rdi
0x1801036c1  call    ?GetY@PatternContext@SVG@Mso@@QEBA?AULength@23@XZ; Mso::SVG::PatternContext::GetY(void)
0x1801036c6  lea     r8, [rsp+260h+var_208]; struct Mso::SVG::StyleResolveChain *
0x1801036cb  mov     rdx, rax; struct Mso::SVG::Length *
0x1801036ce  mov     rcx, [rsp+260h+var_1F8]; this
0x1801036d3  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x1801036d8  movaps  xmm10, xmm0
0x1801036dc  lea     rdx, [rbp+160h+var_1C0]
0x1801036e0  mov     rcx, rdi
0x1801036e3  call    ?GetWidth@PatternContext@SVG@Mso@@QEBA?AULength@23@XZ; Mso::SVG::PatternContext::GetWidth(void)
0x1801036e8  lea     r8, [rsp+260h+var_208]; struct Mso::SVG::StyleResolveChain *
0x1801036ed  mov     rdx, rax; struct Mso::SVG::Length *
0x1801036f0  mov     rcx, [rsp+260h+var_1F8]; this
0x1801036f5  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x1801036fa  movaps  xmm8, xmm0
0x1801036fe  lea     rdx, [rbp+160h+var_1C0]
0x180103702  mov     rcx, rdi
0x180103705  call    ?GetHeight@PatternContext@SVG@Mso@@QEBA?AULength@23@XZ; Mso::SVG::PatternContext::GetHeight(void)
0x18010370a  lea     r8, [rsp+260h+var_208]; struct Mso::SVG::StyleResolveChain *
0x18010370f  mov     rdx, rax; struct Mso::SVG::Length *
0x180103712  mov     rcx, [rsp+260h+var_1F8]; this
0x180103717  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x18010371c  cmp     r12d, 1
0x180103720  jnz     short loc_180103753
0x180103722  movsd   xmm2, qword ptr [rbx+10h]
0x180103727  subsd   xmm2, qword ptr [rbx]
0x18010372b  mulsd   xmm8, xmm2
0x180103730  movsd   xmm1, qword ptr [rbx+18h]
0x180103735  subsd   xmm1, qword ptr [rbx+8]
0x18010373a  mulsd   xmm0, xmm1
0x18010373e  mulsd   xmm9, xmm2
0x180103743  addsd   xmm9, qword ptr [rbx]
0x180103748  mulsd   xmm10, xmm1
0x18010374d  addsd   xmm10, qword ptr [rbx+8]
0x180103753  xorps   xmm1, xmm1
0x180103756  comisd  xmm1, xmm8
0x18010375b  jnb     loc_180103BB9
0x180103761  comisd  xmm1, xmm0
0x180103765  jnb     loc_180103BB9
0x18010376b  movaps  xmm7, xmm6
0x18010376e  maxsd   xmm7, xmm8
0x180103773  maxsd   xmm6, xmm0
0x180103777  movdqa  xmm0, cs:__xmm@00000000000000003ff0000000000000
0x18010377f  movups  [rbp+160h+var_140], xmm0
0x180103783  movdqa  xmm1, cs:__xmm@3ff00000000000000000000000000000
0x18010378b  movups  [rbp+160h+var_130], xmm1
0x18010378f  xorps   xmm0, xmm0
0x180103792  movups  [rbp+160h+var_120], xmm0
0x180103796  lea     rcx, [r15+28h]
0x18010379a  cmp     byte ptr [rcx+20h], 0
0x18010379e  jz      short loc_1801037B1
0x1801037a0  lea     r9, [rbp+160h+var_140]
0x1801037a4  movaps  xmm2, xmm6
0x1801037a7  movaps  xmm1, xmm7
0x1801037aa  call    ?CalculateViewboxTransform@ViewboxAdapter@SVG@Mso@@QEBAXNNAEAU?$TAffine3x3@N@Math@@@Z; Mso::SVG::ViewboxAdapter::CalculateViewboxTransform(double,double,Math::TAffine3x3<double> &)
0x1801037af  jmp     short loc_1801037D7
0x1801037b1  cmp     dword ptr [rbp+160h+arg_0], 1
0x1801037b8  jnz     short loc_1801037D7
0x1801037ba  movsd   xmm1, qword ptr [rbx+18h]
0x1801037bf  subsd   xmm1, qword ptr [rbx+8]
0x1801037c4  movsd   xmm0, qword ptr [rbx+10h]
0x1801037c9  subsd   xmm0, qword ptr [rbx]
0x1801037cd  movsd   qword ptr [rbp+160h+var_140], xmm0
0x1801037d2  movsd   qword ptr [rbp+160h+var_130+8], xmm1
0x1801037d7  xor     ebx, ebx
0x1801037d9  mov     [rsp+260h+var_210], rbx
0x1801037de  lea     r8, [rsp+260h+var_210]
0x1801037e3  lea     rdx, [rsp+260h+var_218]
0x1801037e8  mov     rcx, rdi
0x1801037eb  call    ?GetChildren@PatternContext@SVG@Mso@@QEBA?AV?$TCntPtr@VContainerContext@SVG@Mso@@@3@AEAV?$TCntPtr@$$CBVStyle@SVG@Mso@@@3@@Z; Mso::SVG::PatternContext::GetChildren(Mso::TCntPtr<Mso::SVG::Style const> &)
0x1801037f0  nop
0x1801037f1  mov     r8, [r15+18h]
0x1801037f5  mov     rdx, [rsp+260h+var_218]
0x1801037fa  lea     rcx, [rsp+260h+var_220]
0x1801037ff  call    ?Create@RenderableRenderer@SVG@Mso@@SA?AV?$TCntPtr@VRenderableRenderer@SVG@Mso@@@3@AEAVRenderableContext@23@AEAVEnvironmentRenderer@23@@Z; Mso::SVG::RenderableRenderer::Create(Mso::SVG::RenderableContext &,Mso::SVG::EnvironmentRenderer &)
0x180103804  nop
0x180103805  mov     rsi, [rsp+260h+var_220]
0x18010380a  test    rsi, rsi
0x18010380d  jz      short loc_180103824
0x18010380f  mov     edx, 3440h
0x180103814  mov     r8d, 90h
0x18010381a  mov     rcx, [rsi]
0x18010381d  call    __castguard_slow_path_check_user_handled
0x180103822  jmp     short loc_180103827
0x180103824  mov     rsi, rbx
0x180103827  mov     qword ptr [rbp+160h+var_1C0], rsi
0x18010382b  test    rsi, rsi
0x18010382e  jz      short loc_180103840
0x180103830  mov     rax, [rsi]
0x180103833  mov     rcx, rsi
0x180103836  mov     rax, [rax]
0x180103839  call    cs:__guard_dispatch_icall_fptr
0x18010383f  nop
0x180103840  xorps   xmm0, xmm0
0x180103843  movups  [rbp+160h+var_1E0], xmm0
0x180103847  xorps   xmm1, xmm1
0x18010384a  movups  [rbp+160h+var_1D0], xmm1
0x18010384e  mov     [rbp+160h+arg_0], rbx
0x180103855  test    rsi, rsi
0x180103858  jz      loc_180103C19
0x18010385e  lea     rax, [rbp+160h+arg_0]
0x180103865  mov     [rsp+260h+var_240], rax; struct GEL::Rect **
0x18010386a  xor     r9d, r9d; struct GEL::Rect *
0x18010386d  lea     r8, [rbp+160h+var_1E0]; struct GEL::Rect *
0x180103871  lea     rdx, [rsp+260h+var_208]; struct Mso::SVG::StyleResolveChain *
0x180103876  mov     rcx, rsi; this
0x180103879  call    ?BeginRendering@RenderableRenderer@SVG@Mso@@QEBA_NAEBVStyleResolveChain@23@AEAURect@GEL@@PEBU56@AEAPEAU56@_N@Z; Mso::SVG::RenderableRenderer::BeginRendering(Mso::SVG::StyleResolveChain const &,GEL::Rect &,GEL::Rect const *,GEL::Rect * &,bool)
0x18010387e  mov     r12b, al
0x180103881  xorps   xmm0, xmm0
0x180103884  movdqu  xmmword ptr [rsp+260h+var_1F8+8], xmm0
0x18010388a  mov     [rsp+260h+var_240], rbx; struct GEL::IColorResolver *
0x18010388f  mov     r9, [rbp+160h+arg_0]; struct GEL::Rect *
0x180103896  lea     r8, [rsp+260h+var_208]; struct Mso::SVG::StyleResolveChain *
0x18010389b  lea     rdx, [rsp+260h+var_1F8+8]; struct GEL::EffectAccumulator *
0x1801038a0  mov     rcx, rsi; this
0x1801038a3  call    ?RenderChildren@ContainerRenderer@SVG@Mso@@QEAAXAEAVEffectAccumulator@GEL@@AEBVStyleResolveChain@23@PEAURect@5@PEBUIColorResolver@5@@Z; Mso::SVG::ContainerRenderer::RenderChildren(GEL::EffectAccumulator &,Mso::SVG::StyleResolveChain const &,GEL::Rect *,GEL::IColorResolver const *)
0x1801038a8  movdqa  xmm0, cs:__xmm@00000000000000003ff0000000000000
0x1801038b0  movups  [rbp+160h+var_110], xmm0
0x1801038b4  movdqa  xmm1, cs:__xmm@3ff00000000000000000000000000000
0x1801038bc  movups  [rbp+160h+var_100], xmm1
0x1801038c0  movsd   [rbp+160h+var_F0], xmm9
0x1801038c6  movsd   [rbp+160h+var_E8], xmm10
0x1801038cc  movups  xmm0, xmmword ptr [r15+58h]
0x1801038d1  movups  [rbp+160h+var_188], xmm0
0x1801038d5  movups  xmm1, xmmword ptr [r15+68h]
0x1801038da  movups  [rbp+160h+var_178], xmm1
0x1801038de  movups  xmm0, xmmword ptr [r15+78h]
0x1801038e3  movups  [rbp+160h+var_168], xmm0
0x1801038e7  lea     rdx, [rbp+160h+var_188]
0x1801038eb  lea     rcx, [rbp+160h+var_110]
0x1801038ef  call    ??$?XNN$0A@@Math@@YAAEAU?$TAffine3x3@N@0@AEAU10@AEBU10@@Z; Math::operator*=<double,double,0>(Math::TAffine3x3<double> &,Math::TAffine3x3<double> const &)
0x1801038f4  lea     rdx, [rbp+160h+var_198]
0x1801038f8  lea     rcx, [rsp+260h+var_1F8+8]
0x1801038fd  call    ?GetEffectOrEmptyContainer@EffectAccumulator@GEL@@QEAA?AV?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@XZ; GEL::EffectAccumulator::GetEffectOrEmptyContainer(void)
0x180103902  nop
0x180103903  lea     r8, [rbp+160h+var_140]
0x180103907  mov     rdx, [rax]
0x18010390a  lea     rcx, [rbp+160h+var_190]
0x18010390e  call    ?ApplyTransform@SVG@Mso@@YA?AV?$TCntPtr@$$CBUIEffect@GEL@@@2@AEBUIEffect@GEL@@AEBU?$TAffine3x3@N@Math@@@Z; Mso::SVG::ApplyTransform(GEL::IEffect const &,Math::TAffine3x3<double> const &)
0x180103913  nop
0x180103914  mov     rcx, [rbp+160h+var_198]
0x180103918  test    rcx, rcx
0x18010391b  jz      short loc_18010392A
0x18010391d  mov     rax, [rcx]
0x180103920  mov     rax, [rax+8]
0x180103924  call    cs:__guard_dispatch_icall_fptr
0x18010392a  test    r12b, r12b
0x18010392d  jz      short loc_18010394F
0x18010392f  lea     r8, [rbp+160h+var_140]
0x180103933  lea     rdx, [rbp+160h+var_188]
0x180103937  lea     rcx, [rbp+160h+var_1E0]
0x18010393b  call    ?GetTransformedBounds@Rect@GEL@@QEBA?AU12@AEBU?$TAffine3x3@N@Math@@@Z; GEL::Rect::GetTransformedBounds(Math::TAffine3x3<double> const &)
0x180103940  movups  xmm0, xmmword ptr [rax]
0x180103943  movups  [rbp+160h+var_1E0], xmm0
0x180103947  movups  xmm1, xmmword ptr [rax+10h]
0x18010394b  movups  [rbp+160h+var_1D0], xmm1
0x18010394f  xorps   xmm0, xmm0
0x180103952  movups  [rbp+160h+var_C8], xmm0
0x180103959  movsd   [rbp+160h+var_B8], xmm7
0x180103961  movsd   [rbp+160h+var_B0], xmm6
0x180103969  mov     rbx, [r13+10h]
0x18010396d  mov     rax, [rdi]
0x180103970  mov     rcx, rdi
0x180103973  mov     rax, [rax+68h]
0x180103977  call    cs:__guard_dispatch_icall_fptr
0x18010397d  xor     r13d, r13d
0x180103980  mov     [rbp+160h+var_158], r13
0x180103984  mov     [rbp+160h+var_150], rax
0x180103988  mov     [rbp+160h+var_148], rbx
0x18010398c  movdqa  xmm0, cs:__xmm@00000000000000003ff0000000000000
0x180103994  movups  [rbp+160h+var_A8], xmm0
0x18010399b  movdqa  xmm1, cs:__xmm@3ff00000000000000000000000000000
0x1801039a3  movups  [rbp+160h+var_98], xmm1
0x1801039aa  xorps   xmm0, xmm0
0x1801039ad  movups  [rbp+160h+var_88], xmm0
0x1801039b4  lea     rax, [rbp+160h+var_A8]
0x1801039bb  mov     [rsp+260h+var_228], rax
0x1801039c0  mov     rax, [rbp+160h+arg_0]
0x1801039c7  mov     qword ptr [rsp+260h+var_238], rax
0x1801039cc  lea     rax, [rbp+160h+var_C8]
0x1801039d3  mov     [rsp+260h+var_240], rax
0x1801039d8  lea     r9, [rbp+160h+var_158]
0x1801039dc  mov     rbx, [rbp+160h+var_190]
0x1801039e0  mov     r8, rbx
0x1801039e3  lea     rdx, [rbp+160h+arg_0]
0x1801039ea  mov     rcx, rsi
0x1801039ed  call    ?ApplyStandardOverflowEffects@RenderableRenderer@SVG@Mso@@QEBA?AV?$TCntPtr@$$CBUIEffect@GEL@@@3@AEBUIEffect@GEL@@AEBVStyleResolveChain@23@AEBURect@6@PEBU86@_NPEBU?$TAffine3x3@N@Math@@@Z; Mso::SVG::RenderableRenderer::ApplyStandardOverflowEffects(GEL::IEffect const &,Mso::SVG::StyleResolveChain const &,GEL::Rect const &,GEL::Rect const *,bool,Math::TAffine3x3<double> const *)
0x1801039f2  test    r12b, r12b
0x1801039f5  jz      short loc_180103A17
0x1801039f7  lea     r8, [rbp+160h+var_110]
0x1801039fb  lea     rdx, [rbp+160h+var_188]
0x1801039ff  lea     rcx, [rbp+160h+var_1E0]
0x180103a03  call    ?GetTransformedBounds@Rect@GEL@@QEBA?AU12@AEBU?$TAffine3x3@N@Math@@@Z; GEL::Rect::GetTransformedBounds(Math::TAffine3x3<double> const &)
0x180103a08  movups  xmm0, xmmword ptr [rax]
0x180103a0b  movups  [rbp+160h+var_1E0], xmm0
0x180103a0f  movups  xmm1, xmmword ptr [rax+10h]
0x180103a13  movups  [rbp+160h+var_1D0], xmm1
0x180103a17  mov     rcx, [r15+20h]; this
0x180103a1b  test    rcx, rcx
0x180103a1e  jz      loc_180103BFD
0x180103a24  xor     r9d, r9d; bool
0x180103a27  xor     r8d, r8d; struct GEL::Rect *
0x180103a2a  lea     rdx, [rbp+160h+var_1E0]; struct GEL::Rect *
0x180103a2e  call    ?EndRendering@RenderableRenderer@SVG@Mso@@QEBAXAEBURect@GEL@@PEAU45@_N@Z; Mso::SVG::RenderableRenderer::EndRendering(GEL::Rect const &,GEL::Rect *,bool)
0x180103a33  mov     rdi, [rbp+160h+arg_0]
0x180103a3a  test    rdi, rdi
0x180103a3d  jz      loc_180103AD6
0x180103a43  movdqa  xmm0, cs:__xmm@000000000000000040c29a8000000000
0x180103a4b  movups  [rbp+160h+var_188], xmm0
0x180103a4f  movdqa  xmm1, cs:__xmm@40c29a80000000000000000000000000
0x180103a57  movups  [rbp+160h+var_178], xmm1
0x180103a5b  xorps   xmm0, xmm0
0x180103a5e  movups  [rbp+160h+var_168], xmm0
0x180103a62  xorps   xmm1, xmm1
0x180103a65  movups  [rbp+160h+var_1C0], xmm1
0x180103a69  movsd   [rbp+160h+var_1B0], xmm7
0x180103a6e  movsd   [rbp+160h+var_1A8], xmm6
0x180103a73  lea     rax, [rbp+160h+var_110]
0x180103a77  mov     [rsp+260h+var_240], rax
0x180103a7c  lea     r9, [rbp+160h+var_188]
0x180103a80  mov     r8, rdi
0x180103a83  lea     rdx, [rbp+160h+var_1C0]
0x180103a87  lea     rcx, [rbp+160h+arg_0]
0x180103a8e  call    cs:__imp_?Create@IBrushEffect@GEL@@SA?AV?$TCntPtr@UIBrushEffect@GEL@@@Ofc@@AEBU?$TRect@N@Math@@AEBUIEffect@2@AEBU?$TAffine3x3@N@6@PEBU86@@Z; GEL::IBrushEffect::Create(Math::TRect<double> const &,GEL::IEffect const &,Math::TAffine3x3<double> const &,Math::TAffine3x3<double> const *)
0x180103a94  mov     rcx, [rax]
0x180103a97  mov     [r14], rcx
0x180103a9a  test    rcx, rcx
0x180103a9d  jz      short loc_180103AAB
0x180103a9f  mov     rax, [rcx]
0x180103aa2  mov     rax, [rax]
0x180103aa5  call    cs:__guard_dispatch_icall_fptr
0x180103aab  mov     rcx, [rbp+160h+arg_0]
0x180103ab2  test    rcx, rcx
0x180103ab5  jz      short loc_180103AC4
0x180103ab7  mov     rax, [rcx]
0x180103aba  mov     rax, [rax+8]
0x180103abe  call    cs:__guard_dispatch_icall_fptr
0x180103ac4  mov     rax, [rdi]
  ... truncated ...
```
