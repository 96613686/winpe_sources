# Mso::SVG::MaskRenderer::ComputeMask(Mso::SVG::StyleResolveChain const &,GEL::Rect const *)

- ea: `0x1801028d0`
- end: `0x180102d32`
- name: `?ComputeMask@MaskRenderer@SVG@Mso@@QEAA?AV?$TCntPtr@UIEffect@GEL@@@3@AEBVStyleResolveChain@23@PEBURect@GEL@@@Z`
- size: `1122`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800422f0`

## callees

- `0x18003fd34`
- `0x18004e740`
- `0x1801028d0`
- `0x1801395a4`
- `0x18013e010`
- `0x18013f738`
- `0x18013f760`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180102d1d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180102d2b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180102d1d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180102d2b`
- `gfx!?Create@IEffectClip@GEL@@SA?AV?$TCntPtr@UIEffectClip@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TRect@N@Math@@W4CombineMode@2@@Z` at `0x180102bae`
- `gfx!?Create@IEffectClip@GEL@@SA?AV?$TCntPtr@UIEffectClip@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TRect@N@Math@@W4CombineMode@2@@Z` at `0x180102bae`
- `gfx!?Create@IEffectAlphaModulateBinary@GEL@@SA?AV?$TCntPtr@UIEffectAlphaModulateBinary@GEL@@@Ofc@@AEBUIEffect@2@0@Z` at `0x180102c3d`
- `gfx!?Create@IEffectAlphaModulateBinary@GEL@@SA?AV?$TCntPtr@UIEffectAlphaModulateBinary@GEL@@@Ofc@@AEBUIEffect@2@0@Z` at `0x180102c3d`
- `gfx!?Create@IEffectLuminanceToAlpha@GEL@@SA?AV?$TCntPtr@UIEffectLuminanceToAlpha@GEL@@@Ofc@@AEBUIEffect@2@W4ColorSpace@2@@Z` at `0x180102bdf`
- `gfx!?Create@IEffectLuminanceToAlpha@GEL@@SA?AV?$TCntPtr@UIEffectLuminanceToAlpha@GEL@@@Ofc@@AEBUIEffect@2@W4ColorSpace@2@@Z` at `0x180102bdf`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall Mso::SVG::MaskRenderer::ComputeMask(__int64 a1, _QWORD *a2, __int64 a3, double *a4)
{
  __int64 v8; // rbx
  int v9; // esi
  int v10; // r12d
  Mso::SVG::LengthResolver *p_si128; // rsi
  __int64 v12; // rax
  __m128i *v13; // rsi
  __int64 v14; // rax
  double v15; // xmm6_8
  double v16; // xmm7_8
  double v17; // xmm8_8
  double v18; // xmm0_8
  double v19; // xmm9_8
  double v20; // xmm2_8
  double v21; // xmm1_8
  __int64 v22; // rcx
  double v23; // xmm4_8
  double v24; // xmm2_8
  double v25; // xmm3_8
  _QWORD *EffectOrEmptyContainer; // rax
  __int64 *v27; // rax
  __int64 v28; // r9
  __int64 v29; // rbx
  __int64 v30; // rcx
  __int64 v31; // rcx
  _QWORD *v32; // rax
  __int64 *v33; // rax
  __int64 v34; // rsi
  __int64 v35; // rdx
  __int64 v36; // rdi
  _QWORD *v37; // rax
  void (__fastcall ***v38)(_QWORD); // r15
  __int64 v40; // [rsp+38h] [rbp-D0h] BYREF
  __int128 v41; // [rsp+40h] [rbp-C8h] BYREF
  _QWORD v42[2]; // [rsp+50h] [rbp-B8h] BYREF
  Mso::SVG::LengthResolver *v43; // [rsp+60h] [rbp-A8h]
  __int64 v44; // [rsp+68h] [rbp-A0h]
  double v45; // [rsp+78h] [rbp-90h] BYREF
  __int128 v46; // [rsp+80h] [rbp-88h]
  double v47; // [rsp+90h] [rbp-78h]
  double v48; // [rsp+98h] [rbp-70h]
  double v49; // [rsp+A0h] [rbp-68h]
  __m128i si128; // [rsp+A8h] [rbp-60h] BYREF
  double v51; // [rsp+B8h] [rbp-50h]
  _QWORD v52[13]; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v53; // [rsp+158h] [rbp+50h] BYREF

  v8 = *(_QWORD *)(a1 + 16);
  if ( !v8 )
  {
LABEL_44:
    CrashWithRecovery(0x1E3C3843u, 0);
    JUMPOUT(0x180102D31LL);
  }
  _castguard_slow_path_check_user_handled(*(_QWORD *)v8, 8048, 0);
  v9 = *(_DWORD *)(v8 + 328);
  LODWORD(v53) = v9;
  v10 = *(_DWORD *)(v8 + 332);
  if ( !*(_BYTE *)(v8 + 400) )
  {
    *a2 = 0;
    return a2;
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v51 = sqrt_0(1.0);
  if ( v9 )
    p_si128 = (Mso::SVG::LengthResolver *)&si128;
  else
    p_si128 = *(Mso::SVG::LengthResolver **)(a3 + 16);
  v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 104LL))(v8);
  v42[0] = 0;
  v42[1] = v12;
  v43 = p_si128;
  if ( v10 )
    v13 = &si128;
  else
    v13 = *(__m128i **)(a3 + 16);
  v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 104LL))(v8);
  v52[0] = 0;
  v52[1] = v14;
  v52[2] = v13;
  v15 = Mso::SVG::LengthResolver::ResolveLength(
          v43,
          (const struct Mso::SVG::Length *)(v8 + 336),
          (const struct Mso::SVG::StyleResolveChain *)v42);
  v16 = Mso::SVG::LengthResolver::ResolveLength(
          v43,
          (const struct Mso::SVG::Length *)(v8 + 352),
          (const struct Mso::SVG::StyleResolveChain *)v42);
  v17 = Mso::SVG::LengthResolver::ResolveLength(
          v43,
          (const struct Mso::SVG::Length *)(v8 + 368),
          (const struct Mso::SVG::StyleResolveChain *)v42);
  v18 = Mso::SVG::LengthResolver::ResolveLength(
          v43,
          (const struct Mso::SVG::Length *)(v8 + 384),
          (const struct Mso::SVG::StyleResolveChain *)v42);
  v19 = v18;
  if ( (_DWORD)v53 == 1 )
  {
    v20 = a4[2] - *a4;
    v17 = v17 * v20;
    v21 = a4[3] - a4[1];
    v19 = v18 * v21;
    v15 = v15 * v20 + *a4;
    v16 = v16 * v21 + a4[1];
  }
  v41 = 0;
  v22 = *(_QWORD *)(a1 + 32);
  if ( !v22 )
  {
    CrashWithRecovery(0x1E3C3840u, 0);
    goto LABEL_44;
  }
  (*(void (__fastcall **)(__int64, __int128 *, _QWORD *, _QWORD, _QWORD))(*(_QWORD *)v22 + 32LL))(v22, &v41, v52, 0, 0);
  v44 = 0;
  if ( v10 == 1 )
  {
    v23 = a4[1];
    v24 = a4[3] - v23;
    v25 = *a4;
    v45 = a4[2] - *a4;
    v46 = 0;
    v47 = v24;
    v48 = v25 + 0.0;
    v49 = v23 + 0.0;
    EffectOrEmptyContainer = (_QWORD *)GEL::EffectAccumulator::GetEffectOrEmptyContainer(&v41, &v40);
    v27 = (__int64 *)Mso::SVG::ApplyTransform(&v53, *EffectOrEmptyContainer, &v45);
    v29 = *v27;
    *v27 = 0;
    v44 = v29;
    v30 = v53;
    if ( v53 )
    {
      v53 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 8LL))(v30);
    }
    v31 = v40;
  }
  else
  {
    v32 = (_QWORD *)GEL::EffectAccumulator::GetEffectOrEmptyContainer(&v41, &v53);
    v29 = *v32;
    if ( *v32 )
      (**(void (__fastcall ***)(_QWORD))v29)(*v32);
    v44 = v29;
    v31 = v53;
  }
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
  v45 = v15;
  *(double *)&v46 = v16;
  *((double *)&v46 + 1) = v17 + v15;
  v47 = v19 + v16;
  LOBYTE(v28) = 1;
  v33 = (__int64 *)GEL::IEffectClip::Create(&v53, v29, &v45, v28);
  v34 = *v33;
  *v33 = 0;
  v52[3] = v34;
  if ( v53 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 8LL))(v53);
  v36 = *(_QWORD *)GEL::IEffectLuminanceToAlpha::Create(&v40, v34, 0);
  v52[4] = v36;
  if ( v36 )
    (**(void (__fastcall ***)(__int64))v36)(v36);
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 8LL))(v40);
  LOBYTE(v35) = 1;
  if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v34 + 88LL))(v34, v35) )
  {
    *a2 = v36;
  }
  else
  {
    v37 = (_QWORD *)GEL::IEffectAlphaModulateBinary::Create(&v53, v36, v34);
    v38 = (void (__fastcall ***)(_QWORD))*v37;
    if ( *v37 )
      (**v38)(*v37);
    if ( v53 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 8LL))(v53);
    *a2 = v38;
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 8LL))(v36);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 8LL))(v34);
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
  if ( *((_QWORD *)&v41 + 1) )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v41 + 1) + 8LL))(*((_QWORD *)&v41 + 1));
  if ( (_QWORD)v41 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v41 + 8LL))(v41);
  return a2;
}

```

## disassembly

```asm
0x1801028d0  mov     rax, rsp
0x1801028d3  mov     [rax+10h], rbx
0x1801028d7  mov     [rax+18h], rsi
0x1801028db  mov     [rax+20h], rdi
0x1801028df  push    rbp
0x1801028e0  push    r12
0x1801028e2  push    r13
0x1801028e4  push    r14
0x1801028e6  push    r15
0x1801028e8  lea     rbp, [rax-48h]
0x1801028ec  sub     rsp, 120h
0x1801028f3  movaps  xmmword ptr [rax-38h], xmm6
0x1801028f7  movaps  xmmword ptr [rax-48h], xmm7
0x1801028fb  movaps  xmmword ptr [rax-58h], xmm8
0x180102900  movaps  xmmword ptr [rax-68h], xmm9
0x180102905  mov     rdi, r9
0x180102908  mov     r15, r8
0x18010290b  mov     r14, rdx
0x18010290e  mov     r13, rcx
0x180102911  mov     rbx, [rcx+10h]
0x180102915  test    rbx, rbx
0x180102918  jz      loc_180102D24
0x18010291e  xor     r8d, r8d
0x180102921  mov     edx, 1F70h
0x180102926  mov     rcx, [rbx]
0x180102929  call    __castguard_slow_path_check_user_handled
0x18010292e  mov     esi, [rbx+148h]
0x180102934  mov     dword ptr [rbp+40h+arg_0], esi
0x180102937  mov     r12d, [rbx+14Ch]
0x18010293e  cmp     byte ptr [rbx+190h], 0
0x180102945  jnz     short loc_180102953
0x180102947  mov     qword ptr [r14], 0
0x18010294e  jmp     loc_180102CDE
0x180102953  movdqa  xmm0, cs:__xmm@3ff00000000000003ff0000000000000
0x18010295b  movups  [rbp+40h+var_A0], xmm0
0x18010295f  movsd   xmm0, cs:__real@3ff0000000000000; X
0x180102967  call    sqrt_0
0x18010296c  movsd   [rbp+40h+var_90], xmm0
0x180102971  test    esi, esi
0x180102973  jnz     short loc_18010297B
0x180102975  mov     rsi, [r15+10h]
0x180102979  jmp     short loc_18010297F
0x18010297b  lea     rsi, [rbp+40h+var_A0]
0x18010297f  mov     rax, [rbx]
0x180102982  mov     rcx, rbx
0x180102985  mov     rax, [rax+68h]
0x180102989  call    cs:__guard_dispatch_icall_fptr
0x18010298f  mov     [rsp+140h+var_F8], 0
0x180102998  mov     [rsp+140h+var_F0], rax
0x18010299d  mov     [rsp+140h+var_E8], rsi
0x1801029a2  test    r12d, r12d
0x1801029a5  jnz     short loc_1801029AD
0x1801029a7  mov     rsi, [r15+10h]
0x1801029ab  jmp     short loc_1801029B1
0x1801029ad  lea     rsi, [rbp+40h+var_A0]
0x1801029b1  mov     rax, [rbx]
0x1801029b4  mov     rcx, rbx
0x1801029b7  mov     rax, [rax+68h]
0x1801029bb  call    cs:__guard_dispatch_icall_fptr
0x1801029c1  mov     [rbp+40h+var_88], 0
0x1801029c9  mov     [rbp+40h+var_80], rax
0x1801029cd  mov     [rbp+40h+var_78], rsi
0x1801029d1  lea     rdx, [rbx+150h]; struct Mso::SVG::Length *
0x1801029d8  lea     r8, [rsp+140h+var_F8]; struct Mso::SVG::StyleResolveChain *
0x1801029dd  mov     rcx, [rsp+140h+var_E8]; this
0x1801029e2  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x1801029e7  movaps  xmm6, xmm0
0x1801029ea  lea     rdx, [rbx+160h]; struct Mso::SVG::Length *
0x1801029f1  lea     r8, [rsp+140h+var_F8]; struct Mso::SVG::StyleResolveChain *
0x1801029f6  mov     rcx, [rsp+140h+var_E8]; this
0x1801029fb  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x180102a00  movaps  xmm7, xmm0
0x180102a03  lea     rdx, [rbx+170h]; struct Mso::SVG::Length *
0x180102a0a  lea     r8, [rsp+140h+var_F8]; struct Mso::SVG::StyleResolveChain *
0x180102a0f  mov     rcx, [rsp+140h+var_E8]; this
0x180102a14  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x180102a19  movaps  xmm8, xmm0
0x180102a1d  lea     rdx, [rbx+180h]; struct Mso::SVG::Length *
0x180102a24  lea     r8, [rsp+140h+var_F8]; struct Mso::SVG::StyleResolveChain *
0x180102a29  mov     rcx, [rsp+140h+var_E8]; this
0x180102a2e  call    ?ResolveLength@LengthResolver@SVG@Mso@@AEBANAEBULength@23@AEBVStyleResolveChain@23@@Z; Mso::SVG::LengthResolver::ResolveLength(Mso::SVG::Length const &,Mso::SVG::StyleResolveChain const &)
0x180102a33  movaps  xmm9, xmm0
0x180102a37  cmp     dword ptr [rbp+40h+arg_0], 1
0x180102a3b  jnz     short loc_180102A6B
0x180102a3d  movsd   xmm2, qword ptr [rdi+10h]
0x180102a42  subsd   xmm2, qword ptr [rdi]
0x180102a46  mulsd   xmm8, xmm2
0x180102a4b  movsd   xmm1, qword ptr [rdi+18h]
0x180102a50  subsd   xmm1, qword ptr [rdi+8]
0x180102a55  mulsd   xmm9, xmm1
0x180102a5a  mulsd   xmm6, xmm2
0x180102a5e  addsd   xmm6, qword ptr [rdi]
0x180102a62  mulsd   xmm7, xmm1
0x180102a66  addsd   xmm7, qword ptr [rdi+8]
0x180102a6b  xorps   xmm0, xmm0
0x180102a6e  movdqu  [rsp+140h+var_110+8], xmm0
0x180102a74  mov     rcx, [r13+20h]
0x180102a78  xor     r13d, r13d
0x180102a7b  test    rcx, rcx
0x180102a7e  jz      loc_180102D16
0x180102a84  mov     rax, [rcx]
0x180102a87  mov     [rsp+140h+var_120], r13
0x180102a8c  xor     r9d, r9d
0x180102a8f  lea     r8, [rbp+40h+var_88]
0x180102a93  lea     rdx, [rsp+140h+var_110+8]
0x180102a98  mov     rax, [rax+20h]
0x180102a9c  call    cs:__guard_dispatch_icall_fptr
0x180102aa2  mov     [rsp+140h+var_E0], r13
0x180102aa7  lea     rcx, [rsp+140h+var_110+8]
0x180102aac  cmp     r12d, 1
0x180102ab0  jnz     loc_180102B42
0x180102ab6  movsd   xmm4, qword ptr [rdi+8]
0x180102abb  movsd   xmm2, qword ptr [rdi+18h]
0x180102ac0  subsd   xmm2, xmm4
0x180102ac4  movsd   xmm3, qword ptr [rdi]
0x180102ac8  movsd   xmm0, qword ptr [rdi+10h]
0x180102acd  subsd   xmm0, xmm3
0x180102ad1  movsd   qword ptr [rsp+140h+var_D0], xmm0
0x180102ad7  xorps   xmm1, xmm1
0x180102ada  movups  [rsp+140h+var_D0+8], xmm1
0x180102adf  movsd   [rbp+40h+var_B8], xmm2
0x180102ae4  xorps   xmm0, xmm0
0x180102ae7  addsd   xmm3, xmm0
0x180102aeb  movsd   [rbp+40h+var_B0], xmm3
0x180102af0  addsd   xmm4, xmm0
0x180102af4  movsd   [rbp+40h+var_A8], xmm4
0x180102af9  lea     rdx, [rsp+140h+var_110]
0x180102afe  call    ?GetEffectOrEmptyContainer@EffectAccumulator@GEL@@QEAA?AV?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@XZ; GEL::EffectAccumulator::GetEffectOrEmptyContainer(void)
0x180102b03  lea     r8, [rsp+140h+var_D0]
0x180102b08  mov     rdx, [rax]
0x180102b0b  lea     rcx, [rbp+40h+arg_0]
0x180102b0f  nop
0x180102b10  call    ?ApplyTransform@SVG@Mso@@YA?AV?$TCntPtr@$$CBUIEffect@GEL@@@2@AEBUIEffect@GEL@@AEBU?$TAffine3x3@N@Math@@@Z; Mso::SVG::ApplyTransform(GEL::IEffect const &,Math::TAffine3x3<double> const &)
0x180102b15  mov     rbx, [rax]
0x180102b18  mov     [rax], r13
0x180102b1b  mov     [rsp+140h+var_E0], rbx
0x180102b20  mov     rcx, [rbp+40h+arg_0]
0x180102b24  test    rcx, rcx
0x180102b27  jz      short loc_180102B3B
0x180102b29  mov     [rbp+40h+arg_0], r13
0x180102b2d  mov     rax, [rcx]
0x180102b30  mov     rax, [rax+8]
0x180102b34  call    cs:__guard_dispatch_icall_fptr
0x180102b3a  nop
0x180102b3b  mov     rcx, qword ptr [rsp+140h+var_110]
0x180102b40  jmp     short loc_180102B6B
0x180102b42  lea     rdx, [rbp+40h+arg_0]
0x180102b46  call    ?GetEffectOrEmptyContainer@EffectAccumulator@GEL@@QEAA?AV?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@XZ; GEL::EffectAccumulator::GetEffectOrEmptyContainer(void)
0x180102b4b  mov     rbx, [rax]
0x180102b4e  test    rbx, rbx
0x180102b51  jz      short loc_180102B62
0x180102b53  mov     rax, [rbx]
0x180102b56  mov     rcx, rbx
0x180102b59  mov     rax, [rax]
0x180102b5c  call    cs:__guard_dispatch_icall_fptr
0x180102b62  mov     [rsp+140h+var_E0], rbx
0x180102b67  mov     rcx, [rbp+40h+arg_0]
0x180102b6b  test    rcx, rcx
0x180102b6e  jz      short loc_180102B7D
0x180102b70  mov     rax, [rcx]
0x180102b73  mov     rax, [rax+8]
0x180102b77  call    cs:__guard_dispatch_icall_fptr
0x180102b7d  movsd   qword ptr [rsp+140h+var_D0], xmm6
0x180102b83  movsd   qword ptr [rsp+140h+var_D0+8], xmm7
0x180102b89  addsd   xmm8, xmm6
0x180102b8e  movsd   [rbp+40h+var_C0], xmm8
0x180102b94  addsd   xmm9, xmm7
0x180102b99  movsd   [rbp+40h+var_B8], xmm9
0x180102b9f  mov     r9b, 1
0x180102ba2  lea     r8, [rsp+140h+var_D0]
0x180102ba7  mov     rdx, rbx
0x180102baa  lea     rcx, [rbp+40h+arg_0]
0x180102bae  call    cs:__imp_?Create@IEffectClip@GEL@@SA?AV?$TCntPtr@UIEffectClip@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TRect@N@Math@@W4CombineMode@2@@Z; GEL::IEffectClip::Create(GEL::IEffect const &,Math::TRect<double> const &,GEL::CombineMode)
0x180102bb4  mov     rsi, [rax]
0x180102bb7  mov     [rax], r13
0x180102bba  mov     [rbp+40h+var_70], rsi
0x180102bbe  mov     rcx, [rbp+40h+arg_0]
0x180102bc2  test    rcx, rcx
0x180102bc5  jz      short loc_180102BD4
0x180102bc7  mov     rax, [rcx]
0x180102bca  mov     rax, [rax+8]
0x180102bce  call    cs:__guard_dispatch_icall_fptr
0x180102bd4  xor     r8d, r8d
0x180102bd7  mov     rdx, rsi
0x180102bda  lea     rcx, [rsp+140h+var_110]
0x180102bdf  call    cs:__imp_?Create@IEffectLuminanceToAlpha@GEL@@SA?AV?$TCntPtr@UIEffectLuminanceToAlpha@GEL@@@Ofc@@AEBUIEffect@2@W4ColorSpace@2@@Z; GEL::IEffectLuminanceToAlpha::Create(GEL::IEffect const &,GEL::ColorSpace)
0x180102be5  mov     rdi, [rax]
0x180102be8  mov     [rbp+40h+var_68], rdi
0x180102bec  test    rdi, rdi
0x180102bef  jz      short loc_180102C01
0x180102bf1  mov     rax, [rdi]
0x180102bf4  mov     rcx, rdi
0x180102bf7  mov     rax, [rax]
0x180102bfa  call    cs:__guard_dispatch_icall_fptr
0x180102c00  nop
0x180102c01  mov     rcx, qword ptr [rsp+140h+var_110]
0x180102c06  test    rcx, rcx
0x180102c09  jz      short loc_180102C18
0x180102c0b  mov     rax, [rcx]
0x180102c0e  mov     rax, [rax+8]
0x180102c12  call    cs:__guard_dispatch_icall_fptr
0x180102c18  mov     rax, [rsi]
0x180102c1b  mov     dl, 1
0x180102c1d  mov     rcx, rsi
0x180102c20  mov     rax, [rax+58h]
0x180102c24  call    cs:__guard_dispatch_icall_fptr
0x180102c2a  test    al, al
0x180102c2c  jz      short loc_180102C33
0x180102c2e  mov     [r14], rdi
0x180102c31  jmp     short loc_180102C89
0x180102c33  mov     r8, rsi
0x180102c36  mov     rdx, rdi
0x180102c39  lea     rcx, [rbp+40h+arg_0]
0x180102c3d  call    cs:__imp_?Create@IEffectAlphaModulateBinary@GEL@@SA?AV?$TCntPtr@UIEffectAlphaModulateBinary@GEL@@@Ofc@@AEBUIEffect@2@0@Z; GEL::IEffectAlphaModulateBinary::Create(GEL::IEffect const &,GEL::IEffect const &)
0x180102c43  mov     r15, [rax]
0x180102c46  test    r15, r15
0x180102c49  jz      short loc_180102C5A
0x180102c4b  mov     rax, [r15]
0x180102c4e  mov     rcx, r15
0x180102c51  mov     rax, [rax]
0x180102c54  call    cs:__guard_dispatch_icall_fptr
0x180102c5a  mov     rcx, [rbp+40h+arg_0]
0x180102c5e  test    rcx, rcx
0x180102c61  jz      short loc_180102C70
0x180102c63  mov     rax, [rcx]
0x180102c66  mov     rax, [rax+8]
0x180102c6a  call    cs:__guard_dispatch_icall_fptr
0x180102c70  mov     [r14], r15
0x180102c73  test    rdi, rdi
0x180102c76  jz      short loc_180102C89
0x180102c78  mov     rax, [rdi]
0x180102c7b  mov     rcx, rdi
0x180102c7e  mov     rax, [rax+8]
0x180102c82  call    cs:__guard_dispatch_icall_fptr
0x180102c88  nop
0x180102c89  mov     rax, [rsi]
0x180102c8c  mov     rcx, rsi
0x180102c8f  mov     rax, [rax+8]
0x180102c93  call    cs:__guard_dispatch_icall_fptr
0x180102c99  test    rbx, rbx
0x180102c9c  jz      short loc_180102CB0
0x180102c9e  mov     rax, [rbx]
0x180102ca1  mov     rcx, rbx
0x180102ca4  mov     rax, [rax+8]
0x180102ca8  call    cs:__guard_dispatch_icall_fptr
0x180102cae  nop
0x180102caf  nop
0x180102cb0  mov     rcx, [rsp+140h+var_100]
0x180102cb5  test    rcx, rcx
0x180102cb8  jz      short loc_180102CC7
0x180102cba  mov     rax, [rcx]
0x180102cbd  mov     rax, [rax+8]
0x180102cc1  call    cs:__guard_dispatch_icall_fptr
0x180102cc7  mov     rcx, qword ptr [rsp+140h+var_110+8]
0x180102ccc  test    rcx, rcx
0x180102ccf  jz      short loc_180102CDE
0x180102cd1  mov     rax, [rcx]
0x180102cd4  mov     rax, [rax+8]
0x180102cd8  call    cs:__guard_dispatch_icall_fptr
0x180102cde  mov     rax, r14
0x180102ce1  lea     r11, [rsp+140h+var_20]
0x180102ce9  mov     rbx, [r11+38h]
0x180102ced  mov     rsi, [r11+40h]
0x180102cf1  mov     rdi, [r11+48h]
0x180102cf5  movaps  xmm6, xmmword ptr [r11-10h]
0x180102cfa  movaps  xmm7, xmmword ptr [r11-20h]
0x180102cff  movaps  xmm8, xmmword ptr [r11-30h]
0x180102d04  movaps  xmm9, xmmword ptr [r11-40h]
0x180102d09  mov     rsp, r11
0x180102d0c  pop     r15
0x180102d0e  pop     r14
0x180102d10  pop     r13
0x180102d12  pop     r12
0x180102d14  pop     rbp
0x180102d15  retn
0x180102d16  xor     edx, edx
0x180102d18  mov     ecx, 1E3C3840h
0x180102d1d  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180102d23  nop
0x180102d24  xor     edx, edx
0x180102d26  mov     ecx, 1E3C3843h
0x180102d2b  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
